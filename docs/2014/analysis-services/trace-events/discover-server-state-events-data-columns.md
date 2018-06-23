---
title: Discover Server State Events Data Columns | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Discover Server State event category
ms.assetid: fbacb187-a4d1-4aa4-be3b-3ddd175f9e19
caps.latest.revision: 31
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: afa5fdcba9e74e23c9ae8f5c4a9d4ac49f3ad0a9
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36060137"
---
# <a name="discover-server-state-events-data-columns"></a>Datenspalten mit Serverstatusermittlungs-Ereignissen
  Die Serverstatusermittlungs-Ereigniskategorie beinhaltet die folgenden Ereignisklassen:  
  
|**Ereignis-ID**|**Ereignisname**|**Ereignisbeschreibung**|  
|------------------|--------------------|---------------------------|  
|33|Server State Discover Begin|Start der Serverstatusermittlung.|  
|34|Server State Discover Data|Inhalt der Antwort der Serverstatusermittlung.|  
|35|Server State Discover End|Ende der Serverstatusermittlung.|  
  
 In den folgenden Tabellen sind die Datenspalten für jede dieser Ereignisklassen aufgeführt.  
  
## <a name="server-state-discover-begin-classdata-columns"></a>Server State Discover Begin-Klasse - Datenspalten  
  
|||||  
|-|-|-|-|  
|**Spaltenname**|**Spalten-ID**|**Spaltentyp**|**Spaltenbeschreibung**|  
|EventClass|0|1|Die Ereignisklasse dient zur Kategorisierung von Ereignissen.|  
|EventSubclass|1|1|Die Ereignisunterklasse enthält zusätzliche Informationen zu jeder Ereignisklasse.<br /><br /> 1: **DISCOVER_CONNECTIONS**<br /><br /> 2: **DISCOVER_SESSIONS**<br /><br /> 3: **DISCOVER_TRANSACTIONS**<br /><br /> 6: **DISCOVER_DB_CONNECTIONS**<br /><br /> 7: **DISCOVER_JOBS**<br /><br /> 8: **DISCOVER_LOCKS**<br /><br /> 12: **DISCOVER_PERFORMANCE_COUNTERS**<br /><br /> 13: **DISCOVER_MEMORYUSAGE**<br /><br /> 14: **DISCOVER_JOB_PROGRESS**<br /><br /> 15: **DISCOVER_MEMORYGRANT**|  
|CurrentTime|2|5|Enthält die aktuelle Zeit des Serverstatusermittlungs-Ereignisses (wenn verfügbar). Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|StartTime|3|5|Enthält den Zeitpunkt, zu dem das Ereignis begonnen hat, falls verfügbar. Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|ConnectionID|25|1|Enthält die eindeutige, dem Serverstatusermittlungs-Ereignis zugeordnete Verbindungs-ID.|  
|NTUserName|32|8|Enthält das mit dem Serverstatusermittlungs-Ereignis verbundene Windows-Benutzerkonto.|  
|NTDomainName|33|8|Enthält das mit dem Serverstatusermittlungs-Ereignis verbundene Windows-Domänenkonto.|  
|ClientProcessID|36|1|Enthält die Prozess-ID der Clientanwendung, die die Verbindung mit dem Server hergestellt hat.|  
|ApplicationName|37|8|Enthält den Namen der Clientanwendung, die die Verbindung mit dem Server hergestellt hat. Diese Spalte wird mit den Werten aufgefüllt, die von der Anwendung übergeben werden, und nicht mit dem angezeigten Namen des Programms.|  
|SessionID|39|8|Enthält die dem Serverstatusermittlungs-Ereignis zugeordnete Sitzungs-ID.|  
|NTCanonicalUserName|40|8|Enthält den mit dem Serverstatusermittlungs-Ereignis verbundenen Windows-Benutzernamen. Der Benutzername liegt im kanonischen Format vor. Beispiel: engineering.microsoft.com/software/user.|  
|SPID|41|1|Enthält die Serverprozess-ID (SPID), mit der die Benutzersitzung eindeutig identifiziert wird, die dem Serverstatusermittlungs-Ereignis zugeordnet ist. Die SPID entspricht direkt dem von XMLA verwendeten Sitzungs-GUID.|  
|TextData|42|9|Enthält die dem Ereignis zugeordneten Textdaten.|  
|ServerName|43|8|Enthält den Namen der Instanz von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , in der das Serverstatusermittlungs-Ereignis aufgetreten ist.|  
|RequestProperties|45|9|Enthält die Eigenschaften der aktuellen XMLA-Anforderung.|  
  
## <a name="server-state-discover-data-classdata-columns"></a>Server State Discover Data-Klasse - Datenspalten  
  
