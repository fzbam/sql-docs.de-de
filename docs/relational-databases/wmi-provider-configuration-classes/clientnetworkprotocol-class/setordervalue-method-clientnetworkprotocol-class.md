---
title: SetOrderValue-Methode (ClientNetworkProtocol-Klasse) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: wmi
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: reference
apiname: SetOrderValue Method (ClientNetworkProtocol Class)
apilocation: sqlmgmproviderxpsp2up.mof
apitype: MOFDef
helpviewer_keywords: SetOrderValue method
ms.assetid: 15f693fd-37f6-41d9-9dab-d2c93db19895
caps.latest.revision: "33"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: be269f8784d3812c0110bfbc12c53f1ad6cca7d0
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2017
---
# <a name="setordervalue-method-clientnetworkprotocol-class"></a>SetOrderValue-Methode (ClientNetworkProtocol-Klasse)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]Wählt das Protokoll mit dem angegebenen Reihenfolgenwert aus der clientprotokollliste aus.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
object.SetOrderValue(OrderValue)  
```  
  
## <a name="parts"></a>Bestandteile  
 *Objekt*  
 Ein [ClientNetworkProtocol-Klassenobjekt](../../../relational-databases/wmi-provider-configuration-classes/clientnetworkprotocol-class/clientnetworkprotocol-class.md) , das das vom [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Client verwendete Netzwerkprotokoll darstellt.  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Description|  
|---------------|-----------------|  
|*OrderValue*|Ein u**int32** -Wert, der den Reihenfolgenwert festlegt.|  
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 Ein **uint32** -Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaften der Clientprotokolle (Registerkarte Reihenfolge)](http://technet.microsoft.com/library/ms187884.aspx)  
  
  