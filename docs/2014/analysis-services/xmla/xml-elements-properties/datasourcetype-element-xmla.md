---
title: DataSourceType-Element (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- DataSourceType Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- urn:schemas-microsoft-com:xml-analysis#DataSourceType
- microsoft.xml.analysis.datasourcetype
- http://schemas.microsoft.com/analysisservices/2003/engine#DataSourceType
helpviewer_keywords:
- DataSourceType element
ms.assetid: f5a348b1-911b-4139-832e-4bcb6d80a728
caps.latest.revision: 12
author: mgblythe
ms.author: mblythe
manager: mblythe
ms.openlocfilehash: cc083742521abfe9114ea474fe0987861d12c04e
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36059887"
---
# <a name="datasourcetype-element-xmla"></a>DataSourceType-Element (XMLA)
  Gibt an, ob eine [Speicherort](location-element-xmla.md) für angegebene Element ein [wiederherstellen](../xml-elements-commands/restore-element-xmla.md) oder [Synchronize](../xml-elements-commands/synchronize-element-xmla.md) Befehl ist, lokal oder remote.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
  
<Location>  
   ...  
   <DataSourceType>...</DataSourceType>  
   ...  
</Location>  
```  
  
## <a name="element-characteristics"></a>Elementmerkmale  
  
|Merkmal|Description|  
|--------------------|-----------------|  
|Datentyp und -länge|Zeichenfolge (Enumeration)|  
|Standardwert|*Remoteserver*|  
|Cardinality|0-1: Optionales Element, das nur einmal auftreten kann.|  
  
## <a name="element-relationships"></a>Elementbeziehungen  
  
|Beziehung|Element|  
|------------------|-------------|  
|Übergeordnete Elemente|[Speicherort](location-element-xmla.md)|  
|Untergeordnete Elemente|InclusionThresholdSetting|  
  
## <a name="remarks"></a>Hinweise  
 Das `DataSourceType`-Element bestimmt, ob die Datenquelle, die vom `Location`-Element definiert wird, eine lokale Datenquelle oder eine Remote-Datenquelle enthält. Weitere Informationen zum Sichern und Wiederherstellen von Remotepartitionen finden Sie unter [sichern, wiederherstellen und Synchronisieren von Datenbanken &#40;XMLA&#41;](../../multidimensional-models-scripting-language-assl-xmla/backing-up-restoring-and-synchronizing-databases-xmla.md).  
  
 Der Wert dieses Elements ist auf eine der in der folgenden Tabelle aufgelisteten Zeichenfolgen beschränkt.  
  
|value|Description|  
|-----------|-----------------|  
|*Lokale*|Die `Location` -Element definiert eine lokale Datenquelle. Wenn dieser Wert verwendet wird, verwenden die `Restore`- und `Synchronize`-Befehle die Informationen, die im `Location`-Element definiert werden, um die Datenquelle zu aktualisieren. Diese wurde entweder aus der Sicherungsdatei abgerufen, die im `File`-Element für den `Backup`-Befehl angegeben ist, oder aus der Datenbank, die im `Source`-Element für den `Synchronize`-Befehl angegeben ist, der im `DataSourceID`-Element des `Location`-Elements definiert ist.<br /><br /> Dieser Wert ermöglicht es, dass Objekte, die ROLAP-Speicherung (relational OLAP) verwenden, nach der Wiederherstellung und Synchronisierung eine andere Datenbank für ihre Daten und Metadaten verwenden. **Hinweis:** ROLAP-Daten, z. B. Daten in Dimensionstabellen oder Rückschreibetabellen werden nicht wiederhergestellt oder synchronisiert. Nur Metadaten für ROLAP-Objekte werden wiederhergestellt oder synchronisiert.|  
|*Remoteserver*|Das `Location`-Element definiert eine Remote-Datenquelle. Wenn dieser Wert wird verwendet, die `Restore` und `Synchronize` Befehle verwenden Sie die Informationen, die definiert, der `Location` Element wiederherstellen oder Synchronisieren von Remotepartitionen abgerufen entweder aus die Sicherungsdatei, die im angegebenen der `File` Element von der `Backup` Befehl oder der Datenbank der `Source` -Element für die `Synchronize` Befehl, auf die Remoteinstanz identifiziert, der `DataSourceID` von der `Location` Element.|  
  
## <a name="see-also"></a>Siehe auch  
 [ConnectionString-Element &#40;XMLA&#41;](connectionstring-element-xmla.md)   
 [DataSourceID-Element &#40;XMLA&#41;](id-element-xmla.md)   
 [Eigenschaften &#40;XMLA&#41;](xml-elements-properties.md)  
  
  