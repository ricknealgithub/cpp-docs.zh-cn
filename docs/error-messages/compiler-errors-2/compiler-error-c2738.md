---
title: 编译器错误 C2738 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2738
dev_langs:
- C++
helpviewer_keywords:
- C2738
ms.assetid: 896b4640-1ee0-4cd8-9910-de3efa30006a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f056d8f38c36011e2b9025283e46164fe53061fd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33236724"
---
# <a name="compiler-error-c2738"></a>编译器错误 C2738
declaration： 不明确或不是 type 的成员  
  
 未正确声明函数。  
  
 下面的示例生成 C2738:  
  
```  
// C2738.cpp  
struct A {  
   template <class T> operator T*();  
   // template <class T> operator T();  
};  
  
template <>  
A::operator int() {   // C2738  
  
// try the following line instead  
// A::operator int*() {  
  
// or use the commented member declaration  
  
   return 0;  
}  
```