---
title: 如何：使用查找程序工具 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Window Finder Tool
ms.assetid: 5841926b-08c3-4e43-88bd-4223d04f9aef
caps.latest.revision: 9
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 00535fd336f504afcebdd24a4d009a10f7f6ff33
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "90840624"
---
# <a name="how-to-use-the-finder-tool"></a>如何：使用查找程序工具
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

可以使用“查找窗口”对话框中的查找程序工具显示窗口属性或消息。 查找程序工具还可以查找禁用的子窗口，并在禁用的子窗口重叠时识别要突出显示的窗口。  
  
 ![Spy&#43;&#43; 查找窗口 "对话框](../debugger/media/icon-spy-find.png "Icon_Spy++_Find")  
"查找窗口" 对话框中的查找器工具  
  
 上图显示了下面的步骤 3 之后的“查找窗口”对话框。  
  
### <a name="to-display-window-properties-or-messages"></a>显示窗口属性或消息  
  
1. 排列窗口，使 Spy++ 和目标窗口都可见。  
  
2. 从“Spy”菜单中，选择“查找窗口” 。  
  
     [“查找窗口”对话框](../debugger/find-window-dialog-box.md)打开。  
  
3. 将查找程序工具拖到目标窗口之上。  
  
     拖动该工具时，“查找窗口”对话框将显示有关所选窗口的详细信息。  
  
     - 或 -  
  
     如果你有要检查的窗口的句柄（例如，从调试器复制），请将其键入到“句柄”文本框中。  
  
    > [!TIP]
    > 若要减少屏幕干扰，请选择“隐藏 Spy”选项。 此选项会隐藏 Spy++ 主窗口，但“查找窗口”对话框仍显示在其他应用程序的前面。 单击“确定”或“取消”时，或清除“隐藏 Spy++”选项时，将还原 Spy++ 主窗口  。  
  
4. 在“显示”下，选择“属性”或“消息”  。  
  
5. 按“确定”。  
  
     如果选择“属性”，则会打开[“窗口属性”对话框](../debugger/window-properties-dialog-box.md)。 如果选择“消息”，则会打开“[消息视图](../debugger/messages-view.md)”窗口。  
  
## <a name="see-also"></a>另请参阅  
 [Spy + + 视图](../debugger/spy-increment-views.md)   
 [使用 Spy + +](../debugger/using-spy-increment.md)   
 [Spy++ 参考](../debugger/spy-increment-reference.md)
