---
title: MSSQLSERVER_18264 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 18264 (Database Engine error)
ms.assetid: 3050fc56-2be5-43cf-916b-50a3ac5f89aa
caps.latest.revision: 12
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e607fb016594ab24870ba60caa8a396e637453d7
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36159514"
---
# <a name="mssqlserver18264"></a>MSSQLSERVER_18264
    
## <a name="details"></a>Details  
  
|||  
|-|-|  
|Produktname|Microsoft SQL Server|  
|Ereignis-ID|18264|  
|Ereignisquelle|MSSQLENGINE|  
|Komponente|SQLEngine|  
|Symbolischer Name|STRMIO_DBDUMP|  
|Meldungstext|Die Datenbank wurde gesichert. Datenbank: %s, Erstellungsdatum(-zeit): %s(%s), gesicherte Seiten: %d, Erste LSN: %s, Letzte LSN: %s, Anzahl der Sicherungsgeräte: %d, Geräteinformationen: (%s). Diese Meldung dient nur zu Informationszwecken. Es ist keine Benutzeraktion erforderlich.|  
  
## <a name="explanation"></a>Erklärung  
 Standardmäßig wird diese Informationsmeldung bei jeder erfolgreichen Sicherung dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll und dem Systemereignisprotokoll hinzugefügt. Wenn Sie das Transaktionsprotokoll sehr häufig sichern, kann die Anzahl dieser Meldungen schnell ansteigen, d.h., es entstehen sehr große Fehlerprotokolle, die das Suchen nach anderen Meldungen erschweren können.  
  
## <a name="user-action"></a>Benutzeraktion  
 Sie können diese Protokolleinträge mit dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Ablaufverfolgungsflag **3226** unterdrücken. Es ist sehr hilfreich, dieses Ablaufverfolgungsflag zu aktivieren, wenn Sie regelmäßig Protokollsicherungen ausführen und keines der Skripts von diesen Einträgen abhängig ist.  
  
 Weitere Informationen zum Verwenden von Ablaufverfolgungsflags finden Sie in der SQL Server-Onlinedokumentation.  
  
## <a name="see-also"></a>Siehe auch  
 [Ablaufverfolgungsflags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql)  
  
  