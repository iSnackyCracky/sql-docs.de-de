---
title: Quellen-Editor (Verbindungsseite) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- Sql12.dts.designer.odatasource.connection.f1
ms.assetid: 20bcd347-4547-4fad-b182-9571030101df
caps.latest.revision: 6
author: douglaslms
ms.author: douglasl
manager: craigg
ms.openlocfilehash: f3ae477a34a296ade90fb50dde0a600cf81ac18a
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37213270"
---
# <a name="odata-source-editor-connection-page"></a>Quellen-Editor für OData (Seite 'Verbindung')
  Auf der Seite **Verbindung** des Dialogfelds **Quellen-Editor für OData** wählen Sie den OData-Verbindungs-Manager für die OData-Quelle aus. Auf dieser Seite können Sie außerdem eine Auflistung oder einen Ressourcenpfad sowie beliebige Abfrageoptionen angeben, mit denen die aus der OData-Quelle abzurufenden Daten bestimmt werden. Weitere Informationen zur OData-Quelle finden Sie unter [OData Source](data-flow/odata-source.md).  
  
## <a name="static-options"></a>Statische Optionen  
 **OData-Verbindungs-Manager**  
 Wählen Sie in der Liste einen vorhandenen Verbindungs-Manager aus, oder erstellen Sie eine neue Verbindung, indem Sie auf **Neu**klicken.  
  
 **Neu**  
 Erstellen Sie mithilfe des Dialogfelds **OData-Verbindungs-Manager-Editor** einen neuen Verbindungs-Manager.  
  
 **Auflistung oder Ressourcenpfad verwenden**  
 Geben Sie die Methode für die Auswahl von Daten aus der Quelle an.  
  
|Option|Description|  
|------------|-----------------|  
|Auflistung|Rufen Sie mithilfe eines Auflistungsnamens Daten aus der OData-Quelle ab.|  
|Ressourcenpfad|Rufen Sie mithilfe eines Ressourcenpfads Daten aus der OData-Quelle ab.|  
  
 **Abfrageoptionen**  
 Geben Sie Optionen für die Abfrage an.  Beispiel: $top=5  
  
 **Feed-URL**  
 Zeigt die schreibgeschützte Feed-URL auf Grundlage der Optionen an, die Sie in diesem Dialogfeld ausgewählt haben.  
  
 **Vorschau**  
 Zeigt mithilfe des Dialogfelds **Vorschau** eine Vorschau der Ergebnisse an. In der**Vorschau** können bis zu 20 Zeilen angezeigt werden.  
  
## <a name="dynamic-options"></a>Dynamische Optionen  
  
### <a name="use-collection-or-resource-path--collection"></a>Auflistung oder Ressourcenpfad verwenden = Auflistung  
 **Auflistung**  
 Wählen Sie eine Auflistung aus dem Dropdownlistenfeld aus.  
  
### <a name="use-collection-or-resource-path--resource-path"></a>Auflistung oder Ressourcenpfad verwenden = Ressourcenpfad  
 **Resource path**  
 Geben Sie einen Ressourcenpfad ein. Beispiel: Mitarbeiter  
  
## <a name="see-also"></a>Siehe auch  
 [Quellen-Editor für OData &#40;Seite "Spalten"&#41;](../../2014/integration-services/odata-source-editor-columns-page.md)   
 [Quellen-Editor für OData &#40;Seite "Fehlerausgabe"&#41;](../../2014/integration-services/odata-source-editor-error-output-page.md)   
 [OData-Verbindungs-Manager](connection-manager/odata-connection-manager.md)  
  
  
