---
title: Beispiel zum Lesen umfangreicher Daten mit gespeicherten Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 07/31/2018
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 58c76635-a117-4661-8781-d6cb231c5809
caps.latest.revision: 27
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: f02c6f338ed7901813abd13b68bec97cf0e31645
ms.sourcegitcommit: e02c28b0b59531bb2e4f361d7f4950b21904fb74
ms.translationtype: MTE75
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39453044"
---
# <a name="reading-large-data-with-stored-procedures-sample"></a>Beispiel zum Lesen umfangreicher Daten mit gespeicherten Prozeduren

[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

In dieser Beispielanwendung für [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] wird das Abrufen eines großen OUT-Parameters aus einer gespeicherten Prozedur veranschaulicht.

Die Codedatei für dieses Beispiel heißt „ExecuteStoredProcedure.java“ und befindet sich unter folgendem Pfad:

```bash
\<installation directory>\sqljdbc_<version>\<language>\samples\adaptive
```

## <a name="requirements"></a>Anforderungen

Zum Ausführen dieser Beispielanwendung benötigen Sie Zugriff auf die [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal_md.md)]-Beispieldatenbank. Nehmen Sie außerdem die Datei „mssql-jdbc.jar“ in den Klassenpfad auf. Weitere Informationen zum Festlegen des Klassenpfads finden Sie unter [mit dem JDBC-Treiber](../../../connect/jdbc/using-the-jdbc-driver.md).

> [!NOTE]  
> Der [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] enthält die Klassenbibliotheksdateien „mssql-jdbc“ für die jeweilige Verwendung mit Ihren bevorzugten JRE-Einstellungen (Java Runtime Environment). Weitere Informationen zu der JAR-Datei auswählen, finden Sie unter [Systemanforderungen für JDBC Driver](../../../connect/jdbc/system-requirements-for-the-jdbc-driver.md).

Erstellen Sie die folgende gespeicherte Prozedur in der [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal_md.md)]-Beispieldatenbank:

```sql
CREATE PROCEDURE GetLargeDataValue
  (@Document_ID int,
   @Document_ID_out int OUTPUT,
   @Document_Title varchar(50) OUTPUT,  
   @Document_Summary nvarchar(max) OUTPUT)  

AS
BEGIN
   SELECT @Document_ID_out = DocumentID,
          @Document_Title = Title,  
          @Document_Summary = DocumentSummary
    FROM  Production.Document  
    WHERE DocumentID = @Document_ID  
END  
```

## <a name="example"></a>Beispiel

Im folgenden Beispielcode wird eine Verbindung mit der [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal_md.md)]-Datenbank hergestellt. Im Beispielcode werden anschließend Beispieldaten erstellt, und die Tabelle Production.Document wird mithilfe einer parametrisierten Abfrage aktualisiert. Dann wird der Modus für die adaptive Pufferung mithilfe der Methode [getResponseBuffering](../../../connect/jdbc/reference/getresponsebuffering-method-sqlserverstatement.md) der Klasse [SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md) abgerufen und die gespeicherte Prozedur „GetLargeDataValue“ wird ausgeführt. Beachten Sie, dass ab Version 2.0 des JDBC-Treibers die responseBuffering-Verbindungseigenschaft standardmäßig auf "adaptive" festgelegt ist.

Schließlich zeigt der Beispielcode die mit den OUT-Parametern zurückgegebenen Daten an. Darüber hinaus wird die Verwendung der Methoden `mark` und `reset` im Datenstrom zum erneuten Lesen eines beliebigen Teils der Daten veranschaulicht.

[!code[JDBC#UsingAdaptiveBuffering2](../../../connect/jdbc/codesnippet/Java/reading-large-data-with-_1_1.java)]

## <a name="see-also"></a>Weitere Informationen finden Sie unter

[Arbeiten mit umfangreichen Daten](../../../connect/jdbc/code-samples/working-with-large-data.md)
