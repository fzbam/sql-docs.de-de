---
title: Batchverarbeitung (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batches [Analysis Services]
ms.assetid: ba4dcf72-0667-41d0-816b-ab8ff9a7d9cb
caps.latest.revision: 38
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: 66cc1d67c589d1794e2beabb03b680e1b1015254
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36059254"
---
# <a name="batch-processing-analysis-services"></a>Batchverarbeitung (Analysis Services)
  In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]können Sie den Batch-Befehl verwenden, um mehrere Verarbeitungsbefehle in einer einzelnen Anforderung an den Server zu senden. Bei der Batchverarbeitung können Sie steuern, welche Objekte verarbeitet werden sollen und in welcher Reihenfolge dies geschehen soll. Außerdem kann ein Batch als eine Reihe von eigenständigen Aufträgen ausgeführt werden oder als Transaktion, in der ein Fehler bei einem Vorgang ein Rollback der Änderungen des gesamten Batches zur Folge hat.  
  
 Die Batchverarbeitung gewährleistet eine maximale Datenverfügbarkeit, da sich die Zeit, die zum Ausführen von Commits für Änderungen benötigt wird, verringert. Wenn Sie eine vollständige Verarbeitung einer Dimension vornehmen, werden Partitionen, die diese Dimension verwenden, als nicht verarbeitet markiert. Infolgedessen sind Cubes, die die nicht verarbeiteten Partitionen verwenden, nicht zum Durchsuchen verfügbar. Mit einem Batchverarbeitungsauftrag können Sie dieses Problem beheben, indem Sie die Dimensionen zusammen mit den betroffenen Partitionen verarbeiten. Indem Sie den Batchverarbeitungsauftrag als Transaktion ausführen, stellen Sie sicher, dass alle in der Transaktion enthaltenen Objekte für Abfragen verfügbar bleiben, bis die Verarbeitung abgeschlossen ist. Während die Transaktion das Commit für die Änderungen durchführt, werden die betroffenen Objekte gesperrt und sind daher vorübergehend nicht verfügbar. Die Zeit, die insgesamt zum Ausführen des Commits für die Änderungen benötigt wird, liegt jedoch unter der Zeit, die zum Verarbeiten jedes einzelnen Objekts benötigt würde.  
  
 Die Verfahren in diesem Thema zeigen die Schritte, die zur vollständigen Verarbeitung von Dimensionen und Partitionen erforderlich sind. Für die Batchverarbeitung sind auch andere Verarbeitungsoptionen verfügbar, wie z. B. die inkrementelle Verarbeitung. Damit diese Verfahren ordnungsgemäß ausgeführt werden können, sollten Sie eine [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank verwenden, die mindestens zwei Dimensionen und eine Partition enthält.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
 [Batchverarbeitung in SQL Server Data Tools](#bkmk_ssdt)  
  
 [Batchverarbeitung mithilfe von XMLA in Management Studio](#bkmk_xmla)  
  
##  <a name="bkmk_ssdt"></a> Batchverarbeitung in SQL Server Data Tools  
 Bevor Objekte in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]verarbeitet werden können, muss das Projekt, in dem sie enthalten sind, bereitgestellt werden. Weitere Informationen finden Sie unter [Bereitstellen von Analysis Services-Projekten &#40;SSDT&#41;](deploy-analysis-services-projects-ssdt.md).  
  
1.  Öffnen Sie [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].  
  
2.  Öffnen Sie ein Projekt, das bereits bereitgestellt ist.  
  
3.  Erweitern Sie im Projektmappen-Explorer den Ordner **Dimensionen** unter dem bereitgestellten Projekt.  
  
4.  Halten Sie die STRG-Taste gedrückt, und klicken Sie auf jede der Dimensionen im Ordner **Dimensionen** .  
  
5.  Klicken Sie mit der rechten Maustaste auf die ausgewählten Dimensionen, und klicken Sie dann auf **Verarbeiten**.  
  
6.  Halten Sie die STRG-Taste gedrückt, und klicken Sie auf jede der in der Liste **Objektliste**aufgeführten Dimensionen.  
  
7.  Klicken Sie mit der rechten Maustaste auf die ausgewählten Dimensionen, und wählen Sie **Vollständig verarbeiten**aus.  
  
8.  Klicken Sie auf **Einstellungen ändern**, um den Batchverarbeitungsauftrag anzupassen.  
  
9. Wählen Sie unter **Verarbeitungsoptionen**die folgenden Einstellungen aus:  
  
    -   Legen Sie für**Verarbeitungsreihenfolge** die Option **Sequenziell**und für **Transaktionsmodus** die Option **Eine Transaktion**fest.  
  
    -   Legen Sie für**Rückschreibetabellenoption** die Option **Vorhandene verwenden**fest.  
  
    -   Aktivieren Sie unter **Betroffene Objekte**das Kontrollkästchen **Betroffene Objekte verarbeiten** .  
  
10. Klicken Sie auf die Registerkarte **Dimensionsschlüsselfehler** . Überprüfen Sie, ob **Standardfehlerkonfiguration verwenden** ausgewählt ist.  
  
11. Klicken Sie auf **OK** , um das Fenster **Einstellungen ändern** zu schließen.  
  
12. Klicken Sie im Fenster **Objekte verarbeiten** auf **Ausführen** , um mit dem Verarbeitungsauftrag zu beginnen.  
  
13. Klicken Sie auf **Schließen** , sobald das Meldungsfeld **Status**die Meldung **Die Verarbeitung wurde erfolgreich ausgeführt**anzeigt.  
  
14. Klicken Sie im Fenster **Objekte verarbeiten** auf **Schließen** .  
  
##  <a name="bkmk_xmla"></a> Batchverarbeitung mithilfe von XMLA in Management Studio  
 Sie können ein XMLA-Skript erstellen, das Batchverarbeitung ausführt. Starten Sie, indem Sie in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] für jedes Objekt ein XMLA-Skript generieren, und kombinieren Sie sie dann in eine einzelne XMLA-Abfrage, die Sie interaktiv oder in einem geplanten Task ausführen.  
  
 Schrittanleitungen finden Sie unter **Beispiel 2** in [Planen von administrativen Tasks in SSAS mithilfe von SQL Server-Agent](../instances/schedule-ssas-administrative-tasks-with-sql-server-agent.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verarbeitung von mehrdimensionalen Modellobjekten](processing-a-multidimensional-model-analysis-services.md)  
  
  