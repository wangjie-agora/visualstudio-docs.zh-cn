---
title: 使用代码分析工具分析应用程序质量 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.analysisresults
helpviewer_keywords:
- application quality, analyzing
- code analysis
- team-based development, analyzing application quality
ms.assetid: 21680516-ddb5-446d-90d4-19d94f6ec699
caps.latest.revision: 26
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: f8ec0706530cd61653d44533654cf453d25eb42e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "75919073"
---
# <a name="analyzing-application-quality-by-using-code-analysis-tools"></a>使用代码分析工具分析应用程序质量
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本部分中的 " [分析](../code-quality/analyzing-managed-code-quality-by-using-code-analysis.md) 托管代码的 Visual Studio 代码分析" 一节提供有关托管程序集的信息，如 Microsoft .NET 框架设计准则中规定的编程和设计规则的冲突。 警告消息标识任何相关的编程和设计问题，如有可能，还提供有关如何修复问题的信息。

 [使用代码分析来分析 c/c + + 代码质量](../code-quality/analyzing-c-cpp-code-quality-by-using-code-analysis.md) C/c + + 代码分析工具向开发人员提供有关其 C/c + + 源代码中可能存在的缺陷的信息。 该工具报告的常见编码错误包括缓冲区溢出、内存未初始化、null 指针取消引用，以及内存和资源泄漏。

 [使用规则集对代码分析规则进行分组](../code-quality/using-rule-sets-to-group-code-analysis-rules.md) 选择并创建要应用于项目的 *规则集* 。

 [代码分析应用程序错误](../code-quality/code-analysis-application-errors.md) 修复代码分析功能中的错误。

 [利用团队项目签入策略提高代码质量](../code-quality/enhancing-code-quality-with-team-project-check-in-policies.md) 使用 Team Foundation 版本控制 (TFVC) 时，可以为团队项目创建签入策略，以强制实施实现更好代码和更高效的组开发的做法。 签入策略是在团队项目级别设置的，并在允许代码签入之前在开发人员计算机上强制实施的规则。

### <a name="code-analysis-for-drivers"></a>驱动程序的代码分析
 通过系统地分析驱动程序源代码，代码分析工具可以帮助提高驱动程序的稳定性和可靠性。

 [使用代码分析工具分析驱动程序质量](/windows-hardware/drivers/devtest/tools-for-verifying-drivers) 驱动程序的代码分析是一种编译时静态验证工具，用于检测 C 和 c + + 程序中的基本编码错误，并且包括专用模块，旨在检测 (主要) 的内核模式驱动程序代码中的错误。 静态驱动程序验证程序 (SDV) 是系统地分析 Windows 内核模式驱动程序的源代码的静态验证工具。 SDV 确定驱动程序是否与 Windows 操作系统内核正确交互。

 [驱动程序警告的代码分析](/windows-hardware/drivers/devtest/prefast-for-drivers-warnings) 描述当驱动程序的代码分析在驱动程序代码中检测到可能的错误时所报告的警告。

## <a name="related-tasks"></a>Related Tasks
 [测量托管代码的复杂性和可维护性](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md) 在此处插入说明。

 [对代码进行单元测试](../test/unit-test-your-code.md) 在此处插入说明。
