---
title: Objektanzahl angeben (Verwendungsbasierte Optimierung-Assistent) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql12.asvs.storagedesignwizard.calculatingobjectcounts.f1
ms.assetid: 306c7c25-ae24-4852-ab8c-c82f68a4bc1f
caps.latest.revision: 25
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: 5a8a027183180cfccc885311218a84a0aa3c8ddd
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36047266"
---
# <a name="specify-object-counts-usage-based-optimization-wizard"></a>Objektanzahl angeben (Assistent für verwendungsbasierte Optimierung)
  Auf der Seite **Objektanzahl angeben** können Sie die Anzahl der Objekte im Cube automatisch berechnen lassen oder die geschätzte Anzahl manuell eingeben. Der Assistent für verwendungsbasierte Optimierung schätzt die Speicheranforderungen anhand der Objektanzahlen.  
  
## <a name="options"></a>Tastatur  
 **Cubeobjekte**  
 Zeigt die Dimensionen und Attribute im Cube an. Nur die Attribute, die nicht ihre `AggregationUsage` Eigenschaftensatz auf keine der **Aggregationsverwendung überprüfen** Seite des Assistenten werden angezeigt, da diese nur für diese Attribute sind, die Anzahl angegeben benötigen.  
  
 **Geschätzte Anzahl**  
 Zeigt die geschätzte Anzahl der Zeilen in der Measuregruppe sowie die geschätzte Anzahl der Attributelemente in den Datenbankdimensionen an. Sie können einen Wert eingeben, der als geschätzte Anzahl verwendet werden soll, oder die Werte für die geschätzte Anzahl berechnen. Geben Sie 0 in das Feld ein, und klicken Sie dann auf **Anzahl**, um die Anzahlwerte zu berechnen. Felder, in denen bereits eine Anzahl angezeigt wird, werden nicht aktualisiert.  
  
 **Partitionsanzahl**  
 (Optional) Geben Sie die geschätzte Anzahl der Zeilen in der Measuregruppe sowie die geschätzte Anzahl der Attributelemente in den Partitionen ein.  
  
 **Count**  
 Berechnet und füllt für alle leeren Felder die Werte in der Spalte **Geschätzte Anzahl** neu. Felder, in denen bereits eine Anzahl angezeigt wird, werden nicht aktualisiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Aggregationsentwurfs-Assistent F1 Hilfe](aggregation-design-wizard-f1-help.md)   
 [Analysis Services-Assistenten &#40;mehrdimensionale Daten&#41;](analysis-services-wizards-multidimensional-data.md)  
  
  