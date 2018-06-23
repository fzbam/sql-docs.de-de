---
title: Erstellen einer Veröffentlichung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/30/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- publications [SQL Server replication], creating
- articles [SQL Server replication], defining
- adding articles
- articles [SQL Server replication], adding
ms.assetid: 52ee6de9-1d58-4cb9-8711-372bddbe7154
caps.latest.revision: 43
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: dbfa449e19f77b7537232e0fc8689a47f30ea1fc
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36060697"
---
# <a name="create-a-publication"></a>Create a Publication
  In diesem Thema wird beschrieben, wie eine Veröffentlichung in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]oder Replikationsverwaltungsobjekten (RMO) erstellt wird.  
  
 **In diesem Thema**  
  
-   **Vorbereitungen:**  
  
     [Einschränkungen](#Restrictions)  
  
     [Security](#Security)  
  
-   **So erstellen Sie eine Veröffentlichung und definieren Artikel mit:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
     [Replikationsverwaltungsobjekte (RMO)](#RMOProcedure)  
  
##  <a name="BeforeYouBegin"></a> Vorbereitungsmaßnahmen  
  
###  <a name="Restrictions"></a> Einschränkungen  
  
-   Veröffentlichungs- und Artikelnamen dürfen folgende Zeichen nicht enthalten: % , \* , [ , ] , | , : , " , ? , ", \, /, \< , >. Wenn Objekte in der Datenbank eines dieser Zeichen enthalten, und Sie die Objekte replizieren möchten, müssen Sie einen Artikelnamen angeben, der sich von dem Objektnamen im Dialogfeld **Artikeleigenschaften - \<Article>** unterscheidet. Dieses Dialogfeld ist im Assistenten auf der Seite **Artikel** verfügbar.  
  
###  <a name="Security"></a> Sicherheit  
 Benutzer sollten nach Möglichkeit dazu aufgefordert werden, Anmeldeinformationen zur Laufzeit anzugeben. Wenn Sie Anmeldeinformationen speichern müssen, verwenden Sie die [Kryptografiedienste](http://go.microsoft.com/fwlink/?LinkId=34733) von [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows .NET Framework.  
  
##  <a name="SSMSProcedure"></a> Verwenden von SQL Server Management Studio  
 Mit dem Assistenten für neue Veröffentlichung erstellen Sie Veröffentlichungen und definieren Artikel. Rufen Sie nach der Erstellung einer Veröffentlichung das Dialogfeld **Veröffentlichungseigenschaften – \<Veröffentlichung>** auf, um die Eigenschaften anzuzeigen und zu ändern. Weitere Informationen zum Erstellen von Veröffentlichungen aus einer Oracle-Datenbank finden Sie unter [Erstellen einer Veröffentlichung aus einer Oracle-Datenbank](create-a-publication-from-an-oracle-database.md).  
  
#### <a name="to-create-a-publication-and-define-articles"></a>So erstellen Sie eine Veröffentlichung und definieren Artikel  
  
1.  Stellen Sie in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]eine Verbindung mit dem Verleger her, und erweitern Sie dann den Serverknoten.  
  
2.  Erweitern Sie den Ordner **Replikation** , und klicken Sie dann mit der rechten Maustaste auf den Ordner **Lokale Veröffentlichungen** .  
  
3.  Klicken Sie auf **Neue Veröffentlichung**.  
  
4.  Folgen Sie den Anweisungen auf den Seiten des Assistenten für neue Veröffentlichung, um folgende Vorgänge auszuführen:  
  
    -   Angeben eines Verteilers, falls die Verteilung auf dem Server nicht konfiguriert wurde. Weitere Informationen zum Konfigurieren der Verteilung finden Sie unter [Konfigurieren der Veröffentlichung und der Verteilung](../configure-publishing-and-distribution.md).  
  
         Wenn Sie auf der Seite **Verteiler** angeben, dass der Verleger als eigener Verteiler fungiert (lokaler Verteiler) und der Server nicht als Verteiler konfiguriert ist, erfolgt die Konfiguration des Servers durch den Assistenten für neue Veröffentlichung. Auf der Seite **Momentaufnahmeordner** geben Sie einen Standardmomentaufnahmeordner für den Verteiler an. Der Momentaufnahmeordner ist lediglich ein von Ihnen freigegebenes Verzeichnis. Agents, die aus diesem Ordner lesen bzw. in den Ordner schreiben, benötigen ausreichende Zugriffsberechtigungen. Weitere Informationen zum Sichern des Ordners finden Sie unter [Sichern des Momentaufnahmeordners](../security/secure-the-snapshot-folder.md).  
  
         Wenn Sie angeben, dass ein anderer Server als Verteiler fungieren soll, müssen Sie auf der Seite **Administratorkennwort** ein Kennwort für Verbindungen eingeben, die zwischen dem Verleger und dem Verteiler hergestellt werden. Dieses Kennwort muss mit dem Kennwort übereinstimmen, dass bei der Aktivierung des Verlegers auf dem Remoteverteiler angegeben wurde.  
  
         Weitere Informationen finden Sie unter [Configure Distribution](../configure-distribution.md).  
  
    -   Auswählen einer Veröffentlichungsdatenbank.  
  
    -   Auswählen eines Veröffentlichungstyps. Weitere Informationen finden Sie unter [Replikationstypen](../types-of-replication.md).  
  
    -   Angeben von Daten und Datenbankobjekten, die veröffentlicht werden sollen. Optional können Sie Spalten aus Tabellenartikeln filtern und Artikeleigenschaften angeben.  
  
    -   Optionales Filtern von Zeilen aus Tabellenartikeln. Weitere Informationen finden Sie unter [Filtern von veröffentlichten Daten](filter-published-data.md).  
  
    -   Festlegen des Zeitplans für den Momentaufnahme-Agent.  
  
    -   Angeben der Anmeldeinformationen, unter denen die folgenden Replikations-Agents ausgeführt werden und Verbindungen herstellen:  
  
         \- Momentaufnahme-Agent (für alle Veröffentlichungen)  
  
         \- Protokolllese-Agent (für alle Transaktionsveröffentlichungen)  
  
         \- Warteschlangenlese-Agent für Transaktionsveröffentlichungen, in denen Updates von Abonnements zulässig sind  
  
         Weitere Informationen finden Sie unter [Replication Agent Security Model](../security/replication-agent-security-model.md) und [Replication Security Best Practices](../security/replication-security-best-practices.md).  
  
    -   Optionale Erstellung eines Skripts für die Veröffentlichung. Weitere Informationen finden Sie unter [Scripting Replication](../scripting-replication.md).  
  
    -   Angeben eines Namens für die Veröffentlichung.  
  
##  <a name="TsqlProcedure"></a> Verwenden von Transact-SQL  
 Veröffentlichungen können programmgesteuert mit gespeicherten Replikationsprozeduren erstellt werden. Welche gespeicherten Prozeduren Sie verwenden, hängt vom Typ der zu erstellenden Veröffentlichung ab.  
  
#### <a name="to-create-a-snapshot-or-transactional-publication"></a>So erstellen Sie eine Momentaufnahme- oder Transaktionsveröffentlichung  
  
1.  Führen Sie auf dem Verleger für die Veröffentlichungsdatenbank [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) aus, um die Veröffentlichung der aktuellen Datenbank mit der Momentaufnahme- oder der Transaktionsreplikation zu aktivieren.  
  
2.  Bestimmen Sie bei einer Transaktionsveröffentlichung, ob ein Auftrag des Protokolllese-Agents für die Veröffentlichungsdatenbank existiert. (Dieser Schritt ist für Momentaufnahmeveröffentlichungen nicht erforderlich.)  
  
    -   Wenn bereits ein Auftrag des Protokolllese-Agents für die Veröffentlichungsdatenbank vorhanden ist, fahren Sie mit Schritt 3 fort.  
  
    -   Wenn Sie sich nicht sicher sind, ob ein Protokolllese-Agentauftrag für die Veröffentlichungsdatenbank vorhanden ist, dann führen Sie [sp_helplogreader_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helplogreader-agent-transact-sql) auf dem Verleger für die Veröffentlichungsdatenbank aus.  
  
    -   Wenn das Resultset leer ist, erstellen Sie einen Auftrag des Protokolllese-Agents. Führen Sie auf dem Verleger [sp_addlogreader_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlogreader-agent-transact-sql) aus. Geben Sie die [!INCLUDE[msCoName](../../../includes/msconame-md.md)] -Anmeldeinformationen, unter denen der Agent ausgeführt wird, für **@job_name** und **@password**aktiviert wird. Wenn der Agent zum Herstellen der Verbindung mit dem Verleger die SQL Server-Authentifizierung verwendet, müssen Sie zudem den Wert **0** für **@publisher_security_mode** und die [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Anmeldeinformationen für **@publisher_login** und **@publisher_password**. Fahren Sie mit Schritt 3 fort.  
  
3.  Führen Sie auf dem Verleger [sp_addpublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql) aus. Geben Sie einen Veröffentlichungsnamen für **@publication**, und für die **@repl_freq** Parameter, geben Sie den Wert `snapshot` für eine momentaufnahmeveröffentlichung oder einen Wert von `continuous` für eine transaktionsveröffentlichung. Geben Sie eventuell weitere Veröffentlichungsoptionen an. Dadurch wird die Veröffentlichung definiert.  
  
    > [!NOTE]  
    >  Veröffentlichungsnamen dürfen die folgenden Zeichen nicht enthalten:  
    >   
    >  % * [ ] | : " ? \ / \< >  
  
4.  Führen Sie auf dem Verleger [sp_addpublication_snapshot &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpublication-snapshot-transact-sql) aus. Geben Sie den in Schritt 3 für **@publication** verwendeten Veröffentlichungsnamen und die Windows-Anmeldeinformationen, unter denen der Momentaufnahme-Agent ausgeführt wird, für **@snapshot_job_name** und **@password**aktiviert wird. Wenn der Agent zum Herstellen der Verbindung mit dem Verleger die SQL Server-Authentifizierung verwendet, müssen Sie zudem den Wert **0** für **@publisher_security_mode** und die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Anmeldeinformationen für **@publisher_login** und **@publisher_password**aktiviert wird. Dadurch wird ein Auftrag des Momentaufnahme-Agents für die Veröffentlichung erstellt.  
  
    > [!IMPORTANT]  
    >  Beim Konfigurieren eines Verlegers mit einem Remoteverteiler werden die Werte, die für alle Parameter, einschließlich *job_login* und *job_password*, bereitgestellt werden, als Nur-Text an den Verteiler gesendet. Sie sollten die Verbindung zwischen dem Verleger und dem zugehörigen Remoteverteiler verschlüsseln, bevor Sie diese gespeicherte Prozedur ausführen. Weitere Informationen finden Sie unter [Aktivieren von verschlüsselten Verbindungen zur Datenbank-Engine &amp;#40;SQL Server-Konfigurations-Manager&amp;#41;](../../../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md).  
  
5.  Fügen Sie der Veröffentlichung Artikel hinzu. Weitere Informationen finden Sie unter [Define an Article](define-an-article.md).  
  
6.  Starten Sie den Auftrag des Momentaufnahme-Agents, um die Anfangsmomentaufnahme für diese Veröffentlichung zu generieren. Weitere Informationen finden Sie unter [Create and Apply the Initial Snapshot](../create-and-apply-the-initial-snapshot.md).  
  
#### <a name="to-create-a-merge-publication"></a>So erstellen Sie eine Mergeveröffentlichung  
  
1.  Führen Sie auf dem Verleger [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) aus, um die Veröffentlichung der aktuellen Datenbank mit der Mergereplikation zu aktivieren.  
  
2.  Führen Sie auf dem Verleger für die Veröffentlichungsdatenbank [sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql) aus. Geben Sie einen Veröffentlichungsnamen für **@publication** und eventuell weitere Veröffentlichungsoptionen an. Dadurch wird die Veröffentlichung definiert.  
  
    > [!NOTE]  
    >  Veröffentlichungsnamen dürfen die folgenden Zeichen nicht enthalten:  
    >   
    >  % * [ ] | : " ? \ / \< >  
  
3.  Führen Sie auf dem Verleger [sp_addpublication_snapshot &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpublication-snapshot-transact-sql) aus. Geben Sie den in Schritt 2 für **@publication** verwendeten Veröffentlichungsnamen und die Windows-Anmeldeinformationen, unter denen der Momentaufnahme-Agent ausgeführt wird, für **@snapshot_job_name** und **@password**aktiviert wird. Wenn der Agent zum Herstellen der Verbindung mit dem Verleger die SQL Server-Authentifizierung verwendet, müssen Sie zudem den Wert **0** für **@publisher_security_mode** und die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Anmeldeinformationen für **@publisher_login** und **@publisher_password**aktiviert wird. Dadurch wird ein Auftrag des Momentaufnahme-Agents für die Veröffentlichung erstellt.  
  
    > [!IMPORTANT]  
    >  Beim Konfigurieren eines Verlegers mit einem Remoteverteiler werden die Werte, die für alle Parameter, einschließlich *job_login* und *job_password*, bereitgestellt werden, als Nur-Text an den Verteiler gesendet. Sie sollten die Verbindung zwischen dem Verleger und dem zugehörigen Remoteverteiler verschlüsseln, bevor Sie diese gespeicherte Prozedur ausführen. Weitere Informationen finden Sie unter [Aktivieren von verschlüsselten Verbindungen zur Datenbank-Engine &amp;#40;SQL Server-Konfigurations-Manager&amp;#41;](../../../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md).  
  
4.  Fügen Sie der Veröffentlichung Artikel hinzu. Weitere Informationen finden Sie unter [Define an Article](define-an-article.md).  
  
5.  Starten Sie den Auftrag des Momentaufnahme-Agents, um die Anfangsmomentaufnahme für diese Veröffentlichung zu generieren. Weitere Informationen finden Sie unter [Create and Apply the Initial Snapshot](../create-and-apply-the-initial-snapshot.md).  
  
###  <a name="TsqlExample"></a> Beispiel (Transact-SQL)  
 In diesem Beispiel wird eine Transaktionsveröffentlichung erstellt. Anhand von Skriptvariablen werden Windows-Anmeldeinformationen übergeben, die zur Erstellung von Aufträgen für den Momentaufnahme-Agent und den Protokolllese-Agent erforderlich sind.  
  
 [!code-sql[HowTo#sp_AddTranPub](../../../snippets/tsql/SQL15/replication/howto/tsql/createtranpub.sql#sp_addtranpub)]  
  
 In diesem Beispiel wird eine Mergeveröffentlichung erstellt. Anhand von Skriptvariablen werden Windows-Anmeldeinformationen übergeben, die zur Erstellung des Auftrags für den Momentaufnahme-Agent erforderlich sind.  
  
 [!code-sql[HowTo#sp_AddMergePub](../../../snippets/tsql/SQL15/replication/howto/tsql/createmergepub.sql#sp_addmergepub)]  
  
##  <a name="RMOProcedure"></a> Verwenden von Replikationsverwaltungsobjekten (RMO)  
 Sie können Veröffentlichungen mithilfe von Replikationsverwaltungsobjekten (RMO) programmgesteuert erstellen. Welche RMO-Klassen Sie zum Erstellen von Veröffentlichungen verwenden, hängt vom Typ der zu erstellenden Veröffentlichung ab.  
  
#### <a name="to-create-a-snapshot-or-transactional-publication"></a>So erstellen Sie eine Momentaufnahme- oder Transaktionsveröffentlichung  
  
1.  Erstellen Sie eine Verbindung mit dem Verleger, indem Sie die <xref:Microsoft.SqlServer.Management.Common.ServerConnection>-Klasse verwenden.  
  
2.  Erstellen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.ReplicationDatabase> -Klasse für die Veröffentlichungsdatenbank, legen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> -Eigenschaft auf die Instanz von <xref:Microsoft.SqlServer.Management.Common.ServerConnection> aus Schritt 1 fest, und rufen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> -Methode auf. Wenn <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> gibt `false`, stellen Sie sicher, dass die Datenbank vorhanden ist.  
  
3.  Hat die <xref:Microsoft.SqlServer.Replication.ReplicationDatabase.EnabledTransPublishing%2A>-Eigenschaft den Wert `false`, dann legen Sie ihren Wert auf `true` fest.  
  
4.  Überprüfen Sie für eine Transaktionsveröffentlichung den Wert der <xref:Microsoft.SqlServer.Replication.ReplicationDatabase.LogReaderAgentExists%2A> -Eigenschaft. Wenn diese Eigenschaft ist `true`, ein Protokolllese-Agentauftrag für diese Datenbank bereits vorhanden. Wenn diese Eigenschaft ist `false`, gehen Sie folgendermaßen vor:  
  
    -   Legen Sie die <xref:Microsoft.SqlServer.Replication.IProcessSecurityContext.Login%2A> und <xref:Microsoft.SqlServer.Replication.IProcessSecurityContext.Password%2A> oder <xref:Microsoft.SqlServer.Replication.IProcessSecurityContext.SecurePassword%2A> Felder des <xref:Microsoft.SqlServer.Replication.ReplicationDatabase.LogReaderAgentProcessSecurity%2A> für die Anmeldeinformationen für die [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows-Konto, unter dem der Protokolllese-Agent ausgeführt wird.  
  
        > [!NOTE]  
        >  Festlegen von <xref:Microsoft.SqlServer.Replication.ReplicationDatabase.LogReaderAgentProcessSecurity%2A> ist nicht erforderlich, beim Erstellen der Veröffentlichung von einem Mitglied der `sysadmin` festen Serverrolle "". In diesem Fall nimmt der Agent die Identität des SQL Server-Agent-Kontos an. Weitere Informationen finden Sie unter [Replication Agent Security Model](../security/replication-agent-security-model.md).  
  
    -   (Optional) Legen Sie die Felder <xref:Microsoft.SqlServer.Replication.ConnectionSecurityContext.SqlStandardLogin%2A> und <xref:Microsoft.SqlServer.Replication.ConnectionSecurityContext.SqlStandardPassword%2A> oder <xref:Microsoft.SqlServer.Replication.ConnectionSecurityContext.SecureSqlStandardPassword%2A> von <xref:Microsoft.SqlServer.Replication.ReplicationDatabase.LogReaderAgentPublisherSecurity%2A> fest, wenn Sie die SQL Server-Authentifizierung zum Herstellen einer Verbindung mit dem Verleger verwenden.  
  
    -   Rufen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationDatabase.CreateLogReaderAgent%2A> -Methode auf, um den Protokolllese-Agentauftrag für die Datenbank zu erstellen.  
  
5.  Erstellen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.TransPublication> -Klasse, und legen Sie die folgenden Eigenschaften für dieses Objekt fest:  
  
    -   Die <xref:Microsoft.SqlServer.Management.Common.ServerConnection> aus Schritt 1 für <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.  
  
    -   Den Namen der veröffentlichten Datenbank für <xref:Microsoft.SqlServer.Replication.Publication.DatabaseName%2A>.  
  
    -   Einen Namen für die Veröffentlichung für <xref:Microsoft.SqlServer.Replication.Publication.Name%2A>.  
  
    -   Einen <xref:Microsoft.SqlServer.Replication.PublicationType> , entweder <xref:Microsoft.SqlServer.Replication.PublicationType.Transactional> oder <xref:Microsoft.SqlServer.Replication.PublicationType.Snapshot>.  
  
    -   Die Felder <xref:Microsoft.SqlServer.Replication.IProcessSecurityContext.Login%2A> und <xref:Microsoft.SqlServer.Replication.IProcessSecurityContext.Password%2A> von <xref:Microsoft.SqlServer.Replication.Publication.SnapshotGenerationAgentProcessSecurity%2A>, um die Anmeldeinformationen für das Windows-Konto bereitzustellen, unter dem der Momentaufnahme-Agent ausgeführt wird. Dieses Konto wird auch verwendet, wenn der Momentaufnahme-Agent Verbindungen mit dem lokalen Verteiler herstellt, sowie für alle Remoteverbindungen mithilfe der Windows-Authentifizierung.  
  
        > [!NOTE]  
        >  Festlegen von <xref:Microsoft.SqlServer.Replication.Publication.SnapshotGenerationAgentProcessSecurity%2A> ist nicht erforderlich, beim Erstellen der Veröffentlichung von einem Mitglied der `sysadmin` festen Serverrolle "". In diesem Fall nimmt der Agent die Identität des SQL Server-Agent-Kontos an. Weitere Informationen finden Sie unter [Replication Agent Security Model](../security/replication-agent-security-model.md).  
  
    -   (Optional) Legen Sie die Felder <xref:Microsoft.SqlServer.Replication.ConnectionSecurityContext.SqlStandardLogin%2A> und <xref:Microsoft.SqlServer.Replication.ConnectionSecurityContext.SqlStandardPassword%2A> oder <xref:Microsoft.SqlServer.Replication.ConnectionSecurityContext.SecureSqlStandardPassword%2A> von <xref:Microsoft.SqlServer.Replication.Publication.SnapshotGenerationAgentPublisherSecurity%2A> fest, wenn Sie die SQL Server-Authentifizierung zum Herstellen einer Verbindung mit dem Verleger verwenden.  
  
    -   (Optional) Verwenden Sie den inklusiven logischen OR-Operator (`|` in Visual C# und `Or` in Visual Basic) und den exklusiven logischen OR-Operator (`^` in Visual C# und `Xor` in Visual Basic), um die <xref:Microsoft.SqlServer.Replication.PublicationAttributes>-Werte für die <xref:Microsoft.SqlServer.Replication.Publication.Attributes%2A>-Eigenschaft festzulegen.  
  
    -   (Optional) Den Namen des Verlegers für <xref:Microsoft.SqlServer.Replication.TransPublication.PublisherName%2A> , wenn der Verleger ein Nicht-SQL Server-Verleger ist.  
  
6.  Rufen Sie die <xref:Microsoft.SqlServer.Replication.Publication.Create%2A>-Methode auf, um die Veröffentlichung zu erstellen.  
  
    > [!IMPORTANT]  
    >  Beim Konfigurieren eines Verlegers mit einem Remoteverteiler werden die Werte, die für alle Eigenschaften einschließlich <xref:Microsoft.SqlServer.Replication.Publication.SnapshotGenerationAgentProcessSecurity%2A>bereitgestellt werden, als Nur-Text an den Verteiler gesendet. Sie sollten die Verbindung zwischen dem Verleger und dem zugehörigen Remoteverteiler verschlüsseln, bevor Sie die <xref:Microsoft.SqlServer.Replication.Publication.Create%2A>-Methode aufrufen. Weitere Informationen finden Sie unter [Aktivieren von verschlüsselten Verbindungen zur Datenbank-Engine &amp;#40;SQL Server-Konfigurations-Manager&amp;#41;](../../../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md).  
  
7.  Rufen Sie die <xref:Microsoft.SqlServer.Replication.Publication.CreateSnapshotAgent%2A>-Methode auf, um den Momentaufnahme-Agentauftrag für die Veröffentlichung zu erstellen.  
  
#### <a name="to-create-a-merge-publication"></a>So erstellen Sie eine Mergeveröffentlichung  
  
1.  Erstellen Sie eine Verbindung mit dem Verleger, indem Sie die <xref:Microsoft.SqlServer.Management.Common.ServerConnection> -Klasse verwenden.  
  
2.  Erstellen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.ReplicationDatabase> -Klasse für die Veröffentlichungsdatenbank, legen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> -Eigenschaft auf die Instanz von <xref:Microsoft.SqlServer.Management.Common.ServerConnection> aus Schritt 1 fest, und rufen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> -Methode auf. Wenn <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> gibt `false`, stellen Sie sicher, dass die Datenbank vorhanden ist.  
  
3.  Wenn <xref:Microsoft.SqlServer.Replication.ReplicationDatabase.EnabledMergePublishing%2A> Eigenschaft `false`, legen Sie es auf `true`, und rufen Sie <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A>.  
  
4.  Erstellen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.MergePublication> -Klasse, und legen Sie die folgenden Eigenschaften für dieses Objekt fest:  
  
    -   Die <xref:Microsoft.SqlServer.Management.Common.ServerConnection> aus Schritt 1 für <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.  
  
    -   Den Namen der veröffentlichten Datenbank für <xref:Microsoft.SqlServer.Replication.Publication.DatabaseName%2A>.  
  
    -   Einen Namen für die Veröffentlichung für <xref:Microsoft.SqlServer.Replication.Publication.Name%2A>.  
  
    -   Die Felder <xref:Microsoft.SqlServer.Replication.IProcessSecurityContext.Login%2A> und <xref:Microsoft.SqlServer.Replication.IProcessSecurityContext.Password%2A> von <xref:Microsoft.SqlServer.Replication.Publication.SnapshotGenerationAgentProcessSecurity%2A> , um die Anmeldeinformationen für das Windows-Konto bereitzustellen, unter dem der Momentaufnahme-Agent ausgeführt wird. Dieses Konto wird auch verwendet, wenn der Momentaufnahme-Agent Verbindungen mit dem lokalen Verteiler herstellt, sowie für alle Remoteverbindungen mithilfe der Windows-Authentifizierung.  
  
        > [!NOTE]  
        >  Festlegen von <xref:Microsoft.SqlServer.Replication.Publication.SnapshotGenerationAgentProcessSecurity%2A> ist nicht erforderlich, beim Erstellen der Veröffentlichung von einem Mitglied der `sysadmin` festen Serverrolle "". Weitere Informationen finden Sie unter [Replication Agent Security Model](../security/replication-agent-security-model.md).  
  
    -   (Optional) Verwenden Sie den inklusiven logischen OR-Operator (`|` in Visual C# und `Or` in Visual Basic) und den exklusiven logischen OR-Operator (`^` in Visual C# und `Xor` in Visual Basic), um die <xref:Microsoft.SqlServer.Replication.PublicationAttributes>-Werte für die <xref:Microsoft.SqlServer.Replication.Publication.Attributes%2A>-Eigenschaft festzulegen.  
  
5.  Rufen Sie die <xref:Microsoft.SqlServer.Replication.Publication.Create%2A> -Methode auf, um die Veröffentlichung zu erstellen.  
  
    > [!IMPORTANT]  
    >  Beim Konfigurieren eines Verlegers mit einem Remoteverteiler werden die Werte, die für alle Eigenschaften einschließlich <xref:Microsoft.SqlServer.Replication.Publication.SnapshotGenerationAgentProcessSecurity%2A>bereitgestellt werden, als Nur-Text an den Verteiler gesendet. Sie sollten die Verbindung zwischen dem Verleger und dem zugehörigen Remoteverteiler verschlüsseln, bevor Sie die <xref:Microsoft.SqlServer.Replication.Publication.Create%2A>-Methode aufrufen. Weitere Informationen finden Sie unter [Aktivieren von verschlüsselten Verbindungen zur Datenbank-Engine &amp;#40;SQL Server-Konfigurations-Manager&amp;#41;](../../../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md).  
  
6.  Rufen Sie die <xref:Microsoft.SqlServer.Replication.Publication.CreateSnapshotAgent%2A> -Methode auf, um den Momentaufnahme-Agentauftrag für die Veröffentlichung zu erstellen.  
  
###  <a name="PShellExample"></a> Beispiele (RMO)  
 In diesem Beispiel wird die AdventureWorks-Datenbank für Transaktionsveröffentlichung aktiviert, ein Protokolllese-Agentauftrag definiert und die AdvWorksProductTran-Veröffentlichung erstellt. Für diese Veröffentlichung muss ein Artikel definiert sein. Die Anmeldeinformationen für das Windows-Konto, die für die Erstellung des Protokolllese- und des Momentaufnahme-Agentauftrags erforderlich sind, werden zur Laufzeit übergeben. Informationen darüber, wie RMO verwendet wird, um Momentaufnahme- und Transaktionsartikel zu definieren, finden Sie unter [Define an Article](define-an-article.md).  
  
 [!code-csharp[HowTo#rmo_CreateTranPub](../../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_createtranpub)]  
  
 [!code-vb[HowTo#rmo_vb_CreateTranPub](../../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_createtranpub)]  
  
 In diesem Beispiel wird die AdventureWorks-Datenbank für Mergepublishing aktiviert und die AdvWorksSalesOrdersMerge-Veröffentlichung erstellt. Für diese Veröffentlichung müssen ebenfalls Artikel definiert sein. Die Anmeldeinformationen für das Windows-Konto, die für die Erstellung des Momentaufnahme-Agentauftrags erforderlich sind, werden zur Laufzeit übergeben. Informationen darüber, wie RMO verwendet wird, um Mergeartikel zu definieren, finden Sie unter [Define an Article](define-an-article.md).  
  
 [!code-csharp[HowTo#rmo_CreateMergePub](../../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_createmergepub)]  
  
 [!code-vb[HowTo#rmo_vb_CreateMergePub](../../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_createmergepub)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von sqlcmd mit Skriptvariablen](../../scripting/sqlcmd-use-with-scripting-variables.md)   
 [Veröffentlichen von Daten und Datenbankobjekten](publish-data-and-database-objects.md)   
 [Replication Management Objects Concepts](../concepts/replication-management-objects-concepts.md)   
 [Define an Article](define-an-article.md)   
 [Anzeigen und Ändern von Veröffentlichungseigenschaften](view-and-modify-publication-properties.md)   
 [Verteilung konfigurieren](../configure-distribution.md)   
 [Schützen des Verteilers](../security/secure-the-distributor.md)   
 [Sichern des Verlegers](../security/secure-the-publisher.md)  
  
  