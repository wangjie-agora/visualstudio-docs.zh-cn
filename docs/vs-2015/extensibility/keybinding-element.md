---
title: 键绑定元素 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- VSCT XML schema elements, KeyBindings
- KeyBinding element (VSCT XML schema)
ms.assetid: e55a1098-15df-42a9-9f87-e3a99cf437dd
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 75d96098e8444aac9a4fc6f895099435b54f640b
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "68180330"
---
# <a name="keybinding-element"></a>KeyBinding 元素
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

键绑定元素指定命令的键盘快捷方式。  
  
 命令可以有与之关联的单键和双键绑定。 对于 " **保存** " 命令，一个键绑定的示例为 CTRL + S。 双键绑定需要两个连续的键组合来触发命令。 例如，按 CTRL + K、CTRL + K 来设置书签。  
  
## <a name="syntax"></a>语法  
  
```  
<Keybinding guid="MyGuid" id="MyId" Editor="MyEditor" key1="B" key2="x" mod1="Control" mod2="Alt" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|说明|  
|---------------|-----------------|  
|guid|必需。|  
|id|必需。|  
|编辑器|必需。 编辑器 GUID 指示此键盘快捷键将处于活动状态的编辑上下文。 全局绑定范围值为 "guidVSStd97"。|  
|key1|必需。 有效值包括所有 typable 字母数字，以及以0x 和 VK_constants 开头的两位数十六进制值。|  
|mod1|可选。 由空格分隔的 CTRL、ALT 和 SHIFT 的任意组合。|  
|key2|可选。 有效值包括所有 typable 字母数字，以及以0x 和 VK_constants 开头的两位数十六进制值。|  
|mod2|可选。 由空格分隔的 CTRL、ALT 和 SHIFT 的任意组合。|  
|模拟器|可选。|  
|条件|可选。 请参阅 [条件特性](../extensibility/vsct-xml-schema-conditional-attributes.md)。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|说明|  
|-------------|-----------------|  
|Parent||  
|Annotation||  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|[KeyBindings 元素](../extensibility/keybindings-element.md)|将键绑定元素和其他键绑定分组分组。|  
  
## <a name="example"></a>示例  
  
```  
<KeyBindings>  
  <KeyBinding guid="guidWidgetPackage" id="cmdidUpdateWidget"   
    editor="guidWidgetEditor" key1="VK_F5"/>  
  <KeyBinding guid="guidWidgetPackage" id="cmdidRunWidget"   
    editor="guidWidgetEditor" key1="VK_F5" mod1="Control"/>  
</KeyBindings>  
```  
  
## <a name="see-also"></a>另请参阅  
 [键绑定元素](../extensibility/keybindings-element.md)   
 [Visual Studio 命令表格 (.Vsct) 文件](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
