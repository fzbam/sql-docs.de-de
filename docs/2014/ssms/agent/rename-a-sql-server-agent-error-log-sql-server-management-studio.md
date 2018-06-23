---
title: Umbenennen eines SQL Server-Agent-Fehlerprotokolls (SQL Server Management Studio)|Microsoft-Dokumente
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- logs [SQL Server], SQL Server Agent
- renaming SQL Server Agent error log
- SQL Server Agent, errors
- errors [SQL Server Agent]
ms.assetid: dee2b199-48af-44cb-9177-d029a5edb169
caps.latest.revision: 27
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: cb195793732393788f698b2e8dca904bf1e5e8ab
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36148313"
---
# <a name="rename-a-sql-server-agent-error-log-sql-server-management-studio"></a>Rename a SQL Server Agent Error Log (SQL Server Management Studio)
  In diesem Thema wird das Umbenennen der Datei beschrieben, in die [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Fehler in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]geschrieben werden.  
  
 **In diesem Thema**  
  
-   **Vorbereitungen:**  
  
     [Einschränkungen](#Restrictions)  
  
     [Security](#Security)  
  
-   [So benennen Sie einen SQL Server-Agent-Fehlerprotokoll mithilfe von SQL Server Management Studio um](#SSMSProcedure)  
  
##  <a name="BeforeYouBegin"></a> Vorbereitungsmaßnahmen  
  
###  <a name="Restrictions"></a> Einschränkungen  
  
-   Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Knoten wird nur im Objekt-Explorer angezeigt, wenn Sie die Berechtigung besitzen, ihn zu verwenden.  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent schreibt erst dann in die neue Protolldatei, wenn der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst neu gestartet wird.  
  
###  <a name="Security"></a> Sicherheit  
  
####  <a name="Permissions"></a> Berechtigungen  
 Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent muss zur Verwendung der Anmeldeinformationen eines Kontos konfiguriert werden, das Mitglied der festen Serverrolle **sysadmin** in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ist, um seine Funktionen ausführen zu können. Das Konto muss über die folgenden Windows-Berechtigungen verfügen:  
  
-   Anmelden als Dienst (SeServiceLogonRight)  
  
-   Ersetzen von Token auf Prozessebene (SeAssignPrimaryTokenPrivilege)  
  
-   Umgehen von durchsuchenden Prüfungen (SeChangeNotifyPrivilege)  
  
-   Anpassen des Arbeitsspeicherkontingents für einen Prozess (SeIncreaseQuotaPrivilege)  
  
 Weitere Informationen zu den Windows-Berechtigungen erforderlich sind, für die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienstkonto, finden Sie unter [wählen Sie ein Konto für den SQL Server-Agent-Dienst](select-an-account-for-the-sql-server-agent-service.md) und [Konfigurieren von Windows-Dienstkonten und Berechtigungen](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).  
  
##  <a name="SSMSProcedure"></a> Verwenden von SQL Server Management Studio  
  
#### <a name="to-rename-a-sql-server-agent-error-log"></a>So benennen Sie ein SQL Server-Agent-Fehlerprotokoll um  
  
1.  Klicken Sie im **Objekt-Explorer** auf das Pluszeichen, um den Server zu erweitern, der das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Fehlerprotokoll enthält, das Sie umbenennen möchten.  
  
2.  Klicken Sie auf das Pluszeichen, um **SQL Server-Agent**zu erweitern.  
  
3.  Klicken Sie mit der rechten Maustaste auf den Ordner **Fehlerprotokolle** , und wählen Sie **Konfigurieren**aus.  
  
4.  Geben Sie im Dialogfeld **Fehlerprotokolle des SQL Server-Agents konfigurieren** im Feld **Fehlerprotokolldatei** den neuen Dateipfad und den Dateinamen für das Fehlerprotokoll an. Klicken Sie alternativ auf die Auslassungspunkte **(...)** , um das Dialogfeld **Geben Sie den Speicherort des Agent-Fehlerprotokolls an** zu öffnen.  
  
5.  Wenn Sie fertig sind, klicken Sie auf **OK**.  
  
  