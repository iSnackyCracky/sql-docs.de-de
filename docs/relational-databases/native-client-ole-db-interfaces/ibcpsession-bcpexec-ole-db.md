---
title: Ibcpsession (OLE DB) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.suite: sql
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IBCPSession::BCPExec (OLE DB)
apitype: COM
helpviewer_keywords:
- BCPExec method
ms.assetid: 0f4ebb63-cf03-4e53-846e-6c3021cde007
caps.latest.revision: 23
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017'
ms.openlocfilehash: 948fe4e4f95776962a7b16d5bc7ac557cde5ecaa
ms.sourcegitcommit: 4cd008a77f456b35204989bbdd31db352716bbe6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39548640"
---
# <a name="ibcpsessionbcpexec-ole-db"></a>IBCPSession::BCPExec (OLE DB)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  Führt den Massenkopiervorgang aus.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
HRESULT BCPExec(   
      DBROWCOUNT *pRowsCopied);  
```  
  
## <a name="remarks"></a>Hinweise  
 Mit der **BCPExec**-Methode werden Daten aus einer Benutzerdatei in eine Datenbanktabelle kopiert oder umgekehrt. Dies ist vom Wert des *eDirection*-Parameters abhängig, der für die [IBCPSession::BCPInit](../../relational-databases/native-client-ole-db-interfaces/ibcpsession-bcpinit-ole-db.md)-Methode verwendet wird.  
  
 Rufen Sie vor dem Aufruf von **BCPExec**die **BCPInit** -Methode mit einem gültigen Benutzerdateinamen auf. Andernfalls wird ein Fehler ausgelöst. Die einzige Ausnahme besteht darin, wenn eine Abfrage für einen Massenkopiervorgang verwendet werden soll. In diesem Fall geben Sie in der **BCPInit** -Methode NULL für den Tabellennamen an, und dann geben Sie die Abfrage mithilfe der BCP_OPTION_HINTS-Option an.  
  
 Die **BCPExec** -Methode ist die einzige Methode zum Massenkopieren, die wahrscheinlich für einige Zeit nicht zurückkehrt. Es ist deshalb die einzige Massenkopiermethode, die den asynchronen Modus unterstützt. Zur Verwendung des asynchronen Modus legen Sie die anbieterspezifische Sitzungseigenschaft SSPROP_ASYNCH_BULKCOPY vor dem Aufrufen der **BCPExec** -Methode auf VARIANT_TRUE fest. Diese Eigenschaft ist im DBPROPSET_SQLSERVERSESSION-Eigenschaftensatz verfügbar. Rufen Sie die **BCPExec** -Methode mit den gleichen Parametern auf, um den Vorgang auf Vollständigkeit zu überprüfen. Wenn das Massenkopieren noch nicht abgeschlossen wurde, gibt die **BCPExec** -Methode DB_S_ASYNCHRONOUS zurück. Sie gibt überdies im *pRowsCopied* -Argument eine Statuszahl der Anzahl von Zeilen fest, die zum Server gesendet bzw. vom Server empfangen wurden. Für die zum Server gesendeten Zeilen wird erst ein Commit ausgeführt, wenn das Ende eines Batches erreicht wurde.  
  
## <a name="arguments"></a>Argumente  
 *pRowsCopied*[out]  
 Ein Zeiger auf einen DWORD-Wert. Die **BCPExec** -Methode füllt den DWORD-Wert mit der Anzahl von Zeilen, die erfolgreich kopiert wurden. Wenn das *pRowsCopied* -Argument auf NULL festgelegt wurde, wird es von der **BCPExec** -Methode ignoriert.  
  
## <a name="return-code-values"></a>Rückgabecodewerte  
 S_OK  
 Die Methode wurde erfolgreich ausgeführt.  
  
 E_FAIL  
 Ein anbieterspezifischer Fehler ist aufgetreten. Ausführliche Informationen erhalten Sie über die [ISQLServerErrorInfo](http://msdn.microsoft.com/library/a8323b5c-686a-4235-a8d2-bda43617b3a1)-Schnittstelle.  
  
 E_UNEXPECTED  
 Die Methode wurde unerwartet aufgerufen. Die **BCPInit** -Methode wurde beispielsweise erst nach dem Aufruf dieser Methode aufgerufen. Wird auch zurückgegeben, wenn der Vorgang mit der BCP_OPTION_ABORT-Option abgebrochen und danach die **BCPExec** -Methode aufgerufen wurde.  
  
 E_OUTOFMEMORY  
 Fehler aufgrund nicht genügenden Arbeitsspeichers  
  
 DB_S_ENDOFROWSET  
 Der Massenkopiervorgang wurde beendet, und die gesamte Datenübertragung wurde abgeschlossen.  
  
 DB_S_ASYNCHRONOUS  
 Der aktuelle Batch von Zeilen wurde kopiert. Rufen Sie die **BCPExec** -Methode erneut auf, um den nächsten Batch zu übertragen.  
  
 DB_S_ERRORSOCCURRED  
 Während des Massenkopiervorgangs sind Fehler aufgetreten, und einige Zeilen sind möglicherweise nicht kopiert worden. Die Anzahl der Fehler ist immer noch weniger als die maximal zulässige Fehleranzahl.  
  
## <a name="see-also"></a>Siehe auch  
 [IBCPSession &#40;OLE-DB&#41;](../../relational-databases/native-client-ole-db-interfaces/ibcpsession-ole-db.md)   
 [Durchführen von Massenkopiervorgängen](../../relational-databases/native-client/features/performing-bulk-copy-operations.md)  
  
  
