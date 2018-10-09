---
title: 如何：导出包含预乘 Alpha 的纹理 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 05348afa-f079-4f53-a05b-ecd91d13adab
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d5089ff81121e9390968fe7e3900eb28cededc27
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47469492"
---
# <a name="how-to-export-a-texture-that-has-premultiplied-alpha"></a>如何：导出包含自左乘的 Alpha 的纹理
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[如何： 导出包含自左乘的 Alpha 的纹理](https://docs.microsoft.com/visualstudio/designers/how-to-export-a-texture-that-has-premultiplied-alpha)。  
  
图像内容管道可从源图像生成预乘 Alpha 纹理。 这些纹理比不包含预乘 alpha 的纹理更易于使用且更可靠。  
  
 本文档演示了这些活动：  
  
-   将源映像配置为由图像内容管道进行处理。  
  
-   配置图像内容管道以生成预乘 alpha。  
  
## <a name="premultiplied-alpha"></a>预乘 Alpha  
 预乘的 alpha 具有相对于传统的、 非预乘 alpha 的许多优点，因为它来分离纹素的颜色量更好地体现了与物理材质的光线现实世界交互 (它将添加到的颜色场景） 通过的底色 （允许通过基础颜色量）。 使用预乘 Alpha 的一些优点为：  
  
-   与预乘 Alpha 混合的是一种结合性运算，无论按何种顺序混合纹理，混合多个半透明纹理的结果都是相同的。  
  
-   因为混合预乘 Alpha 具有结合性，所以简化了半透明对象的多通渲染。  
  
-   通过使用预乘 Alpha，可以同时实现纯附加混合（通过将 Alpha 设置为零）和线性内插混合。 例如，在粒子系统中，附加混合的火粒子可能会成为通过使用线性内插的半透明烟粒子。 如果没有预乘 Alpha，将需要在烟粒子之外单独绘制火粒子，并修改绘图调用间的呈现状态。  
  
-   使用预乘的 alpha 的纹理压缩较高的质量比不这样做，并且它们不显示变色的边缘，或"晕效果"—，则可能导致时不要使用预乘的 alpha 的纹理。  
  
#### <a name="to-create-a-texture-that-uses-premultiplied-alpha"></a>创建使用预乘 Alpha 的纹理  
  
1.  从基本纹理开始。 加载现有图像文件，或根据[如何：创建基本纹理](../designers/how-to-create-a-basic-texture.md)所述，创建一个纹理。  
  
2.  配置纹理文件，以便由图像内容管道处理。 在“解决方案资源管理器”中，打开纹理文件的快捷菜单，然后选择“属性”。 在“配置属性”，常规”页上，将“项目类型”属性设置为“图像内容管道”。 请确保将“内容”属性设置为“是”，并且将“从生成中排除”设置为“否”，然后选择“应用”按钮。 将出现“图像内容管道”配置属性页。  
  
3.  配置图像内容管道，生成预乘 Alpha。 在“配置属性”、“图像内容管道”、“常规”页上，将“转换为预乘 alpha 格式”属性设置为“是(/generatepremultipliedalpha)”。  
  
4.  选择“确定”  按钮。  
  
 生成项目时，图像内容管道源映像将从工作格式转换为指定的输出格式，这包括将图像转换为预乘 alpha 格式，并将结果复制到项目的输出目录。


