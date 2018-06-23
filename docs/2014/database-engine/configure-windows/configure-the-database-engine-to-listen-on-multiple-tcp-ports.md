---
title: Konfigurieren der Datenbank-Engine zum Überwachen mehrerer TCP-Ports | Microsoft-Dokumentation
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
- ports [SQL Server], multiple
- TDS
- listen on multiple ports
- endpoints [SQL Server], TDS
- adding ports
- tabular data stream
- multiple ports
ms.assetid: 8e955033-06ef-403f-b813-3d8241b62f1f
caps.latest.revision: 25
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: 766c72f478be2cce2688312ed3accd43e67998b5
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36160968"
---
# <a name="configure-the-database-engine-to-listen-on-multiple-tcp-ports"></a>Konfigurieren der Datenbank-Engine zum Überwachen mehrerer TCP-Ports
  In diesem Thema wird beschrieben, wie Sie [!INCLUDE[ssDE](../../includes/ssde-md.md)] konfigurieren können, um auf mehreren TCP-Ports in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe des SQL Server-Konfigurations-Managers lauschen zu können. Wenn TCP/IP für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]aktiviert wird, überwacht der [!INCLUDE[ssDE](../../includes/ssde-md.md)] eingehende Verbindungen auf einem Verbindungspunkt, der aus der IP-Adresse und der TCP-Portnummer besteht. Die folgenden Prozeduren erstellen einen Tabular Data Stream-Endpunkt (TDS), damit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf einem zusätzlichen TCP-Port lauschen kann.  
  
 Die folgenden Gründe kommen für das Erstellen eines zweiten TDS-Endpunkts in Betracht:  
  
-   Erhöhen der Sicherheit durch Konfigurieren der Firewall zum Einschränken des Zugriffs auf den Standardendpunkt auf lokale Clientcomputer in einem bestimmten Teilnetz. Verwalten des Internetzugriffs auf [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] durch Ihr Supportteam durch Erstellen eines neuen Endpunkts, den die Firewall im Internet verfügbar macht, und Einschränken der Verbindungsrechte für diesen Endpunkt auf Ihr Serversupportteam.  
  
-   Zuordnen von Verbindungen zu bestimmten Prozessoren, wenn NUMA (Non-Uniform Memory Access) verwendet wird.  
  
 Das Konfigurieren eines TDS-Endpunkts besteht aus den folgenden Schritten, die in beliebiger Reihenfolge ausgeführt werden können:  
  
-   Erstellen des TDS-Endpunkts für den TCP-Port und ggf. Wiederherstellen des Zugriffs auf den Standardendpunkt.  
  
-   Erteilen des Zugriffs auf den Endpunkt für die gewünschten Serverprinzipale.  
  
