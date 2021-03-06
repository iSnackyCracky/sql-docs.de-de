---
title: Konvertierungen von C-in SQL | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.suite: sql
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- conversions [ODBC], C to SQL
ms.assetid: 7ac098db-9147-4883-8da9-a58ab24a0d31
caps.latest.revision: 35
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017'
ms.openlocfilehash: f983a9ae2d98b5e93b08b65938b6627e1ea83c6c
ms.sourcegitcommit: 4cd008a77f456b35204989bbdd31db352716bbe6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39542550"
---
# <a name="datetime-data-type-conversions-from-c-to-sql"></a>datetime-Datentypkonvertierungen von C in SQL
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  In diesem Thema werden Probleme zu berücksichtigen, bei der Konvertierung von C-Typen in aufgelistet [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Datum/Uhrzeit-Typen.  
  
 Die in der folgenden Tabelle beschriebenen Konvertierungen gelten für auf dem Client ausgeführte Konvertierungen. In Fällen, in dem der Client bruchsekundengenauigkeit für einen Parameter, die von abweicht, die auf dem Server definiert angibt, die clientkonvertierung möglicherweise erfolgreich, aber der Server einen Fehler zurück Wenn **SQLExecute** oder  **SQLExecuteDirect** aufgerufen wird. Insbesondere ODBC behandelt jedes Abschneiden von Sekundenbruchteilen als Fehler, wohingegen die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rundet; beispielsweise wird gerundet, beim Wechseln vom **datetime2(6)** zu **datetime2(2)**. Werte der Datetime-Spalte werden auf 1/300 einer Sekunde gerundet, und für smalldatetime -Spalten werden Sekunden vom Server auf null festgelegt.  
  
|||||||||  
|-|-|-|-|-|-|-|-|  
||SQL_TYPE_DATE|SQL_TYPE_TIME|SQL_SS_TIME2|SQL_TYPE_TIMESTAMP|SQL_SS_TIMSTAMPOFFSET|SQL_CHAR|SQL_WCHAR|  
|SQL_C_DATE|1|-|-|1,6|1,5,6|1,13|1,13|  
|SQL_C_TIME|-|1|1|1,7|1,5,7|1,13|1,13|  
|SQL_C_SS_TIME2|-|1,3|1,10|1,7|1,5,7|1,13|1,13|  
|SQL_C_BINARY(SQL_SS_TIME2_STRUCT)|–|–|1,10,11|–|–|–|–|  
|SQL_C_TYPE_TIMESTAMP|1,2|1,3,4|1,4,10|1,10|1,5,10|1,13|1,13|  
|SQL_C_SS_TIMESTAMPOFFSET|1,2,8|1,3,4,8|1,4,8,10|1,8,10|1,10|1,13|1,13|  
|SQL_C_BINARY(SQL_SS_TIMESTAMPOFFSET_STRUCT)|–|–|–|–|1,10,11|–|–|  
|SQL_C_CHAR/SQL_WCHAR (date)|9|9|9|9,6|9,5,6|–|–|  
|SQL_C_CHAR/SQL_WCHAR (time2)|9|9,3|9,10|9,7,10|9,5,7,10|–|–|  
|SQL_C_CHAR/SQL_WCHAR (datetime)|9,2|9,3,4|9,4,10|9,10|9,5,10|–|–|  
|SQL_C_CHAR/SQL_WCHAR (datetimeoffset)|9,2,8|9,3,4,8|9,4,8,10|9,8,10|9,10|–|–|  
|SQL_C_BINARY(SQL_DATE_STRUCT)|1,11|–|–|–|–|–|–|  
|SQL_C_BINARY(SQL_TIME_STRUCT)|–|–|–|–|–|–|–|  
|SQL_C_BINARY(SQL_TIMESTAMP_STRUCT)|–|–|–|–|–|–|–|  
  
## <a name="key-to-symbols"></a>Aufschlüsselung der Symbole  
  
-   **-**: Keine Konvertierung wird unterstützt. Es wird ein Diagnosedatensatz mit SQLSTATE 07006 und der Meldung "Attributverletzung beschränkter Datentypen" generiert.  
  
-   **1**: Wenn die bereitgestellten Daten nicht gültig ist, wird ein Diagnosedatensatz mit SQLSTATE 22007 und der Meldung "Ungültiges Datetime-Format" generiert.  
  
-   **2**: Time-Felder müssen 0 (null) oder ein Diagnosedatensatz mit SQLSTATE 22008 und der Meldung "Teilbereiche wurden abgeschnitten" generiert wird.  
  
-   **3**: Sekundenbruchteile müssen 0 (null) oder wird ein Diagnosedatensatz mit SQLSTATE 22008 und der Meldung "Teilbereiche wurden abgeschnitten" generiert.  
  
-   **4**: die Datumskomponente wird ignoriert.  
  
-   **5**: die Zeitzone auf die Einstellung des Clients Zeitzone festgelegt ist.  
  
-   **6**: die Zeit auf 0 (null) festgelegt ist.  
  
-   **7**: das Datum wird auf das aktuelle Datum festgelegt.  
  
-   **8**: die Zeit wird von der Zeitzone des Clients in UTC konvertiert. Tritt während dieser Konvertierung ein Fehler auf, wird ein Diagnosedatensatz mit SQLSTATE 22008 und der Meldung "Überlauf im Datetime-Feld" generiert.  
  
-   **9**: die Zeichenfolge analysiert und konvertiert ein Datum, Datetime, Datetimeoffset oder Time-Werten, je nach dem ersten Satzzeichen und dem Vorhandensein weiterer Komponenten. Die Zeichenfolge wird dann in den Zieltyp konvertiert. Dabei wird nach den Regeln in der vorangehenden Tabelle für den Quelltyp vorgegangen, der von diesem Prozess ermittelt wird. Wenn bei der Analyse der Daten ein Fehler ermittelt wird, wird ein Diagnosedatensatz mit SQLSTATE 22018 und der Meldung "Ungültiger Zeichenwert für Konvertierungsangabe" generiert. Wenn die Jahresangabe außerhalb des vom datetime- und smalldatetime-Parameter unterstützten Bereichs liegt, wird ein Diagnosedatensatz mit SQLSTATE 22007 und der Meldung "Ungültiges datetime-Format" generiert.  
  
     Der Wert für datetimeoffset muss nach der Konvertierung in das UTC-Format innerhalb des gültigen Bereichs liegen, und zwar selbst dann, wenn keine Konvertierung in UTC angefordert wird. Der Grund dafür ist, dass der TDS und der Server das Datum stets in datetimeoffset-Werte für UTC normalisieren, weshalb der Client prüfen muss, ob die Zeitkomponenten innerhalb des nach Konvertierung in UTC unterstützten Bereichs liegen. Wenn der Wert nicht innerhalb des unterstützten UTC-Bereichs liegt, wird ein Diagnosedatensatz mit SQLSTATE 22007 und der Meldung "Ungültiges datetime-Format" generiert.  
  
-   **10**: Wenn Kürzung mit Datenverlust auftritt, wird ein Diagnosedatensatz mit SQLSTATE 22008 und der Meldung "Ungültiges Zeitformat" generiert. Dieser Fehler tritt auch dann auf, wenn der Wert außerhalb des Bereichs liegt, der vom UTC-Bereich, den der Server verwendet, dargestellt werden kann.  
  
-   **11**: Wenn die Bytelänge der Daten nicht die Größe der Struktur erforderlich, die vom SQL-Typ entspricht, wird ein Diagnosedatensatz mit SQLSTATE 22003 und der Meldung "Numerischer Wert außerhalb des gültigen Bereichs" generiert.  
  
-   **12**: Wenn die Bytelänge der Daten 4 oder 8 beträgt, ist die Daten an den Server im raw TDS Smalldatetime oder Datetime-Format gesendet. Wenn die Bytelänge der Daten exakt mit der Größe von SQL_TIMESTAMP_STRUCT übereinstimmt, werden die Daten in das TDS-Format für datetime2 konvertiert.  
  
-   **13**: Wenn Kürzung mit Datenverlust auftritt, wird ein Diagnosedatensatz mit SQLSTATE 22001 und der Meldung "Die Zeichenfolgedaten rechts abgeschnitten" generiert.  
  
     Die Anzahl der Dezimalziffern für Sekundenbruchteile (Dezimalstellen) wird anhand der Größe der Zielspalte gemäß der folgenden Tabelle ermittelt:  
  
    ||||  
    |-|-|-|  
    |Typ|Implizierte Dezimalstellen<br /><br /> 0|Implizierte Dezimalstellen<br /><br /> 1..9|  
    |SQL_C_TYPE_TIMESTAMP|19|21..29|  
  
     Wenn die Sekundenbruchteile für SQL_C_TYPE_TIMESTAMP mit drei Ziffern ohne Datenverlust dargestellt werden können und die Spaltengröße 23 oder größer ist, werden genau drei Dezimalstellen für Sekundenbruchteile generiert. Dieses Verhalten stellt die Abwärtskompatibilität für Anwendungen sicher, die mit älteren ODBC-Treibern entwickelt wurden.  
  
     Für Spaltengrößen, die den Bereich in der Tabelle übersteigen, werden 9 Dezimalstellen impliziert. Diese Konvertierung sollte bis zu neun Dezimalstellen für Sekundenbruchteile ermöglichen, das von ODBC zugelassene Maximum.  
  
     Eine Spaltengröße von 0 (null) impliziert unendliche Größe für Zeichentypen mit variabler Länge in ODBC (9 Ziffern, sofern die 3-Ziffern-Regel für SQL_C_TYPE_TIMESTAMP nicht gilt). Die Angabe einer Spaltengröße von 0 (null) mit einem Zeichentyp fester Länge ist ein Fehler.  
  
-   **N/v**: vorhandene [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] und vorherige Verhalten beibehalten wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Datums- / Uhrzeitverbesserungen &#40;ODBC&#41;](../../relational-databases/native-client-odbc-date-time/date-and-time-improvements-odbc.md)  
  
  
