---
title: Festlegen von Konvertierung und Migrationsoptionen (AccessToSQL) | Microsoft-Dokumentation
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
helpviewer_keywords:
- conversion, setting options
- migration options
- modes
- options, conversion settings
- project settings
- schemas
ms.assetid: 0a7304df-2f35-4453-96ef-7ac83dea1167
caps.latest.revision: 20
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.openlocfilehash: 21cbf6f3a5dac0b77669b940bf27be26198a4456
ms.sourcegitcommit: 79d4dc820767f7836720ce26a61097ba5a5f23f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2018
ms.locfileid: "40396530"
---
# <a name="setting-conversion-and-migration-options-accesstosql"></a>Festlegen von Konvertierung und Migrationsoptionen (AccessToSQL)
Für jedes Projekt SSMA können Sie Projekt auf Dokumentebene-Optionen festlegen. Diese Optionen angeben, wie Objekte konvertiert werden, wie Daten migriert werden und Zuordnung von Datentypen für die Quelle, Ziel-Datentypen. Bevor Sie Objekte konvertieren [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oder SQL Azure oder Migrieren von Daten in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oder SQL Azure, stellen Sie sicher, dass die Konfigurationsoptionen für das Projekt geeignet sind.  
  
## <a name="configuration-options-and-modes"></a>Optionen für die Konfiguration und -Modi  
SSMA verfügt über vier Sätze von Konfigurationseinstellungen und vier Modi zum Konfigurieren dieser Einstellungen: Standard, Optimistic, vollständig und Benutzerdefiniert. Der Standardmodus ist für die meisten Benutzer empfohlen. Verwenden Sie den vollständigen Modus für einfache Konvertierungen. Verwenden Sie den vollständigen Modus, wenn alle Nachrichten angezeigt werden sollen. In den benutzerdefinierten Modus legen Sie die Optionen an.  
  
Die Einstellungen werden im Abschnitt "Referenz zur Benutzeroberfläche" in dieser Dokumentation beschrieben. Weitere Informationen über die Einstellungen und wie die Einstellungen in den einzelnen Modi angewendet werden finden Sie unter den folgenden Themen:  
  
-   [Project Settings (Conversion) (Projekteinstellungen (Konvertierung)](http://msdn.microsoft.com/bcebc635-c638-4ddb-924c-b9ccfef86388)  
  
-   [Project Settings (Migration) (Projekteinstellungen (Migration))](http://msdn.microsoft.com/4caebc9c-8680-4b99-a8fa-89c43161c95d)  
  
-   [Project Settings (GUI) (Projekteinstellungen (GUI))](http://msdn.microsoft.com/cf06baf1-8714-48a3-95dc-781f6ca53693)  
  
-   [Project Settings (Type Mapping) (Projekteinstellungen (Typzuordnung))](http://msdn.microsoft.com/b87b9683-abed-4677-8c50-18bdba704655)  
  
-   [Project Settings (SQL Azure)](http://msdn.microsoft.com/bbb8a204-d0e4-4f0b-9709-271feb1f136e)  
  
## <a name="setting-project-options"></a>Festlegen von Projektoptionen  
In SSMA können Sie die Standardeinstellungen für alle Projekte konfigurieren. Diese Einstellungen sind in der SSMA-Konfigurationsdatei gespeichert und angewendet werden, um neue Projekte, die Sie erstellen.  
  
**Projektoptionen festlegen**  
  
1.  Auf der **Tools** , wählen Sie im Menü **Projekt Standardeinstellungen**.  
  
2.  In der **Projekt Standardeinstellungen** (Dialogfeld), führen Sie einen der folgenden:  
  
    -   Wählen Sie die Migration-Projekttyp, die für die Einstellungen erforderlich sind, angezeigt oder geändert werden, **Migration Zielversion** Dropdown-Liste, klicken Sie auf **allgemeine** am unteren Rand der linken Seite, und wählen **Konvertierung oder Migration oder SQL Azure**.  
  
        > [!NOTE]  
        > SQL Azure-Option steht in der **allgemeine** Registerkarte nur, wenn der Projekttyp erstellt SQL Azure ist.  
  
    -   Wählen Sie zum Auswählen eines vordefinierten Modus **Standard**, **Optimistic**, oder **vollständige** in die **Modus** Dropdown-Listenfeld.  
  
    -   Wählen Sie zum Angeben eines benutzerdefinierten Modus **benutzerdefinierte** in die **Modus** wählen Sie eine Option im linken Bereich, klicken Sie auf die Einstellung oder einen Wert im rechten Bereich, und klicken Sie dann wählen oder geben Sie die neue Einstellung oder einen Wert.  
  
3.  Klicken Sie auf **OK** zum Speichern der Einstellungen.  
  
Sie können auch Einstellungen für das aktuelle Projekt anpassen. Diese Einstellungen werden in der aktuellen Projektdatei gespeichert.  
  
**Anpassen der Einstellungen für das aktuelle Projekt**  
  
1.  Auf der **Tools** , wählen Sie im Menü **Projekteinstellungen**.  
  
2.  In der **Projekteinstellungen** (Dialogfeld), führen Sie einen der folgenden:  
  
    -   Wählen Sie zum Auswählen eines vordefinierten Modus **Standard**, **Optimistic**, oder **vollständige** in die **Modus** Dropdown-Listenfeld.  
  
    -   Wählen Sie zum Angeben eines benutzerdefinierten Modus **benutzerdefinierte** in die **Modus** wählen Sie eine Option im linken Bereich, klicken Sie auf die Einstellung oder einen Wert im rechten Bereich, und klicken Sie dann wählen oder geben Sie die neue Einstellung oder einen Wert.  
  
3.  Klicken Sie auf **OK** zum Speichern der Einstellungen.  
  
## <a name="next-steps"></a>Nächste Schritte  
Der nächste Schritt bei der Migration hängt von den Anforderungen Ihrer Projekte:  
  
-   Wenn die Zuordnung von Datentypen für Quell- und zieleinstellungen anpassen möchten, finden Sie unter [Zuordnung-Quelle und Ziel-Datentypen](mapping-source-and-target-data-types-accesstosql.md)  
  
-   Wenn die Zuordnung der Quell-und Zieldatenbanken anpassen möchten, finden Sie unter [Zuordnung Quell- und Zieldatenbank](mapping-source-and-target-databases-accesstosql.md)  
  
-   Andernfalls können Sie die Access-Datenbank-Objektdefinitionen in konvertieren [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oder SQL Azure-Objektdefinitionen. Weitere Informationen finden Sie unter [den Zugriff auf Datenbankobjekte konvertieren](converting-access-database-objects-accesstosql.md)  
  
## <a name="see-also"></a>Siehe auch  
[Migrieren von Access-Datenbanken zu SQLServer](migrating-access-databases-to-sql-server-azure-sql-db-accesstosql.md)  
  
