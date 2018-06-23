---
title: Migrieren von Check- und Foreign Key-Einschränkungen | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine-imoltp
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e0a1a1e4-0062-4872-93c3-cd91b7a43c23
caps.latest.revision: 9
author: stevestein
ms.author: sstein
manager: jhubbard
ms.openlocfilehash: fdb1b87e74c93cbacca1f1d18fe4e5c25bc65256
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36048791"
---
# <a name="migrating-check-and-foreign-key-constraints"></a>Migrieren von Check- und Foreign Key-Einschränkungen
  Check- und foreign Key-Einschränkungen werden nicht unterstützt, [!INCLUDE[hek_2](../includes/hek-2-md.md)] in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]. Diese Konstrukte werden in der Regel zum Erzwingen der logischen Datenintegrität im Schema verwendet und können die Wartung von funktionalen Anwendungen auf Richtigkeit wichtig sein.  
  
 Logische Integrität überprüft wird, für eine Tabelle z. B. Check und foreign Key-Einschränkungen erfordern zusätzliche Verarbeitung auf Transaktionen und sollte im Allgemeinen für leistungsabhängigen Anwendungen vermieden werden. Allerdings bestehen solchen Überprüfungen aus für Ihre Anwendung von entscheidender Bedeutung, es zwei problemumgehungen.  
  
## <a name="checking-constraints-after-an-insert-update-or-delete-operation"></a>Überprüfen von Einschränkungen nach einem INSERT-, Update- oder Delete-Vorgang  
 Diese problemumgehung optimistischen, basiert auf der Annahme, dass die meisten Änderungen nicht die Einschränkungen verletzen. In dieser problemumgehung werden Daten zuerst geändert, bevor die Einschränkungen ausgewertet werden. Wenn eine Einschränkung verletzt wird, wäre es erkannt werden, jedoch wird die Änderung nicht rückgängig gemacht werden.  
  
 Diese problemumgehung hat den Vorteil, dass minimale Auswirkungen auf die Leistung, da Daten vorgenommenen Änderungen nicht von einschränkungsüberprüfungen blockiert wird. Wenn eine Änderung, die eine oder mehrere Einschränkungen verletzt auftritt, konnte der Prozess zum Rollback für diese Änderung sehr lange dauern.  
  
## <a name="enforcing-constraints-before-an-insert-update-or-delete-operation"></a>Erzwingen von Einschränkungen vor einer INSERT-, Update- oder Delete-Vorgang  
 Diese problemumgehung emuliert das Verhalten der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Einschränkungen. Die Einschränkungen überprüft werden, bevor der Datenänderung tritt auf, und die Transaktion beendet wird, wenn es sich bei einem Überprüfungsfehler. Diese Methode einem Leistungsverlust für datenänderungen, aber es wird sichergestellt, dass die Daten in einer Tabelle immer die Einschränkungen erfüllen.  
  
 Verwenden Sie dieses Problem zu umgehen, wenn logische Datenintegrität entscheidend, um die Richtigkeit ist und voraussichtlich Änderungen, die eine Einschränkung verletzen. Allerdings müssen zur Integrität zu gewährleisten, alle datenänderungen mithilfe von gespeicherten Prozeduren auftreten, die diese Erzwingungen enthalten. Änderungen durch Ad-hoc-Abfragen und andere gespeicherte Prozeduren erzwingt keine dieser Einschränkungen und daher verstößt gegen diese ohne Warnung.  
  
## <a name="sample-code"></a>Beispielcode  
 Die folgenden Beispiele basieren auf der AdventureWorks2012-Datenbank. Insbesondere in diesen Beispielen basiert auf der [Sales]. [SalesOrderDetail]-Tabelle und die zugehörigen Kontrollkästchen und foreign Key-Einschränkungen, zusätzlich zu den eindeutigen Index.  
  
 Die gespeicherten Prozeduren, die hier angegebene sind nur Inset Vorgänge. Gespeicherte Prozeduren für Update- und Löschvorgänge sollten haben ähnliche Strukturen.  
  
## <a name="table-definition-for-the-workarounds"></a>Tabelle (Definition) für die Problemumgehungen  
 Vor dem Konvertieren in eine Speicheroptimierte Tabelle, die Definition für [Sales]. [SalesOrderDetail] lautet wie folgt:  
  
