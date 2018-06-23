---
title: ODBC-SQL-Typ für Tabellenwertparameter | Microsoft Docs
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
- SQL_SS_TABLE
ms.assetid: 6725bfb9-5f10-4115-be09-fd9c9f5779ea
caps.latest.revision: 17
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0b537b4807dc96dcc5f3b30acbd591dc108939f2
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36047139"
---
# <a name="odbc-sql-type-for-table-valued-parameters"></a>ODBC-SQL-Typ für Tabellenwertparameter
  Unterstützung für Tabellenwertparameter wird von einem neuen ODBC-SQL-Typ, SQL_SS_TABLE, bereitgestellt.  
  
## <a name="remarks"></a>Hinweise  
 SQL_SS_TABLE kann nicht konvertiert werden, in einen anderen ODBC- oder [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datentyp.  
  
 Wenn SQL_SS_TABLE, als C-Datentyp in verwendet wird der *ValueType* -Parameter von SQLBindParameter oder den Versuch erfolgt SQL_DESC_TYPE in einem anwendungsparameterdeskriptor (APD)-Datensatz auf SQL_SS_TABLE festgelegt, wird SQL_ERROR zurückgegeben und ein Diagnosedatensatz generiert, mit der Meldung SQLSTATE = HY003, "Ungültiger Anwendungspuffertyp".  
  
 Wenn SQL_DESC_TYPE in einem IPD-Datensatz auf SQL_SS_TABLE festgelegt wird, und der entsprechende Anwendungsparameterdeskriptor-Datensatz nicht SQL_C_DEFAULT ist, wird SQL_ERROR zurückgegeben, und ein Diagnosedatensatz mit der Meldung SQLSTATE=HY003, "Ungültiger Anwendungspuffertyp" wird generiert. Dies kann auftreten, mit der *ParameterType* eines SQLSetDescField, SQLSetDescRec oder SQLBindParameter.  
  
 Wenn die *TargetType* Aufrufen von SQLGetData-Parameter SQL_SS_TABLE ist, wird SQL_ERROR zurückgegeben, und ein Diagnosedatensatz mit SQLSTATE generiert = HY003, "Ungültiger Anwendungspuffertyp".  
  
 Eine Tabellenwertparameter-Spalte kann nicht als SQL_SS_TABLE-Datentyp gebunden werden. Wenn `SQLBindParameter` aufgerufen wird und *ParameterType* auf SQL_SS_TABLE festgelegt ist, wird SQL_ERROR zurückgegeben und ein Diagnosedatensatz mit SQLSTATE generiert = HY004, "Ungültiger SQL-Datentyp". Dies kann auch mit SQLSetDescField und SQLSetDescRec auftreten.  
  
 Tabellenwertparameter-Spaltenwerte verfügen über dieselben Datenkonvertierungsoptionen wie Parameter und Ergebnisspalten.  
  
 Bei einem Tabellenwertparameter kann es sich nur um einen Eingabeparameter in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] oder höher handeln. Wenn versucht wird, SQL_DESC_PARAMETER_TYPE auf einen anderen Wert als SQL_PARAM_INPUT über SQLBindParameter oder SQLSetDescField festgelegt, dann SQL_ERROR zurückgegeben wird und ein Diagnosedatensatz mit SQLSTATE-Anweisung hinzugefügt = HY105 und der Meldung "Ungültiger parameter Geben Sie".  
  
 Tabellenwertparameter-Spalten können SQL_DEFAULT_PARAM nicht in *StrLen_or_IndPtr*verwenden, da Standardwerte pro Zeile nicht mit Tabellenwertparametern unterstützt werden. Stattdessen kann eine Anwendung das Spaltenattribut SQL_CA_SS_COL_HAS_DEFAULT_VALUE auf 1 festlegen. Dies bedeutet, dass die Spalte Standardwerte für alle Zeilen aufweist. Wenn *StrLen_or_IndPtr* ist festgelegt auf SQL_DEFAULT_PARAM, SQLExecute oder SQLExecDirect SQL_ERROR zurück, und wird ein Diagnosedatensatz mit SQLSTATE-Anweisung hinzugefügt werden = HY090 und der Meldung "Ungültige Zeichenfolgen- oder Pufferlänge".  
  
## <a name="see-also"></a>Siehe auch  
 [Tabellenwertparameter &#40;ODBC&#41;](table-valued-parameters-odbc.md)  
  
  