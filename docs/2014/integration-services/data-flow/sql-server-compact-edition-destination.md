---
title: SQL Server Compact Edition-Ziel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql12.dts.designer.sqlservercompactdest.f1
helpviewer_keywords:
- destinations [Integration Services], SQL Server Compact
- SQL Server Compact, destination
- inserting data
ms.assetid: 697742ba-cc14-414d-8187-1845ad0dd99b
caps.latest.revision: 56
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: 59754dabe5cfb4da9fc131874fb6e04057cee959
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36048294"
---
# <a name="sql-server-compact-edition-destination"></a>SQL Server Compact Edition-Ziel
  Das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact-Ziel schreibt Daten in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact-Datenbanken.  
  
> [!NOTE]  
>  Auf einem 64-Bit-Computer müssen Sie Pakete, die mit den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact-Datenquellen verbunden sind, im 32-Bit-Modus ausführen. Der Anbieter von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact, der von [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] zum Herstellen einer Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact-Datenquellen verwendet wird, ist lediglich in einer 32-Bit-Version verfügbar.  
  
 Sie konfigurieren das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact-Ziel, indem Sie den Namen der Tabelle angeben, in die die Daten vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact-Ziel eingefügt werden. Die benutzerdefinierte Eigenschaft TableName des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact-Ziels enthält den Tabellennamen.  
  
 Von diesem Ziel wird ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact-Verbindungs-Manager zum Herstellen einer Verbindung mit einer Datenquelle verwendet, und der Verbindungs-Manager gibt den zu verwendenden OLE DB-Anbieter an. Weitere Informationen finden Sie unter [SQL Server Compact Edition-Verbindungs-Managerl](../connection-manager/sql-server-compact-edition-connection-manager.md).  
  
 Das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact-Ziel schließt die benutzerdefinierte Eigenschaft TableName ein, die beim Laden des Pakets durch einen Eigenschaftsausdruck aktualisiert werden kann. Weitere Informationen finden Sie unter [Integration Services-Ausdrücke &#40;SSIS&#41;](../expressions/integration-services-ssis-expressions.md), [Verwenden von Eigenschaftsausdrücken in Paketen](../expressions/use-property-expressions-in-packages.md) und [Benutzerdefinierte Eigenschaften des Ziels für SQL Server Compact Edition](sql-server-compact-edition-destination-custom-properties.md).  
  
 Das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact-Ziel hat eine Eingabe und unterstützt keine Fehlerausgabe.  
  
## <a name="configuration-of-the-sql-server-compact-edition-destination"></a>Konfiguration des SQL Server Compact Edition-Ziels  
 Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.  
  
 Das Dialogfeld **Erweiterter Editor** enthält die Eigenschaften, die programmgesteuert festgelegt werden können. Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Erweiterter Editor** oder programmgesteuert festlegen können:  
  
-   [Common Properties](../common-properties.md)  
  
-   [Benutzerdefinierte Eigenschaften des SQL Server-Ziels](sql-server-destination-custom-properties.md)  
  
## <a name="related-tasks"></a>Related Tasks  
 Weitere Informationen zum Festlegen von Eigenschaften finden Sie unter [Festlegen der Eigenschaften einer Datenflusskomponente](set-the-properties-of-a-data-flow-component.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Datenfluss](data-flow.md)  
  
  