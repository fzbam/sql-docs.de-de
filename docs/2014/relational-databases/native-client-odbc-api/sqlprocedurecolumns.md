---
title: SQLProcedureColumns | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLProcedureColumns function
ms.assetid: 6671e180-0072-4de5-90f5-314306d2ba9c
caps.latest.revision: 50
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: de18cc3a646e9aefa8ffaf5d07a8379be0588c3f
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36050111"
---
# <a name="sqlprocedurecolumns"></a>SQLProcedureColumns
  `SQLProcedureColumns` Gibt eine Zeile, die den Rückgabewert Berichtsattribute aller [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gespeicherte Prozeduren.  
  
 `SQLProcedureColumns` Gibt SQL_SUCCESS zurück, unabhängig davon, ob Werte für vorhanden *CatalogName*, *SchemaName*, *ProcName*, oder *ColumnName* Parameter. **SQLFetch** gibt SQL_NO_DATA zurück, wenn in diesen Parametern ungültige Werte verwendet werden.  
  
 `SQLProcedureColumns` kann in einem statischen Servercursor ausgeführt werden. Wenn `SQLProcedureColumns` in einem aktualisierbaren Cursor (dynamischer Cursor oder Keysetcursor) ausgeführt wird, wird SQL_SUCCESS_WITH_INFO zurückgegeben. Das bedeutet, dass der Cursortyp geändert wurde.  
  
 Die folgende Tabelle enthält die Spalten zurückgegebenes Resultset und wie sie erweitert worden sein, um die Behandlung der **Udt** und **Xml** Datentypen über die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC-Treiber:  
  
|Spaltenname|Description|  
|-----------------|-----------------|  
|SS_UDT_CATALOG_NAME|Gibt den Namen des Katalogs zurück, der den benutzerdefinierten Typ (User-Defined Type, UDT) enthält.|  
|SS_UDT_SCHEMA_NAME|Gibt den Namen des Schemas zurück, das den UDT enthält.|  
|SS_UDT_ASSEMBLY_TYPE_NAME|Gibt den qualifizierten Namen des UDT-Assemblys zurück.|  
|SS_XML_SCHEMACOLLECTION_CATALOG_NAME|Gibt den Namen des Katalogs zurück, in dem ein XML-Schemaauflistungsname definiert ist. Wenn der Katalogname nicht gefunden werden kann, enthält diese Variable eine leere Zeichenfolge.|  
|SS_XML_SCHEMACOLLECTION_SCHEMA_NAME|Gibt den Namen des Schemas zurück, in dem ein XML-Schemaauflistungsname definiert ist. Wenn der Schemaname nicht gefunden werden kann, enthält diese Variable eine leere Zeichenfolge.|  
|SS_XML_SCHEMACOLLECTION_NAME|Gibt den Namen einer XML-Schemaauflistung zurück. Wenn der Name nicht gefunden werden kann, enthält diese Variable eine leere Zeichenfolge.|  
  
## <a name="sqlprocedurecolumns-and-table-valued-parameters"></a>SQLProcedureColumns und Tabellenwertparameter  
 SQLProcedureColumns handhabt Tabellenwertparameter ähnlich wie eine benutzerdefinierte CLR-Typen. In Zeilen, die für Tabellenwertparameter zurückgegeben werden, verfügen Spalten über die folgenden Werte:  
  
|Spaltenname|Beschreibung/Wert|  
|-----------------|------------------------|  
|DATA_TYPE|SQL_SS_TABLE|  
|TYPE_NAME|Der Name des Tabellentyps für den Tabellenwertparameter.|  
|COLUMN_SIZE|NULL|  
|BUFFER_LENGTH|0|  
|DECIMAL_DIGITS|Die Anzahl der Spalten im Tabellenwertparameter.|  
|NUM_PREC_RADIX|NULL|  
|NULLABLE|SQL_NULLABLE|  
|REMARKS|NULL|  
|COLUMN_DEF|NULL. Tabellentypen könnten keine Standardwerte besitzen.|  
|SQL_DATA_TYPE|SQL_SS_TABLE|  
|SQL_DATEIME_SUB|NULL|  
|CHAR_OCTET_LENGTH|NULL|  
|IS_NULLABLE|"YES"|  
|SS_TYPE_CATALOG_NAME|Gibt den Namen des Katalogs zurück, der die Tabelle oder den CLR-benutzerdefinierten Typ enthält.|  
|SS_TYPE_SCHEMA_NAME|Gibt den Namen des Schemas zurück, das die Tabelle oder den CLR-benutzerdefinierten Typ enthält.|  
  
 Die Spalten SS_TYPE_CATALOG_NAME und SS_TYPE_SCHEMA_NAME sind ab [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] verfügbar, um den Katalog bzw. das Schema für Tabellenwertparameter zurückzugeben. Dieses Spalten werden nicht nur mit Tabellenwertparametern sondern auch mit Parametern des CLR-benutzerdefinierten Typs aufgefüllt. Vorhandene Schema- und Katalogspalten für Parameter des CLR-benutzerdefinierten Typs sind von dieser zusätzlichen Funktionalität nicht betroffen. Sie werden ebenfalls aufgefüllt, um die Abwärtskompatibilität zu gewährleisten.  
  
 In Übereinstimmung mit der ODBC-Spezifikation werden SS_TYPE_CATALOG_NAME und SS_TYPE_SCHEMA_NAME vor allen treiberspezifischen Spalten angezeigt, die in früheren Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] hinzugefügt wurden, sowie nach allen Spalten, die von ODBC selbst benötigt werden.  
  
 Weitere Informationen zu Tabellenwertparametern finden Sie unter [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).  
  
## <a name="sqlprocedurecolumns-support-for-enhanced-date-and-time-features"></a>SQLProcedureColumns-Unterstützung für erweiterte Funktionen für Datum und Uhrzeit  
 Die Werte für Datum/Uhrzeit-Typen zurückgegeben wird, finden Sie unter [Katalogmetadaten](../native-client-odbc-date-time/metadata-catalog.md).  
  
 Weitere allgemeine Informationen finden Sie unter [Datum und Uhrzeit-Verbesserungen &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).  
  
## <a name="sqlprocedurecolumns-support-for-large-clr-udts"></a>SQLProcedureColumns-Unterstützung für große CLR-UDTs  
 `SQLProcedureColumns` unterstützt große benutzerdefinierte CLR-Typen (UDTs). Weitere Informationen finden Sie unter [Large CLR User-Defined Typen &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [SQLProcedureColumns-Funktion](http://go.microsoft.com/fwlink/?LinkId=59363)   
 [ODBC-API-Implementierungsdetails](odbc-api-implementation-details.md)  
  
  