---
title: 'Lektion 1: Erstellen von RDL-Schema-Visual Studio-Projekt | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f420509c-51aa-4170-8c25-64c2954f4bb9
caps.latest.revision: 17
author: douglaslM
ms.author: douglasl
manager: mblythe
ms.openlocfilehash: b6c502205f669c48efe1f939ba88e5352205f4de
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36159899"
---
# <a name="lesson-1-create-the-rdl-schema-visual-studio-project"></a>Lektion 1: Erstellen des RDL-Schema-Projekts in Visual Studio
  In diesem Lernprogramm erstellen Sie eine einfache Konsolenanwendung. In diesem Lernprogramm wird vorausgesetzt, Sie entwickeln [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)].  
  
> [!NOTE]  
>  Wenn Sie auf den Berichtsserver-Webdienst zugreifen, der in [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] mit Advanced Services ausgeführt wird, müssen Sie "_SQLExpress" an den "ReportServer"-Pfad anfügen. Zum Beispiel:  
>   
>  `http://myserver/reportserver_sqlexpress/reportservice2010.asmx"`  
  
### <a name="to-create-the-web-service-proxy"></a>So erstellen Sie den Webdienstproxy  
  
1.  Aus der **starten** klicken Sie im Menü **Programme**, klicken Sie dann Microsoft Visual Studio, klicken Sie dann **Visual Studio-Tools**, und klicken Sie dann **Visual Studio 2010-Eingabeaufforderung** .  
  
2.  Führen Sie den folgenden Befehl im Eingabeaufforderungsfenster aus, wenn Sie C# verwenden:  
  
    ```  
    wsdl /language:CS /n:"ReportService2010" http://<Server Name>/reportserver/reportservice2010.asmx?wsdl  
    ```  
  
     Wenn Sie Visual Basic verwenden, führen Sie dann den folgenden Befehl aus: ///  
  
    ```  
    wsdl /language:VB /n:"ReportService2010" http://<Server Name>/reportserver/reportservice2010.asmx?wsdl  
    ```  
  
     Dieser Befehl generiert eine .cs oder eine .vb-Datei. Sie fügen diese Datei der Anwendung hinzu.  
  
### <a name="to-create-a-console-application"></a>So erstellen Sie eine Konsolenanwendung  
  
1.  Auf der **Datei** Startmenü nacheinander auf **neu**, und klicken Sie dann auf **Projekt** So öffnen die **neues Projekt** (Dialogfeld).  
  
2.  Im linken Bereich unter **installierte Vorlagen**, klicken Sie auf **Visual Basic** oder **Visual C#-** Knoten, und wählen Sie eine Kategorie für Projekttypen, in der erweiterten Liste.  
  
3.  Wählen Sie die **Konsolenanwendung** Projekttyp.  
  
4.  In der **Namen** Geben Sie einen Namen für das Projekt. Geben Sie den Namen `SampleRDLSchema`.  
  
5.  In der **Speicherort** Feld, geben Sie den Pfad, in dem Sie das Projekt gespeichert werden soll, oder klicken möchten **Durchsuchen** zu dem Ordner zu navigieren.  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)] Eine reduzierte Ansicht des Projekts wird im Projektmappen-Explorer angezeigt.  
  
7.  Klicken Sie im Menü **Projekt** auf **Vorhandenes Element hinzufügen**.  
  
8.  Navigieren Sie zum Speicherort der CS- oder VB-Datei löschen, die Sie generiert, wählen Sie dann die Datei, und klicken Sie dann auf **hinzufügen**.  
  
     Sie müssen auch einen Verweis hinzufügen der <xref:System.Web.Services> Namespace-URI für den Webverweis arbeiten.  
  
9. Klicken Sie auf das Menü Projekt auf **Verweis hinzufügen**.  
  
     In der **Verweis hinzufügen** Dialogfeld die **.NET** Registerkarte **System.Web.Services**, klicken Sie dann auf **OK**.  
  
     Weitere Informationen zum Herstellen einer Verbindung mit der Berichtsserver-Webdienst finden Sie unter [Erstellen von Anwendungen mit dem Webdienst und .NET Framework](../reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md).  
  
