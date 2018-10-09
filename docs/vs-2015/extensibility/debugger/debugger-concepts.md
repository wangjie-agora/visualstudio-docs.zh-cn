---
title: 调试器概念 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK]
ms.assetid: 2d371d38-f1a0-4a9a-8ea3-100e8c0149b7
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ec7d32d19b6b2bac906bb974e2e17f86efd45243
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47481159"
---
# <a name="debugger-concepts"></a>调试器概念
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[调试器概念](https://docs.microsoft.com/visualstudio/extensibility/debugger/debugger-concepts)。  
  
若要在 Visual Studio 调试包上构建，需要熟悉在设计包中使用的体系结构概念。  
  
## <a name="in-this-section"></a>本节内容  
 [调试会话](../../extensibility/debugger/debug-session.md)  
 介绍会话的调试体系结构中的角色。  
  
 [服务器](../../extensibility/debugger/servers-visual-studio-sdk.md)  
 定义哪台服务器是在抽象和物理条款中的调试体系结构方面。  
  
 [端口提供程序](../../extensibility/debugger/port-suppliers.md)  
 定义端口提供程序是在调试体系结构方面。  
  
 [端口](../../extensibility/debugger/ports.md)  
 定义哪些端口是在调试体系结构方面。  
  
 [进程](../../extensibility/debugger/processes.md)  
 定义哪些进程是在调试体系结构方面。  
  
 [程序节点](../../extensibility/debugger/program-nodes.md)  
 定义根据调试体系结构，包括如何它可以标识本身和它正在运行中的进程的程序节点。  
  
 [程序](../../extensibility/debugger/programs.md)  
 定义在调试体系结构方面的程序。  
  
 [线程](../../extensibility/debugger/threads.md)  
 定义线程在调试体系结构方面的特征。  
  
 [堆栈帧](../../extensibility/debugger/stack-frames.md)  
 定义在调试体系结构方面的堆栈帧。 堆栈帧是堆栈提供一个线程的执行上下文的抽象。  
  
 [模块](../../extensibility/debugger/modules.md)  
 定义模块，在调试的代码，如可执行文件或 DLL 的物理容器体系结构方面。  
  
 [断点](../../extensibility/debugger/breakpoints-visual-studio-sdk.md)  
 定义了三种类型的断点，挂起、 绑定和错误 — 在调试体系结构方面。  
  
## <a name="related-sections"></a>相关章节  
 [调试器上下文](../../extensibility/debugger/debugger-contexts.md)  
 介绍了调试引擎 (DE) 的运行方式同时代码、 文档和表达式计算上下文中。 介绍的三个上下文、 位置、 位置或与它相关评估每个。  
  
 [调试器组件](../../extensibility/debugger/debugger-components.md)  
 概述 Visual Studio 调试组件，包括调试引擎 (DE)、 表达式计算器 (EE) 和符号处理程序 (SH)。  
  
 [调试任务](../../extensibility/debugger/debugging-tasks.md)  
 包含指向不同的调试任务，如启动程序和计算表达式。
