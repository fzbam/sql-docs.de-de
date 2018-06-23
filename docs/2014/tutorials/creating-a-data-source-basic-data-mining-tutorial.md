---
title: Erstellen einer Datenquelle (Lernprogramm zu Datamining-Lernprogramm) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7107c32-69ed-49a8-9b6e-32753eebf42c
caps.latest.revision: 51
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: b86c10563ffae3073b92373eec5e07c18c1c0668
ms.sourcegitcommit: 8c040e5b4e8c7d37ca295679410770a1af4d2e1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/21/2018
ms.locfileid: "36312588"
---
# <a name="creating-a-data-source-basic-data-mining-tutorial"></a>Erstellen einer Datenquelle (Lernprogramm zu Data Mining-Grundlagen)
  Ein *Datenquelle* ist eine Datenverbindung, die gespeichert und in Ihrem Projekt verwaltet und bereitgestellt werden, um Ihre [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Datenbank. Die Datenquelle umfasst neben anderen erforderlichen Verbindungseigenschaften den Servernamen und den Namen der Datenbank, auf dem sich Ihre Quelldaten befinden.  
  
> [!IMPORTANT]  
>  Der Name der Datenbank lautet [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)]. Wenn Sie diese Datenbank nicht bereits installiert haben, finden Sie auf der Seite [Microsoft SQL Sample Databases](http://go.microsoft.com/fwlink/?LinkId=88417) weitere Informationen.  
  
### <a name="to-create-a-data-source"></a>So erstellen Sie eine Datenquelle  
  
1.  Klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf **Datenquellen** und wählen Sie **Neue Datenquelle**aus.  
  
2.  Klicken Sie auf der Seite **Willkommen** auf **Weiter**.  
  
3.  Auf der **auswählen, wie die Verbindung definiert** auf **neu** eine Verbindung zum Hinzufügen der [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] Datenbank.  
  
4.  Wählen Sie im **Verbindungs-Manager** in der Liste **Anbieter**die Option **Native OLE DB\SQL Server Native Client 11.0**aus.  
  
5.  In der **Servernamen** Feld eingeben oder auswählen den Namen des Servers, auf dem Sie installiert [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].  
  
     Geben Sie beispielsweise **localhost** ein,  wenn die Datenbank auf dem lokalen Server gehostet wird.  
  
6.  Wählen Sie in der Gruppe **Am Server anmelden** die Option **Windows-Authentifizierung verwenden**aus.  
  
    > [!IMPORTANT]  
    >  Die Windows-Authentifizierung sollte wenn immer möglich verwendet werden, da hiermit eine größere Sicherheit als bei der SQL Server-Authentifizierung verbunden ist. Die SQL Server-Authentifizierung wird aus Gründen der Abwärtskompatibilität bereitgestellt. Weitere Informationen zu Authentifizierungsmethoden finden Sie unter [Datenbankmodulkonfiguration - Kontobereitstellung](../../2014/sql-server/install/database-engine-configuration-account-provisioning.md).  
  
7.  In der **einen Datenbanknamen eingeben oder auswählen** wählen [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] , und klicken Sie dann auf **OK**.  
  
8.  Klicken Sie auf **Weiter**.  
  
9. Klicken Sie auf der Seite **Identitätswechselinformationen** auf **Dienstkonto verwenden**und klicken Sie dann auf **Weiter**.  
  
     Hinweis: Auf der Seite **Assistenten abschließen** wird standardmäßig Adventure Works DW 2012 als Name der Datenquelle angegeben.  
  
10. Klicken Sie auf **Fertig stellen**.  
  
     Die neue Datenquelle **Adventure Works DW 2012** wird im Ordner Datenquellen im Projektmappen-Explorer angezeigt.  
  
## <a name="next-task-in-lesson"></a>Nächste Aufgabe in dieser Lektion  
 [Erstellen eine Datenquellensicht &#40;Lernprogramm zu Datamining-Lernprogramm&#41;](../../2014/tutorials/creating-a-data-source-view-basic-data-mining-tutorial.md)  
  
## <a name="previous-task-in-lesson"></a>Vorherige Aufgabe in der Lektion  
 [Erstellen eines Analysis Services-Projekts &#40;Lernprogramm zu Datamining-Lernprogramm&#41;](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen einer Datenquelle (SSAS: mehrdimensional)](../analysis-services/multidimensional-models/create-a-data-source-ssas-multidimensional.md)   
 [Definieren einer Datenquelle](../analysis-services/lesson-1-2-defining-a-data-source.md)   
 [Festlegen von Identitätswechseloptionen &#40;SSAS – mehrdimensional&#41;](../analysis-services/multidimensional-models/set-impersonation-options-ssas-multidimensional.md)  
  
  