```tsql  
USE [AdventureWorks2012]  
GO  
  
CREATE TABLE [Sales].[SalesOrderDetail]([SalesOrderID] [int] NOT NULL,  
   [SalesOrderDetailID] [int] IDENTITY(1,1) NOT NULL,  
   [CarrierTrackingNumber] [nvarchar](25) NULL,  
   [OrderQty] [smallint] NOT NULL,  
   [ProductID] [int] NOT NULL,  
   [SpecialOfferID] [int] NOT NULL,  
   [UnitPrice] [money] NOT NULL,  
   [UnitPriceDiscount] [money] NOT NULL CONSTRAINT [DF_SalesOrderDetail_UnitPriceDiscount]  DEFAULT ((0.0)),  
   [LineTotal]  AS (isnull(([UnitPrice]*((1.0)-[UnitPriceDiscount]))*[OrderQty],(0.0))),  
   [rowguid] [uniqueidentifier] ROWGUIDCOL  NOT NULL CONSTRAINT [DF_SalesOrderDetail_rowguid]  DEFAULT (newid()),  
   [ModifiedDate] [datetime] NOT NULL CONSTRAINT [DF_SalesOrderDetail_ModifiedDate]  DEFAULT (getdate()),  
 CONSTRAINT [PK_SalesOrderDetail_SalesOrderID_SalesOrderDetailID] PRIMARY KEY CLUSTERED   
(  
   [SalesOrderID] ASC,  
   [SalesOrderDetailID] ASC  
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]  
  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail]  WITH CHECK ADD  CONSTRAINT [FK_SalesOrderDetail_SalesOrderHeader_SalesOrderID] FOREIGN KEY([SalesOrderID])  
REFERENCES [Sales].[SalesOrderHeader] ([SalesOrderID])  
ON DELETE CASCADE  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail] CHECK CONSTRAINT [FK_SalesOrderDetail_SalesOrderHeader_SalesOrderID]  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail]  WITH CHECK ADD  CONSTRAINT [FK_SalesOrderDetail_SpecialOfferProduct_SpecialOfferIDProductID] FOREIGN KEY([SpecialOfferID], [ProductID])  
REFERENCES [Sales].[SpecialOfferProduct] ([SpecialOfferID], [ProductID])  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail] CHECK CONSTRAINT [FK_SalesOrderDetail_SpecialOfferProduct_SpecialOfferIDProductID]  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail]  WITH CHECK ADD  CONSTRAINT [CK_SalesOrderDetail_OrderQty] CHECK  (([OrderQty]>(0)))  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail] CHECK CONSTRAINT [CK_SalesOrderDetail_OrderQty]  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail]  WITH CHECK ADD  CONSTRAINT [CK_SalesOrderDetail_UnitPrice] CHECK  (([UnitPrice]>=(0.00)))  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail] CHECK CONSTRAINT [CK_SalesOrderDetail_UnitPrice]  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail]  WITH CHECK ADD  CONSTRAINT [CK_SalesOrderDetail_UnitPriceDiscount] CHECK  (([UnitPriceDiscount]>=(0.00)))  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail] CHECK CONSTRAINT [CK_SalesOrderDetail_UnitPriceDiscount]  
GO  
```  
  
 Nach dem Konvertieren in eine Speicheroptimierte Tabelle, die Definition für [Sales]. [SalesOrderDetail] lautet wie folgt:  
  
 Beachten Sie, Rowguid ist eine ROWGUIDCOL-Spalte nicht mehr, als in nicht unterstützt wird [!INCLUDE[hek_2](../includes/hek-2-md.md)]. Die Spalte wurde entfernt. Darüber hinaus "LineTotal" ist eine berechnete Spalte und außerhalb des gültigen Bereichs für diesen Artikel, sodass es auch entfernt wurde.  
  
