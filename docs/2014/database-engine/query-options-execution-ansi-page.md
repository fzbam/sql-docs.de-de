---
title: Abfrageoptionen, Ausführung (Seite ANSI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql12.swb.query.ansi.f1
ms.assetid: c90d7cdf-3309-46f4-b900-220521bb9552
caps.latest.revision: 23
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: 41c8957ebd2dfb77b13803945c210d6a09f1e874
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36047254"
---
# <a name="query-options-execution-ansi-page"></a>Abfrageausführung (Seite ANSI)
  Mithilfe dieser Seite können Sie festlegen, dass [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] die Abfragen mithilfe aller oder eines Teils der im ISO-Standard (ANSI) angegebenen Einstellungen ausführt.  
  
## <a name="uielement-list"></a>Liste der Benutzeroberflächenelemente  
 **SET ANSI_DEFAULTS**  
 Wählt alle Standard-ISO-Einstellungen aus. Dieses Feld ist standardmäßig nicht verfügbar, weil nur einige der ISO-Einstellungen konfiguriert sind.  
  
 **SET QUOTED_IDENTIFIER**  
 Schließt Objektbezeichner in Anführungszeichen ein. Diese Option ist standardmäßig aktiviert.  
  
 **SET ANSI_NULL_DFLT_ON**  
 Ermöglicht NULL-Werte für alle benutzerdefinierten Datentypen- oder -spalten, die während einer CREATE TABLE- oder ALTER TABLE-Anweisung (Standardstatus) nicht explizit als NOTNULL festgelegt wurden. Diese Option ist standardmäßig aktiviert.  
  
 **SET IMPLICIT_TRANSACTIONS**  
 Diese Option ist standardmäßig nicht aktiviert.  
  
 **SET CURSOR_CLOSE_ON_COMMIT**  
 Schließt automatisch alle offenen Cursors (in Übereinstimmung mit ISO), wenn eine Transaktion durchgeführt wird. Wenn diese Einstellung deaktiviert (auf OFF festgelegt) ist, bleiben Cursor über Transaktionsgrenzen hinweg geöffnet und werden nur geschlossen, wenn die Verbindung geschlossen wird oder die Cursor explizit geschlossen werden. Diese Option ist standardmäßig nicht aktiviert.  
  
 **SET ANSI_PADDING**  
 Steuert das Speichern von Werten in der Spalte, wenn die Werte kürzer als die definierte Spaltengröße sind, und das Speichern von Werten mit nachfolgenden Leerzeichen in **char**-, **varchar**-, **binary**- und **varbinary** -Daten. Diese Einstellung betrifft ausschließlich die Definition neuer Spalten. Nachdem die Spalte erstellt wurde, speichert [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] die Werte gemäß der Einstellung, die beim Erstellen der Spalte festgelegt war. Bestehende Spalten sind von späteren Änderungen dieser Einstellung nicht betroffen. Dieses Kontrollkästchen ist standardmäßig aktiviert.  
  
 **SET ANSI_WARNINGS**  
 Gibt das ISO-Standardverhalten für verschiedene Fehlerbedingungen an:  
  
-   Wenn dieses Kontrollkästchen aktiviert ist, wird eine Warnmeldung erstellt, wenn NULL-Werte in Aggregatfunktionen (z. B. SUM, AVG, MAX, MIN, STDEV, STDEVP, VAR, VARP oder COUNT) auftreten. Bei **OFF**wird keine Warnung ausgegeben.  
  
-   Wenn dieses Kontrollkästchen deaktiviert ist, bewirken Fehler aufgrund einer Division durch null und arithmetische Überlauffehler, dass für die Anweisung ein Rollback ausgeführt und eine Fehlermeldung erstellt wird. Bei OFF bewirken Fehler aufgrund einer Division durch null und arithmetische Überlauffehler, dass NULL-Werte zurückgegeben werden. Das Verhalten, bei dem Fehler aufgrund einer Division durch null oder arithmetische Überlauffehler bewirken, dass NULL-Werte zurückgegeben werden, tritt auf, wenn versucht wird, einen INSERT- oder UPDATE-Vorgang an einer Zeichen-, Unicode- oder Binärspalte auszuführen, wobei die Länge eines neuen Werts die maximale Spaltengröße überschreitet. Wenn **SET ANSI_WARNINGS** auf ON festgelegt ist, wird der INSERT- oder UPDATE-Vorgang gemäß ISO-Standard abgebrochen. Nachfolgende Leerzeichen werden in Zeichenspalten ignoriert, und nachfolgende Nullen werden in Binärspalten ignoriert. Bei OFF werden Daten auf die Spaltengröße abgeschnitten, und die Anweisung wird erfolgreich ausgeführt.  
  
 Diese Option ist standardmäßig aktiviert.  
  
 **SET ANSI_NULLS**  
 Gibt an, dass sich der Gleichheitsoperator (`=`) und der Ungleichheitsoperator (`<>`) bei Verwendung mit NULL-Werten ISO-konform verhalten müssen. Wenn **SET ANSI_NULLS** ausgewählt ist, werden alle Vergleiche mit einem NULL-Wert in Übereinstimmung mit dem Verhalten nach ISO als UNKNOWN ausgewertet. Wenn **SET ANSI_NULLS** nicht ausgewählt ist, werden alle Datenvergleiche mit einem NULL-Wert als TRUE ausgewertet, falls der Datenwert NULL ist. Diese Option ist standardmäßig aktiviert.  
  
 **Standard wiederherstellen**  
 Setzt alle auf dieser Seite verfügbaren Werte auf die ursprünglichen Standardwerte zurück.  
  
  