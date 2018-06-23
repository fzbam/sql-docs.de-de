---
title: Neu bezeichnen (SQL Server Data Mining-Add-ins) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data preparation
- relabel
- data cleaning
ms.assetid: af041b39-fdd1-4cb5-a5ef-2f3ddab84614
caps.latest.revision: 14
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: 50dd1a2c4cd425243c55ef9181387a08c5d935ba
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36151450"
---
# <a name="relabel-sql-server-data-mining-add-ins"></a>Neu bezeichnen (SQL Server Data Mining-Add-Ins)
  ![Office 13-Symbol für das Tool neu bezeichnen](media/dm13-relabel.gif "Office 13-Symbol für Tool neu bezeichnen")  
  
 Im Data Mining-Client für Excel können Sie neue Bezeichnungen für Ihre Daten erstellen, um die Ergebnisse der Analyse übersichtlicher zu gestalten.  
  
 Gründe für das Neubezeichnen umfassen:  
  
-   Die Daten enthalten codierte Ergebnisse, wie 1 für Männlich und 2 für Weiblich.  
  
-   Sie gruppieren numerische Werte und möchten den Bereichen einen aussagekräftigen Namen geben.  
  
-   Sie möchten lange Namen vereinfachen.  
  
## <a name="using-the-relabel-wizard"></a>Verwenden des Assistenten zum Neubezeichnen  
  
1.  In der **Data Mining** des Menübands, klicken Sie auf **Bereinigen** und wählen Sie dann **neu bezeichnen**.  
  
2.  Wählen Sie die Tabelle oder den Datenbereich mit den zu bereinigenden Daten aus.  
  
3.  In der **neu bezeichnen** Seite des Assistenten wählen Sie eine einzelne Spalte, durch die Spalte aus der Dropdownliste auswählen oder indem Sie auf die Spalte in der **Datenstichproben** Bereich.  
  
     Die **Datenstichproben** Bereich zeigt nur etwa 50 Datenzeilen, aber um sicherzustellen, dass Sie sehen, dass eine hinreichenden Spannweite von Werten als Stichprobe verwendet.  
  
     Klicken Sie auf die Spaltenüberschrift für **Anzahl** um nach der Anzahl der einzelnen Werte zu sortieren.  
  
     Sie können auch sortieren, indem **ursprüngliche Bezeichnungen**, dies ist hilfreich, wenn Sie zunächst alle höchsten oder niedrigsten Werte neu bezeichnen möchten.  
  
4.  In der **neu bezeichnen** Datenseite des Assistenten, überprüfen Sie die Werte in der **ursprüngliche Bezeichnungen** Spalte, und entscheiden, wie die gruppiert oder bearbeitet werden sollen.  
  
5.  Geben Sie einen neuen Wert in der Zeile unter **neue Bezeichnungen**. Sie können auch einen Wert aus der Liste der vorhandenen Werte auswählen. Bei der Eingabe neuer Werte werden diese sofort für die Wiederverwendung verfügbar.  
  
6.  Wenn Sie genügend Zeilen eingegeben haben, klicken Sie auf **Weiter**, und klicken Sie auf die **Ziel auswählen** Seite, und wählen Sie in dem Sie die neu bezeichneten Daten speichern müssen.  
  
    -   **Dem aktuellen Arbeitsblatt als neue Spalte hinzuzufügen**  
  
         Klicken Sie auf diese Option, um der Tabelle eine neue Spalte mit den neuen Werten hinzuzufügen.  
  
    -   **Kopieren Sie Blattdaten mit Änderungen in ein neues Arbeitsblatt**  
  
         Klicken Sie auf diese Option, um ein neues Arbeitsblatt mit den aktualisierten Daten zu erstellen.  
  
    -   **Daten direkt ändern**  
  
         Klicken Sie auf diese Option, um die ursprünglichen Daten durch die neuen Werte zu ersetzen.  
  
## <a name="see-also"></a>Siehe auch  
 [Durchsuchen und Bereinigen von Daten](exploring-and-cleaning-data.md)  
  
  