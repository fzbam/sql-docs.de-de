---
title: Ändern der Zeilenhöhe oder der Spaltenbreite (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f061c204-5cd5-4467-9a9c-8a12803d93ba
caps.latest.revision: 8
author: douglaslM
ms.author: douglasl
manager: mblythe
ms.openlocfilehash: 5d56262f6ea03782f3e739b4b81d4070b9987f74
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36149337"
---
# <a name="change-row-height-or-column-width-report-builder-and-ssrs"></a>Ändern der Zeilenhöhe oder der Spaltenbreite (Berichts-Generator und SSRS)
  Wenn Sie eine Zeilenhöhe festlegen, legen Sie damit die maximale Höhe der Zeile im gerenderten Bericht fest. Textfelder in einer Zeile passen sich jedoch zur Laufzeit automatisch vertikal an die darin enthaltenen Daten an. Dies kann dazu führen, dass eine Zeile über die festgelegte Höhe hinausgeht. Wenn Sie eine feste Zeilenhöhe definieren möchten, müssen Sie die Textfeldeigenschaften so ändern, dass sich die Zeile nicht automatisch ausdehnt.  
  
 Wenn Sie eine Spaltenbreite festlegen, legen Sie damit die maximale Breite der Spalte im gerenderten Bericht fest. Spalten passen sich nicht automatisch horizontal an den darin enthaltenen Text an.  
  
 Falls eine Zelle in einer Zeile oder Spalte ein Rechteck oder einen Datenbereich enthält, werden die Mindesthöhe und -breite der Zelle durch die Höhe und Breite des darin enthaltenen Elements bestimmt. Weitere Informationen finden Sie unter [Renderingverhalten &#40;Berichts-Generator und SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-row-height-by-moving-row-handles"></a>So ändern Sie die Zeilenhöhe durch das Bewegen von Zeilenhandles  
  
1.  Klicken Sie in der Entwurfsansicht auf eine Stelle im Tablix-Datenbereich, um diesen auszuwählen. Graue Zeilenziehpunkte werden am Außenrand des Tablix-Datenbereichs angezeigt.  
  
2.  Zeigen Sie mit der Maus auf die Ziehpunktkante der Zeile, die Sie erweitern möchten. Es wird ein Pfeil mit zwei Spitzen angezeigt.  
  
3.  Klicken Sie mit der Maus, und ziehen Sie die Kante der Zeile nach oben oder unten, um die Zeilenhöhe zu ändern.  
  
### <a name="to-change-row-height-by-setting-cell-properties"></a>So ändern Sie die Zeilenhöhe durch das Festlegen von Zelleneigenschaften  
  
1.  Klicken Sie in der Ansicht Entwurf auf eine Zelle in der Tabellenzeile.  
  
     ![Ausgewählte Zelle in einer Tabelle](../media/table-selectcell.png "Selected Cell in a Table")  
  
2.  Ändern Sie im angezeigten Bereich **Eigenschaften** die Eigenschaft **Höhe** , und klicken Sie anschließend auf eine beliebige Stelle außerhalb des Bereichs **Eigenschaften** .  
  
     ![Eigenschaftenbereich für ausgewählte Tabellenzelle](../media/cell-propertiespane.png "Properties Pane for selected table cell")  
  
### <a name="to-prevent-a-row-from-automatically-expanding-vertically"></a>So deaktivieren Sie die automatische Ausdehnung einer Zeile  
  
1.  Klicken Sie in der Entwurfsansicht auf eine Stelle im Tablix-Datenbereich, um diesen auszuwählen. Graue Zeilenziehpunkte werden am Außenrand des Tablix-Datenbereichs angezeigt.  
  
2.  Klicken Sie auf den Zeilenziehpunkt, um die Zeile auszuwählen.  
  
3.  Legen Sie im Eigenschaftenbereich CanGrow auf **FALSE**fest.  
  
    > [!NOTE]  
    >  Falls der Eigenschaftenbereich noch nicht angezeigt wird, klicken Sie im Menü **Ansicht** auf **Eigenschaften**.  
  
### <a name="to-change-column-width"></a>So ändern Sie die Spaltenbreite  
  
1.  Klicken Sie in der Entwurfsansicht auf eine Stelle im Tablix-Datenbereich, um diesen auszuwählen. Graue Spaltenziehpunkte werden am Außenrand des Tablix-Datenbereichs angezeigt.  
  
2.  Zeigen Sie mit der Maus auf die Ziehpunktkante der Spalte, die Sie erweitern möchten. Es wird ein Pfeil mit zwei Spitzen angezeigt.  
  
3.  Klicken Sie mit der Maus, und ziehen Sie die Kante der Spalte nach links oder rechts, um die Spaltenbreite zu ändern.  
  
## <a name="see-also"></a>Siehe auch  
 [Tablix-Datenbereich &#40;Berichts-Generator und SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md)   
 [Tablix-Datenbereichszelle, Zeilen und Spalten &#40;Berichts-Generator&#41; und SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md)   
 [Tabellen (Berichts-Generator und SSRS)](tables-report-builder-and-ssrs.md)   
 [Matrizen (Berichts-Generator und SSRS)](create-a-matrix-report-builder-and-ssrs.md)   
 [Listen (Berichts-Generator und SSRS)](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md)   
 [Tabellen, Matrizen und Listen &#40;Berichts-Generator und SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  