---
title: Herstellen einer Verbindung im Onlinemodus mit einer Analysis Services-Datenbank | Microsoft Docs
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
- Analysis Services, connecting
ms.assetid: 33041234-7106-404f-a289-8e904f32aff2
caps.latest.revision: 12
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: 4233f9d50cb64bb3827e4dec49251e382ca3c4b3
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36057294"
---
# <a name="connect-in-online-mode-to-an-analysis-services-database"></a>Herstellen in Onlinemodus einer Verbindung mit einer Analysis Services-Datenbank
  Sie können eine direkte Verbindung mit einer vorhandenen [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank herstellen und die Objekte in dieser Datenbank direkt ändern. Wenn Sie eine direkte Verbindung mit einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank herstellen, werden Änderungen an Objekten unmittelbar wirksam, und es wird kein [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Projekt innerhalb von [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]erstellt.  
  
### <a name="to-connect-directly-to-an-analysis-services-database-by-using-sql-server-data-tools"></a>So stellen Sie eine direkte Verbindung zu einer Analysis Services-Datenbank mit SQL Server-Datentools her  
  
1.  Öffnen Sie [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].  
  
2.  Zeigen Sie im Menü **Datei** auf **Öffnen** , und klicken Sie dann auf **Analysis Services-Datenbank**.  
  
3.  Wählen Sie **Verbindung mit vorhandener Datenbank herstellen**aus.  
  
4.  Geben Sie den Server- und den Datenbanknamen an.  
  
     Sie können den Datenbanknamen entweder eingeben oder den Server abfragen, um die vorhandenen Datenbanken auf dem Server anzuzeigen.  
  
5.  Klicken Sie auf **OK**.  
  
     Sie können nun alle Objekte innerhalb der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank direkt bearbeiten.  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit Analysis Services-Projekten und-Datenbanken während der Entwicklungsphase](work-with-analysis-services-projects-and-databases-in-development.md)   
 [Erstellen mehrdimensionaler Modelle mithilfe von SQL Server Datatools &#40;SSDT&#41;](creating-multidimensional-models-using-sql-server-data-tools-ssdt.md)  
  
  