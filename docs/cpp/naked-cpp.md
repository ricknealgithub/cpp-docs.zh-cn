---
title: 裸 （C++） |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- naked_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], naked
- naked __declspec keyword
ms.assetid: 69723241-05e1-439b-868e-20a83a16ab6d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1057754b5c98086de42daedd5e7aab70656eba69
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2018
ms.locfileid: "37942396"
---
# <a name="naked-c"></a>naked (C++)
**Microsoft 专用**  
  
 函数声明与为**裸**特性，因此编译器将生成代码而无需 prolog 和 epilog 代码。 利用此功能，可以使用内联汇编程序代码编写您自己的 prolog/epilog 代码序列。 裸函数对于编写虚拟设备驱动程序特别有用。  请注意，**裸**属性仅适用于 x86 和 ARM，和上不可用[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]。  
  
## <a name="syntax"></a>语法  
  
```  
__declspec(naked) declarator  
```  
  
## <a name="remarks"></a>备注  
 因为**裸**特性仅与函数定义相关且不是类型修饰符，裸函数必须使用扩展的特性语法和[__declspec](../cpp/declspec.md)关键字。  
  

 编译器无法生成使用 naked 特性标记的函数的内联函数，即使该函数还将标有[__forceinline](inline-functions-cpp.md)关键字。  

  
 如果编译器将发出错误**裸**特性应用于非成员方法的定义之外的任何内容。  
  
## <a name="examples"></a>示例  
 此代码定义的函数**裸**属性：  
  
```  
__declspec( naked ) int func( formal_parameters ) {}  
```  
  
 或者，或者：  
  
```  
#define Naked __declspec( naked )  
Naked int func( formal_parameters ) {}  
```  
  
 **裸**特性影响仅的函数的 prolog 和 epilog 序列的编译器的代码生成的特性。 它不影响为调用这些函数而生成的代码。 因此，**裸**属性不被视为函数的类型的一部分并且不能具有函数指针**裸**属性。 此外，**裸**属性不能应用于数据定义。 例如，此代码示例生成错误：  
  
```  
__declspec( naked ) int i;  
// Error--naked attribute not permitted on data declarations.  
```  
  
 **裸**特性仅与函数定义相关且不能在函数的原型中指定。 例如，此声明生成编译器错误：  
  
```  
__declspec( naked ) int func();  // Error--naked attribute not permitted on function declarations  
```  
  
 **结束 Microsoft 专用**  
  
## <a name="see-also"></a>请参阅  
 [__declspec](../cpp/declspec.md)   
 [关键字](../cpp/keywords-cpp.md)   
 [Naked 函数调用](../cpp/naked-function-calls.md)