---
title: Verwenden einer Anweisung (ODBC) | Microsoft Docs
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
- statements [ODBC]
ms.assetid: f7573f8f-6f21-4e03-8dd5-a5f2ea4878cc
caps.latest.revision: 14
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 50a4f012b556bb6f54a0b9e672c2f9ff16a44fd2
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36046219"
---
# <a name="use-a-statement-odbc"></a>Verwenden einer Anweisung (ODBC)
    
### <a name="to-use-a-statement"></a>So verwenden Sie eine Anweisung  
  
1.  Rufen Sie [SQLAllocHandle](http://go.microsoft.com/fwlink/?LinkId=58396) mit einem *HandleType* von SQL_HANDLE_STMT auf, um ein Anweisungshandle zuzuweisen.  
  
2.  Rufen Sie optional [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) auf, um Anweisungsoptionen festzulegen, oder [SQLGetStmtAttr](../../native-client-odbc-api/sqlgetstmtattr.md), um Anweisungsattribute abzurufen.  
  
     Um Servercursor zu verwenden, müssen Sie die Cursorattribute auf Werte setzen, die von den Standardwerten abweichen.  
  
3.  Bereiten Sie optional die Anweisung mit der [SQLPrepare-Funktion](http://go.microsoft.com/fwlink/?LinkId=59360)auf die Ausführung vor, wenn die Anweisung mehrmals ausgeführt wird.  
  
4.  Binden Sie optional mit [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md)die Parametermarkierungen an Programmvariablen, wenn die Anweisung über gebundene Parametermarkierungen verfügt. Wenn die Anweisung vorbereitet wurde, können Sie [SQLNumParams](http://go.microsoft.com/fwlink/?LinkId=58404) und [SQLDescribeParam](../../native-client-odbc-api/sqldescribeparam.md) to find the number und characteristics of the parameters.  
  
5.  Führen Sie eine Anweisung direkt mit SQLExecDirect aus.  
  
     \- oder –  
  
     Wenn die Anweisung vorbereitet wurde, führen Sie sie mehrmals mit [SQLExecute](http://go.microsoft.com/fwlink/?LinkId=58400)aus.  
  
     \- oder –  
  
     Rufen Sie eine Katalogfunktion auf, die Ergebnisse zurückgibt.  
  
6.  Verarbeiten Sie die Ergebnisse, indem Sie die Resultset-Spalten an Programmvariablen binden, indem Sie Daten mit [SQLGetData](../../native-client-odbc-api/sqlgetdata.md)oder einer Kombination der beiden Methoden aus den Resultset-Spalten zu Programmvariablen verschieben.  
  
     Rufen Sie eine Zeile nach der anderen über das Resultset einer Anweisung ab.  
  
     \- oder –  
  
     Rufen Sie mehrere Zeilen gleichzeitig über das Resultset mithilfe eines Blockcursors ab.  
  
     \- oder –  
  
     Rufen Sie [SQLRowCount](../../native-client-odbc-api/sqlrowcount.md) auf, um die Anzahl der Zeilen, die von einer INSERT-, UPDATE- oder DELETE-Anweisung betroffen sind, zu bestimmen.  
  
     Wenn die SQL-Anweisung über mehrere Resultsets verfügen kann, rufen Sie am Ende des Resultsets [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) auf, um zu überprüfen, ob zusätzliche Resultsets verarbeitet werden müssen.  
  
7.  Nachdem die Ergebnisse verarbeitet wurden, müssen möglicherweise die folgenden Aktionen ausgeführt werden, um das Anweisungshandle zum Ausführen einer neuen Anweisung verfügbar zu machen.  
  
    -   Wenn Sie [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) nicht aufgerufen haben, bis SQL_NO_DATA zurückgegeben wurde, rufen Sie [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) auf, um den Cursor zu schließen.  
  
    -   Wenn Sie Parametermarkierungen an Programmvariablen gebunden haben, rufen Sie [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) auf, wobei *Option* auf SQL_RESET_PARAMS gesetzt ist, um die gebundenen Parameter freizugeben.  
  
    -   Wenn Sie Resultset-Spalten an Programmvariablen gebunden haben, rufen Sie [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) auf, wobei *Option* auf SQL_UNBIND gesetzt ist, um die gebundenen Spalten freizugeben.  
  
    -   Gehen Sie zu Schritt 2, um das Anweisungshandle wiederzuverwenden.  
  
8.  Rufen Sie [SQLFreeHandle](../../native-client-odbc-api/sqlfreehandle.md) mit einem *HandleType* von SQL_HANDLE_STMT auf, um das Anweisungshandle freizugeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausführen von Abfragen: Themen zur Vorgehensweise &#40;ODBC&#41;](executing-queries-how-to-topics-odbc.md)  
  
  