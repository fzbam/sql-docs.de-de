---
title: Verwenden von Katalogfunktionen | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- ODBC, functions
- SQLLinkedCatalogs function
- SQL Server Native Client ODBC driver, catalog functions
- SQLLinkedServers function
- catalog functions [ODBC]
- functions [ODBC]
ms.assetid: 7773fb2e-06b5-4c4b-88e9-0ad9132ad273
caps.latest.revision: 35
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: d13d091efbadba5971360cc8a019b432770c228a
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36148591"
---
# <a name="using-catalog-functions"></a>Verwenden von Katalogfunktionen
  Alle Datenbanken verfügen über eine Struktur, die die in der Datenbank gespeicherten Daten enthält. Eine Definition dieser Struktur ist zusammen mit anderen Informationen, wie beispielsweise Berechtigungen, in einem Katalog gespeichert, der als Satz Systemtabellen implementiert und auch als Datenwörterbuch bezeichnet wird.  
  
 Die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC-Treiber ermöglicht einer Anwendung, die Datenbankstruktur durch Aufrufen von ODBC-Katalogfunktionen zu bestimmen. Katalogfunktionen geben Informationen in Resultsets zurück und werden mithilfe von gespeicherten Katalogprozeduren implementiert, um die Systemtabellen im Katalog abzufragen. Beispielsweise könnte eine Anwendung ein Resultset mit Informationen über alle Tabellen im System oder alle Spalten in einer bestimmten Tabelle anfordern. Die standardmäßigen ODBC-Katalogfunktionen dienen dazu, Kataloginformationen von der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Instanz abzurufen, mit der die Anwendung verbunden ist.  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] unterstützt verteilte Abfragen, in denen auf Daten aus mehreren heterogenen OLE DB-Datenquellen in einer einzigen Abfrage zugegriffen wird. Eine Methode des Zugriffs auf eine OLE DB-Datenquelle ist die Definition der Datenquelle als Verbindungsserver. Dies kann geschehen, indem Sie mithilfe von [Sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql). Nachdem der Verbindungsserver definiert wurde, kann in Transact-SQL-Anweisungen auf Objekte dieses Servers verwiesen werden. Dazu wird ein vierteiliger Name verwendet:  
  
 *linked_server_name.catalog.schema.object_name*.  
  
 Der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC-Treiber unterstützt zwei treiberspezifische Funktionen, die dazu dienen, Kataloginformationen von Verbindungsservern abzurufen:  
  
-   **SQLLinkedServers**  
  
     Gibt eine Liste der auf den lokalen Servern definierten Verbindungsserver zurück.  
  
-   **SQLLinkedCatalogs**  
  
     Gibt eine Liste der in einem Verbindungsserver enthaltenen Kataloge zurück.  
  
 Nachdem Sie einen Verbindungsservernamen und einen Katalognamen verfügen die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC-Treiber unterstützt beim Abrufen von Informationen aus dem Katalog mithilfe eines zweiteiligen Namens des *Linked_server_name ***.*** Katalog* für *CatalogName* auf die folgenden ODBC-Katalogfunktionen:  
  
-   **SQLColumnPrivileges**  
  
-   **SQLColumns**  
  
-   **SQLPrimaryKeys**  
  
-   **SQLStatistics**  
  
-   **SQLTablePrivileges**  
  
-   **SQLTables**  
  
 Der zweiteilige *Linked_server_name ***.*** Katalog* wird ebenfalls unterstützt *FKCatalogName* und *PKCatalogName* auf [SQLForeignKeys](../../native-client-odbc-api/sqlforeignkeys.md).  
  
 Zur Verwendung von SQLLinkedServers und SQLLinkedCatalogs sind die folgenden Dateien erforderlich:  
  
-   sqlncli.h  
  
     Enthält Funktionsprototypen und Konstantendefinitionen für die Verbindungsserverkatalogfunktionen. sqlncli.h muss in der ODBC-Anwendung enthalten sein und im Includepfad angegeben werden, wenn die Anwendung kompiliert wird.  
  
-   sqlncli11.lib  
  
     Muss im Bibliothekspfad des Linkers enthalten sein und als zu verknüpfende Datei angegeben werden. sqlncli11.lib wird zusammen mit dem [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber bereitgestellt.  
  
-   sqlncli11.dll  
  
     Muss zur Ausführungszeit verfügbar sein. sqlncli11.dll wird zusammen mit den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC-Treiber.  
  
## <a name="see-also"></a>Siehe auch  
 [SQL Server Native Client &#40;ODBC&#41;](sql-server-native-client-odbc.md)   
 [SQLColumnPrivileges](../../native-client-odbc-api/sqlcolumnprivileges.md)   
 [SQLColumns](../../native-client-odbc-api/sqlcolumns.md)   
 [SQLPrimaryKeys](../../native-client-odbc-api/sqlprimarykeys.md)   
 [SQLTablePrivileges](../../native-client-odbc-api/sqltableprivileges.md)   
 [SQLTables](../../native-client-odbc-api/sqltables.md)   
 [SQLStatistics](../../statistics/statistics.md)  
  
  