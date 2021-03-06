---
title: satype |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.satype
dev_langs:
- C++
helpviewer_keywords:
- satype attribute
ms.assetid: 1716590b-6bcb-4aba-b1bc-82f7335f02c3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a77021cbcf6622701a1025ef33000196ba7bb6d9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2018
ms.locfileid: "33888677"
---
# <a name="satype"></a>satype
指定的数据类型**SAFEARRAY**结构。  
  
## <a name="syntax"></a>语法  
  
```  
  
      [ satype(  
   data_type  
) ]  
```  
  
#### <a name="parameters"></a>参数  
 *data_type*  
 数据类型**SAFEARRAY**作为参数传递给接口方法的数据结构。  
  
## <a name="requirements"></a>要求  
  
### <a name="attribute-context"></a>特性上下文  
  
|||  
|-|-|  
|**适用对象**|接口参数，接口方法|  
|**可重复**|否|  
|**必需的特性**|无|  
|**无效的特性**|无|  
  
## <a name="remarks"></a>备注  
 **Satype** c + + 特性指定的数据类型**SAFEARRAY**。  
  
> [!NOTE]
>  从删除一定程度的间接性**SAFEARRAY**中如何在.cpp 文件中声明的生成的.idl 文件中的指针。  
  
## <a name="example"></a>示例  
  
```  
// cpp_attr_ref_satype.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyModule")];  
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]  
__interface A {  
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);  
};  
```  
  
## <a name="see-also"></a>请参阅  
 [编译器特性](../windows/compiler-attributes.md)   
 [Parameter 特性](../windows/parameter-attributes.md)   
 [方法特性](../windows/method-attributes.md)   
 [id](../windows/id.md)   
