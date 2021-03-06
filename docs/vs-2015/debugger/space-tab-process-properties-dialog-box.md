---
title: “进程属性”对话框 ->“空间”选项卡 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Process properties for Windows NT
ms.assetid: c4de1866-7447-48f7-aa88-28ad92c0b930
caps.latest.revision: 7
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: de5df4c55feba8c9aaba0def7585029cc71426b5
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "68189430"
---
# <a name="space-tab-process-properties-dialog-box"></a>“进程属性”对话框 ->“空间”选项卡
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

使用“空间”选项卡可检查进程的地址空间。 若要显示[“进程属性”对话框](../debugger/process-properties-dialog-box.md)，请将焦点移动到[进程视图](../debugger/processes-view.md)窗口。 在树中选择任意进程节点，然后从“视图”菜单选择“属性” 。  
  
 “空间”选项卡上有以下可用设置：  
  
|条目|描述|  
|-----------|-----------------|  
|**显示这种标记的空间**|使用此列表框可选择空间的类别（图像、映射、保留或未分配）。|  
|**可执行字节数**|对于所选类别，其为此进程正在使用的所有地址空间的总和。 可执行内存是可以由程序执行，但可能无法进行读取或写入的内存。|  
|**可执行只读字节数**|对于所选类别，其为此进程正在使用的具有只读属性的所有地址空间的总和。 可执行只读内存是可以进行执行和读取的内存。|  
|**可执行读写字节数**|对于所选类别，其为此进程正在使用的具有读写属性的所有地址空间的总和。 可执行读写内存是可以由程序执行以及进行读取和修改的内存。|  
|**可执行写入副本字节数**|对于所选类别，其为可以由程序执行以及进行读取和写入的所有地址空间的总和。 如果需要在进程之间共享内存，则使用这种类型的保护。 如果共享进程仅读取内存，则它们将全部使用相同的内存。 如果共享进程需要写入访问权限，则将为该进程创建此内存的副本。|  
|**不可访问字节数**|对于所选类别，其为阻止进程对其进行使用的所有地址空间的总和。 如果尝试写入或读取，会生成访问冲突。|  
|**只读字节数**|对于所选类别，其为可以进行执行和读取的所有地址空间的总和。|  
|**读写字节数**|对于所选类别，其为允许进行读取和写入的所有地址空间的总和。|  
|**写复制字节数**|对于所选类别，其为允许进行内存共享（以供读取）但不允许进行写入的所有地址空间的总和。 当进程读取此内存时，它们可以共享相同的内存。 但是，当共享进程需要对此共享内存具有读取/写入访问权限时，将生成该内存的副本以供写入。|
