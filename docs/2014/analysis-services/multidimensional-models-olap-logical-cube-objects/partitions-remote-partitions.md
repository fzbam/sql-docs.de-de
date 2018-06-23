---
title: Remotepartitionen | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- storage [Analysis Services], partitions
- archiving remote partitions [Analysis Services]
- partitions [Analysis Services], remote
- restoring remote partitions [Analysis Services]
- backing up remote partitions [Analysis Services]
- partitions [Analysis Services], storage
- storing data [Analysis Services], partitions
- MasterDataSourceID property
- remote partitions [Analysis Services]
ms.assetid: 63f5d9f5-c6b6-4ceb-94fe-7b6c396d10bb
caps.latest.revision: 33
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: 31629125aacd20b4d8d5ea69b68372abf4f5599b
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36057900"
---
# <a name="remote-partitions"></a>Remotepartitionen
  Die Daten einer Remotepartition auf einer anderen Instanz von Microsoft gespeichert [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] als die Instanz, die die Definitionen (Metadaten) der Partition und deren übergeordneter Cube enthält. Eine Remotepartition wird auf derselben Instanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] verwaltet, auf der die Partition und der übergeordnete Cube definiert sind.  
  
> [!NOTE]  
>  Der Computer muss zum Speichern einer Remotepartition auf eine Instanz von verfügen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] installiert und die gleichen Service Pack-Ebene ausgeführt werden, wie die Instanz, in dem die Partition definiert wurde. Remotepartitionen auf Instanzen einer früheren Version von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] werden nicht unterstützt.  
  
 Wenn Remotepartitionen in einer Measuregruppe enthalten sind, wird die Arbeitsspeicher- und CPU-Nutzung des Cubes auf alle Partitionen in der Measuregruppe verteilt. Wenn beispielsweise eine Remotepartition verarbeitet wird (entweder allein oder als Teil der Verarbeitung des übergeordneten Cubes), erfolgt ein großer Teil der Arbeitsspeicher- und CPU-Nutzung für diese Partition auf der Remoteinstanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].  
  
> [!NOTE]  
>  Ein Cube, der Remotepartitionen enthält, kann Dimensionen mit aktiviertem Schreibzugriff enthalten. Dies kann sich jedoch auf die Leistung für diesen Cube auswirken. Weitere Informationen zu Dimensionen mit aktiviertem Schreibzugriff finden Sie unter [Dimensionen mit aktiviertem Schreibzugriff](../multidimensional-models-olap-logical-dimension-objects/write-enabled-dimensions.md).  
  
## <a name="storage-modes-for-remote-partitions"></a>Speichermodi für Remotepartitionen  
 Remotepartitionen können alle Speichertypen verwenden, die von lokalen Partitionen verwendet werden: mehrdimensionale OLAP (MOLAP), hybride OLAP (HOLAP) oder relationale OLAP (ROLAP). Remotepartitionen können zudem die proaktive Zwischenspeicherung verwenden. Die folgenden Daten werden in Abhängigkeit vom Speichermodus einer Remotepartition auf der Remoteinstanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] gespeichert.  
  
|||  
|-|-|  
|Speichertyp|data|  
|MOLAP|Die Aggregationen einer Partition sowie eine Kopie der Quelldaten der Partition|  
|HOLAP|Die Aggregationen von Partitionen|  
|ROLAP|Keine Partitionsdaten|  
  
 Wenn eine Measuregruppe mehrere MOLAP- oder HOLAP-Partitionen enthält, die auf mehreren Instanzen von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] gespeichert sind, verteilt der Cube die Daten in den Measuregruppendaten auf diese Instanzen von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].  
  
## <a name="merging-remote-partitions"></a>Zusammenführen von Remotepartitionen  
 Remotepartitionen können nur mit anderen Remotepartitionen zusammengeführt werden, die auf der gleichen Remoteinstanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] gespeichert sind. Weitere Informationen zum Zusammenführen von Partitionen finden Sie unter [Zusammenführen von Partitionen in Analysis Services &#40;SSAS – mehrdimensional&#41;](../multidimensional-models/merge-partitions-in-analysis-services-ssas-multidimensional.md).  
  
## <a name="archiving-and-restoring-remote-partitions"></a>Archivieren und Wiederherstellen von Remotepartitionen  
 Daten in Remotepartitionen können archiviert oder wiederhergestellt werden, wenn die Datenbank, in der die Remotepartition gespeichert ist, archiviert oder wiederhergestellt wird. Wenn Sie eine Datenbank ohne Wiederherstellung einer Remotepartition wiederherstellen, müssen Sie die Remotepartition verarbeiten, bevor Sie die Daten in der Partition verwenden können. Weitere Informationen zum Archivieren und Wiederherstellen von Datenbanken finden Sie unter [sichern und Wiederherstellen von Analysis Services-Datenbanken](../multidimensional-models/backup-and-restore-of-analysis-services-databases.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen und Verwalten einer Remotepartition &#40;Analysis Services&#41;](../multidimensional-models/create-and-manage-a-remote-partition-analysis-services.md)   
 [Verarbeiten von Analysis Services-Objekte](../multidimensional-models/processing-analysis-services-objects.md)  
  
  