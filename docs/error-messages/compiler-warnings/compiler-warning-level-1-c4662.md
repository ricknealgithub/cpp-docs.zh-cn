---
title: 编译器警告 （等级 1） C4662 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4662
dev_langs:
- C++
helpviewer_keywords:
- C4662
ms.assetid: 7efda273-d04a-47b7-ad65-ff1ff94b5ffc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 60739959a6c26e0a1674b287ebf0a4605966e09b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33283421"
---
# <a name="compiler-warning-level-1-c4662"></a>编译器警告（等级 1）C4662
显式实例化；模板类“identifier1”无用于专用化“identifier2”的定义  
  
 已声明但未定义指定的模板类。  
  
## <a name="example"></a>示例  
  
```  
// C4662.cpp  
// compile with: /W1 /LD  
template<class T, int i> class MyClass; // no definition  
template MyClass< int, 1>;              // C4662  
```