---
title: Volltextindex (Dialogfeld) (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vdt.dlgbox.fulltextindex
ms.assetid: ef45b585-2567-4abe-b421-9fd0994e0146
caps.latest.revision: 15
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: 3c3b8e9d67aa21db8aaef3992f484b10caa64e78
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36057071"
---
# <a name="full-text-index-dialog-box-visual-database-tools"></a>Volltextindex (Dialogfeld) (Visual Database Tools)
  Mit diesem Dialogfeld können Sie einen Volltextindex für Volltextsuchen in textbasierten Spalten von Datenbanktabellen erstellen. Da ein Volltextindex auf einem regulären Index basiert, müssen Sie zuerst einen regulären Index erstellen. Der reguläre Index muss für eine einzelne Nicht-NULL-Spalte erstellt werden. Am besten wählen Sie eine Spalte mit kleinen Werten anstatt einer Spalte mit großen Werten aus.  
  
> [!NOTE]  
>  Bevor Sie einen Volltextindex erstellen können, müssen Sie mithilfe eines externen Tools wie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder Enterprise Manager einen Volltextkatalog für die Datenbank erstellen.  
  
> [!NOTE]  
>  Eine Volltextindex-Funktionalität ist nicht in jeder Edition von [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verfügbar. Eine Liste der Funktionen, die von den Editionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]unterstützt werden, finden Sie unter [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).  
  
## <a name="options"></a>Tastatur  
 **Ausgewählter Volltextindex**  
 Listet vorhandene Volltextindizes auf. Wählen Sie einen Index aus, um seine Eigenschaften im Datenblatt rechts anzuzeigen. Wenn die Liste leer ist, wurden bisher keine Volltextbeziehungen für die Tabelle definiert.  
  
 **Hinzufügen**  
 Erstellen Sie einen neuen Volltextindex.  
  
 **Delete**  
 Löschen Sie den in der Liste **Ausgewählter Volltextindex** ausgewählten Volltextindex.  
  
 **Kategorie Allgemein**  
 Wenn die Kategorie erweitert ist, werden **Spalten** und **Volltextkatalogname**angezeigt.  
  
 **Spalten**  
 Zeigt eine durch Trennzeichen getrennte Liste mit den Namen volltextdurchsuchbarer Spalten an. Um die Liste vollständig anzuzeigen, klicken Sie auf die Schaltfläche mit den Auslassungspunkten (**…**) links neben dem Eigenschaftenfeld.  
  
 **Full-Text Catalog Name**  
 Zeigt den Namen des Volltextkatalogs an, für den dieser Volltextindex gespeichert wird. Um den Index für einen anderen Katalog zu speichern, klicken Sie auf den Katalognamen, und wählen Sie aus der Dropdownliste den gewünschten Katalog aus.  
  
> [!NOTE]  
>  Der Katalog muss vorher in einem externen Tool (z. B. [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder Enterprise Manager) erstellt werden.  
  
 **Kategorie Identität**  
 Wenn die Kategorie erweitert ist, wird das Feld Name für den Index angezeigt.  
  
 **Name**  
 Zeigt den systemspezifischen Namen für diesen Volltextindex an.  
  
 **Kategorie Tabellen-Designer**  
 Wenn die Kategorie erweitert ist, werden Eigenschaften angezeigt, die das Verhalten des Indexes festlegen.  
  
 **Active**  
 Gibt an, ob Sie zurzeit mit diesem Volltextindex eine Volltextsuche ausführen können.  
  
 **Einstellung für das Nachverfolgen von Änderungen**  
 Beschreibt den Status der Änderungsnachverfolgung für den Index: Manuell, Automatisch oder Aus.  
  
 **Die Durchforstung ist abgeschlossen**  
 Zeigt an, ob die zuletzt gestartete Durchforstung abgeschlossen ist. Wenn der Wert dieser Eigenschaft No ist, wird gerade eine Durchforstung ausgeführt.  
  
 **Enddatum und -uhrzeit der aktuellen oder letzten Durchforstung**  
 Zeigt Abschlussdatum und -zeit der letzten Durchforstung an.  
  
 **Fehler in der aktuellen oder letzten Durchforstung**  
 Zeigt die Anzahl der Fehler in der aktuellen oder letzten Durchforstung an.  
  
 **Indexversion**  
 Zeigt die Schemaversion der Tabelle zum Zeitpunkt des Durchforstungsstarts an.  
  
 **Zeilen in der aktuellen oder letzten Durchforstung**  
 Zeigt die Anzahl der aktualisierten Zeilen in der aktuellen oder letzten Durchforstung an.  
  
 **Startdatum und -uhrzeit der aktuellen oder letzten Durchforstung**  
 Zeigt Startdatum und -zeit der aktuellen oder letzten Durchforstung an.  
  
 **Timestamp für nächste Durchforstung**  
 Zeigt Datum und Zeit des nächsten Durchforstungsstarts an.  
  
 **Typ der aktuellen oder letzten Durchforstung**  
 Zeigt den Typ der aktuellen oder letzten Durchforstung an: Vollständig, Inkrementell, Aktualisieren oder Automatische Propagierung.  
  
 **Eindeutiger Indexname**  
 Zeigt eine Liste der Namen aller Spalten in dieser Datenbank an, die einen eindeutigen, einspaltigen Index haben. Diese Spalten können verwendet werden, um einen Volltextindex zu erstellen.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden Sie den Volltextindizierungs-Assistenten](../../relational-databases/search/use-the-full-text-indexing-wizard.md)   
 [CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql)  
  
  