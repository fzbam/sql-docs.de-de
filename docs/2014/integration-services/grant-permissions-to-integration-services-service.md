---
title: Erteilen von Berechtigungen an Integration Services-Dienst | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c2caa68-7834-4ea0-bd77-4f3a7c86d634
caps.latest.revision: 7
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: 32b8ee36951ec828340de5c6d581f0b8d8bc919a
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36149097"
---
# <a name="grant-permissions-to-integration-services-service"></a>Gewähren von Berechtigungen an Integration Services-Dienst
  In vorherigen Versionen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]hatten alle Benutzer in der Gruppe Benutzer standardmäßig Zugriff auf den Dienst [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , wenn Sie [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] installiert haben. Wenn Sie die aktuelle Version von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]installieren, haben Benutzer keinen Zugriff auf den Dienst [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] . Der Dienst ist standardmäßig sicher. Nach der Installation von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] muss der Administrator Zugriff auf den Dienst gewähren.  
  
### <a name="to-grant-access-to-the-integration-services-service"></a>So gewähren Sie Zugriff auf den Integration Services-Dienst  
  
1.  Führen Sie "Dcomcnfg.exe" aus. "Dcomcnfg.exe" verfügt über eine Benutzeroberfläche, über die Sie bestimmte Einstellungen in der Registrierung ändern können.  
  
2.  Erweitern Sie im Dialogfeld **Komponentendienste** den Knoten „Komponentendienste“ > „Computer“ > „Arbeitsplatz“ > „DCOM-Konfiguration“.  
  
3.  Mit der rechten Maustaste **Microsoft SQL Server Integration Services 12.0**, und klicken Sie dann auf **Eigenschaften**.  
  
4.  Klicken Sie auf der Registerkarte **Sicherheit** im Abschnitt **Start- und Aktivierungsberechtigungen** auf **Bearbeiten** .  
  
5.  Fügen Sie Benutzer hinzu, weisen Sie ihnen entsprechende Berechtigungen zu, und klicken Sie dann auf OK.  
  
6.  Wiederholen Sie die Schritte 4 - 5 für Zugriffsberechtigungen.  
  
7.  Starten Sie SQL Server Management Studio neu.  
  
8.  Starten Sie den [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Dienst neu.  
  
  