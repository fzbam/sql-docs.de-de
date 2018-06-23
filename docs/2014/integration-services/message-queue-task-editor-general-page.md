---
title: Task ' Nachrichtenwarteschlange ' (Seite Allgemein) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql12.dts.designer.msgqueuetask.general.f1
helpviewer_keywords:
- Message Queue Task Editor
ms.assetid: 09368b18-37a5-4321-a173-7cfe5d42d2a2
caps.latest.revision: 25
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: f6f6a3624a387ede27cc10e366a1632a1df38b08
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36159616"
---
# <a name="message-queue-task-editor-general-page"></a>Editor für den Task 'Nachrichtenwarteschlange' (Seite Allgemein)
  Auf der Seite **Allgemein** des Dialogfelds **Editor für den Task „Nachrichtenwarteschlange“** können Sie den Task „Nachrichtenwarteschlange“ benennen und beschreiben, das Nachrichtenformat angeben und kennzeichnen, ob vom Task Nachrichten gesendet oder empfangen werden.  
  
 Informationen, um sich mit diesem Thema vertraut zu machen, finden Sie unter [Message Queue Task](control-flow/message-queue-task.md).  
  
## <a name="options"></a>Tastatur  
 **Name**  
 Geben Sie einen eindeutigen Namen für den Task Nachrichtenwarteschlange an. Dieser Name wird im Tasksymbol als Bezeichnung verwendet.  
  
> [!NOTE]  
>  Tasknamen müssen innerhalb eines Pakets eindeutig sein.  
  
 **Beschreibung**  
 Geben Sie eine Beschreibung des Tasks Nachrichtenwarteschlange ein.  
  
 **Use2000Format**  
 Geben Sie an, ob das 2000-Format von Message Queuing (auch bekannt als MSMQ) verwendet werden soll. Der Standardwert ist `False`.  
  
 **MSMQConnection**  
 Wählen Sie einen vorhandenen MSMQ-Verbindungs-Manager aus, oder klicken Sie auf \<**Neue Verbindung…**>, um einen neuen Verbindungs-Manager zu erstellen.  
  
 **Verwandte Themen:** [MSMQ Connection Manager](connection-manager/msmq-connection-manager.md), [MSMQ Connection Manager Editor](../../2014/integration-services/msmq-connection-manager-editor.md)  
  
 **MessageBox**  
 Geben Sie an, ob Nachrichten vom Task Nachrichtenwarteschlange gesendet oder empfangen werden. Wenn Sie **Nachricht senden**auswählen, wird im linken Bereich des Dialogfelds die Seite Senden angezeigt; wenn Sie **Nachricht empfangen**auswählen, wird die Seite Empfangen aufgelistet. Standardmäßig ist dieser Wert auf **Nachricht senden**festgelegt.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen und Meldungsreferenz von Integration Services-Fehler](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Task ' Nachrichtenwarteschlange ' &#40;Seite empfangen&#41;](../../2014/integration-services/message-queue-task-editor-receive-page.md)   
 [Task ' Nachrichtenwarteschlange ' &#40;Seite "Senden"&#41;](../../2014/integration-services/message-queue-task-editor-send-page.md)   
 [Seite Ausdrücke](expressions/expressions-page.md)  
  
  