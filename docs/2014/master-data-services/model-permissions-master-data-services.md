---
title: Modellberechtigungen (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- models [Master Data Services], permissions
- permissions [Master Data Services], models
ms.assetid: 210f440b-2cc1-4c49-94b1-3a97e2af7bc3
caps.latest.revision: 5
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: e92f595bcf701e20378fe94dfde6c91d8c57bee1
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36050129"
---
# <a name="model-permissions-master-data-services"></a>Modellberechtigungen (Master Data Services)
  Modellberechtigungen gelten für alle Entitäten, Attribute, abgeleiteten Hierarchien, expliziten Hierarchien und Auflistungen innerhalb des Modells. Dem Modell zugewiesene Berechtigungen können für beliebige einzelne Objekte überschrieben werden.  
  
> [!NOTE]  
>  Wenn ein Benutzer ein Modelladministrator ist, wird das Modell in allen Funktionsbereichen der Benutzeroberfläche angezeigt. Andernfalls wird das Modell nur im Funktionsbereich **Explorer** angezeigt. Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).  
  
|Berechtigung|Description|  
|----------------|-----------------|  
|**Schreibgeschützt**|In **Explorer**, wird das Modell angezeigt, aber der Benutzer kann nicht hinzugefügt oder Entfernen von Mitgliedern und Attributwerte, hierarchiemitgliedschaften oder sammlungszugehörigkeiten kann nicht aktualisiert werden.|  
|**Update**|In **Explorer**, das Modell angezeigt und kann vom Benutzer hinzufügen und Entfernen von Mitgliedern, Attributwerte, hierarchiemitgliedschaften und auflistungsmitgliedschaften aktualisieren können.|  
|**Verweigern**|Das Modell wird nicht angezeigt.|  
  
 Wenn Sie einem Modell eine Berechtigung zuweisen, erhält der Benutzer Zugriff auf alle Versionen des Modells. Sie können keine Berechtigung für eine einzelne Version zuweisen.  
  
## <a name="see-also"></a>Siehe auch  
 [Zuweisen von Berechtigungen für Modellobjekte &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md)   
 [Modellobjektberechtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md)   
 [Entitätsberechtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/entity-permissions-master-data-services.md)   
 [Sammlungsberechtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/collection-permissions-master-data-services.md)  
  
  