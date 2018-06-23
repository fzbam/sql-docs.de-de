---
title: 'Lektion 1: Erstellen einer Beispiel-Abonnentendatenbank | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 47a882b7-efe5-4ee6-bef4-06118eb56903
caps.latest.revision: 41
author: markingmyname
ms.author: maghan
manager: mblythe
ms.openlocfilehash: c1b01246166c6d7e75f1083fc23b9bd15502c731
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36049640"
---
# <a name="lesson-1-creating-a-sample-subscriber-database"></a>Lektion 1: Erstellen einer Beispiel-Abonnentendatenbank
  Ein datengesteuertes Abonnement können Sie nur dann definieren, wenn Sie über eine Datenquelle verfügen, die Abonnementdaten bereitstellt. In diesem Schritt erstellen Sie eine kleine Datenbank zum Speichern der Abonnementdaten, die in diesem Lernprogramm verwendet werden. Wenn dann später das Abonnement verarbeitet wird, werden diese Daten vom Berichtsserver abgerufen und verwendet, um die Berichtsausgabe, Übermittlungsoptionen und das Berichtspräsentationsformat benutzerspezifisch anzupassen.  
  
 Diese Lektion wird vorausgesetzt, Sie verwenden [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] zum Erstellen einer [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Datenbank.  
  
### <a name="to-create-a-sample-subscriber-database"></a>So erstellen Sie eine Beispiel-Abonnentendatenbank  
  
1.  Starten Sie [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], und stellen Sie eine Verbindung mit einer [!INCLUDE[ssDE](../includes/ssde-md.md)] her.  
  
2.  Klicken Sie mit der rechten Maustaste auf „Datenbanken“, und wählen Sie **Neue Datenbank...** aus.  
  
3.  Geben Sie im Dialogfeld neue Datenbank Datenbankname *Abonnenten*. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
4.  Klicken Sie auf der Symbolleiste auf die Schaltfläche **Neue Abfrage** .  
  
5.  Kopieren Sie die folgenden [!INCLUDE[tsql](../includes/tsql-md.md)] -Anweisungen in die leere Abfrage:  
  
    ```  
    Use Subscribers  
    CREATE TABLE [dbo].[OrderInfo] (  
        [SubscriptionID] [int] NOT NULL PRIMARY KEY ,  
        [Order] [nvarchar] (20) NOT NULL,  
        [FileType] [bit],  
        [Format] [nvarchar] (20) NOT NULL ,  
    ) ON [PRIMARY]  
    GO  
  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('1', 'so43659', '1', 'IMAGE')  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('2', 'so43664', '1', 'MHTML')  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('3', 'so43668', '1', 'PDF')  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('4', 'so71949', '1', 'Excel')  
    GO  
    ```  
  
6.  Klicken Sie auf **! Führen Sie**  in der Symbolleiste aus.  
  
7.  Verwenden Sie eine SELECT-Anweisung, um sicherzustellen, dass drei Datenzeilen vorhanden sind. Beispiel: `select * from OrderInfo`  
  
## <a name="next-steps"></a>Nächste Schritte  
 Sie haben erfolgreich die Abonnementdaten erstellt, welche die Berichtsverteilung steuern und über die die Berichtsausgabe für jeden Abonnenten angepasst werden kann. Nun ändern Sie noch die Datenquelleneigenschaften des Berichts, den Sie an die Abonnenten verteilen. Die Datenquelleneigenschaften werden geändert, um den Bericht auf die Übermittlung als datengesteuertes Abonnement vorzubereiten. Sie ändern auch den Berichtsentwurf, um einen Parameter einzuschließen, den das Abonnement mit den Abonnentendaten verwendet. [Lektion 2: Ändern der Eigenschaften der Berichtsdatenquelle](lesson-2-modifying-the-report-data-source-properties.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen eines datengesteuerten Abonnements &#40;SSRS-Tutorial&#41;](create-a-data-driven-subscription-ssrs-tutorial.md)   
 [Erstellen Sie eine Datenbank](../relational-databases/databases/create-a-database.md)   
 [Erstellen ein einfachen Tabellenberichts &#40;SSRS-Lernprogramm&#41;](create-a-basic-table-report-ssrs-tutorial.md)  
  
  