---
title: 'Eventsource:: Targetspointerlock_ 数据成员 |Microsoft 文档'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource::targetsPointerLock_
dev_langs:
- C++
helpviewer_keywords:
- targetsPointerLock_ data member
ms.assetid: 8f08409f-5262-4be7-9cf1-2ed15f19684a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fb3c2131331521dab1b8264b696206d953762851
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873103"
---
# <a name="eventsourcetargetspointerlock-data-member"></a>EventSource::targetsPointerLock_ 数据成员
同步对内部数据成员的访问，即使在添加、删除或调用此 EventSource 的事件处理程序时也是如此。  
  
## <a name="syntax"></a>语法  
  
```  
Wrappers::SRWLock targetsPointerLock_;  
```  
  
## <a name="requirements"></a>要求  
 **标头：** event.h  
  
 **命名空间：** Microsoft::WRL
 
 ## <a name="see-also"></a>请参阅
 [EventSource 类](../windows/eventsource-class.md)