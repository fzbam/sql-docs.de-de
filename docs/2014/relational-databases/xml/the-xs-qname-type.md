---
title: Der xs:QName-Typ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-xml
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- xs:QName type
ms.assetid: 72c5bfde-b0b2-4372-bf36-97ba930dea06
caps.latest.revision: 8
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: 393130177c3597a9681e784e09be29fa8c2341fa
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36150532"
---
# <a name="the-xsqname-type"></a>Der xs:QName-Typ
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unterstützt keine von **xs:QName** abgeleiteten Typen, die ein Beschränkungselement des XML-Schemas verwenden. Außerdem unterstützt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aktuell keine union-Typen mit **QName** als Elementtyp.  
  
## <a name="example"></a>Beispiel  
 Die folgende `CREATE XML SCHEMA COLLECTION` -Anweisungen kann das XML-Schema nicht laden, weil sie den `xs:QName` -Typ als Mitgliedstyp von union festlegen:  
  
```  
CREATE XML SCHEMA COLLECTION QNameLimitation1 AS N'  
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:simpleType name="myUnion">  
        <xs:union memberTypes="xs:int xs:QName"/>  
    </xs:simpleType>  
</xs:schema>'  
GO  
  
CREATE XML SCHEMA COLLECTION QNameLimitation2 AS N'  
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:simpleType name="myUnion">  
        <xs:union memberTypes="xs:integer">  
   <xs:simpleType>  
    <xs:list itemType="xs:QName"/>  
   </xs:simpleType>  
  </xs:union>  
    </xs:simpleType>  
</xs:schema>'  
GO  
```  
  
 Beide Anweisungen führen zu einem Fehler.  
  
## <a name="see-also"></a>Siehe auch  
 [Anforderungen und Einschränkungen für XML-Schemaauflistungen auf dem Server](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  