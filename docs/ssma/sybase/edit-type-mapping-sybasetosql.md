---
title: Bearbeiten der Typzuordnung (SybaseToSQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.technology: ssma
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: 513f071a-d5e6-4ed5-acca-269bf76323c5
caps.latest.revision: 4
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.openlocfilehash: ecd9719ee3f3b8d1117f6926434af40256d8fd9a
ms.sourcegitcommit: 603d2e588ac7b36060fa0cc9c8621ff2a6c0fcc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2018
ms.locfileid: "40394643"
---
# <a name="edit-type-mapping-sybasetosql"></a>Bearbeiten der Typzuordnung (SybaseToSQL)
Die **Bearbeiten der Typzuordnung** Dialogfeld können Sie angeben, wie Datentypen zwischen Quelle und Ziel-Datenbankobjekten zugeordnet werden.  
  
Sie können dieses Dialogfeld an mehreren Stellen zugreifen:  
  
-   Bei Auswahl einer Quelldatenbank oder ein Datenbankobjekt, das **Type Mapping** Registerkarte wird rechts neben dem Metadaten-Explorer angezeigt. Klicken Sie auf **hinzufügen** fügen Sie eine neue Zuordnung hinzu, oder klicken Sie auf **bearbeiten** so ändern Sie eine vorhandene Typzuordnung.  
  
-   Auf der **Tools** , wählen Sie im Menü **Projekteinstellungen** oder **Projekt Standardeinstellungen**. Wählen Sie im daraufhin angezeigten Dialogfeld **Type Mapping**. Klicken Sie auf **hinzufügen** fügen Sie eine neue Zuordnung hinzu, oder klicken Sie auf **bearbeiten** so ändern Sie eine vorhandene Typzuordnung.  
  
Tabelle-spezifische Zuordnungen für Projekte replikationsdatentyp-Zuordnungen und Datenbank zu überschreiben. Datenbank-spezifische Zuordnungen überschreiben Project-Zuordnungen.  
  
## <a name="options"></a>Tastatur  
**Quelltyp**  
Wählen Sie den Quelltyp für die Daten zuordnen einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datentyp.  
  
Wenn der Datentyp mit variabler Länge ist, erscheint die folgenden Felder unter **Quelltyp**:  
  
**From**  
Geben Sie die minimale Länge für diese Zuordnung. Z. B. für die **Nchar** -Datentyp, Sie können eingeben, 10, um anzugeben, dass diese Zuordnung für einen Bereich ab **nchar(10)**.  
  
**Aktion**  
Geben Sie die maximale Länge für diese Zuordnung. Z. B. für die **Nchar** -Datentyp, Sie können eingeben, 20, um anzugeben, dass diese Zuordnung für einen Bereich endet **nchar(20)**.  
  
**Zieltyp**  
Wählen Sie die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datentyp, der der Quelldatentyp zugeordnet ist. Wenn SSMA erstellt, die Tabelle oder eine gespeicherte Prozedur in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ändert sich der Quelldatentyp auf diesen Datentyp.  
  
Wenn der Datentyp mit variabler Länge ist, erscheint das folgende Feld unter **Zieltyp**:  
  
**Replace with**  
Geben Sie die Ziellänge für diese Zuordnung. Z. B. für die **Nvarchar** -Datentyp, Sie können eingeben, 20, um anzugeben, dass die angegebene Quelle-Datentyp zugeordnet werden soll **nvarchar(20)**.  
  
