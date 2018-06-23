---
title: CLR-fähig (Serverkonfigurationsoption) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assemblies [CLR integration], verifying can run
- clr enabled option
ms.assetid: 0722d382-8fd3-4fac-b4a8-cd2b7a7e0293
caps.latest.revision: 34
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1eb4bd97f6e008dbc84e7d7882b80cfff5c88f2c
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36150425"
---
# <a name="clr-enabled-server-configuration-option"></a>CLR-fähig (Serverkonfigurationsoption)
  Mithilfe der Option CLR-fähig können Sie angeben, ob Benutzerassemblys von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ausgeführt werden dürfen. Von der Option "CLR-fähig" werden folgende Werte bereitgestellt.  
  
|value|Description|  
|-----------|-----------------|  
|0|Das Ausführen von Assemblys für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ist unzulässig.|  
|1|Das Ausführen von Assemblys für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ist zulässig.|  
  
 WOW64-Server müssen neu gestartet werden, bevor die Änderungen an dieser Einstellung wirksam werden. Ein Neustart ist für andere Servertypen nicht erforderlich.  
  
> [!NOTE]  
>  Wenn RECONFIGURE ausgeführt und der Ausführungswert der Option "CLR-fähig" von 1 in 0 geändert wird, werden alle Anwendungsdomänen mit Benutzerassemblys sofort entladen.  
  
> [!NOTE]  
>  CLR (Common Language Runtime) wird beim Lightweightpooling nicht unterstützt. Deaktivieren Sie eine der beiden Optionen "CLR-fähig" oder "Lightweightpooling". Funktionen, die auf CLR basieren und nicht arbeiten ordnungsgemäß im Fibermodus, gehören die `hierarchy` -Datentyp, Replikation und richtlinienbasierte Verwaltung.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird zunächst die aktuelle Einstellung der Option CLR-fähig angezeigt und die Option dann aktiviert, indem der Optionswert auf 1 festgelegt wird. Wenn Sie die Option deaktivieren möchten, legen Sie den Wert auf 0 fest.  
  
```  
EXEC sp_configure 'clr enabled';  
EXEC sp_configure 'clr enabled' , '1';  
RECONFIGURE;  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Lightweightpooling (Serverkonfigurationsoption)](lightweight-pooling-server-configuration-option.md)   
 [Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md)   
 [sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)   
 [Lightweightpooling (Serverkonfigurationsoption)](lightweight-pooling-server-configuration-option.md)  
  
  