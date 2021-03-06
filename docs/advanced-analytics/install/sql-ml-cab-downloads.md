---
title: CAB-Datei für den kumulativen Updates für SQL Server-downloads | Microsoft-Dokumentation
description: CAB-Downloads für SQL Server 2017-Machine Learning Services und SQL Server 2016 R Services.
ms.prod: sql
ms.technology: machine-learning
ms.date: 08/02/2018
ms.topic: conceptual
author: HeidiSteen
ms.author: heidist
manager: cgronlun
ms.openlocfilehash: 6a2893e976e64315a1aad742062e962269439b72
ms.sourcegitcommit: 4cd008a77f456b35204989bbdd31db352716bbe6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39566317"
---
# <a name="cab-downloads-for-cumulative-updates-of-sql-server-in-database-analytics-instances"></a>CAB-downloads für kumulative Updates Analysefunktionen von SQL Server in der Datenbank-Instanzen

SQL Server-Instanzen, die für in-Database-Analyse konfiguriert einschließen, R und Python-Funktionen, die in CAB-Dateien installiert ist und über serviced SQL Server-Setup enthalten sind. 

Auf Servern, die mit dem Internet verbunden werden werden die CAB-Updates über Windows Update in der Regel angewendet. Nicht verbundene Server müssen manuell aktualisiert werden. Dieser Artikel enthält Links zum Herunterladen der CAB-Dateien für die kumulativen Updates von SQL Server 2017 Machine Learning Services (R- und Python) – oder SQL Server 2016 R Services –, damit Sie vom Internet getrennt Server manuell aktualisieren. 

## <a name="prerequisites"></a>Erforderliche Komponenten

Beginnen Sie mit einer Basisinstallation.

+ Auf SQL Server 2017 Machine Learning Services ist die erste Version die Baseline-Installation. 

+ Auf SQL Server 2016 R Services können Sie mit der ersten Version, SP1 oder SP2 starten. 

Weitere Informationen finden Sie unter [Installieren von SQL Server-Machine learning-Komponenten ohne Internetzugang](sql-ml-component-install-without-internet-access.md).

