---
title: Hinzufügen einer Source using Source Assistant | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5e850b7c-4b89-42ad-b0a6-d63ac7cc9568
caps.latest.revision: 5
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: 7ef237b263aa37d3998b8634b18926850d2cb4f4
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36162978"
---
# <a name="add-a-source-using-source-assistant"></a>Hinzufügen einer Quelle mit dem Quellen-Assistenten
  Dieses Thema gibt Schritte an, um eine neue Quelle mithilfe des Quellen-Assistenten hinzuzufügen, und führt die im Dialogfeld **Neue Quelle hinzufügen** verfügbaren Optionen auf, die angezeigt werden, wenn Sie den Quellen-Assistent per Drag & Drop in den SSIS-Designer ziehen.  
  
### <a name="to-use-source-assistant-to-add-a-source"></a>So verwenden Sie den Quellen-Assistenten, um eine Quelle hinzuzufügen  
  
1.  Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Paket, dem eine neue Quellkomponente hinzugefügt werden soll.  
  
2.  Ziehen Sie die **Quellen-Assistenten** -Komponente von der SSIS-Toolbox auf die Registerkarte **Datenfluss** . Sie sollten das Dialogfeld **Neue Quelle hinzufügen** sehen. Der nächste Abschnitt enthält Details zu den im Dialogfeld verfügbaren Optionen.  
  
3.  Wählen Sie den Zieltyp in der Liste **Typ** aus.  
  
4.  Wählen Sie in der Liste **Verbindungs-Manager** einen vorhandenen Verbindungs-Manager aus. Wählen Sie alternativ **\<Neu>** aus, um einen neuen Verbindungs-Manager zu erstellen.  
  
5.  Wenn Sie einen vorhandenen Verbindungs-Manager auswählen, klicken Sie auf **OK** , um das Dialogfeld **Neues Ziel hinzufügen** zu schließen. Sie sollten nun das Ziel und die Verbindungs-Manager sehen, die dem Datenfluss hinzugefügt wurden.  
  
6.  Wenn Sie auf **\<Neu>** klicken, um einen neuen Verbindungs-Manager zu erstellen, sollten Sie ein **Verbindungs-Manager**-Dialogfeld sehen, in dem Sie Parameter für die Verbindung angeben können. Nachdem Sie einen neuen Verbindungs-Managers erstellt haben, werden das Ziel und der Verbindungs-Manager in SSIS-Designer angezeigt.  
  
  