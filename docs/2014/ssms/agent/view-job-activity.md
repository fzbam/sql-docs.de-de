---
title: Auftragsaktivitäten anzeigen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- viewing job activity
- jobs [SQL Server Agent], viewing
- SQL Server Agent jobs, viewing
- displaying job activity
ms.assetid: 5c284e5e-7775-435d-ac49-f3f12a27ddc7
caps.latest.revision: 24
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 2a71eb46918d9ae7c0189293b6c67313b6b8a285
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36161466"
---
# <a name="view-job-activity"></a>Auftragsaktivitäten anzeigen
  In diesem Thema wird beschrieben, wie Sie den Laufzeitstatus von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Aufträgen in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]anzeigen können.  
  
 Wenn der [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst startet, wird eine neue Sitzung erstellt und die **sysjobactivity** -Tabelle in der **msdb** -Datenbank wird mit allen vorhandenen definierten Aufträgen aufgefüllt. In dieser Tabelle werden die aktuelle Auftragsaktivität und der aktuelle Auftragsstatus aufgezeichnet. Mithilfe des Auftragsaktivitätsmonitors im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent können Sie den aktuellen Status von Aufträgen anzeigen. Falls der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst unerwartet beendet wird, ersehen Sie aus der **sysjobactivity** -Tabelle, welche Aufträge ausgeführt wurden, als der Dienst beendet wurde.  
  
 **In diesem Thema**  
  
-   **Vorbereitungen:**  
  
     [Security](#Security)  
  
-   **So zeigen Sie die Auftragsaktivität an mit**  
  
     [SQL Server Management Studio](#SSMS)  
  
     [Transact-SQL](#TSQL)  
  
## <a name="before-you-begin"></a>Vorbereitungen  
  
###  <a name="Security"></a> Sicherheit  
 Ausführliche Informationen finden Sie unter [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).  
  
##  <a name="SSMS"></a> Verwenden von SQL Server Management Studio  
  
#### <a name="to-view-job-activity"></a>So zeigen Sie die Auftragsaktivität an  
  
1.  Stellen Sie im **Objekt-Explorer**eine Verbindung zu einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]her, und erweitern Sie dann diese Instanz.  
  
2.  Erweitern Sie **SQL Server-Agent**.  
  
3.  Klicken Sie mit der rechten Maustaste auf **Auftragsaktivitätsmonitor** , und klicken Sie dann auf **Auftragsaktivitäten anzeigen**.  
  
4.  Im **Auftragsaktivitätsmonitor**können Sie Details zu jedem Auftrag anzeigen, der für diesen Server definiert ist.  
  
5.  Klicken Sie mit der rechten Maustaste auf einen Auftrag. Nun können Sie den Auftrag starten, beenden, aktivieren oder deaktivieren, löschen, dessen Status im Auftragsaktivitätsmonitor aktualisieren oder dessen Verlauf oder Eigenschaften anzeigen.  Um mehrere Aufträge zu starten, beenden, aktivieren, deaktivieren oder aktualisieren, wählen Sie mehrere Zeilen im Auftragsaktivitätsmonitor aus, und klicken Sie mit der rechten Maustaste auf die Auswahl.  
  
6.  Klicken Sie auf **Aktualisieren**, um den Auftragsaktivitätsmonitor zu aktualisieren. Um weniger Zeilen anzuzeigen, klicken Sie auf **Filter** , und geben Sie Filterparameter ein.  
  
##  <a name="TSQL"></a> Verwenden von Transact-SQL  
  
#### <a name="to-view-job-activity"></a>So zeigen Sie die Auftragsaktivität an  
  
1.  Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.  
  
2.  Klicken Sie in der Standardleiste auf **Neue Abfrage**.  
  
3.  Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.  
  
    ```  
    -- lists activity for all jobs that the current user has permission to view.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_jobactivity ;  
    GO  
    ```  
  
 Weitere Informationen finden Sie unter [Sp_help_jobactivity &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobactivity-transact-sql).  
  
  