---
title: Remoteadministratorverbindungen (Serverkonfigurationsoption) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- administrator connections [SQL Server]
- DAC
- connections [SQL Server], dedicated administrator
- remote admin connections option
- dedicated administrator connections [SQL Server]
ms.assetid: bf32b60a-7a48-401f-b6be-b5e2e46c413f
caps.latest.revision: 15
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: 35113a648a66b1122e7bf92785fab7bd7aaa1317
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36162102"
---
# <a name="remote-admin-connections-server-configuration-option"></a>Remoteadministratorverbindungen (Serverkonfigurationsoption)
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stellt eine dedizierte Administratorverbindung (Dedicated Administrator Connection, DAC) zur Verfügung. Mit der DAC kann ein Administrator auf einen laufenden Server zugreifen, um Diagnosefunktionen oder [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen auszuführen oder um Probleme auf dem Server zu behandeln, selbst wenn der Server gesperrt ist oder nicht in einem normalen Status ausgeführt wird und nicht auf eine [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] -Verbindung antwortet. Standardmäßig ist die DAC nur von einem Client auf dem Server verfügbar. Verwenden Sie die Option remote admin connections von sp_configure, um zuzulassen, dass Clientanwendungen auf Remotecomputern die DAC verwenden.  
  
 Standardmäßig lauscht die DAC nur an der Loopback-IP-Adresse (127.0.0.1), Port 1434. Ist der TCP-Port 1434 nicht verfügbar, wird ein TCP-Port dynamisch zugewiesen, wenn [!INCLUDE[ssDE](../../includes/ssde-md.md)] startet. Wenn mehr als eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf einem Computer installiert ist, müssen Sie das Fehlerprotokoll auf die TCP-Portnummer überprüfen.  
  
 In der folgenden Tabelle sind die möglichen Werte für die Option remote admin connections aufgeführt.  
  
|value|Description|  
|-----------|-----------------|  
|0|Nur lokale Verbindungen sind mit der DAC zulässig.|  
|1|Remoteverbindungen sind mit der DAC zulässig.|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die DAC von einem Remotecomputer aus aktiviert.  
  
```  
sp_configure 'remote admin connections', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Diagnoseverbindung für Datenbankadministratoren](diagnostic-connection-for-database-administrators.md)  
  
  