---
title: Sp_update_agent_profile (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: replication
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to: SQL Server
f1_keywords:
- sp_update_agent_profile_TSQL
- sp_update_agent_profile
helpviewer_keywords: sp_update_agent_profile
ms.assetid: cc81f227-0df3-4151-bb4d-4f45ea997b71
caps.latest.revision: "27"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: d4f3088c28098611567b80de916b84b73800dc2e
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="spupdateagentprofile-transact-sql"></a>sp_update_agent_profile (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Aktualisiert das von einem Replikations-Agent verwendete Profil. Diese gespeicherte Prozedur wird auf dem Verteiler für die Verteilungsdatenbank ausgeführt.  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
  
sp_update_agent_profile [@agent_type=] agent_type, [ @agent_id= ] agent_id, [ @profile_id= ] profile_id  
```  
  
## <a name="arguments"></a>Argumente  
 [**@agent_type=**] **"***Agent_type***"**  
 Der Typ des Agents. *Agent_type* ist **Int**, hat keinen Standardwert und kann einen der folgenden Werte sein.  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|**1**|Momentaufnahme-Agent.|  
|**2**|Protokolllese-Agent.|  
|**3**|Verteilungs-Agent.|  
|**4**|Merge-Agent an.|  
|**9**|Warteschlangenlese-Agent|  
  
 [**@agent_id=**] *agent_id-Wert*  
 Ist die ID des Agents. *Agent_id* ist **Int**, hat keinen Standardwert.  
  
 [**@profile_id=**] *Profile_id*  
 Die ID des Profils, das der Agent verwenden soll. *Profile_id* ist **Int**, hat keinen Standardwert. Verwenden Sie zum Anzeigen einer Liste der für jeden Agent definierten Profile [Sp_help_agent_profile &#40; Transact-SQL &#41; ](../../relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql.md). Weitere Informationen zu Systemprofilen finden Sie unter [Replikations-Agentprofilen](../../relational-databases/replication/agents/replication-agent-profiles.md).  
  
## <a name="return-code-values"></a>Rückgabecodewerte  
 **0** (Erfolg) oder **1** (Fehler)  
  
## <a name="remarks"></a>Hinweise  
 **Sp_update_agent_profile** wird für alle Replikationstypen verwendet.  
  
## <a name="permissions"></a>Berechtigungen  
 Nur Mitglieder der **Sysadmin** -Serverrolle kann ausführen **Sp_update_agent_profile**.  
  
## <a name="see-also"></a>Siehe auch  
 [Replikations-Agent-Profile](../../relational-databases/replication/agents/replication-agent-profiles.md)   
 [Sp_add_agent_profile &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-add-agent-profile-transact-sql.md)   
 [Sp_change_agent_profile &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-change-agent-profile-transact-sql.md)   
 [Sp_drop_agent_profile &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-drop-agent-profile-transact-sql.md)   
 [Sp_help_agent_profile &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql.md)   
 [Gespeicherte Systemprozeduren &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  