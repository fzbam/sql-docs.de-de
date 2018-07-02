---
title: Servereigenschaften (Seite „Prozessoren“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql12.swb.serverproperties.processor.f1
ms.assetid: cc1581a2-492b-41f0-bda5-17909b65c4f7
caps.latest.revision: 24
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: 0c857a8095f304bb1c97a31c1e0b5cfbc8c265fd
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36160286"
---
# <a name="server-properties-processors-page"></a>Servereigenschaften (Seite Prozessoren)
  Auf dieser Seite können Sie die Prozessoroptionen anzeigen und ändern. Prozessoraffinitätsoptionen sind nur aktiviert, wenn mehr als ein Prozessor installiert ist.  
  
## <a name="options"></a>Tastatur  
 **Prozessoraffinität**  
 Weist Prozessoren bestimmte Threads zu, um ein Neuladen des Prozessors zu verhindern und die Threadmigration zwischen Prozessoren zu reduzieren. Weitere Informationen finden Sie unter [Affinitätsmaske (Serverkonfigurationsoption)](affinity-mask-server-configuration-option.md).  
  
 **E/A-Affinität**  
 Verbindet die Datenträger-E/A-Operationen von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mit einer angegebenen CPU-Untergruppe. Weitere Informationen finden Sie unter [Affinity I/O Mask (Serverkonfigurationsoption)](affinity-input-output-mask-server-configuration-option.md).  
  
 **Prozessor-Affinitätsmaske für alle Prozessoren automatisch festlegen**  
 Ermöglicht es [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , die Prozessoraffinität festzulegen.  
  
 **E/A-Affinitätsmaske für alle Prozessoren automatisch festlegen**  
 Ermöglicht es [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , die E/A-Affinität festzulegen.  
  
 **Maximale Arbeitsthreadanzahl**  
 0 ermöglicht es [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , die Anzahl der Arbeitsthreads dynamisch festzulegen. Diese Einstellung ist für die meisten Systeme am besten geeignet. In Abhängigkeit von der Systemkonfiguration kann jedoch durch Festlegen dieser Option auf einen bestimmten Wert manchmal die Leistung verbessert werden. Weitere Informationen finden Sie unter [Configure the max worker threads Server Configuration Option](configure-the-max-worker-threads-server-configuration-option.md).  
  
 **SQL Server-Priorität höher stufen**  
 Gibt an, ob [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unter [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows mit höherer Planungspriorität als andere Prozesse auf dem gleichen Computer ausgeführt werden soll. Weitere Informationen finden Sie unter [Configure the priority boost Server Configuration Option](configure-the-priority-boost-server-configuration-option.md).  
  
 **Windows-Fibers verwenden ('Lightweightpooling')**  
 Verwendet Windows-Fibers für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst statt Threads. Beachten Sie, dass diese Option nur unter Windows 2003 Server Edition verfügbar ist. Weitere Informationen finden Sie unter [Lightweightpooling (Serverkonfigurationsoption)](lightweight-pooling-server-configuration-option.md).  
  
 **Konfigurierte Werte**  
 Zeigt für die Optionen in diesem Bereich konfigurierte Werte an. Wenn Sie diese Werte ändern, klicken Sie anschließend auf **Ausgeführte Werte** , um zu sehen, ob die Änderungen wirksam sind. Sind sie nicht wirksam, muss die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zuerst neu gestartet werden.  
  
 **Ausgeführte Werte**  
 Zeigt die gegenwärtig ausgeführten Werte für die Optionen in diesem Bereich an. Diese Werte sind schreibgeschützt.  
  
## <a name="see-also"></a>Siehe auch  
 [Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md)  
  
  