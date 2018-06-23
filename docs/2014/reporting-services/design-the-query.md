---
title: Entwerfen der Abfrage | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql12.rtp.rptwizard.designquery.f1
ms.assetid: 2dad800f-10a1-453c-8761-2935b9826d84
caps.latest.revision: 39
author: douglaslM
ms.author: douglasl
manager: mblythe
ms.openlocfilehash: 2ca850de7e8f09f704434910ccf0fa45cbfca726
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36160378"
---
# <a name="design-the-query"></a>Entwerfen der Abfrage
  Auf dieser Seite des Berichts-Assistenten können Sie eine Abfrage erstellen, indem Sie die Abfrage entweder manuell eingeben, den Abfrage-Generator für die interaktive Erstellung der Abfrage nutzen oder indem Sie eine Abfrage aus einem anderen Bericht importieren.  
  
 Der auf der Seite Datenquelle auswählen, einer vorhergehenden Seite im Berichts-Assistenten, von Ihnen ausgewählte Datenquellentyp bestimmt die Abfrage, die Sie auf dieser Seite eingeben können. Wenn der Datenquellentyp beispielsweise [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]ist, können Sie [!INCLUDE[tsql](../includes/tsql-md.md)] -Anweisungen oder Namen von gespeicherten Prozeduren eingeben. Wenn der Datenquellentyp [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]ist, ist der Abfragebereich deaktiviert, sodass Sie Abfragen nicht direkt eingeben können. Sie können Abfragen mithilfe des Abfrage-Generators angeben.  
  
## <a name="options"></a>Tastatur  
 **Abfragezeichenfolge**  
 Geben Sie eine Abfrage ein, die die Daten abruft, die Sie in Ihrem Bericht verwenden möchten.  
  
 **Abfrage-Generator**  
 Klicken Sie auf **Abfrage-Generator** , um einen Abfrage-Designer für die Datenquelle zu öffnen oder eine Abfrage aus einem anderen Bericht zu importieren.  
  
 Weitere Informationen zu Abfrage-Designern finden Sie unter [Reporting Services Query Designers](../../2014/reporting-services/reporting-services-query-designers.md).  
  
## <a name="example"></a>Beispiel  
 Für den Datenquellentyp **Microsoft SQL Server**, die folgende Abfrage ruft eine Liste der Nachnamen aus der [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] Datenbank `Person` Tabelle.  
  
```  
SELECT LastName FROM Person.Person;  
```  
  
 Für den Datenquellentyp **Microsoft SQL Server**, die folgende Abfrage die [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] gespeicherte Prozedur `uspGetEmployeeManagers` -Nummer für den Mitarbeiter mit der ID 1:  
  
```  
EXEC uspgetEmployeeManagers '1';  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Hilfe zum Berichts-Assistenten](../../2014/reporting-services/report-wizard-help.md)   
 [Erstellen von Berichten zu eingebetteten und freigegebenen Datasets &#40;Berichts-Generator und SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)   
 [Hinzufügen von Daten zu einem Bericht &#40;Berichts-Generator und SSRS&#41;](report-data/report-datasets-ssrs.md)  
  
  