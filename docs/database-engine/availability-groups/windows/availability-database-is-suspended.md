---
title: Verfügbarkeitsdatenbank angehalten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 05/17/2016
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.technology: high-availability
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql13.swb.agdashboard.drp1notsuspended.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 6baee70f-848c-4e86-b20d-78875c0f82cb
caps.latest.revision: 15
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 890e178af2d0f4577dce42e681a6156ae99b0246
ms.sourcegitcommit: 8aa151e3280eb6372bf95fab63ecbab9dd3f2e5e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2018
ms.locfileid: "34769956"
---
# <a name="availability-database-is-suspended"></a>Verfügbarkeitsdatenbank angehalten
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
    
## <a name="introduction"></a>Einführung  
  
|||  
|-|-|  
|**Richtlinienname**|Verfügbarkeitsdatenbank im angehaltenen Zustand|  
|**Problem**|Die Verfügbarkeitsdatenbank wurde angehalten.|  
|**Kategorie**|**Warnung**|  
|**Facet**|Verfügbarkeitsdatenbank|  
  
## <a name="description"></a>und Beschreibung  
 Diese Richtlinie überprüft den Status der Datenverschiebung für die sekundäre Datenbank (auch bekannt als "sekundäres Datenbankreplikat"). Die Richtlinie befindet sich in einem fehlerhaften Zustand, wenn die Datenverschiebung angehalten wird. Die Richtlinie befindet sich andernfalls in einem ordnungsgemäßen Zustand.  
  
> [!NOTE]  
>  Für diese Version von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]finden Sie Informationen zu möglichen Ursachen und Lösungen im TechNet Wiki unter [Availability database is suspended](http://go.microsoft.com/fwlink/p/?LinkId=220860) .  
  
## <a name="possible-causes"></a>Mögliche Ursachen  
 Die Datensynchronisierung dieser Verfügbarkeitsdatenbank kann aus den folgenden Gründen angehalten worden sein:  
  
-   Aufgrund eines Fehlers kann es sein, dass das System die Datensynchronisierung angehalten hat.  
  
-   Der Datenbankadministrator hat die Datensynchronisierung ggf. zu Wartungszwecken angehalten.  
  
## <a name="possible-solution"></a>Mögliche Lösung  
 Setzen Sie die Datensynchronisierung fort. Falls das Problem weiterhin auftritt, sollten Sie die Verfügbarkeitsgruppe im Ereignisprotokoll überprüfen und dann diagnostizieren, warum das System die Datenverschiebung angehalten hat.  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
 [Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](../../../database-engine/availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md)   
 [Verwenden des AlwaysOn-Dashboards &#40;SQL Server Management Studio&#41;](../../../database-engine/availability-groups/windows/use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
