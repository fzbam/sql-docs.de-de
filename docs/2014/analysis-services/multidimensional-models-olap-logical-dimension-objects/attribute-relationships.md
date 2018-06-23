---
title: Attributbeziehungen | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- member properties [Analysis Services], attribute relationships
- security [Analysis Services], properties
- PROPERTIES keyword
- storage [Analysis Services], attribute relationships
- natural hierarchies [Analysis Services]
- dimensions [Analysis Services], member properties
- queries [MDX], attribute relationships
- user-defined hierarchies [Analysis Services]
- attributes [Analysis Services], relationships
- member properties [Analysis Services]
- members [Analysis Services], attribute relationships
- storing data [Analysis Services], attribute relationships
- relationships [Analysis Services], attributes
ms.assetid: 2491422a-4cf5-4b23-b6ab-289222b22ce8
caps.latest.revision: 46
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: e2eb8155b2515a04191eeeccadcc3c21843f19e2
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36059699"
---
# <a name="attribute-relationships"></a>Attributbeziehungen
  In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], Attributen innerhalb einer Dimension sind immer entweder direkt oder indirekt mit dem Schlüsselattribut verknüpft. Wenn Sie eine Dimension auf Basis eines Sternschemas definieren, in dem sämtliche Dimensionsattribute aus derselben relationalen Tabelle abgeleitet werden, wird automatisch eine Attributbeziehung zwischen dem Schlüsselattribut und den einzelnen Nichtschlüsselattributen definiert. Wenn Sie eine Dimension auf Basis eines Schneeflockenschemas definieren, in dem Dimensionsattribute aus mehreren verknüpften Tabellen abgeleitet werden, wird eine Attributbeziehung automatisch wie folgt definiert:  
  
-   Zwischen dem Schlüsselattribut und den einzelnen Nichtschlüsselattributen, die an die Spalten in der Dimensionshaupttabelle gebunden sind  
  
-   Zwischen dem Schlüsselattribut und dem Attribut, das an den Fremdschlüssel in der sekundären Tabelle gebunden ist, die die zugrunde liegenden Dimensionstabellen verknüpft  
  
-   Zwischen dem Attribut, das an den Fremdschlüssel in der sekundären Tabelle gebunden ist, und den einzelnen Nichtschlüsselattributen, die an Spalten aus der sekundären Tabelle gebunden sind  
  
 Es kann jedoch Gründe dafür geben, die Standardattributbeziehungen zu ändern. Ein möglicher Grund wäre, dass Sie eine natürliche Hierarchie, eine benutzerdefinierte Sortierreihenfolge oder Dimensionsgranularität auf Basis eines Nichtschlüsselattributs definieren möchten. Weitere Informationen finden Sie unter [Dimensionsattributeigenschaftenverweis](../multidimensional-models/dimension-attribute-properties-reference.md).  
  
> [!NOTE]  
>  Attributbeziehungen sind in MDX (Multidimensional Expressions) als Elementeigenschaften bekannt.  
  
## <a name="natural-hierarchy-relationships"></a>Beziehungen mit natürlicher Hierarchie  
 Eine Hierarchie wird als natürlich bezeichnet, wenn die in der benutzerdefinierten Hierarchie enthaltenen Attribute 1:n-Beziehungen mit dem jeweils direkt darunter liegenden Attribut haben. Ein Beispiel ist eine Customer-Dimension, die auf einer relationalen Quelltabelle mit acht Spalten basiert:  
  
-   CustomerKey  
  
-   CustomerName  
  
-   Age  
  
-   Geschlecht  
  
-   Email  
  
-   Ort  
  
-   Country  
  
-   Region  
  
 Die entsprechende Analysis Services-Dimension verfügt über sieben Attribute:  
  
-   Customer (basierend auf CustomerKey, wobei CustomerName Elementnamen angibt)  
  
-   Age, Gender, Email, City, Region, Country  
  
 Beziehungen, die natürliche Hierarchien darstellen, werden dadurch erzwungen, dass eine Attributbeziehung zwischen dem Attribut einer Ebene und dem Attribut der darunter liegenden Ebene erstellt wird. Für [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] gibt dies eine natürliche Beziehung und potenzielle Aggregation an. In der Customer-Dimension besteht für die Attribute Country, Region, City und Customer eine natürliche Hierarchie. Die natürliche Hierarchie für `{Country, Region, City, Customer}` wird durch Hinzufügen der folgenden Attributbeziehungen beschrieben:  
  
