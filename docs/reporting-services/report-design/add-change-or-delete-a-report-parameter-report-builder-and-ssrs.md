---
title: Hinzufügen, Ändern oder Löschen von Berichtsparametern (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.component: report-design
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: d44a8e0a-10cf-4502-9391-09743ffc9bad
caps.latest.revision: 9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5cba98e1d3aacddfe191dfec324d664e905fc1f5
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "33020367"
---
# <a name="add-change-or-delete-a-report-parameter-report-builder-and-ssrs"></a>Hinzufügen, Ändern oder Löschen von Berichtsparametern (Berichts-Generator und SSRS)
  Mithilfe von Berichtsparametern können Sie Berichtsdaten auswählen, eine Verbindung zwischen verwandten Berichten herstellen und die Berichtspräsentation anpassen. Sie können einen Standardwert und eine Liste mit verfügbaren Werten bereitstellen, und die Benutzer können dann eine Auswahl treffen.  
  
 Nachdem ein Bericht veröffentlicht wurde, können Sie die Standardwerte, die verfügbaren Werte und andere Berichtsparametereigenschaften auf dem Berichtsserver ändern. Sie können mehrere Gruppen mit Standardparameterwerten bereitstellen, indem Sie verknüpfte Berichte erstellen. Weitere Informationen finden Sie unter [Berichtsparameter &#40;Berichts-Generator und Berichts-Designer&#41;](../../reporting-services/report-design/report-parameters-report-builder-and-report-designer.md)" basiert.  
  
 Thema dieses Artikel ist das Hinzufügen von Berichtsparametern zu einem paginierten Bericht in [!INCLUDE[ssRBnoversion](../../includes/ssrbnoversion-md.md)] oder zu Berichts-Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]. Sie können Berichtsparameter auch mobilen Berichte in  [!INCLUDE[SS_MobileReptPub_Long](../../includes/ss-mobilereptpub-long-md.md)]hinzufügen. Weitere Informationen finden Sie unter [Create mobile reports with SQL Server Mobile Report Publisher](../../reporting-services/mobile-reports/create-mobile-reports-with-sql-server-mobile-report-publisher.md) .  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-or-edit-a-report-parameter"></a>So können Sie einen Berichtsparameter hinzufügen oder bearbeiten  
  
1.  Klicken Sie in [!INCLUDE[ssRBnoversion](../../includes/ssrbnoversion-md.md)] oder in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]im Berichts-Designer im Bereich **Berichtsdaten** mit der rechten Maustaste auf den Knoten **Parameter** , und klicken Sie dann auf **Parameter hinzufügen**. Das Dialogfeld **Berichtsparametereigenschaften** wird geöffnet.  
  
2.  Geben Sie unter **Name**einen Namen für den Parameter ein, oder übernehmen Sie den Standardnamen.  
  
3.  Geben Sie unter **Eingabeaufforderung**den Text ein, der neben dem Parametertextfeld angezeigt wird, wenn der Bericht ausgeführt wird.  
  
4.  Wählen Sie unter **Datentyp**den Datentyp für den Parameterwert aus.  
  
5.  Falls der Parameter einen leeren Wert enthalten darf, wählen Sie **Leeren Wert zulassen**aus.  
  
6.  Falls der Parameter einen Nullwert enthalten darf, wählen Sie **NULL-Wert zulassen**aus.  
  
7.  Falls für einen Parameter mehrere Werte ausgewählt werden dürfen, aktivieren Sie die Option **Mehrere Werte zulassen**.  
  
8.  Legen Sie die Sichtbarkeit fest.  
  
    -   Wenn der Parameter oben im Bericht auf der Symbolleiste angezeigt werden soll, wählen Sie **Sichtbar**aus.  
  
    -   Um den Parameter auszublenden und nicht auf der Symbolleiste anzuzeigen, wählen Sie **Ausgeblendet**aus.  
  
    -   Um den Parameter auszublenden und zu verhindern, dass er nach Veröffentlichung des Berichts auf dem Berichtsserver geändert wird, wählen Sie die Option **Intern**aus. Der Berichtsparameter kann dann nur in der Berichtsdefinition angezeigt werden. Bei dieser Option müssen Sie einen Standardwert festlegen oder NULL-Werte für den Parameter zulassen.  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-report-parameter"></a>So löschen Sie einen Berichtsparameter  
  
1.  Erweitern Sie im Bereich **Berichtsdaten** den Knoten **Parameter** .  
  
2.  Klicken Sie mit der rechten Maustaste auf den Berichtsparameter, und klicken Sie anschließend auf **Löschen**.  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
 [Hinzufügen, Ändern oder Löschen von verfügbaren Werten für einen Berichtsparameter &#40;Berichts-Generator und SSRS&#41;](../../reporting-services/report-design/add-change-or-delete-available-values-for-a-report-parameter.md)   
 [Hinzufügen, Ändern oder Löschen von Standardwerten für einen Berichtsparameter (Berichts-Generator und SSRS)](../../reporting-services/report-design/add-change-or-delete-default-values-for-a-report-parameter.md)   
 [Ändern der Reihenfolge von Berichtsparametern &#40;Berichts-Generator und SSRS&#41;](../../reporting-services/report-design/change-the-order-of-a-report-parameter-report-builder-and-ssrs.md)   
 [Berichtsparameter &#40;Berichts-Generator und Berichts-Designer&#41;](../../reporting-services/report-design/report-parameters-report-builder-and-report-designer.md)   
 [Hinzufügen von kaskadierenden Parametern zu einem Bericht &#40;Berichts-Generator und SSRS&#41;](../../reporting-services/report-design/add-cascading-parameters-to-a-report-report-builder-and-ssrs.md)   
 [Tutorial: Add a Parameter to Your Report (Report Builder) (Tutorial: Hinzufügen eines Parameters zu einem Bericht (Berichts-Generator))](../../reporting-services/tutorial-add-a-parameter-to-your-report-report-builder.md)   
 [Hinzufügen von Datasetfiltern, Datenbereichsfiltern und Gruppenfiltern &#40;Berichts-Generator und SSRS&#41;](../../reporting-services/report-design/add-dataset-filters-data-region-filters-and-group-filters.md)   
 [Parameters Collection References (Report Builder and SSRS) (Verweise auf Parameterauflistungen (Berichts-Generator und SSRS))](../../reporting-services/report-design/built-in-collections-parameters-collection-references-report-builder.md)   
 [Add a multi-value parameter to a Report (Hinzufügen eines aus mehreren Werten bestehenden Parameters zu einem Bericht)](../../reporting-services/report-design/add-a-multi-value-parameter-to-a-report.md)  
  
  
