---
title: So importieren Sie eine richtlinienbasierte Verwaltungsrichtlinie | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, import policy
ms.assetid: 850b7ef9-d2b7-4754-bf04-7cb419ffb776
caps.latest.revision: 10
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 40c9e6e32cebd7811a57ae1b8154fb446d8f90e4
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37302310"
---
# <a name="import-a-policy-based-management-policy"></a>Importieren einer Richtlinie der richtlinienbasierten Verwaltung
  In diesem Thema wird beschrieben, wie Sie eine Instanz einer Richtlinie der richtlinienbasierten Verwaltung mithilfe von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]importieren.  
  
 **In diesem Thema**  
  
-   **Vorbereitungen:**  
  
     [Einschränkungen](#Restrictions)  
  
     [Security](#Security)  
  
-   **Importieren einer Richtlinieninstanz mit:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
##  <a name="BeforeYouBegin"></a> Vorbereitungsmaßnahmen  
  
###  <a name="Restrictions"></a> Einschränkungen  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] enthält Richtlinien, die verwendet werden können, um eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]zu überwachen. Diese Richtlinien sind standardmäßig nicht in [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]installiert, aber sie können aus ihrem Standardspeicherort C:\Programme\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033 importiert werden.  
  
###  <a name="Security"></a> Sicherheit  
  
####  <a name="Permissions"></a> Berechtigungen  
 Erfordert die Mitgliedschaft in der PolicyAdministratorRole-Rolle in der msdb-Datenbank.  
  
##  <a name="SSMSProcedure"></a> Verwenden von SQL Server Management Studio  
  
#### <a name="to-import-a-policy-instance"></a>So importieren Sie eine Richtlinieninstanz  
  
1.  Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um den Server zu erweitern, in dem sich die neu importierte Richtlinieninstanz befinden wird.  
  
2.  Klicken Sie auf das Pluszeichen, um den Ordner **Verwaltung** zu erweitern.  
  
3.  Klicken Sie auf das Pluszeichen, um **Richtlinienverwaltung**zu erweitern.  
  
4.  Klicken Sie mit der rechten Maustaste auf den Ordner **Richtlinien** , und wählen Sie **Richtlinie importieren**aus.  
  
5.  Geben Sie im Dialogfeld **Importieren** den Pfad und den Namen der Datei ein, oder klicken Sie auf die Schaltfläche zum Durchsuchen (**…**), um die XML-Datei zu suchen, die die Richtlinie enthält, und wählen Sie dann die Datei aus. Weitere Informationen zu den Optionen im Dialogfeld **Importieren** finden Sie unter [Import Policies Dialog Box](import-policies-dialog-box.md).  
  
6.  Wenn Sie fertig sind, klicken Sie auf **OK**.  
  
  
