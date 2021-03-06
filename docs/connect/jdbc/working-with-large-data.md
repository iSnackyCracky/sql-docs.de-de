---
title: Arbeiten mit großen Datenmengen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 5b93569f-eceb-4f05-b49c-067564cd3c85
caps.latest.revision: 24
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: a60bc049b02ca998119fd4741fa51589a029aeca
ms.sourcegitcommit: e02c28b0b59531bb2e4f361d7f4950b21904fb74
ms.translationtype: MTE75
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39452294"
---
# <a name="working-with-large-data"></a>Arbeiten mit umfangreichen Daten

[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

Der JDBC-Treiber bietet Unterstützung für die adaptive Pufferung, mit der Sie beliebige Daten mit umfangreichen Werten ohne den Aufwand von Servercursorn abrufen können. Mithilfe der adaptiven Pufferung ruft der [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] Ergebnisse der Anweisungsausführung erst dann aus [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] ab, wenn sie in der Anwendung benötigt werden, statt alle Ergebnisse auf einmal abzurufen. Der Treiber verwirft außerdem die Ergebnisse, sobald die Anwendung nicht mehr auf sie zugreifen kann.

In der JDBC-Treiberversion 1.2 für [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005_md.md)] war der Puffermodus standardmäßig auf **full** festgelegt. Wenn die responseBuffering-Verbindungseigenschaft in der Anwendung nicht auf **adaptive** festgelegt war – entweder in den Verbindungseigenschaften oder mit der [setResponseBuffering](../../connect/jdbc/reference/setresponsebuffering-method-sqlserverstatement.md)-Methode des [SQLServerStatement](../../connect/jdbc/reference/sqlserverstatement-class.md)-Objekts –, unterstützte der Treiber das Lesen des gesamten Resultsets vom Server in einem einzigen Vorgang. Um ein adaptives Pufferungsverhalten zu erzielen, musste die responseBuffering-Verbindungseigenschaft in der Anwendung explizit auf **adaptive** festgelegt werden.  
  
Der **adaptive**-Wert ist der Standardpuffermodus, und der JDBC-Treiber puffert nach Bedarf so wenig Daten wie möglich. Weitere Informationen zum Verwenden der adaptiven Pufferung finden Sie unter [Using Adaptive Buffering](../../connect/jdbc/using-adaptive-buffering.md).  
  
 Die Themen in diesem Abschnitt beschreiben verschiedene Möglichkeiten, wie Sie Daten mit einer großen Menge an Werten aus einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]-Datenbank abrufen können.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
| Thema                                                                                                                      | und Beschreibung                                                              |
| -------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| [Beispiel zum Lesen umfangreicher Daten](../../connect/jdbc/reading-large-data-sample.md)                                               | Beschreibt die Verwendung einer SQL-Anweisung zum Abrufen von Daten mit umfangreichen Werten.       |
| [Beispiel zum Lesen umfangreicher Daten mit gespeicherten Prozeduren](../../connect/jdbc/reading-large-data-with-stored-procedures-sample.md) | Beschreibt das Abrufen eines umfangreichen CallableStatement OUT-Parameterwerts. |
| [Beispiel zum Aktualisieren umfangreicher Daten](../../connect/jdbc/updating-large-data-sample.md)                                             | Beschreibt das Aktualisieren von Daten mit umfangreichen Werten in einer Datenbank.                |
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter

[Beispiele für JDBC-Treiberanwendungen](../../connect/jdbc/sample-jdbc-driver-applications.md)  
