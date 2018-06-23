---
title: 'Lektion 5: Automatisierung der Bereinigung und Abgleich mit SSIS | Microsoft Docs'
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- data-quality-services
- integration-services
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f068d4db-2d56-41b1-bed2-0cffa3ca411d
caps.latest.revision: 8
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: 00dff9ac204e5e1b86feafc51da643222bce1758
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36048184"
---
# <a name="lesson-5-automating-the-cleansing-and-matching-using-ssis"></a>Lektion 5: Automatisierung der Bereinigung und des Abgleich mit SSIS
  In Lektion 1 die Wissensdatenbank ' Suppliers ' erstellt und in Lektion 2 Daten bereinigen und Abgleichen der Daten in Lektion 3 mit dem Tool zur **DQS-Client**. In einem realen Szenario müssen Sie möglicherweise Daten aus einer Quelle, die DQS nicht unterstützt, oder Sie die Bereinigung automatisieren möchten und den Abgleichsprozess abrufen, ohne Verwenden der **DQS-Client** Tool. SQL Server Integration Services (SSIS) besteht aus Komponenten, die Sie verwenden können, um Daten aus verschiedenen heterogenen Quellen zu integrieren und eine **[HYPERLINK "http://msdn.microsoft.com/library/ee677619.aspx" \t "_blank" DQS-Bereinigungstransformation](http://msdn.microsoft.com/library/ee677619.aspx)** Komponente, für die DQS bereinigungsfunktionalität aufzurufen. Momentan DQS macht keine Abgleichsfunktionalität für SSIS, aber Sie können die **[Transformation für Fuzzygruppierung](http://msdn.microsoft.com/library/ms141764.aspx)** um Duplikate in den Daten zu identifizieren.  
  
 Sie können Daten in MDS hochladen, mithilfe der **Entitätsbasierte stagingfunktion**. Wenn Sie eine Entität in MDS erstellen, werden entsprechende Stagingtabellen und gespeicherte Prozeduren automatisch erstellt. Z. B. beim Erstellen der Entität "Supplier", die **supplier_leaf** Tabelle und die **stg. udp_supplier_leaf** gespeicherte Prozedur automatisch erstellt wurden. Sie verwenden die Stagingtabellen und Prozeduren, um Entitätselemente zu erstellen, zu aktualisieren und zu löschen. In dieser Lektion erstellen Sie neue Entitätselemente für die Entität "Suppliers". Um Daten auf den MDS-Server zu laden, lädt das SSIS-Paket zuerst die Daten in die Stagingtabelle stg.supplier_Leaf und löst dann die zugeordnete gespeicherte Prozedur stg.udp_Supplier_Leaf aus. Finden Sie unter [Importieren von Daten](http://msdn.microsoft.com/library/ee633726.aspx) Weitere Details.  
  
 In dieser Lektion führen Sie die folgenden Aufgaben aus:  
  
1.  Entfernen Sie Lieferantendaten in MDS (wenn Sie die vorherigen vier Lektionen durchgearbeitet haben). Das SSIS-Paket, das Sie in dieser Lektion erstellen, lädt die Daten in MDS automatisch hoch. Sie haben die bereinigten und abgeglichenen Lieferantendaten in einem früheren Schritt manuell mit DQS-Client auf den MDS-Server hochgeladen.  
  
2.  Erstellen Sie eine Abonnementsicht in der Entität "Suppliers", um Daten in der Entität anderen Anwendungen bereitzustellen. Diese Aktion erstellt eine SQL-Sicht, die Sie mit SQL Server Management Studio überprüfen. Sie werden diese Sicht nicht in dieser Version des Lernprogramms nutzen.  
  
3.  Erstellen und Ausführen ein SSIS-Projekts mit **SQL Server Data Tools**. Das Projekt verwendet **DatenBereinigung** Transformation, um eine bereinigungsanforderung an den DQS-Server zu senden. DQS macht nicht die entsprechende Funktionalität noch, daher Sie verwenden **Fuzzygruppierung** Transformation, um Duplikate zu identifizieren.  
  
4.  Überprüfen Sie mit Master Data Manager, ob die Daten in MDS erstellt wurden.  
  
5.  Überprüfen Sie die Ergebnisse des DQS-Bereinigungsprojekts, das vom SSIS-Paket erstellt wurde, und führen Sie optional eine interaktive Bereinigung durch, um die Wissensdatenbank auszubauen.  
  
## <a name="next-step"></a>Nächster Schritt  
 [Aufgabe 1 &#40;erforderliche&#41;: Entfernen von Lieferantendaten in MDS](../../2014/tutorials/task-1-prerequisite-removing-supplier-data-in-mds.md)  
  
  