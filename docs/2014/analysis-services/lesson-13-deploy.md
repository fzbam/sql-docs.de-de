---
title: 'Lektion 14: Bereitstellen | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24863a8a-9017-415a-a97b-fbac76ed0675
caps.latest.revision: 19
author: Minewiskan
ms.author: owend
manager: jhubbard
ms.openlocfilehash: 2b9bf4afde77cc0438e097c14f6b3743c7da427d
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36149747"
---
# <a name="lesson-14-deploy"></a>Lektion 14: Bereitstellen
  In dieser Lektion konfigurieren Sie Bereitstellungseigenschaften, wobei Sie eine Bereitstellungsserverinstanz von Analysis Services im Tabellenmodus sowie einen Namen für das bereitgestellte Modell angeben. Sie stellen dann das Modell auf dieser Instanz bereit. Nach der Bereitstellung können Benutzer unter Verwendung einer Clientanwendung zur Berichtserstellung eine Verbindung zum Modell herstellen. Weitere Informationen finden Sie unter [Bereitstellung von Tabellenmodelllösungen &#40;SSAS – tabellarisch&#41;](tabular-models/tabular-model-solution-deployment-ssas-tabular.md).  
  
 Geschätzte Zeit zum Bearbeiten dieser Lektion: **5 Minuten**  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Dieses Thema ist Teil eines Lernprogramms zur Tabellenmodellierung, das in der entsprechenden Reihenfolge bearbeitet werden sollte. Sie sollten vor dem Ausführen der Aufgaben in dieser Lektion die vorherige Lektion abgeschlossen haben: [Lektion 13: Analysieren in Excel](lesson-12-analyze-in-excel.md).  
  
## <a name="deploy-the-model"></a>Bereitstellen des Modells  
  
#### <a name="to-configure-deployment-properties"></a>So konfigurieren Sie Bereitstellungseigenschaften  
  
1.  Klicken Sie in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt für das **Tabellenmodell für die Adventure Works-Internetverkäufe**. Klicken Sie anschließend im Kontextmenü auf **Eigenschaften**.  
  
2.  Klicken Sie im Dialogfeld für die **Eigenschaftenseiten des Tabellenmodells für AW-Internetverkäufe** unter **Bereitstellungsserver**in der Eigenschaft **Server** den Namen einer Analysis Services-Instanz ein, die im Tabellenmodus ausgeführt wird. Dies ist die Instanz, auf der das Modell bereitgestellt wird.  
  
    > [!IMPORTANT]  
    >  Sie benötigen für die Bereitstellung auf einer Analysis Services-Remoteinstanz entsprechende Administratorberechtigungen.  
  
3.  Überprüfen Sie die **Abfragemodus** -Eigenschaftensatz auf **In-Memory-**.  
  
    > [!NOTE]  
    >  Das in diesem Lernprogramm erstellte Modell wird im DirectQuery-Modus nicht unterstützt.  
  
4.  In der **Datenbank** Eigenschaft `Adventure Works Internet Sales Model`.  
  
5.  In der **Cube** Geben Sie Name-Eigenschaft `Adventure Works Internet Sales Model`.  
  
6.  Überprüfen Sie die Auswahl, und klicken Sie anschließend auf **OK**.  
  
#### <a name="to-deploy-the-adventure-works-internet-sales-tabular-model"></a>So stellen Sie das Tabellenmodell für Adventure Works-Internetverkäufe bereit  
  
1.  Klicken Sie in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] auf das Menü **Erstellen** und anschließend auf die **Option zum Bereitstellen des Tabellenmodells für AW-Internetverkäufe**.  
  
     Das Dialogfeld für die Bereitstellung öffnet sich und zeigt den Bereitstellungsstatus der Metadaten sowie jede im Modell enthaltene Tabelle an.  
  
## <a name="conclusion"></a>Fazit  
 Gratulation! Sie haben die Erstellung und Bereitstellung des ersten Analysis Services-Tabellenmodells abgeschlossen. Mit diesem Lernprogramm wurden Sie durch die häufigsten Aufgaben zur Erstellung eines Tabellenmodells geführt. Nach der Bereitstellung des Adventure Works-Internetverkaufsmodells können Sie nun mit SQL Server Management Studio das Modell verwalten und Prozessskripts sowie einen Sicherungsplan erstellen. Benutzer können mithilfe einer Clientanwendung zur Berichtserstellung wie Microsoft Excel oder [!INCLUDE[ssCrescent](../includes/sscrescent-md.md)] eine Verbindung zum Modell herstellen.  
  
## <a name="additional-resources"></a>Zusätzliche Ressourcen  
 Weitere Informationen zu Tabellenmodelleigenschaften, die [!INCLUDE[ssCrescent](../includes/sscrescent-md.md)]-Berichte unterstützen, finden Sie unter [Power View-Berichterstellungseigenschaften &#40;SSAS – tabellarisch&#41;](tabular-models/properties-ssas-tabular.md).  
  
## <a name="see-also"></a>Siehe auch  
 [DirectQuery-Modus &#40;SSAS – tabellarisch&#41;](tabular-models/directquery-mode-ssas-tabular.md)   
 [Konfigurieren von Standarddatenmodellierung und Bereitstellungseigenschaften &#40;SSAS – tabellarisch&#41;](tabular-models/configure-default-data-modeling-and-deployment-properties-ssas-tabular.md)   
 [Tabellarische Modelldatenbanken &#40;SSAS – tabellarisch&#41;](tabular-models/tabular-model-databases-ssas-tabular.md)  
  
  