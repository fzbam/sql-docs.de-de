---
title: PropertyValType-Eigenschaft (ClientNetworkProtocolProperty-Klasse) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: wmi
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- PropertyValType Property (ClientNetworkProtocolProperty Class)
apilocation:
- sqlmgmproviderxpsp2up.mof
apitype: MOFDef
helpviewer_keywords:
- PropertyValType property
ms.assetid: 624b9bdd-ed93-4140-bd4e-00d714a2558c
caps.latest.revision: 31
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: 52652be7212b51e166b808f9f1ce0df514a40d6f
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="propertyvaltype-property-clientnetworkprotocolproperty-class"></a>PropertyValType-Eigenschaft (ClientNetworkProtocolProperty-Klasse)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]
  Ruft den Datentyp des Werts ab, der in der Eigenschaft gespeichert ist, auf die durch den [PropertyIdx-Eigenschaftswert (ClientNetworkProtocolProperty-Klasse)](../../../relational-databases/wmi-provider-configuration-classes/clientnetworkprotocolproperty-class/propertyidx-property-clientnetworkprotocolproperty-class.md) verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
object.PropertyValType [= value]  
```  
  
## <a name="parts"></a>Bestandteile  
 *Objekt*  
 A [ClientNetworkProtocolProperty-Klassenobjekt](../../../relational-databases/wmi-provider-configuration-classes/clientnetworkprotocolproperty-class/clientnetworkprotocolproperty-class.md) , das ein Attribut des vom [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Client verwendeten Netzwerkprotokolls darstellt.  
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 Ein **uint32** -Wert, der den Datentyp des Eigenschaftswerts angibt.  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Konfigurieren von Clientprotokollen](../../../database-engine/configure-windows/configure-client-protocols.md)  
  
  
