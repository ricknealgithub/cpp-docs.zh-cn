---
title: library_block |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.library_block
dev_langs:
- C++
helpviewer_keywords:
- library_block attribute
ms.assetid: ae7a7ebe-5e1a-4eda-a058-11bbd058ece8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dbd97897138edffba12baf47d64465b1f6ca0df4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2018
ms.locfileid: "33877886"
---
# <a name="libraryblock"></a>library_block
将放置在该 IDL 库块内的构造。  
  
## <a name="syntax"></a>语法  
  
```  
  
[library_block]  
  
```  
  
## <a name="remarks"></a>备注  
 当你将放在库块内的构造时，你确保，它将传递到类型库，而不考虑是否引用它。 默认情况下，唯一的构造将修改通过[组件类](../windows/coclass.md)，[调度接口](../windows/dispinterface.md)，和[idl_module](../windows/idl-module.md)的库块中放置的属性。  
  
## <a name="example"></a>示例  
 在下面的代码中，自定义接口被放置到的库块。  
  
```  
// cpp_attr_ref_library_block.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLib")];  
[object, library_block, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]  
__interface IMyInterface {  
   HRESULT f1();  
};  
```  
  
## <a name="requirements"></a>要求  
  
### <a name="attribute-context"></a>特性上下文  
  
|||  
|-|-|  
|**适用对象**|任何位置|  
|**可重复**|否|  
|**必需的特性**|无|  
|**无效的特性**|无|  
  
 有关详细信息，请参见 [特性上下文](../windows/attribute-contexts.md)。  
  
## <a name="see-also"></a>请参阅  
 [编译器特性](../windows/compiler-attributes.md)   
 [独立特性](../windows/stand-alone-attributes.md)   
