---
title: Visual Basic 调试配置的项目设置 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vbProjectPropertiesDebug
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- project settings [Visual Studio], debug configurations
- debug builds, project settings
- debugging [Visual Basic], debugger settings
- projects [Visual Studio], debug configurations
- project configurations, debug
- debug configurations, Visual Basic
ms.assetid: 72a8483a-af0b-4403-8b0d-ee9ad71ee435
caps.latest.revision: 20
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 27acc89790e0759d3b284e3d9a4c6798c3d9a16f
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "65687578"
---
# <a name="project-settings-for-a-visual-basic-debug-configuration"></a>Project Settings for a Visual Basic Debug Configuration
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

可以在“属性页”窗口中更改 [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] 调试配置的项目设置，这在[调试和发布配置](../debugger/how-to-set-debug-and-release-configurations.md)中进行了探讨。 下表显示“属性页”窗口中与调试器有关的设置的位置。  
  
> [!WARNING]
> 本主题不适用于应用商店应用。 请参阅[启动调试会话（VB、C#、C++ 和 XAML）](../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md)  
  
### <a name="debug-tab"></a>“调试”选项卡  
  
|设置|描述|  
|-------------|-----------------|  
|**配置**|设置编译应用程序的模式。 在“活动(调试)”、“调试”、“发布”和“所有配置”之间进行选择   。|  
|**启动操作**|这组控件指定在从“调试”菜单中选择“启动”时将发生的操作。<br /><br /> -   “启动项目”是默认值，用于启动启动项目以供调试。 有关详细信息，请参阅 [笔尖如何：设置启动项目](https://msdn.microsoft.com/31465836-0911-48db-a5d9-e456b635e970)。<br />-   “启动外部程序”用于启动和附加到不属于 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 项目的程序。 有关详细信息，请参阅[附加到运行中的进程](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)。<br />-   “使用 URL 启动浏览器”可用于调试 Web 应用程序。|  
|**命令行参数**|指定要调试的程序的命令行参数。 该命令名是在“启动外部程序”中指定的程序名。 如果“启动操作”设置为“启动 URL”，则忽略命令行自变量。|  
|**工作目录**|指定被调试的程序的工作目录。 在 [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] 中，工作目录就是启动应用程序所在的目录。 默认工作目录是 \bin\Debug 或 \bin\Release，具体取决于当前配置。|  
|**使用远程计算机**|选中此复选框后，将启用远程调试。 在文本框中，可以键入出于调试目的运行应用程序的远程计算机的名称或 [Msvsmon 服务器名称](https://msdn.microsoft.com/library/55b60ce7-834b-4e83-a10e-fe4248260a4c)。 该 EXE 在远程计算机上的位置是由“生成”选项卡中的“输出路径”属性指定的。此位置必须是远程计算机上的共享目录。|  
|**非托管代码调试**|使你能够从托管应用程序中调试对本机（非托管）Win32 代码的调用。 这与在 [!INCLUDE[vcprvc](../includes/vcprvc-md.md)] 项目中为“调试器类型”选择“混合”的效果相同。|  
|**SQL Server 调试**|允许对 SQL Server 数据库对象进行调试。|  
  
### <a name="compile-tab-press-advanced-compile-options-button"></a>编译选项卡：按“高级编译选项”按钮  
  
|设置|描述|  
|-------------|-----------------|  
|**启用优化**|此选项不应选中。 优化会导致实际执行的代码与在 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 中看到的源代码不一样，从而造成调试困难。 如果代码被优化，则在使用“仅我的代码”调试时，默认情况下不加载符号。|  
|**生成调试信息**|默认情况下，调试版本和发布版本中定义了此设置，它（与 /debug 编译器选项等效）在生成时创建调试信息。 在调试时，调试器使用该信息以有用的格式显示变量名和其他信息。 如果编译程序时没有该信息，则调试器的功能将受到限制。 有关详细信息，请参阅 [/debug](https://msdn.microsoft.com/library/c2b0bea5-1d5e-499f-9bd5-4f6c6b715ea2)。|  
|**定义 DEBUG 常量**|定义该符号可启用对 [Debug 类](https://msdn.microsoft.com/library/system.diagnostics.debug.aspx)中的输出函数的条件编译。 定义该符号后，Debug 类方法可向[输出窗口](../ide/reference/output-window.md)生成输出。 如果没有该符号，则 Debug 类方法将不会被编译，并且不生成任何输出。 该符号应在调试版本中定义而不应在发布版本中定义。 在发布版本中定义该符号将创建不必要的代码，从而降低程序的速度。|  
|**定义 TRACE 常量**|定义该符号可启用对 [Trace 类](https://msdn.microsoft.com/library/system.diagnostics.trace.aspx)中的输出函数的条件编译。 定义该符号后，Trace 类方法可向[输出窗口](../ide/reference/output-window.md)生成输出。 如果没有该符号，则 Trace 类方法将不会被编译，并且不生成任何 Trace 输出。 默认情况下，在调试版本和发布版本中都定义了此符号。|  
  
## <a name="see-also"></a>另请参阅  
 [调试器设置和准备](../debugger/debugger-settings-and-preparation.md)
