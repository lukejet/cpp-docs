---
title: "to Functions"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - C++
  - C
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: article
apilocation: 
  - msvcr120.dll
  - msvcr90.dll
  - msvcr110.dll
  - msvcr110_clr0400.dll
  - msvcr80.dll
  - msvcr100.dll
apitype: DLLExport
ms.assetid: f636a4c6-8c9f-4be2-baac-064f9dbae300
caps.latest.revision: 11
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
# to Functions
Each of the **to** functions and its associated macro, if any, converts a single character to another character.  
  
|||  
|-|-|  
|[__toascii](../VS_visualcpp/toascii--__toascii.md)|[toupper, _toupper, towupper](../VS_visualcpp/toupper--_toupper--towupper--_toupper_l--_towupper_l.md)|  
|[tolower, _tolower, towlower](../VS_visualcpp/tolower--_tolower--towlower--_tolower_l--_towlower_l.md)||  
  
## Remarks  
 The **to** functions and macro conversions are as follows.  
  
|Routine|Macro|Description|  
|-------------|-----------|-----------------|  
|`__toascii`|`__toascii`|Converts `c` to ASCII character|  
|`tolower`|`tolower`|Converts `c` to lowercase if appropriate|  
|`_tolower`|`_tolower`|Converts `c` to lowercase|  
|`towlower`|None|Converts `c` to corresponding wide-character lowercase letter|  
|`toupper`|`toupper`|Converts `c` to uppercase if appropriate|  
|`_toupper`|`_toupper`|Converts `c` to uppercase|  
|`towupper`|None|Converts c to corresponding wide-character uppercase letter|  
  
 To use the function versions of the **to** routines that are also defined as macros, either remove the macro definitions with `#undef` directives or do not include CTYPE.H. If you use the /Za compiler option, the compiler uses the function version of `toupper` or `tolower`. Declarations of the `toupper` and `tolower` functions are in STDLIB.H.  
  
 The `__toascii` routine sets all but the low-order 7 bits of `c` to 0, so that the converted value represents a character in the ASCII character set. If `c` already represents an ASCII character, `c` is unchanged.  
  
 The `tolower` and `toupper` routines:  
  
-   Are dependent on the `LC_CTYPE` category of the current locale (`tolower` calls `isupper` and `toupper` calls `islower`).  
  
-   Convert `c` if `c` represents a convertible letter of the appropriate case in the current locale and the opposite case exists for that locale. Otherwise, `c` is unchanged.  
  
 The `_tolower` and `_toupper` routines:  
  
-   Are locale-independent, much faster versions of `tolower` and **toupper.**  
  
-   Can be used only when **isascii(**`c`**)** and either **isupper(**`c`**)** or **islower(**`c`**)**, respectively, are nonzero.  
  
-   Have undefined results if `c` is not an ASCII letter of the appropriate case for converting.  
  
 The `towlower` and `towupper` functions return a converted copy of `c` if and only if both of the following conditions are nonzero. Otherwise, `c` is unchanged.  
  
-   `c` is a wide character of the appropriate case (that is, for which `iswupper` or **iswlower,** respectively, is nonzero).  
  
-   There is a corresponding wide character of the target case (that is, for which `iswlower` or **iswupper,** respectively, is nonzero).  
  
## Example  
  
```  
// crt_toupper.c  
/* This program uses toupper and tolower to  
 * analyze all characters between 0x0 and 0x7F. It also  
 * applies _toupper and _tolower to any code in this  
 * range for which these functions make sense.  
 */  
  
#include <ctype.h>  
#include <string.h>  
  
char msg[] = "Some of THESE letters are Capitals.";  
char *p;  
  
int main( void )  
{  
   printf( "%s\n", msg );  
  
   /* Reverse case of message. */  
   for( p = msg; p < msg + strlen( msg ); p++ )  
   {  
      if( islower( *p ) )  
         putchar( _toupper( *p ) );  
      else if( isupper( *p ) )  
         putchar( _tolower( *p ) );  
      else  
         putchar( *p );  
   }  
}  
```  
  
 **Some of THESE letters are Capitals.**  
**sOME OF these LETTERS ARE cAPITALS.**   
## See Also  
 [Data Conversion](../VS_visualcpp/Data-Conversion.md)   
 [Locale](../VS_visualcpp/Locale.md)   
 [is, isw Routines](../VS_visualcpp/is--isw-Routines.md)