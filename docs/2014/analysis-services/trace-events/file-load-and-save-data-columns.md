---
title: File Load- und Save Data Columns | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0101e809-d6ea-4d0c-95ec-65dd77acf665
caps.latest.revision: 4
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: f3e5ddbc14ab934dfdd0c1a16c2ec7f711f67a57
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36056346"
---
# <a name="file-load-and-save-data-columns"></a>Laden von Dateien und Speichern von Datenspalten
  Die Dateiereigniskategorie "Laden und speichern" besitzt die folgende Ereignisklasse:  
  
|**Ereignis-ID**|**Ereignisname**|**Ereignisbeschreibung**|  
|------------------|--------------------|---------------------------|  
|90|File Load Begin|Beginnt das Laden der Datei.|  
|91|File Load End|Beendet das Laden der Datei.|  
|92|File Save Begin|Beginnt das Speichern der Datei.|  
|93|File Save End|File Save End|  
|94|PageOut Begin|Beginnt den PageOut-Vorgang.|  
|95|PageOut End|PageOut End|  
|96|PageIn Begin|Beginnt den PageIn-Vorgang.|  
|97|PageIn End|PageIn End|  
  
 In der folgenden Tabelle sind die Datenspalten für diese Ereignisklasse aufgeführt.  
  
## <a name="file-load-begin"></a>File Load Begin  
  
|**Spaltenname**|**Spalten-ID**|**Spaltentyp**|**Spaltenbeschreibung**|  
|---------------------|-------------------|---------------------|----------------------------|  
|EventClass|0|1|Die Ereignisklasse dient zur Kategorisierung von Ereignissen.|  
|CurrentTime|2|5|Der Zeitpunkt, zu dem das Ereignis begonnen hat (falls verfügbar). Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|StartTime|3|5|Der Zeitpunkt, zu dem das Ereignis begonnen hat (falls verfügbar). Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|JobID|7|1|Auftrags-ID für den Status.|  
|SessionType|8|8|Sitzungstyp (Entität, die den Vorgang verursacht hat).|  
|ObjectID|11|8|Objekt-ID (beachten Sie, dass dies eine Zeichenfolge ist).|  
|ObjectType|12|1|Objekttyp.|  
|ObjectName|13|8|Objektname.|  
|ObjectPath|14|8|Objektpfad. Eine durch Trennzeichen getrennte Liste von übergeordneten Elementen, die beim übergeordneten Element des Objekts beginnt.|  
|ConnectionID|25|1|Eindeutige Verbindungs-ID.|  
|DatabaseName|28|8|Name der Datenbank, in der die Anweisung des Benutzers ausgeführt wird.|  
|ClientProcessID|36|1|Die Prozess-ID der Clientanwendung.|  
|SessionID|39|8|Sitzungs-GUID.|  
|TextData|42|9|Dem Ereignis zugeordnete Textdaten.|  
|ServerName|43|8|Name des Servers, der das Ereignis erzeugt.|  
  
## <a name="file-load-end"></a>File Load End  
  
|**Spaltenname**|**Spalten-ID**|**Spaltentyp**|**Spaltenbeschreibung**|  
|---------------------|-------------------|---------------------|----------------------------|  
|EventClass|0|1|Die Ereignisklasse dient zur Kategorisierung von Ereignissen.|  
|CurrentTime|2|5|Der Zeitpunkt, zu dem das Ereignis begonnen hat (falls verfügbar). Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|StartTime|3|5|Der Zeitpunkt, zu dem das Ereignis begonnen hat (falls verfügbar). Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|EndTime|4|5|Der Zeitpunkt, zu dem das Ereignis beendet wurde. Diese Spalte wird für Startereignisklassen (z. B. SQL:BatchStarting oder SP:Starting) nicht aufgefüllt. Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|Duration|5|2|Die Zeit (in Millisekunden), die für das Ereignis benötigt wurde.|  
|JobID|7|1|Auftrags-ID für den Status.|  
|SessionType|8|8|Sitzungstyp (Entität, die den Vorgang verursacht hat).|  
|IntegerData|10|1|Ganzzahlige Daten.|  
|ObjectID|11|8|Objekt-ID (beachten Sie, dass dies eine Zeichenfolge ist).|  
|ObjectType|12|1|Objekttyp.|  
|ObjectName|13|8|Objektname.|  
|ObjectPath|14|8|Objektpfad. Eine durch Trennzeichen getrennte Liste von übergeordneten Elementen, die beim übergeordneten Element des Objekts beginnt.|  
|Schweregrad|22|1|Schweregrad einer Ausnahme.|  
|Success|23|1|1 = Erfolg 0 = Fehler (z. B. gibt 1 den Erfolg einer Berechtigungsüberprüfung und 0 einen Fehler bei dieser Überprüfung an).|  
|Fehler|24|1|Fehlernummer eines bestimmten Ereignisses.|  
|ConnectionID|25|1|Eindeutige Verbindungs-ID.|  
|DatabaseName|28|8|Name der Datenbank, in der die Anweisung des Benutzers ausgeführt wird.|  
|ClientProcessID|36|1|Die Prozess-ID der Clientanwendung.|  
|SessionID|39|8|Sitzungs-GUID.|  
|TextData|42|9|Dem Ereignis zugeordnete Textdaten.|  
|ServerName|43|8|Name des Servers, der das Ereignis erzeugt.|  
  
