---
title: Verwenden Sie erweiterte Ereignisse (XEvents) von SQLServer zum Überwachen von Analysis Services | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: b57cc2fe-52dc-4fa9-8554-5a866e25c6d7
caps.latest.revision: 5
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 4aa591ff08106f7af8946d6725d8894c52149634
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37332800"
---
# <a name="use-sql-server-extended-events-xevents-to-monitor-analysis-services"></a>Verwenden von erweiterten Ereignissen von SQL Server (XEvents) zum Überwachen von Analysis Services
  Analysis Services bietet Ablaufverfolgungsfunktionen durch die Verwendung von [Extended Events](../../relational-databases/extended-events/extended-events.md).  
  
 Erweiterte Ereignisse ist eine Ereignisinfrastruktur, die für Serversysteme stark skalierbar und konfigurierbar ist. Erweiterte Ereignisse ist ein Lightweight-Leistungsüberwachungssystem, das sehr wenige Leistungsressourcen verwendet.  
  
 Alle Analysis Services-Ereignisse aufgezeichnet werden können und auf bestimmte Consumer, gemäß Definition in ausgerichtet [Extended Events](../../relational-databases/extended-events/extended-events.md), durch XEvents.  
  
## <a name="initiating-extended-events-in-analysis-services"></a>Initiieren von Erweiterte Ereignisse in Analysis Services  
 Die Erweiterte Ereignis-Ablaufverfolgung wird mit einem ähnlichen XMLA-Skriptbefehl zum Erstellen eines Objekts wie unten dargestellt aktiviert:  
  
```  
<Execute …>  
   <Command>  
      <Batch …>  
         <Create …>  
            <ObjectDefinition>  
               <Trace>  
                  <ID>trace_id</ID>  
                  <Name>trace_name</Name>  
                  <ddl300_300:XEvent>  
                     <event_session …>  
                        <event package="AS" name="AS_event">  
                           <action package="PACKAGE0" …/>  
                        </event>  
                        <target package="PACKAGE0" name="asynchronous_file_target">  
                           <parameter name="filename" value="data_filename.xel"/>  
                           <parameter name="metadatafile" value="metadata_filename.xem"/>  
                        </target>  
                     </event_session>  
                  </ddl300_300:XEvent>  
               </Trace>  
            </ObjectDefinition>  
         </Create>  
      </Batch>  
   </Command>  
   <Properties></Properties>  
</Execute>  
  
```  
  
 Dabei sind die folgenden Elemente abhängig von den Ablaufverfolgungsanforderungen vom Benutzer zu definieren:  
  
 *trace_id*  
 Definiert den eindeutigen Bezeichner für diese Ablaufverfolgung.  
  
 *trace_name*  
 Der Name dieser Ablaufverfolgung, normalerweise eine lesbare Beschreibung der Ablaufverfolgung. Üblicherweise wird der *trace_id* -Wert als Name verwendet.  
  
 *AS_event*  
 Das Analysis Services-Ereignis, das verfügbar gemacht werden soll. Die Namen der Ereignisse finden Sie unter [Analysis Services-Ablaufverfolgungsereignisse](../trace-events/analysis-services-trace-events.md) .  
  
 *data_filename*  
 Der Name der Datei, die die Ereignisdaten enthält. Für diesen Namen wird ein Zeitstempel als Suffix verwendet, um das Überschreiben von Daten zu vermeiden, wenn die Ablaufverfolgung fortlaufend gesendet wird.  
  
 *metadata_filename*  
 Der Name der Datei, die die Ereignismetadaten enthält. Für diesen Namen wird ein Zeitstempel als Suffix verwendet, um das Überschreiben von Daten zu vermeiden, wenn die Ablaufverfolgung fortlaufend gesendet wird.  
  
## <a name="stopping-extended-events-in-analysis-services"></a>Beenden von Erweiterte Ereignisse in Analysis Services  
 Um das Erweiterte Ereignisse-Ablaufverfolgungsobjekt zu beenden, müssen Sie dieses Objekt mit einem ähnlichen XMLA-Skriptbefehl zum Löschen eines Objekts wie unten dargestellt löschen:  
  
```  
<Execute xmlns="urn:schemas-microsoft-com:xml-analysis">  
   <Command>  
      <Batch …>  
         <Delete …>  
            <Object>  
               <TraceID>trace_id</TraceID>  
            </Object>  
         </Delete>  
      </Batch>  
   </Command>  
   <Properties></Properties>  
</Execute>  
  
```  
  
 Dabei sind die folgenden Elemente abhängig von den Ablaufverfolgungsanforderungen vom Benutzer zu definieren:  
  
 *trace_id*  
 Definiert den eindeutigen Bezeichner für die zu löschende Ablaufverfolgung.  
  
## <a name="see-also"></a>Siehe auch  
 [Erweiterte Ereignisse](../../relational-databases/extended-events/extended-events.md)  
  
  
