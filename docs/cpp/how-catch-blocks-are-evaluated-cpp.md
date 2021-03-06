---
title: Catch 块的计算 （C++） 的方式 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- try-catch keyword [C++], catchable types
- catch keyword [C++], types of catch handlers
- C++ exception handling, catch handlers
- exception handling, catching and deleting exceptions
- types [C++], exception handling
ms.assetid: 202dbf07-8ace-4b3b-b3ae-4b45c275e0b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0190b62491dbb9d15ee4f01a1cbc4c2741f74dbe
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2018
ms.locfileid: "37942579"
---
# <a name="how-catch-blocks-are-evaluated-c"></a>Catch 块的计算方式 (C++)
虽然通常建议您引发派生自 std::exception 的类型，但 C++ 使您能够引发任何类型的异常。 可由捕获 C++ 异常**捕获**指定相同的类型，为所引发的异常，或可以捕获任何类型的异常处理程序的处理程序。  
  
 如果引发的异常的类型是类，它还具有基类（或类），则它可由接受异常类型的基类和对异常类型的基的引用的处理程序捕获。 请注意，当异常由引用捕获时，会将其绑定到实际引发的异常对象；否则，它将为一个副本（与函数的自变量大致相同）。  
  
 时引发异常，它可能以下类型的捕捉**捕获**处理程序：  
  
-   可以接受任何类型的处理程序（使用省略号语法）。  
  
-   接受与异常对象; 相同的类型的处理程序它是副本，因为**const**并**易失性**修饰符将被忽略。  
  
-   接受对与异常对象相同的类型的引用的处理程序。  
  
-   接受对引用的处理程序**const**或**易失性**窗体的与异常对象相同的类型。  
  
-   接受与异常对象; 相同的类型的基类的处理程序由于它是副本，因此**const**并**易失性**修饰符将被忽略。 **捕获**基类的处理程序必须位于**捕获**派生的类处理程序。  
  
-   接受对与异常对象相同的类型的基类的引用的处理程序。  
  
-   接受对引用的处理程序**const**或**易失性**窗体的与异常对象相同的类型的基类。  
  
-   接受可通过标准指针转换规则将引发的指针对象转换为的指针的处理程序。  
  
 依据的顺序**捕获**处理程序出现非常重要，因为处理程序给定**尝试**块按其出现的顺序进行检查。 例如，将基类的处理程序放置在派生类的处理程序的前面是错误的。   匹配后**捕获**找到处理程序中，不会检查后续处理程序。 因此，省略号**捕获**处理程序必须是最后一个处理程序及其**尝试**块。 例如：  
  
```cpp 
// ...  
try  
{  
    // ...  
}  
catch( ... )  
{  
    // Handle exception here.  
}  
// Error: the next two handlers are never examined.  
catch( const char * str )  
{  
    cout << "Caught exception: " << str << endl;  
}  
catch( CExcptClass E )  
{  
    // Handle CExcptClass exception here.  
}  
```  
  
 在此示例中，省略号**捕获**处理程序是唯一处理程序的讨论。  
  
## <a name="see-also"></a>请参阅  
 [C++ 异常处理](../cpp/cpp-exception-handling.md)