## <a name="file-save-begin"></a>File Save Begin  
  
|**Spaltenname**|**Spalten-ID**|**Spaltentyp**|**Spaltenbeschreibung**|  
|---------------------|-------------------|---------------------|----------------------------|  
|EventClass|0|1|Die Ereignisklasse dient zur Kategorisierung von Ereignissen.|  
|CurrentTime|2|5|Der Zeitpunkt, zu dem das Ereignis begonnen hat (falls verfügbar). Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|StartTime|3|5|Der Zeitpunkt, zu dem das Ereignis begonnen hat (falls verfügbar). Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|JobID|7|1|Auftrags-ID für den Status.|  
|SessionType|8|8|Sitzungstyp (Entität, die den Vorgang verursacht hat).|  
|ObjectID|11|8|Objekt-ID (beachten Sie, dass dies eine Zeichenfolge ist).|  
|ObjectType|12|1|Objekttyp.|  
|ObjectName|13|8|Objektname.|  
|ObjectPath|14|8|Objektpfad. Eine durch Trennzeichen getrennte Liste von übergeordneten Elementen, die beim übergeordneten Element des Objekts beginnt.|  
|ConnectionID|25|1|Eindeutige Verbindungs-ID.|  
|DatabaseName|28|8|Name der Datenbank, in der die Anweisung des Benutzers ausgeführt wird.|  
|ClientProcessID|36|1|Die Prozess-ID der Clientanwendung.|  
|SessionID|39|8|Sitzungs-GUID.|  
|TextData|42|9|Dem Ereignis zugeordnete Textdaten.|  
|ServerName|43|8|Name des Servers, der das Ereignis erzeugt|  
  
## <a name="file-save-end"></a>File Save End  
  
|**Spaltenname**|**Spalten-ID**|**Spaltentyp**|**Spaltenbeschreibung**|  
|---------------------|-------------------|---------------------|----------------------------|  
|EventClass|0|1|Die Ereignisklasse dient zur Kategorisierung von Ereignissen.|  
|CurrentTime|2|5|Der Zeitpunkt, zu dem das Ereignis begonnen hat (falls verfügbar). Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|StartTime|3|5|Der Zeitpunkt, zu dem das Ereignis begonnen hat (falls verfügbar). Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|EndTime|4|5|Der Zeitpunkt, zu dem das Ereignis beendet wurde. Diese Spalte wird für Startereignisklassen (z. B. SQL:BatchStarting oder SP:Starting) nicht aufgefüllt. Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|Duration|5|2|Die Zeit (in Millisekunden), die für das Ereignis benötigt wurde.|  
|JobID|7|1|Auftrags-ID für den Status.|  
|SessionType|8|8|Sitzungstyp (Entität, die den Vorgang verursacht hat).|  
|IntegerData|10|1|Ganzzahlige Daten.|  
|ObjectID|11|8|Objekt-ID (beachten Sie, dass dies eine Zeichenfolge ist).|  
|ObjectType|12|1|Objekttyp.|  
|ObjectName|13|8|Objektname.|  
|ObjectPath|14|8|Objektpfad. Eine durch Trennzeichen getrennte Liste von übergeordneten Elementen, die beim übergeordneten Element des Objekts beginnt.|  
|Schweregrad|22|1|Schweregrad einer Ausnahme.|  
|Success|23|1|1 = Erfolg 0 = Fehler (z. B. gibt 1 den Erfolg einer Berechtigungsüberprüfung und 0 einen Fehler bei dieser Überprüfung an).|  
|Fehler|24|1|Fehlernummer eines bestimmten Ereignisses.|  
|ConnectionID|25|1|Eindeutige Verbindungs-ID.|  
|DatabaseName|28|8|Name der Datenbank, in der die Anweisung des Benutzers ausgeführt wird.|  
|ClientProcessID|36|1|Die Prozess-ID der Clientanwendung.|  
|SessionID|39|8|Sitzungs-GUID.|  
|TextData|42|9|Dem Ereignis zugeordnete Textdaten.|  
|ServerName|43|8|Name des Servers, der das Ereignis erzeugt.|  
  
