---
title: 编译器错误 C2326 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2326
dev_langs:
- C++
helpviewer_keywords:
- C2326
ms.assetid: 01a5ea40-de83-4e6f-a4e8-469f441258e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4578743350e58463ce8e743efbaa89a3e4db9ba2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33222327"
---
# <a name="compiler-error-c2326"></a>编译器错误 C2326
“声明符”: 函数无法访问“名称”  
  
 该代码尝试修改成员变量，这是不可能的。  
  
## <a name="example"></a>示例  
 下面的示例生成 C2326:  
  
```  
// C2326.cpp  
void MyFunc() {  
   int i;  
  
   class MyClass  {  
   public:  
      void mf() {  
         i = 4;   // C2326 i is inaccessible  
      }  
   };  
}  
```