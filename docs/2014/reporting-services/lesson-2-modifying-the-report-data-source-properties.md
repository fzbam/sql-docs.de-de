---
title: 'Lektion 2: Ändern der Eigenschaften der Berichtsdatenquelle | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c962b0ff-ce8a-4742-8262-dc730901afcf
caps.latest.revision: 40
author: markingmyname
ms.author: maghan
manager: mblythe
ms.openlocfilehash: f2d985681028cf919e1f56d1138863497b931c30
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36162631"
---
# <a name="lesson-2-modifying-the-report-data-source-properties"></a>Lektion 2: Ändern der Eigenschaften der Berichtsdatenquelle
  In dieser Lektion verwenden Sie den Berichts-Manager für die Auswahl eines Berichts, der an Empfänger übermittelt werden soll. Das datengesteuerte Abonnement, das Sie definieren, verteilt den im Tutorial **Erstellen eines einfachen Tabellenberichts &#40;SSRS-Tutorial&#41;** erstellten Bericht [Erstellen eines einfachen Tabellenberichts &#40;SSRS-Tutorial&#41;](../reporting-services/create-a-basic-table-report-ssrs-tutorial.md). In den folgenden Schritten wird erläutert, wie Sie die Datenquellen-Verbindungsinformationen ändern, die vom Bericht zum Abrufen von Daten verwendet werden. Nur Berichte, die **gespeicherte Anmeldeinformationen** für das Zugreifen auf eine Berichtsdatenquelle verwenden, können über ein datengesteuertes Abonnement verteilt werden. Für die unbeaufsichtigte Berichtsverarbeitung sind gespeicherte Anmeldeinformationen erforderlich.  
  
 Sie ändern auch das Dataset und den Bericht, um einen Parameter zu verwenden, mit dem der Bericht nach `[Order]` gefiltert wird, damit das Abonnement verschiedene Instanzen des Berichts für bestimmte Aufträge und Renderingformate ausgeben kann.  
  
 **In diesem Thema:**  
  