-   Das Country-Attribut als Attributbeziehung zum Region-Attribut.  
  
-   Das Region-Attribut als Attributbeziehung zum City-Attribut.  
  
-   Das City-Attribut als Attributbeziehung zum Customer-Attribut.  
  
 Für das Navigieren durch Daten in den Cube, können Sie auch eine benutzerdefinierte Hierarchie, die keine natürliche Hierarchie in den Daten darstellt erstellen (das heißt eine *ad-hoc-* oder *reporting* Hierarchie). Sie könnten z. B. eine benutzerdefinierte Hierarchie auf der Basis von `{Age, Gender}` erstellen. Benutzer erkennen keine Unterschiede im Verhalten der beiden Hierarchien, aber die natürliche Hierarchie profitiert von den Strukturen für Aggregation und Indizierung (ohne dass der Benutzer es bemerkt), die für die natürlichen Beziehungen in den Quelldaten verantwortlich sind.  
  
 Durch die `SourceAttribute`-Eigenschaft einer Ebene ist festgelegt, mit welchem Attribut die Ebene beschrieben wird. Die `KeyColumns`-Eigenschaft des Attributs gibt an, welche Spalte in der Datenquellensicht die Elemente bereitstellt. Mit der `NameColumn`-Eigenschaft des Attributs kann eine andere Namensspalte für die Elemente festgelegt werden.  
  
 So definieren Sie eine Ebene in einer benutzerdefinierten Hierarchie mithilfe von [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], **Dimensions-Designer** können Sie aus einer verknüpften Tabelle enthalten, die in der Datenquellensicht für ein Dimensionsattribut, eine Spalte in einer Dimensionstabelle oder eine Spalte auswählen Der Cube. Weitere Informationen zum Erstellen von benutzerdefinierten Hierarchien finden Sie unter [Situationen Hierarchien](../multidimensional-models/user-defined-hierarchies-create.md).  
  
 In Analysis Services erfolgt in der Regel eine Annahme zum Inhalt von Elementen. Blattelemente haben keine nachfolgenden Werte und enthalten von zugrunde liegenden Datenquellen abgeleitete Daten. Nicht-Blattelemente haben nachfolgende Werte und enthalten von Aggregationen abgeleitete Daten, die für untergeordnete Elemente ausgeführt wurden. Auf aggregierten Ebenen basieren Elemente auf Aggregationen der untergeordneten Ebenen. Wenn also die `IsAggregatable`-Eigenschaft für das Quellattribut einer Ebene auf `False` festgelegt ist, sollten keine aggregierbaren Attribute als nächst höhere Ebenen hinzugefügt werden.  
  
## <a name="defining-an-attribute-relationship"></a>Definieren einer Attributbeziehung  
 Die wesentliche Einschränkung beim Erstellen einer Attributbeziehung liegt darin, sicherzustellen, dass das Attribut, auf das durch die Attributbeziehung verwiesen wird, maximal einen Wert für jeweils ein Element in dem Attribut aufweist, zu dem die Attributbeziehung gehört. Wenn Sie beispielsweise eine Beziehung zwischen einem City-Attribut und einem State-Attribut definieren, kann sich jede Stadt nur auf ein Bundesland beziehen.  
  
## <a name="attribute-relationship-queries"></a>Abfragen von Attributbeziehungen  
 Sie können MDX-Abfragen verwenden, um Daten aus Attributbeziehungen abzurufen, und zwar in Form von Elementeigenschaften, mit dem `PROPERTIES`-Schlüsselwort der `SELECT`-MDX-Anweisung. Weitere Informationen zur Verwendung von MDX zum Abrufen von Elementeigenschaften finden Sie unter [mithilfe von Elementeigenschaften &#40;MDX&#41;](../multidimensional-models/mdx/mdx-member-properties.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Attribute und Attributhierarchien](attributes-and-attribute-hierarchies.md)   
 [Dimensionsattributeigenschaftenverweis](../multidimensional-models/dimension-attribute-properties-reference.md)   
 [Benutzerhierarchien](user-hierarchies.md)   
 [Eigenschaften der Benutzerhierarchie](user-hierarchies-properties.md)  
  
  