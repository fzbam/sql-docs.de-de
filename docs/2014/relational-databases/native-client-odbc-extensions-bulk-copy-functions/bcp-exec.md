---
title: Bcp_exec | Microsoft Docs
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
api_name:
- bcp_exec
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_exec function
ms.assetid: b23ea2cc-8545-4873-b0c1-57e76b0a3a7b
caps.latest.revision: 34
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 7f7fabbf20276bca314d5c98847ef9a850be7738
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36050311"
---
# <a name="bcpexec"></a>bcp_exec
  Führt ein vollständiges Massenkopieren der Daten zwischen einer Datenbanktabelle und einer Benutzerdatei aus.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
RETCODE bcp_exec (  
HDBC   
hdbc  
,  
LPDBINT   
pnRowsProcessed  
);  
  
```  
  
## <a name="arguments"></a>Argumente  
 *HDBC*  
 Das für den Massenkopiervorgang aktivierte ODBC-Verbindungshandle.  
  
 *pnRowsProcessed*  
 Ein Zeiger auf DBINT. Die **bcp_exec** -Funktion füllt DBINT mit der Anzahl der erfolgreich kopierten Zeilen. Wenn *pnRowsProcessed* auf NULL festgelegt ist, wird es von **bcp_exec**ignoriert.  
  
## <a name="returns"></a>Rückgabewert  
 SUCCEED, SUCCEED_ASYNC oder FAIL. Die **bcp_exec** -Funktion gibt SUCCEED zurück, wenn alle Zeilen kopiert wurden. **bcp_exec** gibt SUCCEED_ASYNC zurück, falls ein asynchroner Massenkopiervorgang aussteht. **Bcp_exec** gibt FAIL zurück, wenn ein vollständiger Fehler auftritt oder wenn die Anzahl der Zeilen, die Fehler generieren, für die Verwendung von BCPMAXERRS angegebenen Wert erreicht [Bcp_control](bcp-control.md). BCPMAXERRS ist standardmäßig auf 10 festgelegt. Die BCPMAXERRS-Option wirkt sich nur auf die Syntaxfehler aus, die vom Anbieter während des Lesens der Zeilen aus der Datendatei (und nicht der Zeilen, die an den Server gesendet werden) erkannt werden. Der Server bricht den Batch ab, wenn er einen Fehler in einer Zeile erkennt. Überprüfen Sie den *pnRowsProcessed* -Parameter auf die Anzahl an erfolgreich kopierten Zeilen.  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion kopiert Daten aus einer Benutzerdatei in eine Datenbanktabelle oder umgekehrt, abhängig vom Wert der *eDirection* im Parameters [Bcp_init](bcp-init.md).  
  
 Vor dem Aufrufen von **bcp_exec**rufen Sie **bcp_init** mit einem gültigen Benutzerdateinamen auf. Andernfalls wird ein Fehler ausgelöst.  
  
 **bcp_exec** ist die einzige Massenkopierfunktion, die im Allgemeinen für eine beliebige Zeitlänge aussteht. Es ist deshalb die einzige Massenkopierfunktion, die den asynchronen Modus unterstützt. Verwenden Sie zum Festlegen von asynchronen Modus [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) festzulegende SQL_ATTR_ASYNC_ENABLE auf SQL_ASYNC_ENABLE_ON vor dem Aufruf **Bcp_exec**. Rufen Sie **bcp_exec** mit denselben Parametern auf, um den Vorgang auf Vollständigkeit zu überprüfen. Wenn das Massenkopieren noch nicht abgeschlossen wurde, gibt **bcp_exec** SUCCEED_ASYNC zurück. Außerdem wird in *pnRowsProcessed* eine Statuszahl der Anzahl der Zeilen zurückgegeben, die an den Server gesendet wurden. Für die zum Server gesendeten Zeilen wird erst ein Commit ausgeführt, wenn das Ende eines Batches erreicht wurde.  
  
 Informationen über eine wichtige Änderung, in Massenkopieren ab [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], finden Sie unter [Durchführen von Massenkopiervorgängen &#40;ODBC&#41;](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Verwendung von **bcp_exec**veranschaulicht:  
  
```  
// Variables like henv not specified.  
HDBC      hdbc;  
DBINT      nRowsProcessed;  
  
// Application initiation, get an ODBC environment handle, allocate the  
// hdbc, and so on.  
...   
  
// Enable bulk copy prior to connecting on allocated hdbc.  
SQLSetConnectAttr(hdbc, SQL_COPT_SS_BCP, (SQLPOINTER) SQL_BCP_ON,  
   SQL_IS_INTEGER);  
  
// Connect to the data source, return on error.  
if (!SQL_SUCCEEDED(SQLConnect(hdbc, _T("myDSN"), SQL_NTS,  
   _T("myUser"), SQL_NTS, _T("myPwd"), SQL_NTS)))  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Initialize bulk copy.   
if (bcp_init(hdbc, _T("pubs..authors"), _T("authors.sav"), NULL, DB_OUT)  
   == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Now, execute the bulk copy.   
if (bcp_exec(hdbc, &nRowsProcessed) == FAIL)  
   {  
   if (nRowsProcessed == -1)  
      {  
      printf_s("No rows processed on bulk copy execution.\n");  
      }  
   else  
      {  
      printf_s("Incomplete bulk copy.   Only %ld row%s copied.\n",  
         nRowsProcessed, (nRowsProcessed == 1) ? "": "s");  
      }  
   return;  
   }  
  
printf_s("%ld rows processed.\n", nRowsProcessed);  
  
// Carry on.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Massenkopierfunktionen](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  