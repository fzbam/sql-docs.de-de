---
title: Update Resync Eigenschaft dynamisch (ADO) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.component: ado
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
apitype: COM
helpviewer_keywords:
- Update Resync property [ADO]
ms.assetid: 8a3bb608-66d7-4128-a3ef-84cb0556de0d
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 71c18ad1db976c24ecb7a7e2ec09e04a8b5955d3
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="update-resync-property-dynamic-ado"></a>Aktualisieren Sie die Resync Eigenschaft dynamisch (ADO)
Gibt an, ob die [UpdateBatch](../../../ado/reference/ado-api/updatebatch-method.md) Methode einen impliziten gefolgt [Resync](../../../ado/reference/ado-api/resync-method.md) Vorgangs-Methode, und wenn dies der Fall ist, den Bereich dieses Vorgangs.  
  
## <a name="settings-and-return-values"></a>Einstellungen und Rückgabewerte  
 Legt fest oder gibt einen oder mehrere der [ADCPROP_UPDATERESYNC_ENUM](../../../ado/reference/ado-api/adcprop-updateresync-enum.md) Werte.  
  
## <a name="remarks"></a>Hinweise  
 Die Werte von ADCPROP_UPDATERESYNC_ENUM können kombiniert werden, mit Ausnahme von AdResyncAll, die bereits die Kombination aus den restlichen Werten darstellt.  
  
 Die Konstante **AdResyncConflicts** speichert die Resync-Werte als zugrunde liegenden Werte, jedoch wird keine ausstehenden Änderungen überschrieben.  
  
 **Resync aktualisieren** ist eine dynamische Eigenschaft angefügt die [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md) Objekt [Eigenschaften](../../../ado/reference/ado-api/properties-collection-ado.md) Auflistung bei der [CursorLocation](../../../ado/reference/ado-api/cursorlocation-property-ado.md) Eigenschaft auf festgelegtist**AdUseClient**.  
  
## <a name="applies-to"></a>Gilt für  
 [Recordset-Objekt (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)
