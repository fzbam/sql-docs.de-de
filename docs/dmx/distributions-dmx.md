---
title: Verteilungen (DMX) | Microsoft Docs
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- DMX
helpviewer_keywords:
- column distributions [DMX]
- distributions [DMX]
- DMX [Analysis Services], distributions
- Data Mining Extensions [Analysis Services], distributions
ms.assetid: cfbb9f38-ae71-401e-867f-15c6a2b6fb97
caps.latest.revision: 32
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 85d01b1e2637b938d093fce3b4cfcc5c1f99abda
ms.contentlocale: de-de
ms.lasthandoff: 08/02/2017

---
# <a name="distributions-dmx"></a>Verteilungen (DMX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  In [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], definieren Sie den Inhalt der Spalten, in einer Miningstruktur, um zu beeinflussen, wie Algorithmen die Daten in diesen Spalten verarbeiten, wenn Sie Miningmodelle erstellen. Für einige Algorithmen ist es hilfreich, vor dem Verarbeiten des Modells für jede kontinuierliche Spalte die Verteilung zu definieren, wenn für die Spalten bekannt ist, dass sie normal verteilte Werte enthalten. Wenn Sie die Verteilungen nicht definieren, liefern die sich ergebenden Miningmodelle möglicherweise ungenauere Vorhersagen, da die Algorithmen weniger Informationen zum Interpretieren der Daten haben.  
  
 [!INCLUDE[msCoName](../includes/msconame-md.md)] Data Mining-Algorithmen unterstützen die folgenden Verteilungstypen:  
  
 **– NORMAL**  
 Die Werte für die kontinuierliche Spalte bilden ein Histogramm, das einer gaußschen Normalverteilung folgt.  
  
 **Log Normal**  
 Die Werte für die kontinuierliche Spalte bilden ein Histogramm, bei dem der Logarithmus der Werte normal verteilt ist.  
  
 **EINHEITLICHE**  
 Die Werte für die kontinuierliche Spalte bilden eine flache Kurve, in der alle Werte gleich wahrscheinlich sind.  
  
 Weitere Informationen zu [!INCLUDE[msCoName](../includes/msconame-md.md)] Datamining-Algorithmen finden Sie unter [Data Mining-Algorithmen &#40; Analysis Services – Datamining &#41; ](../analysis-services/data-mining/data-mining-algorithms-analysis-services-data-mining.md). Algorithmenanbieter von Drittanbietern unterstützen möglicherweise weitere Verteilungstypen. Um zu bestimmen, welche Verteilungstypen ein Algorithmus unterstützt, verwenden Sie die **supported_modeling_flags** -Schemarowsets.  
  
 Weitere Informationen zu Verteilungstypen finden Sie unter [Spaltenverteilungen &#40; Data Mining &#41;](../analysis-services/data-mining/column-distributions-data-mining.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Content-Arten &#40; Datamining &#41;](../analysis-services/data-mining/content-types-data-mining.md)   
 [Datamining-Erweiterungen &#40; DMX &#41; Referenz](../dmx/data-mining-extensions-dmx-reference.md)   
 [Datamining-Erweiterungen &#40; DMX &#41; Syntaxelemente](../dmx/data-mining-extensions-dmx-syntax-elements.md)   
 [Datamining-Erweiterungen &#40; DMX &#41; Funktionsreferenz](../dmx/data-mining-extensions-dmx-function-reference.md)   
 [Datamining-Erweiterungen &#40; DMX &#41; Operator (Referenz)](../dmx/data-mining-extensions-dmx-operator-reference.md)   
 [Datamining-Erweiterungen &#40; DMX &#41; -Anweisungsreferenz](../dmx/data-mining-extensions-dmx-statements.md)   
 [Datamining-Erweiterungen &#40; DMX &#41; Syntaxkonventionen](../dmx/data-mining-extensions-dmx-syntax-conventions.md)   
 [Allgemeine Vorhersagefunktionen &#40; DMX &#41;](../dmx/general-prediction-functions-dmx.md)   
 [Struktur und die Verwendung von DMX-Vorhersageabfragen](../dmx/structure-and-usage-of-dmx-prediction-queries.md)   
 [Grundlegendes zur Select-Anweisung von DMX](../dmx/understanding-the-dmx-select-statement.md)  
  
  
