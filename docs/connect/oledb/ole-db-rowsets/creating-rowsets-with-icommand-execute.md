---
title: 'Erstellen von Rowsets mit ICommand:: Execute | Microsoft Docs'
description: 'Erstellen von Rowsets mit ICommand:: Execute'
ms.custom: ''
ms.date: 03/26/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.component: ole-db-rowsets
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- rowsets [OLE DB], creating
- OLE DB Driver for SQL Server, rowsets
- OLE DB rowsets, creating
- Execute method
author: pmasl
ms.author: Pedro.Lopes
manager: craigg
ms.openlocfilehash: 6b7fc3b387144ba6442b99ede37818c72b4ef462
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="creating-rowsets-with-icommandexecute"></a>Erstellen von Rowsets mit 'ICommand::Execute'
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

  Für Rowsets erstellt mithilfe der **ICommand:: Execute** -Methode, die Eigenschaften, die im resultierenden Rowset sollen können Sie den Text des Befehls einschränken. Dies ist insbesondere für Consumer wichtig, die dynamischen Befehlstext unterstützen.  
  
 Der OLE DB-Treiber für SQL Server können keine [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Cursor zur Unterstützung der mehrere rowsetergebnisse von zahlreichen Befehlen generiert. Wenn ein Consumer ein Rowset anfordert, das Unterstützung durch [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Cursor benötigt, tritt ein Fehler auf, falls der Befehlstext mehr als ein einzelnes Rowset als Ergebnis generiert. Weitere Informationen finden Sie unter [Befehle generiert mehrere Rowsetergebnisse](../../oledb/ole-db-commands/commands-generating-multiple-rowset-results.md).  
  
 Bildlauffähige OLE DB-Treiber für SQL Server-Rowsets werden von unterstützt [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Cursor. [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] erzwingt Einschränkungen für Cursor, die durch Änderungen anderer Benutzer der Datenbank beeinflusst werden können. Konkret kann die Reihenfolge der Zeilen in einigen Cursorn nicht verändert werden, und der Versuch, ein Rowset mithilfe eines Befehls zu erstellen, der eine SQL ORDER BY-Klausel enthält, kann fehlschlagen. Weitere Informationen finden Sie unter [Rowsets und SQL Server-Cursor](../../oledb/ole-db-rowsets/rowsets-and-sql-server-cursors.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Rowsets](../../oledb/ole-db-rowsets/rowsets.md)  
  
  
