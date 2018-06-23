---
title: Beispiel für eine XML-Eingabedatei mit benutzerdefinierter Konfiguration (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- XML
helpviewer_keywords:
- sample applications [DTA]
ms.assetid: b29c9716-e5c3-4003-9efb-3ade2197b630
caps.latest.revision: 18
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: 933cae8582f104d9c70e608ab30ee938c8674175
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36056832"
---
# <a name="xml-input-file-sample-with-user-specified-configuration-dta"></a>Beispiel für eine XML-Eingabedatei mit benutzerdefinierter Konfiguration (DTA)
  Kopieren Sie dieses Beispiel für eine XML-Eingabedatei, die eine benutzerdefinierte Konfiguration mit dem **Configuration**-Element angibt, und fügen Sie sie in Ihren XML-Editor oder Text-Editor ein. Dadurch können Sie Was-wäre-wenn-Analysen ausführen. Bei Was-wäre-wenn-Analysen wird mit dem **Configuration** -Element eine Gruppe von hypothetischen physischen Entwurfsstrukturen für die Datenbank angegeben, die Sie optimieren möchten. Anschließend analysieren Sie mit dem Datenbankoptimierungsratgeber, welche Auswirkungen das Ausführen einer Arbeitsauslastung für diese hypothetische Konfiguration hat, um herauszufinden, ob dadurch die Abfrageverarbeitungsleistung verbessert werden kann. Diese Art einer Analyse hat den Vorteil, dass die neue Konfiguration ausgewertet werden kann, ohne dass eine Implementierung erforderlich ist. Wenn die hypothetische Konfiguration nicht die gewünschten Leistungssteigerungen erzielt, lässt sie sich auf einfache Weise ändern und erneut analysieren, bis Sie die Konfiguration haben, die die gewünschten Ergebnisse erzielt.  
  
 Nach dem Kopieren dieses Beispiels in Ihr Bearbeitungstool ersetzen Sie die Werte für das **Server**-, **Database**-, **Schema**-, **Table**-, **Workload**-, **TuningOptions**- und **Configuration** -Element durch die Werte für Ihre Optimierungssitzung. Weitere Informationen zu sämtlichen Attributen und untergeordneten Elementen, die Sie zusammen mit diesen Elementen verwenden können, finden Sie unter [XML Input File Reference &#40;Database Engine Tuning Advisor&#41;](xml-input-file-reference-database-engine-tuning-advisor.md). Im folgenden Beispiel wird nur eine Teilmenge der verfügbaren Optionen für Attribute und untergeordnete Elemente verwendet.  
  
## <a name="code"></a>Code  
 [!code-xml[InputFileSamples#UserSpecifiedConfigInputFile](../../snippets/xml/SQL14/dta_xml/inputfilesamples/xml/dta_xml_input_file_samples.xml#userspecifiedconfiginputfile)]  
  
## <a name="comments"></a>Kommentare  
  
-   Das Löschen von physischen Entwurfsstrukturen wird nicht unterstützt, wenn Sie den **Absolute** -Modus für das **Configuration** -Element angeben (`Configuration SpecificationMode="Absolute"`).  
  
-   Sie können die gleiche physische Entwurfsstruktur nicht in beiden Modi (**Relative** oder **Absolute**) des **Configuration** -Elements erstellen und löschen.  
  
## <a name="see-also"></a>Siehe auch  
 
  [Starten und Verwenden des Datenbankoptimierungsratgebers](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md)   
 
  [Anzeigen und Verwenden der Ausgabe des Datenbankoptimierungsratgebers](../../relational-databases/performance/view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md)   
 
  [XML-Eingabedateireferenz &amp;#40;Datenbankoptimierungsratgeber&amp;#41;](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  