---
title: ActivationFactoryCallback 函数 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::ActivationFactoryCallback
dev_langs:
- C++
helpviewer_keywords:
- ActivationFactoryCallback function
ms.assetid: dd40c79b-1273-4f2a-8c24-ae9926fb4fd9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2f1bae2c503f4e5f0c887a46956248184ece9a1e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857319"
---
# <a name="activationfactorycallback-function"></a>ActivationFactoryCallback 函数
支持 WRL 基础结构，不应在代码中直接使用。  
  
## <a name="syntax"></a>语法  
  
```  
inline HRESULT STDAPICALLTYPE ActivationFactoryCallback(  
   HSTRING activationId,  
   IActivationFactory **ppFactory  
);  
```  
  
#### <a name="parameters"></a>参数  
 `activationId`  
 一个字符串，指定运行时类名称的句柄。  
  
 `ppFactory`  
 此操作完成后，对应于参数的激活工厂`activationId`。  
  
## <a name="return-value"></a>返回值  
 如果成功，则为 S_OK；否则为描述失败的 HRESULT。 可能失败的 hresult 映射为 CLASS_E_CLASSNOTAVAILABLE 和 E_INVALIDARG。  
  
## <a name="remarks"></a>备注  
 获取指定的激活 id。 激活工厂  
  
 Windows 运行时调用此回调函数来请求由其运行时类名称指定的对象。  
  
## <a name="requirements"></a>要求  
 **标头：** module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>请参阅  
 [Microsoft::WRL::Details 命名空间](../windows/microsoft-wrl-details-namespace.md)