---
title: "Overload resolution failed because no accessible &#39;&lt;genericprocedurename&gt;&#39; accepts this number of type arguments"
ms.custom: na
ms.date: 10/01/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-csharp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: a3eaafd3-80f6-4b7d-9b75-47b043fe17b5
caps.latest.revision: 11
manager: douge
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
# Overload resolution failed because no accessible &#39;&lt;genericprocedurename&gt;&#39; accepts this number of type arguments
A call to an overloaded generic procedure cannot be resolved because the compiler cannot access any overloaded version with the appropriate number of type parameters.  
  
 When you call a generic procedure, you must supply one type argument for each type parameter. Alternatively, you can supply no type arguments at all and let the compiler attempt to do *type inference*. For more information, see "Type Inference" in [Generic Procedures in Visual Basic](../Topic/Generic%20Procedures%20in%20Visual%20Basic.md).  
  
 **Error ID:** BC32087  
  
### To correct this error  
  
1.  Ensure that the version you intend to call is accessible by the calling code. See [Access Levels in Visual Basic](../Topic/Access%20Levels%20in%20Visual%20Basic.md).  
  
2.  Add or remove type arguments from your calling code so that the type argument list matches the type parameter list of the version you intend to call.  
  
     -or-  
  
     Remove all type arguments from your calling code and let the compiler attempt to do type inference. Be aware that type inference can fail if there are conflicts or ambiguities.  
  
## See Also  
 [Overloaded Properties and Methods](../Topic/Overloaded%20Properties%20and%20Methods%20\(Visual%20Basic\).md)   
 [Overload Resolution](../Topic/Overload%20Resolution%20\(Visual%20Basic\).md)   
 [Generic Types in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Type List](../Topic/Type%20List%20\(Visual%20Basic\).md)