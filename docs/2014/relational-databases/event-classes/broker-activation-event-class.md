---
title: Broker:Activation (Ereignisklasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
topic_type:
- apiref
helpviewer_keywords:
- Broker:Activation event class
ms.assetid: 481d5b13-657e-4b51-8783-ccac3595bd45
caps.latest.revision: 24
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 8449de73e5cb4f45d954774fd8a6b49d63d0d7e6
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36162715"
---
# <a name="brokeractivation-event-class"></a>Broker:Activation (Ereignisklasse)
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] generiert ein **Broker:Activation** -Ereignis, wenn eine Warteschlangenüberwachung eine gespeicherte Aktivierungsprozedur startet oder eine QUEUE_ACTIVATION-Benachrichtigung sendet oder wenn eine gespeicherte Aktivierungsprozedur, die von einer Warteschlangenüberwachung gestartet wurde, beendet wird.  
  
## <a name="brokeractivation-event-class-data-columns"></a>Datenspalten der Broker:Activation-Ereignisklasse  
  
|Datenspalte|Typ|Description|Spaltennummer|Filterbar|  
|-----------------|----------|-----------------|-------------------|----------------|  
|**ClientProcessID**|`int`|Die ID, die der Hostcomputer dem Prozess zuweist, in dem die Clientanwendung ausgeführt wird. Diese Datenspalte wird aufgefüllt, wenn die Clientprozess-ID durch den Client bereitgestellt wird.|9|ja|  
|**DatabaseID**|`int`|Die ID der Datenbank, die durch die USE *database* -Anweisung angegeben wurde, bzw. die ID der Standarddatenbank, wenn für eine bestimmte Instanz keine USE *database*-Anweisung ausgegeben wurde. [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] zeigt den Namen der Datenbank an, wenn die **ServerName** -Datenspalte in der Ablaufverfolgung aufgezeichnet wird und der Server verfügbar ist. Der Wert für eine Datenbank kann mithilfe der DB_ID-Funktion ermittelt werden.|3|ja|  
|**EventClass**|`int`|Der Typ der aufgezeichneten Ereignisklasse. Immer **163** für **Broker:Activation**.|27|nein|  
|**EventSequence**|`int`|Die Sequenznummer für dieses Ereignis.|51|nein|  
|**EventSubClass**|`nvarchar`|Die spezielle Aktion, die von diesem Ereignis gemeldet wird. Einer der folgenden Werte:<br /><br /> **Starten Sie**: <br />                [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] startete eine gespeicherte Aktivierungsprozedur.<br /><br /> **beendet**: die gespeicherte Aktivierungsprozedur wurde normal beendet.<br /><br /> **abgebrochene**: die gespeicherte Aktivierungsprozedur wurde mit einem Fehler beendet.|21|nein|  
|**HostName**|`nvarchar`|Der Name des Computers, auf dem der Client ausgeführt wird. Diese Datenspalte wird aufgefüllt, wenn der Hostname durch den Client bereitgestellt wird. Der Hostname kann mithilfe der HOST_NAME-Funktion bestimmt werden.|8|ja|  
|**IntegerData**|`int`|Die Anzahl der in dieser Warteschlange aktiven Aufgaben.|25|nein|  
|**IsSystem**|`int`|Gibt an, ob das Ereignis bei einem Systemprozess oder einem Benutzerprozess aufgetreten ist. 1 = System, 0 = Benutzer.|60|nein|  
|**LoginSid**|`image`|Die Sicherheits-ID (SID, Security Identification Number) des angemeldeten Benutzers. Die SID ist für jede Anmeldung beim Server eindeutig.|41|ja|  
|**NTDomainName**|`nvarchar`|Die Windows-Domäne, der der Benutzer angehört.|7|ja|  
|**NTUserName**|`nvarchar`|Der Name des Benutzers, der Besitzer der Verbindung ist, die dieses Ereignis generiert hat.|6|ja|  
|**ObjectID**|`int`|Die diesem Ereignis zugeordnete Warteschlange.|22|nein|  
|**ServerName**|`nvarchar`|Der Name der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , für die eine Ablaufverfolgung ausgeführt wird.|26|nein|  
|**SPID**|`int`|Die Serverprozess-ID, die von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dem Prozess zugewiesen wurde, der diesem Client zugeordnet ist.|12|ja|  
|**StartTime**|`datetime`|Der Zeitpunkt, zu dem das Ereignis begonnen hat, falls verfügbar.|14|ja|  
|**TransactionID**|`bigint`|Die vom System zugewiesene ID der Transaktion.|4|nein|  
  
  