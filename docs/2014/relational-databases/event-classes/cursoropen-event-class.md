---
title: CursorOpen-Ereignisklasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
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
- CursorOpen event class
ms.assetid: d39262c0-0035-42fc-b989-7a16ae0c7345
caps.latest.revision: 32
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 3bd0d597556c1dfbfff60b4b5f169e6185dd02d4
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36162534"
---
# <a name="cursoropen-event-class"></a>CursorOpen-Ereignisklasse
  Die **CursorOpen** -Ereignisklasse beschreibt cursoröffnende Ereignisse, die in API-Cursors (Application Programming Interface, Anwendungsprogrammierschnittstelle) auftreten. CursorOpen-Ereignisse treten auf, wenn [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] die SQL-Anweisung so definiert, dass sie dem Cursor und den Cursoroptionen zugeordnet wird und anschließend den Cursor füllt.  
  
 Schließen Sie die **CursorOpen** -Ereignisklasse in Ablaufverfolgungen ein, die die Leistung von Cursorn aufzeichnen. Wenn die **CursorOpen** -Ereignisklasse in eine Ablaufverfolgung eingeschlossen wird, hängt der Aufwand davon ab, wie oft Cursor für die Datenbank während der Ablaufverfolgung verwendet werden. Wenn Cursor sehr häufig verwendet werden, kann die Ablaufverfolgung die Leistung erheblich beeinträchtigen.  
  
## <a name="cursoropen-event-class-data-columns"></a>Datenspalten der CursorOpen-Ereignisklasse  
  
|Datenspaltenname|Datentyp|Description|Column ID|Filterbar|  
|----------------------|---------------|-----------------|---------------|----------------|  
|**ApplicationName**|**nvarchar**|Name der Clientanwendung, die die Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]hergestellt hat. Diese Spalte wird mit den Werten aufgefüllt, die von der Anwendung übergeben werden, und nicht mit dem angezeigten Namen des Programms.|10|ja|  
|**ClientProcessID**|**int**|Die ID, die der Hostcomputer dem Prozess zuweist, in dem die Clientanwendung ausgeführt wird. Diese Datenspalte wird aufgefüllt, wenn der Client die Clientprozess-ID angibt.|9|ja|  
|**DatabaseID**|**int**|Die ID der Datenbank, die durch die USE *Datenbank* -Anweisung angegeben wurde, bzw. die ID der Standarddatenbank, wenn für eine bestimmte Instanz keine USE *Datenbank*-Anweisung ausgegeben wurde. [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] zeigt den Namen der Datenbank an, wenn die **ServerName** -Datenspalte in der Ablaufverfolgung aufgezeichnet wird und der Server verfügbar ist. Der Wert für eine Datenbank kann mithilfe der DB_ID-Funktion ermittelt werden.|3|ja|  
|**DatabaseName**|**nvarchar**|Name der Datenbank, in der die Benutzeranweisung ausgeführt wird.|35|ja|  
|**EventClass**|**int**|Typ des aufgezeichneten Ereignisses = 53.|27|nein|  
|**EventSequence**|**int**|Die Sequenz der **CursorOpen** -Ereignisklasse im Batch.|51|nein|  
|**GroupID**|**int**|ID der Arbeitsauslastungsgruppe, in der das SQL-Ablaufverfolgungsereignis ausgelöst wird.|66|ja|  
|**Handle**|**int**|Eine ganze Zahl, die von ODBC, OLE DB oder DB-Library zum Koordinieren der Ausführung mit dem Server verwendet wird.|33|ja|  
|**HostName**|**nvarchar**|Der Name des Computers, auf dem der Client ausgeführt wird. Diese Datenspalte wird aufgefüllt, wenn der Hostname vom Client bereitgestellt wird. Der Hostname kann mithilfe der HOST_NAME-Funktion bestimmt werden.|8|ja|  
|**IntegerData**|**int**|Cursortyp. Die Werte sind:<br /><br /> 1 = Keyset<br /><br /> 2 = Dynamisch<br /><br /> 4 = Vorwärtscursor<br /><br /> 8 = Statisch<br /><br /> 16 = Schneller Vorlauf|25|ja|  
|**IsSystem**|**int**|Gibt an, ob das Ereignis bei einem Systemprozess oder einem Benutzerprozess aufgetreten ist. 1 = System, 0 = Benutzer.|60|ja|  
|**LoginName**|**nvarchar**|Der Anmeldename des Benutzers ( [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Sicherheitsanmeldung oder [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Anmeldeinformationen im Format DOMAIN\username).|11|ja|  
|**LoginSid**|**image**|Die Sicherheits-ID (Security Identifier, SID) des angemeldeten Benutzers. Diese Informationen finden Sie in der **sys.server_principals** -Katalogsicht. Die SID ist für jede Anmeldung beim Server eindeutig.|41|ja|  
|**NTDomainName**|**nvarchar**|Windows-Domäne, zu der der Benutzer gehört.|7|ja|  
|**NTUserName**|**nvarchar**|Windows-Benutzername.|6|ja|  
|**RequestID**|**int**|Die Anforderungs-ID, von der der Cursor geöffnet wurde.|49|ja|  
|**ServerName**|**nvarchar**|Name der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz, für die eine Ablaufverfolgung ausgeführt wird.|26|nein|  
|**SessionLoginName**|**nvarchar**|Der Anmeldename des Benutzers, der die Sitzung geöffnet hat. Wenn Sie z. B. mit Login1 eine Verbindung zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herstellen und mit Login2 eine Anweisung ausführen, zeigt **SessionLoginName** Login1 an, und **LoginName** zeigt Login2 an. Diese Spalte zeigt sowohl den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] - als auch den Windows-Anmeldenamen an.|64|ja|  
|**SPID**|**int**|Die ID der Sitzung, in der das Ereignis aufgetreten ist.|12|ja|  
|**StartTime**|**datetime**|Zeitpunkt, zu dem das Ereignis begonnen hat (falls vorhanden).|14|ja|  
|**TransactionID**|**bigint**|Die vom System zugewiesene ID der Transaktion.|4|ja|  
|**XactSequence**|**bigint**|Das Token zur Beschreibung der aktuellen Transaktion.|50|ja|  
  
## <a name="see-also"></a>Siehe auch  
 [Erweiterte Ereignisse](../extended-events/extended-events.md)   
 [sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)   
 [Cursor](../cursors.md)  
  
  