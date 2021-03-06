---
title: Konfigurieren eines Servers für das Ausführen der Richtlinie „Standardmäßig aus“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 41c3022d-ab13-443e-ac64-ba1d64584f79
caps.latest.revision: 22
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 1aa6dfabe09541fd60809c337b296cb417ffd1b5
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37211010"
---
# <a name="configure-a-server-to-run-the-off-by-default-policy"></a>Konfigurieren eines Servers für das Ausführen der Richtlinie 'Standardmäßig aus'
  Nun verfügen Sie über eine Richtlinie mit dem Namen Standardmäßig aus. In dieser Aufgabe überprüfen Sie, ob Ihr Server die Anforderungen dieser Richtlinie einhält.  
  
### <a name="to-run-the-off-by-default-policy"></a>So führen Sie die Richtlinie 'Standardmäßig aus' aus  
  
1.  Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf Ihre Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], zeigen Sie auf **Richtlinien**, und klicken Sie anschließend auf **Auswerten**.  
  
2.  Im Dialogfeld **Richtlinien auswerten** können Sie Richtlinien aus einer anderen Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oder aus einer Datei auswählen. Für diesen Schritt belassen Sie als Einstellung für **Quelle** Ihre Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)].  
  
3.  Wählen Sie im Abschnitt **Richtlinien** die Richtlinie **Standardmäßig aus** aus.  
  
4.  Um zu sehen, ob der Server diese Richtlinie einhält, klicken Sie auf **Auswerten**.  
  
5.  Im Bereich **Ergebnisse** wird ein grüner Kreis mit einem Häkchen angezeigt, wenn [!INCLUDE[ssDE](../../includes/ssde-md.md)] die Richtlinie einhält. Ein roter Kreis mit einem X wird angezeigt, wenn [!INCLUDE[ssDE](../../includes/ssde-md.md)] die Richtlinie nicht einhält.  
  
6.  Im Bereich **Zieldetails** werden weitere Informationen in der Spalte **Meldung** angezeigt, wenn ein Fehler auftritt. Klicken Sie in der Spalte **Meldung** auf **Anzeigen** , um einen Bericht anzuzeigen, der die Überprüfungsergebnisse für jede überprüfte Facet-Eigenschaft enthält.  
  
7.  Die Richtlinienbeschreibung wird unten auf der Seite angezeigt, und im Abschnitt **Zusätzliche Hilfe** wird der Link angezeigt, den Sie für die Richtlinie konfiguriert haben. Klicken Sie auf den Meldungslink, um die Webseite zu öffnen, die Sie beim Erstellen der Richtlinie angegeben haben.  
  
8.  Schließen Sie den Browser, und schließen Sie dann das Dialogfeld **Ergebnisse, Detailansicht** .  
  
9. Wenn der Server die Richtlinie nicht einhält und Sie Datenbank-E-Mail deaktivieren möchten, klicken Sie auf der Seite **Auswertungsergebnisse** auf **Anwenden** .  
  
10. Schließen Sie das Dialogfeld **Ergebnisse, Detailansicht** und das Dialogfeld **Richtlinien auswerten** .  
  
## <a name="next-lesson"></a>Nächste Lektion  
 [Lektion 2: Erstellen und Anwenden einer Richtlinie für Benennungsstandards](lesson-2-create-and-apply-a-naming-standards-policy.md)  
  
  
