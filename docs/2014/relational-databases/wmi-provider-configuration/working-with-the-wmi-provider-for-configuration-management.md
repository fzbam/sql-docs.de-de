---
title: Arbeiten mit dem WMI-Anbieter für die Verwaltung | Microsoft Docs
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
- permissions [WMI]
- connection strings [WMI]
- security [WMI]
- WMI Provider for Configuration Management, connection strings
- WMI Provider for Configuration Management, security
- late binding [WMI]
- WMI Provider for Configuration Management, late binding
- binding [WMI]
ms.assetid: 34daa922-7074-41d0-9077-042bb18c222a
caps.latest.revision: 22
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 757c5bf468ff1c9fb2b5d493121a9e4b7daab144
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36046409"
---
# <a name="working-with-the-wmi-provider-for-configuration-management"></a>Arbeiten mit dem WMI-Anbieter für die Konfigurationsverwaltung
  Beachten Sie vor dem Programmieren mit dem WMI-Anbieter für die Computerverwaltung die folgenden Punkte:  
  
## <a name="binding"></a>Bindung  
 Der WMI-Anbieter für die Konfigurationsverwaltung ist ein COM-Objektmodell und unterstützt frühes und spätes Binden. Mit spätem Binden können Sie Skriptsprachen wie VBScript verwenden, um die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Dienste, Netzwerkeinstellungen und Aliasnamen programmgesteuert zu bearbeiten.  
  
 Weitere Informationen über das Programmieren von WMI-anbieterimplementierungen mit Skriptsprachen finden Sie unter der [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN [Website](http://go.microsoft.com/fwlink/?linkid=15426).  
  
## <a name="specifying-a-connection-string"></a>Angeben einer Verbindungszeichenfolge  
 Anwendungen leiten den WMI-Anbieter für die Konfigurationsverwaltung an eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] weiter, indem sie eine Verbindung zu einem vom Anbieter definierten WMI-Namespace herstellen. Der Windows-WMI-Dienst ordnet der Anbieter-DLL diesen Namespace zu und lädt sie in den Arbeitsspeicher. Alle Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] werden mit einem einzigen WMI-Namespace dargestellt. Der Namespace lautet standardmäßig  
  
```  
\\.\root\Microsoft\SqlServer\ComputerManagement12\instance_name  
```  
  
 wobei `instance_name` in einer Standardinstallation von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] standardmäßig auf `MSSQLSERVER` festgelegt wird.  
  
 **Hinweis:** , wenn Sie über Windows-Firewall eine Verbindung herstellen müssen Sie sicherstellen, dass Ihre Computer ordnungsgemäß konfiguriert sind. Finden Sie im Artikel "Connecting Through Windows Firewall" in der Dokumentation zu Windows-Verwaltungsinstrumentation auf [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN [Website](http://go.microsoft.com/fwlink/?linkid=15426).  
  
## <a name="permissions-and-server-authentication"></a>Berechtigungen und Serverauthentifizierung  
 Für den Zugriff auf den WMI-Anbieter für die Konfigurationsverwaltung muss das WMI-Verwaltungsskript des Clients im Kontext eines Administrators auf dem Zielcomputer ausgeführt werden. Sie müssen ein Mitglied der lokalen Windows-Administratorengruppe auf dem Computer sein, den Sie verwalten möchten.  
  
 Der Administrator kann Gruppenrichtlinien festlegen, um den Benutzerzugriff auf WMI-Anbieter zu kontrollieren. Weitere Informationen zum Festlegen von Gruppenrichtlinien finden Sie im Abschnitt zu Gruppenrichtlinien und MMC in der Hilfe zum [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Konfigurations-Manager.  
  
 Das WMI-Verwaltungsskript kann zum Aktualisieren des Kontos verwendet werden, unter dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Dienste ausgeführt werden.  
  
 Sicherheitszertifikate werden vom WMI-Anbieter für die Konfigurationsverwaltung unterstützt. Weitere Informationen zu Zertifikaten finden Sie unter [Verschlüsselungshierarchie](../security/encryption/encryption-hierarchy.md).  
  
## <a name="see-also"></a>Siehe auch  
 [SQL Server-Konfigurations-Manager](../sql-server-configuration-manager.md)  
  
  