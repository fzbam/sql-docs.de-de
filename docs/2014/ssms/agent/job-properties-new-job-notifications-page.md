---
title: 'Auftragseigenschaften: Neuer Auftrag (Benachrichtigungsseite) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql12.ag.job.notifications.f1
ms.assetid: ed393cbd-4496-4399-a177-e5baa92fb689
caps.latest.revision: 28
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 39dd7fe869b89b7793e2128c619beb4ec9c36a84
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36047313"
---
# <a name="job-properties-new-job-notifications-page"></a>Auftragseigenschaften: Neuer Auftrag (Benachrichtigungsseite)
  Auf dieser Seite können Sie die Aktionen für den [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent festlegen, die bei Abschluss des Auftrags auszuführen sind.  
  
## <a name="options"></a>Tastatur  
 **E-Mail**  
 Diese Option wird ausgewählt, um bei Abschluss des Auftrags eine E-Mail zu senden. Nachdem Sie die Option ausgewählt haben, müssen Sie den zu benachrichtigenden Operator und die Bedingung auswählen, durch die die Benachrichtigung ausgelöst wird. Die Bedingungen sind **Bei erfolgreicher Auftragsausführung**, **Bei Auftragsfehler**oder **Beim Abschluss des Auftrags**.  
  
 **Page**  
 Diese Option wird ausgewählt, um eine E-Mail an den Pager des Operators zu senden, wenn der Auftrag abgeschlossen ist. Nachdem Sie die Option ausgewählt haben, müssen Sie den zu benachrichtigenden Operator und die Bedingung auswählen, durch die die Benachrichtigung ausgelöst wird. Die Bedingungen sind **Bei erfolgreicher Auftragsausführung**, **Bei Auftragsfehler**oder **Beim Abschluss des Auftrags**.  
  
 **NET SEND**  
 Diese Option wird ausgewählt, um einen Operator bei Abschluss des Auftrags über net send zu benachrichtigen. Nachdem Sie die Option ausgewählt haben, müssen Sie den zu benachrichtigenden Operator und die Bedingung auswählen, durch die die Benachrichtigung ausgelöst wird. Die Bedingungen sind **Bei erfolgreicher Auftragsausführung**, **Bei Auftragsfehler**oder **Beim Abschluss des Auftrags**.  
  
 **In das Windows-Anwendungsereignisprotokoll schreiben**  
 Diese Option wird ausgewählt, um bei Abschluss des Auftrags einen Eintrag in das Anwendungsereignisprotokoll zu schreiben. Nachdem Sie die Option ausgewählt haben, müssen Sie die Bedingung angeben, durch die veranlasst wird, dass der Eintrag geschrieben wird. Die Bedingungen sind **Bei erfolgreicher Auftragsausführung**, **Bei Auftragsfehler**und **Beim Abschluss des Auftrags**.  
  
 **Auftrag automatisch löschen**  
 Diese Option wird ausgewählt, um den Auftrag bei Abschluss zu löschen. Nachdem Sie die Option ausgewählt haben, müssen Sie die Bedingung angeben, durch die veranlasst wird, dass der Auftrag gelöscht wird. Die Bedingungen sind **Bei erfolgreicher Auftragsausführung**, **Bei Auftragsfehler**und **Beim Abschluss des Auftrags**.  
  
## <a name="see-also"></a>Siehe auch  
 [Implementieren von Aufträgen](implement-jobs.md)   
 [Konfigurieren von SQL Server-Agent-Mail zum Verwenden von Datenbank-E-Mails](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md)  
  
  