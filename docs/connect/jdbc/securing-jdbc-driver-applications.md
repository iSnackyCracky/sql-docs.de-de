---
title: Sichern von JDBC-Treiberanwendungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 90724ec6-a9cb-43ef-903e-793f89410bc0
caps.latest.revision: 19
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 15ac2b868066efcf978fc92d17b381e08ce2932d
ms.sourcegitcommit: e02c28b0b59531bb2e4f361d7f4950b21904fb74
ms.translationtype: MTE75
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39454924"
---
# <a name="securing-jdbc-driver-applications"></a>Sichern von JDBC-Treiberanwendungen

[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

Das Verbessern der Sicherheit einer [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)]-Anwendung beschränkt sich nicht allein auf das Vermeiden der häufigsten Programmierfehler. Eine Anwendung, die auf Daten zugreift, weist eine Vielzahl von möglichen Fehlern auf, die Angreifer ausnutzen können, um vertrauliche Daten abzurufen, zu ändern oder zu beschädigen. Es ist daher wichtig, alle Aspekte der Sicherheit zu kennen, von der Bedrohungsmodellierung während der Entwurfsphase der Anwendung bis zur endgültigen Bereitstellung und weiter bei der laufenden Wartung.  
  
In den Themen in diesem Abschnitt werden einige häufige Sicherheitsrisiken beschrieben, unter anderem Verbindungszeichenfolgen, das Überprüfen von Benutzereingaben und allgemeine Anwendungssicherheit.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
| Thema                                                                            | und Beschreibung                                                                                                                                                           |
| -------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Sichern von Verbindungszeichenfolgen](../../connect/jdbc/securing-connection-strings.md) | Beschreibt Verfahren zum Schützen von Informationen, mit denen eine Verbindung mit einer Datenquelle hergestellt wird.                                                                                    |
| [Überprüfen der Benutzereingabe](../../connect/jdbc/validating-user-input.md)             | Beschreibt Verfahren zum Überprüfen von Benutzereingaben.                                                                                                                          |
| [Anwendungssicherheit](../../connect/jdbc/application-security.md)               | Beschreibt die Verwendung von Java-Richtlinienberechtigungen zum Sichern einer JDBC-Treiberanwendung.                                                                                |
| [Verwenden der SSL-Verschlüsselung](../../connect/jdbc/using-ssl-encryption.md)               | Beschreibt das Herstellen eines sicheren Kommunikationskanals mit einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]-Datenbank mithilfe von Secure Sockets Layer (SSL). |
| [FIPS-Modus](../../connect/jdbc/fips-mode.md)                                     | Beschreibt, wie Sie JDBC-Treiber in FIPS-kompatiblen Modus zu verwenden.                                                                                                              |
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  

 [Overview of the JDBC Driver (Übersicht über den JDBC-Treiber)](../../connect/jdbc/overview-of-the-jdbc-driver.md)  
