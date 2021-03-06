---
title: 必须在安装后运行的命令 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- post-install commands
ms.assetid: c9601f2e-2c6e-4da9-9a6e-e707319b39e2
caps.latest.revision: 23
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 158119759f8e90161e1f3b5267be498dfc1c9b38
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "90840733"
---
# <a name="commands-that-must-be-run-after-installation"></a>安装后必须运行的命令
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

如果通过 .msi 文件部署扩展，则必须 `devenv /setup` 在安装过程中运行，Visual Studio 才能发现扩展。  
  
> [!NOTE]
> 本主题中的信息适用于通过 Visual Studio 2008 和更早版本查找 DevEnv。 有关如何在 Visual Studio 的更高版本中发现 DevEnv 的信息，请参阅 [检测系统要求](../../extensibility/internals/detecting-system-requirements.md)。  
  
## <a name="finding-devenvexe"></a>查找 devenv.exe  
 您可以 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 使用 RegLocator 表和 AppSearch 表将注册表值存储为属性，从安装程序编写的注册表值中查找每个版本的 devenv.exe。 有关详细信息，请参阅 [检测系统要求](../../extensibility/internals/detecting-system-requirements.md)。  
  
### <a name="reglocator-table-rows-to-locate-devenvexe-from-different-versions-of-visual-studio"></a>RegLocator 表行，用于从不同版本的 Visual Studio 查找 devenv.exe  
  
|Signature_|Root|键|名称|类型|  
|-----------------|----------|---------|----------|----------|  
|RL_DevenvExe_2002|2|SOFTWARE\Microsoft\VisualStudio\7.0\Setup\VS|EnvironmentPath|2|  
|RL_DevenvExe_2003|2|SOFTWARE\Microsoft\VisualStudio\7.1\Setup\VS|EnvironmentPath|2|  
|RL_DevenvExe_2005|2|SOFTWARE\Microsoft\VisualStudio\8.0\Setup\VS|EnvironmentPath|2|  
|RL_DevenvExe_2008|2|SOFTWARE\Microsoft\VisualStudio\9.0\Setup\VS|EnvironmentPath|2|  
  
### <a name="appsearch-table-rows-for-corresponding-reglocator-table-rows"></a>对应 RegLocator 表行的 AppSearch 表行  
  
|Property|Signature_|  
|--------------|-----------------|  
|DEVENV_EXE_2002|RL_DevenvExe_2002|  
|DEVENV_EXE_2003|RL_DevenvExe_2003|  
|DEVENV_EXE_2005|RL_DevenvExe_2005|  
|DEVENV_EXE_2008|RL_DevenvExe_2008|  
  
 例如，Visual Studio 安装程序将 **HKEY_LOCAL_MACHINE \software\microsoft\visualstudio\9.0\setup\vs\environmentpath** 的注册表值写入 **C:\VS2008\Common7\IDE\devenv.exe**，这是安装程序必须运行的可执行文件的完整路径。  
  
 **注意** 由于 RegLocator 类型列是2，因此不需要在签名表中指定其他版本信息。  
  
## <a name="running-devenvexe"></a>运行 devenv.exe  
 在安装程序中运行 AppSearch 标准操作后，AppSearch 表中的每个属性都有一个值，该值指向相应版本的 Visual Studio 的 devenv.exe 文件。 如果不存在任何指定的注册表值（因为未安装该版本的 Visual Studio），则指定的属性将设置为 null。  
  
 Windows Installer 支持运行属性指向自定义操作类型50的可执行文件。 自定义操作应包括脚本内执行选项、msidbCustomActionTypeInScript (1024) 和 msidbCustomActionTypeCommit (512) ，以确保在将其集成到之前已成功安装 VSPackage [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 。 有关详细信息，请参阅 CustomAction 表和自定义操作的脚本执行选项。  
  
 类型为50的自定义操作指定包含可执行文件的属性，作为目标列中源列和命令行参数的值。  
  
### <a name="customaction-table-rows-to-run-devenvexe"></a>要运行的 CustomAction 表行 devenv.exe  
  
|操作|类型|Source|目标|  
|------------|----------|------------|------------|  
|CA_RunDevenv2002|1586|DEVENV_EXE_2002|/setup|  
|CA_RunDevenv2003|1586|DEVENV_EXE_2003|/setup|  
|CA_RunDevenv2005|1586|DEVENV_EXE_2005|/setup|  
|CA_RunDevenv2008|1586|DEVENV_EXE_2008|/setup|  
  
 必须将自定义操作编写到 InstallExecuteSequence 表中，以便在安装过程中计划执行这些操作。 使用 "条件" 列的每一行中的相应属性可防止在 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 系统上未安装该版本的时运行自定义操作。  
  
> [!NOTE]
> `Null` 在条件中使用时，属性的计算结果为 `False` 。  
  
 每个自定义操作的序列列的值取决于 Windows Installer 包中的其他序列值。 序列值应满足 devenv.exe 自定义操作在 InstallFinalize 标准操作之前尽可能接近。  
  
### <a name="installexecutesequence-table-to-schedule-the-devenvexe-custom-actions"></a>用于计划 devenv.exe 自定义操作的 InstallExecuteSequence 表  
  
|操作|条件|序列|  
|------------|---------------|--------------|  
|CA_RunDevenv2002|DEVENV_EXE_2002|6602|  
|CA_RunDevenv2003|DEVENV_EXE_2003|6603|  
|CA_RunDevenv2005|DEVENV_EXE_2005|6605|  
|CA_RunDevenv2008|DEVENV_EXE_2008|6608|  
  
## <a name="see-also"></a>另请参阅  
 [使用 Windows Installer 安装 VSPackage](../../extensibility/internals/installing-vspackages-with-windows-installer.md)
