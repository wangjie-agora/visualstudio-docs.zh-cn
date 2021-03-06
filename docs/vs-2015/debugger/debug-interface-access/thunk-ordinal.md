---
title: THUNK_ORDINAL | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- Thunk_Ordinal enumeration
ms.assetid: 026f98a9-36b8-41ef-8a72-12d7cbc2d362
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: b98098c0b6e1de9c3c2ceda5c644bc2957ab22bd
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "62576403"
---
# <a name="thunk_ordinal"></a>THUNK_ORDINAL
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

指定 thunk 类型。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
typedef enum THUNK_ORDINAL {   
   THUNK_ORDINAL_NOTYPE,  
   THUNK_ORDINAL_ADJUSTOR,  
   THUNK_ORDINAL_VCALL,  
   THUNK_ORDINAL_PCODE,  
   THUNK_ORDINAL_LOAD   
  
   // trampoline thunk ordinals - only for use in Trampoline thunk symbols  
   THUNK_ORDINAL_TRAMP_INCREMENTAL,  
   THUNK_ORDINAL_TRAMP_BRANCHISLAND,  
} THUNK_ORDINAL;  
```  
  
## <a name="elements"></a>元素  
 THUNK_ORDINAL_NOTYPE  
 标准 thunk。  
  
 THUNK_ORDINAL_ADJUSTOR  
 `this`Adjustor thunk。  
  
 THUNK_ORDINAL_VCALL  
 虚调用 thunk。  
  
 THUNK_ORDINAL_PCODE  
 P 代码 thunk。  
  
 THUNK_ORDINAL_LOAD  
 延迟加载 thunk。  
  
 THUNK_ORDINAL_TRAMP_INCREMENTAL  
 增量 trampoline thunk (trampoline thunk 用于将调用从一个内存空间弹跳到另一个) 。  
  
 THUNK_ORDINAL_TRAMP_BRANCHISLAND  
 分支点 trampoline thunk。  
  
## <a name="remarks"></a>备注  
 此枚举中的值从对 [IDiaSymbol：： get_thunkOrdinal](../../debugger/debug-interface-access/idiasymbol-get-thunkordinal.md) 方法的调用返回。  
  
## <a name="requirements"></a>要求  
 标头： cvconst  
  
## <a name="see-also"></a>另请参阅  
 [枚举和结构](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_thunkOrdinal](../../debugger/debug-interface-access/idiasymbol-get-thunkordinal.md)
