---
title: Für SQL Server-Verbindung erforderliche Berechtigungen für den CDC Service | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: integration-services
ms.component: change-data-capture
ms.reviewer: ''
ms.suite: sql
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: d9e968f9-180c-4fa0-a849-98f2b1942330
caps.latest.revision: 8
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: dc242dfeb9d3892d1545396eebfa6db57f3fa271
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="sql-server-connection-required-permissions-for-the-cdc-service"></a>Für SQL Server-Verbindung erforderliche Berechtigungen für den CDC Service
  Die CDC Service Configuration Console erfordert Verbindungsinformationen zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , um die damit verbundenen Tasks auszuführen. In diesem Thema werden die Informationen beschrieben, die im Dialogfeld Verbindung mit SQL Server herstellen zum Einrichten der Verbindung zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]angegeben werden können.  
  
 Das Dialogfeld Verbindung mit SQL Server herstellen wird jeweils bei Bedarf geöffnet, z. B. wenn keine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Verbindungsinformationen verfügbar sind oder wenn die Informationen zwar vorhanden sind, aber die Verbindung nicht die erforderlichen Berechtigungen aufweist.  
  
 In der folgenden Tabelle werden die verschiedenen Tasks beschrieben, für die eine Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] erforderlich ist, sowie die erforderlichen Berechtigungen für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Benutzer (Anmeldung).  
  
|Task|Mindestberechtigungen|  
|----------|-------------------------|  
|Vorbereiten der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz|`dbcreator` Feste Serverrolle|  
|Erstellen einer Oracle CDC Service-SQL Server-Anmeldung zur Verwendung durch den Oracle CDC Service|`public` Feste Serverrolle|  
|Erstellen einer Oracle CDC Service-Anmeldung, die zum Registrieren des neuen Diensts in MSXDBCDC verwendet werden soll|`db_datareader` und `db_datawriter` für MSXDBCDC|  
|Bearbeiten einer Oracle CDC Service-Anmeldung, die zum Aktualisieren der Registrierung des Diensts in MSXDBCDC verwendet werden soll|`db_datareader` und `db_datawriter` für MSXDBCDC|  
|Löschen einer Oracle CDC Service-Anmeldung, die zum Aktualisieren der Registrierung des Diensts in MSXDBCDC verwendet werden soll|`db_datareader` und `db_datawriter` für MSXDBCDC|  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
 [Verbindung zu SQL Server](../../integration-services/change-data-capture/connection-to-sql-server.md)   
 [Verbindung zu SQL Server zum Löschen](../../integration-services/change-data-capture/connection-to-sql-server-for-delete.md)  
  
  
