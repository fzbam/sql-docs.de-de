---
title: CHECK-Einschränkung (Dialogfeld) (Visual Database Tools) | Microsoft-Dokumentation
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
- vdt.dlgbox.checkconstraint
ms.assetid: ad0bbf7f-b0de-406a-bd0a-cb779816b101
caps.latest.revision: 17
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a3dc13f77788f46796c274d43d5dea920167033f
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36058419"
---
# <a name="check-constraint-dialog-box-visual-database-tools"></a>CHECK-Einschränkung (Dialogfeld) (Visual Database Tools)
  Dieses Dialogfeld wird angezeigt, wenn Sie im Tabellen-Designer mit der rechten Maustaste auf ein Tabellendefinitions-Datenblatt klicken und auf **Einschränkungen überprüfen**klicken. Dieses Dialogfeld enthält eine Reihe von Eigenschaften für Einschränkungen (außer für Unique-Einschränkungen), die den Tabellen in der Datenbank zugeordnet sind. Eigenschaften für Unique-Einschränkungen werden im Dialogfeld **Indizes/Schlüssel** angezeigt.  
  
> [!NOTE]  
>  Wenn die Tabelle zur Replikation veröffentlicht ist, müssen Sie mit der Transact-SQL-Anweisung [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) oder mit SMO (SQL Server Management Objects) Schemaänderungen ausführen. Wenn die Schemaänderungen mit dem Tabellen-Designer oder dem Datenbankdiagramm-Designer ausgeführt werden, wird versucht, die Tabelle zu entfernen und erneut zu erstellen. Da veröffentlichte Objekte nicht gelöscht werden können, schlägt die Schemaänderung fehl.  
  
## <a name="options"></a>Tastatur  
 **Ausgewählte CHECK-Einschränkungen**  
 Listet verfügbare CHECK-Einschränkungen auf. Um die Eigenschaften einer Einschränkung anzuzeigen, wählen Sie sie in der Liste aus.  
  
 **Hinzufügen**  
 Erstellt eine neue Einschränkung für die ausgewählte Datenbanktabelle und stellt den Standardnamen sowie weitere Werte für die Einschränkung zur Verfügung. Die Einschränkung wird erst dann gültig, wenn ein Ausdruck für die Einschränkung eingegeben wird.  
  
 **Delete**  
 Entfernt die ausgewählte Einschränkung aus der Tabelle. Verwenden Sie diese Schaltfläche zum Entfernen der Einschränkung, um das Hinzufügen einer CHECK-Einschränkung abzubrechen.  
  
 **Kategorie Allgemein**  
 Wenn die Kategorie erweitert ist, wird das Eigenschaftenfeld **Ausdruck** angezeigt.  
  
 **Ausdruck**  
 Zeigt den Ausdruck für die ausgewählte CHECK-Einschränkung an. Bei neuen Einschränkungen müssen Sie den Ausdruck vor dem Verlassen dieses Felds eingeben. Sie können auch vorhandene CHECK-Einschränkungen bearbeiten. Weitere Informationen finden Sie unter [Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md).  
  
 **Kategorie Identität**  
 Wenn die Kategorie erweitert ist, wird die Eigenschaften für **Name** und **Beschreibung**angezeigt.  
  
 **Name**  
 Zeigt den Namen der ausgewählten CHECK-Einschränkung an. Um den Namen dieser Einschränkung zu ändern, geben Sie den Text direkt in das Eigenschaftenfeld ein.  
  
 **Beschreibung**  
 Beschreibt die CHECK-Einschränkung. Sie können die Beschreibung bearbeiten, indem Sie Änderungen in das Eigenschaftenfeld eingeben. Alternativ können Sie rechts neben dem Eigenschaftenfeld auf die Auslassungspunkte (**…**) klicken und die Beschreibung im Dialogfeld **Description-Eigenschaft** bearbeiten.  
  
 **Kategorie Tabellen-Designer**  
 Wenn die Kategorie erweitert ist, werden Eigenschaften für **Vorhandene Daten bei Erstellung oder Reaktivierung überprüfen**, **Für INSERTs und UPDATEs erzwingen**und **Für Replikation erzwingen**angezeigt.  
  
 **Check Existing Data On Creation or Re-Enabling**  
 Gibt an, ob alle vorhandenen Daten (Daten, die vor Erstellen der Einschränkung in der Tabelle vorhanden sind) mit der Einschränkung überprüft werden.  
  
 **Für INSERTs und UPDATEs erzwingen**  
 Gibt an, ob die Einschränkung erzwungen wird, wenn die Daten in die Tabelle eingefügt oder in der Tabelle aktualisiert werden.  
  
 **Für Replikation erzwingen**  
 Gibt an, ob die Einschränkung erzwungen wird, wenn durch einen Replikations-Agent in der Tabelle ein INSERT oder ein UPDATE ausgeführt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Unique- und Check-Einschränkungen](../../relational-databases/tables/unique-constraints-and-check-constraints.md)   
 [Indizes und Schlüssel im Dialogfeld &#40;Visual Database Tools&#41;](visual-database-tools.md)  
  
  