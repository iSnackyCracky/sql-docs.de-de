---
title: Funktionen (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- functions [Integration Services]
- expressions [Integration Services], functions
- string functions
- SQL Server Integration Services, functions
- SSIS, functions
ms.assetid: e9a41a31-94f4-46a4-b737-c707dd59ce48
caps.latest.revision: 35
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 5b67a495d92d0bfc59288533d5f7c21e0f86d645
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37171031"
---
# <a name="functions-ssis-expression"></a>Funktionen (SSIS-Ausdruck)
  Die Ausdruckssprache schließt Funktionen für die Verwendung in Ausdrücken ein. In einem Ausdruck kann eine einzelne Funktion verwendet werden. Normalerweise werden in einem Ausdruck Funktionen mit Operatoren kombiniert und mehrere Funktionen verwendet.  
  
 Die Funktionen können in die folgenden Gruppen eingeteilt werden:  
  
-   Mathematische Funktionen, die Berechnungen auf der Basis von numerischen Eingabewerten ausführen, die als Parameter für die Funktion bereitgestellt werden. Sie geben numerische Werte zurück.  
  
-   Zeichenfolgenfunktionen, die Operationen für Zeichenfolgen-Eingabewerte und hexadezimale Eingabewerte ausführen und eine Zeichenfolge oder einen numerischen Wert zurückgeben.  
  
-   Datums- und Zeitfunktionen, die Operationen für Datums- und Zeitwerte ausführen und Zeichenfolgen-, Datums- Zeit- oder numerische Werte zurückgeben.  
  
-   Systemfunktionen, die Informationen zu einem Ausdruck zurückgeben.  
  
 Die Ausdruckssprache stellt die folgenden mathematischen Funktionen bereit.  
  
|Funktion|Description|  
|--------------|-----------------|  
|[ABS &#40;SSIS-Ausdruck&#41;](abs-ssis-expression.md)|Gibt den absoluten, positiven Wert eines numerischen Ausdrucks zurück.|  
|["Exp" &#40;SSIS-Ausdruck&#41;](exp-ssis-expression.md)|Gibt den Exponenten für die Basis e des angegebenen Ausdrucks zurück.|  
|[CEILING- &#40;SSIS-Ausdruck&#41;](ceiling-ssis-expression.md)|Gibt die kleinste ganze Zahl zurück, die größer oder gleich einem numerischen Ausdruck ist.|  
|[FLOOR &#40;SSIS-Ausdruck&#41;](floor-ssis-expression.md)|Gibt die größte ganze Zahl zurück, die kleiner oder gleich einem numerischen Ausdruck ist.|  
|[LN &#40;SSIS-Ausdruck&#41;](ln-ssis-expression.md)|Gibt den natürlichen Logarithmus eines numerischen Ausdrucks zurück.|  
|[LOG &#40;SSIS-Ausdruck&#41;](log-ssis-expression.md)|Gibt den Logarithmus eines numerischen Ausdrucks zur Basis 10 zurück.|  
|[POWER &#40;SSIS-Ausdruck&#41;](power-ssis-expression.md)|Gibt das Ergebnis eines in eine Potenz erhobenen numerischen Ausdrucks zurück.|  
|[ROUND &#40;SSIS-Ausdruck&#41;](round-ssis-expression.md)|Gibt einen numerischen Ausdruck zurück, der auf die angegebene Länge oder Genauigkeit gerundet wurde. zugreifen.|  
|[Anmeldung &#40;SSIS-Ausdruck&#41;](sign-ssis-expression.md)|Gibt das positive (+) oder negative (-) Vorzeichen oder Null (0) für einen numerischen Ausdruck zurück.|  
|[QUADRAT &#40;SSIS-Ausdruck&#41;](square-ssis-expression.md)|Gibt das Quadrat eines numerischen Ausdrucks zurück.|  
|["SQRT" &#40;SSIS-Ausdruck&#41;](sqrt-ssis-expression.md)|Gibt die Quadratwurzel eines numerischen Ausdrucks zurück.|  
  
 Die Ausdrucksauswertung stellt die folgenden Zeichenfolgenfunktionen bereit.  
  
|Funktion|Description|  
|--------------|-----------------|  
|[CODEPOINT &#40;SSIS-Ausdruck&#41;](codepoint-ssis-expression.md)|Gibt den Unicode-Codewert des äußeren linken Zeichens eines Zeichenausdrucks zurück.|  
|[FINDSTRING &#40;SSIS-Ausdruck&#41;](findstring-ssis-expression.md)|Gibt den einsbasierten Index für das angegebene Auftreten einer Zeichenfolge innerhalb eines Ausdrucks zurück.|  
|[HEX &#40;SSIS-Ausdruck&#41;](hex-ssis-expression.md)|Gibt eine Zeichenfolge zurück, die den hexadezimalen Wert einer ganzen Zahl darstellt.|  
|[LEN &#40;SSIS-Ausdruck&#41;](len-ssis-expression.md)|Gibt die Anzahl von Zeichen in einem Zeichenausdruck zurück.|  
|[Links &#40;SSIS-Ausdruck&#41;](left-ssis-expression.md)|Gibt die angegebene Anzahl von Zeichen ab der äußersten linken Position des angegebenen Zeichenausdrucks zurück.|  
|[NIEDRIGERE &#40;SSIS-Ausdruck&#41;](lower-ssis-expression.md)|Gibt einen Zeichenausdruck zurück, nachdem Großbuchstaben in Kleinbuchstaben konvertiert wurden.|  
|[LTRIM &#40;SSIS-Ausdruck&#41;](trim-ssis-expression.md)|Gibt einen Zeichenausdruck zurück, nachdem führende Leerzeichen entfernt wurden.|  
|[Ersetzen Sie dies &#40;SSIS-Ausdruck&#41;](replace-ssis-expression.md)|Gibt einen Zeichenausdruck zurück, nachdem eine Zeichenfolge im Ausdruck durch eine andere Zeichenfolge oder durch eine leere Zeichenfolge ersetzt wurde.|  
|[Replizieren von &#40;SSIS-Ausdruck&#41;](replicate-ssis-expression.md)|Gibt einen Zeichenausdruck zurück, der mehrfach repliziert wurde.|  
|[REVERSE- &#40;SSIS-Ausdruck&#41;](reverse-ssis-expression.md)|Gibt einen Zeichenausdruck in umgekehrter Reihenfolge zurück.|  
|[RECHTS &#40;SSIS-Ausdruck&#41;](right-ssis-expression.md)|Gibt die angegebene Anzahl von Zeichen ab der äußersten rechten Position des angegebenen Zeichenausdrucks zurück.|  
|[RTRIM &#40;SSIS-Ausdruck&#41;](rtrim-ssis-expression.md)|Gibt einen Zeichenausdruck zurück, nachdem nachfolgende Leerzeichen entfernt wurden.|  
|[TEILZEICHENFOLGE &#40;SSIS-Ausdruck&#41;](substring-ssis-expression.md)|Gibt einen Teil eines Zeichenausdrucks zurück.|  
|[TRIM &#40;SSIS-Ausdruck&#41;](trim-ssis-expression.md)|Gibt einen Zeichenausdruck zurück, nachdem führende und nachfolgende Leerzeichen entfernt wurden.|  
|[OBERE &#40;SSIS-Ausdruck&#41;](upper-ssis-expression.md)|Gibt einen Zeichenausdruck zurück, nachdem Kleinbuchstaben in Großbuchstaben konvertiert wurden.|  
  
 Die Ausdrucksauswertung stellt die folgenden Datums- und Zeitfunktionen bereit.  
  
|Funktion|Description|  
|--------------|-----------------|  
|[DATEADD &#40;SSIS-Ausdruck&#41;](dateadd-ssis-expression.md)|Gibt einen neuen DT_DBTIMESTAMP-Wert zurück, indem ein Datums- oder Zeitintervall einem angegebenen Datum hinzugefügt wird.|  
|[DATEDIFF &#40;SSIS-Ausdruck&#41;](datediff-ssis-expression.md)|Gibt die Anzahl von Datums- und Zeiteinheiten zurück, die zwischen zwei angegebenen Daten überschritten wurden.|  
|[DATEPART &#40;SSIS-Ausdruck&#41;](datepart-ssis-expression.md)|Gibt eine ganze Zahl zurück, die einen datepart-Wert eines Datums darstellt.|  
|[Tag &#40;SSIS-Ausdruck&#41;](day-ssis-expression.md)|Gibt eine ganze Zahl zurück, die den Tag des angegebenen Datums darstellt.|  
|[GETDATE &#40;SSIS-Ausdruck&#41;](getdate-ssis-expression.md)|Gibt das aktuelle Datum des Systems zurück.|  
|[GETUTCDATE &#40;SSIS-Ausdruck&#41;](getutcdate-ssis-expression.md)|Gibt das aktuelle Datum des Systems als UTC-Zeit (Universal Time Coordinate oder Greenwich Mean Time) zurück.|  
|[Monat &#40;SSIS-Ausdruck&#41;](month-ssis-expression.md)|Gibt eine ganze Zahl zurück, die den Monat des angegebenen Datums darstellt.|  
|[Jahr &#40;SSIS-Ausdruck&#41;](year-ssis-expression.md)|Gibt eine ganze Zahl zurück, die das Jahr des angegebenen Datums darstellt.|  
  
 Die Ausdrucksauswertung stellt die folgenden NULL-Funktionen bereit.  
  
|Funktion|Description|  
|--------------|-----------------|  
|[ISNULL &#40;SSIS-Ausdruck&#41;](null-ssis-expression.md)|Gibt abhängig davon, ob ein Ausdruck NULL ist, ein boolesches Ergebnis zurück.|  
|[NULL &#40;SSIS-Ausdruck&#41;](null-ssis-expression.md)|Gibt einen NULL-Wert eines angeforderten Datentyps zurück.|  
  
 Ausdrucksnamen werden in Großbuchstaben dargestellt, aber bei Ausdrucksnamen wird nicht nach Groß-/Kleinschreibung unterschieden. Beispielsweise spielt es keine Rolle, ob Sie "null" oder "NULL" verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Operatoren &#40;SSIS-Ausdruck&#41;](operators-ssis-expression.md)   
 [Beispiele für erweiterte SQL Server Integration Services-Ausdrücke](examples-of-advanced-integration-services-expressions.md)   
 [Integration Services-Ausdrücke &#40;SSIS&#41;](integration-services-ssis-expressions.md)  
  
  
