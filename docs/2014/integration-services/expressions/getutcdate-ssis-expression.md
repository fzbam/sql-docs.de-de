---
title: GETUTCDATE (SSIS-Ausdruck) | Microsoft-Dokumentation
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
- dates [Integration Services], GETUTCDATE
- current date
- UTC time
- GETUTCDATE function
ms.assetid: 2282339c-c24f-493e-8e66-181ea8af5ad0
caps.latest.revision: 31
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: 091063acbaea65d155e578ff6a4c21c95d941a39
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36056510"
---
# <a name="getutcdate-ssis-expression"></a>GETUTCDATE (SSIS-Ausdruck)
  Gibt das aktuelle Datum des Systems als UTC-Zeit (Universal Time Coordinate oder Greenwich Mean Time) in einem DT_DBTIMESTAMP-Format zurück. Die GETUTCDATE-Funktion weist keine Argumente auf.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
GETUTCDATE()  
```  
  
## <a name="arguments"></a>Argumente  
 InclusionThresholdSetting  
  
## <a name="result-types"></a>Ergebnistypen  
 DT_DBTIMESTAMP  
  
## <a name="expression-examples"></a>Beispiele für Ausdrücke  
 In diesem Beispiel wird das Jahr des aktuellen Datums als UTC-Zeit zurückgegeben.  
  
```  
DATEPART("year",GETUTCDATE())  
```  
  
 In diesem Beispiel wird die Anzahl von Tagen zwischen einem Datum in der **ModifiedDate** -Spalte und dem aktuellen UTC-Datum zurückgegeben.  
  
```  
DATEDIFF("dd",ModifiedDate,GETUTCDATE())  
```  
  
 In diesem Beispiel werden dem aktuellen UTC-Datum drei Monate hinzugefügt.  
  
```  
DATEADD("Month",3,GETUTCDATE())  
```  
  
## <a name="see-also"></a>Siehe auch  
 [GETDATE &#40;SSIS-Ausdruck&#41;](getdate-ssis-expression.md)   
 [Funktionen &#40;SSIS-Ausdruck&#41;](functions-ssis-expression.md)  
  
  