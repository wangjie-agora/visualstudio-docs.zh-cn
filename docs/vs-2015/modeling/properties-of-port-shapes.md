---
title: 端口形状的属性 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: reference
f1_keywords:
- vs.dsltools.dsldesigner.port
helpviewer_keywords:
- Domain-Specific Language, port shape
ms.assetid: 9d69c4c1-4f72-4876-96b6-9b846e0495a4
caps.latest.revision: 23
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 906a35f1b564c4e3794d1000f03cb32cda003ca2
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "72671367"
---
# <a name="properties-of-port-shapes"></a>端口形状的属性
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

可以在生成的设计器中使用端口形状来表示域类。

 有关详细信息，请参阅 [如何定义域特定语言](../modeling/how-to-define-a-domain-specific-language.md)。 有关如何使用这些属性的详细信息，请参阅 [自定义和扩展域特定语言](../modeling/customizing-and-extending-a-domain-specific-language.md)。

 端口形状具有下表中列出的属性。

|属性|说明|默认|
|--------------|-----------------|-------------|
|填充颜色|此形状的填充颜色。|白色|
|填充渐变模式|此形状的填充渐变模式。|横向|
|几何结构|此形状的几何图形 (矩形、圆角矩形、椭圆形或圆圈) 。|Rectangle|
|具有默认连接点|如果为 `True` ，则形状将使用生成的设计器中的顶部、底部、左侧和右侧连接点。|错误|
|轮廓颜色|此形状的边框颜色。|黑色|
|空心虚线样式|此形状的边框虚线样式 (纯色、破折号、点、DashDot、DashDotDot 或自定义) 。|单色|
|边框粗细|此形状的边框宽度。|0.03125|
|文本颜色|与此形状相关联的文本修饰器所使用的颜色。|黑色|
|访问修饰符|类的访问级别 (`public` 或 `internal`) 。|公用|
|自定义特性|用于将特性添加到从此形状生成的源代码类中。|\<none>|
|生成双派生|如果为 `True` ，则将生成基类和分部类 (来支持通过重写进行自定义) 。 有关详细信息，请参阅 [重写和扩展生成的类](../modeling/overriding-and-extending-the-generated-classes.md)|错误|
|具有自定义构造函数|如果为 `True` ，则在源代码中提供自定义构造函数。 有关详细信息，请参阅 [重写和扩展生成的类](../modeling/overriding-and-extending-the-generated-classes.md)。|错误|
|继承修饰符|描述从端口 (或) 生成的源代码类的继承类型 `none` `abstract` `sealed` 。|无|
|基端口|此形状的基类。|（无）|
|名称|此形状的名称。|当前名称|
|命名空间|与此形状关联的命名空间。|当前命名空间|
|工具提示类型|如何定义工具提示 (fixed、variable 或 none) 。 如果已修复，则属性的值 `Fixed Tooltip Text` 将用作工具提示; 如果变量为，则在自定义代码中定义工具提示。|无|
|备注|与此形状相关联的非正式注释。|\<none>|
|初始高度|此形状的初始高度（英寸）。|1|
|初始宽度|此形状的初始宽度（英寸）。|1.5|
|作为属性公开的填充颜色<br /><br /> 公开的填充渐变模式<br /><br /> 作为属性公开的大纲颜色<br /><br /> 已公开大纲虚线样式为属性<br /><br /> 作为属性公开的大纲粗细<br /><br /> 公开文本颜色|如果 `True` 为，则用户可以设置形状的指定属性。 若要设置此项，请右键单击形状定义，然后单击 "添加" " **公开**"。|错误|
|说明|用于记录生成的设计器。|\<none>|
|显示名称|将在生成的设计器中显示的此形状的名称。|\<none>|
|固定工具提示文本|用于固定工具提示的文本。|\<none>|
|帮助关键字|用于索引此形状的 F1 帮助的关键字。|\<none>|

## <a name="see-also"></a>另请参阅
 [域特定语言工具术语表](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
