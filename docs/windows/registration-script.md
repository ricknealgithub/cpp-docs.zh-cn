---
title: registration_script |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.registration_script
dev_langs:
- C++
helpviewer_keywords:
- registration_script attribute
ms.assetid: 786f8072-9187-4163-a979-7a604dd4c888
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d4385dd12fccafb154a637dd5260764667d3887a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878718"
---
# <a name="registrationscript"></a>registration_script
执行指定的自定义注册脚本。  
  
## <a name="syntax"></a>语法  
  
```  
  
      [ registration_script(   
   script   
) ]  
```  
  
#### <a name="parameters"></a>参数  
 *脚本*  
 自定义注册脚本 (.rgs) 文件的完整路径。 值为**无**，如`script = "none"`，该值指示组件类具有没有注册要求。  
  
## <a name="remarks"></a>备注  
 **Registration_script** c + + 特性执行自定义注册脚本指定**脚本**。 如果未指定此属性，使用标准.rgs 文件 （包含将组件注册信息）。 .Rgs 文件的详细信息，请参阅[ATL 注册表组件 （注册器）](../atl/atl-registry-component-registrar.md)。  
  
 此属性要求 [coclass](../windows/coclass.md)、 [progid](../windows/progid.md)或 [vi_progid](../windows/vi-progid.md) 属性（或隐含这些属性之一的其他属性）也应用于同一个元素。  
  
## <a name="example"></a>示例  
 下面的代码指定该组件具有名为 cpp_attr_ref_registration_script.rgs 的注册表脚本。  
  
```  
// cpp_attr_ref_registration_script.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="REG")];  
  
[object, uuid("d9cd196b-6836-470b-9b9b-5b04b828e5b0")]  
__interface IFace {};  
  
// requires "cpp_attr_ref_registration_script.rgs"  
// create sample .RGS file "cpp_attr_ref_registration_script.rgs" if it does not exist  
[ coclass, registration_script(script="cpp_attr_ref_registration_script.rgs"),  
  uuid("50d3ad42-3601-4f26-8cfe-0f1f26f98f67")]  
class CMyClass:public IFace {};  
```  
  
## <a name="requirements"></a>要求  
  
### <a name="attribute-context"></a>特性上下文  
  
|||  
|-|-|  
|**适用对象**|**class**， `struct`|  
|**可重复**|否|  
|**必需的特性**|以下一个或多个属性： **coclass**、 **progid**或 **vi_progid**。|  
|**无效的特性**|无|  
  
 有关特性上下文的详细信息，请参见 [特性上下文](../windows/attribute-contexts.md)。  
  
## <a name="see-also"></a>请参阅  
 [COM 特性](../windows/com-attributes.md)   
 [类特性](../windows/class-attributes.md)   
 [rdx](../windows/rdx.md)   
