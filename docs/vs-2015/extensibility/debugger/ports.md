---
title: 端口 |Microsoft Docs
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
- ports
- debugging [Debugging SDK], ports
ms.assetid: 1d7f3aa7-7eff-4cab-bc53-0a566b1a9363
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: dbc8778af1cbc82b4f9e7f577a95123a1c1f5843
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47472056"
---
# <a name="ports"></a>端口
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[端口](https://docs.microsoft.com/visualstudio/extensibility/debugger/ports)。  
  
在调试器体系结构，方面**端口**:  
  
-   服务器上运行的进程组的容器。 例如，端口可能表示连接到基于 Windows CE 的设备的串行电缆或网络的非 DCOM 计算机。 一个特殊的端口，称为本地端口，包含在本地计算机上运行的所有进程。  
  
-   可以将自己标识的名称或标识符。  
  
-   可枚举的端口上运行的所有进程和启动并终止这些进程。  
  
-   为由[IDebugPort2](../../extensibility/debugger/reference/idebugport2.md)接口，通过将传递创建[IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md)参数[端口](../../extensibility/debugger/reference/idebugportsupplier2-addport.md)。  
  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 提供了处理所有基于 Windows 的进程，本机和托管的默认端口。 自定义端口必须与不是基于 Windows 的外部设备实现的连接。 若要提供此类自定义端口，自定义端口提供程序还需要实现。  
  
## <a name="see-also"></a>请参阅  
 [服务器](../../extensibility/debugger/servers-visual-studio-sdk.md)   
 [进程](../../extensibility/debugger/processes.md)   
 [调试器概念](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md)   
 [IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md)   
 [AddPort](../../extensibility/debugger/reference/idebugportsupplier2-addport.md)