-   Angeben der TCP-Portnummer für die ausgewählte IP-Adresse.  
  
 Weitere Informationen zu den Standardeinstellungen der Windows-Firewall und eine Beschreibung der TCP-Ports, die sich auf Datenbank-Engine, Analysis Services, Reporting Services und Integration Services auswirken, finden Sie unter [Konfigurieren der Windows-Firewall für den SQL Server-Zugriff](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-create-a-tds-endpoint"></a>So erstellen Sie einen TDS-Endpunkt  
  
-   Geben Sie die folgende Anweisung aus, um einen Endpunkt namens **CustomConnection** für Port 1500 für alle verfügbaren TCP-Adressen auf dem Server zu erstellen.  
  
    ```  
    USE master;  
    GO  
    CREATE ENDPOINT [CustomConnection]  
    STATE = STARTED  
    AS TCP  
       (LISTENER_PORT = 1500, LISTENER_IP =ALL)  
    FOR TSQL() ;  
    GO  
    ```  
  
 Wenn Sie einen neuen [!INCLUDE[tsql](../../includes/tsql-md.md)] -Endpunkt erstellen, werden die Verbindungsberechtigungen für die **public** -Gruppe für den TDS-Standardendpunkt aufgehoben. Wenn der Zugriff auf die **public** -Gruppe für den Standardendpunkt erforderlich ist, wenden Sie diese Berechtigung mithilfe der `GRANT CONNECT ON ENDPOINT::[TSQL Default TCP] to [public];` -Anweisung erneut an.  
  
#### <a name="to-grant-access-to-the-endpoint"></a>So erteilen Sie Zugriff auf den Endpunkt  
  
-   Geben Sie die folgende Anweisung aus, um den Zugriff auf den **CustomConnection** -Endpunkt für die SQLSupport-Gruppe in der corp-Domäne zu erteilen.  
  
    ```  
    GRANT CONNECT ON ENDPOINT::[CustomConnection] to [corp\SQLSupport] ;  
    GO  
    ```  
  
#### <a name="to-configure-the-sql-server-database-engine-to-listen-on-an-additional-tcp-port"></a>So konfigurieren Sie die SQL Server-Datenbank-Engine zum Lauschen an einem zusätzlichen TCP-Port  
  
1.  Erweitern Sie im SQL Server-Konfigurations-Manager den Eintrag **SQL Server-Netzwerkkonfiguration**, und klicken Sie dann auf **Protokolle für***<Instanzname>*.  
  
2.  Erweitern Sie **Protokolle für***<Instanzname>*, und klicken Sie dann auf **TCP/IP**.  
  
3.  Klicken Sie im rechten Bereich mit der rechten Maustaste auf jede deaktivierte IP-Adresse, die Sie aktivieren möchten, und klicken Sie dann auf **Aktivieren**.  
  
4.  Klicken Sie mit der rechten Maustaste auf **IPAll**, und klicken Sie dann auf **Eigenschaften**.  
  
5.  Geben Sie im Feld **TCP-Port** die Ports ein, an denen [!INCLUDE[ssDE](../../includes/ssde-md.md)] lauschen soll; trennen Sie die einzelnen Werte dabei durch Kommas. Wenn der Standardport 1433 aufgelistet wird, geben Sie in unserem Beispiel `,1500` sodass im Feld `1433,1500`, und klicken Sie dann auf **OK**.  
  
    > [!NOTE]  
    >  Wenn Sie den Port nicht für alle IP-Adressen aktivieren möchten, konfigurieren Sie den zusätzlichen Port im Eigenschaftenfeld nur für die gewünschte Adresse. Klicken Sie dann im Konsolenbereich mit der rechten Maustaste auf **TCP/IP**, klicken Sie auf **Eigenschaften**, und wählen Sie anschließend die Option **Nein** im Feld **Alle überwachen**.  
  
6.  Klicken Sie im linken Bereich auf **SQL Server-Dienste**.  
  
7.  Klicken Sie im rechten Bereich mit der rechten Maustaste auf **SQL Server***<Instanzname>*, und klicken Sie dann auf **Neu starten**.  
  
     Wenn [!INCLUDE[ssDE](../../includes/ssde-md.md)] neu gestartet wird, führt das Fehlerprotokoll die Ports auf, die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] überwacht.  
  
#### <a name="to-connect-to-the-new-endpoint"></a>So stellen Sie eine Verbindung mit dem neuen Endpunkt her  
  
-   Geben Sie die folgende Anweisung aus, um eine Verbindung mit dem **CustomConnection** -Endpunkt der Standardinstanz von SQL Server auf dem Server namens ACCT mithilfe einer vertrauenswürdigen Verbindung herzustellen, wobei davon ausgegangen wird, dass der Benutzer ein Mitglied der [corp\SQLSupport]-Gruppe ist.  
  
    ```  
    sqlcmd -SACCT,1500  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql)   
 [DROP ENDPOINT (Transact-SQL)](/sql/t-sql/statements/drop-endpoint-transact-sql)   
 [GRANT (Endpunktberechtigungen) (Transact-SQL)](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql)   
 [Zuordnen von TCP/IP-Ports zu NUMA-Knoten &#40;SQL Server&#41;](map-tcp-ip-ports-to-numa-nodes-sql-server.md)  
  
  