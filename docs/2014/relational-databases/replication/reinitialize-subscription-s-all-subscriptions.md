---
title: Abonnements erneut initialisieren - Alle Abonnements | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql12.rep.reinit.all.f1
helpviewer_keywords:
- Reinitialize Subscription(s) dialog box
ms.assetid: e1122018-9f74-43e3-8489-7eae33ff23d9
caps.latest.revision: 10
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: 953f091e9f55798a9d152a8911d9f041dfc18a45
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36056664"
---
# <a name="reinitialize-subscriptions---all-subscriptions"></a>Abonnements erneut initialisieren - Alle Abonnements
  Im Dialogfeld **Abonnements erneut initialisieren** können Sie alle Abonnements einer Veröffentlichung für eine Neuinitialisierung kennzeichnen. Im Zuge der Neuinitialisierung wird eine Momentaufnahme auf jeden Abonnenten angewendet. Die Momentaufnahmeanwendung wird für Abonnements von Transaktionsveröffentlichungen durch den Verteilungs-Agent und für Abonnements von Mergeveröffentlichungen durch den Merge-Agent vorgenommen.  
  
## <a name="options"></a>Tastatur  
 **Aktuelle Momentaufnahme verwenden**  
 Wählen Sie diese Option aus, wenn die aktuelle Momentaufnahme beim nächsten Ausführen des Verteilungs- oder Merge-Agents für das Abonnement auf alle Abonnenten angewendet werden soll. Wenn keine gültige Momentaufnahme verfügbar ist, kann diese Option nicht ausgewählt werden.  
  
 **Neue Momentaufnahme verwenden**  
 Wählen Sie diese Option aus, wenn alle Abonnements mithilfe einer neuen Momentaufnahme erneut initialisiert werden sollen. Die Momentaufnahme kann erst auf alle Abonnenten angewendet werden, nachdem er vom Momentaufnahme-Agent generiert wurde. Wenn für die Ausführung des Momentaufnahme-Agents ein Zeitplan festgelegt ist, werden die Abonnements erst bei der nächsten Ausführung des Momentaufnahme-Agents erneut initialisiert.  
  
 Wählen Sie die Option **Neue Momentaufnahme jetzt generieren** , um den Momentaufnahme-Agent sofort zu starten.  
  
 **Unsynchronisierte Änderungen am Abonnenten vor der erneuten Initialisierung hochladen**  
 Nur für Mergereplikationen zulässig. Wählen Sie diese Option aus, um alle ausstehenden Änderungen aus den Abonnementdatenbanken herunterzuladen, bevor die Daten der Abonnenten durch eine Momentaufnahme überschrieben werden.  
  
 Wenn Sie einen parametrisierten Filter hinzufügen, löschen oder ändern, können ausstehende Änderungen auf dem Abonnenten während der erneuten Initialisierung nicht auf den Verleger hochgeladen werden. Wenn Sie ausstehende Änderungen hochladen möchten, sollten Sie vor dem Ändern des Filters alle Abonnements synchronisieren.  
  
 **Für erneute Initialisierung kennzeichnen**  
 Klicken Sie auf diese Option, um alle Abonnements für die Neuinitialisierung zu kennzeichnen. Sofern eine gültige Momentaufnahme verfügbar ist, wird er beim nächsten Start des Verteilungs- oder Merge-Agents für das Abonnement auf den Abonnenten angewendet.  
  
## <a name="see-also"></a>Siehe auch  
 [Erneutes Initialisieren von Abonnements](reinitialize-subscriptions.md)  
  
  