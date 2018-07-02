---
title: Erstellen, ändern und Löschen von gespeicherten Prozeduren | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- stored procedures [SMO]
ms.assetid: 2a072f9c-8f11-4364-ab71-3990735a8d66
caps.latest.revision: 44
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 18ab85b6ea304660e412e0e0156fcc1cc9491fc3
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36047562"
---
# <a name="creating-altering-and-removing-stored-procedures"></a>Erstellen, Ändern und Löschen von gespeicherten Prozeduren
  In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) werden gespeicherte Prozeduren werden dargestellt durch die <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> Objekt.  
  
 Erstellen einer <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> -Objekt in SMO erfordert die Einstellung der <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure.TextBody%2A> Eigenschaft, um die [!INCLUDE[tsql](../../../includes/tsql-md.md)] Skript, das die gespeicherte Prozedur definiert. Die Parameter erfordern das @-Prefix und müssen einzeln mithilfe der <xref:Microsoft.SqlServer.Management.Smo.StoredProcedureParameter>-Objekte und durch Hinzufügen der <xref:Microsoft.SqlServer.Management.Smo.StoredProcedureParameter>-Auflistung des <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure>-Objekts erstellt werden.  
  
## <a name="example"></a>Beispiel  
 Zum Verwenden eines angegebenen Codebeispiels müssen Sie die Programmierumgebung, Programmiervorlage und die zu verwendende Programmiersprache auswählen, um Ihre Anwendung zu erstellen. Weitere Informationen finden Sie unter [Erstellen eines Visual Basic SMO-Projekts in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) oder [Erstellen eines Visual C&#35; SMO-Projekts in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).  
  
## <a name="creating-altering-and-removing-a-stored-procedure-in-visual-basic"></a>Erstellen, Ändern und Entfernen einer gespeicherten Prozedur in Visual Basic  
 In diesem Codebeispiel wird veranschaulicht, wie eine gespeicherte Prozedur zum Erstellen der [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] Datenbank. Im Beispiel wird der Nachname eines Mitarbeiters zurückgegeben, wenn die Mitarbeiter-ID-Nummer angegeben wird. Die gespeicherte Prozedur erfordert einen Eingabeparameter zur Angabe der Mitarbeiter-ID-Nummer und einen Ausgabeparameter für die Rückgabe des Nachnamens des Mitarbeiters.  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBStoredProcs1](SMO How to#SMO_VBStoredProcs1)]  -->  
  
## <a name="creating-altering-and-removing-a-stored-procedure-in-visual-c"></a>Erstellen, Ändern und Löschen einer gespeicherten Prozedur in Visual C#  
 In diesem Codebeispiel wird veranschaulicht, wie eine gespeicherte Prozedur zum Erstellen der [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] Datenbank. Im Beispiel wird der Nachname eines Mitarbeiters zurückgegeben, wenn die Mitarbeiter-ID-Nummer angegeben wird (`BusinessEntityID`). Die gespeicherte Prozedur erfordert einen Eingabeparameter zur Angabe der Mitarbeiter-ID-Nummer und einen Ausgabeparameter für die Rückgabe des Nachnamens des Mitarbeiters.  
  
```  
{  
            //Connect to the local, default instance of SQL Server.   
            Server srv;  
            srv = new Server();  
            //Reference the AdventureWorks2012 database.   
            Database db;  
            db = srv.Databases["AdventureWorks2012"];  
            //Define a StoredProcedure object variable by supplying the parent database and name arguments in the constructor.   
            StoredProcedure sp;  
            sp = new StoredProcedure(db, "GetLastNameByBusinessEntityID");  
            //Set the TextMode property to false and then set the other object properties.   
            sp.TextMode = false;  
            sp.AnsiNullsStatus = false;  
            sp.QuotedIdentifierStatus = false;  
            //Add two parameters.   
            StoredProcedureParameter param;  
            param = new StoredProcedureParameter(sp, "@empval", DataType.Int);  
            sp.Parameters.Add(param);  
            StoredProcedureParameter param2;  
            param2 = new StoredProcedureParameter(sp, "@retval", DataType.NVarChar(50));  
            param2.IsOutputParameter = true;  
            sp.Parameters.Add(param2);  
            //Set the TextBody property to define the stored procedure.   
            string stmt;  
            stmt = " SELECT @retval = (SELECT LastName FROM Person.Person,HumanResources.Employee WHERE Person.Person.BusinessEntityID = HumanResources.Employee.BusinessentityID AND HumanResources.Employee.BusinessEntityID = @empval )";  
            sp.TextBody = stmt;  
            //Create the stored procedure on the instance of SQL Server.   
            sp.Create();  
            //Modify a property and run the Alter method to make the change on the instance of SQL Server.   
            sp.QuotedIdentifierStatus = true;  
            sp.Alter();  
            //Remove the stored procedure.   
            sp.Drop();  
        }  
```  
  
## <a name="creating-altering-and-removing-a-stored-procedure-in-powershell"></a>Erstellen, Ändern und Löschen einer gespeicherten Prozedur in PowerShell  
 In diesem Codebeispiel wird veranschaulicht, wie eine gespeicherte Prozedur zum Erstellen der [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] Datenbank. Im Beispiel wird der Nachname eines Mitarbeiters zurückgegeben, wenn die Mitarbeiter-ID-Nummer angegeben wird (`BusinessEntityID`). Die gespeicherte Prozedur erfordert einen Eingabeparameter zur Angabe der Mitarbeiter-ID-Nummer und einen Ausgabeparameter für die Rückgabe des Nachnamens des Mitarbeiters.  
  
```  
# Set the path context to the local, default instance of SQL Server and get a reference to AdventureWorks2012  
CD \sql\localhost\default\databases  
$db = get-item Adventureworks2012  
  
# Define a StoredProcedure object variable by supplying the parent database and name arguments in the constructor.   
$sp  = New-Object -TypeName Microsoft.SqlServer.Management.SMO.StoredProcedure `  
-argumentlist $db, "GetLastNameByBusinessEntityID"  
  
#Set the TextMode property to false and then set the other object properties.   
$sp.TextMode = $false  
$sp.AnsiNullsStatus = $false  
$sp.QuotedIdentifierStatus = $false  
  
# Add two parameters  
$type = [Microsoft.SqlServer.Management.SMO.Datatype]::Int  
$param  = New-Object -TypeName Microsoft.SqlServer.Management.SMO.StoredProcedureParameter `  
-argumentlist $sp,"@empval",$type  
$sp.Parameters.Add($param)  
  
$type = [Microsoft.SqlServer.Management.SMO.DataType]::NVarChar(50)  
$param2  = New-Object -TypeName Microsoft.SqlServer.Management.SMO.StoredProcedureParameter `  
-argumentlist $sp,"@retval",$type  
$param2.IsOutputParameter = $true  
$sp.Parameters.Add($param2)  
  
#Set the TextBody property to define the stored procedure.   
$sp.TextBody =  " SELECT @retval = (SELECT LastName FROM Person.Person,HumanResources.Employee WHERE Person.Person.BusinessEntityID = HumanResources.Employee.BusinessentityID AND HumanResources.Employee.BusinessEntityID = @empval )"  
  
# Create the stored procedure on the instance of SQL Server.   
$sp.Create()  
  
# Modify a property and run the Alter method to make the change on the instance of SQL Server.   
$sp.QuotedIdentifierStatus = $true  
$sp.Alter()  
  
#Remove the stored procedure.   
$sp.Drop()  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure>  
  
  