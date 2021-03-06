---
title: Projektorientierte Datenbankentwicklung mit Befehlszeilentools | Microsoft-Dokumentation
ms.custom:
- SSDT
ms.date: 04/26/2017
ms.prod: sql
ms.technology: ssdt
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 9a26def9-8fbd-43e4-9e57-414840b73ed8
caps.latest.revision: 10
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 157aa8f1aca7fac32f7c7606c4681b2e27db1d37
ms.sourcegitcommit: c8f7e9f05043ac10af8a742153e81ab81aa6a3c3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2018
ms.locfileid: "39087932"
---
# <a name="project-oriented-database-development-using-command-line-tools"></a>Projektorientierte Datenbankentwicklung mit Befehlszeilentools
SQL Server Data Tools stellt Befehlszeilentools bereit, die eine Reihe von Szenarios für die projektorientierte Datenbankentwicklung ermöglichen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
|||  
|-|-|  
|[SqlPackage.exe](../tools/sqlpackage.md)|In diesem Thema wird das Hilfsprogramm SQLPackage.exe beschrieben, das für die folgenden Aufgaben verwendet wird:<br /><br />– Extrahieren einer DACPAC-Datei aus einer SQL Server-Livedatenbank<br />– Veröffentlichen einer DACPAC-Datei in einer SQL Server-Livedatenbank, um das Livedatenbankschema inkrementell so zu aktualisieren, dass es mit der DACPAC-Datei übereinstimmt<br />– Vergleichen einer DACPAC-Datei mit einer SQL Server-Livedatenbank und Generieren eines Transact\-SQL-Skripts für inkrementelle Upgrades, ohne dass die Livedatenbank aktualisiert wird<br />– Vergleichen von zwei DACPAC-Dateien, um ein Transact\-SQL-Skript für inkrementelle Upgrades zu generieren<br />– Generieren eines XML-Berichts mit einer Übersicht über die Änderungen durch inkrementelle Upgrades, die bei inkrementellen Upgrades der Datenbank auftreten würden|  
|[Verwenden von MSDeploy mit dem dbSqlPackage-Anbieter](../ssdt/using-msdeploy-with-dbsqlpackage-provider.md)|In diesem Thema wird der in SSDT enthaltene [Webbereitstellungstool](http://go.microsoft.com/fwlink/?LinkId=231798)-Anbieter „dbSqlPackage“ beschrieben. Dieser wird zusammen mit dem Webbereitstellungstool der Microsoft-Internetinformationsdienste (IIS) (MSDeploy.exe) für folgende Aufgaben verwendet:<br /><br />– Extrahieren einer DACPAC-Datei aus einer lokalen SQL Server- oder SQL Azure-Datenbank oder SQL Server- bzw. SQL Azure-Remotedatenbank<br />– Veröffentlichen einer DACPAC-Datei in einer lokalen SQL Server- oder SQL Azure-Datenbank oder SQL Server- bzw. SQL Azure-Remotedatenbank, um inkrementelle Upgrades durchzuführen<br />– Veröffentlichen aus einer lokalen SQL Server-Datenbank in einer SQL Server- oder SQL Azure-Remotedatenbank, um inkrementelle Upgrades für die Remotedatenbank durchzuführen<br />– Vergleichen einer DACPAC-Datei mit einer lokalen SQL Server- oder SQL Azure-Datenbank oder SQL Server- bzw. SQL Azure-Remotedatenbank, um ein Transact\-SQL-Skript für inkrementelle Upgrades zu generieren, ohne dass die Livedatenbank aktualisiert wird.<br />– Generieren eines XML-Berichts mit einer Übersicht über die Änderungen durch inkrementelle Upgrades, die bei inkrementellen Upgrades der Datenbank auftreten würden|  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
[Projektorientierte Offlinedatenbankentwicklung](../ssdt/project-oriented-offline-database-development.md)  
  