```tsql  
USE [AdventureWorks2012]  
GO  
  
CREATE TABLE [Sales].[SalesOrderDetail]([SalesOrderID] [int] NOT NULL,  
   [SalesOrderDetailID] [int] IDENTITY(1,1) NOT NULL,  
   [CarrierTrackingNumber] [nvarchar](25) NULL,  
   [OrderQty] [smallint] NOT NULL,  
   [ProductID] [int] NOT NULL,  
   [SpecialOfferID] [int] NOT NULL,  
   [UnitPrice] [money] NOT NULL,  
   [UnitPriceDiscount] [money] NOT NULL CONSTRAINT [DF_SalesOrderDetail_UnitPriceDiscount]  DEFAULT ((0.0)),  
   [ModifiedDate] [datetime] NOT NULL CONSTRAINT [DF_SalesOrderDetail_ModifiedDate]  DEFAULT (getdate()),  
   CONSTRAINT [PK_SalesOrderDetail_SalesOrderID_SalesOrderDetailID] PRIMARY KEY NONCLUSTERED   
   (  
      [SalesOrderID] ASC,  
      [SalesOrderDetailID] ASC  
   ),  
   INDEX [AK_SalesOrderDetail_rowguid] NONCLUSTERED HASH ([rowguid]) WITH (BUCKET_COUNT = 1048576),  
   INDEX [IX_SalesOrderDetail_ProductId] NONCLUSTERED ([ProductId] ASC)) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
  
GO  
```  
  
## <a name="checking-constraints-after-an-insert-update-or-delete-operation"></a>Überprüfen von Einschränkungen nach einem INSERT-, Update- oder Delete-Vorgang  
  
```tsql  
USE AdventureWorks2012  
GO  
  
CREATE PROCEDURE Sales.usp_insert_SalesOrderDetails   
   @SalesOrderId int, @CarrierTrackingNumber nvarchar(25) = null, @OrderQty smallint, @ProductId int, @SpecialOfferID int,   
   @UnitPrice money, @UnitPriceDiscount money = 0.00, @ModifiedDate datetime = null  
AS  
BEGIN  
BEGIN TRANSACTION   
   -- handle defaults for the insert.  
   -- This is to make the insert logic less complex. Default constraints on the table should be in sync with this logic.  
   -- Conversely, you can write an INSERT statement for each case where one or more values for the three columns with default constraints are not specified.  
   IF @ModifiedDate = null SET @ModifiedDate = GETDATE()  
  
   -- Insert the row.  
   INSERT INTO Sales.SalesOrderDetail   
      (SalesOrderID, CarrierTrackingNumber, OrderQty, ProductID, SpecialOfferID, UnitPrice, UnitPriceDiscount, ModifiedDate)  
   VALUES   
      (@SalesOrderId, @CarrierTrackingNumber, @OrderQty, @ProductID, @SpecialOfferID, @UnitPrice, @UnitPriceDiscount, , @ModifiedDate)   
  
   -- Now handle constraints  
   DECLARE @violations TABLE   
   (   
      ConstraintName sysname,  
      ViolatedValue1 sql_variant,  
      ViolatedValue2 sql_variant  
   )  
  
   -- FK_SalesOrderDetail_SalesOrderHeader_SalesOrderID  
   IF NOT EXISTS (SELECT soh.SalesOrderId AS [Exists] FROM Sales.SalesOrderHeader soh WHERE soh.SalesOrderID = @SalesOrderId)   
      INSERT INTO @violations (ConstraintName, ViolatedValue1, ViolatedValue2)   
      VALUES (N'FK_SalesOrderDetail_SalesOrderHeader_SalesOrderID', @SalesOrderId, NULL)  
   -- FK_SalesOrderDetail_SpecialOfferProduct_SpecialOfferIDProductID  
   IF NOT EXISTS (SELECT sop.SpecialOfferID, sop.ProductID FROM [Sales].[SpecialOfferProduct] sop WHERE sop.SpecialOfferID = @SpecialOfferID AND sop.ProductID = @ProductId)  
      INSERT INTO @violations (ConstraintName, ViolatedValue1, ViolatedValue2)   
      VALUES (N'FK_SalesOrderDetail_SpecialOfferProduct_SpecialOfferIDProductID', @SpecialOfferId, @ProductId)  
   -- CK_SalesOrderDetail_OrderQty  
   IF NOT @OrderQty > 0   
      INSERT INTO @violations (ConstraintName, ViolatedValue1, ViolatedValue2)   
      VALUES (N'CK_SalesOrderDetail_OrderQty', @OrderQty, NULL)  
   -- CK_SalesOrderDetail_UnitPrice  
   IF NOT @UnitPrice >= 0.00  
      INSERT INTO @violations (ConstraintName, ViolatedValue1, ViolatedValue2)   
      VALUES (N'CK_SalesOrderDetail_UnitPrice', @UnitPrice, NULL)  
   -- CK_SalesOrderDetail_UnitPriceDiscout  
   IF NOT @UnitPriceDiscount >= 0.00  
      INSERT INTO @violations (ConstraintName, ViolatedValue1, ViolatedValue2)   
      VALUES (N'CK_SalesOrderDetail_UnitPriceDiscount', @UnitPriceDiscount, NULL)  
  
   -- Return a rowset containing violated constraints. On an item that doesn't violate anything, should return an empty rowset.  
   SELECT ConstraintName, ViolatedValue1, ViolatedValue2 FROM @violations  
   COMMIT TRANSACTION  
END  
```  
  
