---
title: "CA1041: Provide ObsoleteAttribute message"
ms.custom: na
ms.date: 10/03/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - vs-devops-test
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: be5bee69-d2d2-44e1-be2e-3ea451969003
caps.latest.revision: 16
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
# CA1041: Provide ObsoleteAttribute message
|||  
|-|-|  
|TypeName|ProvideObsoleteAttributeMessage|  
|CheckId|CA1041|  
|Category|Microsoft.Design|  
|Breaking Change|Non-breaking|  
  
## Cause  
 A type or member is marked by using a <xref:System.ObsoleteAttribute?qualifyHint=True> attribute that does not have its <xref:System.ObsoleteAttribute.Message?qualifyHint=True> property specified.  
  
## Rule Description  
 <xref:System.ObsoleteAttribute?qualifyHint=False> is used to mark deprecated library types and members. Library consumers should avoid the use of any type or member that is marked obsolete. This is because it might not be supported and will eventually be removed from later versions of the library. When a type or member marked by using <xref:System.ObsoleteAttribute?qualifyHint=False> is compiled, the <xref:System.ObsoleteAttribute.Message?qualifyHint=False> property of the attribute is displayed. This gives the user information about the obsolete type or member. This information generally includes how long the obsolete type or member will be supported by the library designers and the preferred replacement to use.  
  
## How to Fix Violations  
 To fix a violation of this rule, add the `message` parameter to the <xref:System.ObsoleteAttribute?qualifyHint=False> constructor.  
  
## When to Suppress Warnings  
 Do not suppress a warning from this rule because the <xref:System.ObsoleteAttribute.Message?qualifyHint=False> property provides critical information about the obsolete type or member.  
  
## Example  
 The following example shows an obsolete member that has a correctly declared <xref:System.ObsoleteAttribute?qualifyHint=False>.  
  
 [!CODE [FxCop.Design.ObsoleteAttributeOnMember#1](../CodeSnippet/VS_Snippets_CodeAnalysis/FxCop.Design.ObsoleteAttributeOnMember#1)]  
  
## See Also  
 <xref:System.ObsoleteAttribute?qualifyHint=True>