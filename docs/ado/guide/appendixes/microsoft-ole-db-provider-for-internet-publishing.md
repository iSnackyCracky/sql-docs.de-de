---
title: Microsoft OLE DB-Anbieter für Internet Publishing | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- OLE DB provider for Internet publishing [ADO]
- providers [ADO], OLE DB provider for Internet publishing
- Internet Publishing provider [ADO]
ms.assetid: 66a208d9-b580-4655-a41e-1d36e5b5bfca
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: c8d3caac3bd857b790372bd6b41fc818090210a0
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "35271219"
---
# <a name="microsoft-ole-db-provider-for-internet-publishing-overview"></a>Microsoft OLE DB-Anbieter für Internet Publishing (Übersicht)
Microsoft OLE DB-Anbieter für Internet Publishing ermöglicht ADO den Zugriff auf Ressourcen, die von Microsoft FrontPage oder Microsoft Internet Information Server bedient. Ressourcen gehören Web-Quelldateien, z. B. HTML-Dateien oder Ordner für Windows 2000-Webserver.

## <a name="connection-string-parameters"></a>Parameter für Verbindungszeichenfolgen
 Zur Verbindung mit diesem Anbieter Festlegen der *Anbieter* Argument der ["ConnectionString"](../../../ado/reference/ado-api/connectionstring-property-ado.md) Eigenschaft:

```
MSDAIPP.DSO
```

 Dieser Wert kann auch festlegen oder lesen, mit der [Anbieter](../../../ado/reference/ado-api/provider-property-ado.md) Eigenschaft.

## <a name="typical-connection-string"></a>Typische Verbindungszeichenfolge
 Eine typische Verbindungszeichenfolge für diesen Anbieter ist:

```
"Provider=MSDAIPP.DSO;Data Source=ResourceURL;User ID=MyUserID;Password=MyPassword;"
```

 -oder-

```
"URL=ResourceURL;User ID=MyUserID;Password=MyPassword;"
```

 Die Zeichenfolge, die dieser Schlüsselwörter besteht aus:

|Schlüsselwort|Description|
|-------------|-----------------|
|**Anbieter**|Gibt die OLE DB-Anbieter für Internet Publishing.|
|**Datenquelle** -"oder" - **URL**|Gibt die URL einer Datei oder eines Verzeichnisses in einem Webordner veröffentlicht.|
|**Benutzer-ID**|Gibt den Benutzernamen an.|
|**Kennwort**|Gibt das Kennwort des Benutzers an.|

> [!NOTE]
>  Wenn Sie ein Datenquellenanbieter, die Windows-Authentifizierung unterstützt Verbindung, müssen Sie angeben **Trusted_Connection = Yes** oder **Integrated Security = SSPI** anstelle von Benutzer-ID und Kennwort die Informationen in der Verbindungszeichenfolge angegeben.

 Wenn Sie festlegen, die *ResourceURL* Wert aus der "URL =" in der Verbindungszeichenfolge auf einen ungültigen Wert wird standardmäßig ein Dialogfeld, um einen gültigen Wert aufzufordern die Publishing Internetanbieter löst. Dies ist die unerwünschtes Verhalten für eine Komponente in der mittleren Ebene einer Anwendung, da die Ausführung des Programms angehalten, bis das Dialogfeld deaktiviert ist und der Client scheint eingefroren werden, da keine Antwort von der Komponente empfangen wurde.

> [!NOTE]
>  Wenn MSDAIPP. DSO wird explizit angegeben, als der Wert des Anbieters, entweder mit der *Anbieter* -Schlüsselwort der Verbindungszeichenfolge oder die **Anbieter** -Eigenschaft, können keine "URL =" in der Verbindungszeichenfolge angegeben. Wenn Sie dies tun, tritt ein Fehler auf. Geben Sie stattdessen einfach die URL in diesem Thema gezeigten [mithilfe von ADO mit dem OLE DB-Anbieter für Internet Publishing](../../../ado/guide/data/the-ole-db-provider-for-internet-publishing.md).

## <a name="see-also"></a>Siehe auch
 [Internet, die Publishing-Szenario](../../../ado/guide/data/internet-publishing-scenario.md) [der OLE DB-Anbieter für Internet Publishing](../../../ado/guide/data/the-ole-db-provider-for-internet-publishing.md)
