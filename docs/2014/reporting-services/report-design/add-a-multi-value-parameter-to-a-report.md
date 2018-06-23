---
title: Hinzufügen eines aus mehreren Werten bestehenden Parameters zu einem Bericht | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 12ad0e77-4c28-4bbb-ab11-473ae89ec9f1
caps.latest.revision: 6
author: douglaslM
ms.author: douglasl
manager: mblythe
ms.openlocfilehash: 4f376b2ba1e707afdba55b6fc7443d9d8be257e3
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36047099"
---
# <a name="add-a-multi-value-parameter-to-a-report"></a>Hinzufügen eines aus mehreren Werten bestehenden Parameters zu einem Bericht
  Sie können einem Bericht einen Parameter hinzufügen, der dem Benutzer die Auswahl mehrerer Werte für den Parameter ermöglicht.  
  
 Sie können mehrere Parameterwerte innerhalb der Berichts-URL an den Bericht übergeben. Ein Beispiel für die URL einen mehrwertigen Parameter enthält, finden Sie unter [einen Bericht innerhalb einer URL übergeben](../pass-a-report-parameter-within-a-url.md).  
  
 Informationen dazu, wie mehrere Parameterwerte an eine gespeicherte Prozedur übergeben werden, finden Sie unter [Verwenden von Mehrfachauswahl-Parametern für SSRS-Berichte](http://go.microsoft.com/fwlink/?LinkId=321529) auf mssqltips.com.  
  
### <a name="to-add-a-multi-value-parameter"></a>So fügen Sie einen aus mehreren Werten bestehenden Parameter hinzu  
  
1.  Öffnen Sie im Berichts-Generator den Bericht, dem Sie den aus mehreren Werten bestehenden Parameter hinzufügen möchten.  
  
2.  Klicken Sie mit der rechten Maustaste auf das Berichtsdataset, und klicken Sie dann auf **Dataseteigenschaften**.  
  
3.  Fügen Sie der Datasetabfrage eine Variable hinzu, indem Sie entweder den Abfragetext im Feld **Abfrage** bearbeiten oder im Abfrage-Designer einen Filter hinzufügen. Weitere Informationen finden Sie unter [Erstellen einer Abfrage im Relationalen Abfrage-Designer (Berichts-Generator und SSRS)](../report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).  
  
    > [!IMPORTANT]  
    >  Der Abfragetext darf keine DECLARE-Anweisung für die Abfragevariable enthalten.  
  
    > [!IMPORTANT]  
    >  Der Text für die Abfragevariable muss den `IN`-Operator enthalten, wie im folgenden Beispiel veranschaulicht.  
  
    ```  
    WHERE  
      Production.ProductInventory.ProductID IN (@ProductID)  
    ```  
  
    > [!IMPORTANT]  
    >  Wenn Sie die Variable nicht wie oben dargestellt in Klammern einschließen, wird der Bericht nicht gerendert und der Fehler "Die Skalarvariable muss deklariert werden" angezeigt.  
  
     Für die Abfragevariable wird automatisch ein Datasetparameter für ein eingebettetes Dataset oder ein freigegebenes Dataset erstellt. Für den Datasetparameter wird automatisch ein Berichtsparameter erstellt.  
  
4.  Erweitern Sie im Bereich **Berichtsdaten** den Knoten **Parameter** , klicken Sie mit der rechten Maustaste auf den Berichtsparameter, der automatisch für den Datasetparameter erstellt wurde, und klicken Sie anschließend auf **Parametereigenschaften**.  
  
5.  Wählen Sie auf der Registerkarte **Allgemein** die Option **Mehrere Werte zulassen** aus, um anzugeben, dass für den Parameter mehr als ein Wert ausgewählt werden darf.  
  
6.  (Optional) Geben Sie auf der Registerkarte **Verfügbare Werte** eine Liste mit verfügbaren Werten an, die dem Benutzer angezeigt werden soll.  
  
     Eine Liste verfügbarer Werte schränkt die Auswahl, die ein Benutzer treffen kann, auf die gültigen Werte für den Parameter ein. Bei mehreren Werten beginnt die Liste mit der Funktion **Alles auswählen** , sodass der Benutzer alle Werte mit einem einzigen Mausklick auswählen oder löschen kann. Wenn Sie die für den Berichtsparameter verfügbaren Werte mit einer Datasetabfrage abrufen möchten, achten Sie darauf, kein Dataset auszuwählen, das die demselben Berichtsparameter zugeordnete Abfragevariable enthält.  
  
     Weitere Informationen finden Sie unter [Hinzufügen, Ändern oder Löschen von verfügbaren Werten für einen Berichtsparameter (Berichts-Generator und SSRS)](add-change-or-delete-available-values-for-a-report-parameter.md).  
  
### <a name="to-add-a-multi-value-parameter"></a>So fügen Sie einen aus mehreren Werten bestehenden Parameter hinzu  
  
1.  Öffnen Sie im Berichts-Generator den Bericht, dem Sie den aus mehreren Werten bestehenden Parameter hinzufügen möchten.  
  
2.  Klicken Sie mit der rechten Maustaste auf das Berichtsdataset, und klicken Sie dann auf **Dataseteigenschaften**.  
  
3.  Fügen Sie der Datasetabfrage eine Variable hinzu, indem Sie entweder den Abfragetext im Feld **Abfrage** bearbeiten oder im Abfrage-Designer einen Filter hinzufügen. Weitere Informationen finden Sie unter [Erstellen einer Abfrage im Relationalen Abfrage-Designer (Berichts-Generator und SSRS)](../report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).  
  
    > [!IMPORTANT]  
    >  Der Abfragetext darf keine DECLARE-Anweisung für die Abfragevariable enthalten.  
  
    > [!IMPORTANT]  
    >  Der Text für die Abfragevariable muss den `IN`-Operator enthalten, wie im folgenden Beispiel veranschaulicht.  
  
    ```  
    WHERE  
      Production.ProductInventory.ProductID IN (@ProductID)  
    ```  
  
    > [!IMPORTANT]  
    >  Wenn Sie die Variable nicht wie oben dargestellt in Klammern einschließen, wird der Bericht nicht gerendert und der Fehler "Die Skalarvariable muss deklariert werden" angezeigt.  
  
     Für die Abfragevariable wird automatisch ein Datasetparameter für ein eingebettetes Dataset oder ein freigegebenes Dataset erstellt. Für den Datasetparameter wird automatisch ein Berichtsparameter erstellt.  
  
4.  Erweitern Sie im Bereich **Berichtsdaten** den Knoten **Parameter** , klicken Sie mit der rechten Maustaste auf den Berichtsparameter, der automatisch für den Datasetparameter erstellt wurde, und klicken Sie anschließend auf **Parametereigenschaften**.  
  
5.  Wählen Sie auf der Registerkarte **Allgemein** die Option **Mehrere Werte zulassen** aus, um anzugeben, dass für den Parameter mehr als ein Wert ausgewählt werden darf.  
  
6.  (Optional) Geben Sie auf der Registerkarte **Verfügbare Werte** eine Liste mit verfügbaren Werten an, die dem Benutzer angezeigt werden soll.  
  
     Eine Liste verfügbarer Werte schränkt die Auswahl, die ein Benutzer treffen kann, auf die gültigen Werte für den Parameter ein. Bei mehreren Werten beginnt die Liste mit der Funktion **Alles auswählen** , sodass der Benutzer alle Werte mit einem einzigen Mausklick auswählen oder löschen kann. Wenn Sie die für den Berichtsparameter verfügbaren Werte mit einer Datasetabfrage abrufen möchten, achten Sie darauf, kein Dataset auszuwählen, das die demselben Berichtsparameter zugeordnete Abfragevariable enthält.  
  
     Weitere Informationen finden Sie unter [Hinzufügen, Ändern oder Löschen von verfügbaren Werten für einen Berichtsparameter (Berichts-Generator und SSRS)](add-change-or-delete-available-values-for-a-report-parameter.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Hinzufügen von kaskadierenden Parametern zu einem Bericht &#40;Berichts-Generator und SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md)   
 [Hinzufügen, ändern oder Löschen von Berichtsparametern &#40;Berichts-Generator und SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md)  
  
  