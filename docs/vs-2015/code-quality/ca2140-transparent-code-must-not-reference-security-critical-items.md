---
title: CA2140：透明代码不得引用安全关键项 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2129
- SecurityTransparentCodeShouldNotReferenceNonpublicSecurityCriticalCode
- CA2140
helpviewer_keywords:
- CA2140
- SecurityTransparentCodeShouldNotReferenceNonpublicSecurityCriticalCode
- CA2129
ms.assetid: 251a12da-0557-47f5-a4f7-0229d590ae7b
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 6f11125f43fd06b0442d1c40cbd4da41e346fd1d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "85546453"
---
# <a name="ca2140-transparent-code-must-not-reference-security-critical-items"></a>CA2140:透明代码不得引用安全关键项
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|项|值|
|-|-|
|TypeName|TransparentMethodsMustNotReferenceCriticalCode|
|CheckId|CA2140|
|类别|Microsoft.Security|
|是否重大更改|重大|

## <a name="cause"></a>原因
 透明方法：

- 处理安全关键安全异常类型

- 具有标记为安全关键类型的参数

- 具有包含安全关键约束的泛型参数

- 具有安全关键类型的局部变量

- 引用标记为安全关键的类型

- 调用标记为 "安全关键" 的方法

- 引用标记为安全关键的字段

- 返回标记为安全关键的类型

## <a name="rule-description"></a>规则描述
 用特性标记的代码元素 <xref:System.Security.SecurityCriticalAttribute> 是安全关键的。 透明方法不能使用安全关键元素。 如果透明类型尝试使用安全关键类型 <xref:System.TypeAccessException> ， <xref:System.MethodAccessException> <xref:System.FieldAccessException> 则会引发、或。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复与此规则的冲突，请执行以下操作之一：

- 标记使用带有特性的安全关键代码的代码元素 <xref:System.Security.SecurityCriticalAttribute>

     \- 或 -

- <xref:System.Security.SecurityCriticalAttribute>从标记为 "安全关键" 的代码元素删除属性，并将其标记为 <xref:System.Security.SecuritySafeCriticalAttribute> 或 <xref:System.Security.SecurityTransparentAttribute> 属性。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 在下面的示例中，透明方法尝试引用安全关键的泛型集合、安全关键的字段和安全关键方法。

 [!code-csharp[FxCop.Security.CA2140.TransparentMethodsMustNotReferenceCriticalCode#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2140.transparentmethodsmustnotreferencecriticalcode/cs/ca2140 - transparentmethodsmustnotreferencecriticalcode.cs#1)]

## <a name="see-also"></a>另请参阅
 <xref:System.Security.SecurityTransparentAttribute> <xref:System.Security.SecurityCriticalAttribute>
 <xref:System.Security.SecurityTransparentAttribute>
 <xref:System.Security.SecurityTreatAsSafeAttribute>
 <xref:System.Security?displayProperty=fullName>
