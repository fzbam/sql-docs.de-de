---
title: Zuordnungs-Assistent (Datamining-Client für Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- nested tables, in association models
- association [data mining]
ms.assetid: 4db6462f-93c7-443f-8ff7-39474dc7029e
caps.latest.revision: 20
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: fbb7f91279b1f3e6ae642e3acbf2548b7205b563
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36061513"
---
# <a name="associate-wizard-data-mining-client-for-excel"></a>Zuordnungs-Assistent (Data Mining-Client für Excel)
  ![Zuordnungs-Assistenten im Data Mining-Menüband](media/dmc-associate.gif "Zuordnungs-Assistent in Data Mining-Menüband")  
  
 Der Zuordnungs-Assistent unterstützt Sie beim Erstellen eines Data Mining-Modells mithilfe des [!INCLUDE[msCoName](../includes/msconame-md.md)] Association Rules-Algorithmus. Solche Miningmodelle sind besonders nützlich zum Erstellen von *empfehlungssysteme*.  
  
 Dazu überprüft der [!INCLUDE[msCoName](../includes/msconame-md.md)] Association Rules-Algorithmus ein Dataset, das aus Transaktionen oder Ereignissen besteht, und sucht die Kombinationen, die häufig zusammen angezeigt werden. Es kann Tausende Kombinationen geben. Der Algorithmus kann jedoch angepasst werden, um mehr oder weniger Kombinationen zu suchen und nur die wahrscheinlichsten Kombinationen beizubehalten.  
  
 Sie können die Zuordnungsanalyse bei vielen Problemen anwenden. Diese Methode wird vor allem für die Warenkorbanalyse verwendet, mit deren Hilfe einzelne Produkte gefunden werden, die oft zusammen gekauft werden. Anhand dieser Informationen können Sie dann Produkte auf der Basis von Produkten empfehlen, die die Kunden bereits gekauft haben.  
  
## <a name="using-the-associate-wizard"></a>Verwenden den Zuordnungs-Assistenten  
  
1.  In der **Data Mining** des Menübands, klicken Sie auf **zuordnen**.  
  
2.  Auf der **Quelldaten auswählen** Seite Wählen Sie eine Excel-Tabelle oder den Datenbereich, und klicken Sie auf **Weiter**.  
  
     Die Beispieldatenarbeitsmappe enthält auf der Registerkarte Zuordnen ein Beispiel, wie Transaktionsdaten in der Regel angeordnet sind, wenn Sie beispielsweise in jeder Transaktion mehrere Produkte oder mehrere Einkaufsdatensätze pro Kunde analysieren möchten.  
  
     Wenn Sie externe Daten verwenden, um ein Zuordnungsmodell mit dem Zuordnungs-Assistenten erstellen möchten, Sie müssen die Daten in Excel hinzufügen zuerst und *vereinfachen* Daten. Weitere Informationen zur Vorbereitung der Daten für zuordnungsmodelle finden Sie unter [geschachtelte Tabellen &#40;Analysis Services – Data Mining&#41;](data-mining/nested-tables-analysis-services-data-mining.md), in der SQL Server-Onlinedokumentation.  
  
3.  Auf der **Zuordnung** Seite, wählen Sie die Spalte, die die Transaktion identifiziert.  
  
     Bei Warenkorbmodellen stellt dieser Bezeichner die Einheit dar, die modelliert werden soll. Möchten Sie Artikel analysieren, die einzelne Kunden in einem bestimmten Zeitraum gekauft haben, oder möchten Sie viele Transaktionen mit mehreren Kunden analysieren? Im ersten Fall würden Sie die Kunden-ID auswählen, im letzten Fall würden Sie die Bestellung oder eine andere Transaktions-ID auswählen.  
  
4.  Für **Element**, wählen Sie die Spalte, die die Artikel enthält, zwischen denen Sie Zuordnungen suchen müssen.  
  
     Bei einem Warenkorbmodell würden Sie zum Beispiel ein Produktfeld auswählen, um zu analysieren, welche Produkte oft zusammen gekauft werden. Wenn zu viele einzelne Produkte für eine effiziente Korrelation vorhanden sind, könnten Sie ein Feld mit der Produktkategorie oder Unterkategorie auswählen.  
  
5.  In **Schwellenwerte**, Sie können Werte, die steuern oder beeinflussen die Ausgabe des Modells festlegen:  
  
    -   **Minimale Unterstützung.** Gibt an, wie häufig eine Gruppe von Artikeln erscheinen muss, um als wichtig betrachtet zu werden. Der Algorithmus ignoriert alle Artikelkombinationen, die dieses Kriterium nicht erfüllen. Beispielsweise könnten Sie nur die Itemsets anzeigen, in denen die Artikel mindestens 10-mal zusammen erschienen sind.  
  
    -   **Minimale regelwahrscheinlichkeit**. Gibt den minimalen Wahrscheinlichkeitswert an, der erforderlich ist, damit eine Regel gespeichert wird. Das gesamte Dataset wird analysiert, um alle Kombinationen zu suchen. Anschließend wird die Wahrscheinlichkeit berechnet. Wird ein niedriger Schwellenwert festgelegt, werden vom Assistenten möglicherweise Elemente zugeordnet, die nur einen losen Zusammenhang aufweisen. Ist der festgelegte Schwellenwert zu hoch, werden bestimmte Zuordnungen möglicherweise ausgelassen, weil nicht genügend unterstützende Daten für sie vorhanden sind.  
  
     Im Allgemeinen haben Änderungen dieser Werte folgende Auswirkungen:  
  
    -   Je niedriger Sie den Wert für die Unterstützung ansetzen, desto mehr Kombinationen werden gefunden.  
  
    -   Wenn Sie die maximale Unterstützung verringern, filtern Sie Elemente heraus, die so oft auftreten, dass sie nur von geringer Bedeutung sind.  
  
    -   Wenn Sie die Wahrscheinlichkeit einer Regel verringern, verringern Sie die Anforderungen, die eine Kombination erreichen muss, um im Kontext des gesamten Datasets als signifikant angesehen zu werden.  
  
     **Tipp:** ist eine gute Idee, die mehrere Miningmodelle mit anderen Kombinationen von Unterstützung und Wahrscheinlichkeit erstellen. Um die Einstellungen zu verfolgen Sie für jedes Modell verwendet haben, können Sie die **Dokumentmodell** Assistenten im Data Mining-Client für Excel, und verwenden Sie die **Detailed** Berichtsoption. Weitere Informationen finden Sie unter [Miningmodelle dokumentieren &#40;Data Mining-Add-ins für Excel&#41;](documenting-mining-models-data-mining-add-ins-for-excel.md).  
  
6.  Klicken Sie optional auf **Parameter** die Algorithmusparameter ändern und das Verhalten des Miningmodells anzupassen.  
  
     Das Dialogfeld Algorithmusparameter enthält alle Parameter, die Sie im Assistenten festgelegt haben, und zusätzlich einige Parameter, die weniger häufig verwendet werden, z. B. MAXIMUM_SUPPORT. Weitere Informationen dazu, wie diese Parameter verwendet, finden Sie unter [Microsoft Association Algorithm Technical Reference](data-mining/microsoft-association-algorithm-technical-reference.md).  
  
7.  Auf der **Fertig stellen** Seite, und geben Sie einen eindeutigen Namen für das DataSet und das Modell.  
  
8.  In **Optionen**, Sie definieren, wie Sie mit dem Modell arbeiten, nach Abschluss möchten:  
  
    -   **Navigieren Sie**.  Wenn das Modell fertig ist, öffnet der Assistent ein Fenster, in dem die Regeln, die Itemsets sowie ein Abhängigkeitsnetzwerkdiagramm angezeigt werden, das die Zuordnungen darstellt.  
  
         Weitere Informationen zum Interpretieren der Daten im Zuordnungsmodell-Viewer finden Sie unter [Modells für Zuordnungsregeln Durchsuchen](browsing-an-association-rules-model.md).  
  
    -   **Aktivieren von Drillthrough**. Wählen Sie diese Option aus, um über das Modell Zugriff auf die zugrunde liegenden Daten zu erhalten.  
  
         Ein Drillthrough ist zum Beispiel nützlich, wenn Sie auf ein bestimmtes Itemset klicken und die Quelldaten anzeigen möchten.  
  
    -   **Temporäres Modell**. Wählen Sie diese Option aus, wenn das Modell nicht auf dem Server gespeichert werden soll. Temporäre Modelle werden beim Schließen von Excel gelöscht.  
  
9. Der Assistent analysiert alle möglichen Kombinationen und erstellt einen Bericht, der die Itemsets und Regeln enthält.  
  
## <a name="more-about-association-models"></a>Weitere Informationen zu Zuordnungsmodellen  
 Der [!INCLUDE[msCoName](../includes/msconame-md.md)] Association Rules-Algorithmus untersucht die Trainingsdaten auf Artikel, die in einer Transaktion zusammen angezeigt werden. Jede Gruppe von Artikeln bildet ein *Itemset*. Der Algorithmus zählt dann, wie häufig die einzelnen Itemsets auftreten, und berechnet die relative Bedeutung jedes Itemsets für alle Transaktionen.  
  
 Der Algorithmus verwendet diese Informationen zu Itemsets, um Regeln zu generieren, mit denen Zuordnungen vorhergesagt oder Empfehlungen abgegeben werden können. Eine Regel könnte beispielsweise wie folgt lauten: "Wenn der Benutzer ein Buch von Autor 1 und ein Buch von Autor 2 gekauft hat, wird er wahrscheinlich auch ein Buch von Autor 3 kaufen". Den Empfehlungen wird eine Wahrscheinlichkeit zugewiesen, die auf der Stärke der Zuordnungen basiert.  
  
### <a name="requirements"></a>Anforderungen  
 Zum Verwenden des Zuordnungs-Assistenten muss eine Verbindung mit einer [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Datenbank bestehen.  
  
 Die Quelldaten müssen in einer Transaktionstabelle organisiert sein. Die Quelldaten müssen eine Spalte enthalten, in der die Transaktions-ID angegeben ist. Mit dieser Spalte werden die einzelnen Artikelgruppen identifiziert. Die Transaktionsspalte muss in einer 1:n-Beziehung mit einer zweiten Spalte (der Artikel-ID) stehen, in der die Namen oder ID-Nummern der einzelnen Artikel der Gruppe gespeichert sind.  
  
 Dieses Konzept ist wahrscheinlich am einfachsten mithilfe des Warenkorbbeispiels zu verstehen. Wenn dem Warenkorb eine ID zugeordnet ist, dient die Warenkorb-ID als Bezeichner für die Transaktion. Jeder Artikel im Warenkorb (z. B. Kartoffeln oder Milch) stellt ein Element dieser Transaktion dar. Der Algorithmus für die Zuordnung kann Artikel über Transaktionen hinweg nachverfolgen, um beispielsweise zu bestimmen, wie oft Kartoffeln und Milch innerhalb einer Transaktion vorkommen.  
  
 Ihre Quelldaten müssen nach der Spalte mit der Transaktions-ID sortiert sein.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Datamining-Modells](creating-a-data-mining-model.md)   
 [Ein Modell für Zuordnungsregeln durchsuchen](browsing-an-association-rules-model.md)   
 [Warenkorbanalyse &#40;Tabelle AnalysisTools für Excel&#41;](shopping-basket-analysis-table-analysistools-for-excel.md)   
 [Exemplarische Vorgehensweise für das Abhängigkeit Netzwerk &#40;Data Mining-Add-ins&#41;](dependency-network-diagram-walkthrough-data-mining-add-ins.md)  
  
  