---
title: 嵌套项目的向导支持 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Add Item wizard
- nested projects, wizard support
- New Project wizard
ms.assetid: 1b496acc-b326-4cdb-bb48-e3b5c6f12e05
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 206fd12ea8f198e1659a49ed566e726e49878c53
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "68180338"
---
# <a name="wizard-support-for-nested-projects"></a>嵌套项目的向导支持
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

IDE 运行可实现嵌套项目的父项目的两个向导： " **新建项目** " 向导和 " **添加项** 向导"。  
  
 如果用户通过在 "文件" 菜单上选择 "**添加项目**" 并单击 "**新建项目**"，或在解决方案资源管理器中选择 "**添加**" 并右键单击 "**新建项目**" 来启动 "**新建**项目" 向导，则 IDE 将运行**AddProject**命令， **AddProject**命令的父项目实现将返回模板项目文件或 ( .vsz) 文件，其中包含一组上下文参数。  
  
 同样，一个父项目的 **AddItem** 向导实现返回一个 .vsz 文件，该文件具有一组不同的上下文参数。  
  
 有关向导的详细信息，请参阅 [向导 (。.Vsz) 文件](../../extensibility/internals/wizard-dot-vsz-file.md)、 [上下文参数](../../extensibility/internals/context-parameters.md) 和 [注册项目和项模板](../../extensibility/internals/registering-project-and-item-templates.md)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>   
 [嵌套项目](../../extensibility/internals/nesting-projects.md)
