---
title: 编译器警告 C4484 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4484
dev_langs:
- C++
helpviewer_keywords:
- C4484
ms.assetid: 3d30e5b3-2297-45b7-a37a-1360056fdd0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 75531c207f0136f16109b4d69d689b883998aae2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33274750"
---
# <a name="compiler-warning-c4484"></a>编译器警告 C4484
override_function: ref 基类类方法 base_class_function 相匹配，但未标记为虚拟一步、 上一 new 或 '重写;假定 new （和不是虚拟）  
  
 使用编译时 **/clr**，编译器将不会隐式重写基类函数，这意味着该函数将获取 vtable 中的新槽。 若要解决，请显式指定函数是否可重写。  
  
 有关详细信息，请参见:  
  
-   [/cgthreads（公共语言运行时编译）](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [override](../../windows/override-cpp-component-extensions.md)  
  
-   [新 (新 vtable 中的槽）](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md)  
  
 C4484 始终作为错误发出。 使用[警告](../../preprocessor/warning.md)杂注来取消显示 C4484。  
  
## <a name="example"></a>示例  
 下面的示例生成 C4484。  
  
```  
// C4484.cpp  
// compile with: /clr  
ref struct A {  
   virtual void Test() {}  
};  
  
ref struct B : A {  
   void Test() {}   // C4484  
};  
  
// OK  
ref struct C {  
   virtual void Test() {}  
   virtual void Test2() {}  
};  
  
ref struct D : C {  
   virtual void Test() new {}  
   virtual void Test2() override {}  
};  
```