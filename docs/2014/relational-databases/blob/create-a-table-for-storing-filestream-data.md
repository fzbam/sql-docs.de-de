---
title: Erstellen einer Tabelle zum Speichern von FILESTREAM-Daten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-blob
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FILESTREAM [SQL Server], table storage
ms.assetid: 029c3059-5c83-43e2-a859-9027031b7de1
caps.latest.revision: 16
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 34c7053b878f49be1b3aa3f6c9aee4a7bc2e24e4
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36160922"
---
# <a name="create-a-table-for-storing-filestream-data"></a>Erstellen einer Tabelle zum Speichern von FILESTREAM-Daten
  In diesem Thema wird erläutert, wie Sie eine Tabelle zum Speichern von FILESTREAM-Daten erstellen.  
  
 Wenn die Datenbank eine FILESTREAM-Dateigruppe aufweist, können Sie Tabellen zum Speichern von FILESTREAM-Daten erstellen oder ändern. Um anzugeben, dass eine Spalte FILESTREAM-Daten enthält, erstellen Sie eine `varbinary(max)`-Spalte und fügen das FILESTREAM-Attribut hinzu.  
  
### <a name="to-create-a-table-to-store-filestream-data"></a>So erstellen Sie eine Tabelle zum Speichern von FILESTREAM-Daten  
  
1.  Klicken Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]auf **Neue Abfrage** , um den Abfrage-Editor zu öffnen.  
  
2.  Kopieren Sie den [!INCLUDE[tsql](../../includes/tsql-md.md)] -Code aus dem folgenden Beispiel in den Abfrage-Editor. Dieser [!INCLUDE[tsql](../../includes/tsql-md.md)] -Code erstellt eine FILESTREAM-aktivierte Tabelle mit dem Namen Records.  
  
3.  Klicken Sie auf **Ausführen**, um die Tabelle zu erstellen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel zeigt, wie eine Tabelle mit der Bezeichnung `Records`erstellt wird. Die `Id` -Spalte ist eine `ROWGUIDCOL` -Spalte, die zur Verwendung von FILESTREAM-Daten mit Win32-APIs erforderlich ist. Die `SerialNumber` -Spalte ist eine `UNIQUE INTEGER`-Spalte. Die `Chart` -Spalte ist eine `FILESTREAM` -Spalte, die verwendet wird, um `Chart` im Dateisystem zu speichern.  
  
> [!NOTE]  
>  Dieses Beispiel bezieht sich auf die Datenbank „Archive“, die unter [Vorgehensweise: Erstellen einer FILESTREAM-aktivierten Datenbank](create-a-filestream-enabled-database.md)erstellt wird.  
  
 [!code-sql[FILESTREAM#FS_CreateTable](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_createtable)]  
  
## <a name="see-also"></a>Siehe auch  
 [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql)   
 [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql)  
  
  