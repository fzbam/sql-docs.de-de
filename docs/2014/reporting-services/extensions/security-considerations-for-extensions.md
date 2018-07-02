---
title: Überlegungen zur Sicherheit von Erweiterungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- security [Reporting Services], extensions
- extensions [Reporting Services], security
- permissions [Reporting Services], extensions
ms.assetid: 58cbdfeb-1105-4a7d-a3b8-b897ff95f367
caps.latest.revision: 29
author: douglaslM
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: f94a5c1ad255b9caec8e004318b45f8be21afae0
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36049643"
---
# <a name="security-considerations-for-extensions"></a>Überlegungen zur Sicherheit von Erweiterungen
  Jede Anwendung für die Common Language Runtime (CLR) muss mit dem CLR-Sicherheitssystem interagieren. Bei der Ausführung einer solchen Anwendung wird diese automatisch ausgewertet, und sie erhält von der CLR einen Berechtigungssatz. Abhängig von den Berechtigungen, die die Anwendung erhält, wird sie entweder weiter ausgeführt, oder es wird eine Sicherheitsausnahme ausgelöst. Die lokalen Sicherheitseinstellungen und –richtlinien in den Dateien für die Sicherheitsrichtlinienkonfiguration eines bestimmten Berichtsservers definieren die Codeberechtigungen, die eine Assembly erhält.  
  
 Bevor Sie Berechtigungen anfordern, sollten Sie wissen, welche Ressourcen und geschützten Operationen Ihr Erweiterungscode verwenden soll. Außerdem sollten Sie wissen, von welchen Berechtigungen diese Ressourcen und Operationen geschützt werden. Darüber hinaus müssen Sie sämtliche Ressourcen verfolgen, auf die von Methoden der Klassenbibliotheken zugegriffen wird, die von den Erweiterungskomponenten aufgerufen werden. Weitere Informationen finden Sie unter "Anfordern von Berechtigungen" im [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Entwicklerhandbuch.  
  
 Erweiterungen, die auf einem Berichtsserver bereitgestellt werden, müssen vollständig vertrauenswürdig sein, d.h., Ihre Erweiterung muss Teil einer Codegruppe sein, der die Berechtigung **FullTrust** erteilt wurde. Dies bedeutet auch, dass Ihre Erweiterung Zugriff auf bestimmte Serverressourcen und -vorgänge haben kann, die über CLR zur Verfügung stehen, abhängig vom Benutzer, der gerade für einen bestimmten Bericht authentifiziert wird. Weitere Informationen zu Codegruppen und Erweiterungen finden Sie unter [Codezugriffssicherheit in Reporting Services](secure-development/code-access-security-in-reporting-services.md).  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] wendet die [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Sicherheit für alle Erweiterungen an.  
  
 Die folgenden Bedingungen gelten für den Einsatz von Datenverarbeitungs-, Übermittlungs-, Rendering- und Sicherheitserweiterungen in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]:  
  
-   Nur der lokale Administrator hat die Berechtigung, eine Erweiterung anzuwenden.  
  
-   Nur Benutzer mit der entsprechenden Lese-/Schreibberechtigung können die Konfigurationsdateien für die [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Komponente ändern, die gerade erweitert wird.  
  
-   Nur berechtigte Benutzer dürfen die Sicherheitsrichtliniendateien ändern und die Codezugriffssicherheit für eine Erweiterung aktivieren.  
  
 Weitere Informationen zur Codezugriffssicherheit in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] finden Sie unter [Sichere Entwicklung (Reporting Services)](secure-development/secure-development-reporting-services.md).  
  
 Weitere Informationen zur [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Sicherheit finden Sie in der .NET Framework-Sicherheit im [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Entwicklerhandbuch.  
  
## <a name="initialization-of-extension-assemblies"></a>Initialisierung von Erweiterungsassemblys  
 Wenn Erweiterungen zum ersten Mal vom Berichtsserver in den Speicher geladen werden, verwenden sie die Anmeldeinformationen für ein Dienstkonto. Denn einige Erweiterungsassemblys benötigen bestimmte Berechtigungen, um auf die Systemressourcen zugreifen, die Konfigurationsdateien lesen und andere abhängige Assemblys laden zu dürfen. Nachdem eine Assembly geladen und initialisiert wurde, verwenden alle nachfolgenden Aufrufe der Erweiterungsassemblys die Anmeldeinformationen vom Konto des Benutzers, der gerade angemeldet ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Erweiterungen für Reporting Services](reporting-services-extensions.md)   
 [Reporting Services Extension Library (Reporting Services-Erweiterungsbibliothek)](reporting-services-extension-library.md)  
  
  