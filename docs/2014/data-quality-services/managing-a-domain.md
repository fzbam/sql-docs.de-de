---
title: Verwalten einer Domäne | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- data-quality-services
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5ab71a3-0dac-45b1-be8e-93bf7e0e03ce
caps.latest.revision: 12
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: 72b2400e8a953490d1650a8e435c6b353c660445
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36048815"
---
# <a name="managing-a-domain"></a>Verwalten einer Domäne
  In diesem Thema wird die Verwendung von Domänen in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) beschrieben. Eine Domäne enthält eine semantische Darstellung der Daten in einem bestimmten Feld in der Datenquelle, die analysiert werden soll. Eine Domäne ist Teil einer Wissensdatenbank, die Sie für eine Datenquelle erstellen, und das Wissen, das Sie durch Analysieren einer Beispieldatenquelle oder dem Importieren von Daten erhalten, wird den in der Wissensdatenbank definierten Domänen hinzugefügt. Das Wissen in diesen Domänen wird später verwendet, um Bereinigungen und Abgleiche in einem Data Quality-Projekt auszuführen. Domänen sind der Kern aller Aktivitäten in Data Quality Services.  
  
 Eine Domäne wird einem Datenquellenfeld zugeordnet und in den Wissensermittlungs-, Domänenverwaltungs- und Abgleichsaktivitäten aufgefüllt. Wie Sie Daten aus der Datenquelle und den Ausgabedaten in einen Bericht laden, wird in den Domäneneigenschaften definiert. Wenn Sie einen Verweisdatenanbieter für das Bereinigen von Daten verwenden, fügen Sie einen Verweisdatendienst an eine Einzel- oder Verbunddomäne an. Sie erstellen Regeln, die auf die Daten in einer Domäne angewendet werden, und Sie können begriffsbasierte Beziehungen für eine Domäne erstellen. Sie können Daten in der Domäne anzeigen und korrigieren.  
  
 Sie können auch eine Verbunddomäne erstellen, die aus zwei oder mehr einzelnen Domänen besteht, von denen jede Wissen über allgemeine Daten enthält. Weitere Informationen finden Sie unter [Verwalten einer Verbunddomäne](../../2014/data-quality-services/managing-a-composite-domain.md).  
  
## <a name="domain-properties"></a>Domäneneigenschaften  
 Wenn Sie eine Domäne erstellen, haben Sie die folgenden Optionen zum Auffüllen der Domäne aus den Quelldaten und zur Ausgabe der Domänenwerte. Weitere Informationen finden Sie unter [Festlegen von Domäneneigenschaften](../../2014/data-quality-services/set-domain-properties.md).  
  
-   Wählen Sie den Typ der Daten aus, mit denen Sie die Domäne auffüllen. Informationen zu Datentypen, die für jeden Domänendatentyp unterstützt wurden, finden Sie unter [Unterstützte SQL Server- und SSIS-Datentypen für DQS-Domänen](../../2014/data-quality-services/supported-sql-server-and-ssis-data-types-for-dqs-domains.md).  
  
-   Geben Sie an, dass nur führende Werte, nicht ihre Synonyme, von der Domäne ausgegeben werden.  
  
-   Geben Sie an, dass Domänenwerte, je nach Datentyp, in einem bestimmten Format ausgegeben werden.  
  
-   Wenn der Datentyp eine Zeichenfolge ist, können Sie die Zeichenfolge normalisieren, indem Sie Sonderzeichen entfernen, wenn die Zeichenfolge aus der Datenquelle in die Domäne geladen wird.  
  
-   Wenn der Datentyp eine Zeichenfolge ist, können Sie die DQS-Rechtschreibprüfung ausführen, um die Syntax, Rechtschreibung und Satzstruktur der Zeichenfolge zu überprüfen und potenzielle Fehler auf der Seite **Domänenwerte** der **Domänenverwaltung**anzugeben. Dies schließt das Angeben der Sprache ein, die die Rechtschreibprüfung verwendet.  
  
-   Wenn der Datentyp eine Zeichenfolge ist, können Sie angeben, dass DQS keine Syntaxfehler identifiziert, wenn Sie wissen, dass keine Syntaxfehler in Zeichenfolgen auftreten.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 Durch das Verwenden einer Domäne erhalten Sie folgende Möglichkeiten:  
  
|||  
|-|-|  
|Erstellen einer semantischen Darstellung für ein Datenfeld mit einem bestimmten Datentyp, Angeben, wie die Domäne aufgefüllt wird, und Formatieren der Ausgabe der Domäne|[Erstellen einer Domäne](../../2014/data-quality-services/create-a-domain.md)|  
|Verknüpfen einer Domäne mit einer anderen Domäne und Aktivieren des gemeinsamen Nutzens der gleichen Einstellungen und die Werte|[Erstellen einer verknüpften Domäne](../../2014/data-quality-services/create-a-linked-domain.md)|  
|Anfügen eines Verweisdatendiensts an eine Einzel- oder Verbunddomäne|[Anfügen einer Domäne oder Verbunddomäne an Verweisdaten](../../2014/data-quality-services/attach-a-domain-or-composite-domain-to-reference-data.md)|  
|Ändern und Erweitern der Werte in einer Wissensdatenbank|[Ändern von Domänenwerten](../../2014/data-quality-services/change-domain-values.md)|  
|Verwenden von Überprüfungs- und Standardisierungsregeln|[Erstellen einer Domänenregel](../../2014/data-quality-services/create-a-domain-rule.md)|  
|Verwenden von Beziehungen zum Korrigieren eines Begriffs, der Teil eines Werts in einer Domäne ist|[Erstellen von begriffsbasierten Beziehungen](../../2014/data-quality-services/create-term-based-relations.md)|  
|Abschließen, Schließen oder Abbrechen der Domänenverwaltungsaktivität|[Beenden der Domänenverwaltungsaktivität](../../2014/data-quality-services/end-the-domain-management-activity.md)|  
  
## <a name="related-tasks"></a>Related Tasks  
  
|Taskbeschreibung|Thema|  
|----------------------|-----------|  
|Erstellen einer Wissensdatenbank durch das Ausführen der Wissensermittlung und interaktives Verwalten von Wissen|[Aufbau einer Wissensdatenbank](../../2014/data-quality-services/building-a-knowledge-base.md)|  
|Importieren von Wissen in oder Exportieren von Wissen aus einer Wissensdatenbank.|[Importieren und Exportieren von Wissen](../../2014/data-quality-services/importing-and-exporting-knowledge.md)|  
|Erstellen einer Verbunddomäne und Hinzufügen von Wissen zur Domäne.|[Verwalten einer Verbunddomäne](../../2014/data-quality-services/managing-a-composite-domain.md)|  
  
  