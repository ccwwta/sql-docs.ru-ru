---
description: Пример свойств IsolationLevel и Mode (Visual c++)
title: Пример свойств IsolationLevel и Mode (Visual c++) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- Mode property [ADO], VC++ example
- IsolationLevel property [ADO], VC++ example
ms.assetid: 92ddec5d-e3dc-4e8e-997a-c5417cceab69
author: rothja
ms.author: jroth
ms.openlocfilehash: ea7af1176e4fb123df44f1640107b7c7ad345309
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100041924"
---
# <a name="isolationlevel-and-mode-properties-example-vc"></a>Пример свойств IsolationLevel и Mode (Visual c++)
В этом примере свойство [mode](./mode-property-ado.md) используется для открытия монопольного соединения, а свойство [IsolationLevel](./isolationlevel-property.md) — для открытия транзакции, которая выполняет изоляцию других транзакций.  
  
## <a name="example"></a>Пример  
  
```  
// BeginIsolationLevelCpp.cpp  
// compile with: /EHsc  
#import "msado15.dll" no_namespace rename("EOF","EndOfFile")  
  
#include <ole2.h>  
#include <stdio.h>  
#include <conio.h>  
#include "icrsint.h"  
  
// This class extracts titles and type from Title table  
class CTitleRs : public CADORecordBinding {  
   BEGIN_ADO_BINDING(CTitleRs)  
  
   // Column title is the 2nd field in the table  
    ADO_VARIABLE_LENGTH_ENTRY2(2, adVarChar, m_szau_Title, sizeof(m_szau_Title), lau_TitleStatus, FALSE)  
  
   // Column type is the 3rd field in the table  
   ADO_VARIABLE_LENGTH_ENTRY2(3, adVarChar, m_szau_Type, sizeof(m_szau_Type), lau_TypeStatus, TRUE)  
   END_ADO_BINDING()  
  
public:  
   CHAR m_szau_Title[81];  
   ULONG lau_TitleStatus;  
   CHAR m_szau_Type[13];  
   ULONG lau_TypeStatus;  
};  
  
// Function Declarations  
inline void TESTHR(HRESULT x) { if FAILED(x) _com_issue_error(x); };  
void IsolationLevelX();  
void PrintProviderError(_ConnectionPtr pConnection);  
void PrintComError(_com_error &e);  
  
int main() {  
   if (FAILED(::CoInitialize(NULL)))  
      return -1;  
  
   IsolationLevelX();  
  
   ::CoUninitialize();  
}  
  
void IsolationLevelX() {  
   // Define ADO ObjectPointers.  Initialize Pointers on define.  These are in the ADODB :: namespace.  
   _RecordsetPtr  pRstTitles  = NULL;  
   _ConnectionPtr pConnection = NULL;  
  
   // Define other Variables  
   HRESULT hr = S_OK;  
   IADORecordBinding *picRs = NULL;   // Interface Pointer Declared  
   CTitleRs titlers;   // C++ Class Object  
   LPSTR p_TempStr = NULL;  
   char * token1;  
  
   // Assign Connection String to Variable  
   _bstr_t strCnn("Provider='sqloledb'; Data Source='My_Data_Source'; Initial Catalog='pubs'; Integrated Security='SSPI';");  
  
   try {  
      // Open Connection and Titles Table  
      TESTHR(pConnection.CreateInstance(__uuidof(Connection)));  
      pConnection->Mode = adModeShareExclusive;  
      pConnection->IsolationLevel = adXactIsolated;  
      pConnection->Open(strCnn,"", "", adConnectUnspecified);  
  
      TESTHR(pRstTitles.CreateInstance(__uuidof(Recordset)));  
      pRstTitles->CursorType = adOpenDynamic;  
      pRstTitles->LockType = adLockPessimistic;  
  
      pRstTitles->Open("titles", _variant_t((IDispatch*) pConnection, true),  
                       adOpenDynamic, adLockPessimistic, adCmdTable);  
  
      pConnection->BeginTrans();  
  
      // Display Connection Mode  
      if (pConnection->Mode == adModeShareExclusive)  
         printf("Connection Mode Is Exclusive");  
      else  
         printf("Connection Mode Is Not Exclusive");       
  
      // Display Isolation Level   
      if (pConnection->IsolationLevel == adXactIsolated)  
         printf("\nTransaction is Isolated\n");  
      else  
         printf("\nTransaction is not Isolated\n");  
  
      // Open an IADORecordBinding interface pointer which we will use for binding Recordset to a class.  
      TESTHR(pRstTitles->QueryInterface( __uuidof(IADORecordBinding), (LPVOID*)&picRs));  
  
      // Bind the Recordset to a C++ class here  
      TESTHR(picRs->BindToRecordset(&titlers));  
  
      // Change the type of psychology titles.  
      p_TempStr = (LPSTR) malloc(sizeof(titlers.m_szau_Type));  
  
      while (!(pRstTitles->EndOfFile)) {  
         // Set the final character of the destination string to NULL.  
         p_TempStr[sizeof(titlers.m_szau_Type) - 1] = '\0';  
  
         // The source string will get truncated if its length is   
         // longer than the length of the destination string minus one.  
         strncpy_s(p_TempStr, sizeof(titlers.m_szau_Type), strtok_s(titlers.m_szau_Type, " ", &token1), sizeof(titlers.m_szau_Type) - 1);  
  
         // Compare type with psychology  
         if (!strcmp(p_TempStr,"psychology")) {  
            // Set the final character of the destination string to NULL.  
            titlers.m_szau_Type[sizeof(titlers.m_szau_Type) - 1] = '\0';  
  
            // Copy "self_help" title field.  The source string will get truncated if its length is   
            // longer than the length of the destination string minus one.  
            strncpy_s(titlers.m_szau_Type, sizeof(titlers.m_szau_Type), "self_help", sizeof(titlers.m_szau_Type) - 1);  
            picRs->Update(&titlers);  
         }  
         pRstTitles->MoveNext();  
      }  
  
      // Print current data in recordset.  
      pRstTitles->Requery(adOptionUnspecified);  
  
      // Open again IADORecordBinding interface pointer for Binding   
      // Recordset to a class.  
      TESTHR(pRstTitles->QueryInterface(__uuidof(IADORecordBinding), (LPVOID*)&picRs));  
  
      // ReBinding the Recordset to a C++ Class  
      TESTHR(picRs->BindToRecordset(&titlers));  
  
      // Move to the first record of the title table  
      pRstTitles->MoveFirst();  
  
      // Clear the screen for the next display  
      // system("cls");  
  
      while (!pRstTitles->EndOfFile) {  
         printf("%s -  %s\n",titlers.lau_TitleStatus == adFldOK ?   
            titlers.m_szau_Title :"<NULL>",  
            titlers.lau_TypeStatus == adFldOK ?   
            titlers.m_szau_Type :"<NULL>");  
         pRstTitles->MoveNext();  
      }  
   }  
   catch(_com_error &e) {  
      // Notify the user of errors if any.  
      PrintProviderError(pConnection);  
      PrintComError(e);  
   }  
  
   // Clean up objects before exit.  Release the IADORecordset Interface here.  
   if (picRs)  
      picRs->Release();  
  
   if (pRstTitles)  
      if (pRstTitles->State == adStateOpen)  
         pRstTitles->Close();  
  
   if (pConnection)  
      if (pConnection->State == adStateOpen) {  
         // Restore Original Data  
         pConnection->RollbackTrans();  
  
         pConnection->Close();  
      }  
  
   // Deallocate the memory  
   if (p_TempStr)  
      free(p_TempStr);  
}  
  
void PrintProviderError(_ConnectionPtr pConnection) {  
   // Print Provider Errors from Connection object  
   // pErr is a record object in the Connection's Error collection  
   ErrorPtr pErr = NULL;  
  
   if ((pConnection->Errors->Count)>0) {  
      long nCount = pConnection->Errors->Count;  
  
      // Collection ranges from 0 to nCount-1  
      for (long i = 0 ; i < nCount ; i++) {  
         pErr = pConnection->Errors->GetItem(i);  
         printf("\t Error Number :%x \t %s",pErr->Number, (LPCSTR) pErr->Description);  
      }  
   }  
}  
  
void PrintComError(_com_error &e) {  
   _bstr_t bstrSource(e.Source());  
   _bstr_t bstrDescription(e.Description());  
  
   // Print Com errors.  
   printf("Error\n");  
   printf("\tCode = %08lx\n", e.Error());  
   printf("\tCode meaning = %s\n", e.ErrorMessage());  
   printf("\tSource = %s\n", (LPCSTR) bstrSource);  
   printf("\tDescription = %s\n", (LPCSTR) bstrDescription);  
}  
```  
  
 **Режим соединения является эксклюзивным**  
