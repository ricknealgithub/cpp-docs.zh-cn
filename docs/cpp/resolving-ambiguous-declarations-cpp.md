---
title: 解决不明确声明 （C++） |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 3d773ee7-bbea-47de-80c2-cb0a9d4ec0b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 530111ee439a991201debab876d485a36b7f5ac5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="resolving-ambiguous-declarations-c"></a>解决不明确声明 （C++）
若要执行从一种类型到另一种类型的显式转换，您必须使用强制转换并指定所需的类型名称。 某些类型转换会导致句法歧义。 下面的函数样式类型转换是不明确的：  
  
```  
char *aName( String( s ) );  
```  
  
 不清楚是否函数声明或一个对象声明以与函数样式强制转换为初始值设定项： 它可以声明函数返回类型**char \*** 采用一个类型自变量`String`它可以声明对象或`aName`并将其初始化的值与`s`强制转换为类型`String`。  
  
 如果声明可被视为有效的函数声明，则会以相同的方式处理。 只有当它不能是函数声明时（即句法不正确时），才会查看语句是否为函数样式类型转换。 因此，编译器将语句视为函数的声明并忽略标识符 `s` 周围的括号。 另一方面，语句：  
  
```  
char *aName( (String)s );  
```  
  
 和  
  
```  
char *aName = String( s );  
```  
  
 一些明显的对象，并从类型的用户定义的转换声明`String`类型**char \*** 调用以执行的初始化`aName`。  
  
## <a name="see-also"></a>请参阅  
 