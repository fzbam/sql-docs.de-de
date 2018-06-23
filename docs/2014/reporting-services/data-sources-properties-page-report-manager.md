---
title: Datenquellen (Eigenschaftenseite) (Berichts-Manager) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f37edda0-19e6-489e-b544-8751fa6b6cfb
caps.latest.revision: 35
author: markingmyname
ms.author: maghan
manager: mblythe
ms.openlocfilehash: 68279fffed6d42fd60ce6a3665eeaf3b0590aae6
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36048676"
---
# <a name="data-sources-properties-page-report-manager"></a>Datenquellen (Eigenschaftenseite) (Berichts-Manager)
  Mithilfe der Eigenschaftenseite "Datenquellen" können Sie definieren, wie der aktuelle Bericht eine Verbindung mit einer externen Datenquelle herstellt. Sie können die ursprünglich mit dem Bericht veröffentlichten Informationen zur Datenquellenverbindung überschreiben. Falls mehrere Datenquellen in einem Bericht verwendet werden, hat jede Datenquelle einen eigenen Abschnitt auf der Eigenschaftenseite. Datenquellen werden in der Reihenfolge aufgeführt, in der sie im Bericht definiert sind.  
  
 Wenn Sie eine Datenquelle zur Verwendung im Bericht angeben, können Sie eine freigegebene Datenquelle verwenden, die unabhängig von den Berichten, in denen sie verwendet wird, erstellt und verwaltet wird. Wenn Sie kein freigegebenes Datenquellenelement verwenden möchten, können Sie eine Datenquellenverbindung definieren, die mit dem Bericht verwendet wird.  
  
## <a name="navigation"></a>Navigation  
 Verwenden Sie folgendes Verfahren, um zu dieser Position in der Benutzeroberfläche zu navigieren.  
  
### <a name="to-open-the-data-sources-properties-page"></a>So öffnen Sie die Eigenschaftenseite 'Datenquellen'  
  
1.  Öffnen Sie den Berichts-Manager, und suchen Sie den Bericht, für den Sie eine Datenquelle auswählen möchten.  
  
2.  Zeigen Sie auf den Bericht, und klicken Sie auf den Dropdownpfeil.  
  
3.  Klicken Sie im Dropdownmenü auf **Verwalten**. Dadurch wird die Seite **Allgemeine Eigenschaften** für den Bericht geöffnet.  
  
4.  Wählen Sie die Registerkarte **Datenquellen** .  
  
