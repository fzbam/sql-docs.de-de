---
title: Sys. database_scoped_configurations (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 05/14/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.component: system-catalog-views
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- database_scoped_configurations
- database_scoped_configurations_TSQL
- sys.database_scoped_configurations
- sys.database_scoped_configurations_TSQL
helpviewer_keywords:
- sys.database_scoped_configurations catalog view
ms.assetid: 8899310a-3464-4d38-9f2f-88396c4e7dc2
caps.latest.revision: 13
author: CarlRabeler
ms.author: carlrab
manager: craigg
monikerRange: = azuresqldb-current || >= sql-server-2016 || = sqlallproducts-allversions
ms.openlocfilehash: 373d2933d362f565799518bfe1af516ad1943276
ms.sourcegitcommit: 0cc2cb281e467a13a76174e0d9afbdcf4ccddc29
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2018
---
# <a name="sysdatabasescopedconfigurations-transact-sql"></a>Sys. database_scoped_configurations (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

  Enthält eine Zeile für jede Konfiguration. 
  
|Spaltenname|Datentyp|Description|  
|-----------------|---------------|-----------------|  
|**configuration_id**|**int**|Die ID der Konfigurationsoption.|  
|**name**|**nvarchar(60)**|Der Name der Konfigurationsoption. Informationen zu den möglichen Konfigurationen finden Sie unter [ALTER DATABASE SCOPED CONFIGURATION &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-scoped-configuration-transact-sql.md).|  
|**value**|**sqlvariant**|Der Wert für diese Konfigurationsoption für das primäre Replikat festgelegt.|  
|**value_for_secondary**|**sqlvariant**|Der Wert für diese Konfigurationsoption für die sekundären Replikate.|  
|**elevate_online**|**nvarchar(60)** |Die Datenbank im Bereich einer Standardsatz für die online-Option für Indexvorgänge |
|**elevate_resumable**|nvarchar(60)|Die Datenbank im Bereich einer Standardsatz für die fortsetzbar-Option für Indexvorgänge| 
  
##  <a name="Permissions"></a> Berechtigungen  
 Erfordert die Mitgliedschaft in der **public** -Rolle.  
  
## <a name="remarks"></a>Hinweise  
 Wenn NULL zurückgegeben wird, als der Wert für **Value_for_secondary**, dies bedeutet, dass die sekundäre Datenbank auf Primär festgelegt ist.  
 
 Die datenbankweit gültigen Konfigurationseinstellungen werden mit der Datenbank übertragen. Dies bedeutet, dass die vorhandenen Konfigurationseinstellungen bei der Wiederherstellung oder dem Anfügen einer bestimmten Datenbank erhalten bleiben.
  
## <a name="see-also"></a>Siehe auch  
 [ALTER DATABASE SCOPED CONFIGURATION (Transact-SQL)](../../t-sql/statements/alter-database-scoped-configuration-transact-sql.md)  
  
  
