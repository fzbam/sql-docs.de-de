---
title: Auflistungen (ASSL) | Microsoft Docs
ms.custom: 
ms.date: 03/17/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- collections [Analysis Services Scripting Language]
- Analysis Services Scripting Language, collections
- ASSL, collections
ms.assetid: 072b8c6b-1550-4cab-ae64-ba0e3e60b059
caps.latest.revision: 19
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: f9751d6b4052575c85abf41f745817def8f7ae75
ms.contentlocale: de-de
ms.lasthandoff: 09/01/2017

---
# <a name="collections-assl"></a>Auflistungen (ASSL)
  In diesem Referenzabschnitt finden Sie Syntax- und Nutzungsinformationen für jedes Element, das im ASSL-Schema (Analysis Services Scripting Language) als Sammlung agiert.  
  
 Obwohl das ASSL-Schema nur XML-Elemente, aus der Sicht eines Entwicklers, enthält die Elemente, die in diesem Abschnitt beschriebenen entsprechen Auflistungen von Objekten, z. B. die **Dimensionen** und **Cubes** Auflistungen.  
  
 Auflistungen sind meistens Auflistungen von Objektelementen, in dem ein Nomen im plural die Auflistung kennzeichnet (z. B. **Cubes**), und die Auflistung enthält Elemente, die von dem gleichen Substantiv im Singular festgelegt (z. B.  **Cube**).  
  
 In einigen Fällen weicht das Schema von dieser allgemeinen Regel ab. Z. B. die **ClassifiedColumns** Auflistung enthält **ClassifiedColumnID** Elemente.  
  
 In anderen Fällen enthält eine Auflistung Elemente, die nicht Objekten, sondern Objekteigenschaften entsprechen. Z. B. die **Aliase** Auflistung enthält **Alias** Eigenschaften, von denen jede ein einfacher Zeichenfolgewert ist.  
  
