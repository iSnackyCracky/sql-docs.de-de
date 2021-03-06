---
title: Sichern, wiederherstellen und Synchronisieren von Datenbanken (XMLA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- restoring databases [XML for Analysis]
- backing up databases [XML for Analysis]
- database backups [XML for Analysis]
- synchronization [XML for Analysis]
- database restores [XML for Analysis]
ms.assetid: 6c021b2e-6ad0-444e-b23f-4b5f72ce084b
caps.latest.revision: 22
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 07f4fd6beae68fc0d8a81f610beb56ff779ec25d
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37159601"
---
# <a name="backing-up-restoring-and-synchronizing-databases-xmla"></a>Sichern, Wiederherstellen und Synchronisieren von Datenbanken (XMLA)
  In XML for Analysis gibt es drei Befehle für das Sichern, Wiederherstellen und Synchronisieren von Datenbanken:  
  
-   Die [Sicherung](../xmla/xml-elements-commands/backup-element-xmla.md) Befehl sichert eine [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank mithilfe einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Sicherungsdatei (.abf), wie im Abschnitt beschrieben [Sichern von Datenbanken](#backing_up_databases).  
  
-   Die [wiederherstellen](../xmla/xml-elements-commands/restore-element-xmla.md) -Befehl wird eine [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Datenbank aus einer ABF-Datei, klicken Sie im Abschnitt beschriebenen [Wiederherstellen von Datenbanken](#restoring_databases).  
  
-   Die [synchronisierende](../xmla/xml-elements-commands/synchronize-element-xmla.md) -Befehl synchronisiert eine [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] mit den Daten und Metadaten einer anderen Datenbank, Datenbank, wie im Abschnitt beschrieben [Synchronisieren von Datenbanken](#synchronizing_databases).  
  
##  <a name="backing_up_databases"></a> Sichern von Datenbanken  
 Wie bereits erwähnt, sichert der `Backup`-Befehl eine angegebene [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Datenbank in einer Sicherungsdatei. Der `Backup`-Befehl weist mehrere Eigenschaften auf, mit denen Sie die zu sichernde Datenbank, die zu verwendende Sicherungsdatei, die Methode zum Sichern von Sicherheitsdefinitionen sowie die zu sichernden Remotepartitionen angeben können.  
  
> [!IMPORTANT]  
>  Das Analysis Services-Dienstkonto muss über die Berechtigung zum Schreiben von Daten in den für jede Datei angegebenen Sicherungsspeicherort verfügen. Dem Benutzer muss zudem eine der folgenden Rollen zugewiesen worden sein: Administratorrolle für die [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Instanz oder Mitglied einer Datenbankrolle mit der Berechtigung Vollzugriff (Administrator) für die wiederherzustellende Datenbank.  
  
### <a name="specifying-the-database-and-backup-file"></a>Angeben der Datenbank und der Sicherungsdatei  
 Um die Datenbank gesichert werden, anzugeben, legen Sie die [Objekt](../xmla/xml-elements-properties/object-element-xmla.md) Eigenschaft der `Backup` Befehl. Die `Object`-Eigenschaft muss einen Objektbezeichner für eine Datenbank enthalten; andernfalls tritt ein Fehler auf.  
  
 Um die Datei anzugeben, die erstellt und der im Sicherungsprozess verwendet werden, legen Sie die [Datei](../xmla/xml-elements-properties/file-element-xmla.md) Eigenschaft der `Backup` Befehl. Die `File`-Eigenschaft sollte auf einen UNC-Pfad und -Dateinamen für die zu erstellende Sicherungsdatei festgelegt werden.  
  
 Sie können nicht nur angeben, welche Datei für die Sicherung verwendet werden soll, sondern Sie können auch die folgenden Optionen für die angegebene Sicherungsdatei festlegen:  
  
-   Setzen Sie die [AllowOverwrite](../xmla/xml-elements-properties/allowoverwrite-element-xmla.md) Eigenschaft auf "true", die `Backup` Befehl überschreibt die Sicherungsdatei aus, wenn die angegebene Datei bereits vorhanden ist. Wenn Sie die `AllowOverwrite`-Eigenschaft auf den Wert FALSE festlegen, tritt ein Fehler auf, falls die angegebene Sicherungsdatei bereits vorhanden ist.  
  
-   Setzen Sie die [ApplyCompression](../xmla/xml-elements-properties/applycompression-element-xmla.md) Eigenschaft auf "true", die Sicherungsdatei komprimiert wird, nachdem die Datei erstellt wird.  
  
-   Setzen Sie die [Kennwort](../xmla/xml-elements-properties/password-element-xmla.md) Eigenschaft auf einen nicht leeren Wert, der Sicherungsdatei wird unter Verwendung des angegebenen Kennworts verschlüsselt.  
  
    > [!IMPORTANT]  
    >  Wenn die Eigenschaften `ApplyCompression` und `Password` nicht angegeben werden, speichert die Sicherungsdatei Benutzernamen und Kennwörter, die in Verbindungszeichenfolgen in Klartext enthalten sind. Daten, die in Klartext gespeichert werden, können abgerufen werden. Verwenden Sie für erhöhte Sicherheit die Einstellungen `ApplyCompression` und `Password`, um die Sicherungsdatei sowohl zu komprimieren als auch zu verschlüsseln.  
  
### <a name="backing-up-security-settings"></a>Sichern von Sicherheitseinstellungen  
 Die [Sicherheit](../xmla/xml-elements-properties/security-element-xmla.md) Eigenschaft bestimmt, ob die `Backup` Befehl sichert die sicherheitsdefinitionen wie Rollen und Berechtigungen definiert werden, auf eine [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Datenbank. Die `Security`-Eigenschaft bestimmt auch, ob die Sicherungsdatei die Windows-Benutzerkonten und -Gruppen enthält, die als Mitglieder der Sicherheitsdefinitionen definiert sind.  
  
 Der Wert der `Security`-Eigenschaft ist auf eine der in der folgenden Tabelle aufgelisteten Zeichenfolgen beschränkt.  
  
|value|Description|  
|-----------|-----------------|  
|*SkipMembership*|Einbeziehen von Sicherheitsdefinitionen und Ausschließen von Informationen zur Mitgliedschaft in der Sicherungsdatei.|  
|*CopyAll*|Einbeziehen von Sicherheitsdefinitionen und Informationen zur Mitgliedschaft in der Sicherungsdatei.|  
|*IgnoreSecurity*|Ausschließen von Sicherheitsdefinitionen aus der Sicherungsdatei.|  
  
### <a name="backing-up-remote-partitions"></a>Sichern von Remotepartitionen  
 Zum Sichern von Remotepartitionen in der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Datenbank Festlegen der [BackupRemotePartitions](../xmla/xml-elements-properties/backupremotepartitions-element-xmla.md) Eigenschaft der `Backup` -Befehls auf true fest. Diese Einstellung veranlasst den `Backup`-Befehl, eine Remotesicherungsdatei für jede Remotedatenquelle zu erstellen, die zum Speichern von Remotepartitionen für die Datenbank verwendet wird.  
  
 Für jede Remotedatenquelle gesichert werden müssen, können Sie eine entsprechende Sicherungsdatei angeben, dazu einen [Speicherort](../xmla/xml-elements-properties/location-element-xmla.md) Element in der [Speicherorte](../xmla/xml-elements-properties/locations-element-xmla.md) Eigenschaft der `Backup` Befehl. Der `Location` Element müssen die `File` -Eigenschaft festgelegt wird, auf den UNC-Pfad und Dateinamen der remotesicherungsdatei und die zugehörige [DataSourceID](../xmla/xml-elements-properties/id-element-xmla.md) -Eigenschaft auf den Bezeichner der Remotedatenquelle, die in der Datenbank definiert.  
  
##  <a name="restoring_databases"></a> Wiederherstellen von Datenbanken  
 Der `Restore`-Befehl stellt eine angegebene [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Datenbank mithilfe einer Sicherungsdatei wieder her. Der `Restore`-Befehl weist mehrere Eigenschaften auf, mit denen Sie die wiederherzustellende Datenbank, die zu verwendende Sicherungsdatei, die Methode zum Wiederherstellen von Sicherheitsdefinitionen sowie die zu speichernden Remotepartitionen und das Verschieben relationaler OLAP-Objekte (ROLAP-Objekte) angeben können.  
  
> [!IMPORTANT]  
>  Für jede Sicherungsdatei muss der Benutzer, der den Wiederherstellungsbefehl ausführt, über die Berechtigung zum Lesen von dem für jede Datei angegebenen Sicherungsspeicherort verfügen. Zum Wiederherstellen einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank, die nicht auf dem Server installiert ist, muss der Benutzer zusätzlich Mitglied der Serverrolle für die betreffende [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Instanz sein. Zum Überschreiben einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Datenbank muss der Benutzer entweder Mitglied der Serverrolle für die [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Instanz oder Mitglied einer Datenbankrolle mit den Berechtigungen Vollzugriff (Administrator) für die wiederherzustellende Datenbank sein.  
  
> [!NOTE]  
>  Nach dem Wiederherstellen einer vorhandenen Datenbank verliert der Benutzer, der die Datenbank wiederhergestellt hat, möglicherweise den Zugriff auf diese Datenbank. Dies ist u. U. der Fall, wenn der Benutzer zum Zeitpunkt der Sicherung kein Mitglied der Serverrolle oder der Datenbankrolle mit der Berechtigung "Vollzugriff (Administrator)" war.  
  
### <a name="specifying-the-database-and-backup-file"></a>Angeben der Datenbank und der Sicherungsdatei  
 Die `DatabaseName`-Eigenschaft des `Restore`-Befehls muss einen Objektbezeichner für eine Datenbank enthalten; andernfalls tritt ein Fehler auf. Wenn die angegebene Datenbank bereits vorhanden ist, bestimmt die `AllowOverwrite`-Eigenschaft, ob die vorhandene Datenbank überschrieben wird. Wenn Sie die `AllowOverwrite`-Eigenschaft auf den Wert FALSE festlegen und die angegebene Datenbank bereits vorhanden ist, tritt ein Fehler auf.  
  
 Die `File`-Eigenschaft des `Restore`-Befehls sollte auf einen UNC-Pfad und -Dateinamen für die Sicherungsdatei festgelegt werden, die in der angegebenen Datenbank wiederhergestellt werden soll. Sie können auch die `Password`-Eigenschaft für die angegebene Sicherungsdatei festlegen. Wenn Sie die `Password`-Eigenschaft auf einen bestimmten Wert festlegen, wird die Sicherungsdatei mithilfe des angegebenen Kennworts entschlüsselt. Wenn die Sicherungsdatei nicht verschlüsselt ist oder wenn das angegebene Kennwort nicht mit dem für die Entschlüsselung der Sicherungsdatei verwendeten Kennwort übereinstimmt, tritt ein Fehler auf.  
  
### <a name="restoring-security-settings"></a>Wiederherstellen von Sicherheitseinstellungen  
 Die `Security`-Eigenschaft bestimmt, ob mit dem `Restore`-Befehl die Sicherheitsdefinitionen wie Rollen und Berechtigungen wiederhergestellt werden, die für eine [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Datenbank definiert sind. Die `Security`-Eigenschaft bestimmt auch, ob der `Restore`-Befehl im Rahmen des Wiederherstellungsprozesses die Windows-Benutzerkonten und -Gruppen einschließt, die als Mitglieder der Sicherheitsdefinitionen definiert sind.  
  
 Der Wert dieses Elements ist auf eine der in der folgenden Tabelle aufgelisteten Zeichenfolgen beschränkt.  
  
|value|Description|  
|-----------|-----------------|  
|*SkipMembership*|Einbeziehen von Sicherheitsdefinitionen und Ausschließen von Informationen zur Mitgliedschaft in der Datenbank.|  
|*CopyAll*|Einbeziehen von Sicherheitsdefinitionen und Informationen zur Mitgliedschaft in der Datenbank.|  
|*IgnoreSecurity*|Ausschließen von Sicherheitsdefinitionen aus der Datenbank.|  
  
### <a name="restoring-remote-partitions"></a>Wiederherstellen von Remotepartitionen  
 Für jede Remotesicherungsdatei, die während eines zuvor ausgeführten `Backup`-Befehls erstellt wurde, können Sie die zugeordnete Remotepartition wiederherstellen, indem Sie ein `Location`-Element in die `Locations`-Eigenschaft des `Restore`-Befehls einbeziehen. Die [DataSourceType](../xmla/xml-elements-properties/type-element-xmla.md) -Eigenschaft für jedes `Location` -Element muss ausgeschlossen oder explizit auf festgelegt *Remote*.  
  
 Für jedes angegebene `Location`-Element kontaktiert die [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Instanz die in der `DataSourceID`-Eigenschaft angegebene Remotedatenquelle, um die Partitionen wiederherzustellen, die in der Remotesicherungsdatei definiert sind, welche in der `File`-Eigenschaft angegeben ist. Neben der `DataSourceID`- und der `File`-Eigenschaft sind die folgenden Eigenschaften für jedes `Location`-Element verfügbar, das zum Wiederherstellen einer Remotepartition verwendet wird:  
  
-   Wenn Sie die Verbindungszeichenfolge für die in `DataSourceID` angegebene Remotedatenquelle überschreiben möchten, können Sie die `ConnectionString`-Eigenschaft für das `Location`-Element auf eine andere Verbindungszeichenfolge festlegen. Der Befehl `Restore` verwendet dann die Verbindungszeichenfolge, die in der `ConnectionString`-Eigenschaft enthalten ist. Wenn `ConnectionString` nicht angegeben ist, verwendet der Befehl `Restore` die Verbindungszeichenfolge, die in der Sicherungsdatei für die angegebene Remotedatenquelle gespeichert ist. Sie können die Einstellung `ConnectionString` verwenden, um eine Remotepartition auf eine andere Remoteinstanz zu verschieben. Sie können jedoch die Einstellung `ConnectionString` nicht verwenden, um eine Remotepartition auf der gleichen Instanz wiederherzustellen, die auch die wiederhergestellt Datenbank enthält. Sie können die Eigenschaft `ConnectionString` also nicht verwenden, um eine Remotepartition in eine lokale Partition umzuwandeln.  
  
-   Für jeden ursprünglichen Ordner zum Speichern von Remotepartitionen auf der Remotedatenquelle verwendet wird, können Sie angeben einer [Ordner](../xmla/xml-elements-properties/folder-element-xmla.md) Element an den neuen Ordner, in dem alle im ursprünglichen Ordner gespeicherte Remotepartitionen wiederherzustellen. Wenn ein `Folder`-Element nicht angegeben ist, verwendet der `Restore`-Befehl die ursprünglichen Ordner, die für die in der Remotesicherungsdatei enthaltenen Remotepartitionen angegeben sind.  
  
### <a name="relocating-rolap-objects"></a>Verschieben von ROLAP-Objekten  
 Mit dem `Restore`-Befehl können keine Aggregationen oder Daten für Objekte wiederhergestellt werden, die den ROLAP-Speichermodus verwenden, da solche Informationen in Tabellen in einer zugrunde liegenden relationalen Datenquelle gespeichert werden. Jedoch können die Metadaten für ROLAP-Objekte wiederhergestellt werden. Zum Wiederherstellen der Metadaten für ROLAP-Objekte erstellt der `Restore`-Befehl die Tabellenstruktur in einer relationalen Datenbank neu.  
  
 Sie können das `Location`-Element in einem `Restore`-Befehl verwenden, um ROLAP-Objekte zu verschieben. Für jede `Location` Element zum Verschieben einer Datenquelle verwendet die `DataSourceType` Eigenschaft muss explizit festgelegt werden, um *lokalen*. Sie müssen auch die `ConnectionString`-Eigenschaft des `Location`-Elements auf die Verbindungszeichenfolge für den neuen Speicherort festlegen. Während der Wiederherstellung ersetzt der `Restore`-Befehl die Verbindungszeichenfolge für die Datenquelle, die von der `DataSourceID`-Eigenschaft des `Location`-Elements identifiziert wird, durch den Wert der `ConnectionString`-Eigenschaft des `Location`-Elements.  
  
##  <a name="synchronizing_databases"></a> Synchronisieren von Datenbanken  
 Der Befehl `Synchronize` synchronisiert die Daten und die Metadaten einer angegebenen [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Datenbank mit denen einer anderen Datenbank. Der `Synchronize`-Befehl weist verschiedene Eigenschaften auf, mit denen Sie die Quelldatenbank, die Methode zur Synchronisierung von Sicherheitsdefinitionen, die zu synchronisierenden Remotepartitionen und die Synchronisierung von ROLAP-Objekten angeben können.  
  
> [!NOTE]  
>  Der `Synchronize`-Befehl kann nur von Serveradministratoren und Datenbankadministratoren ausgeführt werden. Sowohl die Quell- als auch die Zieldatenbank müssen den gleichen Datenbank-Kompatibilitätsgrad besitzen.  
  
### <a name="specifying-the-source-database"></a>Angeben der Quelldatenbank  
 Die [Quelle](../xmla/xml-elements-properties/source-element-xmla.md) Eigenschaft der `Synchronize` -Befehl enthält zwei Eigenschaften, `ConnectionString` und `Object`. Die `ConnectionString`-Eigenschaft enthält die Verbindungszeichenfolge der Instanz, die die Quelldatenbank enthält, und die `Object`-Eigenschaft enthält den Objektbezeichner für die Quelldatenbank.  
  
 Die Zieldatenbank ist die aktuelle Datenbank für die Sitzung, in der der `Synchronize`-Befehl ausgeführt wird.  
  
 Wenn die `ApplyCompression`-Eigenschaft des `Synchronize`-Befehls auf den Wert TRUE festgelegt ist, werden die von der Quelldatenbank an die Zieldatenbank gesendeten Informationen vor dem Senden komprimiert.  
  
### <a name="synchronizing-security-settings"></a>Synchronisieren von Sicherheitseinstellungen  
 Die [SynchronizeSecurity](../xmla/xml-elements-properties/synchronizesecurity-element-xmla.md) Eigenschaft bestimmt, ob die `Synchronize` -Befehl synchronisiert die sicherheitsdefinitionen wie Rollen und Berechtigungen, die für die Quelldatenbank definiert. Die `SynchronizeSecurity`-Eigenschaft bestimmt auch, ob der `Sychronize`-Befehl die Windows-Benutzerkonten und -Gruppen enthält, die als Mitglieder der Sicherheitsdefinitionen definiert sind.  
  
 Der Wert dieses Elements ist auf eine der in der folgenden Tabelle aufgelisteten Zeichenfolgen beschränkt.  
  
|value|Description|  
|-----------|-----------------|  
|*SkipMembership*|Einbeziehen von Sicherheitsdefinitionen und Ausschließen von Informationen zur Mitgliedschaft in der Zieldatenbank.|  
|*CopyAll*|Einbeziehen von Sicherheitsdefinitionen und Informationen zur Mitgliedschaft in der Zieldatenbank.|  
|*IgnoreSecurity*|Ausschließen von Sicherheitsdefinitionen aus der Zieldatenbank.|  
  
### <a name="synchronizing-remote-partitions"></a>Synchronisieren von Remotepartitionen  
 Für jede Remotedatenbank, die in der Zieldatenbank vorhanden ist, können Sie jede zugeordnete Remotepartition synchronisieren, indem Sie ein `Location`-Element in die `Locations`-Eigenschaft des `Synchronize`-Befehls einbeziehen. Für jede `Location` -Element, das `DataSourceType` Eigenschaft muss ausgeschlossen oder explizit auf festgelegt *Remote*.  
  
 Zum Definieren und Herstellen einer Verbindung zu einer Remotedatenquelle in der Zieldatenbank verwendet der `Synchronize`-Befehl die Verbindungszeichenfolge, die in der `ConnectionString`-Eigenschaft des `Location`-Elements definiert ist. Der `Synchronize`-Befehl verwendet dann die `DataSourceID`-Eigenschaft des `Location`-Elements, um die zu synchronisierenden Remotepartitionen zu identifizieren. Die `Synchronize`-Befehl synchronisiert die Remotepartitionen in der Remotedatenquelle, die im angegebenen die `DataSourceID` Eigenschaft für die Quelldatenbank mit der Remotedatenquelle, die im angegebenen die `DataSourceID` Eigenschaft in der Zieldatenbank.  
  
 Für jeden ursprünglich zum Speichern der Remotepartitionen in der Remotedatenquelle der Quelldatenbank verwendeten Ordner können Sie auch ein `Folder`-Element im `Location`-Element verwenden. Das `Folder`-Element gibt den neuen Ordner für die Zieldatenbank an, in dem alle im ursprünglichen Ordner in der Remotedatenquelle gespeicherten Remotepartitionen synchronisiert werden sollen. Wenn ein `Folder`-Element nicht angegeben ist, verwendet der Synchronize-Befehl die ursprünglichen Ordner, die für die in der Quelldatenbank enthaltenen Remotepartitionen angegeben sind.  
  
### <a name="synchronizing-rolap-objects"></a>Synchronisieren von ROLAP-Objekten  
 Mit dem `Synchronize`-Befehl können keine Aggregationen oder Daten für Objekte synchronisiert werden, die den ROLAP-Speichermodus verwenden, da solche Informationen in Tabellen in einer zugrunde liegenden relationalen Datenquelle gespeichert werden. Jedoch können die Metadaten für ROLAP-Objekte synchronisiert werden. Zum Synchronisieren der Metadaten stellt der `Synchronize`-Befehl die Tabellenstruktur für eine relationale Datenbank wieder her.  
  
 Sie können das `Location`-Element in einem Synchronize-Befehl verwenden, um ROLAP-Objekte zu synchronisieren. Für jede `Location` Element zum Verschieben einer Datenquelle verwendet die `DataSourceType` Eigenschaft muss explizit festgelegt werden, um *lokalen*. zugreifen. Sie müssen auch die `ConnectionString`-Eigenschaft des `Location`-Elements auf die Verbindungszeichenfolge für den neuen Speicherort festlegen. Während der Synchronisierung ersetzt der `Synchronize`-Befehl die Verbindungszeichenfolge für die Datenquelle, die von der `DataSourceID`-Eigenschaft des `Location`-Elements identifiziert wird, durch den Wert der `ConnectionString`-Eigenschaft des `Location`-Elements.  
  
## <a name="see-also"></a>Siehe auch  
 [Sichern des Elements &#40;XMLA&#41;](../xmla/xml-elements-commands/backup-element-xmla.md)   
 [Restore-Element &#40;XMLA&#41;](../xmla/xml-elements-commands/restore-element-xmla.md)   
 [Synchronize-Element &#40;XMLA&#41;](../xmla/xml-elements-commands/synchronize-element-xmla.md)   
 [Sichern und Wiederherstellen von Analysis Services-Datenbanken](../multidimensional-models/backup-and-restore-of-analysis-services-databases.md)  
  
  
