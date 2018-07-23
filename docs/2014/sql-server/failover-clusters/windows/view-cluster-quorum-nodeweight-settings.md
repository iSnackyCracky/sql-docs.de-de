---
title: Anzeigen von Cluster-Quorum-NodeWeight-Einstellungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: high-availability
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], WSFC clusters
- quorum [SQL Server], AlwaysOn and WSFC quorum
ms.assetid: b845e73a-bb01-4de2-aac2-8ac12abebc95
caps.latest.revision: 16
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 174405ce5c25edec5344b11728a2bb29e3c88e64
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37325590"
---
# <a name="view-cluster-quorum-nodeweight-settings"></a>Anzeigen von Cluster-Quorum-NodeWeight-Einstellungen
  In diesem Thema wird beschrieben, wie NodeWeight-Einstellungen für jeden Elementknoten in einem Windows Server-Failoverclustering-Cluster angezeigt werden. NodeWeight-Einstellungen werden während der Quorumabstimmung verwendet, um Notfallwiederherstellungs- und Multisubnetzszenarien für [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] - und [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Failoverclusterinstanzen zu unterstützen.  
  
-   **Vorbereitungen:**  [Erforderliche Komponenten](#Prerequisites), [Sicherheit](#Security)  
  
-   **Anzeigen von Quorum-NodeWeight-Einstellungen mit:** [Verwenden von Transact-SQL](#TsqlProcedure), [Verwenden von PowerShell](#PowerShellProcedure), [Verwenden von Cluster.exe](#CommandPromptProcedure)  
  
##  <a name="BeforeYouBegin"></a> Vorbereitungen  
  
###  <a name="Prerequisites"></a> Erforderliche Komponenten  
 Diese Funktion wird nur in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] oder höheren Versionen unterstützt.  
  
> [!IMPORTANT]  
>  Um NodeWeight-Einstellungen zu verwenden, muss der folgende Hotfix im WSFC-Cluster für alle Server übernommen werden:  
>   
>  [KB2494036](http://support.microsoft.com/kb/2494036): Ein Hotfix ist verfügbar, mit dem sich ein Clusterknoten konfigurieren lässt, der keine Quorumabstimmung in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] und in [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)]  
  
> [!TIP]  
>  Ist dieser Hotfix nicht installiert, geben die Beispiele in diesem Thema leere Werte oder NULL-Werte für NodeWeight zurück.  
  
###  <a name="Security"></a> Sicherheit  
 Der Benutzer muss einem Domänenkonto entsprechen, das Mitglied der lokalen Administratorgruppe an jedem Knoten des WSFC-Clusters ist.  
  
##  <a name="TsqlProcedure"></a> Verwenden von Transact-SQL  
  
##### <a name="to-view-nodeweight-settings"></a>So zeigen Sie NodeWeight-Einstellungen an  
  
1.  Stellen Sie im Cluster eine Verbindung mit einer beliebigen [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Instanz her.  
  
2.  Fragen Sie die Sicht "[sys].[dm_hadr_cluster_members]" ab.  
  
### <a name="example-transact-sql"></a>Beispiel (Transact-SQL)  
 Im folgenden Beispiel wird eine Systemsicht zur Rückgabe von Werten für alle Knoten im betreffenden Cluster der Instanz abgefragt.  
  
```tsql  
SELECT  member_name, member_state_desc, number_of_quorum_votes  
 FROM   sys.dm_hadr_cluster_members;  
```  
  
##  <a name="PowerShellProcedure"></a> Verwenden von PowerShell  
  
##### <a name="to-view-nodeweight-settings"></a>So zeigen Sie NodeWeight-Einstellungen an  
  
1.  Starten Sie eine erhöhte Windows PowerShell mittels **Als Administrator ausführen**.  
  
2.  Importieren Sie das `FailoverClusters` -Modul, um Cluster-Cmdlets zu aktivieren.  
  
3.  Verwenden Sie das `Get-ClusterNode` -Objekt, um eine Auflistung von Clusterknotenobjekten zurückzugeben.  
  
4.  Geben Sie die Clusterknoteneigenschaften in einem lesbaren Format aus.  
  
### <a name="example-powershell"></a>Beispiel (PowerShell)  
 Im folgenden Beispiel wurden einige der Knoteneigenschaften für den Cluster "Cluster001" ausgegeben.  
  
```powershell  
Import-Module FailoverClusters  
  
$cluster = "Cluster001"  
$nodes = Get-ClusterNode -Cluster $cluster  
  
$nodes | Format-Table -property NodeName, State, NodeWeight  
```  
  
##  <a name="CommandPromptProcedure"></a> Verwenden von Cluster.exe  
  
> [!NOTE]  
>  Das Hilfsprogramm von cluster.exe ist in der [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)] -Version veraltet.  Verwenden Sie PowerShell mit Failoverclustering für künftige Entwicklungen.  Das Hilfsprogramm von cluster.exe wird in der nächsten Version von Windows Server entfernt. Weitere Informationen finden Sie unter [Zuordnen von Cluster.exe-Befehlen zu Windows PowerShell-Cmdlets für Failovercluster](http://technet.microsoft.com/library/ee619744\(WS.10\).aspx).  
  
##### <a name="to-view-nodeweight-settings"></a>So zeigen Sie NodeWeight-Einstellungen an  
  
1.  Starten Sie mit **Als Administrator ausführen**eine Eingabeaufforderung mit erweiterten Berechtigungen.  
  
2.  Verwenden Sie **cluster.exe** , um Knotenstatus- und NodeWeight-Werte zurückzugeben.  
  
### <a name="example-clusterexe"></a>Beispiel (Cluster.exe)  
 Im folgenden Beispiel werden einige der Knoteneigenschaften für den Cluster "Cluster001" ausgegeben.  
  
```ms-dos  
cluster.exe Cluster001 node /status /properties  
```  
  
## <a name="see-also"></a>Siehe auch  
 [WSFC-Quorummodi und Abstimmungskonfiguration &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md)   
 [Konfigurieren von Cluster-Quorum-NodeWeight-Einstellungen](configure-cluster-quorum-nodeweight-settings.md)   
 [sys.dm_hadr_cluster_members &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-members-transact-sql)   
 [Failovercluster-Cmdlets in Windows PowerShell, aufgelistet nach Taskfokus](http://technet.microsoft.com/library/ee619761\(WS.10\).aspx)  
  
  