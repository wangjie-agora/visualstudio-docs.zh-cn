---
title: 文本模板转换过程 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- text templates, transformation process
ms.assetid: 80b3f0e0-49e7-4865-a1ac-dba068abe96b
caps.latest.revision: 32
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 7322724b2118cb8b844262696a6e7cbd91a74e9b
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "72658497"
---
# <a name="the-text-template-transformation-process"></a>文本模板转换过程
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

文本模板转换过程会将文本模板文件作为输入，并生成一个新的文本文件作为输出。 例如，您可以使用文本模板来生成 Visual Basic 或 c # 代码，也可以生成 HTML 报表。

 此过程中包含三个组件：引擎、主机和指令处理器。 引擎控制进程;它与主机和指令处理器进行交互，以生成输出文件。 宿主提供与环境的任何交互，如查找文件和程序集。 指令处理器添加功能，如从 XML 文件或数据库读取数据。

 在两个步骤中执行文本模板转换过程。 首先，引擎创建一个临时类，称为生成转换类。 此类包含指令和控制块生成的代码。 在此之后，该引擎将编译并执行生成的转换类来生成输出文件。

## <a name="components"></a>组件

|组件|说明|可自定义 (是/否) |
|---------------|-----------------|------------------------------|
|引擎|引擎组件控制文本模板转换过程|不是。|
|主机|宿主是引擎和用户环境之间的接口。 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 是文本转换过程的宿主。|是的。 可以编写自定义主机。|
|指令处理器|指令处理器是在文本模板中处理指令的类。 您可以使用指令向输入源中的文本模板提供数据。|是的。 您可以编写自定义指令处理器|

## <a name="the-engine"></a>引擎
 引擎接收来自主机的模板，该模板用于处理转换进程中使用的所有文件。 然后，引擎会要求主机找到任何自定义指令处理器和环境的其他方面。 然后，引擎将编译并运行生成的转换类。 引擎将生成的文本返回到宿主，这通常会将文本保存到文件中。

## <a name="the-host"></a>主机
 宿主负责在转换过程之外与环境相关的任何内容，包括以下各项：

- 查找引擎或指令处理器请求的文本和二进制文件。 宿主可以搜索目录和全局程序集缓存以定位程序集。 宿主可以找到引擎的自定义指令处理器代码。 宿主还可以查找并读取文本文件，并将其内容作为字符串返回。

- 提供引擎用来创建生成转换类的标准程序集和命名空间的列表。

- 提供引擎编译和执行生成的转换类时使用的应用程序域。 使用单独的应用程序域，以防止主机应用程序在模板代码中出现错误。

- 写入生成的输出文件。

- 设置生成的输出文件的默认扩展。

- 处理文本模板转换错误。 例如，主机可以在用户界面中显示错误或将错误写入文件。  (在中 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ，错误将显示在错误消息窗口中。 ) 

- 如果用户在未提供值的情况下调用了指令，则提供所需的参数值。 指令处理器可以指定指令的名称和参数，并要求主机提供默认值（如果有）。

## <a name="directives-and-directive-processors"></a>指令和指令处理器
 指令是文本模板中的一个命令。 它为生成过程提供参数。 通常，指令定义模型的源和类型、其他输入和输出文件的文件扩展名。

 指令处理器可以处理一个或多个指令。 转换模板时，必须安装可处理模板中的指令的指令处理器。

 指令的工作方式是在生成的转换类中添加代码。 从文本模板调用指令，引擎将在创建生成的转换类时处理所有指令调用。 成功调用指令后，在文本模板中编写的代码的其余部分可以依赖于指令提供的功能。 例如，可以在模板中对指令进行以下调用 `import` ：

 `<#@ import namespace="System.Text" #>`

 标准指令处理器将此转换为 `using` 生成的转换类中的语句。 然后，你可以 `StringBuilder` 在模板代码的其余部分中使用类，而无需将其限定为 `System.Text.StringBuilder` 。