|Element|Description|  
|-------------|-----------------|  
|[Accounts-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/accounts-element-assl.md)|Enthält die Auflistung der Kontotypen, die in definierten ein [Datenbank](../../../analysis-services/scripting/objects/database-element-assl.md) Element.|  
|[Actions-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/actions-element-assl.md)|Enthält die Auflistung der Aktionen für eine [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) oder [Perspektive](../../../analysis-services/scripting/objects/perspective-element-assl.md) Element.|  
|[AggregationDesigns-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/aggregationdesigns-element-assl.md)|Enthält die Auflistung der Aggregationsentwürfe, die für mehrere Partitionen in einer Datenbank freigegeben sein können.|  
|[AggregationInstances-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/aggregationinstances-element-assl.md)|Enthält die Auflistung der aggregationsinstanzen, die in definierten ein [Partition](../../../analysis-services/scripting/objects/partition-element-assl.md) Element.|  
|[Aggregations-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/aggregations-element-assl.md)|Enthält die Auflistung von Aggregationen für definierte ein [AggregationDesign](../../../analysis-services/scripting/objects/aggregationdesign-element-assl.md) Element.|  
|[AlgorithmParameters-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/algorithmparameters-element-assl.md)|Enthält die Auflistung der Parameter für den Algorithmus, der verwendet wird, indem Sie eine [MiningModel](../../../analysis-services/scripting/objects/miningmodel-element-assl.md) Element.|  
|[Aliases-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/aliases-element-assl.md)|Enthält die Auflistung der [Alias](../../../analysis-services/scripting/properties/alias-element-assl.md) Elemente, die zu einer [Konto](../../../analysis-services/scripting/objects/account-element-assl.md) Element|  
|[AllMemberTranslations-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/allmembertranslations-element-assl.md)|Enthält die Auflistung der [Übersetzung](../../../analysis-services/scripting/objects/translation-element-assl.md) Elemente für die Beschriftung des alle-Elements ein [Hierarchie](../../../analysis-services/scripting/objects/hierarchy-element-assl.md) Element.|  
|[Annotations-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/annotations-element-assl.md)|Enthält die Auflistung der [Anmerkung](../../../analysis-services/scripting/objects/annotation-element-assl.md) Elemente mit dem übergeordneten Element verknüpft sind.|  
|[Assemblies-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/assemblies-element-assl.md)|Enthält die Auflistung der [Assembly](../../../analysis-services/scripting/objects/assembly-element-assl.md) Elemente, die zu einem [Server](../../../analysis-services/scripting/objects/server-element-assl.md) Element oder ein [Datenbank](../../../analysis-services/scripting/objects/database-element-assl.md) Element.|  
|[AttributeAllMemberTranslations-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/attributeallmembertranslations-element-assl.md)|Enthält die Auflistung von Übersetzungen für die Beschriftung des "Alle"-Elements der Dimension.|  
|[AttributePermissions-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/attributepermissions-element-assl.md)|Enthält die Auflistung der Attributberechtigungen für eine einzelnes [Rolle](../../../analysis-services/scripting/objects/role-element-assl.md) für eine bestimmte Dimension des Elements ein [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) Element.|  
|[AttributeRelationships-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/attributerelationships-element-assl.md)|Enthält die Auflistung der [AttributeRelationship](../../../analysis-services/scripting/objects/attributerelationship-element-assl.md) Elemente für das Attribut.|  
|[Attributes-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/attributes-element-assl.md)|Enthält die Auflistung der Attribute für die verknüpfte Dimension.|  
|[Blocks-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/blocks-element-assl.md)|Enthält die Auflistung der Blöcke mit binären Daten, die den binären Inhalt darstellen einer [ClrAssemblyFile](../../../analysis-services/scripting/data-type/clrassemblyfile-data-type-assl.md) Element.|  
|[CalculationProperties-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/calculationproperties-element-assl.md)|Enthält die Auflistung der [CalculationProperty](../../../analysis-services/scripting/objects/calculationproperty-element-assl.md) Elemente, die zu einer [MdxScript](../../../analysis-services/scripting/objects/mdxscript-element-assl.md) Element.|  
|[Calculations-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/calculations-element-assl.md)|Enthält die Auflistung der [PerspectiveCalculation](../../../analysis-services/scripting/data-type/perspectivecalculation-data-type-assl.md) Elemente, die zu einem [Perspektive](../../../analysis-services/scripting/objects/perspective-element-assl.md) Element.|  
|[CellPermissions-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/cellpermissions-element-assl.md)|Enthält die Auflistung der Berechtigungen für Zellen im zugehörigen [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) Element.|  
|[ClassifiedColumns-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/classifiedcolumns-element-assl.md)|Enthält die Auflistung der verknüpften Spalten, die von klassifiziert werden die [ScalarMiningStructureColumn](../../../analysis-services/scripting/data-type/scalarminingstructurecolumn-data-type-assl.md) Element.|  
|[Columns-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/columns-element-assl.md)|Enthält die Auflistung der Spalten, die mit dem übergeordneten Element verknüpft sind.|  
|[Commands-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/commands-element-assl.md)|Enthält die Auflistung der [Command](../../../analysis-services/scripting/objects/command-element-assl.md) -Elemente, die mit einem [MdxScript](../../../analysis-services/scripting/objects/mdxscript-element-assl.md) -Element verknüpft sind.|  
|[CubePermissions-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/cubepermissions-element-assl.md)|Enthält die Auflistung der Berechtigungen für eine [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) Element.|  
|[Cubes-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/cubes-element-assl.md)|Enthält die Auflistung der [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) Elemente, die zu einem [Datenbank](../../../analysis-services/scripting/objects/database-element-assl.md) Element.|  
|[DatabasePermissions-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/databasepermissions-element-assl.md)|Enthält die Auflistung der [DatabasePermission](../../../analysis-services/scripting/objects/databasepermission-element-assl.md) Elemente, die zu einem [Datenbank](../../../analysis-services/scripting/objects/database-element-assl.md) Element.|  
|[Databases-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/databases-element-assl.md)|Enthält die Auflistung der [Datenbank](../../../analysis-services/scripting/objects/database-element-assl.md) Elemente, die zu einem [Server](../../../analysis-services/scripting/objects/server-element-assl.md) Element.|  
|[DataSources-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/datasources-element-assl.md)|Enthält die Auflistung der [DataSourcePermission](../../../analysis-services/scripting/objects/datasourcepermission-element-assl.md) Elemente, die zu einem [DataSource](../../../analysis-services/scripting/data-type/datasource-data-type-assl.md) -Datentyp.|  
|[DataSourcePermissions-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/datasourcepermissions-element-assl.md)|Enthält die Auflistung der [DataSource](../../../analysis-services/scripting/objects/datasource-element-assl.md) Elemente, die zu einem [Datenbank](../../../analysis-services/scripting/objects/database-element-assl.md) Element.|  
|[DataSourceViews-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/datasourceviews-element-assl.md)|Enthält die Auflistung der [DataSourceView](../../../analysis-services/scripting/objects/datasourceview-element-assl.md) Elemente, die zu einem [Datenbank](../../../analysis-services/scripting/objects/database-element-assl.md) Element.|  
|[DimensionPermissions-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/dimensionpermissions-element-assl.md)|Enthält die Auflistung der Berechtigungen für eine [Dimension](../../../analysis-services/scripting/objects/dimension-element-assl.md) Element oder ein [CubePermission](../../../analysis-services/scripting/objects/cubepermission-element-assl.md) Element.|  
|[Dimensions-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/dimensions-element-assl.md)|Enthält die Auflistung der Dimensionen, die mit dem übergeordneten Element verknüpft sind.|  
|[Events-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/events-element-assl.md)|Definiert die Auflistung der Ereigniselemente von erfasst werden sollen eine [Ablaufverfolgung](../../../analysis-services/scripting/objects/trace-element-assl.md).|  
|[Files-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/files-element-assl.md)|Enthält die Auflistung der [Datei](../../../analysis-services/scripting/objects/file-element-assl.md) Elemente, aus denen eine [ClrAssembly](../../../analysis-services/scripting/data-type/clrassembly-data-type-assl.md) Element.|  
|[ForeignKeyColumns-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/foreignkeycolumns-element-assl.md)|Enthält die Sammlung der Spalten, die den Join mit der übergeordneten Tabelle für eine relationale Datenquelle identifizieren.|  
|[Groups-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/groups-element-assl.md)|Enthält die Auflistung der Gruppen von Elementen, die an ein Attribut gebunden sind.|  
|[Hierarchies-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/hierarchies-element-assl.md)|Enthält die Auflistung der [Hierarchie](../../../analysis-services/scripting/objects/hierarchy-element-assl.md) Elemente mit dem übergeordneten Element verknüpft sind.|  
|[IncrementalProcessingNotifications-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/incrementalprocessingnotifications-element-assl.md)|Enthält die Auflistung der [IncrementalProcessingNotification](../../../analysis-services/scripting/objects/incrementalprocessingnotification-element-assl.md) Elemente, die Informationen zum Bereitstellen der [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) -Element zu Abfragen ausführen, um den Fortschritt zu bestimmen. inkrementelle Verarbeitung.|  
|[KeyColumns-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/keycolumns-element-assl.md)|Enthält die Auflistung der [KeyColumn](../../../analysis-services/scripting/objects/keycolumn-element-assl.md) -Elementdefinitionen für ein übergeordnetes Objekt.|  
|[KPIs-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/kpis-element-assl.md)|Enthält die Auflistung der [Kpi](../../../analysis-services/scripting/objects/kpi-element-assl.md) Elemente mit dem übergeordneten Element verknüpft sind.|  
|[Levels-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/levels-element-assl.md)|Enthält die Auflistung der [Ebene](../../../analysis-services/scripting/objects/level-element-assl.md) Elemente in einem [Hierarchie](../../../analysis-services/scripting/objects/hierarchy-element-assl.md) Element.|  
|[MdxScripts-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/mdxscripts-element-assl.md)|Enthält die Auflistung der [MdxScript](../../../analysis-services/scripting/objects/mdxscript-element-assl.md) Elemente, die zu einem [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) Element.|  
|[MeasureGroups-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/measuregroups-element-assl.md)|Enthält die Auflistung der [MeasureGroup](../../../analysis-services/scripting/objects/measuregroup-element-assl.md) Elemente mit dem übergeordneten Element verknüpft sind.|  
|[Measures-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/measures-element-assl.md)|Enthält die Auflistung der [Measure](../../../analysis-services/scripting/objects/measure-element-assl.md) Elemente mit dem übergeordneten Element verknüpft sind.|  
|[Members-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/members-element-assl.md)|Enthält die Auflistung der [Member](../../../analysis-services/scripting/objects/member-element-assl.md) -Elemente des übergeordneten Elements.|  
|[MiningModelPermissions-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/miningmodelpermissions-element-assl.md)|Enthält die Auflistung der Berechtigungen für eine [MiningModel](../../../analysis-services/scripting/objects/miningmodel-element-assl.md) Element.|  
|[MiningModels-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/miningmodels-element-assl.md)|Enthält die Auflistung der [MiningModel](../../../analysis-services/scripting/objects/miningmodel-element-assl.md) Elemente, die zu einem [MiningStructure](../../../analysis-services/scripting/objects/miningstructure-element-assl.md).|  
|[MiningStructurePermissions-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/miningstructurepermissions-element-assl.md)|Enthält die Auflistung der Berechtigungen auf eine [MiningStructure](../../../analysis-services/scripting/objects/miningstructure-element-assl.md) Element.|  
|[MiningStructures-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/miningstructures-element-assl.md)|Enthält die Auflistung der [MiningStructure](../../../analysis-services/scripting/objects/miningstructure-element-assl.md) Elemente in einem [Datenbank](../../../analysis-services/scripting/objects/database-element-assl.md) Element.|  
|[ModelingFlags-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/modelingflags-element-assl.md)|Enthält die Auflistung der [ModelingFlag](../../../analysis-services/scripting/objects/modelingflag-element-assl.md) Elemente für eine Spalte in einer [MiningStructure](../../../analysis-services/scripting/objects/miningstructure-element-assl.md) oder ein [MiningModel](../../../analysis-services/scripting/objects/miningmodel-element-assl.md).|  
|[Namingtemplatetranslation-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/namingtemplatetranslations-element-assl.md)|Stellt eine Auflistung lokalisierter Übersetzungen für die [NamingTemplate](../../../analysis-services/scripting/properties/namingtemplate-element-assl.md) Element des übergeordneten Elements [DimensionAttribute](../../../analysis-services/scripting/data-type/dimensionattribute-data-type-assl.md).|  
|[Partitions-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/partitions-element-assl.md)|Enthält die Auflistung der [Partition](../../../analysis-services/scripting/objects/partition-element-assl.md) Elementen, die verwendet werden, indem eine [MeasureGroup](../../../analysis-services/scripting/objects/measuregroup-element-assl.md) Element oder die Auflistung der partitionsbindungen, die eine Out-of-Line bilden [MeasureGroupBinding](../../../analysis-services/scripting/data-type/measuregroupbinding-data-type-out-of-line-assl.md)Element.|  
|[Perspectives-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/perspectives-element-assl.md)|Enthält die Auflistung der [Perspektive](../../../analysis-services/scripting/objects/perspective-element-assl.md) Elemente, die zu einem [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) Element.|  
|[QueryNotifications-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/querynotifications-element-assl.md)|Enthält die Auflistung der [QueryNotification](../../../analysis-services/scripting/objects/querynotification-element-assl.md) Elemente, die Informationen zum Bereitstellen der [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) -Element zu Abfragen ausführen, um zu bestimmen, ob eine Datenquelle geändert wurde.|  
|[ReportFormatParameters-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/reportformatparameters-element-assl.md)|Enthält die Auflistung der [ReportFormatParameter](../../../analysis-services/scripting/objects/reportformatparameter-element-asl.md) -Elemente für ein [ReportAction](../../../analysis-services/scripting/data-type/reportaction-data-type-assl.md) -Element.|  
|[ReportParameters-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/reportparameters-element-assl.md)|Enthält die Auflistung der [ReportParameter](../../../analysis-services/scripting/objects/reportparameter-element-assl.md) Elemente für eine [ReportAction](../../../analysis-services/scripting/data-type/reportaction-data-type-assl.md) Element.|  
|[Roles-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/roles-element-assl.md)|Enthält die Auflistung der [Role](../../../analysis-services/scripting/objects/role-element-assl.md) -Elemente, die unter dem übergeordneten Element definiert sind.|  
|[ServerProperties-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/serverproperties-element-assl.md)|Enthält die Auflistung der [ServerProperty](../../../analysis-services/scripting/objects/serverproperty-element-assl.md) Elemente, die zu einem [Server](../../../analysis-services/scripting/objects/server-element-assl.md) Element.|  
|[TableNotifications-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/tablenotifications-element-assl.md)|Enthält die Auflistung der [TableNotification](../../../analysis-services/scripting/objects/tablenotification-element-assl.md) Elemente, die Anmeldeinformationen für die [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) Element zu Tabellen oder Sichten in einer Datenquelle, die geändert wurden.|  
|[Traces-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/traces-element-assl.md)|Enthält die Auflistung der [Trace](../../../analysis-services/scripting/objects/trace-element-assl.md) -Elemente, die zu einem [Server](../../../analysis-services/scripting/objects/server-element-assl.md) -Element gehören.|  
|[Translations-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/translations-element-assl.md)|Enthält die Auflistung der [Übersetzung](../../../analysis-services/scripting/objects/translation-element-assl.md) Elemente mit dem übergeordneten Element verknüpft sind.|  
|[UnknownMemberTranslations-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/unknownmembertranslations-element-assl.md)|Enthält die Auflistung der Übersetzungen für die Beschriftung des der [UnknownMember](../../../analysis-services/scripting/properties/unknownmember-element-assl.md) -Elements einer Dimension.|  
  
## <a name="see-also"></a>Siehe auch  
 [Analysis Services Scripting Language-XML-Element-Hierarchie &#40; ASSL &#41;](../../../analysis-services/scripting/analysis-services-scripting-language-xml-element-hierarchy-assl.md)  
  
  