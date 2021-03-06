---
title: Artikel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.articles.f1
ms.assetid: 7c743dc6-6c6d-4c92-b711-842e1b0b273e
caps.latest.revision: 31
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 2e1bc1d8da2b6090861d9fdf1bf82bf7df3a7b96
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37156191"
---
# <a name="articles"></a>Artikel
  Auf der Seite **Artikel** können Sie angeben, welche Datenbankobjekte als Artikel in die Veröffentlichung eingeschlossen werden sollen. Wenn Sie ein Datenbankobjekt veröffentlichen, das von mindestens einem weiteren Datenbankobjekt abhängt, müssen Sie alle Objekte veröffentlichen, auf die verwiesen wird. Wenn Sie beispielsweise eine Sicht veröffentlichen, die von einer Tabelle abhängt, muss auch die Tabelle veröffentlicht werden.  
  
 Objekte, die nicht veröffentlicht werden können, sind neben dem Objekt durch ein rotes Symbol gekennzeichnet. Zusätzlich wird im Informationsbereich am unteren Rand der Assistentenseite eine Erläuterung angezeigt. Folgende Objekte können nicht veröffentlicht werden:  
  
-   Verschlüsselte Objekte.  
  
-   Tabellen ohne Primärschlüssel können nicht in Transaktionsveröffentlichungen veröffentlicht werden.  
  
-   Tabellen können nicht gleichzeitig in einer Mergeveröffentlichung und in einer Transaktionsveröffentlichung veröffentlicht werden, für die Abonnements mit verzögertem Update über eine Warteschlange zulässig sind. Weitere Informationen zum Veröffentlichen eines Artikels in mehreren Veröffentlichungen finden Sie im Abschnitt über das „Veröffentlichen von Tabellen in mehreren Veröffentlichungen“ unter [Veröffentlichen von Daten und Datenbankobjekten](publish/publish-data-and-database-objects.md).  
  
## <a name="oracle-publishers"></a>Oracle-Verleger  
 Für Oracle-Verleger gelten zusätzliche Festlegungen:  
  
-   Eine Liste der Objekte, die aus Oracle veröffentlicht werden können, finden Sie unter [Design Considerations and Limitations for Oracle Publishers](non-sql/design-considerations-and-limitations-for-oracle-publishers.md). Objekte, die nicht veröffentlicht werden können, werden nicht angezeigt.  
  
-   Eine Liste der Datentypen, die veröffentlicht werden können, finden Sie unter [Data Type Mapping for Oracle Publishers](non-sql/data-type-mapping-for-oracle-publishers.md). Spalten mit Datentypen, die nicht veröffentlicht werden können, werden nicht angezeigt.  
  
## <a name="column-filters"></a>Spaltenfilter  
 Die Spalten auf dieser Seite können Sie filtern, indem Sie im Bereich **Zu veröffentlichende Objekte** eine Tabelle erweitern und dann nur die erforderlichen Spalten auswählen (Zeilen können auf der Seite **Tabellenzeilen filtern** dieses Assistenten gefiltert werden). Das Filtern von Spalten kann aus verschiedenen Gründen nützlich sein, darunter aus Sicherheitsgründen (um zu vermeiden, dass vertrauliche Daten ungewollt repliziert werden) oder aus Leistungsgründen (um beispielsweise die Replikation großer BLOB-Spalten zu vermeiden). Weitere Informationen zum Filtern von Spalten, einschließlich einer Liste von Spaltentypen, die nicht gefiltert werden können, finden Sie unter [Filtern von veröffentlichten Daten](publish/filter-published-data.md).  
  
## <a name="options"></a>Tastatur  
 Im Bereich **Zu veröffentlichende Objekte** können Sie folgende Schritte ausführen:  
  
-   Anzeigen aller für die Replikation verfügbaren Objekte.  
  
-   Einschließen eines Objektes in eine Veröffentlichung durch Auswählen des Kontrollkästchens neben diesem Objekt.  
  
