---
title: Sichern des Abonnenten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/26/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [SQL Server replication], security
- Subscribers [SQL Server replication], security
- security [SQL Server replication], Subscribers
ms.assetid: c8f0d62a-8b5d-4a21-9aec-223da52bb708
caps.latest.revision: 35
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 5cf7b8219c8a3810ce5222ef7ac2fca040dd1a08
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37258326"
---
# <a name="secure-the-subscriber"></a>Sichern des Abonnenten
  Merge-Agents und Verteilungs-Agents stellen Verbindungen mit dem Abonnenten her. Diese Verbindungen können im Kontext einer [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Anmeldung oder einer Windows-Anmeldung erfolgen. Es ist wichtig, eine geeignete Anmeldung für diese Agents bereitzustellen, ohne dass dabei der Grundsatz verletzt wird, dass nur so viele Rechte erteilt werden sollten, wie unbedingt erforderlich sind. Außerdem muss der Aufbewahrungsort für die Kennwörter geschützt sein. Informationen zu den für die einzelnen Agents erforderlichen Berechtigungen finden Sie unter [Replication Agent Security Model](replication-agent-security-model.md).  
  
## <a name="distribution-agent"></a>Verteilungs-Agent  
 Es gibt entweder einen Verteilungs-Agent pro Abonnement (unabhängiger Agent – dies ist der Standard bei Veröffentlichungen, die mit dem Assistenten für neue Veröffentlichung erstellt werden) oder einen Verteilungs-Agent pro Veröffentlichungsdatenbank/Abonnementdatenbank-Paar (ein freigegebener Agent). T  
  
 Hinweise zum Angeben von Verbindungsinformationen für Pushabonnements finden Sie unter [Erstellen eines Pushabonnements](../create-a-push-subscription.md).  
  
 Hinweise zum Angeben von Verbindungsinformationen für Pullabonnements finden Sie unter [Erstellen eines Pullabonnements](../create-a-pull-subscription.md).  
  
## <a name="merge-agent"></a>Merge-Agent  
 Jedes Mergeabonnement besitzt einen Merge-Agent, der eine Verbindung mit dem Verleger und mit dem Abonnenten herstellt und beide aktualisiert.  
  
 Hinweise zum Angeben von Verbindungsinformationen für Pushabonnements finden Sie unter [Erstellen eines Pushabonnements](../create-a-push-subscription.md).  
  
 Hinweise zum Angeben von Verbindungsinformationen für Pullabonnements finden Sie unter [Erstellen eines Pullabonnements](../create-a-pull-subscription.md).  
  
## <a name="immediate-updating-subscriptions"></a>Abonnements mit sofortigem Update  
 Beim Konfigurieren eines Abonnements mit sofortigem Update müssen Sie ein Konto auf dem Abonnenten angeben, über das die Verbindungen zum Verleger hergestellt werden. Die Verbindungen werden durch die Trigger verwendet, die auf dem Abonnenten ausgelöst werden und die Änderungen zum Verleger weitergeben. Für den Typ der Verbindung gibt es drei Optionen:  
  
-   Verbindungsserver, der von der Replikation erstellt wird. Die Verbindung erfolgt mit den Anmeldeinformationen, die Sie zum Zeitpunkt des Konfigurierens angegeben haben.  
  
-   Ein durch die Replikation erstellter Verbindungsserver. Die Verbindung wird mit den Anmeldeinformationen des Benutzers hergestellt, der die Änderung auf dem Abonnenten vornimmt.  
  
-   Ein vordefinierter Verbindungsserver oder Remoteserver.  
  
> [!IMPORTANT]  
>  Verwenden Sie die gespeicherte Prozedur [sp_link_publication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-link-publication-transact-sql), um Verbindungsinformationen anzugeben. Sie können auch die Seite **Anmeldename für aktualisierbare Abonnements** des Assistenten für neue Abonnements mit **sp_link_publication**verwenden. Unter bestimmten Umständen kann diese gespeicherte Prozedur fehlerhaft sein, wenn der Abonnent [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] Service Pack 1 (SP1) oder höher ausführt, und wenn der Verleger auf einer früheren Version ausgeführt wird. Wenn die gespeicherte Prozedur in diesem Szenario fehlerhaft ist, dann aktualisieren Sie den Verleger auf [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] SP1 oder höher.  
  
 Weitere Informationen finden Sie unter [Erstellen von aktualisierbaren Abonnements für eine Transaktionsveröffentlichung](../create-updatable-subscription-transactional-publication-transact-sql.md) und [Anzeigen und Ändern von Replikationssicherheitseinstellungen](view-and-modify-replication-security-settings.md).  
  
> [!IMPORTANT]  
>  Dem für die Verbindung angegebenen Konto sollten nur die Berechtigung zum Einfügen, Aktualisieren und Löschen der Daten in den durch die Replikation in der Veröffentlichungsdatenbank erstellten Sichten erteilt werden; darüber hinaus sollte das Konto über keine weiteren Berechtigungen verfügen. Erteilen Sie dem von Ihnen auf den einzelnen Abonnenten konfigurierten Konto Berechtigungen für Sichten in der Veröffentlichungsdatenbank, deren Namen das Format **syncobj_***\<Hexadezimalzahl>* aufweisen.  
  
## <a name="queued-updating-subscriptions"></a>Abonnements mit verzögertem Update über eine Warteschlange  
 Beim Konfigurieren von Abonnements mit verzögertem Update über eine Warteschlange sind hinsichtlich der Sicherheit die folgenden beiden Punkte zu berücksichtigen:  
  
-   Es gibt für jeden Verteiler nur einen Warteschlangenlese-Agent. Es empfiehlt sich daher, dass Sie für jeden Verteiler maximal eine Veröffentlichung konfigurieren, die für Abonnements mit verzögertem Update über eine Warteschlange aktiviert ist.  
  
-   Der Warteschlangenlese-Agent stellt Verbindungen zum Verteiler, zum Verleger und zu allen Abonnenten her:  
  
    -   Das Konto, über das der Agent ausgeführt wird und das die Verbindungen zum Verteiler herstellt, wird beim Erstellen des Agents angegeben (wenn Sie den Assistenten für neue Veröffentlichung verwenden, wird der Agent beim Erstellen einer Veröffentlichung erstellt, die für Updateabonnements aktiviert ist).  
  
    -   Das Konto, über das der Agent Verbindungen zum Verleger herstellt, wird beim Konfigurieren der Verteilung für einen Verleger angegeben. Geben Sie ein [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Konto oder das Windows-Konto an, unter dem der Agent ausgeführt wird.  
  
    -   Das Konto, über das der Agent Verbindungen zum Abonnenten herstellt, wird beim Erstellen des Abonnements angegeben.  
  
    > [!IMPORTANT]  
    >  Verwenden Sie für Verbindungen zu Abonnenten die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Authentifizierung, und geben Sie für die Verbindungen mit den einzelnen Abonnenten jeweils ein eigenes Konto an. Bei Verwendung eines Pullabonnements wird von der Replikation in jedem Fall die Verwendung der Windows-Authentifizierung durchgesetzt, da die Replikation bei dieser Art von Abonnements nicht auf die Metadaten auf dem Abonnenten zugreifen kann, die für die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Authentifizierung erforderlich sind. Ändern Sie in diesem Fall nach dem Konfigurieren des Abonnements die Verbindung so, dass die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Authentifizierung verwendet wird.  
  
     Weitere Informationen finden Sie unter Vorgehensweise: Erstellen eines Aktualisierungsabonnements für eine Transaktionsveröffentlichung (SQL Server Management Studio) und [Anzeigen und Ändern von Replikationssicherheitseinstellungen](view-and-modify-replication-security-settings.md).  
  
## <a name="see-also"></a>Siehe auch  
 
  [Aktivieren von verschlüsselten Verbindungen zur Datenbank-Engine &amp;#40;SQL Server-Konfigurations-Manager&amp;#41;](../../../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md)   
 [Replication Security Best Practices](replication-security-best-practices.md)   
 [Sicherheit und Schutz &#40;Replikation&#41;](security-and-protection-replication.md)  
  
  
