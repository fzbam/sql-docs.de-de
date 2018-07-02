---
title: Erstellen einer Attributgruppe (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attribute groups [Master Data Services], creating
- creating attribute groups [Master Data Services]
ms.assetid: 798c325e-e8d8-412a-b02e-118f2741d1c7
caps.latest.revision: 5
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: 0a063af91090ff2e8d5eb1145bb5968573d04523
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36149713"
---
# <a name="create-an-attribute-group-master-data-services"></a>Erstellen einer Attributgruppe (Master Data Services)
  Erstellen Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]Attributgruppen, wenn Sie Attribute auf einzelnen Registerkarten im **Explorerraster** anzeigen möchten.  
  
> [!NOTE]  
>  Beim Erstellen einer Attributgruppe wird diese automatisch für alle Benutzer bis auf den Ersteller ausgeblendet. Weitere Informationen zu die Gruppe sichtbar machen, finden Sie unter [für Benutzer ein Attribut Gruppe sichtbar machen &#40;Master Data Services&#41;](make-an-attribute-group-visible-to-users-master-data-services.md).  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 So führen Sie diese Prozedur aus  
  
-   Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **Systemverwaltung** zuzugreifen.  
  
-   Sie müssen ein Modelladministrator sein. Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).  
  
-   Es muss mindestens ein Attribut vorhanden sein. Weitere Informationen finden Sie unter [Erstellen eines Textattributs &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md).  
  
### <a name="to-create-an-attribute-group"></a>So erstellen Sie eine Attributgruppe  
  
1.  Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.  
  
2.  Auf der **Modellansicht** Seite zeigen Sie auf der Menüleiste **verwalten** , und klicken Sie auf **Attributgruppen**.  
  
3.  Wählen Sie aus der Liste **Modell** ein Modell aus.  
  
4.  Wählen Sie aus der Liste **Entität** eine Entität aus.  
  
5.  Klicken Sie auf **Blattgruppen**, **Konsolidierte Gruppen**oder **Auflistungsgruppen** , um eine Attributgruppe von Blattelementen, konsolidierten Elementen oder Auflistungen zu erstellen.  
  
6.  Klicken Sie auf **Attributgruppe hinzufügen**.  
  
7.  In der **Name der Blattgruppe** geben einen Namen für die Gruppe. Dies ist der Name angezeigt, auf der Registerkarte im **Explorer**.  
  
    > [!NOTE]  
    >  Wenn Sie ausgewählt haben **konsolidierte Gruppen** oder **Auflistungsgruppen** in Schritt 5 dieses Feld ist **Name der konsolidierten Gruppe** oder **Auflistungsgruppe**bzw.  
  
8.  Klicken Sie auf **Gruppe speichern**.  
  
9. Erweitern Sie den Ordner für die Gruppe.  
  
10. Klicken Sie auf **Attribute**.  
  
11. Klicken Sie auf **ausgewähltes Element bearbeiten**.  
  
12. Klicken Sie auf die Attribute in der **verfügbar** Feld, und klicken Sie auf die **hinzufügen** Pfeil. Klicken Sie auf den Pfeil für **Alle hinzufügen** , um alles hinzuzufügen.  
  
13. Klicken Sie optional auf die **einrichten** und **unten** Pfeile, um die links-nach-rechts-Reihenfolge der Attribute ändern.  
  
14. Klicken Sie auf **Speichern**.  
  
## <a name="next-steps"></a>Nächste Schritte  
  
-   [Sichtbarmachen einer Attributgruppe für Benutzer &#40;Master Data Services&#41;](make-an-attribute-group-visible-to-users-master-data-services.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Attributgruppen &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md)   
 [Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md)   
 [Ändern des Namens einer Attributgruppe &#40;Master Data Services&#41;](../../2014/master-data-services/change-an-attribute-group-name-master-data-services.md)   
 [Löschen einer Attributgruppe &#40;Master Data Services&#41;](../../2014/master-data-services/delete-an-attribute-group-master-data-services.md)   
 [Blattelemente Berechtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md)   
 [Konsolidierte Berechtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/consolidated-permissions-master-data-services.md)  
  
  