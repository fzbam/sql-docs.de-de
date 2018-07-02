---
title: Angeben des Inhalts einer Abfrageachse (MDX) | Microsoft Docs
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
- cellsets [MDX]
- query axis [MDX]
ms.assetid: c745ade0-738e-4a98-a3f0-3eabfd3eeba2
caps.latest.revision: 30
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: e540d77db8b6834df4a0cdc00a3b9aad54d9970e
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36160090"
---
# <a name="specifying-the-contents-of-a-query-axis-mdx"></a>Angeben des Inhalts einer Abfrageachse (MDX)
  Abfrageachsen geben die Kanten eines Cellsets an, die von einer SELECT-Anweisung von MDX (Multidimensional Expressions) zurückgegeben wird. Durch Angeben der Kanten eines Cellsets können Sie die zurückgegebenen Daten einschränken, die für den Client sichtbar sind.  
  
 Sie geben Abfrageachsen an, indem Sie einer Menge mithilfe eines `<SELECT query axis clause>` -Wertes eine bestimmte Abfrageachse zuweisen. Jeder `<SELECT query axis clause>` -Wert definiert eine Abfrageachse. Die Anzahl der Achsen im Dataset entspricht der Anzahl von `<SELECT query axis clause>` -Werten in der SELECT-Anweisung.  
  
## <a name="query-axis-syntax"></a>Abfrageachse (Syntax)  
 Nachstehend ist die Syntax von `<SELECT query axis clause>`definiert:  
  
```  
  
<SELECT query axis clause> ::=  
   [ NON EMPTY ] Set_Expression [ <SELECT dimension property list clause> ] [<HAVING clause>]  
   ON {  
      Integer_Expression |   
      AXIS( Integer_Expression ) |   
      {COLUMNS | ROWS | PAGES | SECTIONS | CHAPTERS}     
      }  
  
```  
  
 Jede Abfrageachse hat eine Nummer: 0 für die x-Achse, 1 für die y-Achse, 2 für die z-Achse usw. In der Syntax für `<SELECT query axis clause>`gibt der `Integer_Expression` -Wert die Achsennummer an. Eine MDX-Abfrage unterstützt maximal 128 angegebene Achsen, jedoch werden nur selten mehr als 5 Achsen verwendet. Anstelle der ersten 5 Achsen können die Aliase COLUMNS, ROWS, PAGES, SECTIONS und CHAPTERS verwendet werden.  
  
 In einer MDX-Abfrage können keine Abfrageachsen ausgelassen werden. In einer Abfrage, die mindestens eine Abfrageachse enthält, dürfen also keine Achsen mit niedrigeren Nummern oder dazwischen liegenden Achsen fehlen. Beispielsweise kann eine Abfrage keine ROWS-Achse ohne eine COLUMNS-Achse enthalten, und sie kann nicht die Achsen COLUMNS und PAGES ohne eine ROWS-Achse enthalten.  
  
 Sie können jedoch eine SELECT-Klausel ohne Achsen (d. h. eine leere SELECT-Klausel) angeben. In diesem Fall sind alle Dimensionen Slicerdimensionen, und die MDX-Abfrage wählt eine Zelle aus.  
  
 In der obigen Syntax für Abfrageachsen gibt jeder `Set_Expression` -Wert die Menge an, die den Inhalt der Abfrageachse definiert. Weitere Informationen zu Mengen finden Sie unter [Arbeiten mit Elementen, Tupeln und Mengen &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md).  
  
## <a name="examples"></a>Beispiele  
 Die folgende einfache SELECT-Anweisung gibt das Measure Internet Sales Amount auf der COLUMNS-Achse zurück und verwendet die MDX MEMBERS-Funktion, um alle Elemente aus der Calendar-Hierarchie der Date-Dimension auf der ROWS-Achse zurückzugeben:  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
{[Date].[Calendar].MEMBERS} ON ROWS  
FROM [Adventure Works]  
  
```  
  
 Die beiden folgenden Abfragen geben genau die gleichen Ergebnisse zurück. Dabei veranschaulichen sie die Verwendung von Achsennummern anstelle von Aliasen:  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON 0,  
{[Date].[Calendar].MEMBERS} ON 1  
FROM [Adventure Works]  
  
SELECT {[Measures].[Internet Sales Amount]} ON AXIS(0),  
{[Date].[Calendar].MEMBERS} ON AXIS(1)  
FROM [Adventure Works]  
  
```  
  
 Um alle leeren Tupel von einer Achse zu entfernen, können Sie das NON EMPTY-Schlüsselwort vor der Mengendefinition verwenden. In den vorherigen Beispielen sind im Cube ab August 2004 beispielsweise keine Daten vorhanden. Um alle Zeilen, die in keiner Spalte Daten enthalten, aus dem Cellset zu entfernen, fügen Sie einfach NON EMPTY vor der Menge für die ROWS-Achsendefinition ein, wie nachfolgend gezeigt:  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
NON EMPTY  
{[Date].[Calendar].MEMBERS} ON ROWS  
FROM [Adventure Works]  
  
```  
  
 NON EMPTY kann für alle Achsen in einer Abfrage verwendet werden. Vergleichen Sie die Ergebnisse der folgenden beiden Abfragen. In der ersten wird NON EMPTY nicht verwendet, und in der zweiten wird NON EMPTY für beide Achsen verwendet:  
  
```  
SELECT {[Measures].[Internet Sales Amount]}   
* [Promotion].[Promotion].[Promotion].MEMBERS  
ON COLUMNS,  
{[Date].[Calendar].[Calendar Year].MEMBERS} ON ROWS  
FROM [Adventure Works]  
WHERE([Product].[Subcategory].&[19])  
  
SELECT NON EMPTY {[Measures].[Internet Sales Amount]}   
* [Promotion].[Promotion].[Promotion].MEMBERS  
ON COLUMNS,  
NON EMPTY  
{[Date].[Calendar].[Calendar Year].MEMBERS} ON ROWS  
FROM [Adventure Works]  
WHERE([Product].[Subcategory].&[19])  
  
```  
  
 Die HAVING-Klausel kann verwendet werden, um die Inhalte einer Achse anhand bestimmter Kriterien zu filtern. Sie ist weniger flexibel als andere Methoden, die die gleichen Ergebnisse erzielen, wie z. B. die FILTER-Funktion, sie ist jedoch einfacher zu verwenden. Es folgt ein Beispiel, in dem nur die Daten zurückgegeben werden, bei denen Internet Sales Amount größer als 15.000 Dollar ist:  
  
```  
SELECT {[Measures].[Internet Sales Amount]}   
ON COLUMNS,  
NON EMPTY  
{[Date].[Calendar].[Date].MEMBERS}   
HAVING [Measures].[Internet Sales Amount]>15000  
ON ROWS  
FROM [Adventure Works]  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Angeben des Inhalts einer slicerachse &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md)  
  
  