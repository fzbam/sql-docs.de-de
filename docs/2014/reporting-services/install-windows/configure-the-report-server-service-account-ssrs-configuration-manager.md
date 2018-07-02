---
title: Konfigurieren des Berichtsserver-Dienstkontos (SSRS-Konfigurations-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f880c623-67c8-4167-b98b-ace17e800faa
caps.latest.revision: 8
author: markingmyname
ms.author: maghan
manager: jhubbard
ms.openlocfilehash: bd5da35233834eb0f57482e7f7faef11f977debe
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36057545"
---
# <a name="configure-the-report-server-service-account-ssrs-configuration-manager"></a>Konfigurieren des Berichtsserver-Dienstkontos (SSRS-Konfigurations-Manager)
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] wird als Einzeldienst mit einem Report Server-Webdienst (Berichts-Manager) und einer Hintergrundverarbeitungsanwendung implementiert, die für die geplante Berichtsverarbeitung und die Abonnementübermittlung verwendet wird. In diesem Thema wird erläutert, wie das Dienstkonto zu Beginn konfiguriert wird. Außerdem wird beschrieben, wie das Konto oder das Kennwort mit dem Reporting Services-Konfigurationstool geändert wird.  
  
## <a name="initial-configuration"></a>Anfängliche Konfiguration  
 Das Berichtsserver-Dienstkonto wird während der Ausführung von Setup definiert. Sie können z. B. den Dienst unter einem Domänenbenutzerkonto oder eine integrierte ausführen `NetworkService` Konto. Es ist kein Standardkonto ein. alle Konten, die Sie, in angeben der [Serverkonfiguration – Dienstkonten](../../sql-server/install/server-configuration-service-accounts.md) Seite des Installations-Assistenten wird das Konto für den Report Server-Dienst.  
  
> [!IMPORTANT]  
>  Obwohl der Berichtsserver-Webdienst und Berichts-Manager [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] Anwendungen, sie führen nicht unter die [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] Konto. Die Einzeldienstarchitektur führt beide ASP.NET-Anwendungen im Rahmen der gleichen Berichtsserver-Prozessidentität aus. Dies ist eine wichtige Änderung gegenüber früheren Versionen, in denen der Report Server-Webdienst und der Berichts-Manager unter der gleichen, in IIS angegebenen [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)]-Arbeitsprozessidentität ausgeführt wurden.  
  
