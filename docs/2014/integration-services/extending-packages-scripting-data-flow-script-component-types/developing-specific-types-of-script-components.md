---
title: Entwickeln bestimmter Typen von Skriptkomponenten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- docset-sql-devref
- integration-services
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- Script component [Integration Services], examples
ms.assetid: dfbbe959-6b4e-4b47-b9dd-bcc31929482d
caps.latest.revision: 11
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: 4737f7723f7403d823ca950557bcccd41c7a750a
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36060528"
---
# <a name="developing-specific-types-of-script-components"></a>Entwickeln bestimmter Arten von Skriptkomponenten
  Bei der Skriptkomponente handelt es sich um ein konfigurierbares Tool, das Sie im Datenfluss eines Pakets verwenden können, um nahezu allen Anforderungen gerecht zu werden, die von den Quellen, Transformationen und Zielen nicht erfüllt werden, die in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] enthalten sind. Dieser Abschnitt enthält Codebeispiele für Skriptkomponenten, in denen die vier Optionen zum Konfigurieren der Skriptkomponente veranschaulicht werden:  
  
-   Als Quelle.  
  
-   Als Transformation mit synchronen Ausgaben.  
  
-   Als Transformation mit asynchronen Ausgaben.  
  
-   Als Ziel.  
  
 Weitere Beispiele von Skriptkomponenten finden Sie unter [Zusätzliche Skriptkomponentenbeispiele](../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Erstellen einer Quelle mit der Skriptkomponente](creating-a-source-with-the-script-component.md)  
 Erläutert und veranschaulicht, wie eine Datenflussquelle mithilfe der Skriptkomponente erstellt wird.  
  
 [Erstellen einer synchronen Transformation mit der Skriptkomponente](creating-a-synchronous-transformation-with-the-script-component.md)  
 Erläutert und veranschaulicht, wie eine Datenflusstransformation mit synchronen Ausgaben mithilfe der Skriptkomponente erstellt wird. Durch diese Art von Transformation werden Datenzeilen an Ort und Stelle beim Durchlaufen der Komponente geändert.  
  
 [Erstellen einer asynchronen Transformation mit der Skriptkomponente](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md)  
 Erläutert und veranschaulicht, wie eine Datenflusstransformation mit asynchronen Ausgaben mithilfe der Skriptkomponente erstellt wird. Bei dieser Art von Transformation müssen alle Datenzeilen gelesen werden, bevor den Daten, die die Komponente durchlaufen, weitere Informationen, z. B. berechnete Aggregate, hinzugefügt werden können.  
  
 [Erstellen eines Ziels mit der Skriptkomponente](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md)  
 Erläutert und veranschaulicht, wie ein Datenflussziel mithilfe der Skriptkomponente erstellt wird.  
  
![Integration Services (kleines Symbol)](../media/dts-16.gif "Integration Services (kleines Symbol)")**bleiben Sie mit Integration Services  **<br /> Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:<br /><br /> [Besuchen Sie die Integration Services-Seite auf MSDN](http://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.  
  
## <a name="see-also"></a>Siehe auch  
 [Vergleichen von Skriptlösungen und benutzerdefinierten Objekten](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md)   
 [Entwickeln bestimmter Arten von Datenflusskomponenten](../extending-packages-custom-objects-data-flow-types/developing-specific-types-of-data-flow-components.md)  
  
  