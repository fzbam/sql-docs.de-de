---
title: Benutzerdefinierte Eigenschaften des SQL Server-Ziels | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b736aa6d-c154-44a0-be08-f25733fca1d9
caps.latest.revision: 6
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: 9a2a69e8c25f55e973740d9b13e39fdb59440a36
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36161162"
---
# <a name="sql-server-destination-custom-properties"></a>Benutzerdefinierte Eigenschaften des SQL Server-Ziels
  Das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Ziel verfügt sowohl über benutzerdefinierte Eigenschaften als auch über die Eigenschaften, die allen Datenflusskomponenten gemeinsam sind.  
  
 In der folgenden Tabelle werden die benutzerdefinierten Eigenschaften des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Ziels beschrieben. Alle Eigenschaften weisen Lese-/Schreibzugriff auf.  
  
|Eigenschaftenname|Datentyp|Description|  
|-------------------|---------------|-----------------|  
|AlwaysUseDefaultCodePage|Boolean|Erzwingt die Verwendung des Eigenschaftswerts „DefaultCodePage“. Der Standardwert dieser Eigenschaft ist `False`.|  
|BulkInsertCheckConstraints|Boolean|Ein Wert, der angibt, ob die Masseneinfügung Einschränkungen überprüft. Der Standardwert dieser Eigenschaft ist `True`.|  
|BulkInsertFireTriggers|Boolean|Ein Wert, der angibt, ob die Masseneinfügung Trigger in Tabellen auslöst. Der Standardwert dieser Eigenschaft ist `False`.|  
|BulkInsertFirstRow|Integer|Ein Wert, der die erste einzufügende Zeile angibt. Der Standardwert dieser Eigenschaft lautet **-1**und bedeutet, dass kein Wert zugewiesen wurde.|  
|BulkInsertKeepIdentity|Boolean|Ein Wert, der angibt, ob Werte in Identitätsspalten eingefügt werden können. Der Standardwert dieser Eigenschaft ist `False`.|  
|BulkInsertKeepNulls|Boolean|Ein Wert, der angibt, ob die Masseneinfügung NULL-Werte beibehält. Der Standardwert dieser Eigenschaft ist `False`.|  
|BulkInsertLastRow|Integer|Ein Wert, der die letzte einzufügende Zeile angibt. Der Standardwert dieser Eigenschaft lautet **-1**und bedeutet, dass kein Wert zugewiesen wurde.|  
|BulkInsertMaxErrors|Integer|Ein Wert, der die Anzahl der Fehler angibt, die auftreten können, bevor die Masseneinfügung abgebrochen wird. Der Standardwert dieser Eigenschaft lautet **-1**und zeigt an, dass kein Wert zugewiesen wurde.|  
|BulkInsertOrder|Zeichenfolge|Die Namen der zu sortierenden Spalten. Jede Spalte kann in auf- oder absteigender Reihenfolge sortiert werden. Wenn mehrere Sortierspalten verwendet werden, sind die Spaltennamen durch Trennzeichen getrennt.|  
|BulkInsertTableName|Zeichenfolge|Die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Tabelle oder -Sicht in der Datenbank, in die die Daten kopiert werden.|  
|BulkInsertTablock|Boolean|Ein Wert, der angibt, ob die Tabelle während der Masseneinfügung gesperrt ist. Der Standardwert dieser Eigenschaft ist `True`.|  
|DefaultCodePage|Integer|Die zu verwendende Codepage, wenn keine Codepageinformationen aus der Datenquelle verfügbar sind.|  
|MaxInsertCommitSize|Integer|Ein Wert, der die maximale Anzahl von Zeilen angibt, die in einen Batch eingefügt werden können. Wenn der Wert 0 (null) ist, werden alle Zeilen in einen einzelnen Batch eingefügt.|  
|Timeout|Integer|Ein Wert, der die Anzahl der Sekunden angibt, für die das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Ziel vor dem Abbruch wartet, wenn keine Daten zum Einfügen verfügbar sind. Der Wert 0 bedeutet, dass für das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Ziel kein Timeout eintritt. Der Standardwert dieser Eigenschaft ist 30.|  
  
 Die Eingabe und die Eingabespalten des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Ziels verfügen nicht über benutzerdefinierte Eigenschaften.  
  
 Weitere Informationen finden Sie unter [SQL Server Destination](sql-server-destination.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Common Properties](../common-properties.md)  
  
  