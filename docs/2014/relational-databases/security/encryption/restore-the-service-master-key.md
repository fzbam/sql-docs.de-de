---
title: Wiederherstellen des Diensthauptschlüssels | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-security
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service master key [SQL Server], importing
- service master key [SQL Server], restoring
ms.assetid: 14bdbbbe-d384-4692-b670-4243d2466fe1
caps.latest.revision: 15
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: ffa66ce3d53c647a282f7bce0bad494eb8ebcaf5
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36059102"
---
# <a name="restore-the-service-master-key"></a>Wiederherstellen des Diensthauptschlüssels
  In diesem Thema wird beschrieben, wie der Diensthauptschlüssel in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[tsql](../../../includes/tsql-md.md)]wiederhergestellt wird.  
  
> [!WARNING]  
>  Es ist unwahrscheinlich, dass die Notwendigkeit zum Wiederherstellen des Diensthauptschlüssels eintreten wird. Sollte dies doch erforderlich sein, muss dies mit äußerster Sorgfalt erfolgen. Weitere Informationen finden Sie unter [Back Up the Service Master Key](service-master-key.md).  
  
 **In diesem Thema**  
  
-   **Vorbereitungen:**  
  
     [Einschränkungen](#Restrictions)  
  
     [Security](#Security)  
  
-   [So stellen Sie den Diensthauptschlüssel mithilfe von Transact-SQL wieder her](#SSMSProcedure)  
  
##  <a name="BeforeYouBegin"></a> Vorbereitungen  
  
###  <a name="Restrictions"></a> Einschränkungen  
  
-   Bei der Wiederherstellung des Diensthauptschlüssels werden alle Schlüssel und geheimen Bereiche von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] entschlüsselt, die mit dem aktuellen Diensthauptschlüssel verschlüsselt wurden. Diese Schlüssel werden dann mit dem aus der Sicherungsdatei geladenen Diensthauptschlüssel verschlüsselt.  
  
-   Falls einer dieser Entschlüsselungsvorgänge nicht erfolgreich ausgeführt werden kann, tritt bei der Wiederherstellung ein Fehler auf. Sie können die FORCE-Option verwenden, um Fehler zu ignorieren, dies kann jedoch zum Verlust von Daten führen, die nicht entschlüsselt werden können.  
  
-   Das Neugenerieren der Verschlüsselungshierarchie ist ein ressourcenintensiver Vorgang. Die Ausführung dieses Vorgangs sollte außerhalb der Hauptzeiten geplant werden.  
  
> [!CAUTION]  
>  Der Diensthauptschlüssel ist der Stamm der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Verschlüsselungshierarchie. Mit dem Diensthauptschlüssel werden alle Schlüssel in der Struktur direkt oder indirekt geschützt. Wenn ein abhängiger Schlüssel während der erzwungenen Wiederherstellung nicht entschlüsselt werden kann, gehen die durch diesen Schlüssel geschützten Daten verloren.  
  
###  <a name="Security"></a> Sicherheit  
  
####  <a name="Permissions"></a> Berechtigungen  
 Erfordert die CONTROL SERVER-Berechtigung auf dem Server.  
  
##  <a name="SSMSProcedure"></a> Verwenden von Transact-SQL  
  
#### <a name="to-restore-the-service-master-key"></a>So stellen Sie den Diensthauptschlüssel wieder her  
  
1.  Rufen Sie entweder von einem physischen Sicherungsmedium oder einem Verzeichnis im lokalen Dateisystem eine Kopie des gesicherten Diensthauptschlüssels ab.  
  
2.  Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.  
  
3.  Klicken Sie in der Standardleiste auf **Neue Abfrage**.  
  
4.  Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.  
  
    ```  
    -- Restores the service master key from a backup file.  
    RESTORE SERVICE MASTER KEY   
        FROM FILE = 'c:\temp_backups\keys\service_master_key'   
        DECRYPTION BY PASSWORD = '3dH85Hhk003GHk2597gheij4';  
    GO  
    ```  
  
    > [!NOTE]  
    >  Der Dateipfad zum Schlüssel und das Kennwort (sofern es vorhanden ist) des Schlüssels unterscheiden sich von den obigen Informationen. Stellen Sie sicher, dass beide für den Server und die Schlüsseleinrichtung spezifisch sind.  
  
  