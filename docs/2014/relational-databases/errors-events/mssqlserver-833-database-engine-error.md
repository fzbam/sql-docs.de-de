---
title: MSSQLSERVER_833 | Microsoft-Dokumentation
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
- 833 (Database Engine error)
ms.assetid: 14129cc4-be80-4772-9e3f-0e5da4d0696b
caps.latest.revision: 19
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: 53f86ad23c967f573e66251430579475e64a0714
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36163135"
---
# <a name="mssqlserver833"></a>MSSQLSERVER_833
    
## <a name="details"></a>Details  
  
|||  
|-|-|  
|Produktname|SQL Server|  
|Ereignis-ID|833|  
|Ereignisquelle|MSSQLSERVER|  
|Komponente|SQLEngine|  
|Symbolischer Name|BUF_LONG_IO|  
|Meldungstext|SQL Server wurden %d Leerungen des e/a-Anforderungen von mehr als %d Sekunden für Datei [%ls] in der Datenbank abgeschlossen`[%ls] (%d)`.  Das Dateihandle des Betriebssystems lautet 0x%p.  Der Offset des letzten langen E/A-Vorgangs lautet: %#016I64x.|  
  
## <a name="explanation"></a>Erklärung  
 Mit dieser Meldung wird angegeben, dass von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eine Lese- oder Schreibanforderung vom Datenträger ausgegeben wurde und dass die Rückgabe der Anforderung länger als 15 Sekunden gedauert hat. Dieser Fehler wird von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gemeldet und deutet auf ein Problem mit dem E/A-Subsystem hin.  
  
### <a name="possible-causes"></a>Mögliche Ursachen  
 Dieses Problem kann durch eine beeinträchtigte Systemleistung, Hardware- oder Firmwarefehler, Gerätetreiberprobleme oder das Eingreifen von Filtertreibern im E/A-Vorgang verursacht werden.  
  
## <a name="user-action"></a>Benutzeraktion  
 Sie können diesen Fehler durch Überprüfung des Systemereignisprotokolls auf hardwarebedingte Fehlermeldungen beheben. Sie können zudem hardwarespezifische Protokolle überprüfen, sofern diese verfügbar sind.  
  
 Prüfen Sie mit dem Systemmonitor die folgenden Leistungsindikatoren:  
  
-   **Average Disk Sec/Transfer**  
  
-   **Average Disk Queue Length**  
  
-   **Current Disk Queue Length**  
  
 Beispielsweise beträgt die Zeit von **Average Disk Sec/Transfer** für einen Computer mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] normalerweise unter 15 Millisekunden. Wenn sich der Wert **Average Disk Sec/Transfer** erhöht, ist dies ein Hinweis darauf, dass das E/A-Subsystem den E/A-Bedarf nicht optimal erfüllt.  
  
> [!NOTE]  
>  Der Datenträgerzugriff wird möglicherweise durch ein Antivirenprogramm verzögert. Schließen Sie die in der Fehlermeldung angegebenen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datendateien von aktiven Virenüberprüfungen aus, um die Zugriffsgeschwindigkeit zu erhöhen.  
  
 Weitere Informationen zu E/A-Fehlern finden Sie unter [Microsoft SQL Server I/O Basics, Chapter 2 (E/A-Grundlagen von Microsoft SQL Server, Kapitel 2)](http://go.microsoft.com/fwlink/?LinkId=69370) und im Knowledge Base-Artikel unter [http://support.microsoft.com/kb/897284/en-us](http://support.microsoft.com/kb/897284/en-us).  
  
  