## <a name="pageout-begin"></a>PageOut Begin  
  
|**Spaltenname**|**Spalten-ID**|**Spaltentyp**|**Spaltenbeschreibung**|  
|---------------------|-------------------|---------------------|----------------------------|  
|EventClass|0|1|Die Ereignisklasse dient zur Kategorisierung von Ereignissen.|  
|CurrentTime|2|5|Der Zeitpunkt, zu dem das Ereignis begonnen hat (falls verfügbar). Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|StartTime|3|5|Der Zeitpunkt, zu dem das Ereignis begonnen hat (falls verfügbar). Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|JobID|7|1|Auftrags-ID für den Status.|  
|SessionType|8|8|Sitzungstyp (Entität, die den Vorgang verursacht hat).|  
|ObjectID|11|8|Objekt-ID (beachten Sie, dass dies eine Zeichenfolge ist).|  
|ObjectType|12|1|Objekttyp.|  
|ObjectName|13|8|Objektname.|  
|ObjectPath|14|8|Objektpfad. Eine durch Trennzeichen getrennte Liste von übergeordneten Elementen, die beim übergeordneten Element des Objekts beginnt.|  
|ConnectionID|25|1|Eindeutige Verbindungs-ID.|  
|DatabaseName|28|8|Name der Datenbank, in der die Anweisung des Benutzers ausgeführt wird.|  
|ClientProcessID|36|1|Die Prozess-ID der Clientanwendung.|  
|SessionID|39|8|Sitzungs-GUID.|  
|TextData|42|9|Dem Ereignis zugeordnete Textdaten.|  
|ServerName|43|8|Name des Servers, der das Ereignis erzeugt.|  
  
## <a name="pageout-end"></a>PageOut End  
  
|**Spaltenname**|**Spalten-ID**|**Spaltentyp**|**Spaltenbeschreibung**|  
|---------------------|-------------------|---------------------|----------------------------|  
|EventClass|0|1|Die Ereignisklasse dient zur Kategorisierung von Ereignissen.|  
|CurrentTime|2|5|Der Zeitpunkt, zu dem das Ereignis begonnen hat (falls verfügbar). Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|StartTime|3|5|Der Zeitpunkt, zu dem das Ereignis begonnen hat (falls verfügbar). Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|EndTime|4|5|Der Zeitpunkt, zu dem das Ereignis beendet wurde. Diese Spalte wird für Startereignisklassen (z. B. SQL:BatchStarting oder SP:Starting) nicht aufgefüllt. Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|Duration|5|2|Die Zeit (in Millisekunden), die für das Ereignis benötigt wurde.|  
|JobID|7|1|Auftrags-ID für den Status.|  
|SessionType|8|8|Sitzungstyp (Entität, die den Vorgang verursacht hat).|  
|IntegerData|10|1|Ganzzahlige Daten.|  
|ObjectID|11|8|Objekt-ID (beachten Sie, dass dies eine Zeichenfolge ist).|  
|ObjectType|12|1|Objekttyp.|  
|ObjectName|13|8|Objektname.|  
|ObjectPath|14|8|Objektpfad. Eine durch Trennzeichen getrennte Liste von übergeordneten Elementen, die beim übergeordneten Element des Objekts beginnt.|  
|Schweregrad|22|1|Schweregrad einer Ausnahme.|  
|Success|23|1|1 = Erfolg 0 = Fehler (z. B. gibt 1 den Erfolg einer Berechtigungsüberprüfung und 0 einen Fehler bei dieser Überprüfung an).|  
|Fehler|24|1|Fehlernummer eines bestimmten Ereignisses.|  
|ConnectionID|25|1|Eindeutige Verbindungs-ID.|  
|DatabaseName|28|8|Name der Datenbank, in der die Anweisung des Benutzers ausgeführt wird.|  
|ClientProcessID|36|1|Die Prozess-ID der Clientanwendung.|  
|SessionID|39|8|Sitzungs-GUID.|  
|TextData|42|9|Dem Ereignis zugeordnete Textdaten.|  
|ServerName|43|8|Name des Servers, der das Ereignis erzeugt.|  
  
