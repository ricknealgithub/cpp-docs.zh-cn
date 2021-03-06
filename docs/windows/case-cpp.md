---
title: 用例 （c + +） |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.case
dev_langs:
- C++
helpviewer_keywords:
- case attribute
ms.assetid: 6fb883c3-0526-4932-a901-b4564dcaeb7d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 30d665861688054a4f6b7491f449014afe646c71
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2018
ms.locfileid: "33860952"
---
# <a name="case-c"></a>case (C++)
与使用[switch_type](../windows/switch-type.md)属性中**联合**。  
  
## <a name="syntax"></a>语法  
  
```  
  
      [ case(  
   value  
) ]  
```  
  
#### <a name="parameters"></a>参数  
 *value*  
 一个可能的输入的值，用于你要为其提供的处理。 一种**值**可以是以下类型之一：  
  
-   `int`  
  
-   `char`  
  
-   `boolean`  
  
-   `enum`  
  
 或这样一个类型的标识符。  
  
## <a name="remarks"></a>备注  
 **用例**c + + 属性具有相同的功能**用例**MIDL 特性。 此属性仅用于[switch_type](../windows/switch-type.md)属性。  
  
## <a name="example"></a>示例  
 下面的代码演示使用**用例**属性：  
  
```  
// cpp_attr_ref_case.cpp  
// compile with: /LD  
#include <unknwn.h>  
[export]  
struct SizedValue2 {  
   [switch_type(char), switch_is(kind)] union {  
      [case(1), string]  
          wchar_t* wval;  
      [default, string]  
          char* val;  
   };  
    char kind;  
};  
[module(name="ATLFIRELib")];  
```  
  
## <a name="requirements"></a>要求  
  
### <a name="attribute-context"></a>特性上下文  
  
|||  
|-|-|  
|**适用对象**|成员**类**或 `struct`|  
|**可重复**|否|  
|**必需的特性**|无|  
|**无效的特性**|无|  
  
 有关特性上下文的详细信息，请参见 [特性上下文](../windows/attribute-contexts.md)。  
  
## <a name="see-also"></a>请参阅  
 [IDL 特性](../windows/idl-attributes.md)   
 [Typedef、 Enum、 Union 和 Struct 特性](../windows/typedef-enum-union-and-struct-attributes.md)   
 [类特性](../windows/class-attributes.md)   
