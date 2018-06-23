---
title: Nicht mehr unterstützte, Verwaltungstools-Funktionen in SQLServer 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- tools-ssms
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e58acd0-73c5-4161-9fbc-8ea531bc681c
caps.latest.revision: 27
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 4c166f5c6bf6676b5af2eb0fc53810bb317718de
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36059676"
---
# <a name="discontinued-management-tools-features-in-sql-server-2014"></a>Nicht mehr unterstützte Funktionen der Verwaltungstools in SQL Server 2014
  In diesem Thema werden die Funktionen der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Verwaltungstools beschrieben, die in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]nicht mehr verfügbar sind.  
  
## <a name="features-removed-in-includesscurrentincludessscurrent-mdmd"></a>Entfernte Features [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]  
 InclusionThresholdSetting  
  
## <a name="features-removed-in-includesssql11includessssql11-mdmd"></a>Entfernte Features [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]  
  
### <a name="sql-server-compact-edition"></a>SQL Server Compact Edition  
 Der SQL Server Compact Edition-Code-Editor wurde aus [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]entfernt. Unterstützung für SQL Server Compact Edition wurde auch aus Objekt-Explorer, Projektmappen-Explorer und Vorlagen-Explorer entfernt. Verwenden Sie stattdessen die Transact-SQL-Editoren in Microsoft Visual Studio 2010 Service Pack 1 oder Webmatrix.  
  
### <a name="activex-subsystem-for-sql-server-agent"></a>ActiveX-Subsystem für SQL Server-Agent  
 Das ActiveX-Subsystem für SQL Server-Agent wurde in dieser Version entfernt. Es gibt keine Ersatzfunktionalität.  
  
### <a name="spaddtask-spdeletetask-spupdatetask"></a>sp_addtask, sp_deletetask, sp_updatetask  
 Sp_addtask, sp_deletetask und sp_updatetask wurden in dieser Version entfernt. Verwenden Sie diese Funktionalität nicht in neuen oder aktualisierten Anwendungen.  
  
### <a name="net-send-and-pager-notification"></a>Net Send- und Pagerbenachrichtigung  
 Die Net Send- und Pagerbenachrichtigung wurde in dieser Version entfernt. Verwenden Sie diese Funktionalität nicht in neuen oder aktualisierten Anwendungen.  
  
### <a name="data-tier-applications"></a>Datenebenenanwendungen  
 Einige in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] enthaltene Funktionen von Datenebenenanwendungen (DAC) wurden in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]entfernt. Das mit [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] freigegebene Datenebenenanwendungs-Framework (DACfx, Version 3.0) ist jedoch mit [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)] bis [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] und [!INCLUDE[ssSDSfull](../includes/sssdsfull-md.md)] kompatibel. Die DAC-Version 3.0 wird von früheren Versionen von [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] einschließlich [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)]nicht unterstützt. Datenbankprojekte von Visual Studio 2010 unterstützen keine DACPAC-Pakete oder Exportpakete (BACPAC) der DAC-Version 3.0, die mit DACfx, Version 3.0 oder höher, generiert wurden.  
  
 Microsoft empfiehlt die Verwendung von Datenbankprojekten der neuesten verfügbaren [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools-Version.  
  
 Die DACfx 3.0-API und [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Tools unterstützen das Lesen von DACPAC- und BACPAC-Dateien, die mit früheren [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Toolversionen und DACfx-Versionen erstellt wurden: das Extrahieren von Datenbanken in DACPAC-Dateien aus diesen Versionen und das Bereitstellen von Datenbanken in unterstützten Versionen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] bis [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] oder [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools.  
  
## <a name="see-also"></a>Siehe auch  
 [Abwärtskompatibilität](../../2014/getting-started/backward-compatibility.md)  
  
  