---
title: "Address of Overloaded Functions"
ms.custom: na
ms.date: 10/01/2016
ms.devlang: 
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-csharp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: e7913e65-a295-445d-b2b0-1e60f8dfbc54
caps.latest.revision: 8
manager: douge
translation.priority.mt: 
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
# Address of Overloaded Functions
Use of a function name without arguments returns the address of that function. For example:  
  
```  
int Func( int i, int j );  
int Func( long l );  
  
...  
  
int (*pFunc) ( int, int ) = Func;  
```  
  
 In the preceding example, the first version of `Func` is selected, and its address is copied into `pFunc`.  
  
 The compiler determines which version of the function to select by finding a function with an argument list that exactly matches that of the target. The arguments in the overloaded function declarations are matched against one of the following:  
  
-   An object being initialized (as shown in the preceding example)  
  
-   The left side of an assignment statement  
  
-   A formal argument to a function  
  
-   A formal argument to a user-defined operator  
  
-   A function return type  
  
 If no exact match is found, the expression that takes the address of the function is ambiguous and an error is generated.  
  
 Note that although a nonmember function, `Func`, was used in the preceding example, the same rules are applied when taking the address of overloaded member functions.  
  
## See Also  
 [Overloading  (C++)](../VS_not_in_toc/Overloading---C---.md)