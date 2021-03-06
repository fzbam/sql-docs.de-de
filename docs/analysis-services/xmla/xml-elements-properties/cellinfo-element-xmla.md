---
title: CellInfo-Element (XMLA) | Microsoft Docs
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 3ada531d33baf7007d08ac8a719fca2bf8f1b2e4
ms.sourcegitcommit: 808d23a654ef03ea16db1aa23edab496b73e5072
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2018
ms.locfileid: "34574252"
---
# <a name="cellinfo-element-xmla"></a>CellInfo-Element (XMLA)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../../includes/ssas-appliesto-sqlas-aas.md)]
  Stellt die Zellmetadaten dar, die das übergeordnete [OlapInfo](../../../analysis-services/xmla/xml-elements-properties/olapinfo-element-xmla.md) -Element enthält.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
  
<OlapInfo>  
   ...  
   <CellInfo>  
      <!-- One or more cell property definitions -->  
   </CellInfo>  
   ...  
</OlapInfo>  
```  
  
## <a name="element-characteristics"></a>Elementmerkmale  
  
|Merkmal|Description|  
|--------------------|-----------------|  
|Datentyp und -länge|InclusionThresholdSetting|  
|Standardwert|InclusionThresholdSetting|  
|Cardinality|1-1: Erforderliches Element, das nur einmal auftritt.|  
  
## <a name="element-relationships"></a>Elementbeziehungen  
  
|Beziehung|Element|  
|------------------|-------------|  
|Übergeordnete Elemente|[OlapInfo](../../../analysis-services/xmla/xml-elements-properties/olapinfo-element-xmla.md)|  
|Untergeordnete Elemente|Eine oder mehrere Definitionen der Zelleneigenschaften|  
  
## <a name="remarks"></a>Hinweise  
 Das **CellInfo** -Element enthält eine Auflistung der Zelleneigenschaften der Zellen, die in dem multidimensionalen Datensatz, der von einem **root** -Element mithilfe des **MDDataSet** -Datentyps zurückgegeben wird, enthalten sind. Jede Zelleneigenschaft in dem **CellInfo** -Element wird durch ein einzelnes XML-Element definiert, das jeweils ein **name** -Attribut und ein **type** -Attribut enthält. Das **name** -Attribut der Zelleneigenschaft entspricht dem Namen der OLE DB für die OLAP-Zelleneigenschaft, die durch das XML-Element dargestellt wird; das **type** -Attribut stellt den XML-Datentyp der Zelleneigenschaft dar. Der Name des XML-Elements wird verwendet, um den Wert der Zelleneigenschaft der Zellen zu identifizieren, die in dem **CellData** -Element des **root** -Elements enthalten sind.  
  
 Die folgende Syntax beschreibt die Definition einer Zelleneigenschaft:  
  
```  
<CellPropertyDefinition name="string" type"string" />  
```  
  
 Die benötigten Eigenschaften und ihre Werte können über eine Nutzung des Anforderungstyps DISCOVER_PROPERTIES mit der **Discover** -Methode abgerufen werden. Es gibt keine erforderliche Reihenfolge für die im **PropertyList** -Element aufgelisteten Eigenschaften.  
  
 Optional können Anbieter Standardwerte für einzelne Elemente oder Zelleneigenschaften im **AxisInfo** - oder **CellInfo** -Abschnitt angeben. Die Standardwerte können für eine kleinere Ergebnismenge sorgen, wenn die Eigenschaft immer oder fast immer den gleichen Wert hat. Zum Angeben eines Standardwerts für eine Eigenschaft kann das**Default** -Element optional als untergeordnetes Element von einem der Zelleneigenschaften-Definitionselemente angegeben werden. Das Fehlen eines Elements oder einer Zelleneigenschaft im Ergebnis deutet daher darauf hin, dass der angegebene Standardwert der Wert der Zelleneigenschaft ist.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt daher, wie die Zelleneigenschaften VALUE, FORMATTED_VALUE und FORMAT_STRING im **CellInfo** -Element dargestellt werden.  
  
```  
<OlapInfo>  
   ...  
      <CellInfo>  
         <Value name="VALUE"></Value>  
         <FmtValue name="FORMATTED_VALUE"></FmtValue>  
         <FormatString name="FORMAT_STRING"></FormatString>  
      </CellInfo>  
</OlapInfo>  
```  
  
## <a name="see-also"></a>Siehe auch
 [Eigenschaften &#40;XMLA&#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  