**Транзакция изолирована**  
**Руководство по базам данных, занятое руководителем — бизнес**  
**Приготовление к компьютерам: Суррептитиаус балансовые листы — бизнес**  
**Вы можете бороться с нагрузкой компьютера! — Бизнес**  
**Прямой разговор о компьютерах — бизнес**  
**Гастрономика Silicon впадин обрабатывает-mod_cook**  
**Микроволновая печь Гаурмет-mod_cook**  
**Психологии Computer кулинар — не принято**  
**Но понятно ли это пользователю? — popular_comp**  
**Секреты впадин Silicon-popular_comp**  
**Сетевой этикет-popular_comp**  
**Computer Фобик и другие пользователи: варианты поведения — self_help**  
**Гнев ли врагов? — self_help**  
**Жизнь, не опасаясь self_help**  
**Деприватион данных с длительными примерами: четыре практических примера — self_help**  
**Безопасность эмоциональном: новый алгоритм — self_help**  
**Луковиц, ликс и чесночный: секреты кулинарных Средиземноморье-trad_cook**  
**50 лет в Буккингхам Palace Китченс-trad_cook**  
**Суши, кто угодно? — trad_cook**   
## <a name="see-also"></a>См. также:  
 [IsolationLevel, свойство](./isolationlevel-property.md)   
 [Свойство Mode (ADO)](./mode-property-ado.md)