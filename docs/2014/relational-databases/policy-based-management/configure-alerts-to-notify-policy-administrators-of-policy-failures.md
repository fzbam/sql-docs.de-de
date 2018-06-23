---
title: Konfigurieren von Warnungen zur Benachrichtigung von Richtlinienadministratoren bei Richtlinienfehlern | Microsoft-Dokumentation
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
- Policy-Based Management, configure alerts
ms.assetid: e8e60159-d5b0-49d5-91f3-af8e9cb994c1
caps.latest.revision: 6
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 4b40bdea995e10e799b1280a2e987a8c55f8fbd8
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36047831"
---
# <a name="configure-alerts-to-notify-policy-administrators-of-policy-failures"></a>Konfigurieren von Warnungen zur Benachrichtigung von Richtlinienadministratoren bei Richtlinienfehlern
  Wenn Richtlinien der richtlinienbasierten Verwaltung in einem der drei automatisierten Auswertungsmodi ausgeführt werden, wird bei einem Richtlinienverstoß eine Meldung im Ereignisprotokoll aufgezeichnet. Wenn Sie bei Aufzeichnung einer solchen Meldung im Ereignisprotokoll benachrichtigt werden möchten, können Sie eine Warnung erstellen, die die Meldung erkennt und eine Aktion ausführt. Die Warnung sollte die Meldungen wie in der folgenden Tabelle gezeigt erkennen.  
  
|Ausführungsmodus|Meldungsnummer|  
|--------------------|--------------------|  
|Bei Änderung - Verhindern<br /><br /> (wenn automatisch)|34050|  
|Bei Änderung - Verhindern<br /><br /> (wenn bedarfsgesteuert)|34051|  
|Nach Zeitplan|34052|  
|Bei Änderung|34053|  
  
 Wie Sie eine Warnung einrichten können, um auf Fehlermeldungen der richtlinienbasierten Verwaltung zu reagieren, wird in den folgenden Themen erläutert:  
  
-   [Erstellen eines Operators](../../ssms/agent/create-an-operator.md)  
  
-   [Erstellen einer Warnung mithilfe einer Fehlernummer](../../ssms/agent/create-an-alert-using-an-error-number.md)  
  
-   [Zuweisen von Warnungen zu einem Operator](../../ssms/agent/assign-alerts-to-an-operator.md)  
  
## <a name="permissions"></a>Berechtigungen  
 Bei Bedarf ausgewertete Richtlinien werden im Sicherheitskontext des Benutzers ausgeführt. Um in das Fehlerprotokoll schreiben zu können, muss der Benutzer über die ALTER TRACE-Berechtigung verfügen oder Mitglied der festen Serverrolle sysadmin sein. Bei Auswertung einer Richtlinie durch einen Benutzer mit niedrigeren Berechtigungen werden eventuell erkannte Fehler nicht in das Ereignisprotokoll geschrieben und lösen keine Warnung aus.  
  
 Die automatisierten Ausführungsmodi werden als Mitglied der Rolle sysadmin ausgeführt. Dies ermöglicht es, dass eventuell erkannte Fehler für die Richtlinie in das Fehlerprotokoll geschrieben werden und eine Warnung auslösen.  
  
## <a name="additional-considerations-about-alerts"></a>Weitere Überlegungen zu Warnungen  
 Beachten Sie die folgenden weiteren Überlegungen zu Warnungen:  
  
-   Warnungen werden nur für Richtlinien ausgelöst, die aktiviert sind. Da **bedarfsgesteuerte** Richtlinien nicht aktiviert werden können, werden Warnungen nicht für Richtlinien ausgelöst, die bedarfsgesteuert ausgeführt werden.  
  
-   Wenn die Aktion, die Sie ausführen möchten, das Senden einer E-Mail umfasst, müssen Sie ein E-Mail-Konto konfigurieren. Es empfiehlt sich die Verwendung von Datenbank-E-Mail. Weitere Informationen zum Einrichten von Datenbank-E-Mail finden Sie unter [Erstellen eines Kontos für Datenbank-E-Mail](../database-mail/create-a-database-mail-account.md).  
  
  