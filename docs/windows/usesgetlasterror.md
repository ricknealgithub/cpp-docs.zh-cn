---
title: usesgetlasterror |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.usesgetlasterror
dev_langs:
- C++
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 399b9fbbcf4b449f5f91beaea89c403d120d0a21
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890270"
---
# <a name="usesgetlasterror"></a>usesgetlasterror
告知调用方，是否调用该函数时，没有出错，则调用方可以然后调用`GetLastError`以检索的错误代码。  
  
## <a name="syntax"></a>语法  
  
```  
  
[usesgetlasterror]  
  
```  
  
## <a name="remarks"></a>备注  
 **Usesgetlasterror** c + + 属性具有相同的功能[usesgetlasterror](http://msdn.microsoft.com/library/windows/desktop/aa367297) MIDL 特性。  
  
## <a name="example"></a>示例  
 请参阅[idl_module](../windows/idl-module.md)如何使用的示例**usesgetlasterror**。  
  
## <a name="requirements"></a>要求  
  
### <a name="attribute-context"></a>特性上下文  
  
|||  
|-|-|  
|**适用对象**|**模块**属性|  
|**可重复**|否|  
|**必需的特性**|无|  
|**无效的特性**|无|  
  
 有关特性上下文的详细信息，请参见 [特性上下文](../windows/attribute-contexts.md)。  
  
## <a name="see-also"></a>请参阅  
 [IDL 特性](../windows/idl-attributes.md)   
