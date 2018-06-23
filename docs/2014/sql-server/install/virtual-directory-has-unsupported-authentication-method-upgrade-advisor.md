---
title: Virtuelle Verzeichnis wurde eine nicht unterstützte Authentifizierungsmethode (Upgrade Advisor) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- virtual directories [Reporting Services]
ms.assetid: 216eca6f-9a66-42e1-aa54-dcf99cec9f7d
caps.latest.revision: 13
author: markingmyname
ms.author: maghan
manager: jhubbard
ms.openlocfilehash: 1504b19f521258e2491626540baf49988d7605c4
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36056405"
---
# <a name="virtual-directory-has-unsupported-authentication-method-upgrade-advisor"></a>Das virtuelle Verzeichnis weist eine nicht unterstützte Authentifizierungsmethode auf (Upgrade Advisor)
  Upgrade Advisor hat im Berichts-Manager oder im virtuellen Verzeichnis des Berichtsservers eine nicht unterstützte Authentifizierungsmethode erkannt. Authentifizierungsmethoden, die von einem Upgrade nicht unterstützt werden, sind Anonymous, Digest und .NET Passport.  
  
||  
|-|  
|**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Einheitlicher Modus.|  
  
## <a name="component"></a>Komponente  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a>Description  
 Setup kann eine [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Installation nicht aktualisieren, die eine der folgenden Authentifizierungsmethoden verwendet  
  
-   Anonym  
  
-   Digest  
  
-   .NET Passport  
  
 Um fortzufahren, können Sie entweder die Authentifizierungsmethode ändern, die für die virtuellen [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Verzeichnisse in den Internetinformationsdiensten (IIS) angegeben ist, oder die Installation migrieren. Weitere Informationen über das Migrieren einer Installation finden Sie in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation.  
  
## <a name="corrective-action"></a>Korrekturmaßnahme  
 Um das Upgrade fortzusetzen, ändern Sie in IIS die Authentifizierungsmethode für die virtuellen Verzeichnisse ReportServer und Reports. Weitere Informationen zum Ändern der Authentifizierungsmethode in IIS finden Sie in der IIS-Dokumentation. Führen Sie nach dem Ändern der Authentifizierungsmethode für die virtuellen Verzeichnisse von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] den Upgrade Advisor erneut aus, um zu bestätigen, dass keine weiteren Upgradeprobleme vorliegen.  
  
## <a name="see-also"></a>Siehe auch  
 [Upgradeprobleme bei Reporting Services &#40;Upgrade Advisor&#41;](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  