---
title: VerifyInheritanceHelper 结构 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper
dev_langs:
- C++
helpviewer_keywords:
- VerifyInheritanceHelper structure
ms.assetid: 8a48a702-0f71-4807-935b-8311f0a7a8b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d758f4b44990d1f03ff698f0740c2aa8491367a5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889698"
---
# <a name="verifyinheritancehelper-structure"></a>VerifyInheritanceHelper 结构
支持 WRL 基础结构，不应在代码中直接使用。  
  
## <a name="syntax"></a>语法  
  
```  
template <  
   typename I,  
   typename Base  
>  
struct VerifyInheritanceHelper;  
template <  
   typename I  
>  
struct VerifyInheritanceHelper<I, Nil>;  
```  
  
#### <a name="parameters"></a>参数  
 `I`  
 一种类型。  
  
 `Base`  
 另一种类型。  
  
## <a name="remarks"></a>备注  
 测试是否一个接口派生自另一个接口。  
  
## <a name="members"></a>成员  
  
### <a name="public-methods"></a>公共方法  
  
|名称|描述|  
|----------|-----------------|  
|[VerifyInheritanceHelper::Verify 方法](../windows/verifyinheritancehelper-verify-method.md)|测试当前的模板参数指定的两个接口，并确定是否将一个接口派生自另。|  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 `VerifyInheritanceHelper`  
  
## <a name="requirements"></a>要求  
 **标头：** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>请参阅  
 [Microsoft::WRL::Details 命名空间](../windows/microsoft-wrl-details-namespace.md)