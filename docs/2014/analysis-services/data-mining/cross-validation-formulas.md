---
title: Kreuzvalidierungsformeln | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd1ea582-29a1-4154-8de2-47bab3539b4d
caps.latest.revision: 8
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: 97500036ed4021c0b1c6d907db1c4aa7858c8b68
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36148291"
---
# <a name="cross-validation-formulas"></a>Kreuzvalidierungsformeln
  Wenn Sie einen Kreuzvalidierungsbericht generieren, enthält dieser in Abhängigkeit des Miningmodelltyps (d.h. der zum Erstellen des Modells verwendet Algorithmus) Genauigkeitsmeasures für jedes Modell, den Datentyp des vorhersagbaren Attributs und ggf. den vorhersagbaren Attributwert.  
  
 In diesem Abschnitt werden die im Kreuzvalidierungsbericht verwendeten Measures aufgeführt und die Berechnungsmethode beschrieben.  
  
 Eine Aufschlüsselung der Genauigkeitsmeasures nach Modelltyp finden Sie unter [Measures im Kreuzvalidierungsbericht](measures-in-the-cross-validation-report.md).  
  
## <a name="formulas-used-for-cross-validation-measures"></a>Für Kreuzvalidierungsmeasures verwendete Formeln  
  
> [!NOTE]  
>  **Wichtig:** Diese Genauigkeitsmeasures werden für jedes Zielattribut berechnet. Sie können für jedes Attribut einen Zielwert bestimmen oder weglassen. Wenn ein Fall in einem Dataset über keinen Wert für das Zielattribut verfügt, wird der Fall so behandelt, als hätte er einen Spezialwert, der als *fehlender Wert*bezeichnet wird. Zeilen, die fehlende Werte aufweisen, werden beim Berechnen des Genauigkeitsmeasures für ein bestimmtes Zielattribut nicht gezählt. Da die Ergebnisse für jedes Attribut einzeln berechnet werden, wird das Ergebnis für das Zielattribut nicht beeinflusst, wenn Werte für das Zielattribut, jedoch nicht für andere Attribute vorhanden sind.  
  
|Measure|Gilt für|Implementierung|  
|-------------|----------------|--------------------|  
|**Richtig positiv**|Diskretes Attribut, Wert wird angegeben|Anzahl der Fälle, die diese Bedingungen erfüllen:<br /><br /> Fall enthält den Zielwert.<br /><br /> Modell hat vorhergesagt, dass der Fall den Zielwert enthält.|  
|**Wahr negativ**|Diskretes Attribut, Wert wird angegeben|Anzahl der Fälle, die diese Bedingungen erfüllen:<br /><br /> Fall enthält den Zielwert nicht.<br /><br /> Modell hat vorhergesagt, dass der Fall den Zielwert nicht enthält.|  
|**Falsch positiv**|Diskretes Attribut, Wert wird angegeben|Anzahl der Fälle, die diese Bedingungen erfüllen:<br /><br /> Tatsächlicher Wert ist gleich dem Zielwert.<br /><br /> Modell hat vorhergesagt, dass der Fall den Zielwert enthält.|  
|**Falsch negativ**|Diskretes Attribut, Wert wird angegeben|Anzahl der Fälle, die diese Bedingungen erfüllen:<br /><br /> Tatsächlicher Wert ist ungleich dem Zielwert.<br /><br /> Modell hat vorhergesagt, dass der Fall den Zielwert nicht enthält.|  
|**Erfolgreich/Fehler**|Diskretes Attribut, kein festgelegtes Ziel|Anzahl der Fälle, die diese Bedingungen erfüllen:<br /><br /> Erfolgreich, wenn der vorhergesagte Status mit der höchsten Wahrscheinlichkeit gleich dem Eingabestatus ist und die Wahrscheinlichkeit größer als der Wert von **Statusschwellenwert**ist.<br /><br /> Andernfalls fehlgeschlagen.|  
|**Lift**|Diskretes Attribut. Zielwert kann angegeben werden, ist aber nicht erforderlich.|Die mittlere logarithmische Wahrscheinlichkeit für alle Zeilen mit Werten für das Zielattribut, wobei die logarithmische Wahrscheinlichkeit pro Fall als Log(ActualProbability/MarginalProbability) berechnet wird. Um den Mittelwert zu berechnen, wird die Summe der Protokollierungswahrscheinlichkeitswerte durch die Anzahl der Zeilen im Eingabedataset dividiert, wobei Zeilen mit fehlenden Werten für das Zielattribut ausgeschlossen werden.<br /><br /> Als Prognosegüte kann ein negativer oder ein positiver Wert angegeben werden. Ein positiver Wert steht für ein effektives Modell, das die Zufallsvorhersage übertrifft.|  
|**Logarithmisches Ergebnis**|Diskretes Attribut. Zielwert kann angegeben werden, ist aber nicht erforderlich.|Logarithmus der tatsächlichen Wahrscheinlichkeit für jeden Fall, summiert und dann dividiert durch die Anzahl von Zeilen im Eingabedataset, ohne die Zeilen mit fehlenden Werten für das Zielattribut.<br /><br /> Da die Wahrscheinlichkeit als Dezimalbruch dargestellt wird, sind logarithmische Ergebnisse immer negative Zahlen. Je näher das Ergebnis an 0 liegt, desto besser ist es.|  
|**Fallwahrscheinlichkeit**|Cluster|Summe der Clusterwahrscheinlichkeitsergebnisse für alle Fälle, dividiert durch die Anzahl der Fälle in der Partition, ohne die Zeilen mit fehlenden Werten für das Zielattribut.|  
|**Mittlerer absoluter Fehler**|Kontinuierliches Attribut|Summe der absoluten Fehler für alle Fälle in der Partition, dividiert durch die Anzahl der Fälle in der Partition.|  
|**Wurzel des mittleren quadratischen Fehlers**|Kontinuierliches Attribut|Quadratwurzel des mittleren Fehlers für die Partition zum Quadrat.|  
|**Wurzel des mittleren Fehlers zum Quadrat**|Diskretes Attribut. Zielwert kann angegeben werden, ist aber nicht erforderlich.|Quadratwurzel des Mittelwerts der quadrierten Komplemente des Wahrscheinlichkeitsergebnisses, dividiert durch die Anzahl der Fälle in der Partition, ohne die Zeilen mit fehlenden Werten für das Zielattribut.|  
|**Wurzel des mittleren Fehlers zum Quadrat**|Diskretes Attribut, kein festgelegtes Ziel|Quadratwurzel des Mittelwerts der quadrierten Komplemente des Wahrscheinlichkeitsergebnisses, dividiert durch die Anzahl der Fälle in der Partition, ohne die Fälle mit fehlenden Werten für das Zielattribut.|  
  
## <a name="see-also"></a>Siehe auch  
 [Tests und Überprüfung &#40;Datamining&#41;](testing-and-validation-data-mining.md)   
 [Übergreifende Überprüfung &#40;Analysis Services – Datamining&#41;](cross-validation-analysis-services-data-mining.md)  
  
  