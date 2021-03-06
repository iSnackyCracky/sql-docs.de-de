---
title: Erste Schritte mit SSMA für Access-Konsole (AccessToSQL) | Microsoft-Dokumentation
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.technology: ssma
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: 8585ec16-7e0a-483a-b250-adab9b9232a3
caps.latest.revision: 21
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.openlocfilehash: 3a218ba28025f882d96cdfc122ceda01464419a3
ms.sourcegitcommit: 79d4dc820767f7836720ce26a61097ba5a5f23f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2018
ms.locfileid: "40396138"
---
# <a name="getting-started-with-ssma-for-access-console-accesstosql"></a>Erste Schritte mit SSMA für Access-Konsole (AccessToSQL)
Dieser Abschnitt beschreibt die Vorgehensweise zum Starten, und beginnen Sie mit der Access-Konsolenanwendung. Auch aufgeführt ist, werden die Konventionen in diesem Dokument, in einer typischen Ausgabefenster von SSMA-Konsole verwendet.  
  
## <a name="launching-ssma-console"></a>Starten SSMA-Konsole  
Verwenden Sie die folgenden Schritte aus, um die SSMA-Console-Anwendung zu starten:  
  
1.  Wechseln Sie zu **starten** und zeigen Sie auf **Programme**.  
  
2.  Klicken Sie auf die **SQL Server Migration Assistant für Access Command Prompt** Verknüpfung.  
  
    Klicken Sie im Menü der SSMA-Konsole Nutzung angezeigt und `(/? Help)`, damit Sie mit der Konsolenanwendung zu beginnen.  
  
## <a name="procedure-for-using-the-ssma-console"></a>Verfahren für die Verwendung der SSMA-Konsole  
Nach dem die Konsole wurde erfolgreich auf Ihrem Windows-System gestartet wird, können Sie die folgenden Schritte aus, an einem Projekt arbeiten:  
  
1.  Konfigurieren Sie SSMA-Konsole, über die Skriptdateien. Weitere Informationen in diesem Abschnitt finden Sie unter [Skriptdateien erstellen &#40;AccessToSQL&#41;](../../ssma/access/creating-script-files-accesstosql.md).  
  
2.  [Erstellen die Variable Value Files &#40;AccessToSQL&#41;](../../ssma/access/creating-variable-value-files-accesstosql.md)  
  
3.  [Erstellen die Server-Verbindungsdateien &#40;AccessToSQL&#41;](../../ssma/access/creating-the-server-connection-files-accesstosql.md)  
  
4.  [Executing the SSMA Console ausführen &#40;AccessToSQL&#41; ](../../ssma/access/executing-the-ssma-console-accesstosql.md) basierend auf Ihrer Projekt-Anforderungen  
  
Zusätzliche Funktionen:  
  
1.  [Geben Sie ein Kennwort](managing-passwords-accesstosql.md) und exportieren / importieren Sie es auf anderen Computern im Fenster  
  
2.  [Generieren von Berichten](generating-reports-accesstosql.md) Ausgabe Berichte für die Bewertung /conversion und Datenmigration detaillierte Xml anzeigen. Ausführliche Berichte können auch für Aktualisierung und Synchronisierung Befehle generiert werden.  
  
## <a name="ssma-console-output-conventions"></a>SSMA-Konsole Ausgabe Konventionen  
Beim Ausführen der SSMA-Skript-Befehle und Optionen an, das Konsolenprogramm zeigt die Ergebnisse und Meldungen (Informationen, Fehler usw.) für den Benutzer in der Konsole oder ggf. umgeleitet werden, um eine XML-Ausgabedatei. Jede Art von Nachricht in der Ausgabe wird durch eine eindeutige Farbe gekennzeichnet. Beispielsweise gibt die Textnachricht in Weiß Skriptbefehle für die Datei an; in Grün stellt dar, eine Eingabeaufforderung für Benutzereingaben und So weiter.  
  
![SSMA-Konsolenausgabe](../../ssma/access/media/ssmaconsoleoutput.jpg "SSMA-Konsolenausgabe")  
  
Color-Interpretation der Konsolenausgabe in der folgenden Tabelle:  
  
|Farbe|Description|  
|---------|---------------|  
|Red|Schwerwiegender Fehler während der Ausführung|  
|Grau|Datums- und Zeitstempel, an den Benutzer|  
|White|Datei Skriptbefehle, Nachrichtentyp|  
|Gelb|Warnung|  
|Green|Eingabeaufforderung für Benutzereingaben|  
|Cyan|Start, Ende und das Ergebnis eines Vorgangs|  
  
## <a name="see-also"></a>Siehe auch  
[Installieren von SQL Server Migration Assistant für Access](installing-sql-server-migration-assistant-for-access-accesstosql.md)  
  
