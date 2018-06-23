---
title: Lokale Cubes (Analysis Services – mehrdimensionale Daten) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- cubes [Analysis Services], local
ms.assetid: e52e1515-35a7-4dc3-9bbf-736d176ba0c7
caps.latest.revision: 13
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: bfb1b14d4dc540f13a98314d8cf299b78adf1550
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36060600"
---
# <a name="local-cubes-analysis-services---multidimensional-data"></a>Lokale Cubes (Analysis Services - Mehrdimensionale Daten)
  Zum Erstellen, Aktualisieren oder Löschen lokaler Cubes muss ein ASSL-Skript oder ein AMO-Programm erstellt und ausgeführt werden.  
  
 Lokale Cubes und lokale Miningmodelle ermöglichen Analysen auf einer Clientarbeitsstation, wenn deren Verbindung mit dem Netzwerk getrennt ist. Beispielsweise könnte eine Clientanwendung den OLE DB-Anbieter für OLAP 9.0 (MSOLAP.3) aufrufen, der die lokale Cube-Engine zum Erstellen und Abfragen von lokalen Cubes lädt, wie in der folgenden Abbildung dargestellt:  
  
 ![Clientarchitektur für lokale Cubes und Modelle](../../../analysis-services/dev-guide/media/as-localcubearch9.gif "Clientarchitektur für lokale Cubes und Modelle")  
  
 ADMOD.NET und Analysis Management Objects (AMO) laden zudem die lokale Cube-Engine, wenn eine Interaktion mit lokalen Cubes erfolgt. Es kann nur mit einem einzelnen Prozess auf eine lokale Cubedatei zugegriffen werden, da die lokale Cube-Engine eine lokale Cubedatei exklusiv sperrt, wenn eine Verbindung mit dem lokalen Cube hergestellt wird. Mit einem Prozess sind bis zu fünf gleichzeitige Verbindungen zulässig.  
  
 Eine CUB-Datei kann mehr als einen Cube bzw. ein Data Mining-Modell enthalten. Abfragen an die lokalen Cubes und Data Mining-Modelle werden von der lokalen Cube-Engine verarbeitet und benötigen keine Verbindung mit einer [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]-Instanz.  
  
> [!NOTE]  
>  Die Verwendung von [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] und [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] zum Verwalten lokaler Cubes wird nicht unterstützt.  
  
## <a name="local-cubes"></a>Lokale Cubes  
 Ein lokaler Cube erstellt und aufgefüllt, die aus einem vorhandenen Cube in einer [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] Instanz oder aus einer relationalen Datenquelle.  
  
