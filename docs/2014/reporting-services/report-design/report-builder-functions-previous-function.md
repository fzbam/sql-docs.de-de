---
title: Previous-Funktion (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 403a9384-6ca4-42e8-97ca-ac3f6fe4316b
caps.latest.revision: 8
author: douglaslM
ms.author: douglasl
manager: mblythe
ms.openlocfilehash: 65f8f0bdc7db2e58efd27522a93e4edf6c4e0bf3
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36150066"
---
# <a name="previous-function-report-builder-and-ssrs"></a>Previous-Funktion (Berichts-Generator und SSRS)
  Gibt den Wert oder den angegebenen Aggregatwert für die vorherige Instanz eines Elements innerhalb des angegebenen Bereichs zurück.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a>Syntax  
  
```  
  
Previous(expression, scope)  
```  
  
#### <a name="parameters"></a>Parameter  
 *expression*  
 (`Variant` oder `Binary`) der Ausdruck zu verwenden, um die Daten zu identifizieren und für das Abrufen des vorherigen Werts `Fields!Fieldname.Value` oder `Sum(Fields!Fieldname.Value)`.  
  
 *Bereich*  
 (`String`) Dies ist optional. Der Name der einer Gruppe oder eines Datenbereichs oder Null (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]), den Bereich aus der zum Abrufen des vorherigen Werts gemäß angibt, *Ausdruck*.  
  
## <a name="return-type"></a>Rückgabetyp  
 Gibt eine `Variant` oder `Binary`.  
  
## <a name="remarks"></a>Hinweise  
 Die `Previous`-Funktion gibt den vorherigen Wert für den Ausdruck zurück, der in dem angegebenen Bereich ausgewertet wird, nachdem die Sortierfunktionen und Filter angewendet wurden.  
  
 Wenn *Ausdruck* enthält keine Aggregatfunktion gehört, die `Previous` -Funktion standardmäßig auf den aktuellen Bereich für das Berichtselement.  
  
 Verwenden Sie in einer Detailgruppe `Previous` um den Wert eines Feldverweises in der vorherigen Instanz der Detailzeile anzugeben.  
  
> [!NOTE]  
>  Die `Previous` -Funktion werden nur Feldverweise in der Detailgruppe unterstützt. Beispielsweise werden in einem Textfeld in der Detailgruppe durch `=Previous(Fields!Quantity.Value)` die Daten für das Feld `Quantity` aus der vorherigen Zeile zurückgegeben. In der ersten Zeile gibt dieser Ausdruck NULL zurück (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).  
  
 Wenn *Ausdruck* enthält eine Aggregatfunktion, die einen Standardbereich verwendet `Previous` im aggregatfunktionsaufruf angegebenen Funktionsaufruf aggregiert die Daten innerhalb der vorherigen Instanz des Bereichs.  
  
 Wenn *Ausdruck* enthält eine Aggregatfunktion, die einen anderen Bereich als der Standardwert gibt an, die *Bereich* -Parameter für die `Previous` Funktion muss einen enthaltenden Bereich für den im angegebenen Bereich Aufrufen der Aggregatfunktion.  
  
 Die Funktionen `Level`, `InScope`, `Aggregate` und `Previous` kann nicht verwendet werden, der *Ausdruck*Parameter. Die Angabe des *recursive* -Parameters für eine Aggregatfunktion wird nicht unterstützt.  
  
 Weitere Informationen finden Sie in der [Aggregatfunktionsreferenz (Berichts-Generator und SSRS)](report-builder-functions-aggregate-functions-reference.md) und unter [Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Auflistungen (Berichts-Generator und SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).  
  
## <a name="examples"></a>Beispiele  
  
### <a name="description"></a>Description  
 Das folgende Codebeispiel stellt bei Angabe in der Standarddatenzeile eines Datenbereichs den Wert für das Feld `LineTotal` in der vorherigen Zeile bereit.  
  
### <a name="code"></a>Code  
  
```  
=Previous(Fields!LineTotal.Value)  
```  
  
### <a name="description"></a>Description  
 Das folgende Codebeispiel zeigt einen Ausdruck, der die Summe der Umsätze an einem bestimmten Tag des Monats und den vorherigen Wert für den Tag des Monats in einem vorhergehenden Jahr berechnet. Der Ausdruck wird einer Zelle in einer Zeile, die zur untergeordneten Gruppe `GroupbyDay`gehört, hinzugefügt. Die übergeordnete Gruppe ist `GroupbyMonth`, deren übergeordnete Gruppe wiederum `GroupbyYear`ist. Der Ausdruck zeigt die Ergebnisse für GroupbyDay (Standardbereich) und anschließend für `GroupbyYear` (der übergeordneten Gruppe der übergeordneten Gruppe `GroupbyMonth`) an.  
  
 Angenommen, in einem Datenbereich verfügt eine übergeordnete Gruppe namens `Year`über die untergeordnete Gruppe `Month`, der wiederum die Gruppe `Day` untergeordnet ist (drei geschachtelte Ebenen). Der Ausdruck `=Previous(Sum(Fields!Sales.Value,"Day"),"Year")` in einer mit der Gruppe `Day` verknüpften Zeile gibt den Umsatzwert für denselben Tag und Monat des vorherigen Jahrs zurück.  
  
### <a name="code"></a>Code  
  
```  
=Sum(Fields!Sales.Value) & " " & Previous(Sum(Fields!Sales.Value,"GroupbyDay"),"GroupbyYear")  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdruck verwendet wird, in Berichten &#40;Berichts-Generator und SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md)   
 [Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expression-examples-report-builder-and-ssrs.md)   
 [Datentypen in Ausdrücken (Berichts-Generator und SSRS)](expressions-report-builder-and-ssrs.md)   
 [Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Auflistungen &#40;Berichts-Generator und SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  