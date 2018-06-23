---
title: Laden von XML-Daten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-xml
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML data [SQL Server], loading
- loading XML data
ms.assetid: d1741e8d-f44e-49ec-9f14-10208b5468a7
caps.latest.revision: 19
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: e3b250b955028e3f0843699688713cb731f00fee
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36150297"
---
# <a name="load-xml-data"></a>Laden von XML-Daten
  XML-Daten können auf unterschiedliche Weise in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] übertragen werden. Zum Beispiel:  
  
-   Wenn sich die Daten in einer [n]text- oder image-Spalte einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank befinden, können Sie die Tabelle mithilfe von [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]importieren. Ändern Sie den Spaltentyp mithilfe der ALTER TABLE-Anweisung zu XML.  
  
-   Sie können bcp out zum Massenkopieren Ihrer Daten aus einer anderen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbanken verwenden, um sie dann mit bcp in als Masseneinfügung in eine aktuellere Datenbankversion einzufügen.  
  
-   Wenn Sie über Daten in relationalen Spalten in einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank verfügen, erstellen Sie eine neue Tabelle in einer [n]text-Spalte und optional eine Primärschlüsselspalte für einen Zeilenbezeichner. Mithilfe clientseitiger Programmierung den XML-Indexinformationen abzurufen, die auf dem Server mit FOR XML generiert wird, und Schreiben Sie ihn in die `[n]text` Spalte. Verwenden Sie dann die oben erwähnten Techniken, um die Daten in eine höhere Version der Datenbank zu übertragen. Sie können den XML-Code auch direkt in eine XML-Spalte in der Datenbank der höheren Version schreiben.  
  
## <a name="bulk-loading-xml-data"></a>Massenladen von XML-Daten  
 Sie können XML-Daten mit einem Massenladevorgang auf den Server laden, indem Sie die Massenladefunktionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verwenden, z. B. bcp. Mit OPENROWSET können Sie Daten aus Dateien in eine XML-Spalte laden. Das folgende Beispiel veranschaulicht diesen Punkt.  
  
##### <a name="example-loading-xml-from-files"></a>Beispiel: Laden von XML-Daten aus Dateien  
 Dieses Beispiel zeigt, wie eine Zeile in Tabelle T eingefügt wird. Der Wert der XML-Spalte wird aus der Datei C:\MyFile\xmlfile.xml als CLOB geladen, und die integer-Spalte erhält den Wert 10.  
  
```  
INSERT INTO T  
SELECT 10, xCol  
FROM    (SELECT *      
    FROM OPENROWSET (BULK 'C:\MyFile\xmlfile.xml', SINGLE_CLOB)   
 AS xCol) AS R(xCol)  
```  
  
## <a name="text-encoding"></a>Textcodierung  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] speichert XML-Daten im Unicode (UTF-16)-Format. Die vom Server abgerufenen XML-Daten liegen UTF-16-codiert vor. Wenn Sie eine andere Codierung wünschen, müssen Sie die erforderliche Konvertierung für die abgerufenen Daten ausführen. Manchmal können die XML-Daten in einer abweichenden Codierung vorliegen. Wenn das der Fall ist, müssen Sie beim Laden der Daten mit großer Sorgfalt vorgehen. Zum Beispiel:  
  
-   Wenn Ihre Text-XML-Daten in Unicode (UCS-2, UTF-16) vorliegen, können Sie sie problemlos einer XML-Spalte, einer XML-Variablen oder einem XML-Parameter zuweisen.  
  
-   Wenn die Codierung nicht Unicode ist und aufgrund der Quellcodeseite implizit ist, sollte die Zeichenfolgencodeseite in der Datenbank den Codepunkten gleichen oder mit den Codepunkten kompatibel sein, die Sie laden wollen. Verwenden Sie falls erforderlich COLLATE. Wenn keine solche Servercodeseite vorhanden ist, müssen Sie eine explizite XML-Deklaration mit der richtigen Codierung hinzufügen.  
  
-   Um eine explizite Codierung verwendet werden soll, verwenden Sie entweder die `varbinary()` Typ, der keinerlei Interaktion mit Codeseiten aufweist, oder einen Zeichenfolgentyp der entsprechenden Codeseite. Weisen Sie anschließend die Daten einer XML-Spalte, einer XML-Variablen oder einem XML-Parameter zu.  
  
### <a name="example-explicitly-specifying-an-encoding"></a>Beispiel: Explizites Angeben einer Codierung  
 Angenommen, Sie besitzen das XML-Dokument vcdoc, das im Datentyp `varchar(max)` gespeichert ist und keine explizite XML-Deklaration aufweist. Die folgende Anweisung wird eine XML-Deklaration mit der Codierung "iso8859-1" hinzugefügt, das XML-Dokument verkettet, wandelt das Ergebnis, das `varbinary(max)` , damit die bytedarstellung erhalten werden, und schließlich in XML umgewandelt. Das ermöglicht es dem XML-Prozessor, die Daten entsprechend der angegebenen Codierung "iso8859-1" zu analysieren und die entsprechende UTF-16-Darstellung für Zeichenfolgenwerte zu generieren.  
  
```  
SELECT CAST(   
CAST (('<?xml version="1.0" encoding="iso8859-1"?>'+ vcdoc) AS VARBINARY (MAX))   
 AS XML)  
```  
  
### <a name="string-encoding-incompatibilities"></a>Inkompatibilitäten bei der Zeichenfolgencodierung  
 Wenn Sie XML als Zeichenfolgenliteral kopieren und in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]im Abfrage-Editor einfügen, stellen Sie ggf. Inkompatibilitäten bei [N]VARCHAR-Zeichenfolgencodierungen fest. Dies hängt von der Codierung Ihrer XML-Instanz ab. In vielen Fällen möchten Sie die XML-Deklaration möglicherweise entfernen. Zum Beispiel:  
  
```  
<?xml version="1.0" encoding="UTF-8"?>  
  <xsd:schema …  
```  
  
 Dann sollten Sie ein N einfügen, um aus der XML-Instanz eine Unicodeinstanz zu machen. Zum Beispiel:  
  
```  
-- Assign XML instance to a variable.  
DECLARE @X XML  
SET @X = N'…'  
-- Insert XML instance into an xml type column.  
INSERT INTO T VALUES (N'…')  
-- Create an XML schema collection  
CREATE XML SCHEMA COLLECTION XMLCOLL1 AS N'<xsd:schema … '  
```  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Daten &#40;SQL Server&#41;](xml-data-sql-server.md)  
  
  