|Quelle für Daten für lokalen Cube|Erstellungsmethode|  
|------------------------------------|---------------------|  
|Serverbasierter Cube|Sie können entweder die CREATE GLOBAL CUBE-Anweisung oder eine [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] Scripting Language (ASSL)-Skript zum Erstellen und Auffüllen eines Cubes aus einem serverbasierten Cube. Weitere Informationen finden Sie unter [GLOBAL CUBE-Anweisung CREATE &#40;MDX&#41; ](/sql/mdx/mdx-data-definition-create-global-cube) oder [Analysis Services Scripting Language &#40;ASSL&#41; Verweis](../../scripting/analysis-services-scripting-language-assl-for-xmla.md).|  
|Relationale Datenquelle|Mithilfe eines ASSL-Skripts können Sie einen Cube aus einer relationalen OLE DB-Datenbank erstellen und auffüllen. Wenn Sie einen lokalen Cube mithilfe von ASSL erstellen möchten, stellen Sie eine Verbindung mit einer lokalen Cubedatei (CUB) her und führen das ASSL-Skript auf dieselbe Weise aus, als wenn Sie ein ASSL-Skript für eine [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]-Instanz ausführen, um einen Servercube zu erstellen. Weitere Informationen finden Sie unter [Analysis Services Scripting Language &#40;ASSL&#41; Verweis](../../scripting/analysis-services-scripting-language-assl-for-xmla.md).|  
  
 Verwenden Sie die REFRESH CUBE-Anweisung, um einen lokalen Cube neu zu erstellen und seine Daten zu aktualisieren. Weitere Informationen finden Sie unter [REFRESH CUBE-Anweisung &#40;MDX&#41;](/sql/mdx/mdx-data-definition-refresh-cube).  
  
### <a name="local-cubes-created-from-server-based-cubes"></a>Aus serverbasierten Cubes erstellte lokale Cubes  
 Wenn lokale Cubes anhand von serverbasierten Cubes erstellt werden, sind folgende Überlegungen zu berücksichtigen:  
  
-   Distinct Count Measures werden nicht unterstützt.  
  
-   Wenn Sie ein Measure hinzufügen, müssen Sie auch mindestens eine Dimension aufnehmen, die sich auf das hinzuzufügende Measure bezieht. Weitere Informationen zu dimensionsbeziehungen mit Measuregruppen finden Sie unter [Dimensionsbeziehungen](../../multidimensional-models-olap-logical-cube-objects/dimension-relationships.md).  
  
-   Wenn Sie eine Über-/Unterordnungshierarchie hinzufügen, werden die Ebenen und Filter einer Über-/Unterordnungshierarchie ignoriert, und die gesamte Über-/Unterordnungshierarchie wird aufgenommen.  
  
-   Elementeigenschaften werden nicht erstellt.  
  
-   Wenn Sie ein semiadditives Measure aufnehmen, sind keine Segmente für die Account-Dimension und die Time-Dimension zulässig.  
  
-   Bezugsdimensionen werden stets materialisiert.  
  
-   Wenn Sie eine m:n-Dimension einschließen, gelten die folgenden Regeln:  
  
    -   Die m:n-Dimension kann nicht segmentiert werden.  
  
    -   Sie müssen ein Measure aus der Measurezwischengruppe hinzufügen.  
  
    -   Sie können keine der Dimensionen segmentieren, die für die beiden an der m:n-Beziehung beteiligten Measuregruppen gleichzeitig vorhanden sind.  
  
-   Es werden nur die berechneten Elemente, benannten Mengen und Zuweisungen im lokalen Cube angezeigt, die auf Measures und Dimensionen beruhen, die dem lokalen Cube hinzugefügt wurden. Ungültige berechnete Elemente, benannte Mengen und Zuweisungen werden automatisch ausgeschlossen.  
  
### <a name="security"></a>Security  
 Im Auftrag eines Benutzers auf einen lokalen Cube von einem Servercube zu erstellen, müssen Sie dem Benutzer erteilt **Drillthrough und lokaler Cube** Berechtigungen für den Servercube. Weitere Informationen finden Sie unter [Erteilen von Cube-oder modellberechtigungen &#40;Analysis Services&#41;](../../multidimensional-models/grant-cube-or-model-permissions-analysis-services.md).  
  
 Lokale Cubes werden nicht wie Servercubes mithilfe von Rollen gesichert. Alle Benutzer mit Zugriff auf Dateiebene auf eine lokale Cubedatei können die darin enthaltenen Cubes abfragen. Sie können die `Encryption Password`-Verbindungseigenschaft für eine lokale Cubedatei verwenden, um ein Kennwort für die lokale Cubedatei festzulegen. Zum Festlegen eines Kennworts für eine lokale Cubedatei ist es erforderlich, dass für alle zukünftigen Verbindungen mit der lokalen Cubedatei dieses Kennwort verwendet wird, damit die Datei abgefragt werden kann.  
  
## <a name="see-also"></a>Siehe auch  
 [CREATE GLOBAL CUBE-Anweisung &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-global-cube)   
 [Entwickeln mit Analysis Services Scripting Language &#40;ASSL&#41;](../scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md)   
 [REFRESH CUBE-Anweisung &#40;MDX&#41;](/sql/mdx/mdx-data-definition-refresh-cube)  
  
  