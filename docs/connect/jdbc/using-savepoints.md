---
title: Verwenden von Sicherungspunkten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 3b48eb13-32ef-4fb3-8e95-dbc9468c9a44
caps.latest.revision: 19
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 125c15caac95f152c6f5009b1a794bd0fb625a2c
ms.sourcegitcommit: 2f9cafc1d7a3773a121bdb78a095018c8b7c149f
ms.translationtype: MTE75
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39661862"
---
# <a name="using-savepoints"></a>Verwenden von Sicherungspunkten

[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

Sicherungspunkte bieten einen Mechanismus, um für Abschnitte einer Transaktion einen Rollback auszuführen. In [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] können Sie mit der Anweisung „SAVE TRANSACTION Sicherungspunktname“ einen Sicherungspunkt erstellen. Später können Sie die Anweisung "ROLLBACK TRANSACTION Sicherungspunktname" ausführen, um ein Rollback bis zum Sicherungspunkt auszuführen, anstatt ein Rollback bis zum Beginn der Transaktion auszuführen.

Sicherungspunkte sind vor allem in Situationen hilfreich, in denen das Auftreten von Fehlern unwahrscheinlich ist. Die Verwendung eines Sicherungspunkts, um für einen Teil einer Transaktion im Falle eines seltenen Fehlers einen Rollback auszuführen, kann effizienter sein, als jede Transaktion vor dem Ausführen einer Aktualisierung daraufhin testen zu lassen, ob die Aktualisierung gültig ist. Aktualisierungen und Rollbacks sind kostspielige Operationen. Sicherungspunkte sind also nur dann effektiv, wenn die Wahrscheinlichkeit eines Fehlers gering und die Kosten für die Vorabüberprüfung der Gültigkeit einer Aktualisierung relativ hoch sind.

[!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] unterstützt die Verwendung von Sicherungspunkten über die [setSavepoint](../../connect/jdbc/reference/setsavepoint-method-sqlserverconnection.md)-Methode der [SQLServerConnection](../../connect/jdbc/reference/sqlserverconnection-class.md)-Klasse. Mit der setSavepoint-Methode können Sie in der aktuellen Transaktion einen benannten oder unbenannten Sicherungspunkt erstellen. Die Methode gibt ein [SQLServerSavepoint](../../connect/jdbc/reference/sqlserversavepoint-class.md)-Objekt zurück. In einer Transaktion können mehrere Sicherungspunkte erstellt werden. Um ein Rollback einer Transaktion bis zu einem bestimmten Sicherungspunkt auszuführen, können Sie das SQLServerSavepoint-Objekt an die [rollback-Methode (java.sql.Savepoint)](../../connect/jdbc/reference/rollback-method-java-sql-savepoint.md) übergeben.

Im folgenden Beispiel wird beim Ausführen einer lokalen Transaktion mit zwei getrennten Anweisungen ein Sicherungspunkt im `try`-Block verwendet. Die Anweisungen werden für die Production.ScrapReason-Tabelle in der [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal_md.md)]-Beispieldatenbank ausgeführt. Für den Rollback der zweiten Anweisung wird ein Sicherungspunkt verwendet. Dies führt dazu, dass nur für die erste Anweisung ein Commit in der Datenbank ausgeführt wird.

[!code[JDBC#UsingSavepoints1](../../connect/jdbc/codesnippet/Java/using-savepoints_1.java)]

## <a name="see-also"></a>Weitere Informationen finden Sie unter

[Ausführen von Transaktionen mit dem JDBC-Treiber](../../connect/jdbc/performing-transactions-with-the-jdbc-driver.md)
