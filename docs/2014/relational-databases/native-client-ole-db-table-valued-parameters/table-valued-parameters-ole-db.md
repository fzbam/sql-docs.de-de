---
title: Tabellenwertparameter (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- OLE DB, table-valued parameters
- table-valued parameters (OLE DB)
ms.assetid: 4298b73d-615b-4d28-9843-03b4d5fc489e
caps.latest.revision: 26
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1a3a4e683887022c905fd2faf45cf5ff36b57a3a
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36160409"
---
# <a name="table-valued-parameters-ole-db"></a>Tabellenwertparameter (OLE DB)
  In diesem Abschnitt wird die Unterstützung für Tabellenwertparameter in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter beschrieben. Übersicht die zusätzliche Übersichtsinformationen finden Sie unter [Table-Valued Parameters &#40;SQL Server Native Client&#41;](../native-client/features/table-valued-parameters-sql-server-native-client.md). Ein Beispiel finden Sie unter [Tabellenwertparametern &#40;OLE DB-&#41;](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md).  
  
## <a name="remarks"></a>Hinweise  
 Derzeit können Sie mehrzeilige Daten an den Server als Parameter an eine Prozedur mit Parametersätzen senden (der DBPARAMS-Parameter in `ICommand::Execute`). Bei Parametersätzen muss jedes Element des Satzes in einer separaten Remoteprozeduranforderung (Remote Procedure Call, RPC) an den Server gesendet werden. Tabellenwertparameter stellen eine ähnliche Funktionalität bereit, bieten jedoch eine bessere Integration mit dem Server. Dadurch werden die Anzahl von RPC-Anforderungen reduziert und setbasierte Vorgänge auf dem Server aktiviert.  
  
 Tabellenwertparameter werden in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter als OLE DB `Rowset`-Objekte unterstützt. Jedes `Rowset`-Objekt kann vom Consumer (d. h. von der Clientanwendung, die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter verwendet) als Platzhalter für Tabellenwertparameter bereitgestellt werden. Tabellenwertparameter werden wie andere [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Parametertypen behandelt. Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter stellt Erstellungs-, Ermittlungs-, Spezifizierungs-, Bindungs- und Schemaschnittstellen zur Verfügung.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
-   [Tabellenwertparameter-Rowseterstellung](table-valued-parameter-rowset-creation.md)  
  
-   [Tabellenwertparameter-Typermittlung](../../database-engine/dev-guide/table-valued-parameter-type-discovery.md)  
  
-   [Ausführen von Befehlen, die Tabellenwertparameter enthalten](executing-commands-containing-table-valued-parameters.md)  
  
-   [Einfügen von Daten in Tabellenwertparameter](inserting-data-into-table-valued-parameters.md)  
  
-   [Schemarowsets für OLE DB-Tabellenwertparameter geändert](schema-rowsets-changed-for-ole-db-table-valued-parameters.md)  
  
-   [OLE DB-Typunterstützung für Tabellenwertparameter](ole-db-table-valued-parameter-type-support.md)  
  
-   [Unterstützung des OLE DB-Tabellenwertparameter-Typ &#40;Methoden&#41;](ole-db-table-valued-parameter-type-support-methods.md)  
  
-   [Unterstützung des OLE DB-Tabellenwertparameter-Typ &#40;Eigenschaften&#41;](ole-db-table-valued-parameter-type-support-properties.md)  
  
## <a name="see-also"></a>Siehe auch  
 [SQL Server Native Client &#40;OLE DB&#41;](../native-client/ole-db/sql-server-native-client-ole-db.md)   
 [Verwenden von Tabellenwertparametern &#40;OLE DB&#41;](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  