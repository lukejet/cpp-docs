---
title: "CRowsetImpl::NameFromDBID"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 6aa5b074-90c7-4434-adfd-c64c13e76c78
caps.latest.revision: 9
manager: ghogen
translation.priority.ht: 
  - cs-cz
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - pl-pl
  - pt-br
  - ru-ru
  - tr-tr
  - zh-cn
  - zh-tw
---
# CRowsetImpl::NameFromDBID
Extracts a string from a **DBID** and copies it to the `bstr` passed in.  
  
## Syntax  
  
```  
  
      HRESULT CRowsetBaseImpl::NameFromDBID(  
   DBID* pDBID,  
   CComBSTR& bstr,  
   bool bIndex   
);  
```  
  
#### Parameters  
 *pDBID*  
 [in] A pointer to the **DBID** from which to extract a string.  
  
 `bstr`  
 [in] A [CComBSTR](../VS_visualcpp/CComBSTR-Class.md) reference to place a copy of the **DBID** string.  
  
 `bIndex`  
 [in] **true** if an index **DBID**; **false** if a table **DBID**.  
  
## Return Value  
 A standard `HRESULT`. Depending on whether the **DBID** is a table or an index (denoted by `bIndex`), the method will either return **DB_E_NOINDEX** or **DB_E_NOTABLE**.  
  
## Remarks  
 This method is called by the `CRowsetImpl` implementations of [ValidateCommandID](../VS_visualcpp/CRowsetImpl--ValidateCommandID.md) and [GetCommandFromID](../VS_visualcpp/CRowsetImpl--GetCommandFromID.md).  
  
## Requirements  
 **Header:** atldb.h  
  
## See Also  
 [CRowsetImpl Class](../VS_visualcpp/CRowsetImpl-Class.md)