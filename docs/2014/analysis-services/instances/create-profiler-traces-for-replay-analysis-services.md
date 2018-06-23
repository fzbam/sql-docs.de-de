---
title: Erstellen von Profilerablaufverfolgungen für Replay (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SQL Server Profiler, Analysis Services
- monitoring Analysis Services [SQL Server]
- replaying queries
- replaying discovers
- events [Analysis Services]
- replaying commands
- Profiler [SQL Server Profiler], Analysis Services
- performance [Analysis Services], replays
- traces [Analysis Services]
ms.assetid: 93b2fc46-7cfb-4ab5-abeb-1475a7d6f0f2
caps.latest.revision: 32
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: 19b7277c52294d88743af5bf99d099a8df4f2f19
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36060837"
---
# <a name="create-profiler-traces-for-replay-analysis-services"></a>Erstellen von Profilerablaufverfolgungen für Replay (Analysis Services)
  Für die Wiedergabe von Abfragen, Ermittlungen und Befehlen, die von Benutzern an [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] die erforderlichen Ereignisse sammeln. Um die Sammlung dieser Ereignisse zu initiieren, müssen auf der Registerkarte **Ereignisauswahl** des Dialogfelds **Ablaufverfolgungseigenschaften** geeignete Ereignisklassen ausgewählt werden. Wenn z. B. die Query Begin-Ereignisklasse ausgewählt ist, werden Ereignisse mit Abfragen gesammelt und für die Wiedergabe verwendet. Die Ablaufverfolgungsdatei enthält außerdem ausreichende Informationen, um die Wiedergabe von Servertransaktionen in einer verteilten Umgebung in der ursprünglichen Abfolge von Transaktionen zu unterstützen.  
  
## <a name="replay-for-queries"></a>Wiedergabe für Abfragen  
 Zur Wiedergabe von Abfragen muss [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] die folgenden Ereignisse erfassen:  
  
-   „Audit Login“-Ereignisklasse mit allen zugehörigen Datenspalten. Diese Ereignisklasse stellt Informationen zu den angemeldeten Benutzern und zu den Sitzungseinstellungen bereit. Die Serverprozess-ID (SPID) verweist auf die betreffende Benutzersitzung. Weitere Informationen finden Sie unter [Security Audit Data Columns](../trace-events/security-audit-data-columns.md).  
  
-   „Query Begin“-Ereignisklasse mit allen zugehörigen Datenspalten. Diese Ereignisklasse stellt Informationen zu der an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]gesendeten Abfrage bereit. Die Event Subclass-Spalte stellt Informationen zum Typ der Abfrage bereit. Der eigentliche Text der Abfrage wird in der TextData-Spalte bereitgestellt. Die RequestParameters-Spalte stellt die Parameter für parametrisierte Abfragen bereit, und die RequestProperties-Spalte stellt die Eigenschaften einer XMLA-Anforderung (XML for Analysis) bereit. Weitere Informationen finden Sie unter [Queries Events Data Columns](../trace-events/queries-events-data-columns.md).  
  
-   „Query End“-Ereignisklasse mit allen zugehörigen Datenspalten. Diese Ereignisklasse überprüft den Status der Abfrageausführung. Weitere Informationen finden Sie unter [Queries Events Data Columns](../trace-events/queries-events-data-columns.md).  
  
## <a name="replay-for-discovers"></a>Wiedergabe für Ermittlungen  
 Zur Wiedergabe von Ermittlungen muss [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] die folgenden Ereignisse erfassen:  
  
-   „Audit Login“-Ereignisklasse mit allen zugehörigen Datenspalten. Diese Ereignisklasse stellt Informationen zu den angemeldeten Benutzern und zu den Sitzungseinstellungen bereit. Die SPID (Serverprozess-ID) stellt die betreffende Benutzersitzung bereit. Weitere Informationen finden Sie unter [Security Audit Data Columns](../trace-events/security-audit-data-columns.md).  
  
-   „Discover Begin“-Ereignisklasse mit allen zugehörigen Datenspalten. Die TextData-Spalte enthält die \<RequestType > Teil die Discover-Anforderung, und die RequestProperties-Spalte enthält die \<Eigenschaften >-Teil der ermittlungsanforderung. Der Ermittlungstyp wird in der EventSubclass-Spalte bereitgestellt. Weitere Informationen finden Sie unter [Discover Events Data Columns](../trace-events/discover-events-data-columns.md).  
  
-   „Discover End“-Ereignisklasse mit allen zugehörigen Datenspalten. Diese Ereignisklasse überprüft den Status der Ermittlungsanforderung. Weitere Informationen finden Sie unter [Discover Events Data Columns](../trace-events/discover-events-data-columns.md).  
  
## <a name="replay-for-commands"></a>Wiedergabe für Befehle  
 Zur Wiedergabe von Befehlen muss [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] die folgenden Ereignisse erfassen:  
  
-   „Command Begin“-Ereignisklasse mit allen zugehörigen Datenspalten. Die TextData-Spalte stellt die Befehlsdetails bereit, z.B. den Prozesstyp, die Datenbank-ID und die Cube-ID. Die RequestParameters-Spalte stellt die Parameter für parametrisierte Befehle bereit, und die RequestProperties-Spalte stellt die Eigenschaften einer XMLA-Anforderung bereit. Weitere Informationen finden Sie unter [Command Events Data Columns](../trace-events/command-events-data-columns.md).  
  
-   „Command End“-Ereignisklasse mit allen zugehörigen Datenspalten. Diese Ereignisklasse überprüft den Status des Befehls. Weitere Informationen finden Sie unter [Command Events Data Columns](../trace-events/command-events-data-columns.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Analysis Services-Ablaufverfolgungsereignisse](../trace-events/analysis-services-trace-events.md)   
 [Einführung in die Überwachung von Analysis Services mit SQL Server Profiler](introduction-to-monitoring-analysis-services-with-sql-server-profiler.md)  
  
  