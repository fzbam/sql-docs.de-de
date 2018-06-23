---
title: Sicherheitsrollenanforderungen für die Replikation | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security [SQL Server replication], roles
- roles [SQL Server], replication
ms.assetid: b324a80f-4319-4cb2-847b-1910c49d90e0
caps.latest.revision: 34
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: 7bddcd23b4da3fa95a3a73e63b6a1566b8f3a588
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36162235"
---
# <a name="security-role-requirements-for-replication"></a>Security Role Requirements for Replication
  Die Replikation schränkt auf der Basis der Rollen, die dem Benutzernamen des jeweiligen Benutzers zugeordnet sind, die Aktionen ein, die dieser Benutzer ausführen kann. Die Replikation hat der festen Serverrolle **sysadmin** , der festen Datenbankrolle **db_owner** und den Benutzernamen in der Veröffentlichungszugriffsliste bestimmte Berechtigungen erteilt.  
  
## <a name="security-role-requirements-for-replication-setup"></a>Sicherheitsrollenanforderungen für die Einrichtung der Replikation  
 Die folgende Tabelle gibt einen Überblick darüber, welche Authentifizierungsanforderungen für allgemeine Aufgaben bei der Einrichtung der Replikation erfüllt sein müssen:  
  
|Einrichtungsaufgabe|Erforderliche Mitgliedschaft|  
|----------------|----------------------------|  
|Aktivieren eines Verteilers, Verlegers bzw. Abonnenten|**sysadmin** -Serverrolle auf dem Verleger|  
|Aktivieren einer Datenbank für die Replikation|**sysadmin** -Serverrolle auf dem Verleger|  
|Erstellen einer Veröffentlichung|**db_owner** -Datenbankrolle in der Veröffentlichungsdatenbank auf dem Verleger bzw. **sysadmin** -Serverrolle auf dem Verleger|  
|Anzeigen von Veröffentlichungseigenschaften|Mitglied der Veröffentlichungszugriffsliste auf dem Verleger, **db_owner** -Datenbankrolle in der Veröffentlichungsdatenbank auf dem Verleger bzw. **sysadmin** -Serverrolle auf dem Verleger|  
|Erstellen eines Abonnements|**db_owner** -Datenbankrolle in der Veröffentlichungsdatenbank auf dem Verleger bzw. **sysadmin** -Serverrolle auf dem Verleger<br /><br /> **db_owner** -Datenbankrolle in der Abonnementdatenbank auf dem Abonnenten bzw. **sysadmin** -Serverrolle auf dem Abonnenten|  
|Konfigurieren von Agentprofilen|**sysadmin** -Serverrolle auf dem Verteiler|  
  
## <a name="security-role-requirements-for-replication-maintenance"></a>Sicherheitsrollenanforderungen für die Replikationswartung  
 Die folgende Tabelle gibt einen Überblick darüber, welche Authentifizierungsanforderungen für allgemeine Aufgaben bei der Wartung der Replikation erfüllt sein müssen:  
  
|Wartungsaufgabe|Erforderliche Mitgliedschaft|  
|----------------------|----------------------------|  
|Ändern oder Löschen eines Verteilers, Verlegers bzw. Abonnenten|**sysadmin** -Serverrolle auf dem entsprechenden Server|  
|Ändern oder Löschen einer Veröffentlichung|**db_owner** -Datenbankrolle in der Veröffentlichungsdatenbank auf dem Verleger bzw. **sysadmin** -Serverrolle auf dem Verleger|  
|Ändern oder Löschen eines Abonnements auf dem Verleger|**db_owner** -Datenbankrolle in der Veröffentlichungsdatenbank auf dem Verleger bzw. **sysadmin** -Serverrolle auf dem Verleger|  
|Ändern oder Löschen eines Abonnements auf dem Abonnenten|**db_owner** -Datenbankrolle in der Abonnementdatenbank auf dem Abonnenten bzw. **sysadmin** -Serverrolle auf dem Abonnenten|  
|Markieren eines Abonnements für die Neuinitialisierung|Pushabonnement: **db_owner** -Datenbankrolle in der Veröffentlichungsdatenbank auf dem Verleger bzw. **sysadmin** -Serverrolle auf dem Verleger.<br /><br /> Pullabonnement: **db_owner** -Datenbankrolle in der Abonnementdatenbank auf dem Abonnenten bzw. **sysadmin** -Serverrolle auf dem Abonnenten.|  
|Anzeigen der Replikationsaktivität, der Fehler und des Verlaufs mithilfe des Replikationsmonitors. Ein Benutzer kann Agentprofile, Zeitpläne usw. nicht ändern, wenn er nicht Mitglied der **sysadmin** -Serverrolle ist.|**replmonitor** -Datenbankrolle in der Verteilungsdatenbank auf dem Verteiler bzw. **sysadmin** -Serverrolle auf dem Verteiler|  
|Warten von Replikations-Agents|**db_owner** -Datenbankrolle in der entsprechenden Datenbank bzw. **sysadmin** -Serverrolle auf dem entsprechenden Server<br /><br /> Wenn der Agent von einem Benutzer in der **sysadmin** -Rolle erstellt wurde und für den Agent kein Proxykonto angegeben wurde, wird der Agent im Kontext des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Agent-Kontos ausgeführt. In diesem Fall können Benutzer mit der **db_owner** -Rolle den dem Agent zugewiesenen Auftrag nicht ändern.|  
|Starten oder Beenden eines Replikations-Agents|Besitzer des Agentauftrags bzw. der **sysadmin** -Serverrolle auf dem entsprechenden Server.|  
  
## <a name="see-also"></a>Siehe auch  
 [Replication Security Best Practices](replication-security-best-practices.md)   
 [Sicherheit und Schutz &#40;Replikation&#41;](security-and-protection-replication.md)  
  
  