## <a name="enforcing-constraints-before-an-insert-update-or-delete-operation"></a>Durchsetzen Einschränkungen vor einer Einfügung, Update oder Löschvorgang  
  
```tsql  
USE AdventureWorks2012  
GO  
  
CREATE PROCEDURE Sales.usp_insert_SalesOrderDetails   
   @SalesOrderId int, @CarrierTrackingNumber nvarchar(25) = null, @OrderQty smallint, @ProductId int, @SpecialOfferID int,   
   @UnitPrice money, @UnitPriceDiscount money = 0.00, @ModifiedDate datetime = null  
AS  
BEGIN  
BEGIN TRY  
   BEGIN TRANSACTION  
   -- Verify the constraints first.  
   -- FK_SalesOrderDetail_SalesOrderHeader_SalesOrderID  
   IF NOT EXISTS (SELECT soh.SalesOrderId FROM Sales.SalesOrderHeader soh WHERE soh.SalesOrderID = @SalesOrderId)   
      THROW 50547, N'This SalesOrderId does not exist in SalesOrderHeader', 1  
   -- FK_SalesOrderDetail_SpecialOfferProduct_SpecialOfferIDProductID  
   IF NOT EXISTS (SELECT sop.SpecialOfferID, sop.ProductID FROM [Sales].[SpecialOfferProduct] sop WHERE sop.SpecialOfferID = @SpecialOfferID AND sop.ProductID = @ProductId)  
      THROW 50547, N'This combination of SpecialOfferID and ProductID does not exist in SpecialOfferProduct', 1   
   -- CK_SalesOrderDetail_OrderQty  
   IF NOT @OrderQty > 0   
      THROW 50547, N'OrderQty must be greater than zero.', 1  
   -- CK_SalesOrderDetail_UnitPrice  
   IF NOT @UnitPrice >= 0.00  
      THROW 50547, N'UnitPrice cannot be negative.', 1  
   -- CK_SalesOrderDetail_UnitPriceDiscout  
   IF NOT @UnitPriceDiscount >= 0.00  
      THROW 50547, N'UnitPriceDiscount cannot be negative', 1  
  
   -- All verifications have now passed. Proceed to insert.  
  
   -- handle defaults for the insert.  
   -- This is to make the insert logic less complex. Default constraints on the table should be in sync with this logic.  
   -- Conversely, you can write an INSERT statement for each case where one or more values for the three columns with default constraints are not specified.  
  
   IF @ModifiedDate = null SET @ModifiedDate = GETDATE()  
  
   -- Calculate computed columnn and store it.  
   DECLARE @LineTotal numeric(38, 6)  
   SET @LineTotal = (isnull((@UnitPrice * ((1.0) - @UnitPriceDiscount)) * @OrderQty, (0.0)))  
  
   -- Insert the row.  
   INSERT INTO Sales.SalesOrderDetail   
      (SalesOrderID, CarrierTrackingNumber, OrderQty, ProductID, SpecialOfferID, UnitPrice, UnitPriceDiscount, ModifiedDate)  
   VALUES   
      (@SalesOrderId, @CarrierTrackingNumber, @OrderQty, @ProductID, @SpecialOfferID, @UnitPrice, @UnitPriceDiscount, @ModifiedDate)  
   COMMIT TRANSACTION  
END TRY  
BEGIN CATCH  
   IF @@TRANCOUNT > 0  
      ROLLBACK TRANSACTION  
      THROW;  
END CATCH  
END  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Migrieren zu In-Memory OLTP](../relational-databases/in-memory-oltp/migrating-to-in-memory-oltp.md)  
  
  