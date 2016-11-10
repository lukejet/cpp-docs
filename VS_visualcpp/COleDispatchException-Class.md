---
title: "COleDispatchException Class"
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
ms.topic: reference
ms.assetid: 0e95c8be-e21a-490c-99ec-181c6a9a26d0
caps.latest.revision: 18
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
# COleDispatchException Class
Handles exceptions specific to the OLE `IDispatch` interface, which is a key part of OLE automation.  
  
## Syntax  
  
```  
class COleDispatchException : public CException  
```  
  
## Members  
  
### Public Data Members  
  
|Name|Description|  
|----------|-----------------|  
|[COleDispatchException::m_dwHelpContext](#coledispatchexception__m_dwhelpcontext)|Help context for error.|  
|[COleDispatchException::m_strDescription](#coledispatchexception__m_strdescription)|Verbal error description.|  
|[COleDispatchException::m_strHelpFile](#coledispatchexception__m_strhelpfile)|Help file to use with `m_dwHelpContext`.|  
|[COleDispatchException::m_strSource](#coledispatchexception__m_strsource)|Application that generated the exception.|  
|[COleDispatchException::m_wCode](#coledispatchexception__m_wcode)|`IDispatch`-specific error code.|  
  
## Remarks  
 Like the other exception classes derived from the `CException` base class, `COleDispatchException` can be used with the **THROW**, `THROW_LAST`, **TRY**, **CATCH**, `AND_CATCH`, and `END_CATCH` macros.  
  
 In general, you should call [AfxThrowOleDispatchException](../Topic/AfxThrowOleDispatchException.md) to create and throw a `COleDispatchException` object.  
  
 For more information on exceptions, see the articles [Exception Handling (MFC)](../VS_visualcpp/Exception-Handling-in-MFC.md) and [Exceptions: OLE Exceptions](../VS_visualcpp/Exceptions--OLE-Exceptions.md).  
  
## Inheritance Hierarchy  
 [CObject](../VS_visualcpp/CObject-Class.md)  
  
 [CException](../VS_visualcpp/CException-Class.md)  
  
 `COleDispatchException`  
  
## Requirements  
 **Header:** afxdisp.h  
  
##  <a name="coledispatchexception__m_dwhelpcontext"></a>  COleDispatchException::m_dwHelpContext  
 Identifies a help context in your application's help (.HLP) file.  
  
```  
DWORD m_dwHelpContext;  
```  
  
### Remarks  
 This member is set by the function [AfxThrowOleDispatchException](../Topic/AfxThrowOleDispatchException.md) when an exception is thrown.  
  
### Example  
  See the example for [COleDispatchDriver::CreateDispatch](../VS_visualcpp/COleDispatchDriver-Class.md#coledispatchdriver__createdispatch).  
  
##  <a name="coledispatchexception__m_strdescription"></a>  COleDispatchException::m_strDescription  
 Contains a verbal error description, such as "Disk full."  
  
```  
CString m_strDescription;  
```  
  
### Remarks  
 This member is set by the function [AfxThrowOleDispatchException](../Topic/AfxThrowOleDispatchException.md) when an exception is thrown.  
  
### Example  
  See the example for [COleDispatchDriver::CreateDispatch](../VS_visualcpp/COleDispatchDriver-Class.md#coledispatchdriver__createdispatch).  
  
##  <a name="coledispatchexception__m_strhelpfile"></a>  COleDispatchException::m_strHelpFile  
 The framework fills in this string with the name of the application's help file.  
  
```  
CString m_strHelpFile;  
```  
  
##  <a name="coledispatchexception__m_strsource"></a>  COleDispatchException::m_strSource  
 The framework fills in this string with the name of the application that generated the exception.  
  
```  
CString m_strSource;  
```  
  
### Example  
  See the example for [COleDispatchDriver::CreateDispatch](../VS_visualcpp/COleDispatchDriver-Class.md#coledispatchdriver__createdispatch).  
  
##  <a name="coledispatchexception__m_wcode"></a>  COleDispatchException::m_wCode  
 Contains an error code specific to your application.  
  
```  
WORD m_wCode;  
```  
  
### Remarks  
 This member is set by the function [AfxThrowOleDispatchException](../Topic/AfxThrowOleDispatchException.md) when an exception is thrown.  
  
## See Also  
 [MFC Sample CALCDRIV](../VS_visualcpp/Visual-C---Samples.md)   
 [CException Class](../VS_visualcpp/CException-Class.md)   
 [Hierarchy Chart](../VS_visualcpp/Hierarchy-Chart.md)   
 [COleDispatchDriver Class](../VS_visualcpp/COleDispatchDriver-Class.md)   
 [COleException Class](../VS_visualcpp/COleException-Class.md)