## <a name="pagein-begin"></a>PageIn Begin  
  
|**Spaltenname**|**Spalten-ID**|**Spaltentyp**|**Spaltenbeschreibung**|  
|---------------------|-------------------|---------------------|----------------------------|  
|EventClass|0|1|Die Ereignisklasse dient zur Kategorisierung von Ereignissen.|  
|CurrentTime|2|5|Der Zeitpunkt, zu dem das Ereignis begonnen hat (falls verfügbar). Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|StartTime|3|5|Der Zeitpunkt, zu dem das Ereignis begonnen hat (falls verfügbar). Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|JobID|7|1|Auftrags-ID für den Status.|  
|SessionType|8|8|Sitzungstyp (Entität, die den Vorgang verursacht hat).|  
|ObjectID|11|8|Objekt-ID (beachten Sie, dass dies eine Zeichenfolge ist).|  
|ObjectType|12|1|Objekttyp.|  
|ObjectName|13|8|Objektname.|  
|ObjectPath|14|8|Objektpfad. Eine durch Trennzeichen getrennte Liste von übergeordneten Elementen, die beim übergeordneten Element des Objekts beginnt.|  
|ConnectionID|25|1|Eindeutige Verbindungs-ID.|  
|DatabaseName|28|8|Name der Datenbank, in der die Anweisung des Benutzers ausgeführt wird.|  
|ClientProcessID|36|1|Die Prozess-ID der Clientanwendung.|  
|SessionID|39|8|Sitzungs-GUID.|  
|TextData|42|9|Dem Ereignis zugeordnete Textdaten.|  
|ServerName|43|8|Name des Servers, der das Ereignis erzeugt.|  
  
## <a name="pagein-end"></a>PageIn End  
  
|**Spaltenname**|**Spalten-ID**|**Spaltentyp**|**Spaltenbeschreibung**|  
|---------------------|-------------------|---------------------|----------------------------|  
|EventClass|0|1|Die Ereignisklasse dient zur Kategorisierung von Ereignissen.|  
|CurrentTime|2|5|Der Zeitpunkt, zu dem das Ereignis begonnen hat (falls verfügbar). Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|StartTime|3|5|Der Zeitpunkt, zu dem das Ereignis begonnen hat (falls verfügbar). Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|EndTime|4|5|Der Zeitpunkt, zu dem das Ereignis beendet wurde. Diese Spalte wird für Startereignisklassen (z. B. SQL:BatchStarting oder SP:Starting) nicht aufgefüllt. Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|Duration|5|2|Die Zeit (in Millisekunden), die für das Ereignis benötigt wurde.|  
|JobID|7|1|Auftrags-ID für den Status.|  
|SessionType|8|8|Sitzungstyp (Entität, die den Vorgang verursacht hat).|  
|IntegerData|10|1|Ganzzahlige Daten.|  
|ObjectID|11|8|Objekt-ID (beachten Sie, dass dies eine Zeichenfolge ist).|  
|ObjectType|12|1|Objekttyp.|  
|ObjectName|13|8|Objektname.|  
|ObjectPath|14|8|Objektpfad. Eine durch Trennzeichen getrennte Liste von übergeordneten Elementen, die beim übergeordneten Element des Objekts beginnt.|  
|Schweregrad|22|1|Schweregrad einer Ausnahme.|  
|Success|23|1|1 = Erfolg 0 = Fehler (z. B. gibt 1 den Erfolg einer Berechtigungsüberprüfung und 0 einen Fehler bei dieser Überprüfung an).|  
|Fehler|24|1|Fehlernummer eines bestimmten Ereignisses.|  
|ConnectionID|25|1|Eindeutige Verbindungs-ID.|  
|DatabaseName|28|8|Name der Datenbank, in der die Anweisung des Benutzers ausgeführt wird.|  
|ClientProcessID|36|1|Die Prozess-ID der Clientanwendung.|  
|SessionID|39|8|Sitzungs-GUID.|  
|TextData|42|9|Dem Ereignis zugeordnete Textdaten.|  
|ServerName|43|8|Name des Servers, der das Ereignis erzeugt.|  
  
## <a name="see-also"></a>Siehe auch  
 [Datei laden und speichern – Ereigniskategorie](file-load-and-save-event-category.md)  
  
  