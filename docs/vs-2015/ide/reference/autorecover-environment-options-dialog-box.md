---
title: “选项”对话框 ->“环境”->“自动恢复”| Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPag.Environment.AutoRecover
- VS.DialogAutoRestore
- VS.ToolsOptionsPages.Environment.AutoRecover
- VS.ToolsOptionsPages.Environment.Auto_Save_and_Restore
helpviewer_keywords:
- files, recovering
- AutoRecover page
- saving files, automatically
- files, saving automatically
ms.assetid: 397e5e44-4bbe-4289-94d1-642b466c9111
caps.latest.revision: 18
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 743543e03806a842eabc2bbfc69011d63b1264d0
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "72660965"
---
# <a name="autorecover-environment-options-dialog-box"></a>“选项”对话框 ->“环境”->“自动恢复”
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

使用选项对话框中的此页可指定是否自动备份文件。 使用此页，还可指定当集成开发环境 (IDE) 意外关闭时是否还原已修改的文件。 要访问此对话框，请依次选择“工具”菜单->“选项”->“环境”文件夹->“自动恢复”页****************。 如果此页未出现在列表中，请在“选项”对话框中选择“显示所有设置”********。

> [!NOTE]
> 显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在“工具”菜单上选择“导入和导出设置”。 有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](https://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。

 **每 \<n> 分钟保存自动恢复信息** 使用此选项可以自定义文件在编辑器中自动保存的频率。 对于以前保存的文件，文件的副本保存在 \\ ..\My Documents\Visual Studio \<*version*> \Backup files \\ < *项目名称*> 中。 如果是新文件且尚未手动保存，则将使用一个随机生成的文件名自动保存该文件。

 **保留自动恢复信息的 \<n> 天数** 使用此选项可指定 Visual Studio 为恢复创建的文件保留多长时间。

## <a name="see-also"></a>另请参阅
 ["选项" 对话框](../../ide/reference/options-dialog-box-visual-studio.md)
