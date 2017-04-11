---
title: "编译器错误 C3247 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3247"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3247"
ms.assetid: f9a2bbb5-3fce-40bf-9fd3-835a5f164dbb
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 编译器错误 C3247
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

“class1”：组件类不能继承自另一个组件类“class2”  
  
 [coclass](../../windows/coclass.md) 特性标记的类不能继承自 `coclass` 特性标记的另一个类。  
  
 以下示例生成 C3247：  
  
```  
// C3247.cpp [module(name="MyLib")]; [coclass] class a { }; [coclass] class b : public a {   // C3247 }; int main() { }  
```