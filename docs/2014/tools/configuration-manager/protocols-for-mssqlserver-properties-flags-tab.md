---
title: Protokolle für MSSQLSERVER-Eigenschaften (Registerkarte „Flags“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- configmgr-client
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSSQLSERVER property protocols
ms.assetid: 4d38e6e9-f95f-4e79-ae45-89f631037528
caps.latest.revision: 31
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: d03ccbb73a848b02f8f388305004020264c25b14
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36159894"
---
# <a name="protocols-for-mssqlserver-properties-flags-tab"></a>Protokolle für MSSQLSERVER-Eigenschaften (Registerkarte Flags)
  Wenn auf dem Server ein Zertifikat installiert ist, verwenden Sie die Registerkarte **Flags** im Dialogfeld **Eigenschaften von Protokolle für 'MSSQLSERVER'** , um die Protokollverschlüsselung anzuzeigen oder anzugeben und Instanzoptionen auszublenden. [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] muss neu gestartet werden, um die **ForceEncryption** -Einstellung zu aktivieren oder zu deaktivieren.  
  
 Zum Verschlüsseln von Verbindungen sollten Sie [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] mit einem Zertifikat bereitstellen. Wenn kein Zertifikat installiert ist, generiert [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ein selbstsigniertes Zertifikat, sobald die Instanz gestartet wird. Dieses selbstsignierte Zertifikat kann anstelle eines Zertifikats von einer vertrauenswürdigen Zertifizierungsstelle verwendet werden. Es ermöglicht jedoch keine Authentifizierung und verhindert auch keine Nichtanerkennung.  
  
> [!CAUTION]  
>  Verschlüsselte SSL-Verbindungen (Secure Sockets Layer), die ein selbstsigniertes Zertifikat verwenden, bieten keine hohe Sicherheit. Sie sind anfällig für "Man-in-the-Middle"-Angriffe. In einer Produktionsumgebung oder auf Servern, die mit dem Internet verbunden sind, sollten Sie sich nicht auf SSL mit Verwendung selbstsignierter Zertifikate verlassen.  
  
 Weitere Informationen zur Verschlüsselung finden Sie unter "Verschlüsseln von Verbindungen zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Onlinedokumentation.  
  
 Der Anmeldeprozess ist immer verschlüsselt. Wenn **ForceEncryption** auf **Ja**festgelegt ist, wird jegliche Client/Server-Kommunikation verschlüsselt. Clients, die mit [!INCLUDE[ssDE](../../includes/ssde-md.md)] verbunden sind, müssen so konfiguriert werden, dass sie der Stammzertifizierungsstelle des Serverzertifikats vertrauen. Weitere Informationen finden Sie unter „Vorgehensweise: Aktivieren von verschlüsselten Verbindungen zum [!INCLUDE[ssDE](../../includes/ssde-md.md)] ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager)“ in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Onlinedokumentation.  
  
## <a name="cluster-servers"></a>Clusterserver  
 Wenn Sie die Verschlüsselung bei einem Failovercluster verwenden möchten, müssen Sie das Serverzertifikat mit dem vollgekennzeichneten DNS-Namen des virtuellen Servers auf allen Knoten im Failovercluster installieren. Wenn Sie z.B. über einen Cluster mit zwei Knoten verfügen, wobei die Knotennamen „test1.*\<Ihr Unternehmen>*.com“ und „test2.*\<Ihr Unternehmen>*.com“ lauten, und ein virtueller Server den Namen „virtsql“ trägt, müssen Sie ein Zertifikat für „virtsql.*\<Ihr Unternehmen>*.com“ auf beiden Knoten installieren. Sie können dann das Kontrollkästchen **ForceEncryption** in **SQL Server-Konfigurations-Manager** aktivieren, um den Failovercluster für die Verschlüsselung zu konfigurieren.  
  
## <a name="options"></a>Tastatur  
 **ForceEncryption**  
 Erzwingen Sie die Protokollverschlüsselung. Die Verschlüsselung ist eine Methode, sensible Informationen vertraulich zu behandeln, indem Daten in eine nicht lesbare Form geändert werden. Durch die Verschlüsselung wird die Sicherheit von Daten sichergestellt, selbst wenn die Übertragungspakete während des Übertragungsvorgangs angezeigt werden. Für die Benutzung von Channelbindung, setzen Sie **Verschlüsselung erzwingen** auf **Ein** , und konfigurieren Sie **Erweiterten Schutz** auf der Registerkarte **Erweitert** .  
  
 **HideInstance**  
 Verhindert, dass der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Browser-Dienst diese Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] für Clientcomputer verfügbar macht, die mithilfe der Schaltfläche **Durchsuchen** versuchen, die Instanz zu finden. Wenn benannte Instanzen auf dem Server vorhanden sind, müssen Clientanwendungen beim Verbinden die Protokollendpunktinformationen angeben. Zum Beispiel die Portnummer oder named Pipe-Namen wie `tcp:server,5000`. Weitere Informationen finden Sie unter [Logging In to SQL Server](../../database-engine/configure-windows/logging-in-to-sql-server.md).  
  
 Weitere Informationen finden Sie in der Onlinedokumentation unter "Vorgehensweise: Aktivieren von Verschlüsselungsverbindungen für die Datenbank-Engine (SQL Server-Konfigurations-Manager)".  
  
  