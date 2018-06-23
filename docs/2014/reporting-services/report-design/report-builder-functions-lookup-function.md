---
title: Lookup-Funktion (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e60e5bab-b286-4897-9685-9ff12703517d
caps.latest.revision: 7
author: douglaslM
ms.author: douglasl
manager: mblythe
ms.openlocfilehash: 8e2617d9704db585e4f8ac3558941a957876fc05
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36056163"
---
# <a name="lookup-function-report-builder-and-ssrs"></a>Lookup-Funktion (Berichts-Generator und SSRS)
  Gibt den ersten übereinstimmenden Wert für den angegebenen Namen aus einem Dataset mit Name-Wert-Paaren zurück.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a>Syntax  
  
```  
  
Lookup(source_expression, destination_expression, result_expression, dataset)  
```  
  
#### <a name="parameters"></a>Parameter  
 *source_expression*  
 (`Variant`) Ein Ausdruck, der im aktuellen Bereich ausgewertet wird und der den zu suchenden Namen oder Schlüssel angibt. Beispiel: `=Fields!ProdID.Value`.  
  
 *destination_expression*  
 (`Variant`) Ein Ausdruck, der für jede Zeile in einem Dataset ausgewertet wird und der den Namen oder den Schlüssel für die Übereinstimmung angibt. Beispiel: `=Fields!ProductID.Value`.  
  
 *result_expression*  
 (`Variant`) Ein Ausdruck, der für die Zeile im Dataset ausgewertet wird, in denen *Source_expression* = *destination_expression gilt*, und die abzurufenden Wert angibt. Beispiel: `=Fields!ProductName.Value`.  
  
 *Dataset (dataset)*  
 Eine Konstante, die den Namen eines Datasets im Bericht angibt. Beispiel: "Products".  
  
## <a name="return"></a>Rückgabewert  
 Gibt eine `Variant`, oder `Nothing` , wenn keine Übereinstimmung vorhanden ist.  
  
## <a name="remarks"></a>Hinweise  
 Verwendung `Lookup` zum Abrufen des Werts aus dem angegebenen Dataset für ein Name/Wert-Paar eine 1: 1-Beziehung vorhanden ist. Beispiel: Für ein ID-Feld in einer Tabelle können Sie das entsprechende Namensfeld mithilfe von `Lookup` aus einem Dataset abrufen, das nicht an den Datenbereich gebunden wird.  
  
 `Lookup` führt Folgendes aus:  
  
-   Der Quellausdruck wird im aktuellen Bereich ausgewertet.  
  
-   Der Zielausdruck wird für jede Zeile des angegebenen Datasets ausgewertet, nachdem Filter angewendet wurden, und zwar anhand der Sortierung des angegebenen Datasets.  
  
-   Bei der ersten Übereinstimmung von Quellausdruck und Zielausdruck wird der Ergebnisausdruck für diese Zeile im Dataset ausgewertet.  
  
-   Der Ergebnisausdruckswert wird zurückgegeben.  
  
 Verwenden Sie [LookupSet-Funktion (Berichts-Generator und SSRS)](report-builder-functions-lookupset-function.md), um mehrere Werte für einen einzelnen Namen oder ein Schlüsselfeld abzurufen, für das eine 1:n-Beziehung vorhanden ist. Aufzurufende `Lookup` für eine Wertemenge verwenden [Multilookup-Funktion &#40;Berichts-Generator und SSRS&#41;](report-builder-functions-lookup-function.md).  
  
 Es gelten folgende Einschränkungen:  
  
-   `Lookup` wird ausgewertet, nachdem alle Filterausdrücke angewendet wurden.  
  
-   Nur eine Suchebene wird unterstützt. Ein Quell-, Ziel- oder Ergebnisausdruck kann keinen Verweis auf eine Suchfunktion einschließen.  
  
-   Quell- und Zielausdrücke müssen den gleichen Datentyp ergeben. Der Rückgabetyp ist der gleiche wie der Datentyp des ausgewerteten Ergebnisausdrucks.  
  
-   Quell-, Ziel- und Ergebnisausdrücke können keine Verweise auf Berichts- oder Gruppenvariablen einschließen.  
  
-   `Lookup` kann nicht als Ausdruck für die folgenden Berichtselemente verwendet werden:  
  
    -   Dynamische Verbindungszeichenfolgen für eine Datenquelle.  
  
    -   Berechnete Felder in einem Dataset.  
  
    -   Abfrageparameter in einem Dataset.  
  
    -   Filter in einem Dataset.  
  
    -   Berichtsparameter.  
  
    -   Die Eigenschaft „Report.Language“.  
  
 Weitere Informationen finden Sie in der [Aggregatfunktionsreferenz (Berichts-Generator und SSRS)](report-builder-functions-aggregate-functions-reference.md) und unter [Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Auflistungen (Berichts-Generator und SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).  
  
## <a name="example"></a>Beispiel  
 Nehmen Sie im folgenden Beispiel an, dass eine Tabelle an ein Dataset gebunden wird, das ein Feld für den Produktbezeichner "ProductID" enthält. Ein separates Dataset mit dem Namen "Product" enthält den entsprechenden Produktbezeichner "ID" und den Produktnamen "Name".  
  
 Im folgenden Ausdruck vergleicht `Lookup` in jeder Zeile des Datasets "Product" den Wert von "ProductID" mit "ID". Wenn eine Übereinstimmung gefunden wird, wird der Wert des Felds "Name" für diese Zeile zurückgegeben.  
  
```  
=Lookup(Fields!ProductID.Value, Fields!ID.Value, Fields!Name.Value, "Product")  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdruck verwendet wird, in Berichten &#40;Berichts-Generator und SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md)   
 [Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expression-examples-report-builder-and-ssrs.md)   
 [Datentypen in Ausdrücken (Berichts-Generator und SSRS)](expressions-report-builder-and-ssrs.md)   
 [Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Auflistungen &#40;Berichts-Generator und SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  