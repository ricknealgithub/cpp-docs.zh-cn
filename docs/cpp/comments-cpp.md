---
title: 注释 （C++） |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- code comments, C++
- comments, documenting code
- comments, C++ code
- white space, C++ comments
ms.assetid: 6fcb906c-c264-4083-84bc-373800b2e514
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 919c40dce53dd5d1c8847287099c61c3e1b229cf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32411749"
---
# <a name="comments-c"></a>注释 （C++）
注释是的文本，编译器将忽略，但这是用于程序员。 通常使用注释来批注代码以供将来参考。 编译器会将它们视为空白区域。 你可以使用在测试中的注释以使某些行代码处于非活动状态;但是， `#if` / `#endif`预处理器指令更适用于这因为可以包含注释的代码外侧，但你无法嵌套注释。  
  
 通过以下方式之一是编写 C++ 注释：  
  
-   `/*`正斜杠 (星号） 字符后, 跟的任意字符序列 （包括新行） 后, 跟`*/`字符。 此语法等同于 ANSI c。  
  
-   `//` （两个斜杠） 字符后, 跟的任意字符序列。 新行不立即前加反斜杠终止这种形式的注释。 因此，它通常称为"单行注释"。  
  
 注释字符 (`/*`， `*/`，和`//`) 有任何特殊意义中的字符常量，字符串文本，或注释。 因此，不能嵌套注释，使用的第一个语法。  
  
## <a name="see-also"></a>请参阅  
 [词法约定](../cpp/lexical-conventions.md)