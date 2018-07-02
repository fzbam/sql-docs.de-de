---
title: Sequence Clustering-Cluster-Registerkarte "Clusterdiagramm" (Miningmodell-Viewer | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql12.dm.miningmodeleditor.sequenceclustering.diagrams.f1
ms.assetid: 4b705397-9af4-4678-9eda-149bc5d762fa
caps.latest.revision: 26
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: 56c384e39ae4ef364f608cef8fa507d20bb746ef
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36048138"
---
# <a name="sequence-clustering-cluster-diagram-tab-mining-model-viewer"></a>Registerkarte "Sequenzcluster/Clusterdiagramm" (Miningmodell-Viewer)
  Die Registerkarte **Clusterdiagramm** im **Microsoft Sequence Clustering-Viewer** stellt eine grafische Ansicht aller im Sequenzclustermodell enthaltenen Cluster bereit.  
  
 Mit dieser Sicht eines Sequenzclustermodells können Sie einen Drillthrough von jedem Cluster zu den unterstützenden Fällen ausführen, wenn Drillthrough aktiviert wurde. Sie können den Clustern auch aussagekräftige Namen zuweisen und die Schattierungsvariable ändern, um die Verteilung der Werte auf einen Blick bewerten zu können.  
  
 **Weitere Informationen:** [Microsoft Sequence Clustering-Algorithmus](data-mining/microsoft-sequence-clustering-algorithm.md), [Durchsuchen eines Modells mit dem Microsoft Sequenzcluster-Viewer](data-mining/browse-a-model-using-the-microsoft-sequence-cluster-viewer.md)  
  
## <a name="options"></a>Tastatur  
 **Viewerinhalt**  
 Lädt das Miningmodell im Viewer neu.  
  
 **Miningmodell**  
 Wählen Sie ein anzuzeigendes, in der aktuellen Miningstruktur enthaltenes Miningmodell aus. Das Miningmodell wird im dazugehörigen Viewer geöffnet.  
  
 **Ereignisanzeige**  
 Wählen Sie den Viewer aus, der zum Durchsuchen des ausgewählten Miningmodells verwendet werden soll. Sie können den benutzerdefinierten Viewer oder den **Microsoft Generic Content Tree Viewer**verwenden. Sie können auch Plug-In-Viewer verwenden, falls diese verfügbar sind.  
  
 **Vergrößern**  
 Vergrößert das Diagramm, um eine detailliertere Darstellung der Cluster zu erhalten.  
  
 **Verkleinern**  
 Verkleinert das Diagramm, um alle Cluster im Modell anzuzeigen.  
  
 **Diagrammsicht kopieren**  
 Kopiert den sichtbaren Abschnitt des Diagramms in die Zwischenablage.  
  
 **Gesamtes Diagramm kopieren**  
 Kopiert das gesamte Diagramm in die Zwischenablage.  
  
 **Diagramm an Fenstergröße anpassen**  
 Verkleinert das Diagramm so weit, dass das gesamte Diagramm auf den Bildschirm passt.  
  
 **Knoten suchen**  
 Mit dem Dialogfeld **Knoten suchen** können Sie die Cluster im Diagramm filtern und so leichter einen bestimmten Cluster finden. Weitere Informationen finden Sie unter [Dialogfeld "Knoten suchen" &#40;Miningmodell-Viewer&#41;](find-node-dialog-box-mining-model-viewer.md).  
  
 Beachten Sie, dass Sie in diesem Kontext nur den Namen des Clusters suchen, nicht die Attribute innerhalb des Clusters. Daher ist diese Option besonders hilfreich, wenn Sie dem Cluster aussagekräftige Namen zugewiesen haben. Sie können Clustern im Viewer Namen zuweisen, indem Sie mit der rechten Maustaste auf einen Cluster klicken und anschließend **Umbenennen**auswählen.  
  
 **Layout verbessern**  
 Ordnet die im Diagramm enthaltenen Cluster neu an, um das Layout zu verbessern.  
  
 **Density**  
 Die Darstellung des Dichtebalkendiagramms und die Werte darin sind abhängig von dem Attribut, das Sie unter **Schattierungsvariable**auswählen.  
  
-   Wenn kein Attributstatus als Schattierungsvariable ausgewählt wurde, stellt standardmäßig die für jeden Cluster angewendete Dichteschattierung die Unterstützung für den Cluster dar, verglichen mit der Gesamtmenge der Fälle.  
  
-   Wenn Sie ein Attribut für **Schattierungsvariable**auswählen, müssen Sie anschließend auch einen Wert für **Status** auswählen. Hierdurch wird das Dichtebalkendiagramm aktualisiert und zeigt die Wahrscheinlichkeit für diesen Status an. Sie können die Maus über jedem einzelnen Cluster anhalten, um die Wahrscheinlichkeit des ausgewählten Status für den Cluster anzuzeigen.  
  
 **Schattierungsvariable**  
 Wählen Sie ein Attribut aus dem Miningmodell aus, das beim Schattieren des Clusterdiagramms verwendet werden soll.  
  
 **Status**  
 Wählen Sie einen Status aus, der dem Wert für **Schattierungsvariable**entspricht. Wenn Sie z.B. die Sequenzen anzeigen möchten, die ein bestimmtes Produkt enthalten, wählen Sie die Spalte [Product] als Attribut für **Schattierungsvariable**und den bestimmten Produktnamen als Wert für **Status** aus.  
  
 **Links**  
 Die Linien im Diagramm geben Zuordnungen zwischen Sequenzclustern an. Sie können die Anzahl der im Viewer angezeigten Links anpassen, indem Sie den Schieberegler rechts neben den Clustern schieben. Wenn Sie den Schieberegler nach unten ziehen, werden nur die stärksten Links angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [Datamining-Algorithmen &#40;Analysis Services – Datamining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md)   
 [Miningmodell-Viewer &#40;Datamining-Modell-Designer&#41;](mining-model-viewers-data-mining-model-designer.md)   
 [Data Mining-Modell-Viewer](data-mining/data-mining-model-viewers.md)  
  
  