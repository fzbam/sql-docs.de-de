---
title: Sqlsrv_server_info | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- sqlsrv_server_info
apitype: NA
helpviewer_keywords:
- API Reference, sqlsrv_server_info
- sqlsrv_server_info
ms.assetid: ef6fe2b7-d267-4379-b948-5626c4684367
caps.latest.revision: 21
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: ca576d890d943aa7df98495ff8a18c91d11e0866
ms.contentlocale: de-de
ms.lasthandoff: 09/09/2017

---
# <a name="sqlsrvserverinfo"></a>sqlsrv_server_info
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

Gibt Informationen über den Server zurück. Eine Verbindung muss hergestellt werden, bevor Sie diese Funktion aufrufen.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
sqlsrv_server_info( resource $conn)  
```  
  
#### <a name="parameters"></a>Parameter  
*$conn*: Die Verbindungsressource, durch die der Client und der Server verbunden sind.  
  
## <a name="return-value"></a>Rückgabewert  
Ein assoziatives Array mit den folgenden Schlüsseln:  
  
|Key|Beschreibung|  
|-------|---------------|  
|CurrentDatabase|Die Datenbank, die derzeit das Ziel darstellt.|  
|SQLServerVersion|Die Version von SQL Server.|  
|SQLServerName|Der Name des Servers.|  
  
## <a name="example"></a>Beispiel  
Das folgende Beispiel schreibt Server-Informationen an die Konsole, wenn das Beispiel über die Befehlszeile ausgeführt wird.  
  
```  
<?php  
/* Connect to the local server using Windows Authentication. */  
$serverName = "(local)";  
$conn = sqlsrv_connect( $serverName);  
if( $conn === false )  
{  
     echo "Could not connect.\n";  
     die( print_r( sqlsrv_errors(), true));  
}  
  
$server_info = sqlsrv_server_info( $conn);  
if( $server_info )  
{  
      foreach( $server_info as $key => $value)  
      {  
             echo $key.": ".$value."\n";  
      }  
}  
else  
{  
      echo "Error in retrieving server info.\n";  
      die( print_r( sqlsrv_errors(), true));  
}  
  
/* Free connection resources. */  
sqlsrv_close( $conn);  
?>  
```  
  
## <a name="see-also"></a>Siehe auch  
[API-Referenz für den SQLSRV-Treiber](../../connect/php/sqlsrv-driver-api-reference.md)  
[Informationen zu den Codebeispielen in der Dokumentation](../../connect/php/about-code-examples-in-the-documentation.md)  
  
