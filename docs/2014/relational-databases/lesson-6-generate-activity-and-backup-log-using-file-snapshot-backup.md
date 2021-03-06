---
title: 'Lektion 7: Verschieben von Datendateien in Microsoft Azure Storage | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 26aa534a-afe7-4a14-b99f-a9184fc699bd
caps.latest.revision: 9
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 44bc025ce3eb536e10f4c77410ea487e59f006ee
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37162711"
---
# <a name="lesson-7-move-your-data-files-to-windows-azure-storage"></a>Lektion 7: Verschieben von Datendateien in den Windows Azure-Speicher
  In dieser Lektion erfahren Sie, wie Sie die Datendateien in den Windows Azure-Speicher verschieben (nicht jedoch die SQL Server-Instanz). Für diese Lektion müssen Sie Lektion 4, 5 und 6 nicht abschließen.  
  
 Um die Datendateien in den Windows Azure-Speicher zu verschieben, können Sie die `ALTER DATABASE`-Anweisung verwenden. Sie ändert den Speicherort der Datendateien.  
  
 In dieser Lektion wird davon ausgegangen, dass Sie bereits die folgenden Schritte abgeschlossen haben:  
  
-   Sie verfügen über ein Windows Azure-Speicherkonto.  
  
-   Sie haben einen Container über Ihr Windows Azure-Speicherkonto erstellt.  
  
-   Sie haben eine Richtlinie in einem Container mit Lese-, Schreib- und Auflistungsrechten erstellt. Sie haben auch einen SAS-Schlüssel generiert.  
  
-   Sie haben die SQL Server-Anmeldeinformationen auf dem Quellcomputer erstellt.  
  
 Führen Sie als Nächstes die folgenden Schritte aus, um die Datendateien in Windows Azure-Speicher zu verschieben:  
  
1.  Erstellen Sie zunächst eine Testdatenbank auf dem Quellcomputer, und fügen Sie einige Daten hinzu.  
  
    ```tsql  
  
    USE master;   
    CREATE DATABASE TestDB1Alter;   
    GO   
    USE TestDB1Alter;   
    GO   
    CREATE TABLE Table1 (Col1 int primary key, Col2 varchar(20));   
    GO   
    INSERT INTO Table1 (Col1, Col2) VALUES (1, 'string1'), (2, 'string2');   
    GO  
  
    ```  
  
2.  Führen Sie den folgenden Code aus:  
  
    ```tsql  
  
    -- In the following statement, modify the path specified in FILENAME to   
    -- the new location of the file in Windows Azure Storage container.   
    ALTER DATABASE TestDB1Alter    
        MODIFY FILE ( NAME = TestDB1Alter,    
                    FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontaineralter/TestDB1AlterData.mdf');   
    GO  
  
    ```  
  
3.  Es wird folgende Meldung angezeigt: "Date Datei "TestDB1Alter" wurde im Systemkatalog geändert. Der neue Pfad wird beim nächsten Start der Datenbank verwendet."  
  
4.  Schalten Sie dann die Datenbank offline.  
  
    ```tsql  
  
    ALTER DATABASE TestDB1Alter SET OFFLINE;   
    GO  
  
    ```  
  
5.  Jetzt müssen Sie die Datendateien in Windows Azure Storage zu kopieren, mit einer der folgenden Methoden: [AzCopy-Tool](http://blogs.msdn.com/b/windowsazurestorage/archive/2012/12/03/azcopy-uploading-downloading-files-for-windows-azure-blobs.aspx), [Put Page](https://msdn.microsoft.com/library/azure/ee691975.aspx), [Referenz zur Speicherclientbibliothek](https://msdn.microsoft.com/library/azure/dn261237.aspx), oder ein Drittanbieter-Speicher-Explorer-Tool.  
  
     **Wichtig:** Wenn Sie diese neue Erweiterung verwenden, stellen Sie immer sicher, dass Sie kein Block-Blob einen Seitenblob erstellen.  
  
6.  Schalten Sie dann die Datenbank online.  
  
    ```tsql  
  
    ALTER DATABASE TestDB1Alter SET ONLINE;   
    GO  
  
    ```  
  
 **Nächste Lektion:**  
  
 [Lektion 8: Wiederherstellen einer Datenbank in Azure Storage](lesson-7-restore-a-database-to-a-point-in-time.md)  
  
  
