---
title: "编译器错误 C3029 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3029"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3029"
ms.assetid: 655eb04d-504a-468d-8c0c-bda1e5f297b7
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 编译器错误 C3029
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

“symbol”: 只能在 OpenMP 指令中的 data\-sharing 子句中出现一次  
  
 指令中一个或多个子句中多次使用符号。 符号只能在指令中使用一次。  
  
 以下示例生成 C3029：  
  
```  
// C3029.cpp // compile with: /openmp /link vcomps.lib #include "omp.h" int g_i; int main() { int i, x; #pragma omp parallel reduction(+ : x, x)   // C3029 ; #pragma omp parallel reduction(+ : x)   // OK ; #pragma omp parallel private(x) reduction(+ : x)   // C3029 ; #pragma omp parallel reduction(+ : x)   // OK ; }  
```