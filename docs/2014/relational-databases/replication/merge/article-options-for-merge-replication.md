---
title: Artikeloptionen für die Mergereplikation | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- merge replication [SQL Server replication], article options
- articles [SQL Server replication], merge replication options
ms.assetid: 670abd41-d204-4cd7-a371-7664e603a0ce
caps.latest.revision: 36
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: f59594ffbb8fcb3edc4d07837b5f4bd3083a9572
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36059827"
---
# <a name="article-options-for-merge-replication"></a>Artikeloptionen für die Mergereplikation
  Die Mergereplikation bietet viele Optionen für Mergetabellenartikel, mit denen Sie das Replikationsverhalten den Anforderungen Ihrer Anwendungen anpassen können. Der Einsatz der Mergereplikation bietet folgende Möglichkeiten:  
  
-   Sie können Zeilenfilter, Joinfilter und Spaltenfilter verwenden. Das Filtern von Tabellenartikeln ermöglicht es Ihnen, Datenpartitionen zu erstellen, die veröffentlicht werden können. Weitere Informationen finden Sie unter [Filtern von veröffentlichten Daten](../publish/filter-published-data.md).  
  
-   Sie können angeben, ob Änderungen des Abonnenten auf den Verleger hochgeladen werden sollen. Bei Anwendungen, in denen auf dem Abonnenten bestimmte oder alle Daten schreibgeschützt sein sollen, bieten nur herunterladbare Artikel eine Möglichkeit zur Leistungssteigerung. Weitere Informationen finden Sie unter [Optimieren der Leistung der Mergereplikation durch nur herunterladbare Artikel](optimize-merge-replication-performance-with-download-only-articles.md).  
  
-   Sie können angeben, dass Löschvorgänge für einen oder mehrere Artikel nicht von Replikationstriggern oder in Systemtabellen nachverfolgt werden sollen. Diese Option kann in vielen Anwendungsszenarios nützlich sein. Hierzu gehören auch Szenarios mit Batchlöschvorgängen, die nicht repliziert werden müssen. Weitere Informationen finden Sie unter [Optimieren der Mergereplikationsleistung durch bedingtes Nachverfolgen von Löschvorgängen](optimize-merge-replication-performance-with-conditional-delete-tracking.md).  
  
-   Sie können die Verarbeitungsreihenfolge von Artikeln angeben, um sicherzustellen, dass diese in der für die Anwendung erforderlichen Reihenfolge verarbeitet werden. Weitere Informationen finden Sie unter [Angeben der Verarbeitungsreihenfolge von Mergeartikeln](specify-the-processing-order-of-merge-articles.md).  
  
-   Sie können angeben, dass miteinander verbundene Datensätze als Einheit verarbeitet werden sollen (standardmäßig verarbeitet die Mergereplikation Änderungen in Tabellen zeilenweise). Weitere Informationen finden Sie unter [Gruppieren von Änderungen an verknüpften Zeilen mithilfe von logischen Datensätzen](group-changes-to-related-rows-with-logical-records.md).  
  
-   Sie können die Konflikterkennung und -lösung verwenden, wenn dieselben Daten auf mehreren Knoten der Topologie geändert werden. Weitere Informationen finden Sie unter [Detect and Resolve Merge Replication Conflicts](advanced-merge-replication-resolve-merge-replication-conflicts.md).  
  
-   Sie können Schemaoptionen angeben, beispielsweise ob Einschränkungen und Trigger auf den Abonnenten kopiert werden. Weitere Informationen finden Sie unter [Angeben von Schemaoptionen](../publish/specify-schema-options.md).  
  
-   Verwenden Sie einen Geschäftslogikhandler, um während der Synchronisierung auf viele Bedingungen zu reagieren. Hierzu gehören Datenänderungen, Konflikte und Fehler. Weitere Informationen finden Sie unter [Ausführen von Geschäftslogik während der Mergesynchronisierung](execute-business-logic-during-merge-synchronization.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Veröffentlichen von Daten und Datenbankobjekten](../publish/publish-data-and-database-objects.md)  
  
  