---
title: MONTH (SSIS-Ausdruck) | Microsoft-Dokumentation
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
- dates [Integration Services], MONTH
- MONTH function
ms.assetid: b5a47a11-c2ef-49bd-bd70-235632ff7bf6
caps.latest.revision: 38
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: 3208fbea606a066d5f1a2e9fdf566cb907267200
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36058526"
---
# <a name="month-ssis-expression"></a>MONTH (SSIS-Ausdruck)
  Gibt eine ganze Zahl zurück, die den datepart-Wert für die Monatsangabe in einem Datum darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
MONTH(date)  
```  
  
## <a name="arguments"></a>Argumente  
 *Datum*  
 Ein Datum in einem beliebigen Datumsformat.  
  
## <a name="result-types"></a>Ergebnistypen  
 DT_I4  
  
## <a name="remarks"></a>Hinweise  
 MONTH gibt ein NULL-Ergebnis zurück, wenn das Argument NULL ist.  
  
 Ein Datumsliteral muss explizit in einen der date-Datentypen umgewandelt werden. Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).  
  
> [!NOTE]  
>  Der Ausdruck wird nicht überprüft, wenn ein Datumsliteral explizit in einen der folgenden Datumsdatentypen umgewandelt wird: DT_DBTIMESTAMPOFFSET oder DT_DBTIMESTAMP2.  
  
 Die MONTH-Funktion entspricht bezüglich der Verwendung der DATEPART("Month", date)-Funktion, ist jedoch schneller.  
  
## <a name="expression-examples"></a>Beispiele für Ausdrücke  
 In diesem Beispiel wird der Monat eines Datumsliterals zurückgegeben. Falls das Datum das Format "mm/dd/yyyy" aufweist, wird 11 zurückgegeben.  
  
```  
MONTH((DT_DBTIMESTAMP)"11/23/2002")  
```  
  
 In diesem Beispiel wird die ganze Zahl zurückgegeben, die den Monat in der **ModifiedDate** -Spalte darstellt.  
  
```  
MONTH(ModifiedDate)  
```  
  
 In diesem Beispiel wird die ganze Zahl zurückgegeben, die den Monat des aktuellen Datums darstellt.  
  
```  
MONTH(GETDATE())  
```  
  
## <a name="see-also"></a>Siehe auch  
 [DATEADD &#40;SSIS-Ausdruck&#41;](dateadd-ssis-expression.md)   
 [DATEDIFF &#40;SSIS-Ausdruck&#41;](datediff-ssis-expression.md)   
 [DATEPART &#40;SSIS-Ausdruck&#41;](datepart-ssis-expression.md)   
 [DAY &#40;SSIS-Ausdruck&#41;](day-ssis-expression.md)   
 [YEAR &#40;SSIS-Ausdruck&#41;](year-ssis-expression.md)   
 [Funktionen &#40;SSIS-Ausdruck&#41;](functions-ssis-expression.md)  
  
  