---
title: Partitionierung auf Anwendungsebene | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine-imoltp
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 162d1392-39d2-4436-a4d9-ee5c47864c5a
caps.latest.revision: 14
author: stevestein
ms.author: sstein
manager: jhubbard
ms.openlocfilehash: b3e1ff29abfaff5aa182019946c0a92d21395960
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36056251"
---
# <a name="application-level-partitioning"></a>Partitionierung auf Anwendungsebene
  Dieses Beispiel veranschaulicht die Partitionierung auf Anwendungsebene zum Speichern von Daten in einer speicheroptimierten Tabelle oder einer datenträgerbasierten Tabelle abhängig davon, ob die Reihenfolge vor oder nach einem bestimmten Datum liegt. Alle Aufträge, die älter oder gleich der *HotDate* befinden sich in der speicheroptimierten Tabelle und alle Aufträge vor dem *HotDate* sind in der datenträgerbasierten Tabelle. Angenommen, es liegt eine extreme OLTP-Arbeitsauslastung mit einer Vielzahl gleichzeitiger Transaktionen vor. Diese Geschäftsregel (neue Aufträge in einer speicheroptimierten Tabelle) muss erzwungen werden, selbst wenn einige gleichzeitige Transaktionen versuchen, das *hotDate*zu ändern.  
  
 Dieses Beispiel verwendet keine [Partitioned Tables](https://msdn.microsoft.com/library/ms190787.aspx) für die datenträgerbasierte Tabelle tut nachverfolgen ein expliziter Teilungspunkt zwischen den beiden Tabellen mithilfe einer dritten Tabelle. Mit dem Teilungspunkt kann sichergestellt werden, dass neu eingefügte Daten basierend auf dem Datum immer der richtigen Tabelle hinzugefügt werden. Er kann auch verwendet werden, um zu bestimmen, wo Daten gesucht werden sollen. Selbst verspätet eingegangene Daten werden in die richtige Tabelle eingefügt.  
  
 Ein Beispiel, die partitionierte Tabellen verwendet, finden Sie unter [Anwendungsmuster zur Partitionierung von speicheroptimierten Tabellen](memory-optimized-tables.md).  
  
## <a name="code-listing"></a>Codelisting  
  
```tsql  
USE MASTER  
GO  
  
IF DB_ID (N'partitionsample2') IS NOT NULL  
DROP DATABASE partitionsample2;  
GO  
  
CREATE DATABASE partitionsample2  
-- Enable the database for In-Memory OLTP.  
ALTER DATABASE partitionsample2 ADD FILEGROUP partitionsample2_mod CONTAINS MEMORY_OPTIMIZED_DATA  
ALTER DATABASE partitionsample2 ADD FILE( NAME = 'partitionsample2_mod' , FILENAME = 'c:\data\partitionsample2_mod') TO FILEGROUP partitionsample2_mod;  
GO  
  
USE partitionsample2  
GO  
  
-- Create a memory-optimized table for current (hot) orders.  
IF OBJECT_ID(N'SalesOrders_hot',N'U') IS NOT NULL  
   DROP TABLE [dbo].[SalesOrders_hot]  
  
CREATE TABLE dbo.SalesOrders_hot (  
   so_id INT NOT NULL PRIMARY KEY NONCLUSTERED,  
   cust_id INT NOT NULL,  
   so_date DATETIME2 NOT NULL INDEX ix_date NONCLUSTERED,  
   so_total MONEY NOT NULL,  
   INDEX ix_date_total NONCLUSTERED (so_date DESC, so_total DESC)  
) WITH (MEMORY_OPTIMIZED=ON)  
GO  
  
-- Create a disk-based table for archiving older (cold) orders.  
IF OBJECT_ID(N'SalesOrders_cold',N'U') IS NOT NULL  
   DROP TABLE [dbo].[SalesOrders_cold]  
  
CREATE TABLE dbo.SalesOrders_cold (  
   so_id INT NOT NULL PRIMARY KEY NONCLUSTERED,  
   cust_id INT NOT NULL,  
   so_date DATETIME2 NOT NULL INDEX ix_date NONCLUSTERED,  
   so_total MONEY NOT NULL,  
   INDEX ix_date_total NONCLUSTERED (so_date DESC, so_total DESC)  
)   
GO  
  
-- The date that splits old and new orders (hotDate)  
-- is stored in this memory-optimized table.  
IF OBJECT_ID(N'SalesOrders_hotDate') IS NOT NULL  
   DROP TABLE [dbo].[SalesOrders_hotDate]  
  
CREATE TABLE dbo.SalesOrders_hotDate (  
   hotDate DATETIME2 not null PRIMARY KEY NONCLUSTERED HASH WITH (BUCKET_COUNT = 1)  
)  WITH (MEMORY_OPTIMIZED=ON)  
GO  
  
-- STORED PROCEDURES  
  
-- Set the hotDate with SNAPSHOT ISOLATION so if other transactions  
-- try to update the hotDate, they will fail immediately due to a  
-- write/write conflict.  
IF OBJECT_ID(N'usp_SetHotDate') IS NOT NULL  
   DROP PROCEDURE [dbo].[usp_SetHotDate]  
GO  
  
CREATE PROCEDURE dbo.usp_SetHotDate (@newDate DATETIME2)  
   WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
   AS BEGIN ATOMIC WITH  
   (  
      TRANSACTION ISOLATION LEVEL = SNAPSHOT,  
      LANGUAGE = N'english'  
   )  
   DELETE FROM [dbo].[SalesOrders_hotDate]  
   INSERT INTO [dbo].[SalesOrders_hotDate] (hotDate) VALUES (@newDate)  
   END  
GO  
  
-- Get the orders up to the hotDate  
-- (Must be serializable, to prevent deleting rows that are not returned.)  
IF OBJECT_ID(N'usp_getHotData') IS NOT NULL  
   DROP PROCEDURE [dbo].[usp_GetHotData]  
GO  
  
CREATE PROCEDURE dbo.usp_GetHotData (@hotDate DATETIME2)  
   WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
   AS BEGIN ATOMIC WITH  
   (  
      TRANSACTION ISOLATION LEVEL = SERIALIZABLE,  
      LANGUAGE = N'english'  
   )  
   SELECT so_id, cust_id, so_date, so_total FROM dbo.SalesOrders_hot WHERE so_date < @hotDate  
   DELETE FROM dbo.SalesOrders_hot WHERE so_date < @hotDate  
END  
GO  
  
-- Inserts an order into the proper table depending on the current hotDate.  
-- It is important that the SP for retrieving the hotDate is REPEATABLEREAD, in order to ensure that  
-- the hotDate is not changed before the decision is made where to insert the order.  
-- Note that insert operations [in both disk-based and memory-optimized tables] are always fully isolated, so the transaction  
-- isolation level has no impact on the insert operations; this whole transaction is effectively REPEATABLEREAD.  
IF OBJECT_ID(N'usp_InsertOrder') IS NOT NULL  
   DROP PROCEDURE [dbo].[usp_InsertOrder]  
GO  
  
CREATE PROCEDURE dbo.usp_InsertOrder (@id int, @custID nvarchar(10), @orderDate DATETIME2, @orderTotal MONEY)  
   AS BEGIN  
   SET TRANSACTION ISOLATION LEVEL READ COMMITTED  
   BEGIN TRAN  
      -- get hot date under repeatableread isolation; this is to guarantee it does not change before the insert is executed  
      DECLARE @hotDate DATETIME2  
      SET @hotDate = (SELECT hotDate FROM [dbo].[SalesOrders_hotDate] WITH (REPEATABLEREAD))  
  
      IF (@orderDate >= @hotDate) BEGIN  
         INSERT INTO [dbo].[SalesOrders_hot] (so_id, cust_id, so_date, so_total) VALUES (@id, @custID, @orderDate, @orderTotal)  
      END  
      ELSE BEGIN  
         INSERT INTO [dbo].[SalesOrders_cold] (so_id, cust_id, so_date, so_total) VALUES (@id, @custID, @orderDate, @orderTotal)  
      END  
   COMMIT TRAN  
END  
GO  
  
-- Changes the hotDate and moves the rows between the tables as appropriate.  
-- The hotDate is updated in this transaction; this means that if the hotDate is changed by another transaction  
-- the update will fail due to a write/write conflict and the transaction is rolled back  
-- therefore, the initial (SNAPSHOT) access of the hotDate is effectively REPEATABLEREAD.  
IF OBJECT_ID(N'usp_ChangeHotDate') IS NOT NULL  
   DROP PROCEDURE [dbo].[usp_ChangeHotDate]  
GO  
  
CREATE PROCEDURE [dbo].[usp_ChangeHotDate](@newHotDate DATETIME2)  
AS BEGIN  
   SET TRANSACTION ISOLATION LEVEL READ COMMITTED  
   BEGIN TRAN  
      DECLARE @oldHotDate DATETIME2  
      SET @oldHotDate = (SELECT hotDate FROM [dbo].[SalesOrders_hotDate] WITH (SNAPSHOT))  
  
       -- get hot date under repeatableread isolation; this is to guarantee it does not change before the insert is executed  
      IF (@oldHotDate < @newHotDate) BEGIN  
         INSERT INTO [dbo].[SalesOrders_cold] EXEC usp_GetHotData @newHotDate  
      END  
      ELSE BEGIN  
         INSERT INTO [dbo].[SalesOrders_hot] SELECT * FROM SalesOrders_cold WITH (SERIALIZABLE) WHERE so_date >= @newHotDate  
         DELETE FROM [dbo].[SalesOrders_cold] WITH (SERIALIZABLE) WHERE so_date >= @newHotDate  
      END  
      EXEC [dbo].[usp_SetHotDate] @newHotDate  
   COMMIT TRAN  
END  
GO  
  
-- DEMO  
DELETE FROM [dbo].[SalesOrders_cold]  
GO  
  
-- Initialize the order split date.  
EXEC [dbo].[usp_SetHotDate] '2014-1-1'   
GO  
  
-- List the hotDate.  
SELECT * FROM [dbo].[SalesOrders_hotDate]  
GO  
  
EXEC [dbo].[usp_InsertOrder] 1, 1001, '2013-11-14', 150  
EXEC [dbo].[usp_InsertOrder] 2, 1001, '2014-3-4', 100  
EXEC [dbo].[usp_InsertOrder] 3, 1001, '2013-1-23', 250  
EXEC [dbo].[usp_InsertOrder] 4, 1001, '2013-8-6', 200  
EXEC [dbo].[usp_InsertOrder] 5, 1001, '2012-11-1', 150  
EXEC [dbo].[usp_InsertOrder] 6, 1001, '2014-1-9', 150  
EXEC [dbo].[usp_InsertOrder] 7, 1001, '2014-2-14', 95  
EXEC [dbo].[usp_InsertOrder] 8, 1001, '2012-1-17', 125  
EXEC [dbo].[usp_InsertOrder] 9, 1001, '2014-3-8', 100  
EXEC [dbo].[usp_InsertOrder] 10, 1001, '2013-9-24', 100  
GO  
  
-- List contents of the tables.  
-- Query new orders.  
SELECT * FROM [dbo].[SalesOrders_hot] ORDER BY so_date DESC  
  
-- Query old orders.  
SELECT * FROM [dbo].[SalesOrders_cold] ORDER BY so_date DESC  
  
-- Move the hot date to March 1, 2014.   
EXEC [dbo].[usp_ChangeHotDate] '2014-03-01'  
  
-- List the new hotDate  
SELECT * FROM [dbo].[SalesOrders_hotDate]  
GO  
  
-- Verify that all orders before March 1, 2014 were moved  
-- to the older order table and list the data.  
SELECT * FROM [dbo].[SalesOrders_hot] ORDER BY so_date DESC  
  
SELECT * FROM [dbo].[SalesOrders_cold] ORDER BY so_date DESC  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [In-Memory-OLTP &#40;Arbeitsspeicheroptimierung&#41;](in-memory-oltp-in-memory-optimization.md)   
 [Codebeispiele für In-Memory OLTP](in-memory-oltp-code-samples.md)  
  
  