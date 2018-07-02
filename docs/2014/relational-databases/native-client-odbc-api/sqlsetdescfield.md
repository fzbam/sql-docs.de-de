---
title: SQLSetDescField | Microsoft Docs
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
helpviewer_keywords:
- SQLSetDescField function
ms.assetid: de4bed15-15be-4825-994c-1046255e725a
caps.latest.revision: 23
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: bf61530ccfd142b473da8a5443cc63b16a435d32
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36048255"
---
# <a name="sqlsetdescfield"></a>SQLSetDescField
  SQLSetDescField kann verwendet werden, um deskriptorfelder für Tabellenwertparameter und Tabellenwertparameter-Spalten festzulegen. Informationen über die verfügbaren Felder finden Sie unter [Deskriptorfelder für Tabellenwertparameter Parameter](../native-client-odbc-table-valued-parameters/table-valued-parameter-descriptor-fields.md) und [Deskriptorfelder für Tabellenwertparameter Parameter konstituierender Spalten](../native-client-odbc-table-valued-parameters/descriptor-fields-for-table-valued-parameter-constituent-columns.md).  
  
## <a name="remarks"></a>Hinweise  
 Tabellenwertparameter-Spalten sind nur verfügbar, wenn das Deskriptorheaderfeld SQL_SOPT_SS_PARAM_FOCUS auf die Ordnungszahl eines Datensatzes festgelegt ist, für den SQL_DESC_TYPE auf SQL_SS_TABLE eingestellt ist. Weitere Informationen zu SQL_SOPT_SS_PARAM_FOCUS finden Sie unter [SQLSetStmtAttr](sqlsetstmtattr.md).  
  
 Wenn es versucht wird, um SQL_SOPT_SS_PARAM_FOCUS auf die Ordnungszahl für einen Parameter festzulegen, die keinem Tabellenwertparameter ist, SQLSetStmtAttr SQL_ERROR zurück gibt und ein Diagnosedatensatz mit SQLSTATE erstellt = HY024 und der Meldung "Ungültiger Attributwert". SQL_SOPT_SS_PARAM_FOCUS wird nicht geändert, wenn SQL_ERROR zurückgegeben wird.  
  
 Durch das Festlegen von SQL_SOPT_SS_PARAM_FOCUS auf 0 (null) wird der Zugriff auf Deskriptordatensätze für Parameter wiederhergestellt.  
  
 Weitere Informationen zu Tabellenwertparametern finden Sie unter [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).  
  
## <a name="sqlsetdescfield-support-for-enhanced-date-and-time-features"></a>SQLSetDescField-Unterstützung für erweiterte Funktionen zu Datum und Uhrzeit  
 Datum/Uhrzeit-Funktionen wurden in ODBC verbessert. Informationen zu den für die neuen Datums-/Uhrzeittypen verfügbare Deskriptorfeld finden Sie unter [Parameter- und Ergebnismetadaten](../native-client-odbc-date-time/metadata-parameter-and-result.md).  
  
 Weitere Informationen finden Sie unter [Datum und Uhrzeit-Verbesserungen &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).  
  
## <a name="sqlsetdescfield-support-for-large-clr-udts"></a>SQLSetDescField-Unterstützung für große CLR-UDTs  
 SQLSetDescField unterstützt große CLR-benutzerdefinierte Typen (UDTs). Weitere Informationen finden Sie unter [Large CLR User-Defined Typen &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).  
  
## <a name="sqlsetdescfield-support-for-sparse-columns"></a>SQLSetDescField-Unterstützung für Spalten mit geringer Dichte  
 SQLSetDecField kann verwendet werden, zum Festlegen von SQL_SOPT_SS_NAME_SCOPE im anweisungsparameterdeskriptor (APD) auf die Werte SQL_SS_NAME_SCOPE_EXTENDED und SQL_SS_NAME_SCOPE_SPARSE_COLUMN_SET.  
  
 Weitere Informationen finden Sie unter [Sparse Columns Support &#40;ODBC&#41;](../native-client/odbc/sparse-columns-support-odbc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [SQLSetDescField](http://go.microsoft.com/fwlink/?LinkId=80705)   
 [ODBC-API-Implementierungsdetails](odbc-api-implementation-details.md)  
  
  