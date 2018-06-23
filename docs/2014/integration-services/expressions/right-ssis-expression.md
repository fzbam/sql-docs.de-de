---
title: RIGHT (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RIGHT function
ms.assetid: 83e70e75-4be5-4783-a8cf-032f82afe16e
caps.latest.revision: 41
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: ad391884f6ae57b6d87a042ede7be12ef1bfb093
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36058334"
---
# <a name="right-ssis-expression"></a>RIGHT (SSIS-Ausdruck)
  Gibt die angegebene Anzahl von Zeichen ab der äußersten rechten Position des angegebenen Zeichenausdrucks zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
RIGHT(character_expression,integer_expression)  
```  
  
## <a name="arguments"></a>Argumente  
 *character_expression*  
 Ein Zeichenausdruck, von dem Zeichen extrahiert werden sollen.  
  
 *integer_expression*  
 Ein ganzzahliger Ausdruck, der die Anzahl der zurückzugebenden Zeichen angibt.  
  
## <a name="result-types"></a>Ergebnistypen  
 DT_WSTR  
  
## <a name="remarks"></a>Hinweise  
 Wenn *integer_expression* größer ist als die Länge von *character_expression*, gibt die Funktion *character_expression*zurück.  
  
 Falls *integer_expression* null ist, gibt die Funktion eine leere Zeichenfolge zurück.  
  
 Falls *integer_expression* eine negative Zahl ist, gibt die Funktion einen Fehler zurück.  
  
 Für das *integer_expression* -Argument sind Variablen und Spalten möglich.  
  
 RIGHT kann nur mit dem DT_WSTR-Datentyp verwendet werden. Ein *character_expression* -Argument, das ein Zeichenfolgenliteral oder eine Datenspalte mit dem DT_STR-Datentyp ist, wird implizit in den DT_WSTR-Datentyp umgewandelt, bevor RIGHT ausgeführt wird. Andere Datentypen müssen explizit in den DT_WSTR-Datentyp umgewandelt werden. Weitere Informationen finden Sie unter [Integration Services-Datentypen](../data-flow/integration-services-data-types.md) und [CAST &#40;SSIS-Ausdruck&#41;](cast-ssis-expression.md).  
  
 RIGHT gibt ein NULL-Ergebnis zurück, wenn eines der Argumente NULL ist.  
  
## <a name="expression-examples"></a>Beispiele für Ausdrücke  
 Im folgenden Beispiel wird ein Zeichenfolgenliteral verwendet. Als Ergebnis wird `"Bike"`zurückgegeben.  
  
```  
RIGHT("Mountain Bike", 4)  
```  
  
 Im folgenden Beispiel wird die in der `Times` -Variablen angegebene Anzahl der äußersten rechten Zeichen aus der `Name` -Spalte zurückgegeben. Wenn `Name` den Wert `Touring Front Wheel` und `Times` den Wert 5 hat, wird als Ergebnis `"Wheel"`zurückgegeben.  
  
```  
RIGHT(Name, @Times)  
```  
  
 Im folgenden Beispiel wird auch die in der `Times` -Variablen angegebene Anzahl der äußersten rechten Zeichen aus der `Name` -Spalte zurückgegeben. `Times` weist einen anderen Datentyp als integer auf, und der Ausdruck umfasst eine explizite Umwandlung in den DT_I2-Datentyp. Wenn `Name` den Wert `Touring Front Wheel` und `Times` den Wert `4.32`hat, wird als Ergebnis `"heel"` zurückgegeben, da die RIGHT-Funktion den Wert 4.32 in 4 umwandelt und dann die äußersten rechten vier Zeichen zurückgibt.  
  
```  
RIGHT(Name, (DT_I2)@Times))  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Links &#40;SSIS-Ausdruck&#41;](left-ssis-expression.md)   
 [Funktionen &#40;SSIS-Ausdruck&#41;](functions-ssis-expression.md)  
  
  