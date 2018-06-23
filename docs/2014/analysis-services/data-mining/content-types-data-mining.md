---
title: Inhaltstypen (Datamining) | Microsoft Docs
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
- columns [data mining], content types
- KEY SEQUENCE column
- content types [data mining]
- attributes [data mining]
- DISCRETIZED column
- CONTINUOUS column
- CYCLICAL column
- ORDERED column
- discretized columns [data mining]
- discrete columns [Analysis Services]
- DISCRETE column
- KEY column
- KEY TIME column
- continuous columns
- coding [Data Mining]
ms.assetid: 2dacd968-70e8-4993-88b6-a6d36024a4e4
caps.latest.revision: 42
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: 2f283ff19a1947cfda208979b80482432ec6c597
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36050684"
---
# <a name="content-types-data-mining"></a>Inhaltstypen (Data Mining)
  In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]können Sie den physischen Datentyp für eine Spalte in einer Miningstruktur sowie einen logischen Inhaltstyp für die Spalte bei Verwendung in einem Modell definieren.  
  
 Der *Datentyp* bestimmt, wie Algorithmen die Daten beim Erstellen von Miningmodellen in diesen Spalten verarbeiten. Durch Definieren des Datentyps einer Spalte erhält der Algorithmus Informationen über die Art und Verarbeitung der Daten in den Spalten. Jeder Datentyp in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] unterstützt einen oder mehrere Inhaltstypen für Data Mining.  
  
 Der *Inhaltstyp* beschreibt das Verhalten der Inhalte in den Spalten. Wenn z. B. der Inhalt in einem bestimmten Intervall wie an den Tagen einer Woche wiederholt wird, können Sie den Inhaltstyp dieser Spalte als zyklisch bezeichnen.  
  
 Einige Algorithmen setzen bestimmte Daten- und Inhaltstypen voraus, um ordnungsgemäß zu funktionieren. Beispielsweise kann der Microsoft Naive Bayes-Algorithmus kontinuierliche Spalten nicht als Eingabe verwenden und keine kontinuierlichen Werte vorhersagen. Einige Inhaltstypen, z. B. Key Sequence, werden nur von einem bestimmten Algorithmus verwendet. Eine Liste der Algorithmen und Inhaltstypen, die unterstützt werden, finden Sie unter [Data Mining-Algorithmen &#40;Analysis Services – Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).  
  
 In der folgenden Liste werden die Inhaltstypen beschrieben, die Sie beim Data Mining verwenden. Außerdem erfahren Sie hier, von welchen Datentypen die einzelnen Inhaltstypen unterstützt werden.  
  
## <a name="discrete"></a>Discrete  
 *Discrete* (Diskret) bedeutet, dass die Spalte eine endliche Anzahl von Werten enthält, wobei sich die Werte nicht durch eine kontinuierliche Größe unterscheiden. Eine Spalte mit der Angabe des Geschlechts ist ein Beispiel für eine typische diskrete Attributspalte, da die Daten eine bestimmte Anzahl von Kategorien darstellen.  
  
 Selbst wenn die Werte einer diskreten Attributspalte numerisch sind, können sie keine Reihenfolge beinhalten. Auch wenn für die diskrete Spalte numerische Werte verwendet werden, können keine Bruchzahlen berechnet werden. Ortskennzahlen sind ein anschauliches Beispiel für numerische diskrete Daten.  
  
 Die `Discrete` Inhaltstyp wird von allen Data mining-Datentypen unterstützt.  
  
## <a name="continuous"></a>Continuous  
 *Continuous* (Kontinuierlich) bedeutet, dass die Spalte Werte enthält, die numerische Daten auf einer Skala darstellen, die Zwischenwerte zulässt. Im Gegensatz zu diskreten Spalten, die endliche, zählbare Daten darstellen, stellt eine kontinuierliche Spalte skalierbare Messdaten dar. Diese Spalten können unendliche viele Bruchzahlen enthalten. Eine Temperaturspalte stellt ein Beispiel für eine kontinuierliche Attributspalte dar.  
  
 Wenn eine Spalte kontinuierliche numerische Daten enthält und Sie wissen, wie die Daten verteilt werden sollen, können Sie die Genauigkeit der Analyse möglicherweise erhöhen, indem Sie die erwartete Verteilung der Werte angeben. Die Spaltenverteilung wird auf Ebene der Miningstruktur festgelegt. Daher bezieht sich die Einstellung auf alle Modelle, die auf der Struktur basieren. Weitere Informationen finden Sie unter [Spaltenverteilungen &#40;Data Mining&#41;](column-distributions-data-mining.md).  
  
 Die `Continuous` Inhaltstyp wird von den folgenden Datentypen unterstützt: `Date`, `Double`, und `Long`.  
  
## <a name="discretized"></a>Discretized  
 Unter*Diskretisierung* wird der Prozess verstanden, Werte eines kontinuierlichen Satzes an Daten in Buckets zu platzieren, sodass sich eine begrenzte Anzahl an möglichen Werten ergibt. Nur numerische Daten können diskretisiert werden.  
  
 Der Inhaltstyp *Discretized* gibt an, dass die Spalte Werte enthält, die Gruppen bzw. Buckets von Werten darstellen, die von einer kontinuierlichen Spalte abgeleitet sind. Die Buckets werden als sortierte und diskrete Werte behandelt.  
  
 Sie können Daten manuell diskretisieren, um sicherzustellen, dass Sie die gewünschten Buckets erhalten. Alternativ können Sie auch die in SQL Server Analysis Services verfügbaren Diskretisierungsmethoden verwenden. Einige Algorithmen führen die Diskretisierung automatisch durch. Weitere Informationen finden Sie unter [Ändern der Diskretisierung von Spalten in Miningmodellen](change-the-discretization-of-a-column-in-a-mining-model.md).  
  
 Der Inhaltstyp `Discretized` wird von den folgenden Datentypen unterstützt: `Date`, `Double`, `Long` und `Text`.  
  
## <a name="key"></a>Key  
 Der Inhaltstyp *Key* (Schlüssel) bedeutet, dass die Spalte eine Zeile eindeutig identifiziert. In einer Falltabelle enthält die Schlüsselspalte in der Regel numerische Bezeichner oder Textbezeichner. Sie den Inhaltstyp festlegen, um `key` um anzugeben, dass die Spalte nicht zu Analysezwecken, sondern nur zum Verfolgen der Datensätze dienen soll.  
  
 Auch geschachtelte Tabellen verfügen über Schlüssel, die Schlüssel geschachtelter Tabellen werden jedoch etwas anders verwendet. Sie den Inhaltstyp festlegen, um `key` in einer geschachtelten Tabelle, wenn die Spalte das Attribut ist, die Sie analysieren möchten. Die Werte der Schlüsselspalte einer geschachtelten Tabelle müssen für die einzelnen Fälle eindeutig sein, in der Gesamtmenge der Fälle kann die Schlüsselspalte jedoch doppelte Werte enthalten.  
  
 Wenn Sie beispielsweise analysieren, welche Produkte von den Kunden gekauft werden, könnten Sie in der Falltabelle für die Spalte **CustomerID** den Inhaltstyp  festlegen, und in der geschachtelten Tabelle könnten Sie für die Spalte **PurchasedProducts** noch einmal den Inhaltstyp  festlegen.  
  
> [!NOTE]  
>  Geschachtelte Tabellen sind nur dann verfügbar, wenn Daten von externen Datenquellen verwendet werden, die in Analysis Services als Datenquellensicht definiert wurden.  
  
 Dieser Inhaltstyp wird von den folgenden Datentypen unterstützt: `Date`, `Double`, `Long`, und `Text`.  
  
## <a name="key-sequence"></a>Key Sequence  
 Der Inhaltstyp *Key Sequence* (Schlüsselsequenz) kann nur in Sequenzclustermodellen verwendet werden. Der Inhaltstyp `key sequence` zeigt an, dass die betreffende Spalte Werte enthält, die eine Folge von Ereignissen darstellen. Die Werte sind sortiert, aber die Abstände zwischen den Werte müssen nicht gleich groß sein.  
  
 Dieser Inhaltstyp wird von den folgenden Datentypen unterstützt: `Double`, `Long`, `Text`, und `Date`.  
  
## <a name="key-time"></a>Key Time  
 Der Inhaltstyp *Key Time* (Schlüsselzeit) kann nur in Zeitreihenmodellen verwendet werden. Der Inhaltstyp `key time` gibt an, dass die Werte sortiert sind und eine Zeitskala darstellen.  
  
 Dieser Inhaltstyp wird von den folgenden Datentypen unterstützt: `Double`, `Long` und `Date`.  
  
## <a name="table"></a>Tabelle  
 Der Inhaltstyp *Table* (Tabelle) gibt an, dass die Spalte eine weitere Datentabelle mit einer oder mehreren Spalten und einer oder mehreren Zeilen enthält. Für jede einzelne Zeile der Falltabelle gilt, dass diese Spalte mehrere Werte enthalten kann, die den übergeordneten Falldatensatz betreffen. Wenn die Hauptfalltabelle beispielsweise eine Kundenliste enthält, könnten mehrere Spalten geschachtelte Tabellen beinhalten. Beispielsweise könnte die Spalte **ProductsPurchased** eine geschachtelte Tabelle mit den Produkten enthalten, die von einem Kunden bislang gekauft wurden, und die Spalte **Hobbies** könnte die Interessensgebiete des Kunden auflisten.  
  
 Diese Spalte hat stets den Datentyp `Table`.  
  
## <a name="cyclical"></a>Cyclical  
 Der Spaltentyp *Cyclical* (Zyklisch) gibt an, dass die Spalte Werte enthält, die eine zyklisch geordnete Menge darstellen. Die nummerierten Tage der Woche stellen z. B. einen zyklische geordnete Menge dar, da Tag Nummer eins auf Tag Nummer sieben folgt.  
  
 Zyklische Spalten werden hinsichtlich des Inhaltstyps als sortierte und diskrete Spalten betrachtet.  
  
 Dieser Inhaltstyp wird von allen Data Mining-Datentypen in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]unterstützt. Die meisten Algorithmen behandeln zyklische Werte jedoch als diskrete Werte und führen keine spezielle Verarbeitung durch.  
  
## <a name="ordered"></a>Ordered  
 Der Inhaltstyp *Ordered* (Sortiert) gibt ebenfalls an, dass die betreffende Spalte Werte enthält, die eine Sequenz oder Reihenfolge definieren. Bei diesem Inhaltstyp implizieren die zum Sortieren verwendeten Werte jedoch keine Abstands- oder Größenbeziehung zwischen den Werten der Menge. Wenn eine sortierte Attributspalte z. B. Informationen zu Kenntnisstufen in der Reihenfolge von eins bis fünf enthält, hat der Abstand zwischen den Kenntnisstufen keine Aussage. Eine Kenntnisstufe von fünf ist nicht notwendigerweise fünf Mal besser, als eine Kenntnisstufe von eins.  
  
 Sortierte Attributspalten werden hinsichtlich des Inhaltstyps auch als diskrete Spalten betrachtet.  
  
 Dieser Inhaltstyp wird von allen Data Mining-Datentypen in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]unterstützt. Die meisten Algorithmen behandeln geordnete Werte jedoch als diskrete Werte und führen keine spezielle Verarbeitung durch.  
  
## <a name="classified"></a>Classified  
 Neben den oben aufgeführten Inhaltstypen, die für alle Modelle verwendet werden, können Sie klassifizierte Spalten verwenden, um Inhaltstypen für einige Datentypen zu definieren. Weitere Informationen zu klassifizierten Spalten finden Sie unter [Klassifizierte Spalten &#40;Data Mining&#41;](classified-columns-data-mining.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Inhaltstypen &#40;DMX&#41;](/sql/dmx/content-types-dmx)   
 [Datentypen &#40;Datamining&#41;](data-types-data-mining.md)   
 [Datentypen &#40;DMX&#41;](/sql/dmx/data-types-dmx)   
 [Ändern der Eigenschaften einer Miningstruktur](change-the-properties-of-a-mining-structure.md)   
 [Miningstrukturspalten](mining-structure-columns.md)  
  
  