---
title: Bewährte Vorgehensweisen für den Aufruf von systemintern kompilierten gespeicherten Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine-imoltp
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f39fc1c7-cfec-4a95-97f6-6b95954694bb
caps.latest.revision: 8
author: stevestein
ms.author: sstein
manager: jhubbard
ms.openlocfilehash: 5439f539e126a64cff92065e049da359e89345b4
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36159157"
---
# <a name="best-practices-for-calling-natively-compiled-stored-procedures"></a>Bewährte Vorgehensweisen für den Aufruf von systemintern kompilierten gespeicherten Prozeduren
  Für systemintern kompilierte gespeicherte Prozeduren gilt Folgendes:  
  
-   Sie werden üblicherweise in leistungskritischen Anwendungskomponenten verwendet.  
  
-   Sie werden häufig ausgeführt.  
  
-   Sie zeichnen sich erwartungsgemäß durch eine sehr schnelle Ausführung aus.  
  
 Der Leistungsvorteil bei Verwendung einer systemintern kompilierten gespeicherten Prozedur nimmt mit der Anzahl der Zeilen und dem Umfang der Logik zu, die von der Prozedur verarbeitet werden. Beispielsweise lässt sich die Leistung einer systemintern kompilierten gespeicherten Prozedur durch eine oder mehrere der folgenden Maßnahmen verbessern:  
  
-   Aggregation.  
  
-   Joins geschachtelter Schleifen.  
  
-   Auswahl-, Einfüge-, Update- und Löschvorgänge mit mehreren Anweisungen.  
  
-   Komplexe Ausdrücke.  
  
-   Prozedurale Logik, wie Bedingungsanweisungen und Schleifen.  
  
 Wenn Sie nur eine einzelne Zeile verarbeiten müssen, bietet eine systemintern kompilierte gespeicherte Prozedur u. U. keinen Leistungsvorteil.  
  
 So vermeiden Sie, dass der Server Parameternamen zuordnen und Typen konvertieren muss:  
  
-   Gleichen Sie die Typen der an die Prozedur übergebenen Parameter mit den Typen in der Prozedurdefinition ab.  
  
-   Verwenden Sie Ordnungszahlparameter (namenlos), wenn Sie systemintern kompilierte gespeicherte Prozeduren aufrufen. Verwenden Sie für die effizienteste Ausführung keine benannten Parameter.  
  
 Die Verwendung von (ineffizienten) benannten Parametern mit systemintern kompilierten gespeicherten Prozeduren kann über das XEvent `hekaton_slow_parameter_passing`, mit `reason=named_parameters`, erkannt werden.  
  
 Auf ähnliche Weise können Sie erkennen, die Verwendung von nicht übereinstimmenden Typen über dasselbe XEvent `hekaton_slow_parameter_passing`, mit `reason=parameter_conversion`.  
  
 Da Sie bei der Verwendung speicheroptimierter Tabellen (in vielen Fällen) Wiederholungslogik implementieren und bestimmte Funktionseinschränkungen umgehen müssen, können Sie eine von einem Wrapper interpretierte gespeicherte [!INCLUDE[tsql](../../includes/tsql-md.md)] -Prozedur erstellen. Ein Beispiel finden Sie unter [Richtlinien für die Wiederholungslogik für Transaktionen in speicheroptimierten Tabellen](memory-optimized-tables.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Systemintern kompilierte gespeicherte Prozeduren](natively-compiled-stored-procedures.md)  
  
  