10. Erweitern Sie den Projektknoten im Projektmappen-Explorer. Sehen Sie eine Codedatei mit dem Standardnamen Program.cs (Module1.vb für [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) zu Ihrem Projekt hinzugefügt wurde.  
  
11. Öffnen Sie die Datei "Program.cs" (bzw. Module1.vb für [!INCLUDE[vbprvb](../includes/vbprvb-md.md)])-Datei und Ersetzen Sie den Code durch Folgendes:  
  
     Mit dem folgenden Code werden die Methodenstubs bereitgestellt, die zum Implementieren der Funktionalität zum Laden, Aktualisieren und Speichern verwendet werden.  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.IO;  
    using System.Text;  
    using System.Xml;  
    using System.Xml.Serialization;  
    using ReportService2010;  
  
    namespace SampleRDLSchema  
    {  
        class ReportUpdater  
        {  
            ReportingService2010 _reportService;  
  
            static void Main(string[] args)  
            {  
                ReportUpdater reportUpdater = new ReportUpdater();  
                reportUpdater.UpdateReport();  
            }  
  
            private void UpdateReport()  
            {  
                try  
                {  
                    // Set up the Report Service connection  
                    _reportService = new ReportingService2010();  
                    _reportService.Credentials =  
                        System.Net.CredentialCache.DefaultCredentials;  
                    _reportService.Url =  
                       "http://<Server Name>/reportserver/" +  
                                       "reportservice2010.asmx";  
  
                    // Call the methods to update a report definition  
                    LoadReportDefinition();  
                    UpdateReportDefinition();  
                    PublishReportDefinition();  
                }  
                catch (Exception ex)  
                {  
                    System.Console.WriteLine(ex.Message);  
                }  
            }  
  
            private void LoadReportDefinition()  
            {  
                //Lesson 3: Load a report definition from the report   
                //          catalog  
            }  
  
            private void UpdateReportDefinition()  
            {  
                //Lesson 4: Update the report definition using the    
                //          classes generated from the RDL Schema  
            }  
  
            private void PublishReportDefinition()  
            {  
                //Lesson 5: Publish the updated report definition back   
                //          to the report catalog  
            }  
        }  
    }  
    ```  
  
    ```vb  
    Imports System  
    Imports System.Collections.Generic  
    Imports System.IO  
    Imports System.Text  
    Imports System.Xml  
    Imports System.Xml.Serialization  
    Imports ReportService2010  
  
    Namespace SampleRDLSchema  
  
        Module ReportUpdater  
  
            Private m_reportService As ReportingService2010  
  
            Public Sub Main(ByVal args As String())  
  
                Try  
                    'Set up the Report Service connection  
                    m_reportService = New ReportingService2010  
                    m_reportService.Credentials = _  
                        System.Net.CredentialCache.DefaultCredentials  
                    m_reportService.Url = _  
                        "http:// <Server Name>/reportserver/" & _  
                               "reportservice2010.asmx"  
  
                    'Call the methods to update a report definition  
                    LoadReportDefinition()  
                    UpdateReportDefinition()  
                    PublishReportDefinition()  
                Catch ex As Exception  
                    System.Console.WriteLine(ex.Message)  
                End Try  
  
            End Sub  
  
            Private Sub LoadReportDefinition()  
                'Lesson 3: Load a report definition from the report   
                '          catalog  
            End Sub  
  
            Private Sub UpdateReportDefinition()  
                'Lesson 4: Update the report definition using the   
                '          classes generated from the RDL Schema  
            End Sub  
  
            Private Sub PublishReportDefinition()  
                'Lesson 5: Publish the updated report definition back   
                '          to the report catalog  
            End Sub  
  
        End Module  
  
    End Namespace   
    ```  
  
## <a name="next-lesson"></a>Nächste Lektion  
 In der nächsten Lektion generieren Sie mithilfe des XML-Schemadefinitionstools (Xsd.exe) Klassen aus dem RDL-Schema und fügen diese in das Projekt ein. Finden Sie unter [Lektion 2: Generieren von Klassen aus dem RDL-Schema mithilfe des XSD-Tool](../../2014/tutorials/lesson-2-generate-classes-from-the-rdl-schema-using-the-xsd-tool.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Aktualisieren von Berichten mithilfe von Klassen, die aus dem RDL-Schema generierten &#40;SSRS-Lernprogramm&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md)   
 [Berichtsdefinitionssprache (SSRS)](../reporting-services/reports/report-definition-language-ssrs.md)  
  
  