-   Einschließen aller Objekte eines bestimmten Typs (z. B. einer Tabelle) in die Veröffentlichung durch Aktivieren des Kontrollkästchens neben dem Objekttyp (z. B. **Tabellen**).  
  
-   Erweitern von Tabellenknoten zum Anzeigen der Spalten in der Tabelle.  
  
-   Filtern von Tabellenspalten aus einer Veröffentlichung durch Deaktivieren des Kontrollkästchens neben dieser Spalte.  
  
-   Aufrufen eines Kontextmenüs durch Klicken mit der rechten Maustaste auf ein Objekt.  
  
 **Artikeleigenschaften**  
 Klicken Sie auf **Artikeleigenschaften**, und führen Sie anschließend einen der folgenden Schritte aus:  
  
-   Klicken Sie auf **Eigenschaften des hervorgehobenen \<ObjectType>-Artikels festlegen**, um das Dialogfeld **Artikeleigenschaften - \<ObjectName>** zu starten. Die in diesem Dialogfeld vorgenommenen Änderungen werden nur auf das Objekt angewendet, das im Objektbereich auf der Seite **Artikel** markiert ist.  
  
-   Klicken Sie auf **Eigenschaften aller \<ObjectType>-Artikel** festlegen, um das Dialogfeld **Eigenschaften für alle \<ObjectType>-Artikel** zu starten. Die in diesem Dialogfeld vorgenommenen Änderungen werden auf alle Objekte dieses Typs angewendet, die im Objektbereich auf der Seite **Artikel** vorhanden sind, einschließlich jener Objekte, die noch nicht für die Veröffentlichung ausgewählt wurden.  
  
    > [!NOTE]  
    >  Durch die Änderungen im Dialogfeld **Eigenschaften für alle \<ObjectType>-Artikel** werden alle zuvor im Dialogfeld **Artikeleigenschaften - \<ObjectName>** vorgenommenen Änderungen überschrieben. Wenn Sie beispielsweise sowohl mehrere Standardwerte für alle Artikel eines Objekttyps als auch bestimmte Eigenschaften für einzelne Objekte festlegen möchten, legen Sie zuerst die Standardwerte für alle Artikel fest. Legen Sie anschließend die Eigenschaften für die einzelnen Objekte fest.  
  
 **Die durch Hervorhebung markierte Tabelle ist nur herunterladbar**  
 Nur für Mergereplikationen zulässig. Nur in[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] und höheren Versionen. Durch Auswahl dieser Option geben Sie an, dass bei Verwendung eines Clientabonnements keine Änderungen auf dem Abonnenten zulässig sind. Da nur herunterladbare Artikel nicht auf dem Abonnenten aktualisiert werden können, wird das Nachverfolgen von Metadaten nicht an die Abonnenten gesendet. Das kann den Speicher auf den Abonnenten entlasten und zu einer höheren Leistung führen, besonders bei einer langsamen Netzwerkverbindung. Diese Option entspricht dem Wert **Nur herunterladbar auf Abonnenten, Abonnentenänderungen nicht zulassen** für die Option **Synchronisierungsrichtung** im Dialogfeld **Artikeleigenschaften** . Weitere Informationen finden Sie unter [Optimieren der Leistung der Mergereplikation durch nur herunterladbare Artikel](merge/optimize-merge-replication-performance-with-download-only-articles.md).  
  
 **Nur in der Liste aktivierte Objekte anzeigen**  
 Aktivieren Sie dieses Kontrollkästchen, um nur die im Objektbereich ausgewählten Artikel anzuzeigen.  
  
## <a name="see-also"></a>Siehe auch  
 [Veröffentlichen von Daten und Datenbankobjekten](publish/publish-data-and-database-objects.md)   
 [Erstellen einer Veröffentlichung](publish/create-a-publication.md)   
 [Anzeigen und Ändern von Veröffentlichungseigenschaften](publish/view-and-modify-publication-properties.md)  
  
  
