---
title: Zusätzliche Tabellenwertparameter-Metadaten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC), catalog functions to retrieve metadata
- table-valued parameters (ODBC), metadata
ms.assetid: 6c193188-5185-4373-9a0d-76cfc150c828
caps.latest.revision: 15
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: f28c5baf528a975b987c68e81543932b63dc5761
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2018
ms.locfileid: "37419749"
---
# <a name="additional-table-valued-parameter-metadata"></a>Zusätzliche Tabellenwertparameter-Metadaten
  Um Metadaten für einen Tabellenwertparameter abzurufen, ruft die Anwendung SQLProcedureColumns. Für einen Tabellenwertparameter gibt SQLProcedureColumns eine einzelne Zeile zurück. Zwei zusätzliche [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-bestimmte Spalten, SS_TYPE_CATALOG_NAME und SS_TYPE_SCHEMA_NAME, wurden hinzugefügt, um Schema und Katalog für Tabellentypen mit Tabellenwertparametern bereitzustellen. In Übereinstimmung mit der ODBC-Spezifikation werden SS_TYPE_CATALOG_NAME und SS_TYPE_SCHEMA_NAME allen treiberspezifischen Spalten vorangestellt, die in früheren Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] hinzugefügt wurden, sowie allen Spalten nachgestellt, die von ODBC selbst benötigt werden.  
  
 In der folgenden Tabelle sind die Spalten aufgeführt, die für Tabellenwertparameter signifikant sind.  
  
|Spaltenname|Datentyp|Wert/Kommentare|  
|-----------------|---------------|---------------------|  
|DATA_TYPE|Smallint nicht NULL|SQL_SS_TABLE|  
|TYPE_NAME|WVarchar(128) nicht NULL|Der Typname des Tabellenwertparameters.|  
|COLUMN_SIZE|Integer|NULL|  
|BUFFER_LENGTH|Integer|0|  
|DECIMAL_DIGITS|Smallint|NULL|  
|NUM_PREC_RADIX|Smallint|NULL|  
|NULLABLE|Smallint nicht NULL|SQL_NULLABLE|  
|REMARKS|Varchar|NULL|  
|COLUMN_DEF|WVarchar(4000)|NULL|  
|SQL_DATA_TYPE|Smallint nicht NULL|SQL_SS_TABLE|  
|SQL_DATETIME_SUB|Smallint|NULL|  
|CHAR_OCTET_LENGTH|Integer|NULL|  
|ORDINAL_POSITION|Integer nicht NULL|Die Ordnungsposition des Parameters.|  
|IS_NULLABLE|Varchar|"YES"|  
|SS_TYPE_CATALOG_NAME|WVarchar(128) nicht NULL|Der Katalog, der die Typdefinition für den Tabellentyp des Tabellenwertparameters enthält.|  
|SS_TYPE_SCHEMA_NAME|WVarchar(128) nicht NULL|Das Schema, das die Typdefinition für den Tabellentyp des Tabellenwertparameters enthält.|  
  
 Die WVarchar-Spalten werden in der ODBC-Spezifikation als Varchar definiert, werden aber tatsächlich in allen neueren Versionen des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-ODBC-Treibers als WVarchar zurückgegeben. Diese Änderung wurde vorgenommen, als der ODBC 3.5-Spezifikation die Unicode-Unterstützung hinzugefügt wurde. Sie wurde jedoch nicht explizit ausgeschrieben.  
  
 Um zusätzliche Metadaten für Tabellenwertparameter abzurufen, verwendet eine Anwendung die Katalogfunktionen SQLColumns und SQLPrimaryKeys. Vor dem Aufruf dieser Funktionen für Tabellenwertparameter muss die Anwendung das Anweisungsattribut SQL_SOPT_SS_NAME_SCOPE auf SQL_SS_NAME_SCOPE_TABLE_TYPE festlegen. Dieser Wert gibt an, dass die Anwendung Metadaten für einen Tabellentyp anstatt einer tatsächlichen Tabelle erfordert. Die Anwendung übergibt dann den TYPE_NAME des Tabellenwertparameters als die *TableName* Parameter. SS_TYPE_CATALOG_NAME und SS_TYPE_SCHEMA_NAME werden verwendet, mit der *CatalogName* und *SchemaName* Parameter, um den Katalog und Schema für den Tabellenwertparameter zu identifizieren. Wenn eine Anwendung das Abrufen von Metadaten für Tabellenwertparameter abgeschlossen hat, muss sie SQL_SOPT_SS_NAME_SCOPE wieder auf den Standardwert SQL_SS_NAME_SCOPE_TABLE festlegen.  
  
 Wenn SQL_SOPT_SS_NAME_SCOPE auf SQL_SS_NAME_SCOPE_TABLE festgelegt ist, schlagen Abfragen von Verbindungsservern fehl. Aufrufen von SQLColumns oder SQLPrimaryKeys mit einem Katalog, der eine Serverkomponente enthält, schlägt fehl.  
  
## <a name="see-also"></a>Siehe auch  
 [Tabellenwertparameter &#40;ODBC&#41;](table-valued-parameters-odbc.md)  
  
  