---
title: 'Schritt 2: Hinzufügen und Konfigurieren eines Verbindungs-Managers für Flatfiles | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a77dd32-d8c2-4961-ad37-2a971f9d6043
caps.latest.revision: 42
author: douglaslM
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: c732e124ca8de59f28f4d5121a85e071d6fda7f2
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36147945"
---
# <a name="step-2-adding-and-configuring-a-flat-file-connection-manager"></a>Schritt 2: Hinzufügen und Konfigurieren eines Verbindungs-Managers für Flatfiles
  In dieser Aufgabe fügen Sie einen Verbindungs-Manager für Flatfiles zum von Ihnen erstellten Paket hinzu. Mithilfe eines Verbindungs-Managers für Flatfiles können von einem Paket Daten aus einer Flatfile extrahiert werden. Mithilfe des Verbindungs-Managers für Flatfiles können Sie den Namen und Speicherort der Datei, die Gebietsschema- und Codepage sowie das Dateiformat einschließlich der Spaltentrennzeichen angeben, die angewendet werden sollen, wenn vom Paket Daten aus der Flatfile extrahiert werden. Zusätzlich können Sie die Datentypen für einzelne Spalten manuell angeben oder das Dialogfeld **Spaltentypen vorschlagen** verwenden, um die Spalten extrahierter Daten automatisch [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Datentypen zuzuordnen.  
  
 Sie müssen einen neuen Verbindungs-Manager für Flatfiles für jedes Dateiformat erstellen, mit dem Sie arbeiten. Weil in diesem Lernprogramm Daten aus mehreren Flatfiles mit genau dem gleichen Datenformat extrahiert werden, müssen Sie für Ihr Paket nur einen Verbindungs-Manager für Flatfiles hinzufügen und konfigurieren.  
  
 Für dieses Lernprogramm konfigurieren Sie die folgenden Eigenschaften in Ihrem Verbindungs-Manager für Flatfiles:  
  
-   **Spaltennamen:** Weil die Flatfile keine Spaltennamen aufweist, werden vom Verbindungs-Manager für Flatfiles Standardspaltennamen erstellt. Diese Standardnamen sind nicht sinnvoll, wenn der Zweck jeder Spalte identifiziert werden soll. Damit diese Standardnamen nützlicher werden, müssen Sie die Standardnamen so ändern, dass sie mit der Faktentabelle übereinstimmen, in die die Flatfiledaten geladen werden.  
  
-   **Datenzuordnungen:** Die Datentypenzuordnungen, die Sie für den Verbindungs-Manager für Flatfiles angeben, werden von allen Flatfile-Datenquellenkomponenten verwendet, die auf den Verbindungs-Manager verweisen. Sie können diese Datentypen entweder mithilfe des Verbindungs-Managers für Flatfiles manuell zuordnen oder das Dialogfeld **Spaltentypen vorschlagen** verwenden. In diesem Tutorial werden die vorgeschlagenen Zuordnungen im Dialogfeld **Spaltentypen vorschlagen** angezeigt. Sie nehmen dann manuell die erforderlichen Zuordnungen im Dialogfeld **Verbindungs-Manager-Editor für Flatfiles** vor.  
  
 Der Verbindungs-Manager für Flatfiles stellt Gebietsschemainformationen zur Datendatei bereit. Wenn Ihr Computer nicht zur Verwendung der regionalen Einstellung Englisch (USA) konfiguriert ist, müssen Sie zusätzliche Eigenschaften im Dialogfeld **Verbindungs-Manager-Editor für Flatfiles** festlegen.  
  
### <a name="to-add-a-flat-file-connection-manager-to-the-ssis-package"></a>So fügen Sie einen Flatfile-Verbindungs-Manager zum SSIS-Paket hinzu  
  
1.  Klicken Sie mit der rechten Maustaste auf eine beliebige Stelle im **Verbindungs-Manager** -Bereich und anschließend auf **Neue Flatfile-Verbindung**.  
  
2.  Geben Sie im Dialogfeld **Verbindungs-Manager-Editor für Flatfiles** für **Name des Verbindungs-Managers**den Namen **Sample Flat File Source Data**ein.  
  
3.  Klicken Sie auf **Durchsuchen**.  
  
4.  Suchen Sie im Dialogfeld **Öffnen** die Datei SampleCurrencyData.txt auf Ihrem Computer.  
  
     Die Beispieldaten sind in den [!INCLUDE[ssIS](../includes/ssis-md.md)] -Lektionspaketen enthalten. Um die Beispieldaten und die Lektionspakete herunterzuladen, gehen Sie wie folgt vor.  
  
    1.  Klicken Sie [hier](http://go.microsoft.com/fwlink/?LinkId=275027), um zur Seite Integration Services Product Samples zu gelangen  
  
    2.  Klicken Sie auf die Registerkarte **DOWNLOADS** .  
  
    3.  Klicken Sie auf die Datei „SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip“.  
  
5.  Löschen Sie die Spaltennamen im ersten Datenzeilen-Kontrollkästchen.  
  
### <a name="to-set-locale-sensitive-properties"></a>So legen Sie gebietsschemabezogene Eigenschaften fest  
  
1.  Klicken Sie im Dialogfeld **Verbindungs-Manager-Editor für Flatfiles** auf **Allgemein**.  
  
2.  Legen Sie **Gebietsschema** auf Englisch (USA) und **Codepage** auf 1252 fest.  
  
### <a name="to-rename-columns-in-the-flat-file-connection-manager"></a>So benennen Sie Spalten im Verbindungs-Manager für Flatfiles um  
  
1.  Klicken Sie im Dialogfeld **Verbindungs-Manager-Editor für Flatfiles** auf **Erweitert**.  
  
2.  Nehmen Sie im Eigenschaftenbereich die folgenden Änderungen vor:  
  
    -   Ändern der **Spalte 0** -Nameneigenschaft in `AverageRate`.  
  
    -   Ändern der **Spalte1** -Nameneigenschaft in `CurrencyID`.  
  
    -   Ändern der **Spalte 2** -Nameneigenschaft in `CurrencyDate`.  
  
    -   Ändern der **Spalte 3** -Nameneigenschaft in `EndOfDayRate`.  
  
    > [!NOTE]  
    >  Standardmäßig sind alle vier Spalten auf einen Zeichenfolgendatentyp [DT_STR] mit einer `OutputColumnWidth` von 50 festgelegt.  
  
### <a name="to-remap-column-data-types"></a>So ordnen Sie Spaltendatentypen neu zu  
  
1.  Klicken Sie im Dialogfeld **Verbindungs-Manager-Editor für Flatfiles** auf **Typen vorschlagen**.  
  
     [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] schlägt automatisch die am besten geeigneten Datentypen auf Basis der ersten 200 Datenzeilen vor. Sie können diese Vorschlagsoptionen auch ändern, um mehr oder weniger Daten auszuwerten, den Standarddatentyp für ganzzahlige oder boolesche Daten anzugeben oder Leerstellen zum Auffüllen von Zeichenfolgenspalten hinzuzufügen.  
  
     Nehmen Sie vorerst keine Änderungen an den Optionen im Dialogfeld **Spaltentypen vorschlagen** vor und klicken Sie auf **OK** , damit von [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Datentypen für Spalten vorgeschlagen werden. Anschließend kehren Sie zum Bereich **Erweitert** im Dialogfeld **Verbindungs-Manager-Editor für Flatfiles** zurück, in dem Sie die von [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]vorgeschlagenen Spaltendatentypen anzeigen können. (Wenn Sie auf **Abbrechen**klicken, werden keine Vorschläge zu Spaltenmetadaten gemacht und wird der Standardtyp für Zeichenfolgendaten (DT_STR) verwendet.)  
  
     In diesem Lernprogramm werden von [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] die Datentypen vorgeschlagen, die in der zweiten Spalte der folgenden Tabelle für die Daten aus der Datei SampleCurrencyData.txt angezeigt werden. Die für die Spalten im Ziel erforderlichen Datentypen, die in einem späteren Schritt definiert werden, werden allerdings in der letzten Spalte der folgenden Tabelle angezeigt.  
  
    |Flatfilespalte|Vorgeschlagener Typ|Zielspalte|Zieltyp|  
    |----------------------|--------------------|------------------------|----------------------|  
    |AverageRate|float [DT_R4]|FactCurrency.AverageRate|FLOAT|  
    |CurrencyID|string [DT_STR]|DimCurrency.CurrencyAlternateKey|nchar(3)|  
    |CurrencyDate|date [DT_DATE]|DimDate.FullDateAlternateKey|date|  
    |EndOfDayRate|float [DT_R4]|FactCurrency.EndOfDayRate|FLOAT|  
  
     Vorgeschlagene Datentyp für die `CurrencyID` Spalte ist nicht kompatibel mit dem Datentyp des Felds in der Zieltabelle. Da der Datentyp des `DimCurrency.CurrencyAlternateKey` ist "Nchar (3)," `CurrencyID` von String [DT_STR] in String [DT_WSTR] geändert werden. Zusätzlich ist das Feld `DimDate.FullDateAlternateKey` ist definiert als Date-Datentyp; daher `CurrencyDate` von Date [DT_Date] in Database Date [DT_DBDATE] geändert werden muss.  
  
2.  Klicken Sie in der Liste, wählen Sie die CurrencyID-Spalte, und ändern Sie im Eigenschaftenbereich den Datentyp der Spalte `CurrencyID` von String [DT_STR] in Unicode string [DT_WSTR].  
  
3.  Ändern Sie im Eigenschaftenbereich den Datentyp der Spalte `CurrencyDate` von Date [DT_DATE] in Database Date [DT_DBDATE].  
  
4.  Klicken Sie auf **OK**.  
  
## <a name="next-task-in-lesson"></a>Nächste Aufgabe in dieser Lektion  
 [Schritt 3: Hinzufügen und Konfigurieren eines OLE DB-Verbindungs-Managers](lesson-1-3-adding-and-configuring-an-ole-db-connection-manager.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Flat File Connection Manager](connection-manager/file-connection-manager.md)   
 [SQL Server Integration Services-Datentypen](data-flow/integration-services-data-types.md)  
  
  