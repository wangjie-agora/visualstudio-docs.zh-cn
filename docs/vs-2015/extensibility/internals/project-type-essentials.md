---
title: 项目类型基础知识 |Microsoft Docs
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
- project types [Visual Studio SDK]
ms.assetid: 09991589-2300-430e-b6a4-7f2b95fe676f
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: dd2c0db72cce80f5345475dfd7e82b019b0ec22a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47480636"
---
# <a name="project-type-essentials"></a>项目类型基础知识
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[项目类型基础知识](https://docs.microsoft.com/visualstudio/extensibility/internals/project-type-essentials)。  
  
[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 包括几种语言的项目类型，如[!INCLUDE[csprcs](../../includes/csprcs-md.md)]或[!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]。 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 此外可以创建自己的项目类型。  
  
 如果只是想要添加自定义命令、 编辑器或到工具窗口[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]，可以完成，而不必创建新的项目类型。 有关详细信息，请参阅下列主题：  
  
-   [命令、菜单和工具栏](../../extensibility/internals/commands-menus-and-toolbars.md)  
  
-   [编辑器和语言服务扩展](../../extensibility/editor-and-language-service-extensions.md)  
  
-   [扩展和自定义工具窗口](../../extensibility/extending-and-customizing-tool-windows.md)  
  
 同样，如果你想要自定义所提供的行为[!INCLUDE[csprcs](../../includes/csprcs-md.md)]和[!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]可以执行的项目类型，因此，使用项目子类型。 有关详细信息，请参阅[项目子类型](../../extensibility/internals/project-subtypes.md)。  
  
 必须创建新项目类型的项目的基于一种语言以外[!INCLUDE[csprcs](../../includes/csprcs-md.md)]和[!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]如果你想要支持的一个或多项操作：  
  
-   生成  
  
-   部署  
  
-   多个配置  
  
-   源代码管理  
  
-   调试  
  
-   在解决方案资源管理器中的项目项  
  
-   **打开项目**或**新项目**对话框  
  
-   项目嵌套  
  
-   项目类型的功能的详细信息，请参阅：  
  
-   项目类型是在 VSPackage 中实现的接口集的对象[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]要求。 如果你使用 C# 开发的项目类型，托管包框架项目类为您实现必要的接口，让您继承该实现。 有关详细信息，请参阅[使用托管包框架来实现一种项目类型 (C#)](../../extensibility/internals/using-the-managed-package-framework-to-implement-a-project-type-csharp.md)。  
  
-   对于 c + + 开发人员，HierUtil 库中的类以类似的方式工作。 有关详细信息，请参阅[不在生成： 使用 HierUtil7 项目类以实现项目类型 （c + +）](http://msdn.microsoft.com/en-us/a5c16a09-94a2-46ef-87b5-35b815e2f346)。  
  
-   项目类型可支持典型的源代码生成为.exe 或.dll 程序集的代码文件之外的数据。 例如，[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]数据库项目包含对存储在磁盘上的脚本和查询文件的引用，并将命令添加到**解决方案资源管理器**执行脚本和针对数据库中，但项目的查询不支持生成行为。 有关详细信息，请参阅[打开和保存项目项](../../extensibility/internals/opening-and-saving-project-items.md)。  
  
-   项目类型无需在所有使用的文件。 例如，项目类型可以存储在数据库中的所有数据。 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 为项目类型提供完全控制如何将项目和项目项的数据的保存。 有关详细信息，请参阅[项目类型设计决策](../../extensibility/internals/project-type-design-decisions.md)。  
  
-   项目类型必须提供*项目工厂*，这是一个对象创建的项目实例，只要键入[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]所指示的打开或创建基于该项目类型的项目。 有关详细信息，请参阅[创建项目实例通过使用项目工厂](../../extensibility/internals/creating-project-instances-by-using-project-factories.md)。  
  
-   项目类型必须提供用于项目和项目项模板。 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 当用户创建新的项目，并将新项添加到现有项目，请使用模板。 有关详细信息，请参阅[添加项目和项目项模板](../../extensibility/internals/adding-project-and-project-item-templates.md)。  
  
-   项目类型可支持多个配置，例如调试和发布。 用户可以通过使用你提供的属性页更改项目的不同配置。 有关详细信息，请参阅[管理配置选项](../../extensibility/internals/managing-configuration-options.md)。  
  
## <a name="see-also"></a>请参阅  
 [部署项目类型](../../extensibility/internals/deploying-project-types.md)
