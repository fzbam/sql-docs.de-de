---
title: Datensynchronisierungsstatus der Verfügbarkeitsdatenbank ist nicht fehlerfrei | Microsoft-Dokumentation
ms.custom: ''
ms.date: 05/17/2016
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.technology: high-availability
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql13.swb.agdashboard.arp3datasynchealthy.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 4fd003e7-808e-4b0e-b28a-47d9f2616f06
caps.latest.revision: 15
author: MashaMSFT
ms.author: mathoma
manager: erikre
ms.openlocfilehash: d8c98abcd48d9e1e703bd4e5ca73d62239727671
ms.sourcegitcommit: 8aa151e3280eb6372bf95fab63ecbab9dd3f2e5e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2018
ms.locfileid: "34770176"
---
# <a name="data-synchronization-state-of-availability-database-is-not-healthy"></a>Datensynchronisierungsstatus der Verfügbarkeitsdatenbank ist nicht fehlerfrei
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
    
## <a name="introduction"></a>Einführung  
  
|||  
|-|-|  
|**Richtlinienname**|Datensynchronisierungsstatus der Verfügbarkeitsdatenbank|  
|**Problem**|Der Datensynchronisierungsstatus der Verfügbarkeitsdatenbank ist nicht fehlerfrei.|  
|**Kategorie**|**Warnung**|  
|**Facet**|Verfügbarkeitsdatenbank|  
  
## <a name="description"></a>und Beschreibung  
 Diese Richtlinie führt ein Rollup des Datensynchronisierungsstatus aller Verfügbarkeitsdatenbanken (auch bekannt als "Datenbankreplikate") im Verfügbarkeitsreplikat aus. Die Richtlinie befindet sich in einem fehlerhaften Zustand, wenn ein beliebiges Datenbankreplikat nicht den erwarteten Datensynchronisierungsstatus aufweist. Die Richtlinie befindet sich andernfalls in einem ordnungsgemäßen Zustand.  
  
> [!NOTE]  
>  Für dieses Release von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]finden Sie Informationen zu möglichen Ursachen und Lösungen im TechNet Wiki unter [Datensynchronisierungsstatus einer Verfügbarkeitsdatenbank ist nicht fehlerfrei](http://go.microsoft.com/fwlink/p/?LinkId=220858) .  
  
## <a name="possible-causes"></a>Mögliche Ursachen  
 Der Datensynchronisierungsstatus dieser Verfügbarkeitsdatenbank ist fehlerhaft. Auf einem Verfügbarkeitsreplikat für asynchrone Commits sollte sich jede Verfügbarkeitsdatenbank im Status SYNCHRONIZING befinden. Auf einem Replikat für synchrone Commits muss sich jede Verfügbarkeitsdatenbank im Status SYNCHRONIZED befinden.  
  
## <a name="possible-solution"></a>Mögliche Lösung  
 Verwenden Sie die Datenbankreplikatrichtlinie zum Suchen nach dem Datenbankreplikat mit einem fehlerhaften Datensynchronisierungsstatus, und beheben Sie das Problem für das Datenbankreplikat.  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
 [Übersicht über Always On-Verfügbarkeitsgruppen &#40;SQL Server&#41;](~/database-engine/availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md)   
 [Verwenden des AlwaysOn-Dashboards &#40;SQL Server Management Studio&#41;](~/database-engine/availability-groups/windows/use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  


