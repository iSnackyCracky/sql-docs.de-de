---
title: Massenkopieren eine SELECT-Resultsets (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- bulk copy [ODBC]
- bulk copy [ODBC], data files
- bulk copy [ODBC], about bulk copy
ms.assetid: 63d5a87b-4d5f-449b-8c77-9f9cc6b190d4
caps.latest.revision: 14
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: d537846035a35497404ec9a26557507b34d08a18
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2018
ms.locfileid: "37428599"
---
# <a name="bulk-copy-a-select-result-set-odbc"></a>Massenkopieren eines SELECT-Resultsets (ODBC)
  In diesem Beispiel wird gezeigt, wie mit Massenkopierfunktionen das Resultset einer SELECT-Anweisung massenkopiert wird. Dieses Beispiel wurde für ODBC, Version 3.0 oder höher, entwickelt.  
  
> [!IMPORTANT]  
>  Verwenden Sie nach Möglichkeit die Windows-Authentifizierung. Wenn die Windows-Authentifizierung nicht verfügbar ist, fordern Sie die Benutzer auf, ihre Anmeldeinformationen zur Laufzeit einzugeben. Die Anmeldeinformationen sollten nicht in einer Datei gespeichert werden. Wenn Sie die Anmeldeinformationen permanent speichern müssen, verschlüsseln Sie sie mit der [Win32 Crypto-API](http://go.microsoft.com/fwlink/?LinkId=64532).  
  
### <a name="to-bulk-copy-out-the-result-set-of-a-select-statement"></a>So kopieren Sie das Resultset einer SELECT-Anweisung mithilfe eines Massenkopiervorgangs  
  
1.  Ordnen Sie ein Umgebungshandle und ein Verbindungshandle zu.  
  
2.  Legen Sie SQL_COPT_SS_BCP und SQL_BCP_ON fest, um Massenkopiervorgänge zu aktivieren.  
  
3.  Stellen Sie eine Verbindung mit SQL Server her.  
  
4.  Rufen Sie [Bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) auf die folgenden Informationen festzulegen:  
  
    -   Geben Sie NULL für den *SzTable* Parameter.  
  
    -   Der Name der Datendatei, die die Daten aus dem Resultset empfangen soll.  
  
    -   Name der Datendatei, in die Fehlermeldungen zum Massenkopiervorgang ausgegeben werden sollen (geben Sie NULL an, wenn keine Meldungsdatei erstellt werden soll)  
  
    -   Die Richtung des Kopiervorgangs: DB_OUT.  
  
5.  Rufen Sie [Bcp_control](../../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md), legen Sie eOption auf BCPHINTS fest, und platzieren Sie in iValue einen Zeiger auf ein SQLTCHAR-Array, das mit der SELECT-Anweisung.  
  
6.  Rufen Sie [Bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) um den Massenkopiervorgang auszuführen.  
  
 Wenn Sie diese Schritte ausführen, wird die Datei im systemeigenen Format erstellt. Sie können die Datenwerte in andere Datentypen konvertieren, indem Sie mithilfe von [Bcp_colfmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md). Weitere Informationen finden Sie unter [Erstellen einer Formatdatei für das Massenkopieren &#40;ODBC&#41;](create-a-bulk-copy-format-file-odbc.md).  
  
## <a name="example"></a>Beispiel  
 Sie benötigen eine ODBC-Datenquelle mit dem Namen AdventureWorks, deren Standarddatenbank die AdventureWorks-Beispieldatenbank ist. (Sie können die AdventureWorks-Beispieldatenbank von der Homepage [Microsoft SQL Server Samples and Community Projects](http://go.microsoft.com/fwlink/?LinkID=85384) herunterladen.) Diese Datenquelle muss auf dem ODBC-Treiber basieren, der vom Betriebssystem bereitgestellt wird (der Treibername lautet "SQL Server"). Wenn Sie dieses Beispiel als 32-Bit-Anwendung entwickeln und unter einem 64-Bit-Betriebssystem ausführen, müssen Sie die ODBC-Datenquelle mit dem ODBC-Administrator in %windir%\SysWOW64\odbcad32.exe erstellen.  
  
 In diesem Beispiel wird eine Verbindung mit der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Standardinstanz des Computers hergestellt. Ändern Sie zum Herstellen einer Verbindung mit einer benannten Instanz die Definition der ODBC-Datenquelle, um die Instanz im folgenden Format anzugeben: Server\benannteInstanz. Standardmäßig wird [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] in einer benannten Instanz installiert.  
  
 Kompilieren Sie mit odbc32.lib und odbcbcp.lib.  
  
```  
// compile with: odbc32.lib odbcbcp.lib  
#include <stdio.h>  
#include <string.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
#define MAXBUFLEN 256  
  
SQLHENV henv = SQL_NULL_HENV;  
HDBC hdbc1 = SQL_NULL_HDBC;  
  
void Cleanup() {  
   if (hdbc1 != SQL_NULL_HDBC) {  
      SQLDisconnect(hdbc1);  
      SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   }  
  
   if (henv != SQL_NULL_HENV)  
      SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
  
int main() {  
   RETCODE retcode;  
  
   // Bulk copy variables.  
   SDWORD cRows;  
   SQLTCHAR szBCPQuery[] = "SELECT BirthDate FROM HumanResources.Employee";  
  
   // Allocate the ODBC environment and save handle.  
   retcode = SQLAllocHandle (SQL_HANDLE_ENV, NULL, &henv);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(Env) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Notify ODBC that this is an ODBC 3.0 app.  
   retcode = SQLSetEnvAttr(henv, SQL_ATTR_ODBC_VERSION, (SQLPOINTER) SQL_OV_ODBC3, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetEnvAttr(ODBC version) Failed\n\n");  
      Cleanup();  
      return(9);      
   }  
  
   // Allocate ODBC connection handle, set bulk copy mode, and then connect.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc1);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLSetConnectAttr(hdbc1, SQL_COPT_SS_BCP, (void *)SQL_BCP_ON, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetConnectAttr(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Sample use Integrated Security, create SQL Server DSN using Windows NT authentication.   
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Initialize the bulk copy.  
   retcode = bcp_init(hdbc1, NULL, "BCPODBC.bcp", "BCPERROR.out", DB_OUT);  
   // The test is for the bulk copy return of SUCCEED, not the ODBC return of SQL_SUCCESS.  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_init(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Specify the query to use.  
   retcode = bcp_control(hdbc1, BCPHINTS, (void *)szBCPQuery);  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_control(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Execute the bulk copy.  
   retcode = bcp_exec(hdbc1, &cRows);  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_exec(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   printf("Number of rows bulk copied out = %d.\n", cRows);  
  
   // Cleanup  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Massenkopieren mit dem SQL Server-ODBC-Treiber – Themen &#40;ODBC&#41;](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md)  
  
  
