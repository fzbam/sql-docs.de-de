---
title: Erstellen, ändern und Löschen von Standardwerten | Microsoft Docs
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
- defaults [SMO]
ms.assetid: c30ac3b9-8150-4264-ba4c-c549f44261ab
caps.latest.revision: 43
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: d7daddec0a7c96776938f2824635b719341ecbe4
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36048943"
---
# <a name="creating-altering-and-removing-defaults"></a>Erstellen, Ändern und Löschen von Standardwerten
  In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) wird die Standardeinschränkung durch das <xref:Microsoft.SqlServer.Management.Smo.Default>-Objekt dargestellt.  
  
 Die <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> Eigenschaft von der <xref:Microsoft.SqlServer.Management.Smo.Default> Objekt dient zum Festlegen des Werts eingefügt werden. Dies kann eine Konstante oder eine [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Anweisung sein, die einen konstanten Wert zurückgibt, z. B. GETDATE(). Die <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A>-Eigenschaft kann über die <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A>-Methode nicht geändert werden. Stattdessen die <xref:Microsoft.SqlServer.Management.Smo.Default> Objekt muss gelöscht und neu erstellt werden.  
  
## <a name="example"></a>Beispiel  
 Zum Verwenden eines angegebenen Codebeispiels müssen Sie die Programmierumgebung, Programmiervorlage und die zu verwendende Programmiersprache auswählen, um Ihre Anwendung zu erstellen. Weitere Informationen finden Sie unter [Erstellen eines Visual Basic SMO-Projekts in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) oder [Erstellen eines Visual C&#35; SMO-Projekts in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).  
  
## <a name="creating-altering-and-removing-a-default-in-visual-basic"></a>Erstellen, Ändern und Löschen eines Standardwerts in Visual Basic  
 Dieses Codebeispiel zeigt, wie erstellt ein Standard, der einfachen Text ist, und ein anderer Standardwert, der eine [!INCLUDE[tsql](../../../includes/tsql-md.md)] Anweisung. Der Standard muss mithilfe der Spalte angefügt werden die <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.BindToColumn%2A> Methode und getrennt werden, mithilfe der <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.UnbindFromColumn%2A> Methode.  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBDefaults1](SMO How to#SMO_VBDefaults1)]  -->  
  
## <a name="creating-altering-and-removing-a-default-in-visual-c"></a>Erstellen, Ändern und Löschen eines Standardwerts in Visual C#  
 Dieses Codebeispiel zeigt, wie erstellt ein Standard, der einfachen Text ist, und ein anderer Standardwert, der eine [!INCLUDE[tsql](../../../includes/tsql-md.md)] Anweisung. Der Standard muss mithilfe der Spalte angefügt werden die <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.BindToColumn%2A> Methode und getrennt werden, mithilfe der <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.UnbindFromColumn%2A> Methode.  
  
```  
{  
  
          Server srv = new Server();  
  
            //Reference the AdventureWorks2012 database.   
            Database  db = srv.Databases["AdventureWorks2012"];  
  
            //Define a Default object variable by supplying the parent database and the default name   
            //in the constructor.   
            Default def = new Default(db, "Test_Default2");  
  
            //Set the TextHeader and TextBody properties that define the default.   
            def.TextHeader = "CREATE DEFAULT [Test_Default2] AS";  
            def.TextBody = "GetDate()";  
  
            //Create the default on the instance of SQL Server.   
            def.Create();  
  
            //Bind the default to a column in a table in AdventureWorks2012  
            def.BindToColumn("SpecialOffer", "StartDate", "Sales");  
  
            //Unbind the default from the column and remove it from the database.   
            def.UnbindFromColumn("SpecialOffer", "StartDate", "Sales");  
            def.Drop();  
        }  
```  
  
## <a name="creating-altering-and-removing-a-default-in-powershell"></a>Erstellen, Ändern und Löschen eines Standardwerts in PowerShell  
 Dieses Codebeispiel zeigt, wie erstellt ein Standard, der einfachen Text ist, und ein anderer Standardwert, der eine [!INCLUDE[tsql](../../../includes/tsql-md.md)] Anweisung. Der Standard muss mithilfe der Spalte angefügt werden die <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.BindToColumn%2A> Methode und getrennt werden, mithilfe der <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.UnbindFromColumn%2A> Methode.  
  
```  
# Set the path context to the local, default instance of SQL Server and get a reference to AdventureWorks2012  
CD \sql\localhost\default\databases  
$db = get-item Adventureworks2012  
  
#Define a Default object variable by supplying the parent database and the default name in the constructor.  
$def = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Default `  
-argumentlist $db, "Test_Default2"  
  
#Set the TextHeader and TextBody properties that define the default.   
$def.TextHeader = "CREATE DEFAULT [Test_Default2] AS"  
$def.TextBody = "GetDate()"  
  
#Create the default on the instance of SQL Server.   
$def.Create()  
  
#Bind the default to the column.   
$def.BindToColumn("SpecialOffer", "StartDate", "Sales")  
  
#Unbind the default from the column and remove it from the database.   
$def.UnbindFromColumn("SpecialOffer", "StartDate", "Sales")  
$def.Drop()  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.SqlServer.Management.Smo.Default>  
  
  