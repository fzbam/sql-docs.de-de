---
title: Administratoren (Master Data Services) | Microsoft-Dokumentation
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
- administrators [Master Data Services], about administrators
- administrators [Master Data Services]
- models [Master Data Services], administrators
ms.assetid: d330aa4e-6ade-4b09-b376-1b15d6c78f7d
caps.latest.revision: 8
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: 11abfb4949bdd7917066ed785dd1014efc026e9a
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36057219"
---
# <a name="administrators-master-data-services"></a>Administratoren (Master Data Services)
  In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] gibt es zwei Arten von Administratoren: Modelladministratoren und den [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]-Systemadministrator.  
  
## <a name="model-administrators"></a>Modelladministratoren  
 In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], ein modelladministrator ist ein Benutzer mit **Update** Berechtigung für das Modellobjekt der obersten Ebene zugewiesen werden, auf die **Modellobjekte** Registerkarte und keine weiteren Berechtigungen zugewiesen.  
  
-   Wenn der Benutzer Zugriff auf den Funktionsbereich **Explorer** hat, kann er alle Masterdaten in diesem Bereich hinzufügen, löschen und aktualisieren.  
  
-   Wenn der Benutzer Zugriff auf andere Funktionsbereiche hat, kann der Benutzer alle im Funktionsbereich verfügbaren administrativen Tasks ausführen.  
  
 Jedes Modell kann mehrere Administratoren aufweisen. Ein Benutzer kann als Modelladministrator für ein Modell, mehrere oder alle Modelle in der [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] -Bereitstellung definiert sein.  
  
 Er wird entweder in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] oder programmgesteuert als Modelladministrator festgelegt. Weitere Informationen finden Sie unter [Create a Model Administrator &#40;Master Data Services&#41;](create-a-model-administrator-master-data-services.md).  
  
## <a name="master-data-services-system-administrator"></a>Master Data Services-Systemadministrator  
 Es gibt nur einen [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]-Systemadministrator. Der Systemadministrator ist für die angegebene Benutzer die **Administratorkonto** beim Erstellen der [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] Datenbank.  
  
 Der [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]-Systemadministrator:  
  
-   Verfügt automatisch über Zugriff auf alle Funktionsbereiche.  
  
-   Hinzufügen, löschen und aktualisieren Sie alle Masterdaten für alle Modelle in können die **Explorer** Funktionsbereich ".  
  
 Sie können den Benutzer ändern, der als Systemadministrator festgelegt ist. Weitere Informationen finden Sie unter [Ändern des Systemadministratorkontos &#40;Master Data Services&#41;](../../2014/master-data-services/change-the-system-administrator-account-master-data-services.md).  
  
## <a name="comparing-administrator-types"></a>Vergleichen von Administratortypen  
  
|Administratortyp|Description|  
|------------------------|-----------------|  
|[!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]-Systemadministrator|Im [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] zugewiesene Berechtigungen wirken sich nicht auf den Zugriff des Administrators aus.<br /><br /> Verfügt automatisch über **Update** Berechtigung für alle Modelle.<br /><br /> Verfügt automatisch über Zugriff auf alle Funktionsbereiche.<br /><br /> In mdm.tblUser lautet der Wert in der **ID** Spalte **1**.|  
|Modelladministrator|In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] zugewiesene Berechtigungen bestimmen, ob der Benutzer Modelladministrator ist.<br /><br /> Kann je nach den Berechtigungen, die explizit zugewiesen oder von einer Gruppe geerbt wurden, Modelladministrator sein.<br /><br /> Ist ein Administrator nur Modelle mit **Update** Objekt der obersten Ebene zugewiesene Berechtigung und keine weiteren Berechtigungen.<br /><br /> Verfügt nur über Zugriff auf Funktionsbereiche, für die ihm eine Berechtigung gewährt wurde.<br /><br /> In mdm.tblUser lautet der Wert in der **ID** Spalte ist keine **1**.|  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen eines Modelladministrators &#40;Master Data Services&#41;](create-a-model-administrator-master-data-services.md)   
 [Ändern des Systemadministratorkontos &#40;Master Data Services&#41;](../../2014/master-data-services/change-the-system-administrator-account-master-data-services.md)   
 [Erstellen einer Master Data Services-Datenbank](install-windows/create-a-master-data-services-database.md)   
 [Benachrichtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/notifications-master-data-services.md)  
  
  