## <a name="changing-the-service-account"></a>Ändern des Dienstkontos  
 Verwenden Sie stets das [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Konfigurationstool, um die Informationen für das Dienstkonto anzuzeigen und neu zu konfigurieren. Die Informationen zur Dienstidentität werden intern an mehreren Speicherorten gespeichert. Durch die Verwendung des Tools wird sichergestellt, dass alle Verweise entsprechend aktualisiert werden, wenn Sie das Konto oder das Kennwort ändern. Vom [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Konfigurationstool werden folgende zusätzlichen Schritte ausgeführt, um sicherzustellen, dass der Berichtsserver verfügbar bleibt:  
  
-   Das neue Konto wird automatisch der auf dem lokalen Computer erstellten Berichtsservergruppe hinzugefügt. Diese Gruppe wird in den Zugriffssteuerungslisten (Access Control Lists, ACLs) angegeben, die [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Dateien schützen.  
  
-   Die Anmeldeberechtigungen der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Instanz, die als Host für die Berichtsserver-Datenbank fungiert, werden automatisch aktualisiert. Das neue Konto wird der **RSExecRole**hinzugefügt.  
  
     Die Datenbankanmeldung für das alte Konto wird nicht automatisch entfernt. Stellen Sie sicher, dass nicht mehr benötigte Konten entfernt werden. Weitere Informationen finden Sie unter [Verwalten einer Berichtsserver-Datenbank (einheitlicher SSRS-Modus)](../report-server/report-server-database-ssrs-native-mode.md) in der SQL Server-Onlinedokumentation.  
  
     Um einem neuen Dienstkonto Datenbankberechtigungen gewähren zu können, muss die Berichtsserver-Datenbankverbindung zuvor für das Dienstkonto konfiguriert worden sein. Wenn Sie die Berichtsserver-Datenbankverbindung für ein Domänenbenutzerkonto oder eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbankanmeldung konfiguriert haben, hat die Aktualisierung des Dienstkontos keine Auswirkungen auf die Verbindungsinformationen.  
  
-   Der Verschlüsselungsschlüssel wird automatisch aktualisiert, sodass er die Profilinformationen des neuen Kontos enthält.  
  
    > [!NOTE]  
    >  Wenn der Berichtsserver Teil einer Bereitstellung für horizontales Skalieren ist, ist nur der Berichtsserver betroffen, den Sie aktualisieren. Auf die Verschlüsselungsschlüssel für andere Berichtsserver in der Bereitstellung hat die Änderung des Dienstkontos keine Auswirkung.  
  
 Anleitungen zum Festlegen des Kontos finden Sie unter [Konfigurieren eines Dienstkontos &#40;SSRS-Konfigurations-Manager&#41;](../../sql-server/install/configure-a-service-account-ssrs-configuration-manager.md).  
  
## <a name="choosing-an-account"></a>Auswählen eines Kontos  
 Sie können den Berichtsserver-Dienst zur Ausführung unter einem der folgenden Kontotypen konfigurieren:  
  
-   Windows-Benutzerkonto mit minimalen Privilegien  
  
-   NetworkService  
  
-   LocalSystem  
  
-   LocalService  
  
 Es gibt nicht den einen idealen Ansatz zum Auswählen eines Kontotyps. Jedes Konto hat Vor- und Nachteile, die Sie berücksichtigen sollten. Bei der Bereitstellung [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] auf einem Produktionsserver bewährte wird empfohlen, die Sie konfigurieren, dass den Dienst unter einem Domänenbenutzerkonto ausgeführt wird, sodass Sie Schäden vermeiden können, wenn ein freigegebenes Konto von einem böswilligen Benutzer gefährdet ist. Dies erleichtert ferner die Überwachung der Anmeldeaktivitäten für dieses Konto. Verwenden Sie ein Windows-Benutzerkonto ist, die bei der Bereitstellung [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in einem Netzwerk, die Kerberos-Authentifizierung verwendet, müssen Sie den Dienst registrieren, mit dem Benutzerkonto an. Weitere Informationen finden Sie unter [Registrieren eines Dienstprinzipalnamens (SPN) für einen Berichtsserver](../report-server/register-a-service-principal-name-spn-for-a-report-server.md).  
  
 Die folgenden Richtlinien und Links in diesem Abschnitt können Ihnen helfen, den für Ihre Bereitstellung am besten geeigneten Ansatz zu finden.  
  
-   [-Dienstkonto &#40;SSRS im einheitlichen Modus&#41;](../../sql-server/install/service-account-ssrs-native-mode.md).  
  
-   [Konfigurieren von Windows-Dienstkonten und -Berechtigungen](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md) in SQL Server-Onlinedokumentation.  
  
-   [The Services and Service Accounts Security Planning Guide](http://go.microsoft.com/fwlink/?LinkId=69155) auf MSDN.  
  
## <a name="updating-an-expired-password"></a>Aktualisieren eines abgelaufenen Kennworts  
 Wenn der Berichtsserver-Dienst unter einem Domänenkonto ausgeführt wird und das Kennwort abläuft, bevor Sie es im Reporting Services-Konfigurationstool aktualisieren können, wird der Dienst erst wieder gestartet, wenn Sie ein neues Kennwort angeben. Wenn der Dienst nicht gestartet werden kann, können Sie mit dem Reporting Services-Konfigurationstool keine Verbindung zum Server herstellen, um das Konto zu aktualisieren. In diesem Fall müssen Sie den Server mit einer Reihe von Tools wieder online schalten.  
  
 Gehen Sie wie folgt vor, um das Kennwort zurückzusetzen:  
  
1.  Auf der **starten** Sie im Menü **Systemsteuerung**, zeigen Sie auf **Administratortools**, und klicken Sie auf **Services**.  
  
2.  Mit der rechten Maustaste **SQL Server Reporting Services**Option **Eigenschaften**.  
  
3.  Klicken Sie auf **anmelden**, und geben Sie das neue Kennwort.  
  
4.  Nachdem Sie das Kennwort aktualisiert haben, starten Sie das [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Konfigurationstool, und aktualisieren Sie das Kenwort auf der Seite Dienstkonto. Dieser zusätzliche Schritt ist erforderlich, um die Kontoinformationen zu aktualisieren, die intern vom Berichtsserver gespeichert werden.  
  
 Wenn das Kennwort des Dienstkontos für das [!INCLUDE[ssDE](../../includes/ssde-md.md)] abgelaufen ist, tritt beim Versuch, eine Verbindung mit dem Berichtsserver herzustellen, der Fehler `rsReportServerDatabaseUnavailable` auf. Durch Zurücksetzen des Kennworts wird der Fehler behoben.  
  
## <a name="configuring-the-report-server-service-for-a-sharepoint-integrated-report-server"></a>Konfigurieren des Berichtsserver-Diensts für einen in SharePoint integrierten Berichtsserver  
 Wenn Sie einen Berichtsserver im integrierten SharePoint-Modus ausführen, müssen die Dienstkontoinformationen aktualisiert werden, die in der SharePoint-Konfigurationsdatenbank gespeichert sind, sofern eine der folgenden Bedingungen zutrifft:  
  
-   Änderung des [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Dienstkontos (z.&B. Wechsel von einem NetworkService-Konto zu einem Domänenbenutzerkonto).  
  
-   Erweiterung einer SharePoint-Farm für eine weitere SharePoint-Webanwendung. Eine Aktualisierung der Datenbankzugriffsinformationen ist erforderlich, wenn die Serverfarm für die Berichtsserverintegration konfiguriert wurde, während die neu hinzugefügte Anwendung zur Ausführung unter einem anderen Benutzerkonto als die Anwendungen in der Farm konfiguriert wurde.  
  
 Nach dem Zurücksetzen der Datenbankzugriffsinformationen sollten Sie den [!INCLUDE[winSPServ](../../includes/winspserv-md.md)]-Dienst neu starten, um sicherzustellen, dass die alte Verbindung nicht mehr verwendet wird.  
  
1.  In **Verwaltung**, klicken Sie auf **SharePoint 2010-Zentraladministration**.  
  
2.  Klicken Sie auf **Anwendungsverwaltung**.  
  
3.  Klicken Sie im Abschnitt Reporting Services auf **Datenbankzugriff**.  
  
4.  Klicken Sie auf **OK**. Das Dialogfeld Anmeldeinformationen eingeben wird angezeigt.  
  
5.  Geben Sie die Anmeldeinformationen eines Benutzers ein, der ein Mitglied der Gruppe lokaler Administratoren auf dem Computer ist, der den Berichtsserver hostet. Die Anmeldeinformationen werden für eine einmalige Verbindung mit dem Berichtsservercomputer zum Abrufen von Dienstkontoinformationen verwendet. Die für jedes Dienstkonto erstellte Datenbankanmeldung wird in SharePoint-Datenbanken aktualisiert.  
  
6.  Um den Dienst zu starten, klicken Sie auf **Operations**.  
  
7.  Klicken Sie in der Topologie und Dienste auf **Dienste auf dem Server**.  
  
8.  Windows SharePoint Services-Web-Anwendung, klicken Sie auf **beenden**.  
  
9. Warten Sie, bis der Dienst beendet wird.  
  
10. Klicken Sie auf **starten**.  
  
> [!NOTE]  
>  Für SharePoint-Produkte und -Technologien sind Domänenkonten zur Dienstkonfiguration erforderlich, wie der SharePoint-Modus für Reporting Services.  
  
## <a name="see-also"></a>Siehe auch  
 [Konfigurieren eines Dienstkontos &#40;SSRS-Konfigurations-Manager&#41;](../../sql-server/install/configure-a-service-account-ssrs-configuration-manager.md)   
 [-Dienstkonto &#40;SSRS im einheitlichen Modus&#41;](../../sql-server/install/service-account-ssrs-native-mode.md)   
 [Konfigurieren von Berichtsserver-URLs &#40;SSRS-Konfigurations-Manager&#41;](configure-report-server-urls-ssrs-configuration-manager.md)   
 [Reporting Services-Konfigurations-Manager &#40;einheitlicher Modus&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md)  
  
  