---
title: 编译器错误 C3741 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3741
dev_langs:
- C++
helpviewer_keywords:
- C3741
ms.assetid: ed311315-cc32-49c9-97fa-01b293d81526
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 67c1bdb78a48571f58b59930615bc3251f3eeea5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33266219"
---
# <a name="compiler-error-c3741"></a>编译器错误 C3741
class： 必须能是组件类时 event_receiver layout_dependent 参数 = true  
  
 当`layout_dependent=true`为[event_receiver](../../windows/event-receiver.md)类，则类还必须具有[组件类](../../windows/coclass.md)属性。  
  
 下面的示例生成 C3741  
  
```  
// C3741.cpp  
// compile with: /c  
// C3741 expected  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
[module(name="xx")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface I{ HRESULT f(); };  
  
// Delete the following line to resolve.  
[ event_receiver(com, layout_dependent=true)]  
  
// class or struct must be declared with coclass  
// Uncomment the following line to resolve.  
// [ event_receiver(com, layout_dependent=true), coclass, uuid("00000000-0000-0000-0000-000000000002")]  
struct R : I {  
   HRESULT f(){ return 0; }  
   R(){}  
   R(I* a){ __hook(I, a); }  
};  
```