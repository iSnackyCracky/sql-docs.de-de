---
title: OData-Verbindungs-Manager | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 3caa4372-aff3-4c0f-9ecd-97870948b8d0
caps.latest.revision: 6
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 0f1a262a52bdc610da81c5b42785fa555967e8bb
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37239350"
---
# <a name="odata-connection-manager"></a>OData-Verbindungs-Manager
  Mithilfe eines OData-Verbindungs-Managers kann ein Paket eine Verbindung mit einer OData-Quelle herstellen. Eine OData-Quellkomponente stellt über einen OData-Verbindungs-Manager eine Verbindung mit einer OData-Quelle her und verwendet die Daten des Diensts. Finden Sie unter [OData-Quelle](../data-flow/odata-source.md)Abschnitt, um ausführliche Informationen einschließlich installationsanweisungen für diese Komponenten.  
  
## <a name="adding-connection-manager-to-an-ssis-package"></a>Hinzufügen des Verbindungs-Managers zu einem SSIS-Paket  
 Sie können einem SSIS-Paket einen neuen OData-Verbindungs-Manager auf drei Arten hinzufügen:  
  
-   Klicken Sie im **Quellen-Editor für OData** auf die Schaltfläche **Neu**  
  
-   Mit der rechten Maustaste **Verbindungs-Manager** Ordner in der **Projektmappen-Explorer** , und klicken Sie auf **neuer Verbindungs-Manager**. Wählen Sie unter **Typ des Verbindungs-Managers** die Option **ODATA**aus.  
  
-   Mit der rechten Maustaste den **Verbindungs-Manager** Bereich am unteren Rand des Pakets, und wählen **neue Verbindung...** . Wählen Sie unter **Typ des Verbindungs-Managers** die Option **ODATA**aus.  
  
## <a name="connection-manager-authentication"></a>Verbindungs-Manager-Authentifizierung  
 Der OData-Verbindungs-Manager unterstützt zwei Authentifizierungsmodi.  
  
-   Windows-Authentifizierung  
  
-   Standardauthentifizierung (Benutzername und Kennwort)  
  
 Für den anonymen Zugriff wählen Sie die Option Windows-Authentifizierung aus.  
  
### <a name="specifying-and-securing-credentials"></a>Festlegen und Sichern von Anmeldeinformationen  
 Wenn Ihr OData-Dienst die Standardauthentifizierung erfordert, können Sie angeben, eines Benutzernamens und Kennworts in der [OData-Verbindungs-Manager-Editor](../odata-connection-manager-editor.md). Die Werte, die Sie in den Editor eingeben, werden im Paket beibehalten. Der Kennwortwert wird gemäß der Schutzebene des Pakets verschlüsselt.  
  
 Es gibt mehrere Möglichkeiten, den Benutzernamen- und Kennwortwert zu externalisieren/parametrisieren. Die beiden Hauptmethoden in [!INCLUDE[ssISversion11](../../includes/ssisversion11-md.md)] bestehen darin, Parameter zu verwenden oder die Eigenschaften des Verbindungs-Managers beim Ausführen des Pakets in SQL Server Management Studio direkt festzulegen.  
  
## <a name="odata-connection-manager-properties"></a>Eigenschaften des OData-Verbindungs-Managers  
 In der folgenden Liste sind einige Eigenschaften des OData-Verbindungs-Managers beschrieben, die Sie ändern können.  
  
|||  
|-|-|  
|Eigenschaft|Description|  
|URL|Die URL zum Dienstdokument.|  
|UserName|Der Benutzername, der für die Standardauthentifizierung verwendet wird.|  
|Kennwort|Das Kennwort, das für die Standardauthentifizierung verwendet wird.|  
|ConnectionString|Stellt weitere Eigenschaften des Verbindungs-Managers dar.|  
  
## <a name="see-also"></a>Siehe auch  
 [OData Connection Manager Editor](../odata-connection-manager-editor.md)  
  
  
