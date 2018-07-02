---
title: Regeln zum Aktualisieren von Ergebnissen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- View Designer, Results pane
- updating query results
- Query Designer [SQL Server], Results pane
- Results pane
ms.assetid: de131ef0-ccbd-446f-9400-b93c7b8fa537
caps.latest.revision: 10
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e1f0dd3467f10c80f728288bc60c57f7d270b394
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36059052"
---
# <a name="rules-for-updating-results-visual-database-tools"></a>Regeln zum Aktualisieren von Ergebnissen (Visual Database Tools)
  In vielen Fällen können Sie das im [Ergebnisbereich](visual-database-tools.md)angezeigte Resultset aktualisieren. Manchmal ist dies allerdings nicht möglich.  
  
 Damit Ergebnisse aktualisiert werden können, muss der [Abfrage- und Sicht-Designer](query-and-view-designer-tools-visual-database-tools.md) über genügend Informationen verfügen, um die Zeile in der Tabelle eindeutig identifizieren zu können. Ein Beispiel ist der Fall, dass die Abfrage einen Primärschlüssel in die Ausgabeliste einfügt. Außerdem müssen Sie über eine ausreichende Berechtigung zum Update der Datenbank verfügen.  
  
 Wenn die Abfrage auf einer Sicht basiert, kann sie aktualisiert werden. Dieselben Richtlinien werden angewendet, allerdings nicht nur auf die Sicht selbst, sondern auf die zugrunde liegenden Tabellen in der Sicht.  
  
> [!NOTE]  
>  Der Abfrage- und Sicht-Designer kann nicht im Voraus ermitteln, ob Sie ein auf einer Sicht basierendes Resultset aktualisieren können. Daher werden alle Sichten angezeigt, obwohl Sie diese möglicherweise nicht aktualisieren können.  
  
 Die folgende Tabelle gibt eine Übersicht über die einzelnen Fälle, in denen Sie Abfrageergebnisse im Ergebnisbereich aktualisieren bzw. nicht aktualisieren können. Häufig wird durch die verwendete Datenbank bestimmt, ob die Ergebnisse einer Abfrage aktualisiert werden können.  
  
|Dataseteigenschaften|Können die Ergebnisse aktualisiert werden?|  
|-----------|-----------------------------|  
|Abfrage auf Grundlage einer Tabelle mit Primärschlüssel in der Ausgabeliste|Ja (außer wie im Folgenden aufgeführt).|  
|Abfrage auf Grundlage einer Tabelle ohne eindeutigen Index und Primärschlüssel|Hängt von der Abfrage und der Datenbank ab. Einige Datenbanken lassen Updates zu, wenn genügend Informationen zur eindeutigen Identifizierung von Datensätzen verfügbar sind.|  
|Abfrage auf Grundlage mehrerer Tabellen, die nicht verknüpft sind|Nein.|  
|Abfrage auf Grundlage von als schreibgeschützt markierten Daten der Datenbank|Nein.|  
|Abfrage auf Grundlage einer Sicht, die eine Tabelle ohne Einschränkungen umfasst|Ja (außer wie im Folgenden aufgeführt).|  
|Abfrage auf Grundlage von Tabellen, die über eine 1:1-Beziehung verknüpft sind|Ja (außer wie im Folgenden aufgeführt).|  
|Abfrage auf Grundlage von Tabellen, die über eine 1:n-Beziehung verknüpft sind|Meistens.|  
|Abfrage auf Grundlage von drei oder mehr Tabellen, bei denen eine m:n-Beziehung vorliegt|Nein.|  
|Abfrage auf Grundlage einer Tabelle, für die keine Updateberechtigung vorliegt|Kann gelöscht, aber nicht aktualisiert werden.|  
|Abfrage auf Grundlage einer Tabelle, für die keine Löschberechtigung vorliegt|Kann aktualisiert, aber nicht gelöscht werden.|  
|Aggregatabfrage|Nein.|  
|Abfrage auf Grundlage einer Unterabfrage, die Summen oder Aggregatfunktionen enthält|Nein.|  
|Abfrage, die das Schlüsselwort DISTINCT zum Ausschließen von doppelten Zeilen enthält|Nein.|  
|Abfrage, deren FROM-Klausel eine benutzerdefinierte Funktion enthält, die eine Tabelle zurückgibt, wobei diese Funktion mehrere SELECT-Anweisungen enthält|Nein.|  
|Abfrage, deren FROM-Klausel eine benutzerdefinierte Inlinefunktion enthält|Ja.|  
  
 Außerdem können Sie möglicherweise bestimmte Spalten in den Abfrageergebnissen nicht aktualisieren. Im Folgenden sind bestimmte Spaltentypen aufgeführt, die Sie im Ergebnisbereich nicht aktualisieren können.  
  
-   Spalten, die auf Ausdrücken basieren  
  
-   Spalten, die auf benutzerdefinierten Skalarfunktionen basieren  
  
-   Zeilen oder Spalten, die von einem anderen Benutzer gelöscht wurden  
  
-   Zeilen oder Spalten, die von einem anderen Benutzer gesperrt wurden (gesperrte Zeilen können i. d. R. unmittelbar nach Aufhebung der Sperre aktualisiert werden)  
  
-   Timestamp- oder BLOB-Spalten  
  
## <a name="see-also"></a>Siehe auch  
 [Themen zur Vorgehensweise: Entwerfen von Abfragen und Sichten &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  