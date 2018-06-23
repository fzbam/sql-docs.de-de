---
title: 'Vorgehensweise: Bereitstellen einer Datenverarbeitungserweiterung für den Berichts-Designer | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- data processing extensions [Reporting Services], deploying
- assemblies [Reporting Services], data processing extension deployments
ms.assetid: 3614e601-004e-4a16-8388-836ffd67e9dd
caps.latest.revision: 40
author: douglaslM
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: f95040735e7ec8987bfdfd194ef1d7f0933df3ed
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36049128"
---
# <a name="how-to-deploy-a-data-processing-extension-to-report-designer"></a>Vorgehensweise: Bereitstellen einer Datenverarbeitungserweiterung für den Berichts-Designer
  Beim Entwerfen von Berichten verwendet der Berichts-Designer Datenverarbeitungserweiterungen zum Abruf und zur Verarbeitung von Daten. Sie sollten Ihre Assembly für Datenverarbeitungserweiterungen auf dem Berichts-Designer als private Assembly bereitstellen. Sie müssen auch einen Eintrag in der Konfigurationsdatei des Berichts-Designers RSReportDesigner.config vornehmen.  
  
#### <a name="to-deploy-a-data-processing-extension-assembly"></a>So stellen Sie eine Assembly für Datenverarbeitungserweiterungen bereit  
  
1.  Kopieren Sie die Assembly aus dem Bereitstellungsverzeichnis in das Verzeichnis „Berichts-Designer“. Das Standardverzeichnis für den Berichts-Designer ist C:\Programme\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.  
  
2.  Nachdem die Assemblydatei kopiert wurde, öffnen Sie die Datei RSReportDesigner.config. Die Datei RSReportDesigner.config befindet sich auch im Verzeichnis „Berichts-Designer“. Sie müssen einen Eintrag in der Konfigurationsdatei für die Datei Ihrer Datenverarbeitungserweiterungsassembly vornehmen. Sie können die Konfigurationsdatei mit [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] oder in einem einfachen Text-Editor wie dem Editor öffnen.  
  
3.  Suchen Sie das **Data** -Element in der Datei RSReportDesigner.config. In folgendem Verzeichnis muss ein Eintrag für Ihre neu erstellte Datenverarbeitungserweiterung erstellt werden:  
  
    ```  
    <Extensions>  
       <Data>  
          <Your extension configuration information goes here>  
       </Data>  
    </Extensions>  
    ```  
  
4.  Fügen Sie einen Eintrag für Ihre datenverarbeitungserweiterung enthält ein **Erweiterung** Element mit Werten für die `Name`, `Type`, und `Visible` Attribute. Der Eintrag könnte folgendermaßen aussehen:  
  
    ```  
    <Extension Name="ExtensionName" Type="CompanyName.ExtensionName.MyConnectionClass, AssemblyName" />  
    ```  
  
     Der Wert für `Name` ist der eindeutige Name der Datenverarbeitungserweiterung. Der Wert für `Type` ist eine durch Trennzeichen getrennte Liste, die einen Eintrag für den vollqualifizierten Namespace der Klasse enthält, welche die Schnittstellen <xref:Microsoft.ReportingServices.Interfaces.IExtension> und <xref:Microsoft.ReportingServices.DataProcessing.IDbConnection> implementiert, gefolgt vom Namen der Assembly (ohne die Dateierweiterung .dll). Standardmäßig sind Datenverarbeitungserweiterungen sichtbar. Eine Erweiterung in Benutzeroberflächen wie dem Berichts-Designer auszublenden Hinzufügen einer `Visible` -Attribut auf die **Erweiterung** Element, und legen Sie dafür `false`.  
  
5.  Zuletzt müssen Sie eine Codegruppe für die benutzerdefinierte Assembly hinzufügen, die die Berechtigung **FullTrust** für Ihre Erweiterung erteilt. Hierzu fügen Sie die Codegruppe zur Datei rspreviewpolicy.config hinzu, die sich standardmäßig im Verzeichnis C:\Programme\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies befindet. Die Codegruppe kann folgendermaßen aussehen:  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="MyExtensionCodeGroup"  
       Description="Code group for my data processing extension">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url="C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies\MyExtensionAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
 Die URL-Mitgliedschaft ist eine der vielen Mitgliedschaftsbedingungen, die Sie für die Datenverarbeitungserweiterung auswählen können. Weitere Informationen zur Codezugriffssicherheit in [!INCLUDE[ssRSversion2005](../../../includes/ssrsversion2005-md.md)] finden Sie unter [Sichere Entwicklung (Reporting Services)](../secure-development/secure-development-reporting-services.md).  
  
## <a name="generic-query-designer"></a>Standardabfrage-Designer  
 Der Berichts-Designer enthält einen Standardabfrage-Designer, den Sie zusammen mit den benutzerdefinierten Datenverarbeitungserweiterungen verwenden können. Dieser Designer besteht aus zwei Bereichen: dem Abfragebereich und dem Ergebnisbereich. Sie können den Standard-Designer verwenden, um Abfragen zu schreiben, die nicht von der grafischen Oberfläche unterstützt werden. Im Gegensatz zum grafischen Abfrage-Designer wird die Abfragesyntax vom Standardabfrage-Designer nicht überprüft und die Abfrage nicht umstrukturiert.  
  
#### <a name="to-enable-the-generic-query-designer-for-a-custom-extension"></a>So aktivieren Sie den Standardabfrage-Designer für eine benutzerdefinierte Erweiterung  
  
-   Fügen Sie den folgenden Eintrag zur Datei RSReportDesigner.config unter der **Designer** Element, und Ersetzen Sie dabei die `Name` Attribut mit dem Namen, den Sie in vorhergehenden Einträgen angegeben.  
  
    ```  
    <Extension Name="ExtensionName" Type="Microsoft.ReportingServices.QueryDesigners.GenericQueryDesigner,Microsoft.ReportingServices.QueryDesigners"/>  
    ```  
  
## <a name="verifying-the-deployment"></a>Überprüfen der Bereitstellung  
 Sie können die Bereitstellung erst überprüfen, wenn Sie alle Instanzen von [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] auf Ihrem lokalen Computer geschlossen haben. Wenn Sie alle aktuellen Sitzungen beendet haben, können Sie überprüfen, ob die Datenverarbeitungserweiterung erfolgreich für den Berichts-Designer bereitgestellt wurde, indem Sie in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] ein neues Berichtsprojekt erstellen. Die Erweiterung sollte beim Erstellen eines neuen Datasets für den Bericht in der Liste der verfügbaren Datenquellentypen aufgeführt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Bereitstellen von Datenverarbeitungserweiterungen](deploying-a-data-processing-extension.md)   
 [Erweiterungen für Reporting Services](../reporting-services-extensions.md)   
 [Implementieren von Datenverarbeitungserweiterungen](implementing-a-data-processing-extension.md)   
 [Reporting Services Extension Library (Reporting Services-Erweiterungsbibliothek)](../reporting-services-extension-library.md)  
  
  