-   [So ändern Sie die Datenquelleneigenschaften](#bkmk_modify_datasource)  
  
-   [So ändern Sie den AdventureWorksDataset](#bkmk_modify_dataset)  
  
-   [Fügen Sie einen Berichtsparameter hinzu und veröffentlichen den Bericht erneut](#bkmk_add_reportparameter)  
  
-   [So stellen Sie den Bericht erneut bereit](#bkmk_redeploy)  
  
##  <a name="bkmk_modify_datasource"></a> So ändern Sie die Datenquelleneigenschaften  
  
1.  Starten Sie [Berichts-Manager &#40;SSRS im einheitlichen Modus&#41; ](../../2014/reporting-services/report-manager-ssrs-native-mode.md) mit Administratorrechten aus, z. B. Maustaste auf das Symbol für Internet Explorer, und klicken Sie auf **als Administrator ausführen**.  
  
2.  Navigieren Sie zu dem Ordner, der den Bericht **Sales Orders** enthält, und klicken Sie im Kontextmenü des Berichts auf **Verwalten**.  
  
     ![Öffnen Sie das Kontextmenü für den Bericht, und wählen Sie verwalten](../../2014/tutorials/media/ssrs-tutorial-datadriven-manage-report.gif "öffnen Sie das Kontextmenü für den Bericht, und wählen Sie verwalten")  
  
3.  Klicken Sie auf die Registerkarte **Datenquellen** .  
  
4.  Wählen Sie unter **Verbindungstyp**die Option **Microsoft SQL Server**aus.  
  
5.  Die benutzerdefinierte Datenquellenverbindungszeichenfolge lautet wie folgt (es wird vorausgesetzt, dass sich die Beispieldatenbank auf einem lokalen Datenbankserver befindet):  
  
    ```  
    Data source=localhost; initial catalog=AdventureWorks2012  
    ```  
  
6.  Klicken Sie auf **Anmeldeinformationen, die sicher im Berichtsserver gespeichert sind**.  
  
7.  Geben Sie Ihren Benutzernamen (verwenden Sie das Format *domain\user*) und Ihr Kennwort ein. Wenn Sie nicht über die Berechtigung zum Zugriff auf verfügen die [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] Datenbank, geben Sie eine gültige Anmeldung an.  
  
8.  Aktivieren Sie das Kontrollkästchen **Als Windows-Anmeldeinformationen verwenden, wenn eine Verbindung zur Datenquelle hergestellt wird**, und klicken Sie dann auf **OK**. Wenn Sie kein Domänenkonto verwenden (z. B. bei Verwendung einer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Anmeldenamen), aktivieren Sie dieses Kontrollkästchen nicht.  
  
9. Klicken Sie auf **Verbindung testen** , um sicherzustellen, dass die Verbindung mit der Datenquelle hergestellt werden kann.  
  
10. Klicken Sie auf **Anwenden**.  
  
11. Zeigen Sie den Bericht an, um zu überprüfen, ob er mit den von Ihnen angegebenen Anmeldeinformationen ausgeführt wird. Klicken Sie zum Anzeigen des Berichts auf die Registerkarte **Ansicht** . Beachten Sie, dass nachdem der Bericht geöffnet ist, wählen Sie einen Mitarbeiternamen und klicken Sie dann auf die **View-Bericht** Schaltfläche, um den Bericht anzuzeigen.  
  
##  <a name="bkmk_modify_dataset"></a> So ändern Sie den AdventureWorksDataset  
  
1.  Öffnen Sie in der Sales Orders-Bericht [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]  
  
2.  Klicken Sie mit der rechten Maustaste auf das Dataset `AdventureWorksDataset` und anschließend auf **Dataseteigenschaften**.  
  
3.  Fügen Sie die Anweisung `WHERE (UPPER(SalesOrderNumber) =UPPER(@OrderNumber) or  @OrderNumber IS NULL)` vor der Anweisung `Group By` hinzu. Die vollständige Abfragesyntax lautet wie folgt:  
  
    ```  
    SELECT soh.OrderDate AS Date, soh.SalesOrderNumber AS [Order], pps.Name AS Subcat, pp.Name AS Product, SUM(sd.OrderQty) AS Qty, SUM(sd.LineTotal)  AS LineTotal  
    FROM Sales.SalesPerson AS sp INNER JOIN  
      Sales.SalesOrderHeader AS soh ON sp.BusinessEntityID = soh.SalesPersonID INNER JOIN  
       Sales.SalesOrderDetail AS sd ON sd.SalesOrderID = soh.SalesOrderID INNER JOIN  
       Production.Product AS pp ON sd.ProductID = pp.ProductID  
    INNER JOIN  
       Production.ProductSubcategory AS pps ON pp.ProductSubcategoryID = pps.ProductSubcategoryID   
    INNER JOIN  
        Production.ProductCategory AS ppc ON ppc.ProductCategoryID = pps.ProductCategoryID  
  
    WHERE (UPPER(SalesOrderNumber) =UPPER(@OrderNumber) or  @OrderNumber IS NULL)  
  
    GROUP BY ppc.Name, soh.OrderDate, soh.SalesOrderNumber, pps.Name, pp.Name, soh.SalesPersonID  
    HAVING (ppc.Name = 'Clothing')  
    ```  
  
4.  Klicken Sie auf **OK**.  
  
##  <a name="bkmk_add_reportparameter"></a> Fügen Sie einen Berichtsparameter hinzu und veröffentlichen den Bericht erneut  
  
1.  Klicken Sie im **Berichtsdatenbereich** auf **Neu** und anschließend auf **Parameter...**.  
  
2.  Geben Sie in **Name**den Namen `OrderNumber`ein.  
  
3.  Geben Sie in **Eingabeaufforderung** `OrderNumber`ein.  
  
4.  Wählen Sie **Leeren Wert zulassen ("")** aus.  
  
5.  Wählen Sie **NULL-Wert zulassen**aus.  
  
6.  Klicken Sie auf **OK**. Dem **Berichtsdatenbereich** wird der Parameter hinzugefügt, und er entspricht der folgenden Abbildung:  
  
     ![Der neue Parameter hinzugefügt wird, in den Bereich Berichtsdaten](../../2014/tutorials/media/ssrs-tutorial-datadriven-parameter.gif "berichtsdatenbereich wird der neue Parameter hinzugefügt")  
  
7.  Klicken Sie auf die Registerkarte **Vorschau** , um den Bericht auszuführen. Beachten Sie das Parametereingabefeld am oberen Rand des Berichts. Sie haben folgende Möglichkeiten:  
  
    -   Klicken Sie auf "Bericht anzeigen", um den vollständigen Bericht zu sehen, ohne einen Parameter zu verwenden.  
  
    -   Deaktivieren Sie die Null-Option, und geben Sie eine Auftragsnummer ein, z. B. so71949, um nur die einen Auftrag im Bericht anzuzeigen.  
  
         ![Berichts-Viewer mit sichtbarem Parameterbereich](../../2014/tutorials/media/ssrs-tutorial-datadriven-reportviewer-parameter.gif "Berichts-Viewer mit sichtbarem Parameterbereich")  
  
8.  Stellen Sie den Bericht erneut bereit, damit bei der Abonnementkonfiguration in der nächsten Lektion die in dieser Lektion vorgenommenen Änderungen verwendet werden können. Weitere Informationen zu den Projekteigenschaften, die im Tabellentutorial verwendet werden, finden Sie im Abschnitt „So veröffentlichen Sie den Bericht auf dem Berichtsserver (Optional)“ in [Lektion 6: Hinzufügen von Gruppierungen und Gesamtwerten (Reporting Services)](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).  
  
##  <a name="bkmk_redeploy"></a> So stellen Sie den Bericht erneut bereit  
  
1.  Stellen Sie den Bericht erneut bereit, damit bei der Abonnementkonfiguration in der nächsten Lektion die in dieser Lektion vorgenommenen Änderungen verwendet werden können. Weitere Informationen zu den Projekteigenschaften, die im Tabellentutorial verwendet werden, finden Sie im Abschnitt „So veröffentlichen Sie den Bericht auf dem Berichtsserver (Optional)“ in [Lektion 6: Hinzufügen von Gruppierungen und Gesamtwerten (Reporting Services)](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).  
  
2.  Klicken Sie auf der Symbolleiste auf **Erstellen** , und klicken Sie dann auf **Tutorial bereitstellen**.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Sie haben damit erfolgreich den Bericht so konfiguriert, dass er beim Abrufen von Daten gespeicherte Anmeldeinformationen verwendet. Als Nächstes geben Sie das Abonnement mit den Seiten für datengesteuerte Abonnements im Berichts-Manager an. Siehe [Lektion 3: Definieren eines datengesteuerten Abonnements](../reporting-services/lesson-3-defining-a-data-driven-subscription.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwalten von Berichtsdatenquellen](report-data/manage-report-data-sources.md)   
 [Angeben der Anmeldeinformationen und Verbindungsinformationen für Berichtsdatenquellen](report-data/specify-credential-and-connection-information-for-report-data-sources.md)   
 [Erstellen eines datengesteuerten Abonnements &#40;SSRS-Tutorial&#41;](../reporting-services/create-a-data-driven-subscription-ssrs-tutorial.md)   
 [Erstellen eines einfachen Tabellenberichts &#40;SSRS-Tutorial&#41;](../reporting-services/create-a-basic-table-report-ssrs-tutorial.md)  
  
  