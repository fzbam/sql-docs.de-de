---
title: Filtern (Dialogfeld) (Mininggenauigkeitsdiagramm) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71e884a9-7ec4-4459-a4c4-87f6c796d478
caps.latest.revision: 15
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: 328ebd3f09037c3288450b75b4acd011481c40a6
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36049590"
---
# <a name="filter-dialog-box-mining-accuracy-chart"></a>Filter (Dialogfeld, Mininggenauigkeitsdiagramm)
  Im Dialogfeld **Filter** können Sie die Bedingungen erstellen, die Sie auf ein Dataset anwenden können. Bei dem Dataset kann es sich um ein zum Testen verwendetes externes Dataset oder um die Falldaten zum Trainieren eines Miningmodells handeln. In diesem Dialogfeld können Sie die Kriterien erstellen, die als Teil von komplexeren Filterkriterien in einem der beiden Dialogfelder **Datasetfilter** oder **Modellfilter** gespeichert werden können.  
  
-   Das Dialogfeld **Datasetfilter** kann über die Registerkarte **Eingabeauswahl** von **Mininggenauigkeitsdiagramm** aufgerufen werden.  
  
-   Das Dialogfeld **Modellfilter** kann über die Registerkarte **Miningmodelle** des Data Mining-Designers aufgerufen werden.  
  
 Wenn Sie einen Filter auf ein Miningmodell anwenden, wählen Sie als erstes im Dialogfeld **Modellfilter** eine Tabelle aus. Dann können Sie im Dialogfeld **Filter** die Bedingungen erstellen, die nur auf diese Tabelle angewendet werden.  
  
 Wenn Sie einen Filter erstellen, der auf ein externes Dataset angewendet werden soll, wählen Sie im Dialogfeld **Datasetfilter** eine Tabelle aus der Liste mit den in einer Datenquellensicht vorhandenen Tabellen aus. Dann erstellen Sie im Dialogfeld **Filter** die Bedingungen, die nur auf diese Tabelle angewendet werden.  
  
 Nachdem Sie einen Satz von Bedingungen erstellt haben, die für eine einzelne Tabelle gelten, [!INCLUDE[clickOK](../includes/clickok-md.md)]. Die von Ihnen im Dialogfeld **Filter** vorgenommenen Änderungen werden automatisch zum Filterausdruck in einem der übergeordneten Dialogfelder **Datasetfilter** oder **Modellfilter**hinzugefügt.  
  
 Wenn Sie den Filter auf das neue Dataset anwenden, werden zum Auswerten des vorhandenen Data Mining-Modells nur die Fälle in den Daten verwendet, die die Bedingungen erfüllen. Wenn Sie den Filter jedoch auf das Miningmodell anwenden, wird die Genauigkeit des Modells nur für die Fälle im Miningmodell bewertet, die diese Bedingungen erfüllen.  
  
 **Weitere Informationen finden Sie unter:** [Tests und Überprüfung &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md)  
  
## <a name="options"></a>Tastatur  
 **Bedingungen**  
 Ein Raster mit Spalten, in denen die Bedingungen für die Spalten aus der Tabelle festgelegt werden, die im Dialogfeld **Datasetfilter** ausgewählt wurden.  
  
|value|Description|  
|-----------|-----------------|  
|**Und/Oder**|Klicken Sie auf diese Option, um anzugeben, ob der AND-Operator oder der OR-Operator auf die Bedingung in dieser Zeile angewendet werden soll. Diese Werte sind nur dann verfügbar, wenn Sie eine Spalte aus der Liste **Miningstrukturspalte** ausgewählt haben.|  
|**Miningstrukturspalte**|Klicken Sie auf diese Option, um eine Spalte aus der Liste mit den Spalten der Tabelle auszuwählen, die Sie aus den Datenquellen im Dialogfeld **Datasetfilter** ausgewählt haben.|  
|**Ist gleich**|Wählen Sie in der Liste einen Operator aus. Die verfügbaren Operatoren hängen vom Datentyp der Spalte ab.<br /><br /> Wenn die Spalte diskrete Werte enthält, sind nur folgende Operatoren verfügbar:<br /><br /> = (ist gleich), <> (ist nicht gleich), IS NOT NULL, IS NULL.<br /><br /> Wenn die Spalte kontinuierliche Werte enthält, werden auch Operatoren für größer als- und kleiner als-Vorgänge unterstützt.|  
|**ReplTest1**|Geben Sie einen Wert ein, der als Bedingung verwendet werden soll.|  
  
## <a name="see-also"></a>Siehe auch  
 [Tests und Überprüfung miningmodelltasks und &#40;Datamining&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md)   
 [Mining-Genauigkeitsdiagramm-Designer &#40;Datamining&#41;](mining-accuracy-chart-designer-data-mining.md)  
  
  