Nachdem Sie eine Baseline-Installation verfügen, können Sie Ausführen einer [slipstream-Upgrade](sql-ml-component-install-without-internet-access.md#slipstream-upgrades) , CAB-Dateien mit aktualisierten Machine Learning-Features umfasst.

CAB-Dateien werden in umgekehrter chronologischer Reihenfolge aufgeführt. Wenn Sie die CAB-Dateien herunterladen und auf den Zielcomputer übertragen, sie in einem geeigneten Ordner speichern wie z. B. **Downloads** oder des Setup-Benutzers % temp %-Ordner.

## <a name="sql-server-2017-cabs"></a>SQL Server 2017 CAB-Dateien

Release  |Downloadlink  |
---------|---------|
**SQL Server 2017 CU8-CU9** |
Microsoft R Open     |keine Änderung; Verwenden der vorherigen [SRO_3.3.3.300_1033.cab](https://go.microsoft.com/fwlink/?LinkId=863894)|
Microsoft R Server      |[SRS_9.2.0.800_1033.cab](https://go.microsoft.com/fwlink/?LinkId=874708&clcid=1033)|
Öffnen Sie Microsoft-Python     |keine Änderung; Verwenden der vorherigen [SPO_9.2.0.24_1033.cab](https://go.microsoft.com/fwlink/?LinkId=851502)|
Microsoft Python-Server    |[SPS_9.2.0.800_1033.cab](https://go.microsoft.com/fwlink/?LinkId=874707&clcid=1033)]|
**SQL Server 2017 CU6-CU7** |
Microsoft R Open     |keine Änderung; Verwenden der vorherigen [SRO_3.3.3.300_1033.cab](https://go.microsoft.com/fwlink/?LinkId=863894)|
Microsoft R Server      |[SRS_9.2.0.600_1033.cab](https://go.microsoft.com/fwlink/?LinkId=871074&clcid=1033)|
Öffnen Sie Microsoft-Python     |keine Änderung; Verwenden der vorherigen [SPO_9.2.0.24_1033.cab](https://go.microsoft.com/fwlink/?LinkId=851502)|
Microsoft Python-Server    |[SPS_9.2.0.600_1033.cab](https://go.microsoft.com/fwlink/?LinkId=871073&clcid=1033)|
**SQL Server 2017 CU5** |
Microsoft R Open     |keine Änderung; Verwenden der vorherigen [SRO_3.3.3.300_1033.cab](https://go.microsoft.com/fwlink/?LinkId=863894)|
Microsoft R Server      |[SRS_9.2.0.500_1033.cab](https://go.microsoft.com/fwlink/?LinkId=869052&clcid=1033)|
Öffnen Sie Microsoft-Python     |keine Änderung; Verwenden der vorherigen [SPO_9.2.0.24_1033.cab](https://go.microsoft.com/fwlink/?LinkId=851502)|
Microsoft Python-Server    |[SPS_9.2.0.500_1033.cab](https://go.microsoft.com/fwlink/?LinkId=869053&clcid=1033)|
**SQL Server 2017 CU4** |
Microsoft R Open     |keine Änderung; Verwenden der vorherigen [SRO_3.3.3.300_1033.cab](https://go.microsoft.com/fwlink/?LinkId=863894)|
Microsoft R Server      |[SRS_9.2.0.400_1033.cab](https://go.microsoft.com/fwlink/?LinkId=866212&clcid=1033)|
Öffnen Sie Microsoft-Python     |keine Änderung; Verwenden der vorherigen [SPO_9.2.0.24_1033.cab](https://go.microsoft.com/fwlink/?LinkId=851502)|
Microsoft Python-Server    |[SPS_9.2.0.400_1033.cab](https://go.microsoft.com/fwlink/?LinkId=866213&clcid=1033)|
**SQL Server 2017 CU3** |
Microsoft R Open     |[SRO_3.3.3.300_1033.cab](https://go.microsoft.com/fwlink/?LinkId=863894)|
Microsoft R Server      |[SRS_9.2.0.300_1033.cab](https://go.microsoft.com/fwlink/?LinkId=863893)|
Öffnen Sie Microsoft-Python     |keine Änderung; Verwenden der vorherigen [SPO_9.2.0.24_1033.cab](https://go.microsoft.com/fwlink/?LinkId=851502)|
Microsoft Python-Server    |[SPS_9.2.0.300_1033.cab](https://go.microsoft.com/fwlink/?LinkId=863892)|
**SQL Server 2017 CU1-CU2** |
Microsoft R Open     |keine Änderung; Verwenden der vorherigen [SRO_3.3.3.24_1033.cab](https://go.microsoft.com/fwlink/?LinkId=851496)|
Microsoft R Server      |[SRS_9.2.0.100_1033.cab](https://go.microsoft.com/fwlink/?LinkId=851501)|
Öffnen Sie Microsoft-Python     |keine Änderung; Verwenden der vorherigen [SPO_9.2.0.24_1033.cab](https://go.microsoft.com/fwlink/?LinkId=851502)|
Microsoft Python-Server    |[SPS_9.2.0.100_1033.cab](https://go.microsoft.com/fwlink/?LinkId=851500) |
**Erste Version von SQL Server 2017** |
Microsoft R Open     |[SRO_3.3.3.24_1033.cab](https://go.microsoft.com/fwlink/?LinkId=851496)|
Microsoft R Server      |[SRS_9.2.0.24_1033.cab](https://go.microsoft.com/fwlink/?LinkId=851507)|
Öffnen Sie Microsoft-Python     |[SPO_9.2.0.24_1033.cab](https://go.microsoft.com/fwlink/?LinkId=851502) |
Microsoft Python-Server    |[SPS_9.2.0.24_1033.cab](https://go.microsoft.com/fwlink/?LinkId=851508) |


<a name="bkmk_2016Installers"></a>

## <a name="sql-server-2016-cabs"></a>SQL Server 2016 CAB-Dateien

Sind für SQL Server 2016 R Services Baseline-Releases, entweder die RTM-Version oder ein Service Pack-Version.

Release  |Downloadlink  |
---------|---------------|
**SQL Server 2016 SP2 CU1-CU2**     |
Microsoft R Open     |[SRO_3.2.2.20000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=866039)|
Microsoft R Server    |[SRS_8.0.3.20000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=866038)|
**SQL Server 2016 SP1 CU4-CU10**     |
Microsoft R Open     |keine Änderung; Verwenden der vorherigen [SRO_3.2.2.16000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=836819)|
Microsoft R Server    |[SRS_8.0.3.17000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=850317)
**SQL Server 2016 SP1 CU1-CU3**     |
Microsoft R Open     |[SRO_3.2.2.16000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=836819)|
Microsoft R Server    |[SRS_8.0.3.16000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=836818)|
**SQL Server 2016 SP1**     |
Microsoft R Open     |[SRO_3.2.2.15000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=824879)
Microsoft R Server     |[SRS_8.0.3.15000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=824881)=
**SQL Server 2016 CU4-CU9**     |
Microsoft R Open     |[SRO_3.2.2.13000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=831785)|
Microsoft R Server     |[SRS_8.0.3.13000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=831676)|
**SQL Server 2016 CU2-CU3**     |
Microsoft R Open     |[SRO_3.2.2.12000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=827398)
Microsoft R Server     |[SRS_8.0.3.12000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=827399)
**SQL Server 2016 CU1**     |
Microsoft R Open     |[SRO_3.2.2.10000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=808803)
Microsoft R Server     |[SRS_8.0.3.10000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=808805)
**SQL Server 2016 RTM**     |
Microsoft R Open     |[SRO_3.2.2.803_1033.cab](https://go.microsoft.com/fwlink/?LinkId=761266)
Microsoft R Server     |[SRS_8.0.3.0_1033.cab](https://go.microsoft.com/fwlink/?LinkId=735051)

> [!NOTE]
> 
> Wenn Sie SQL Server 2016 SP1 CU4 oder SP1 CU5 offline zu installieren, laden Sie SRO_3.2.2.16000_1033.cab herunter. Wenn Sie SRO_3.2.2.13000_1033.cab von FWLINK 831785 heruntergeladen, gemäß der einrichten (Dialogfeld), benennen Sie die Datei als SRO_3.2.2.16000_1033.cab vor der Installation des kumulativen Updates.

Wenn Sie den Quellcode für Microsoft R anzeigen möchten, es ist zum Download zur Verfügung als eines Archivs in TAR-Datei vor: [Installationsprogramme für R Server herunterladen](https://docs.microsoft.com/machine-learning-server/install/r-server-install-windows#download)

# <a name="see-also"></a>Siehe auch

[Installieren von SQL Server-Machine learning-Komponenten ohne Internetzugang](sql-ml-component-install-without-internet-access.md)
