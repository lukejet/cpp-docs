---
title: "collate_byname Class"
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
ms.assetid: 3dc380df-867c-4763-b60e-ba62a8e63ca7
caps.latest.revision: 22
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
# collate_byname Class
A derived template class that describes an object that can serve as a collate facet of a given locale, enabling the retrieval of information specific to a cultural area concerning string sorting conventions.  
  
## Syntax  
  
```  
template<Class CharType>  
    class collate_byname : public collate<CharType> {  
public:  
    explicit collate_byname(  
        const char* _Locname,  
        size_t _Refs = 0  
    );  
    explicit collate_byname(  
        const string& _Locname,  
        size_t _Refs = 0);  
protected:  
    virtual ~collate_byname( );  
};  
```  
  
#### Parameters  
 `_Locname`  
 A named locale.  
  
 `_Refs`  
 An initial reference count.  
  
## Remarks  
 The template class describes an object that can serve as a [locale facet](../VS_visualcpp/locale-Class.md#facet_class) of type [collate](../VS_visualcpp/collate-Class.md#collate__collate)<CharType\>. Its behavior is determined by the [named](../VS_visualcpp/locale-Class.md#locale__name) locale `_Locname`. Each constructor initializes its base object with [collate](../VS_visualcpp/collate-Class.md#collate__collate)<CharType\>( `_Refs`).  
  
## Requirements  
 **Header:** <locale\>  
  
 **Namespace:** std  
  
## See Also  
 [Thread Safety in the C++ Standard Library](../VS_visualcpp/Thread-Safety-in-the-C---Standard-Library.md)