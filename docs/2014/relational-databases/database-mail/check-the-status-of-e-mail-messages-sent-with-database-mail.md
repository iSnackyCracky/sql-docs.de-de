---
title: Prüfen des Status von mit Datenbank-E-Mail gesendeten E-Mail-Nachrichten | Microsoft- Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- e-mail [SQL Server], status information
- mail [SQL Server], status information
- Database Mail [SQL Server], message status
- status information [Database Mail]
ms.assetid: eb290f24-b52f-46bc-84eb-595afee6a5f3
caps.latest.revision: 29
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: f192ac08bf5309f660e2b4a78eeaf748b54cdb3c
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37188507"
---
# <a name="check-the-status-of-e-mail-messages-sent-with-database-mail"></a>Überprüfen des Status von mit Datenbank-E-Mail gesendeten E-Mail-Nachrichten
  In diesem Thema wird beschrieben, wie der Status der mittels Datenbank-E-Mail in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] gesendeten E-Mail durch das Verwenden von [!INCLUDE[tsql](../../includes/tsql-md.md)]überprüft wird.  
  
-   **Vorbereitungen:**  
  
-   **So zeigen Sie den Status der mittels Datenbank-E-Mail gesendeten E-Mail mit folgender Komponente an:**  [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> Vorbereitungsmaßnahmen  
 Datenbank-E-Mail speichert Kopien ausgehender E-Mail-Nachrichten in den Sichten **sysmail_allitems**, **sysmail_sentitems**, **sysmail_unsentitems**und **sysmail_faileditems** der **msdb** -Datenbank. Das externe Programm Datenbank-E-Mail protokolliert die Aktivität und zeigt das Protokoll über das Windows-Anwendungsereignisprotokoll und die **sysmail_event_log** -Sicht der **msdb** -Datenbank an. Führen Sie zum Prüfen des Status einer E-Mail-Nachricht eine Abfrage für diese Sicht aus. Für E-Mail-Nachrichten gibt es vier Statusmöglichkeiten: **sent**, **unsent**, **retrying**und **failed**.  
  
##  <a name="TsqlProcedure"></a> Verwenden von Transact-SQL  
 **So zeigen Sie den Status der E-Mail an, die mittels Datenbank-E-Mail gesendet wurde**  
  
> [!NOTE]  
>  Ein Beispiel für diese Prozedur finden Sie weiter unten in diesem Abschnitt unter [Beispiel (Transact-SQL)](#TsqlExample).  
  
1.  Wählen Sie aus der **sysmail_allitems** -Tabelle aus, und geben Sie dabei die zu prüfenden Nachrichten nach **mailitem_id** oder **sent_status**an.  
  
2.  Um den von dem externen Programm zurückgegebenen Status für die E-Mail-Nachricht zu prüfen, verknüpfen Sie die **sysmail_allitems** -Sicht mit der **sysmail_event_log** -Sicht auf der **mailitem_id** -Spalte, wie im folgenden Abschnitt gezeigt.  
  
     Standardmäßig protokolliert das externe Programm keine Informationen zu Nachrichten, die erfolgreich gesendet wurden. Um alle Nachrichten zu protokollieren, legen Sie die Protokolliergrad auf der Seite **Systemparameter konfigurieren** des **Assistenten zum Konfigurieren von Datenbank-E-Mail**auf 'Ausführlich' fest.  
  
###  <a name="TsqlExample"></a> Beispiel (Transact-SQL)  
 Im folgenden Beispiel werden Informationen zu allen an `danw` gesendeten E-Mail-Nachrichten aufgelistet, die das externe Programm nicht erfolgreich senden konnte. Die Anweisung listet den Betreff, Datum und Uhrzeit, zu denen das Senden der Nachricht durch das externe Programm fehlgeschlagen ist, und die Fehlermeldung des Datenbank-E-Mail-Protokolls.  
  
```  
USE msdb ;  
GO  
  
-- Show the subject, the time that the mail item row was last  
-- modified, and the log information.  
-- Join sysmail_faileditems to sysmail_event_log   
-- on the mailitem_id column.  
-- In the WHERE clause list items where danw was in the recipients,  
-- copy_recipients, or blind_copy_recipients.  
-- These are the items that would have been sent  
-- to danw.  
  
SELECT items.subject,  
    items.last_mod_date  
    ,l.description FROM dbo.sysmail_faileditems as items  
INNER JOIN dbo.sysmail_event_log AS l  
    ON items.mailitem_id = l.mailitem_id  
WHERE items.recipients LIKE '%danw%'    
    OR items.copy_recipients LIKE '%danw%'   
    OR items.blind_copy_recipients LIKE '%danw%'  
GO  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Datenbank-E-Mail-Protokoll und -Überwachung](database-mail-log-and-audits.md)  
  
  
