---
title: Erstellen und Verwalten von Rollen | Microsoft Docs
ms.date: 05/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 5d97cd04228b13d0f57d99b6f8808a955bba1bea
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2018
ms.locfileid: "34045614"
---
# <a name="create-and-manage-roles"></a>Erstellen und Verwalten von Rollen 
[!INCLUDE[ssas-appliesto-sqlas-aas](../../includes/ssas-appliesto-sqlas-aas.md)]
  Mit Rollen werden in tabellarischen Modellen Elementberechtigungen für ein Modell definiert. Rollen für ein Modellprojekt werden in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]im Dialogfeld Rollen-Manager definiert. Nach der Bereitstellung eines Modells können die Rollen vom Datenbankadministrator in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]verwaltet werden.  
  
 Die Aufgaben in diesem Artikel wird beschrieben, wie zum Erstellen und Verwalten von Rollen während der Modellerstellung mit dem Dialogfeld Rollen-Manager in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]. Informationen zum Verwalten von Rollen in einer bereitgestellten Modelldatenbank finden Sie unter [Rollen für tabellarische Modelle](../../analysis-services/tabular-models/tabular-model-roles-ssas-tabular.md).  
  
## <a name="tasks"></a>Aufgaben  
 Zum Erstellen, Bearbeiten, Kopieren und Löschen von Rollen verwenden Sie das Dialogfeld **Rollen-Manager** . Klicken Sie zum Anzeigen des Dialogfelds **Rollen-Manager** in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]auf das Menü **Modell** und anschließend auf **Rollen-Manager**.  
  
###  <a name="bkmk_new_role"></a> So erstellen Sie eine neue Rolle  
  
1.  Klicken Sie in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]auf das Menü **Modell** und dann auf **Rollen-Manager**.  
  
2.  Klicken Sie im Dialogfeld **Rollen-Manager** auf **Neu**.  
  
     Der Liste Rollen wird eine neue hervorgehobene Rolle hinzugefügt.  
  
3.  Geben Sie in der Liste **Rollen** im Feld **Name** einen Namen für die Rolle ein.  
  
     Der Name der Standardrolle wird für jede neue Rolle automatisch inkrementell erhöht. Es wird empfohlen, einen Namen einzugeben, durch den der Elementtyp eindeutig identifiziert wird, beispielsweise "Finance Managers" oder "Human Resources Specialists".  
  
4.  Klicken Sie im Feld **Berechtigungen** auf den Pfeil nach unten, und wählen Sie einen der folgenden Berechtigungstypen aus:  
  
    |Berechtigung|Description|  
    |----------------|-----------------|  
    |**InclusionThresholdSetting**|Mitglieder können keine Änderungen am Modellschema vornehmen und keine Daten abfragen.|  
    |**Lesen**|Mitglieder dürfen Daten (basierend auf Zeilenfiltern) abfragen, doch sie können keine Änderungen am Modellschema vornehmen.|  
    |**Lesen und verarbeiten**|Mitglieder können Daten (basierend auf Filtern auf Zeilenebene) abfragen und die Vorgänge Verarbeiten und Alles verarbeiten ausführen, jedoch keine Änderungen am Modellschema vornehmen.|  
    |**Verarbeiten**|Mitglieder können die Vorgänge Verarbeiten und Alles verarbeiten ausführen. Sie können weder das Modellschema ändern noch Daten abfragen.|  
    |**Administrator**|Mitglieder können Änderungen am Modellschema vornehmen und alle Daten abfragen.|  
  
5.  Um eine Beschreibung für die Rolle einzugeben, klicken Sie auf das Feld **Beschreibung** und geben dann eine Beschreibung ein.  
  
6.  Wenn die erstellte Rolle über Lese- bzw. Lese- und Verarbeitungsberechtigungen verfügt, können Sie Zeilenfilter mithilfe einer DAX-Formel hinzufügen. Um Zeilenfilter hinzuzufügen, klicken Sie auf die Registerkarte **Zeilenfilter** , wählen eine Tabelle aus, klicken auf das Feld **DAX-Filter** und geben eine DAX-Formel ein.  
  
7.  Um der Rolle Mitglieder hinzuzufügen, klicken Sie auf die Registerkarte **Mitglieder** und dann auf **Hinzufügen**.  
  
    > [!NOTE]  
    >  Rollenmitglieder können einem bereitgestellten Modell auch mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]hinzugefügt werden. Weitere Informationen finden Sie unter [Verwalten von Rollen mit SSMS](../../analysis-services/tabular-models/manage-roles-by-using-ssms-ssas-tabular.md).  
  
8.  Geben Sie im Dialogfeld **Benutzer oder Gruppen auswählen** Windows-Benutzer- oder Windows-Gruppenobjekte als Mitglieder ein.  
  
9. Klicken Sie auf **OK**.  
  
## <a name="see-also"></a>Siehe auch  
 [Rollen](../../analysis-services/tabular-models/roles-ssas-tabular.md)   
 [Perspektiven](../../analysis-services/tabular-models/perspectives-ssas-tabular.md)   
 [In Excel analysieren](../../analysis-services/tabular-models/analyze-in-excel-ssas-tabular.md)   
 [USERNAME-Funktion (DAX)](http://msdn.microsoft.com/en-us/22dddc4b-1648-4c89-8c93-f1151162b93f)   
 [CUSTOMDATA-Funktion (DAX)](http://msdn.microsoft.com/en-us/58235ad8-226c-43cc-8a69-5a52ac19dd4e)  
  
  
