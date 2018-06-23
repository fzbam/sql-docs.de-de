---
title: Percentage Sampling Transformation Editor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql12.dts.designer.percentagesamplingtransformation.f1
helpviewer_keywords:
- Percentage Sampling Transformation Editor
ms.assetid: 2c40d804-26a3-4d35-809b-bc923d83d451
caps.latest.revision: 24
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: 70e9b290c9d797e6471dc198da7a6299739c0be3
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36161613"
---
# <a name="percentage-sampling-transformation-editor"></a>Transformations-Editor für Prozentwertstichprobe
  Im Dialogfeld **Transformations-Editor für Prozentwertstichprobe** können Sie einen Teil der Eingabe mithilfe des angegebenen Prozentsatzes von Zeilen als Stichprobe entnehmen. Durch diese Transformation wird die Eingabe in zwei getrennte Ausgaben geteilt.  
  
 Weitere Informationen zur Transformation für Prozentwert-Stichproben finden Sie unter [Percentage Sampling Transformation](data-flow/transformations/percentage-sampling-transformation.md).  
  
## <a name="options"></a>Tastatur  
 **Prozentsatz der Zeilen**  
 Geben Sie den Prozentsatz der Zeilen in der Eingabe an, die als Stichprobe verwendet werden sollen.  
  
 Der Wert dieser Eigenschaft kann mithilfe eines Eigenschaftsausdrucks angegeben werden.  
  
 **Ausgabename für Stichprobendaten**  
 Geben Sie einen eindeutigen Namen für die Ausgabe an, die die als Stichprobe entnommenen Zeilen enthalten wird. Der bereitgestellte Name wird im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer angezeigt.  
  
 **Ausgabename für nicht ausgewählte Daten**  
 Geben Sie einen eindeutigen Namen für die Ausgabe an, die die Zeilen enthalten wird, die nicht zur Stichprobe gehören. Der bereitgestellte Name wird im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer angezeigt.  
  
 **Folgenden zufälligen Ausgangswert verwenden**  
 Geben Sie den Ausgangswert für den Zufallszahlen-Generator an, der von der Transformation zum Erstellen der Stichprobe verwendet wird. Dies wird ausschließlich für Entwicklung und Tests empfohlen. Wenn kein zufälliger Ausgangswert angegeben wird, wird von der Transformation die Taktanzahl aus Microsoft Windows verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen und Meldungsreferenz von Integration Services-Fehler](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Transformation für Zeilenstichproben](data-flow/transformations/row-sampling-transformation.md)  
  
  