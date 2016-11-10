---
title: "Fatal Error C1128"
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
ms.topic: error-reference
ms.assetid: 6f9580fd-ecef-48be-9780-dcf666704279
caps.latest.revision: 11
manager: ghogen
translation.priority.ht: 
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - ru-ru
  - zh-cn
  - zh-tw
translation.priority.mt: 
  - cs-cz
  - pl-pl
  - pt-br
  - tr-tr
---
# Fatal Error C1128
number of sections exceeded object file format limit : compile with /bigobj  
  
 An .obj file exceeded the number of allowable sections, a COFF object file format limitation.  
  
 Reaching this section limitation can be the result of using [/Gy](../VS_visualcpp/-Gy--Enable-Function-Level-Linking-.md) and a debug build; **/Gy** causes functions to go into their own COMDAT sections. In a debug build, there is a debug info section for each COMDAT function.  
  
 C1128 can also be caused when there are too many inline functions.  
  
 To correct this error, divide your source file into multiple source code files, compile without **/Gy**, or compile with [/bigobj (Increase Number of Sections in .Obj file)](../VS_visualcpp/-bigobj--Increase-Number-of-Sections-in-.Obj-file-.md).  If you do not compile with **/Gy**, you will need to specify the optimizations individually, since **/O2** and **/O1** both imply **/Gy**.  
  
 If possible, compile without debugging information.  
  
 You may also need to have specific instantiations of templates in separate source code files, rather than having the compiler emit them.  
  
 When porting code, C1128 will likely appear first when using the x64 compiler, and much later with the x86 compiler. x64 will have at least 4 sections associated with each function compiled **/Gy** or inlined from templates or class-inline: code, pdata, and debug info, and possibly xdata.  X86 won’t have the pdata.