## <a name="options"></a>Tastatur  
 **Eine freigegebene Datenquelle**  
 Geben Sie eine freigegebene Datenquelle zur Verwendung im Bericht an. Weitere Informationen zum Erstellen einer neuen Datenquelle finden Sie unter [erstellen, löschen oder Ändern einer freigegebenen Datenquelle &#40;Berichts-Manager&#41;](../../2014/reporting-services/create-delete-or-modify-a-shared-data-source-report-manager.md).  
  
 **Durchsuchen**  
 Klicken Sie auf **Durchsuchen** , um die Seite zum Auswählen der Datenquelle zu öffnen, mit deren Hilfe Sie eine freigegebene Datenquelle auswählen können. Weitere Informationen finden Sie unter [Seite zur Auswahl der Datenquelle &#40;Berichts-Manager&#41;](../../2014/reporting-services/data-source-selection-page-report-manager.md).  
  
 **Eine benutzerdefinierte Datenquelle**  
 Geben Sie die Art des Verbindungsaufbaus zur Datenquelle an.  
  
 Die folgenden Optionen können beim Angeben einer benutzerdefinierten Datenquellenverbindung verwendet werden.  
  
 **Datenquellentyp**  
 Geben Sie die Datenverarbeitungserweiterung an, die zum Verarbeiten von Daten aus der Datenquelle verwendet wird. Die Liste der integrierten datenerweiterungen finden Sie [von Reporting Services unterstützte Datenquellen &#40;SSRS&#41;](create-deploy-and-manage-mobile-and-paginated-reports.md). Weitere Datenverarbeitungserweiterungen können von Drittanbietern zur Verfügung stehen.  
  
 **Verbindungszeichenfolge**  
 Geben Sie die Verbindungszeichenfolge an, die vom Berichtsserver zum Herstellen der Verbindung mit der Datenquelle verwendet wird. Der Verbindungstyp bestimmt die Syntax, die Sie verwenden sollten. So ist z.B. eine Verbindungszeichenfolge für die XML-Datenverarbeitungserweiterung eine URL zu einem XML-Dokument. In den meisten Fällen gibt eine typische Verbindungszeichenfolge den Datenbankserver und die Datendatei an. Im folgenden Beispiel wird eine Verbindungszeichenfolge erläutert, die für die Verbindung mit einer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Datenbank mit dem Namen "MyData" verwendet wird:  
  
 `data source=<a SQL Server instance>;initial catalog=MyData`  
  
 Eine Verbindungszeichenfolge kann als ein Ausdruck konfiguriert werden, sodass Sie die Datenquelle zur Laufzeit angeben können. Datenquellenausdrücke für den Bericht werden im Berichts-Designer definiert. Datenquellenausdrücke können im Berichts-Manager nicht definiert, angezeigt oder geändert werden. Sie können einen Datenquellenausdruck jedoch ersetzen, indem Sie auf **Standardwert überschreiben** klicken, um eine statische Verbindungszeichenfolge einzugeben. Wenn Sie zurück zum Ausdruck wechseln möchten, klicken Sie auf **Standardwert wiederherstellen**. Der Berichtsserver speichert die ursprüngliche Verbindungszeichenfolge für den Fall, dass Sie sie wiederherstellen müssen. Um Datenquellenausdrücke verwenden zu können, müssen Sie die ursprünglich im Bericht veröffentlichten Informationen zur Datenquellenverbindung verwenden. Freigegebene Datenquellen unterstützen die Verwendung von Ausdrücken in der Verbindungszeichenfolge nicht.  
  
 **Verbindung herstellen über**  
 Gibt Optionen an, die bestimmen, wie Anmeldeinformationen abgerufen werden.  
  
> [!IMPORTANT]  
>  Falls die Verbindungszeichenfolge Anmeldeinformationen enthält, werden die in diesem Abschnitt festgelegten Optionen und Werte ignoriert. Beachten Sie, dass bei Angabe der Anmeldeinformationen in der Verbindungszeichenfolge die Werte für alle Benutzer, die diese Seite anzeigen, in Klartext angezeigt werden.  
  
 **Bereitgestellte Anmeldeinformationen vom Benutzer den Bericht ausführt**  
 Jeder Benutzer muss einen Benutzernamen und ein Kennwort für den Zugriff auf die Datenquelle eingeben. Sie können den Text der Eingabeaufforderung definieren, in der die Benutzeranmeldeinformationen angefordert werden. Die Standardtextzeichenfolge lautet: "Geben Sie einen Benutzernamen und ein Kennwort für den Zugriff auf die Datenquelle ein".  
  
 Aktivieren Sie das Kontrollkästchen **Als Windows-Anmeldeinformationen verwenden, wenn eine Verbindung mit der Datenquelle hergestellt wird** , wenn es sich bei den durch den Benutzer bereitgestellten Informationen um Anmeldeinformationen der Windows-Authentifizierung handelt. Wählen Sie dieses Kontrollkästchen nicht, wenn Sie die Datenbankauthentifizierung verwenden (z. B. [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentifizierung).  
  
 **Anmeldeinformationen sind sicher auf dem Berichtsserver gespeichert.**  
 Speichern Sie einen verschlüsselten Benutzernamen und ein Kennwort in der Berichtsserver-Datenbank. Wählen Sie diese Option aus, um einen Bericht unbeaufsichtigt auszuführen (z. B. Berichte, die durch Zeitpläne initiiert werden oder durch Ereignisse anstelle einer Benutzeraktion). Wenn Sie die Standardsicherheitseinstellungen verwenden, muss der Benutzername ein Windows-Domänenkonto sein. Geben Sie das Konto im folgenden Format: \<Domäne >\\< Benutzername\>. Das von Ihnen angegebene Konto muss über lokale Systemadministratorberechtigungen auf dem Computer verfügen, der die von dem Bericht verwendete Datenquelle hostet.  
  
 Aktivieren Sie das Kontrollkästchen **Als Windows-Anmeldeinformationen verwenden, wenn eine Verbindung mit der Datenquelle hergestellt wird** , wenn es sich bei den Informationen um Anmeldeinformationen der Windows-Authentifizierung handelt. Wählen Sie dieses Kontrollkästchen nicht, wenn Sie die Datenbankauthentifizierung verwenden (z. B. [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentifizierung).  
  
 Wählen Sie die Option **Nach dem Herstellen einer Verbindung mit der Datenquelle die Identität des authentifizierten Benutzers annehmen** aus, um die Delegierung von Anmeldeinformationen zuzulassen. Dies ist jedoch nur möglich, wenn eine Datenquelle den Identitätswechsel unterstützt. Für [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Datenbanken, die diese Option wird der SETUSER-Funktion.  
  
> [!TIP]  
>  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]unterstützt nur Windows-Anmeldeinformationen ein. Daher wählen, sowohl die Optionen "als Windows-Anmeldeinformationen beim Verbinden mit der Datenquelle" und "Identität des authentifizierten Benutzers, nachdem eine Verbindung mit der Datenquelle hergestellt wurde" für eine [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Datenquelle.  
  
 **Integrierte Sicherheit von Windows**  
 Verwenden Sie die Windows-Anmeldeinformationen des aktuellen Benutzers für den Zugriff auf die Datenquelle. Wählen Sie diese Option aus, wenn die für den Zugriff auf die Datenquelle verwendeten Anmeldeinformationen mit denen übereinstimmen, die zum Anmelden an der Netzwerkdomäne verwendet werden. Diese Option kann am besten verwendet werden, wenn die Kerberos-Authentifizierung für die Domäne aktiviert ist oder wenn sich die Datenquelle auf demselben Computer wie der Berichtsserver befindet. Wenn Kerberos nicht aktiviert ist, können die Windows-Anmeldeinformationen an einen anderen Computer weitergegeben werden. Falls weitere Computerverbindungen erforderlich sind, wird eine Fehlermeldung statt der erwarteten Daten zurückgegeben.  
  
 Ein Berichtsserveradministrator kann die Verwendung der integrierten Sicherheit von Windows deaktivieren, um auf Berichtsdatenquellen zugreifen zu können. Wenn dieser Wert ausgegraut ist, ist die Funktion nicht verfügbar.  
  
 Verwenden Sie diese Option nicht, wenn Sie vorhaben, diesen Bericht zu planen oder zu abonnieren. Die geplante oder unbeaufsichtigte Berichtsverarbeitung benötigt Anmeldeinformationen, die ohne Benutzereingaben oder den Sicherheitskontext des aktuellen Benutzers abgerufen werden können. Diese Möglichkeit bieten nur gespeicherte Anmeldeinformationen. Aus diesem Grund hindert Sie der Berichtsserver daran, die Ausführung eines Berichts oder eines Abonnements zu planen, wenn der Bericht für den Anmeldeinformationstyp der integrierten Windows-Sicherheit konfiguriert ist. Wenn Sie diese Option für einen Bericht wählen, der bereits abonniert ist oder geplante Vorgänge aufweist, werden das Abonnement und die geplanten Vorgänge beendet.  
  
 **Anmeldeinformationen sind nicht erforderlich**  
 Geben Sie an, dass keine Anmeldeinformationen für den Zugriff auf die Datenquelle erforderlich sind. Beachten Sie, dass diese Option keine Auswirkungen hat, wenn für die Datenquelle eine Benutzeranmeldung erforderlich ist. Sie sollten diese Option nur auswählen, wenn für die Datenquellenverbindung keine Benutzeranmeldeinformationen erforderlich sind.  
  
 Um diese Option verwenden zu können, müssen Sie vorher das unbeaufsichtigte Ausführungskonto für die Bereitstellung des Berichtsservers konfiguriert haben. Das unbeaufsichtigte Ausführungskonto wird zum Herstellen der Verbindung mit externen Datenquellen verwendet, wenn keine anderen Quellen für Anmeldeinformationen verfügbar sind. Wenn Sie diese Option angeben und das Konto nicht konfiguriert ist, schlägt die Verbindung mit der Berichtsdatenquelle fehl, und der Bericht wird nicht verarbeitet.  Weitere Informationen zu diesem Konto finden Sie unter [Konfigurieren des unbeaufsichtigten Ausführungskontos &#40;SSRS-Konfigurations-Manager&#41;](install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).  
  
 **Anwenden**  
 Klicken Sie auf diese Schaltfläche, um die Änderungen zu speichern.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwalten von Berichtsdatenquellen](report-data/manage-report-data-sources.md)   
 [Angeben der Anmeldeinformationen und Verbindungsinformationen für Berichtsdatenquellen](report-data/specify-credential-and-connection-information-for-report-data-sources.md)   
 [Berichts-Manager (F1-Hilfe)](../../2014/reporting-services/report-manager-f1-help.md)  
  
  