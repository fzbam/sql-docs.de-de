---
title: AllowedRowsExpression-Element (ASSL) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: ec24b11d-d11e-4369-a619-7e41a3c46159
caps.latest.revision: 7
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: 99a340f2bbeb1e5d61a20b4031beeade9fbcc5c7
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36047483"
---
# <a name="allowedrowsexpression-element-assl"></a>AllowedRowsExpression-Element (ASSL)
  Enthält einen DAX-Ausdruck (Data Analysis Expression) des booleschen Typs, der den Inhalt des übergeordneten Elements definiert.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
  
<CellPermission> <!-- or StandardAction -->  
   ...  
   <Expression>...</Expression>  
   ...  
</CellPermission>  
```  
  
## <a name="element-characteristics"></a>Elementmerkmale  
  
|Merkmal|Description|  
|--------------------|-----------------|  
|Datentyp und -länge|Zeichenfolge|  
|Standardwert|InclusionThresholdSetting|  
|Cardinality|1-1: Erforderliches Element, das nur einmal auftritt.|  
  
## <a name="element-relationships"></a>Elementbeziehungen  
  
|Beziehung|Element|  
|------------------|-------------|  
|Übergeordnete Elemente|[CellPermission](../objects/cellpermission-element-assl.md), [StandardAction](../data-type/action-data-type-assl.md)|  
|Untergeordnete Elemente|InclusionThresholdSetting|  
  
## <a name="remarks"></a>Hinweise  
 Für die `CellPermission` Element, die `Expression` Element enthält einen logischen MDX-Ausdruck, der auf den angegebenen Rechte anwendbar Zellen identifiziert die [Zugriff](access-element-assl.md) Element von der `CellPermission` Element. Wenn der Wert des ein `Expression` -Element für eine `CellPermission` -Element leer ist, die `CellPermission` Element wird ignoriert.  
  
 Beim Element `StandardAction` enthält das `Expression`-Element einen MDX-Ausdruck, der für die Inhalte der Aktion steht. Wenn der Wert des ein `Expression` -Element für eine `StandardAction` -Element leer ist, die `StandardAction` Element wird ignoriert.  
  
 Die Elemente, die den übergeordneten Elementen im AMO-Objektmodell (Analysis Management Objects) entsprechen, sind <xref:Microsoft.AnalysisServices.CellPermission> und <xref:Microsoft.AnalysisServices.StandardAction>.  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaften &#40;ASSL&#41;](properties-assl.md)  
  
  