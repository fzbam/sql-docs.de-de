---
title: Angeben von Verarbeitungsoptionen | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Analysis Services deployments, processing options
- input files [Analysis Services]
- deploying [Analysis Services], processing options
- modifying processing options
- Analysis Services Deployment Wizard, processing options
ms.assetid: e9e50817-908e-4210-bc3d-8e2957568241
caps.latest.revision: 31
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: 7035045d1d55e9158431dd4245b9d5112b2df0a4
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36049807"
---
# <a name="specifying-processing-options"></a>Angeben von Verarbeitungsoptionen
  Die [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Bereitstellungsassistent liest die Verarbeitungsoptionen aus der \< *Projektname*> .deploymentoptions-Datei. [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] erstellt diese Datei, wenn Sie das [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Projekt erstellen. [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] verwendet die Verarbeitungsoptionen, angegeben auf der **Bereitstellung** auf der Seite  *\<Projektname >* **Eigenschaftenseiten** Dialogfeld zum Erstellen der \< *Projektname*> .deploymentoptions-Datei.  
  
## <a name="reviewing-the-processing-options-for-deployment"></a>Überprüfen der Verarbeitungsoptionen für die Bereitstellung  
 Konfigurationseinstellungen gespeichert, die innerhalb der \< *Projektname*> .deploymentoptions Datei lauten wie folgt:  
  
-   **Verarbeitungsmethode** Diese Einstellung steuert, ob die bereitgestellten Objekte nach der Bereitstellung verarbeitet werden und welche Art von Verarbeitung ausgeführt wird. Es stehen drei Verarbeitungsoptionen zur Verfügung:  
  
    -   Standardverarbeitung (Standardeinstellung)  
  
    -   Vollständige Verarbeitung  
  
    -   InclusionThresholdSetting  
  
-   **Optionen für die Rückschreibetabelle** Wenn im [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Projekt Rückschreiben aktiviert ist, wird mit dieser Einstellung die Ausführung dieses Vorgangs definiert. Es sind drei Rückschreibetabellenoptionen verfügbar:  
  
    -   Wenn eine Rückschreibetabelle vorhanden ist, wird diese standardmäßig verwendet. Ist keine Rückschreibetabelle vorhanden, wird eine neue Rückschreibetabelle erstellt.  
  
    -   Wenn bereits eine Rückschreibetabelle vorhanden ist, kann die Bereitstellung nicht durchgeführt werden. Ist keine Rückschreibetabelle vorhanden, wird eine neue Rückschreibetabelle erstellt.  
  
    -   Unabhängig davon, ob bereits eine Rückschreibetabelle vorhanden ist, wird eine neue Rückschreibetabelle erstellt. In diesem Fall löscht der Bereitstellungs-Assistent für [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] die vorhandene Tabelle und ersetzt sie durch eine neue Rückschreibetabelle.  
  
-   **Transaktionsbereitstellung** Diese Einstellung steuert, ob die Bereitstellung von Metadatenänderungen und Verarbeitungsbefehlen in einer einzelnen Transaktion oder in getrennten Transaktionen erfolgt.  
  
    -   Wenn diese Option ist `True` (Standard), [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] stellt alle Metadatenänderungen und alle Verarbeitungsbefehle in einer einzelnen Transaktion bereit.  
  
    -   Wenn diese Option ist `False`, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] stellt die Metadatenänderungen in einer einzelnen Transaktion und jeden Verarbeitungsbefehl jeweils in einer eigenen Transaktion bereitgestellt.  
  
## <a name="modifying-the-processing-options-for-deployment"></a>Ändern der Verarbeitungsoptionen für die Bereitstellung  
 Sie möchten jedoch Bereitstellen der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Projekt mit anderen Verarbeitungsoptionen als in der \< *Projektname*> .deploymentoptions-Datei. Vielleicht sollen alle Objekte vollständig oder mithilfe der Standardverarbeitungsoption oder überhaupt nicht verarbeitet werden. Wenn die Cubes oder Dimensionen für den Schreibzugriff aktiviert sind, können Sie angeben, ob eine neue oder eine vorhandene Rückschreibetabelle verwendet werden soll.  
  
 Wenn Sie die bei der Bereitstellung zu verwendenden Verarbeitungsoptionen ändern möchten, können Sie entweder das Projekt bearbeiten und neu erstellen, oder Sie ändern mithilfe einer der im Folgenden beschriebenen Prozedur die Verarbeitungsoptionen in der Eingabedatei.  
  
#### <a name="to-change-processing-options-after-the-input-files-have-been-generated"></a>So ändern Sie Verarbeitungsoptionen, nachdem die Eingabedateien generiert wurden  
  
-   Führen Sie den Bereitstellungs-Assistenten für [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] interaktiv aus. Geben Sie auf der Seite **Verarbeitungsoptionen** die Verarbeitungsoptionen für das bereitzustellende Projekt an.  
  
     – oder –  
  
-   Führen Sie den Bereitstellungs-Assistenten für [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] an der Eingabeaufforderung aus, und legen Sie fest, dass der Assistent im Antwortdateimodus ausgeführt wird. Weitere Informationen zum Antwortdateimodus finden Sie unter [Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md).  
  
     – oder –  
  
-   Ändern der \< *Projektname*> .deploymentoptions-Datei mit einem beliebigen Texteditor.  
  
## <a name="see-also"></a>Siehe auch  
 [Angeben des Installationszieles](deployment-script-files-specifying-the-installation-target.md)   
 [Angeben von Partition und Optionen für die Rollenbereitstellung](deployment-script-files-partition-and-role-deployment-options.md)   
 [Angeben der Konfigurationseinstellungen für die Lösungsbereitstellung](deployment-script-files-solution-deployment-config-settings.md)  
  
  