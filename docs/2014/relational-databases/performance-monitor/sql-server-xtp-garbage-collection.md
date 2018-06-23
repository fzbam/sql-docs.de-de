---
title: XTP-Garbagecollection | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 64ae91e5-b420-44b4-af1a-f8bca83d7f41
caps.latest.revision: 5
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 20f321806077a60aa0a3c628efb38505afa01679
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36060931"
---
# <a name="xtp-garbage-collection"></a>XTP Garbage Collection
  Das XTP-Leistungsobjekt für die Garbage Collection enthält Leistungsindikatoren für die Garbage Collection der XTP-Engine.  
  
 Diese Tabelle beschreibt die **XTP-Garbage Collection** Leistungsindikatoren.  
  
|Leistungsindikator|Description|  
|-------------|-----------------|  
|**Dusty-Corner-Scanwiederholungen/s (durch GC ausgegeben)**|Die durchschnittliche Anzahl von Scanwiederholungen aufgrund von Schreibkonflikten während Dusty-Corner-Sweep-Vorgängen, die pro Sekunde durch die Garbage Collection ausgegeben werden. Dieser Leistungsindikator befindet sich auf einer sehr niedrigen Ebene und dient nicht der Verwendung durch Kunden.|  
|**Arbeitselemente des GC-Hauptthreads/s**|Die Anzahl an Arbeitselementen, die vom GC-Hauptthread verarbeitet werden.|  
|**Parallele GC-Arbeitselemente/s**|Die Häufigkeit, mit der ein paralleler Thread ein GC-Arbeitselement ausgeführt hat.|  
|**Verarbeitete Zeilen/s**|Die durchschnittliche Anzahl von Zeilen, die pro Sekunde von der Garbage Collection verarbeitet werden.|  
|**Verarbeitete Zeilen/s (erste in Bucket und entfernt)**|Die durchschnittliche Anzahl der pro Sekunde von der Garbage Collection verarbeiteten Zeilen, die sich zuerst im entsprechenden Hashbucket befanden und sofort entfernt werden konnten.|  
|**Verarbeitete Zeilen/s (erste in Bucket)**|Die durchschnittliche Anzahl der pro Sekunde verarbeiteten Zeilen, die sich zuerst im entsprechenden Hashbucket befanden.|  
|**Verarbeitete Zeilen/s (zum Aufheben der Verknüpfung markiert)**|Die durchschnittliche Anzahl der pro Sekunde von der Garbage Collection verarbeiteten Zeilen, die bereits für das Aufheben der Verknüpfung markiert waren.|  
|**Verarbeitete Zeilen/s (kein Sweep erforderlich)**|Die durchschnittliche Anzahl der pro Sekunde von der Garbage Collection verarbeiteten Zeilen, für die kein Dusty-Corner-Sweep-Vorgang erforderlich ist.|  
|**Entfernte nach Sweep abgelaufene Zeilen/s**|Die durchschnittliche Anzahl der pro Sekunde abgelaufenen Zeilen, die bei Dusty-Corner-Sweep-Vorgängen entfernt werden.|  
|**Berührte nach Sweep abgelaufene Zeilen/s**|Die durchschnittliche Anzahl der abgelaufenen Zeilen, die pro Sekunde bei Dusty-Corner-Sweep-Vorgängen berührt werden.|  
|**Berührte nach Sweep ablaufende Zeilen/s**|Die durchschnittliche Anzahl ablaufender Zeilen, die pro Sekunde bei Dusty-Corner-Sweep-Vorgängen berührt werden.|  
|**Berührte Sweepzeilen/s**|Die durchschnittliche Anzahl der Zeilen, die pro Sekunde bei Dusty-Corner-Sweep-Vorgängen berührt werden.|  
|**Gestartete Sweep-Scans/s**|Die durchschnittliche Anzahl der pro Sekunde gestarteten Dusty-Corner-Sweep-Scans.|  
  
## <a name="see-also"></a>Siehe auch  
 [XTP &#40;In-Memory OLTP&#41; -Leistungsindikatoren](../../integration-services/performance/performance-counters.md)  
  
  