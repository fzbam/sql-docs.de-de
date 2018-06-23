---
title: Aktualisierbare Abonnements | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql12.rep.newsubwizard.updatablesubscriptions.f1
ms.assetid: 8e9a13a0-6b24-47c6-9d83-3cbaf08f673d
caps.latest.revision: 21
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: 17b561938c9d1d8852e59db7078bfca5e9f298ab
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36056222"
---
# <a name="updatable-subscriptions"></a>Aktualisierbare Abonnements
  Bei der Transaktionsreplikation müssen replizierte Daten als schreibgeschützte Daten behandelt werden. Allerdings können Sie replizierte Daten auf einem [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Abonnenten ändern, indem Sie aktualisierbare Abonnements verwenden. Wenn Sie Daten auf dem Abonnenten ändern möchten, wählen Sie in Abhängigkeit von Ihren Anforderungen eine der folgenden Optionen aus:  
  
|Aktualisierbarer Abonnementtyp|Anforderungen|  
|---------------------------------|------------------|  
|Sofortige Updates|Verleger und Abonnent müssen verbunden sein, damit Daten auf dem Abonnenten aktualisiert werden können.|  
|Verzögerte Updates über eine Warteschlange|Verleger und Abonnent müssen nicht verbunden sein, damit Daten auf dem Abonnenten aktualisiert werden können. Updates können zunächst offline vorgenommen und später dann zwischen Verleger und Abonnent synchronisiert werden.|  
  
## <a name="options"></a>Tastatur  
 **Abonnentenänderungen replizieren**  
 Aktivieren Sie das Kontrollkästchen in der **Replizieren** -Spalte für jeden Abonnenten, der in der Lage sein soll, Updates vorzunehmen. Für jene Abonnenten, die Updates vornehmen können, wählen Sie aus dem Dropdownlistenfeld in der **Commit auf Verleger ausführen** -Spalte die entsprechende Option aus.  
  
-   Für ein Abonnement mit sofortigem Update wählen Sie **Commit für Änderungen gleichzeitig ausführen** aus.  
  
-   Für ein Abonnement mit verzögertem Update über eine Warteschlange wählen Sie **Änderungen in die Warteschlange einreihen und Commit baldmöglichst ausführen** .  
  
## <a name="see-also"></a>Siehe auch  
 [Create a Pull Subscription](create-a-pull-subscription.md)   
 [Create a Push Subscription](create-a-push-subscription.md)   
 [Subscribe to Publications](subscribe-to-publications.md)   
 [Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md)  
  
  