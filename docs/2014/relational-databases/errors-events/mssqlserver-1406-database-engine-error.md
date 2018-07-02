---
title: MSSQLSERVER_1406 | Microsoft-Dokumentation
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
- 1406 (Database Engine error)
ms.assetid: 915f97de-9b74-41f8-8bd5-b2d061416718
caps.latest.revision: 15
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 259d6e37f0798cfacaac39c89dec091053c16c57
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36050137"
---
# <a name="mssqlserver1406"></a>MSSQLSERVER_1406
    
## <a name="details"></a>Details  
  
|||  
|-|-|  
|Produktname|SQL Server|  
|Ereignis-ID|1406|  
|Ereignisquelle|MSSQLSERVER|  
|Komponente|SQLEngine|  
|Symbolischer Name|DBM_BADSTATEFORFORCESERVICE|  
|Meldungstext|Der Dienst kann nicht auf sichere Weise erzwungen werden. Entfernen Sie die Datenbankspiegelung, und stellen Sie die "%.*ls"-Datenbank wieder her, um Zugriff zu erhalten.|  
  
## <a name="explanation"></a>Erklärung  
 Der Dienst kann von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] nicht erzwungen werden, da mit dem Spiegelungsstatus nicht garantiert werden kann, dass der erzwungene Dienstvorgang ordnungsgemäß funktioniert.  
  
## <a name="user-action"></a>Benutzeraktion  
 Entfernen Sie die Datenbankspiegelung. Sie können anschließend die Spiegeldatenbank wiederherstellen, um Zugriff zu erhalten.  
  
## <a name="see-also"></a>Siehe auch  
 [Erzwingen des Diensts in einer Datenbank-Spiegelungssitzung (Transact-SQL)](../../database-engine/database-mirroring/force-service-in-a-database-mirroring-session-transact-sql.md)   
 [Entfernen der Datenbankspiegelung &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md)  
  
  