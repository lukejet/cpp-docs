---
title: "pointer_to_unary_function Class"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "xfunctional/std::pointer_to_unary_function"
  - "pointer_to_unary_function"
  - "std.pointer_to_unary_function"
  - "std::pointer_to_unary_function"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pointer_to_unary_function function"
  - "pointer_to_unary_function class"
ms.assetid: 05600207-b916-4759-beca-6b6facd2d6f6
caps.latest.revision: 20
ms.author: "corob"
manager: "ghogen"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# pointer_to_unary_function Class
Converts a unary function pointer into an adaptable unary function.  
  
## Syntax  
  
```
template<class Arg, class Result>
class pointer_to_unary_function
 : public unary_function<Arg, Result>
 {
    public:
 explicit pointer_to_unary_function(
    Result (* _pfunc)(Arg));

    Result operator()(
    Arg left) const;

 };
```  
  
#### Parameters  
 `_pfunc`  
 The binary function to be converted.  
  
 `left`  
 The object that the *\*_pfunc* is called on.  
  
## Return Value  
 The template class stores a copy of **_pfunc**. It defines its member function `operator()` as returning (\* **_pfunc**)(_ *Left*).  
  
## Remarks  
 A unary function pointer is a function object and may be passed to any Standard Template Library algorithm that is expecting a unary function as a parameter, but it is not adaptable. To use it with an adaptor, such as binding a value to it or using it with a negator, it must be supplied with the nested types **argument_type** and **result_type** that make such an adaptation possible. The conversion by `pointer_to_unary_function` allows the function adaptors to work with binary function pointers.  
  
## Example  
 The constructor of `pointer_to_unary_function` is rarely used directly. See the helper function [ptr_fun](../stdcpplib/-functional--functions.md#ptr_fun_function) for an example of how to declare and use the `pointer_to_unary_function` adaptor predicate.  
  
## Requirements  
 **Header:** \<functional>  
  
 **Namespace:** std  
  
## See Also  
 [Standard Template Library](../notintoc/standard-template-library.md)
