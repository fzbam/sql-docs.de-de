---
title: ODBC-Verbindungs-Manager | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connections [Integration Services], ODBC
- ODBC connection manager
- data sources [Integration Services], connections
- connection managers [Integration Services], ODBC
ms.assetid: e8c77aa7-6772-485e-918e-cef9eeb18c58
caps.latest.revision: 41
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: 9453dc6e402fce60e1f4f440d84f882e513abea7
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36060087"
---
# <a name="odbc-connection-manager"></a>ODBC-Verbindungs-Manager
  Mit einem ODBC-Verbindungs-Manager kann ein Paket eine Verbindung mit einer Reihe von Datenbank-Managementsystemen mithilfe der ODBC-Spezifikation (Open Database Connectivity) herstellen.  
  
 Wenn Sie einem Paket eine ODBC-Verbindung hinzufügen und die Eigenschaften des Verbindungs-Managers festlegen, erstellt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] einen Verbindungs-Manager und fügt der `Connections`-Auflistung des Pakets den Verbindungs-Manager hinzu. Zur Laufzeit wird der Verbindungs-Manager als physische ODBC-Verbindung aufgelöst.  
  
 Die `ConnectionManagerType` des Verbindungs-Managers ist-Eigenschaftensatz auf `ODBC`.  
  
 Es gibt folgende Möglichkeiten, um den ODBC-Verbindungs-Manager zu konfigurieren:  
  
-   Geben Sie eine Verbindungszeichenfolge an, die auf einen Benutzer- oder System-Datenquellennamen verweist.  
  
-   Geben Sie den Server für die Verbindungsherstellung an.  
  
-   Geben Sie an, ob die Verbindung zur Laufzeit beibehalten wird.  
  
## <a name="configuration-of-the-odbc-connection-manager"></a>Konfiguration des ODBC-Verbindungs-Managers  
 Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.  
  
 Klicken Sie auf das folgende Thema, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen können:  
  
-   [ODBC-Verbindungs-Manager: Referenz zur Benutzeroberfläche](../odbc-connection-manager-ui-reference.md)  
  
 Informationen zum programmgesteuerten Konfigurieren eines Verbindungs-Managers finden Sie unter <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> und [Verbindungen programmgesteuert hinzufügen](../building-packages-programmatically/adding-connections-programmatically.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Integrationsservices &#40;SSIS&#41; Verbindungen](integration-services-ssis-connections.md)  
  
  