|||||  
|-|-|-|-|  
|**Spaltenname**|**Spalten-ID**|**Spaltentyp**|**Spaltenbeschreibung**|  
|EventClass|0|1|Die Ereignisklasse dient zur Kategorisierung von Ereignissen.|  
|EventSubclass|1|1|Die Ereignisunterklasse enthält zusätzliche Informationen zu jeder Ereignisklasse.<br /><br /> 1: **DISCOVER_CONNECTIONS**<br /><br /> 2: **DISCOVER_SESSIONS**<br /><br /> 3: **DISCOVER_TRANSACTIONS**<br /><br /> 6: **DISCOVER_DB_CONNECTIONS**<br /><br /> 7: **DISCOVER_JOBS**<br /><br /> 8: **DISCOVER_LOCKS**<br /><br /> 12: **DISCOVER_PERFORMANCE_COUNTERS**<br /><br /> 13: **DISCOVER_MEMORYUSAGE**<br /><br /> 14: **DISCOVER_JOB_PROGRESS**<br /><br /> 15: **DISCOVER_MEMORYGRANT**|  
|CurrentTime|2|5|Enthält die aktuelle Zeit des Serverstatusermittlungs-Ereignisses (wenn verfügbar). Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|StartTime|3|5|Enthält den Zeitpunkt, zu dem das Ereignis begonnen hat, falls verfügbar. Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|ConnectionID|25|1|Enthält die eindeutige, dem Serverstatusermittlungs-Ereignis zugeordnete Verbindungs-ID.|  
|SessionID|39|8|Enthält die dem Serverstatusermittlungs-Ereignis zugeordnete Sitzungs-ID.|  
|SPID|41|1|Enthält die Serverprozess-ID (SPID), mit der die Benutzersitzung eindeutig identifiziert wird, die dem Serverstatusermittlungs-Ereignis zugeordnet ist. Die SPID entspricht direkt dem von XMLA verwendeten Sitzungs-GUID.|  
|TextData|42|9|Enthält die Serverantwort auf die der Ermittlungsanforderung zugeordneten Textdaten.|  
|ServerName|43|8|Enthält den Namen der Instanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , in der das Serverstatusermittlungs-Ereignis aufgetreten ist.|  
  
## <a name="server-state-discover-end-classdata-columns"></a>Server State Discover Begin-Klasse - Datenspalten  
  
|||||  
|-|-|-|-|  
|**Spaltenname**|**Spalten-ID**|**Spaltentyp**|**Spaltenbeschreibung**|  
|EventClass|0|1|Die Ereignisklasse dient zur Kategorisierung von Ereignissen.|  
|EventSubclass|1|1|Die Ereignisunterklasse enthält zusätzliche Informationen zu jeder Ereignisklasse.<br /><br /> 1: **DISCOVER_CONNECTIONS**<br /><br /> 2: **DISCOVER_SESSIONS**<br /><br /> 3: **DISCOVER_TRANSACTIONS**<br /><br /> 6: **DISCOVER_DB_CONNECTIONS**<br /><br /> 7: **DISCOVER_JOBS**<br /><br /> 8: **DISCOVER_LOCKS**<br /><br /> 12: **DISCOVER_PERFORMANCE_COUNTERS**<br /><br /> 13: **DISCOVER_MEMORYUSAGE**<br /><br /> 14: **DISCOVER_JOB_PROGRESS**<br /><br /> 15: **DISCOVER_MEMORYGRANT**|  
|CurrentTime|2|5|Enthält die aktuelle Zeit des Serverstatusermittlungs-Ereignisses (wenn verfügbar). Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|StartTime|3|5|Enthält den Zeitpunkt, zu dem das Ereignis begonnen hat, falls verfügbar. Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|EndTime|4|5|Enthält die Uhrzeit, zu der das Ereignis beendet wurde. Diese Spalte wird für Startereignisklassen (z. B. SQL:BatchStarting oder SP:Starting) nicht aufgefüllt. Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|Duration|5|2|Enthält die Zeit (in Millisekunden), die für das Ereignis benötigt wurde.|  
|CPUTime|6|2|Enthält die CPU-Zeit (in Millisekunden), die vom Serverstatusermittlungs-Ereignis verwendet wird.|  
|ConnectionID|25|1|Enthält die eindeutige, dem Serverstatusermittlungs-Ereignis zugeordnete Verbindungs-ID.|  
|NTUserName|32|8|Enthält das mit dem Serverstatusermittlungs-Ereignis verbundene Windows-Benutzerkonto.|  
|NTDomainName|33|8|Enthält das mit dem Serverstatusermittlungs-Ereignis verbundene Windows-Domänenkonto.|  
|ClientProcessID|36|1|Enthält die Prozess-ID der Clientanwendung, von der die XMLA-Anforderung initiiert wurde.|  
|ApplicationName|37|8|Enthält den Namen der Clientanwendung, die die Verbindung mit dem Server hergestellt hat. Diese Spalte wird mit den Werten aufgefüllt, die von der Anwendung übergeben werden, und nicht mit dem angezeigten Namen des Programms.|  
|SessionID|39|8|Enthält das mit dem Serverstatusermittlungs-Ereignis verbundene Windows-Domänenkonto.|  
|NTCanonicalUserName|40|8|Enthält den mit dem Serverstatusermittlungs-Ereignis verbundenen Windows-Benutzernamen. Der Benutzername liegt im kanonischen Format vor. Beispiel: engineering.microsoft.com/software/user.|  
|SPID|41|1|Enthält die Serverprozess-ID (SPID), mit der die Benutzersitzung eindeutig identifiziert wird, die dem Serverstatusermittlungs-Ereignis zugeordnet ist. Die SPID entspricht direkt dem von XMLA verwendeten Sitzungs-GUID.|  
|TextData|42|9|Enthält die Serverantwort auf die der Ermittlungsanforderung zugeordneten Textdaten.|  
|ServerName|43|8|Enthält den Namen der Instanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , in der das Serverstatusermittlungs-Ereignis aufgetreten ist.|  
  
## <a name="see-also"></a>Siehe auch  
 [Serverstatusermittlung (Ereigniskategorie)](discover-server-state-event-category.md)  
  
  