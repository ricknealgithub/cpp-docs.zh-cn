---
title: 成员访问运算符:。 和-&gt; |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- .
- ->
dev_langs:
- C++
helpviewer_keywords:
- member access, expressions
- operators [C++], member access
- dot operator (.)
- -> operator
- member access, operators
- postfix operators [C++]
- . operator
- member access
ms.assetid: f8fc3df9-d728-40c5-b384-276927f5f1b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2958291551d081b4284c6683d62f6dd5de06f70d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="member-access-operators--and--gt"></a>成员访问运算符:。 和-&gt;
## <a name="syntax"></a>语法  
  
```  
postfix-expression . name  
postfix-expression -> name  
```  
  
## <a name="remarks"></a>备注  
 成员访问运算符**。** 和**->** 用于引用的结构、 联合和类成员。 成员访问表达式具有选定成员的值和类型。  
  
 有两种形式的成员访问表达式：  
  
1.  在第一种形式，*后缀表达式*表示结构、 类或联合类型的值和*名称*指定的结构、 联合或类的成员命名。 操作的值是*名称*如果是左值和*后缀表达式*是左值。  
  
2.  在第二种形式，*后缀表达式*表示指向结构、 联合或类的指针和*名称*指定的结构、 联合或类的成员命名。 值是*名称*和是左值。 **->** 运算符取消引用指针。 因此，表达式 * e ***->** `member`和 **(\****e***)**。`member` (其中*e*表示的指针) 产生完全相同的结果 (除非时运算符**->** 或**\*** 都重载方法)。  
  
## <a name="example"></a>示例  
 以下示例演示成员访问运算符的两种形式。  
  
```  
// expre_Selection_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
struct Date {  
   Date(int i, int j, int k) : day(i), month(j), year(k){}  
   int month;  
   int day;  
   int year;  
};  
  
int main() {  
   Date mydate(1,1,1900);  
   mydate.month = 2;     
   cout  << mydate.month << "/" << mydate.day  
         << "/" << mydate.year << endl;  
  
   Date *mydate2 = new Date(1,1,2000);  
   mydate2->month = 2;  
   cout  << mydate2->month << "/" << mydate2->day  
         << "/" << mydate2->year << endl;  
   delete mydate2;  
}  
```  
  
```Output  
2/1/1900  
2/1/2000  
```  
  
## <a name="see-also"></a>请参阅  
 [后缀表达式](../cpp/postfix-expressions.md)   
 [C++ 内置运算符、 优先级和关联性](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [类和结构](../cpp/classes-and-structs-cpp.md)   
 [结构和联合成员](../c-language/structure-and-union-members.md)