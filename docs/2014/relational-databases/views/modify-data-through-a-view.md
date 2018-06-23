---
title: Ändern von Daten über eine Ansicht | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-views
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data modifications [SQL Server], views
- views [SQL Server], modifying data through
- modifying data [SQL Server], views
ms.assetid: 410e2812-4ebe-48b2-b95f-c7784f1c4336
caps.latest.revision: 33
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: fbc9d4bd90bea3dd6589fd92c8548653c5315d02
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36151764"
---
# <a name="modify-data-through-a-view"></a>Ändern von Daten über eine Sicht
  Sie können die Daten einer zugrunde liegenden Basistabelle in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]ändern.  
  
 **In diesem Thema**  
  
-   **Vorbereitungen:**  
  
     [Einschränkungen](#Restrictions)  
  
     [Security](#Security)  
  
-   **So ändern Sie Tabellendaten durch eine Sicht mit:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> Vorbereitungsmaßnahmen  
  
###  <a name="Restrictions"></a> Einschränkungen  
  
-   Weitere Informationen finden Sie im Abschnitt „Aktualisierbare Sichten“ in [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).  
  
###  <a name="Security"></a> Sicherheit  
  
####  <a name="Permissions"></a> Berechtigungen  
 Erfordert je nach ausgeführter Aktion Berechtigungen für UPDATE, INSERT oder DELETE in der Zieltabelle.  
  
##  <a name="SSMSProcedure"></a> Verwenden von SQL Server Management Studio  
  
#### <a name="to-modify-table-data-through-a-view"></a>So ändern Sie Tabellendaten durch eine Sicht  
  
1.  Erweitern Sie in **Objekt-Explorer**die Datenbank, die die Sicht enthält, und erweitern Sie dann **Sichten**.  
  
2.  Klicken Sie mit der rechten Maustaste auf die Sicht, und wählen Sie **Die ersten 200 Zeilen bearbeiten**aus.  
  
3.  Sie müssen möglicherweise die SELECT-Anweisung im Bereich **SQL** ändern, um die Zeilen zurückzugeben, die geändert werden sollen.  
  
4.  Suchen Sie im Bereich **Ergebnisse** die zu ändernde oder zu löschende Zeile. Klicken Sie mit der rechten Maustaste auf die zu löschende Zeile, und wählen Sie **Löschen**aus. Zum Ändern von Daten in mindestens einer Spalte ändern Sie die Daten in der Spalte.  
  
    > [!IMPORTANT]  
    >  Sie können keine Zeile löschen, wenn die Sicht auf mehr als eine Basistabelle verweist. Sie können nur Spalten aktualisieren, die zu einer einzelnen Basistabelle gehören.  
  
5.  Zum Einfügen einer Zeile führen Sie einen Bildlauf nach unten zum Ende der Zeilen durch, und fügen Sie die neuen Werte ein.  
  
    > [!IMPORTANT]  
    >  Sie können keine Zeile einfügen, wenn die Sicht auf mehr als eine Basistabelle verweist.  
  
##  <a name="TsqlProcedure"></a> Verwenden von Transact-SQL  
  
#### <a name="to-update-table-data-through-a-view"></a>So aktualisieren Sie Tabellendaten durch eine Sicht  
  
1.  Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.  
  
2.  Klicken Sie in der Standardleiste auf **Neue Abfrage**.  
  
3.  Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**. In diesem Beispiel wird der Wert in den Spalten `StartDate` und `EndDate` für einen bestimmten Mitarbeiter geändert, indem in der Sicht `HumanResources.vEmployeeDepartmentHistory`auf Spalten verwiesen wird. Diese Sicht gibt Werte von zwei Tabellen zurück. Diese Anweisung ist erfolgreich, da die geänderten Spalten aus nur einer der Basistabellen stammen.  
  
    ```  
    USE AdventureWorks2012 ;   
    GO  
    UPDATE HumanResources.vEmployeeDepartmentHistory  
    SET StartDate = '20110203', EndDate = GETDATE()   
    WHERE LastName = N'Smith' AND FirstName = 'Samantha';   
    GO  
    ```  
  
 Weitere Informationen finden Sie unter [UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql).  
  
#### <a name="to-insert-table-data-through-a-view"></a>So fügen Sie Tabellendaten durch eine Sicht ein  
  
1.  Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.  
  
2.  Klicken Sie in der Standardleiste auf **Neue Abfrage**.  
  
3.  Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**. Im Beispiel wird eine neue Zeile in die Basistabelle `HumanResouces.Department` eingefügt, indem die relevanten Spalten der Sicht `HumanResources.vEmployeeDepartmentHistory`angegeben werden. Die Anweisung ist erfolgreich, da nur Spalten von einer einzelnen Basistabelle angegeben werden. In den anderen Spalten der Basistabelle befinden sich Standardwerte.  
  
    ```  
    USE AdventureWorks2012 ;  
    GO  
    INSERT INTO HumanResources.vEmployeeDepartmentHistory (Department, GroupName)   
    VALUES ('MyDepartment', 'MyGroup');   
    GO  
    ```  
  
 Weitere Informationen finden Sie unter [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql).  
  
  