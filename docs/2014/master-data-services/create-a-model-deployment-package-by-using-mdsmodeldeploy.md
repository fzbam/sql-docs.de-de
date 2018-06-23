---
title: Erstellen eines Modellbereitstellungspakets mit MDSModelDeploy | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2687e39-dc20-494f-a707-2aa29f4c329e
caps.latest.revision: 15
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: 399c6743f302bd616fe0a232527fcb5fc0af62ab
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36160452"
---
# <a name="create-a-model-deployment-package-by-using-mdsmodeldeploy"></a>Erstellen eines Modellbereitstellungspakets mit MDSModelDeploy
  Sie verwenden in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]das Tool MDSModelDeploy, um ein Paket zu erstellen. Abhängig von den angegebenen Befehlen kann das Paket folgenden Inhalt haben:  
  
-   Nur Modellobjekte.  
  
-   Modellobjekte und Daten.  
  
 Wenn Sie ein Paket bereitstellen möchten, das nur Modellobjekte enthält, können Sie stattdessen den Modellbereitstellungs-Assistenten in der [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] -Webanwendung verwenden. Weitere Informationen finden Sie unter [Erstellen eines Modellbereitstellungspakets mithilfe des Assistenten](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md).  
> [!NOTE]  
> Diese Version des Tools MDSModelDeploy kann nicht mehrere Gigabyte (GB) Speicher verwenden. Beim Erstellen oder Bereitstellen von großen Modellen mithilfe von **Model-Objekte und Daten** Option "nicht genügend Arbeitsspeicher" oder "Datenstrom war zu lang"-Fehler können auftreten. Um dieses Problem zu beheben, verwenden Sie MDS-Stagingtabelle zum Bereitstellen von Daten; oder eine Aktualisierung auf MDS 2016 oder eine höhere Version, die die aktualisierte Version des Tools MDSModelDeploy enthält.
## <a name="prerequisites"></a>Erforderliche Komponenten  
 So führen Sie diese Prozedur aus  
  
1.  Die grundlegenden Berechtigungen zum Ausführen des MDSModelDeploy-Tools lauten wie folgt:  
  
    -   Die gleiche Windows-Berechtigung wie der MDS-Konfigurations-Manager (Windows-Administrator)  
  
    -   DBA-Berechtigung für die MDS-Datenbank  
  
2.  Die grundlegenden Berechtigungen zum Erstellen des Pakets mit dem MDSModelDeploy-Tool lauten wie folgt:  
  
    -   MDS-Modelladministratorberechtigung für das Datenmodell.  
  
    -   Funktionsberechtigung für das MDS-Integrationsmanagement  
  
3.  Die grundlegenden Berechtigungen zum Bereitstellen eines Modells mit dem MDSModelDeploy-Tool lauten wie folgt:  
  
    -   Funktionsberechtigung für den MDS-Explorer  
  
    -   Funktionsberechtigung für die MDS-Integrationsmanagement  
  
    -   Funktionsberechtigung für die MDS-Systemverwaltung  
  
4.  Die grundlegenden Berechtigungen zum Auflisten von Modellen mit dem MDSModelDeploy-Tool lauten wie folgt:  
  
    -   Funktionsberechtigung für den MDS-Explorer  
  
    -   MDS-Modelladministratorberechtigung für das Datenmodell zum Anzeigen des Modells in der Liste.  
  
 Es muss ein Modell vorhanden sein, aus dem Sie ein Paket erstellen können. Weitere Informationen finden Sie unter [Erstellen eines Modells &#40;Master Data Services&#41;](create-a-model-master-data-services.md).  
  
 Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).  
  
### <a name="to-create-a-model-deployment-package-by-using-mdsmodeldeploy"></a>So erstellen Sie ein Modellbereitstellungspaket mit MDSModelDeploy  
  
1.  Öffnen Sie eine Eingabeaufforderung.  
  
2.  Navigieren Sie zum Speicherort von "MDSModelDeploy.exe".  
  
    -   Wenn MDS am Standardspeicherort installiert wurde, wird die Datei *Laufwerk*: \Programme\Microsoft SQL Server\120\Master Data Services\Configuration.  
  
    -   Wenn MDS nicht am Standardspeicherort installiert wurde, suchen Sie auf dem lokalen Computer nach der Datei "MDSModelDeploy.exe".  
  
3.  Optional. Dient zum Anzeigen der Optionen und der Hilfe.  
  
    -   Geben Sie `MDSModelDeploy` ein, und drücken Sie EINGABETASTE, um alle verfügbaren Optionen anzuzeigen.  
  
    -   Geben Sie Folgendes ein, um Hilfe für eine Option anzuzeigen, wobei *OptionName* der Name der Option ist: `MDSModelDeploy help OptionName`.  
  
4.  Optional. Wenn Sie über mehrere Webanwendungen verfügen, bestimmen Sie den Namen des Diensts, für den Sie die Bereitstellung durchführen, indem Sie diesen Befehl eingeben und die EINGABETASTE drücken:  
  
    ```  
    MDSModelDeploy listservices  
    ```  
  
     Eine Liste von Werten wird zurückgegeben, z. B. `MDS1, Default Web Site, MDS`. Der erste Wert in dieser Liste (in diesem Fall `MDS1`) wird benötigt, um das Modell bereitzustellen.  
  
5.  Geben Sie Folgendes ein, um ein Paket zu erstellen, das Modellobjekte und Daten enthält. Dabei gilt: *ModelName*, *VersionName*, *ServiceName*und *PackageName* sind die Namen des Modells, der Version, des Diensts bzw. der PKG-Ausgabedatei:  
  
    ```  
    MDSModelDeploy createpackage -model ModelName -version VersionName -service ServiceName -package PackageName -includedata  
    ```  
  
     Wenn Sie keine Daten einschließen möchten, verwenden Sie nicht die Schalter `-version` und `-includedata` .  
  
6.  Drücken Sie die EINGABETASTE. Nach der erfolgreichen Erstellung des Pakets wird eine Meldung angezeigt, die besagt, dass der MDSModelDeploy-Vorgang erfolgreich abgeschlossen wurde.  
  
## <a name="next-steps"></a>Nächste Schritte  
  
-   [Bereitstellen eines Modellbereitstellungspakets mit MDSModelDeploy](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Modellieren von Bereitstellungsoptionen &#40;Master Data Services&#41;](../../2014/master-data-services/model-deployment-options-master-data-services.md)   
 [Bereitstellen von Modellen &#40;Master Data Services&#41;](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
  