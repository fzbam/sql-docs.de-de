---
title: Hinzufügen von MSOLAP. 5 als vertrauenswürdigen Datenanbieter in Excel Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1f40fa4-de6d-41ee-8124-14b4d65988f5
caps.latest.revision: 5
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: 86686f5ba9ffcdb6e640ce8328d11f600b3bf36c
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36160314"
---
# <a name="add-msolap5-as-a-trusted-data-provider-in-excel-services"></a>Hinzufügen von MSOLAP.5 als vertrauenswürdigen Datenanbieter in Excel Services
  MSOLAP.5 bezieht sich auf den Analysis Services OLE DB-Anbieter für SQL Server 2012. Excel Services müssen diesem Anbieter vertrauen, bevor es die Verbindunganforderung ermöglicht, wodurch die PowerPivot-Daten auf dem Server verfügbar werden.  
  
 Wenn Sie PowerPivot für SharePoint mithilfe des PowerPivot-Konfigurationstools konfiguriert haben, ist MSOLAP.5 möglicherweise ein vertrauenswürdiger Anbieter, da das Tool eine Aktion bietet, die diese Anforderung erfüllt. Wenn Sie jedoch die PowerShell-Zentraladministration verwenden oder die Aktion für den vertrauenswürdigen Anbieter im Konfigurationstool ausgeschlossen haben, fehlt möglicherweise der Anbieter, und Sie müssen den Anbieter jetzt bei der Konfiguration der Farm für den PowerPivot-Datenzugriff hinzufügen.  
  
 Sie müssen diesen Schritt für jede Excel Services-Dienstanwendung nur einmal ausführen.  
  
 Für jeden physischen Server, der eine PowerPivot-Datenanforderung behandelt, z. B. ein PowerPivot für SharePoint-Server oder ein Excel Services-Server, muss auf dem Computer der OLE DB-Anbieter installiert sein. Eine PowerPivot für SharePoint-Installation umfasst immer den OLE DB-Anbieter. Wenn Sie die Excel Services jedoch auf einem Computer ausführen, auf dem PowerPivot für SharePoint nicht vorhanden ist, müssen Sie den Anbieter manuell installieren. Weitere Informationen finden Sie unter [Installieren des OLE DB-Anbieters für Analysis Services auf SharePoint-Servern](../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md).  
  
## <a name="add-a-trusted-provider-to-excel-services"></a>Hinzufügen eines vertrauenswürdigen Anbieters zu Excel Services  
  
1.  Klicken Sie in der Zentraladministration auf **Dienstanwendungen verwalten**und dann auf die Excel Services-Dienstanwendung.  
  
2.  Klicken Sie auf **Vertrauenswürdige Dienstanbieter**.  
  
3.  Überprüfen Sie, dass MSOLAP.5 in der Liste angezeigt wird. Je nach der Art der Konfiguration von PowerPivot für SharePoint wird MSOLAP.5 möglicherweise bereits vertraut.  
  
4.  Falls nicht aufgeführt, klicken Sie auf **Vertrauenswürdigen Datenanbieter hinzufügen**.  
  
5.  Geben Sie unter Anbieter-ID `MSOLAP.5`.  
  
6.  Stellen Sie sicher, dass für den Anbietertyp OLE DB ausgewählt ist.  
  
7.  Geben Sie als Anbieterbeschreibung **Microsoft OLE DB-Anbieter für OLAP Services 11.0**ein.  
  
  