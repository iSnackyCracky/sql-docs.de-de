---
title: Festlegen und Konfigurieren von Maßeinheiten (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/01/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.component: report-design
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: a15a96c3-7d2c-433e-a440-4ea051e967a9
caps.latest.revision: 8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 86607db4b618c0d56ab7684f9d3223721b306858
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "33028887"
---
# <a name="set-and-configure-measurement-units-report-builder-and-ssrs"></a>Festlegen und Konfigurieren von Maßeinheiten (Berichts-Generator und SSRS)
  In einem paginierten [!INCLUDE[ssRSnoversion_md](../../includes/ssrsnoversion-md.md)] -Bericht verwenden Indikatoren eine von zwei Maßeinheiten: Prozentsatz oder Maßeinheit.   
    
  Standardmäßig sind Indikatoren so konfiguriert, dass Prozentsätze als Maßeinheit verwendet werden. Dies bedeutet, dass die Indikatorwerte, die den einzelnen Symbolen im Indikatorsatz zugewiesen sind, von einem Prozentbereich bestimmt werden. Die Prozentbereiche werden gleichmäßig auf die Symbole im Indikatorsatz verteilt. Jedes Symbol stellt einen Indikatorstatus dar. Sie können die Prozentsätze für die einzelnen Symbole im Indikatorsatz ändern, indem Sie andere Prozentsätze für den Start- und Endbereich angeben. Darüber hinaus wird der Minimal- und Maximalwert in den Daten von Indikatoren automatisch erkannt.  
  
 Sie können die Maßeinheit in einen numerischen Wert ändern. In diesem Fall geben Sie kein Minimum oder Maximum für die Daten an, sondern legen stattdessen nur den Start- und Endwert für jedes vom Indikator verwendete Symbol fest.  
  
 Optionen wie Maßeinheiten können mithilfe von Ausdrücken festgelegt werden. Weitere Informationen finden Sie unter [Ausdrücke &#40;Berichts-Generator und SSRS&#41;](../../reporting-services/report-design/expressions-report-builder-and-ssrs.md).  
  
## <a name="to-use-the-numeric-state-measurement-unit"></a>So verwenden Sie die numerische Maßeinheit  
  
1.  Klicken Sie mit der rechten Maustaste auf den Indikator, der geändert werden soll, und klicken Sie auf **Indikatoreigenschaften**.  
  
2.  Klicken Sie im linken Bereich auf **Wert und Status** .  
  
3.  Klicken Sie in der Liste **Maßeinheit für Status** auf **Numerisch**.  
  
     Klicken Sie optional auf die Schaltfläche **Ausdruck** (*fx*), um einen Ausdruck zu bearbeiten, der den Wert der Option festlegt.  
  
4.  Aktualisieren Sie für jedes Symbol im Indikatorsatz die Werte in den Textfeldern **Start** und **Ende** .  
  
     Klicken Sie optional auf die Schaltfläche **Ausdruck** (*fx*), um einen Ausdruck zu bearbeiten, mit dem die Werte der Optionen **Start** und **Ende** festgelegt werden.  
  
    > [!NOTE]  
    >  Die Werte in den Textfeldern **Start** und **Ende** müssen numerisch sein.  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="to-use-the-percentage-measurement-unit"></a>So verwenden Sie die prozentuale Maßeinheit  
  
1.  Klicken Sie mit der rechten Maustaste auf den Indikator, der geändert werden soll, und klicken Sie auf **Indikatoreigenschaften**.  
  
2.  Klicken Sie im linken Bereich auf **Wert und Status** .  
  
3.  Klicken Sie in der Liste **Maßeinheit für Status** auf **Prozent**.  
  
     Klicken Sie optional auf die Schaltfläche **Ausdruck** (*fx*), um einen Ausdruck zu bearbeiten, der den Wert der Option festlegt.  
  
4.  Optional können Sie die Optionen **Minimum** und **Maximum** ändern, um bestimmte Werte zu verwenden, statt die vom Indikator verwendeten Minimum- und Maximumwerte der Daten automatisch zu bestimmen. Der Wert von **Minimum** muss kleiner als der Wert von **Maximum**sein.  
  
    > [!NOTE]  
    >  Wenn Sie explizit Minimum- und Maximumwerte festlegen, wird dieser Wertbereich vom Indikator unabhängig von den tatsächlichen Minimum- und Maximumwerten in den Daten verwendet. Das bedeutet, dass die Werte unter dem Minimumwert und über dem Maximumwert von der Auswertung ausgeschlossen wird, über die die im Bericht anzuzeigenden Indikatorsymbole bestimmt werden.  
  
     Klicken Sie optional auf die Schaltfläche **Ausdruck** (*fx*), um einen Ausdruck zu bearbeiten, der die Werte der Option festlegt.  
  
5.  Aktualisieren Sie für jedes Symbol im Indikatorsatz die Werte in den Textfeldern **Start** und **Ende** .  
  
     Klicken Sie optional auf die Schaltfläche **Ausdruck** (*fx*), um einen Ausdruck zu bearbeiten, mit dem die Werte der Optionen **Start** und **Ende** festgelegt werden.  
  
    > [!NOTE]  
    >  Die Werte in den Textfeldern **Start** und **Ende** müssen numerisch sein.  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
 [Indikatoren &#40;Berichts-Generator und SSRS&#41;](../../reporting-services/report-design/indicators-report-builder-and-ssrs.md)  
  
  
