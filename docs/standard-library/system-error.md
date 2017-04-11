---
title: '&lt;system_error&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.<system_error>
- std::<system_error>
- <system_error>
- system_error
dev_langs:
- C++
helpviewer_keywords:
- system_error header
ms.assetid: 5e046c6e-48d9-4740-8c8a-05f3727c1215
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: ad53550cce165587057910e3cd4c77427fb1cd55
ms.lasthandoff: 02/24/2017

---
# <a name="ltsystemerrorgt"></a>&lt;system_error&gt;
包括定义异常类 `system_error` 的标头 `<system_error>` 以及处理低级别系统错误的相关模板。  
  
## <a name="syntax"></a>语法  
  
```  
#include <system_error>  
```  
  
### <a name="objects"></a>对象  
  
|||  
|-|-|  
|[generic_category](../standard-library/system-error-functions.md#generic_category)|表示一般错误的类别。|  
|[system_category](../standard-library/system-error-functions.md#system_category)|表示因低级别系统溢出而引起的错误类别。|  
  
### <a name="typedefs"></a>Typedef  
  
|||  
|-|-|  
|[generic_errno](../standard-library/system-error-typedefs.md#generic_errno)|一种表示枚举的类型，用于为所有由 `<errno.h>` 中的 Posix 定义的错误代码宏提供符号名称。|  
  
### <a name="functions"></a>函数  
  
|||  
|-|-|  
|[make_error_code](../standard-library/system-error-functions.md#make_error_code)|创建一个 `error_code` 对象。|  
|[make_error_condition](../standard-library/system-error-functions.md#make_error_condition)|创建一个 `error_condition` 对象。|  
  
### <a name="operators"></a>运算符  
  
|||  
|-|-|  
|[operator==](../standard-library/system-error-operators.md#operator_eq_eq)|测试运算符左侧的对象是否等于右侧的对象。|  
|[operator!=](../standard-library/system-error-operators.md#operator_neq)|测试运算符左侧的对象是否不等于右侧的对象。|  
|[operator<](../standard-library/system-error-operators.md#operator_lt_)|测试一个对象是否小于要比较的传入对象。|  
  
### <a name="enumerations"></a>枚举  
  
|||  
|-|-|  
|[errc](../standard-library/system-error-enums.md#errc_enumeration)|为 `<errno.h>` 中的 Posix 定义的所有错误代码宏提供符号名称。|  
  
### <a name="classes-and-structs"></a>类和结构  
  
|||  
|-|-|  
|[error_category](../standard-library/error-category-class.md)|表示描述错误代码类别的对象的抽象、公用基。|  
|[error_code](../standard-library/error-code-class.md)|表示特定于实现的低级别系统错误。|  
|[error_condition](../standard-library/error-condition-class.md)|表示用户定义的错误代码。|  
|[is_error_code_enum](../standard-library/is-error-code-enum-class.md)|表示测试 [error_code](../standard-library/error-code-class.md) 枚举的类型谓词。|  
|[is_error_condition_enum](../standard-library/is-error-condition-enum-class.md)|表示测试 [error_condition Class](../standard-library/error-condition-class.md) 枚举的类型谓词。|  
|[system_error](../standard-library/system-error-class.md)|表示为报告低级别系统溢出而引发的所有异常的基类。|  
  
## <a name="requirements"></a>要求  
 **标头：**\<system_error>  
  
 **命名空间：** std  
  
## <a name="see-also"></a>另请参阅  
 [头文件引用](../standard-library/cpp-standard-library-header-files.md)



