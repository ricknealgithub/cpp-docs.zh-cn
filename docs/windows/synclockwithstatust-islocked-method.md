---
title: 'Synclockwithstatust:: Islocked 方法 |Microsoft 文档'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked
dev_langs:
- C++
helpviewer_keywords:
- IsLocked method
ms.assetid: e1b75b7b-c145-471a-aa5d-71abf31f5990
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a564c4223b09d9295ff0ac3159e165944c4d885d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892548"
---
# <a name="synclockwithstatustislocked-method"></a>SyncLockWithStatusT::IsLocked 方法
支持 WRL 基础结构，不应在代码中直接使用。  
  
## <a name="syntax"></a>语法  
  
```  
bool IsLocked() const;  
```  
  
## <a name="remarks"></a>备注  
 指示当前的 SyncLockWithStatusT 对象是否拥有资源;SyncLockWithStatusT 对象也是*锁定*。  
  
## <a name="return-value"></a>返回值  
 **true** SyncLockWithStatusT 对象是否锁定; 否则为**false**。  
  
## <a name="requirements"></a>要求  
 **标头：** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>请参阅  
 [SyncLockWithStatusT 类](../windows/synclockwithstatust-class.md)