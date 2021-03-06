---
title: Aktualisieren des Protokollversands auf SQLServer 2014 (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: high-availability
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], upgrading
ms.assetid: b1289cc3-f5be-40bb-8801-0e3eed40336e
caps.latest.revision: 57
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 96179ecc9f49bde6b27e2d2bf8dab86835054f0b
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37310400"
---
# <a name="upgrade-log-shipping-to-sql-server-2014-transact-sql"></a>Aktualisieren des Protokollversands auf SQL Server 2014 (Transact-SQL)
  Beim Aktualisieren von [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] oder [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] ist es möglich, die Protokollversandkonfigurationen beizubehalten. In diesem Thema werden alternative Szenarien und bewährte Methoden zum Aktualisieren einer Protokollversandkonfiguration beschrieben.  
  
> [!NOTE]  
>  Die[Sicherungskomprimierung](../../relational-databases/backup-restore/backup-compression-sql-server.md) wurde in [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)]eingeführt. In einer aktualisierten Protokollversandkonfiguration wird durch die Serverkonfigurationsoption **Komprimierungsstandard für Sicherung** bestimmt, ob die Transaktionsprotokoll-Sicherungsdateien mithilfe der Sicherungskomprimierung komprimiert werden. Das Verhalten für die Sicherungskomprimierung der Protokollsicherung kann für jede Protokollversandkonfiguration festgelegt werden. Weitere Informationen finden Sie unter [Konfigurieren des Protokollversands &#40;SQL Server&#41;](configure-log-shipping-sql-server.md)eingeführt.  
  
  
##  <a name="ProtectData"></a> Datensicherung vor dem Upgrade  
 Als bewährte Methode wird empfohlen, dass Sie die Daten vor einem Protokollversandupgrade schützen.  
  
 **So schützen Sie die Daten**  
  
1.  Führen Sie für jede primäre Datenbank eine vollständige Datenbanksicherung aus.  
  
     Weitere Informationen finden Sie unter [Erstellen einer vollständigen Datenbanksicherung &#40;SQL Server&#41;](../../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md).  
  
2.  Führen Sie den [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) -Befehl für jede primäre Datenbank aus.  
  
##  <a name="UpgradeMonitor"></a> Aktualisieren der Überwachungsserverinstanz  
 Die Überwachungsserverinstanz, sofern vorhanden, kann jederzeit aktualisiert werden.  
  
 Während der Aktualisierung des Überwachungsservers ist die Protokollversandkonfiguration weiterhin in Betrieb, ihr Status wird allerdings nicht in den Tabellen auf dem Überwachungsserver aufgezeichnet. Warnungen, die ggf. konfiguriert wurden, werden während der Aktualisierung des Überwachungsservers nicht ausgelöst. Nach der Aktualisierung können Sie die Überwachungstabellen aktualisieren, indem Sie die gespeicherte Systemprozedur [sp_refresh_log_shipping_monitor](/sql/relational-databases/system-stored-procedures/sp-refresh-log-shipping-monitor-transact-sql) ausführen.  
  
##  <a name="UpgradeSingleSecondary"></a> Aktualisieren von Protokollversandkonfigurationen mit einem einzelnen sekundären Server  
 Für den in diesem Abschnitt beschriebenen Upgradevorgang wird eine Konfiguration vorausgesetzt, die einen primären Server und nur einen sekundären Server umfasst. Diese Konfiguration wird in der folgenden Abbildung dargestellt, die eine primäre Serverinstanz A und eine einzelne sekundäre Serverinstanz B zeigt.  
  
 ![Ein sekundärer Server und kein Überwachungsserver](../media/ls-2-wayconfig-nomonitor.gif "einen sekundären Server und kein Überwachungsserver")  
  
 Informationen zur Aktualisierung mehrerer sekundärer Server finden Sie unter [Aktualisieren von mehreren sekundären Serverinstanzen](#MultipleSecondaries)weiter hinten in diesem Thema.  
 
  
###  <a name="UpgradeSecondary"></a> Aktualisieren der sekundären Serverinstanz  
 Der Upgradevorgang erfordert das Upgrade der sekundären Serverinstanzen einer [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] oder höher-Protokollversandkonfiguration auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] vor dem Upgrade der primären Serverinstanz. Aktualisieren Sie immer zuerst die sekundäre Serverinstanz. Wenn der primäre Server vor einem sekundären Server aktualisiert wurden, würde Protokollversand fehl, da eine Sicherung auf einer neueren Version von erstellt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] kann nicht wiederhergestellt werden, auf eine ältere Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 Der Protokollversand wird während des Upgradevorgangs weiter ausgeführt, weil die aktualisierten sekundären Server die Protokollsicherungen vom primären [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] -Server (oder höher) weiterhin wiederherstellen. Der Upgradevorgang für die sekundären Serverinstanzen hängt teilweise davon ab, ob die Protokollversandkonfiguration mehrere sekundäre Server umfasst Weitere Informationen finden Sie im Abschnitt [Aktualisieren von mehreren sekundären Serverinstanzen](#MultipleSecondaries)weiter hinten in diesem Thema.  
  
 Während des Upgrades der sekundären Serverinstanz werden die Aufträge zum Kopieren und Wiederherstellen des Protokollversands nicht ausgeführt, daher sammeln sich nicht wiederhergestellte Sicherungen von Transaktionsprotokollen an. Die Menge dieser Ansammlung hängt von der Frequenz der geplanten Sicherung auf dem primären Server ab. Wenn ein getrennter Überwachungsserver konfiguriert wurde, werden möglicherweise Warnungen ausgegeben, die anzeigen, dass über einen längeren Zeitraum als das konfigurierte Intervall hinweg keine Wiederherstellungsvorgänge ausgeführt wurden.  
  
 Sobald der sekundäre Server aktualisiert wurde, werden die Protokollversandaufträge der Agents zum Kopieren und Wiederherstellen von Protokollsicherungen von der primären Serverinstanz, Server A, wieder aufgenommen und fortgesetzt. Wie lange der sekundäre Server für die Aktualisierung der sekundären Datenbank benötigt, hängt davon ab, wie lange das Upgrade des sekundären Servers dauert und wie häufig die Sicherungen auf dem primären Server ausgeführt werden.  
  
> [!NOTE]  
>  Während der serveraktualisierung wird die sekundäre Datenbank nicht auf aktualisiert eine [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Datenbank. Sie wird nur aktualisiert, wenn sie online geschaltet wird.  
  
> [!IMPORTANT]  
>  Die RESTORE WITH STANDBY-Option wird für Datenbanken, die eine Aktualisierung erfordern, nicht unterstützt. Wenn eine aktualisierte sekundäre Datenbank mithilfe von RESTORE WITH STANDBY konfiguriert wurde, können Transaktionsprotokolle nach einer Aktualisierung nicht wiederhergestellt werden. Um den Protokollversand auf dieser sekundären Datenbank fortzusetzen, müssen Sie ihn auf diesem Standbyserver erneut einrichten. Weitere Informationen zur STANDBY-Option finden Sie unter [RESTORE-Argumente &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql).  
  
###  <a name="UpgradePrimary"></a> Aktualisieren der primären Serverinstanz  
 Bei der Planung eines Upgrades ist der Zeitraum, während dessen die Datenbank nicht verfügbar sein wird, ein maßgeblicher Aspekt. Im einfachsten Aktualisierungsszenario ist die Datenbank nicht verfügbar, während der primäre Server aktualisiert wird (Szenario 1, unten).  
  
 Ein etwas komplizierteres Upgradevorgang wird dadurch allerdings können Sie die datenbankverfügbarkeit per Failover Maximieren der [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] oder höher-Primärserver zum eine [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] sekundären Server, bevor Sie den ursprünglichen primären Server aktualisieren (Szenario 2 weiter unten). Es sind zwei Varianten des Failoverszenarios denkbar. Sie können zurück zum ursprünglichen primären Server wechseln und die ursprüngliche Protokollversandkonfiguration beibehalten. Alternativ können Sie die ursprüngliche Protokollversandkonfiguration entfernen, bevor Sie den ursprünglichen primären Server aktualisieren, und später unter Verwendung des neuen primären Servers eine neue Konfiguration erstellen. In diesem Abschnitt werden diese beiden Szenarien beschrieben.  
  
> [!IMPORTANT]  
>  Aktualisieren Sie unbedingt die sekundäre Serverinstanz vor der primären Serverinstanz. Weitere Informationen finden Sie im Abschnitt [Aktualisieren der sekundären Serverinstanz](#UpgradeSecondary)weiter oben in diesem Thema.  
  
  
####  <a name="Scenario1"></a> Szenario 1: Upgrade primären Serverinstanz ohne Failover  
 Dies ist das einfachere Szenario, aber es verursacht eine längere Ausfallzeit als die Aktualisierung mit Failover. Die primäre Serverinstanz wird einfach aktualisiert, und die Datenbank ist während dieses Aktualisierungsvorgangs nicht verfügbar.  
  
 Sobald der Server aktualisiert wurde, wird die Datenbank automatisch online geschaltet. Daraufhin wird sie automatisch aktualisiert. Nachdem die Datenbank aktualisiert wurde, werden die Protokollversandaufträge fortgesetzt.  
  
#### <a name="scenario-2-upgrade-primary-server-instance-with-failover"></a>Szenario 2: Aktualisieren der primären Serverinstanz mit Failover  
 In diesem Szenario wird die Verfügbarkeit maximiert und die Ausfallzeit minimiert. Es wird ein kontrolliertes Failover auf die sekundäre Serverinstanz durchgeführt, wodurch die Datenbank verfügbar bleibt, während die ursprüngliche primäre Serverinstanz aktualisiert wird. Die Ausfallzeit wird auf den relativen kurzen Zeitraum beschränkt, der zur Durchführung des Failovers erforderlich ist, statt auf den Zeitraum, der zur Aktualisierung der primären Serverinstanz benötigt wird.  
  
 Das Aktualisieren der primären Serverinstanz mit Failover umfasst drei allgemeine Schritte: Ausführen eines kontrollierten Failovers auf den sekundären Server, Aktualisieren der ursprünglichen primären Serverinstanz auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] und Einrichten des Protokollversands auf einer primären Serverinstanz von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]. In diesem Abschnitt werden diese Schritte beschrieben.  
  
> [!IMPORTANT]  
>  Wenn Sie die sekundäre Serverinstanz als neue primäre Serverinstanz nutzen möchten, müssen Sie die Protokollversandkonfiguration entfernen. Der Protokollversand muss vom neuen primären auf den neuen sekundären Server konfiguriert werden, nachdem die ursprüngliche primäre Serverinstanz aktualisiert wurde. Weitere Informationen finden Sie unter [Entfernen des Protokollversands &#40;SQL Server&#41;](remove-log-shipping-sql-server.md).  
  
  
#####  <a name="Procedure1"></a> Schritt 1: Ausführen eines kontrollierten Failovers auf den sekundären Server  
 Kontrollierter Failover auf den sekundären Server:  
  
1.  Führen Sie manuell eine [protokollfragmentsicherung](../../relational-databases/backup-restore/tail-log-backups-sql-server.md) des Transaktionsprotokolls in der primären Datenbank, die Angabe von WITH NORECOVERY. Mit dieser Protokollsicherung werden alle bislang noch nicht gesicherten Protokolldatensätze erfasst und die Datenbank offline geschaltet. Beachten Sie Folgendes: Während die Datenbank offline ist, kann der Protokollversandsicherungsauftrag nicht ausgeführt werden.  
  
     Im folgenden Beispiel wird das Ende des Protokolls für die `AdventureWorks` -Datenbank auf dem primären Server gesichert. Die Sicherungsdatei erhält den Namen `Failover_AW_20080315.trn`:  
  
    ```  
    BACKUP LOG AdventureWorks   
      TO DISK = N'\\FileServer\LogShipping\AdventureWorks\Failover_AW_20080315.trn'   
       WITH NORECOVERY;  
    GO  
    ```  
  
     Es wird empfohlen, dass Sie eine eigene Dateibenennungskonvention verwenden, um manuell erstellte Sicherungsdateien von den Sicherungsdateien, die vom Protokollversandsicherungsauftrag erstellt werden, unterscheiden zu können.  
  
2.  Auf dem sekundären Server:  
  
    1.  Stellen Sie sicher, dass alle von Protokollversandsicherungsaufträgen durchgeführten Sicherungen automatisch übernommen wurden. Um zu überprüfen, welche Sicherungsaufträge übernommen wurden, verwenden die [Sp_help_log_shipping_monitor](/sql/relational-databases/system-stored-procedures/sp-help-log-shipping-monitor-transact-sql) System gespeicherte Prozedur aus, auf dem Überwachungsserver oder auf dem primären und sekundären Servern. Die gleiche Datei sollte in den Spalten **last_backup_file**, **last_copied_file**und **last_restored_file** aufgeführt sein. Wenn eine der Sicherungsdateien nicht kopiert und wiederhergestellt wurde, starten Sie die Aufträge der Agents zum Kopieren und Wiederherstellens für die Protokollversandkonfiguration manuell.  
  
         Informationen zum Starten eines Auftrags finden Sie unter [Starten eines Auftrags](../../ssms/agent/start-a-job.md).  
  
    2.  Kopieren Sie die letzte Protokollsicherungsdatei, die Sie in Schritt 1 erstellt haben, von der Dateifreigabe an den Speicherort, der vom Protokollversand auf dem sekundären Server verwendet wird.  
  
    3.  Stellen Sie die letzte Protokollsicherung wieder her, und geben Sie hierbei WITH RECOVERY an, um die Datenbank online zu schalten. Die Datenbank wird im Rahmen des Onlineschaltens auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] aktualisiert.  
  
         Im folgenden Beispiel wird das Ende der Protokollsicherung für die `AdventureWorks` -Datenbank in der sekundären Datenbank wiederhergestellt. Im Beispiel wird die WITH RECOVERY-Option verwendet, mit der die Datenbank online geschaltet wird:  
  
        ```  
        RESTORE LOG AdventureWorks   
          FROM DISK = N'c:\logshipping\Failover_AW_20080315.trn'   
           WITH RECOVERY;  
        GO  
        ```  
  
        > [!NOTE]  
        >  Bei einer Konfiguration, die mehr als einen sekundären Server enthält, sind weitere Aspekte zu berücksichtigen. Weitere Informationen finden Sie im Abschnitt [Aktualisieren von mehreren sekundären Serverinstanzen](#MultipleSecondaries)weiter hinten in diesem Thema.  
  
    4.  Führen Sie einen Failover für die Datenbank aus, indem Sie Clients vom ursprünglichen primären Server (Server A) auf den online geschalteten sekundären Server (Server B) durchführen.  
  
    5.  Sorgen Sie dafür, dass das Transaktionsprotokoll der zweiten Datenbank nicht gefüllt wird, während die Datenbank online ist. Um das Füllen des Transaktionsprotokolls zu verhindern, müssen Sie es sichern. Wenn Sie es sichern, wird die Verwendung eines gemeinsam genutzten Speicherorts, einer *Sicherungsfreigabe*, empfohlen, damit die Sicherungen zum Wiederherstellen auf der anderen Serverinstanz verfügbar sind.  
  
#####  <a name="Procedure2 "></a> Vorgehensweise 2: Aktualisieren der ursprünglichen primären Serverinstanz auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]  
 Auch nachdem Sie die ursprüngliche primäre Serverinstanz auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] aktualisiert haben, ist die Datenbank noch offline und hat dieses Format.  
  
#####  <a name="Procedure3"></a> Schritt 3: Einrichten des Protokollversands auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]  
 Der restliche Upgradevorgang hängt davon ab, ob der Protokollversand immer noch konfiguriert ist. Hier gilt:  
  
-   Wenn Sie die [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]-Protokollversandkonfiguration (oder höher) beibehalten haben, wechseln Sie zurück zur ursprünglichen primären Serverinstanz. Weitere Informationen hierzu finden Sie unter [So wechseln Sie zurück zur ursprünglichen primären Serverinstanz](#SwitchToOrigPrimary)weiter hinten in diesem Thema.  
  
-   Wenn Sie die Protokollversandkonfiguration vor dem Failover entfernt haben, erstellen Sie eine neue Protokollversandkonfiguration, in der die ursprüngliche sekundäre Serverinstanz die neue primäre Serverinstanz bildet. Weitere Informationen hierzu finden Sie unter [So behalten Sie die ursprüngliche sekundäre Serverinstanz als neue primäre Serverinstanz bei](#KeepOldSecondaryAsNewPrimary)weiter hinten in diesem Thema.  
  
######  <a name="SwitchToOrigPrimary"></a> So wechseln Sie zurück zum ursprünglichen primären Serverinstanz  
  
1.  Erstellen Sie auf dem zwischenzeitlichen primären Server (Server B) eine Sicherung des Endes der Protokolldatei unter Angabe von WITH NORECOVERY, um eine Sicherung des Protokollfragments zu erstellen und die Datenbank offline zu schalten. Die Sicherung des Protokollfragments hat den Namen `Switchback_AW_20080315.trn`. Beispiel:  
  
    ```  
    BACKUP LOG AdventureWorks   
      TO DISK = N'\\FileServer\LogShipping\AdventureWorks\Switchback_AW_20080315.trn'   
       WITH NORECOVERY;  
    GO  
    ```  
  
2.  Wenn für die zwischenzeitliche primäre Datenbank Transaktionsprotokollsicherungen durchgeführt wurden, die sich von der in Schritt 1 erstellten Sicherung des Protokollfragments unterscheiden, stellen Sie diese Sicherungen unter Angabe von WITH NORECOVERY in der offline geschalteten Datenbank auf dem ursprünglichen primären Server (Server A) wieder her. Die Datenbank wird aktualisiert, um [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] formatieren, wenn die erste protokollsicherung wiederhergestellt wird.  
  
3.  Stellen Sie die Sicherung des Protokollfragments `Switchback_AW_20080315.trn`für die ursprüngliche primäre Datenbank (auf Server A) unter Angabe von WITH RECOVERY wieder her, um die Datenbank online zu schalten.  
  
4.  Führen Sie einen Failover zur ursprünglichen primären Datenbank (auf Server A) aus, indem Sie Clients vom ursprünglichen primären Server zum online geschalteten sekundären Server umleiten.  
  
 Nachdem die Datenbank online geschaltet wurde, wird die ursprüngliche Protokollversandkonfiguration wieder aufgenommen.  
  
######  <a name="KeepOldSecondaryAsNewPrimary"></a> Die ursprüngliche sekundäre Serverinstanz als neue primäre Serverinstanz beibehalten  
 Richten Sie eine neue Protokollversandkonfiguration ein, in der die alte sekundäre Serverinstanz B als primärer Server und die alte primäre Serverinstanz A als neuer sekundärer Server fungiert. Beispiel:  
  
> [!IMPORTANT]  
>  Die alte Protokollversandkonfiguration sollte zu Beginn dieses Schritts vom ursprünglichen primären Server entfernt worden sein, bevor die manuelle Transaktionsprotokollsicherung durchgeführt wurde, mit der die Datenbank offline geschaltet wurde.  
  
1.  Um die Ausführung einer vollständigen Sicherung und Wiederherstellung der Datenbank auf dem neuen sekundären Server (Server A) zu vermeiden, wenden Sie die Protokollsicherungen der neuen primären Datenbank auf die neue sekundäre Datenbank an. In der Beispielkonfiguration werden hierzu die auf Server B erstellten Protokollsicherungen in der Datenbank auf Server A wiederhergestellt.  
  
2.  Sichern Sie das Protokoll der neuen primären Datenbank (auf Server B).  
  
3.  Stellen Sie die Protokollsicherungen auf der neuen sekundären Serverinstanz (Server A) unter Angabe von WITH NORECOVERY wieder her. Der erste Restore-Vorgang aktualisiert die Datenbank [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
4.  Konfigurieren Sie den Protokollversand so, dass der frühere sekundäre Server (Server B) die primäre Serverinstanz bildet.  
  
    > [!IMPORTANT]  
    >  Bei Verwendung von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], anzugeben, dass die sekundäre Datenbank bereits initialisiert ist.  
  
     Weitere Informationen finden Sie unter [Konfigurieren des Protokollversands &#40;SQL Server&#41;](configure-log-shipping-sql-server.md)eingeführt.  
  
5.  Führen Sie einen Failover für die Datenbank aus, indem Sie Clients vom ursprünglichen primären Server (Server A) auf den online geschalteten sekundären Server (Server B) durchführen.  
  
    > [!IMPORTANT]  
    >  Wenn Sie einen Failover auf eine neue primäre Datenbank durchführen, sollten Sie sicherstellen, dass die Metadaten mit den Metadaten der ursprünglichen primären Datenbank übereinstimmen. Weitere Informationen finden Sie unter [Verwalten von Metadaten beim Bereitstellen einer Datenbank auf einer anderen Serverinstanz &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).  
  
##  <a name="MultipleSecondaries"></a> Aktualisieren von mehreren sekundären Serverinstanzen  
 Diese Konfiguration wird in der folgenden Abbildung dargestellt, die eine primäre Serverinstanz A und zwei einzelne sekundäre Serverinstanzen B und C zeigt.  
  
 ![Zwei sekundäre Server und kein Überwachungsserver](../media/ls-3-wayconfig-nomonitor.gif "zwei sekundäre Server und kein Überwachungsserver")  
  
 In diesem Abschnitt wird erläutert, wie Sie eine Aktualisierung mit einem Failover durchführen können und dann zum ursprünglichen primären Server zurückwechseln können. Wenn die primäre Serverinstanz mit Failover aktualisiert wird, ist der Upgradevorgang komplizierter, wenn mehrere sekundäre Serverinstanzen vorhanden sind. Im folgenden Verfahren wird nach der Aktualisierung aller sekundären Server ein Failover für den primären Server auf eine der aktualisierten sekundären Datenbanken durchgeführt. Der ursprüngliche primäre Server wird aktualisiert, und für den Protokollversand wird ein Failover zurück zu diesem Server ausgeführt.  
  
> [!IMPORTANT]  
>  Aktualisieren Sie stets sämtliche sekundäre Serverinstanzen vor der primären Serverinstanz.  
  
 **Um ein upgrade Sichern mithilfe eines Failovers und der anschließende Wechsel zum ursprünglichen primären server**  
  
1.  Aktualisieren Sie alle sekundären Serverinstanzen (Server B und C).  
  
2.  Erstellen Sie eine Sicherung des Endes der Protokolldatei (auf Server A) unter Angabe von WITH NORECOVERY, um eine Sicherung des Protokollfragments der primären Datenbank zu erhalten und die Datenbank offline zu schalten.  
  
3.  Schalten Sie auf dem sekundären Server, auf den das Failover durchgeführt werden soll (Server B), die sekundäre Datenbank online, indem Sie die Protokollsicherung unter Angabe von WITH RECOVERY wiederherstellen.  
  
4.  Lassen Sie auf dem anderen sekundären Server (Server C) die sekundäre Datenbank offline, indem Sie die Protokollsicherung unter Angabe von WITH NORECOVERY wiederherstellen.  
  
    > [!NOTE]  
    >  Die Aufträge zum Kopieren und Wiederherstellen des Protokollversands werden auf den sekundären Servern ausgeführt, aber die Aufträge bewirken nichts, weil die neuen Protokollsicherungsdateien nicht in der Sicherungsfreigabe abgelegt werden.  
  
5.  Führen Sie einen Failover für die Datenbank aus, indem Sie Clients vom ursprünglichen primären Server (Server A) auf den online geschalteten sekundären Server (Server B) durchführen. Die online geschaltete Datenbank fungiert zwischenzeitlich als primärer Server, wodurch die Datenbank verfügbar bleibt, während die ursprüngliche primäre Serverinstanz aktualisiert wird.  
  
6.  Aktualisieren Sie den ursprünglichen primären Server (Server A).  
  
7.  Führen Sie für die Datenbank, auf die das Failover durchgeführt wurde – die zwischenzeitliche primäre Datenbank (auf Server B) – eine manuelle Sicherung des Transaktionsprotokolls unter Angabe von WITH NORECOVERY durch. Dadurch wird die Datenbank offline geschaltet.  
  
8.  Stellen Sie alle Transaktionsprotokollsicherungen, die Sie in der zwischenzeitlichen Datenbank (auf Server B) erstellt haben, in jeder anderen sekundären Datenbank (auf Server C) unter Angabe von WITH NORECOVERY wieder her. Dadurch kann der Protokollversand von der ursprünglichen primären Datenbank nach deren Aktualisierung fortgesetzt werden, ohne dass in jeder sekundären Datenbank eine komplette Datenbankwiederherstellung durchgeführt werden muss.  
  
9. Stellen Sie das Transaktionsprotokoll vom zwischenzeitlichen primären Server (Server B) unter Angabe von WITH RECOVERY in der ursprünglichen primären Datenbank (auf Server A) wieder her.  
  
##  <a name="Redeploying"></a> Erneutes Bereitstellen des Protokollversands  
 Wenn Sie die Protokollversandkonfiguration nicht mit einem der oben beschriebenen Verfahren migrieren möchten, können Sie den Protokollversand neu bereitstellen, indem Sie die sekundäre Datenbank mit einer vollständigen Sicherung und Wiederherstellung der primären Datenbank neu initialisieren. Diese Option bietet sich u. U. an, wenn es um eine kleine Datenbank geht oder wenn Hochverfügbarkeit während des Upgradevorgangs nicht wichtig ist.  
  
 Informationen zum Aktivieren des Protokollversands finden Sie unter [Konfigurieren des Protokollversands &#40;SQL Server&#41;](configure-log-shipping-sql-server.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Transaktionsprotokollsicherungen &#40;SQL Server&#41;](../../relational-databases/backup-restore/transaction-log-backups-sql-server.md)   
 [Anwenden von Transaktionsprotokollsicherungen &#40;SQL Server&#41;](../../relational-databases/backup-restore/apply-transaction-log-backups-sql-server.md)   
 [Protokollversandtabellen und gespeicherte Prozeduren](log-shipping-tables-and-stored-procedures.md)  
  
  
