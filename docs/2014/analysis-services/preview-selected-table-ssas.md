---
title: Vorschau der ausgewählten Tabelle (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql12.asvs.bidtoolset.previewselecttable.f1
ms.assetid: b6b34b5a-43b3-4a75-9f3b-b2ad1084b1b6
caps.latest.revision: 11
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: ccaa243593d2885ab935e1cbe4da5c194d36b708
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36046775"
---
# <a name="preview-selected-table-ssas"></a>Vorschau der ausgewählten Tabelle (SSAS)
  Auf dieser Seite des **Tabellenimport-Assistenten** können Sie die Daten in der ausgewählten Tabelle in der Vorschau anzeigen, die Spalten auswählen, die im Datenimport enthalten sein sollen, und Daten in den ausgewählten Spalten filtern. Um im [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]auf den Assistenten zuzugreifen, klicken Sie im Menü **Modell** auf **Aus Datenquelle importieren**.  
  
 Nicht alle Zeilen in der Tabelle werden angezeigt. Die festgelegten Filter werden jedoch während des Imports auf alle Daten in der Tabelle angewendet.  
  
 Für Datenquellen mit Windows-Authentifizierung werden die Anmeldeinformationen des aktuellen Benutzers verwendet, um die im Dialogfeld Vorschau anzeigen und filtern angezeigten Daten abzurufen. Für andere Datenquellen werden die in der Verbindungszeichenfolge angegebenen Anmeldeinformationen zum Abrufen der Daten verwendet.  
  
 Die Darstellung der Daten auf dieser Seite garantiert nicht, dass der Import erfolgreich ist. Der Import ist nicht erfolgreich, wenn der auf der Seite Identitätswechselinformationen angegebene Benutzername nicht über ausreichend Berechtigungen zum Lesen aus der ausgewählten Datenbank verfügt.  
  
## <a name="uielement-list"></a>Liste der Benutzeroberflächenelemente  
 **Kontrollkästchen im Spaltenheader**  
 Aktivieren Sie das Kontrollkästchen, um die Spalte in den Datenimport einzuschließen. Deaktivieren Sie das Kontrollkästchen, um die Spalte aus dem Datenimport zu entfernen.  
  
 **Nach-unten Schaltfläche in der Kopfzeile der Spalte**  
 Filtern Sie Daten in der Spalte.  
  
 **Zeilenfilter löschen**  
 Entfernen Sie alle Filter, die auf die Daten in den Spalten angewendet wurden.  
  
  