---
title: Showplan XML Statistics Profile-Ereignisklasse | Microsoft-Dokumentation
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
- Showplan XML Statistics Profile event class
ms.assetid: 77e8ca69-d98a-4acd-9d6a-f825bf079d84
caps.latest.revision: 33
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e80473e97652d7991b8804429c2b6b6e228774a0
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36148367"
---
# <a name="showplan-xml-statistics-profile-event-class"></a>Showplan XML Statistics Profile-Ereignisklasse
  Die Showplan XML Statistics Profile-Ereignisklasse tritt auf, wenn [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eine SQL-Anweisung ausführt. Schließen Sie die Showplan XML Statistics Profile-Ereignisklasse ein, um die Showplan-Operatoren in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]zu identifizieren.  
  
 Die Showplan XML Statistics Profile-Ereignisklasse zeigt vollständige Kompilierzeitdaten an, sodass Ablaufverfolgungen, in denen diese Ereignisklasse enthalten ist, zu einer deutlich geringeren Systemleistung führen können. Beschränken Sie die Verwendung dieser Ereignisklasse auf Ablaufverfolgungen, die für kurze Zeit spezielle Probleme überwachen, um die Leistungsbeeinträchtigung möglichst gering zu halten.  
  
 Mit Showplan XML-Dokumenten ist ein Schema verknüpft. Sie finden dieses Schema auf der [Website von Microsoft](http://go.microsoft.com/fwlink/?LinkId=41740). Außerdem ist es Teil der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Installation.  
  
## <a name="showplan-xml-statistics-profile-event-class-data-columns"></a>Datenspalten der Showplan XML Statistics Profile-Ereignisklasse  
  
|Datenspaltenname|Datentyp|Description|Column ID|Filterbar|  
|----------------------|---------------|-----------------|---------------|----------------|  
|ApplicationName|`nvarchar`|Name der Clientanwendung, die die Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]hergestellt hat. Diese Spalte wird mit den Werten aufgefüllt, die von der Anwendung übergeben werden, und nicht mit dem angezeigten Namen des Programms.|10|ja|  
|BinaryData|`image`|Die geschätzten Kosten der Abfrage.|2|nein|  
|ClientProcessID|`int`|Die ID, die der Hostcomputer dem Prozess zuweist, in dem die Clientanwendung ausgeführt wird. Diese Datenspalte wird aufgefüllt, wenn die Clientprozess-ID durch den Client bereitgestellt wird.|9|ja|  
|DatabaseID|`int`|Die ID der Datenbank, die durch die USE *database* -Anweisung angegeben wurde, bzw. die ID der Standarddatenbank, wenn für eine bestimmte Instanz keine USE *database* -Anweisung ausgegeben wurde. [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] zeigt den Namen der Datenbank an, wenn die ServerName-Datenspalte in der Ablaufverfolgung aufgezeichnet wird und der Server verfügbar ist. Der Wert für eine Datenbank kann mithilfe der DB_ID-Funktion ermittelt werden.|3|ja|  
|DatabaseName|`nvarchar`|Name der Datenbank, in der die Benutzeranweisung ausgeführt wird.|35|ja|  
|Ereignisklasse|`int`|Ereignistyp = 146.|27|nein|  
|EventSequence|`int`|Sequenz eines bestimmten Ereignisses innerhalb der Anforderung.|51|nein|  
|GroupID|`int`|ID der Arbeitsauslastungsgruppe, in der das SQL-Ablaufverfolgungsereignis ausgelöst wird.|66|ja|  
|HostName|`nvarchar`|Der Name des Computers, auf dem der Client ausgeführt wird. Diese Datenspalte wird aufgefüllt, wenn der Hostname durch den Client bereitgestellt wird. Der Hostname kann mithilfe der HOST_NAME-Funktion bestimmt werden.|8|ja|  
|IntegerData|`int`|Geschätzte Anzahl der zurückgegebenen Zeilen.|25|ja|  
|IsSystem|`int`|Gibt an, ob das Ereignis bei einem Systemprozess oder einem Benutzerprozess aufgetreten ist. 1 = System, 0 = Benutzer.|60|ja|  
|LineNumber|`int`|Zeigt die Nummer der Zeile an, die den Fehler enthält|5|ja|  
|LoginName|`nvarchar`|Der Anmeldename des Benutzers ( [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Sicherheitsanmeldung oder [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Anmeldeinformationen im Format DOMAIN\username).|11|ja|  
|LoginSID|`image`|Sicherheits-ID (SID) des angemeldeten Benutzers. Diese Informationen finden Sie in der sys.server_principals-Katalogsicht. Die SID ist für jede Anmeldung beim Server eindeutig.|41|nein|  
|NestLevel|`int`|Ganze Zahl, die die von @@NESTLEVEL zurückgegebenen Daten darstellt.|29|ja|  
|NTDomainName|`nvarchar`|Windows-Domäne, zu der der Benutzer gehört.|7|ja|  
|ObjectID|`int`|Vom System zugewiesene ID des Objekts.|22|ja|  
|ObjectName|`nvarchar`|Der Name des Objekts, auf das verwiesen wird.|34|ja|  
|ObjectType|`int`|Der Wert, der den Typ des am Ereignis beteiligten Objekts darstellt. Dieser Wert entspricht der type-Spalte in der sys.objects-Katalogsicht. Weitere Werte finden Sie unter [ObjectType (Spalte für Ablaufverfolgungsereignisse)](objecttype-trace-event-column.md).|28|ja|  
|RequestID|`int`|Die ID der Anforderung, die die Anweisung enthält.|49|ja|  
|ServerName|`nvarchar`|Name der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz, für die eine Ablaufverfolgung ausgeführt wird.|26|nein|  
|SessionLoginName|`nvarchar`|Der Anmeldename des Benutzers, der die Sitzung gestartet hat. Wenn Sie beispielsweise mithilfe von Login1 eine Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herstellen und eine Anweisung als Login2 ausführen, zeigt SessionLoginName den Wert Login1 an und LoginName den Wert Login2. Diese Spalte zeigt die Windows-Anmeldenamen für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und [!INCLUDE[msCoName](../../includes/msconame-md.md)] an.|64|ja|  
|SPID|`int`|Die ID der Sitzung, in der das Ereignis aufgetreten ist.|12|ja|  
|StartTime|`datetime`|Zeitpunkt, zu dem das Ereignis begonnen hat (falls vorhanden).|14|ja|  
|TextData|`ntext`|Textwert, der von der Ereignisklasse abhängt, die in der Ablaufverfolgung aufgezeichnet wurde.|1|ja|  
|TransactionID|`bigint`|Die vom System zugewiesene ID der Transaktion.|4|ja|  
|XactSequence|`bigint`|Token zur Beschreibung der aktuellen Transaktion.|50|ja|  
  
## <a name="see-also"></a>Siehe auch  
 [Erweiterte Ereignisse](../extended-events/extended-events.md)   
 [sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)   
 [Referenz zu logischen und physischen Showplanoperatoren](../showplan-logical-and-physical-operators-reference.md)  
  
  