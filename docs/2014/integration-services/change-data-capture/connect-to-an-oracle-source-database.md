---
title: Herstellen einer Verbindung mit einer Oracle-Quelldatenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- oraDb
ms.assetid: 220cf555-0db2-443c-8f87-8e413f3ca731
caps.latest.revision: 7
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: aadbab5ab6164ca68488cb8bc6dc6ed8e55aed3c
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37164873"
---
# <a name="connect-to-an-oracle-source-database"></a>Herstellen einer Verbindung zu einer Oracle-Quelldatenbank
  Verwenden Sie die Seite der Oracle-Quelle zum Eingeben der Informationen, die zum Herstellen einer Verbindung mit der Oracle-Quelldatenbank erforderlich sind. Die CDC-Instanz liest die Wiederholungsprotokolle (Redo Logs) der Oracle-Datenbank, mit der Sie verbunden sind.  
  
 **Oracle Connect String**  
 Geben Sie die Oracle-Verbindungszeichenfolge zum Computer mit der verwendeten Oracle-Datenbank ein. Zum Schreiben der Verbindungszeichenfolge wird eine der folgenden Methoden verwendet:  
  
 `host[:port][/service name]`  
  
 In der Verbindungszeichenfolge kann auch ein Oracle Net-Verbindungsdeskriptor angegeben werden, z. B. `(DESCRIPTION=(ADDRESS=(PROTOCOL=tcp) (HOST=erp.contoso.com) (PORT=1521)) (CONNECT_DATA=(SERVICE_NAME=orcl)))`  
  
 Wenn Sie einen Verzeichnisserver oder tnsnames verwenden, kann die Verbindungszeichenfolge der Name der Verbindung sein.  
  
 **Oracle Log Mining Authentication**  
 Um die Anmeldeinformationen für den Oracle-Datenbankbenutzer einzugeben, der für das Log Mining autorisiert ist, wählen Sie eine der folgenden Optionen aus:  
  
-   **Windows-Authentifizierung**: Wählen Sie diese Option, um die aktuellen Anmeldeinformationen für die Windows-Domäne zu verwenden. Sie können diese Option nur verwenden, wenn die Oracle-Datenbank für die Nutzung der Windows-Authentifizierung konfiguriert ist.  
  
-   **Oracle Authentication**: Wenn Sie diese Option aktivieren, müssen Sie **Benutzername** und **Kennwort** für den Benutzer der Oracle-Datenbank eingeben, mit der Sie eine Verbindung herstellen.  
  
> [!NOTE]  
>  Einem Benutzer müssen in der Oracle-Datenbank die folgenden Berechtigungen gewährt werden, um als Log Mining-Benutzer fungieren zu können.  
>   
>  -   SELECT on \<beliebige-aufgezeichnete-tabelle>  
> -   SELECT ANY TRANSACTION  
> -   EXECUTE on DBMS LOGMNR  
> -   SELECT on V$LOGMNR CONTENTS  
> -   SELECT on V$ARCHIVED LOG  
> -   SELECT on V$LOG  
> -   SELECT on V$LOGFILE  
> -   SELECT on V$DATABASE  
> -   SELECT on V$THREAD  
> -   SELECT on ALL INDEXES  
> -   SELECT on ALL OBJECTS  
> -   SELECT on DBA OBJECTS  
> -   SELECT on ALL TABLES  
>   
>  Falls eine dieser Berechtigungen nicht für V$xxx gewährt werden kann, können Sie diese V_S$xxx gewähren.  
  
 **Verbindung testen**  
 Klicken Sie auf **Verbindung testen** , um zu ermitteln, ob Sie eine Verbindung mit dem Remotecomputer hergestellt haben, der über die Oracle-Datenbank verfügt. Ein Dialogfeld wird geöffnet, in dem Sie informiert werden, ob die Verbindungsherstellung erfolgreich war.  
  
> [!IMPORTANT]  
>  Aufgrund eines bekannten Problems kann beim Herstellen der Verbindung zur Oracle-Quelldatenbank ein Fehler auftreten, wenn der CDC Designer nicht als Administrator ausgeführt wird. Falls bei der Verbindungsherstellung ein Fehler auftritt, schließen Sie den CDC Designer, und starten Sie die Anwendung unter Verwendung der Option **Als Administrator ausführen** neu.  
  
 Klicken Sie **Weiter** , wenn Sie alle Informationen auf dieser Seite eingegeben haben, um den Schritt [Select Oracle Tables and Columns](select-oracle-tables-and-columns.md)auszuführen.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Erstellen von SQL Server Change Database-Instanz](how-to-create-the-sql-server-change-database-instance.md)   
 [Bearbeiten von Instanzeigenschaften](edit-instance-properties.md)  
  
  
