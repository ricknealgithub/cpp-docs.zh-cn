---
title: no_namespace |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_namespace
dev_langs:
- C++
helpviewer_keywords:
- no_namespace attribute
ms.assetid: 5d81b741-a558-451b-b493-1f3b18967337
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b3d4558b0fd6a4014bc9601d5260882af444f87e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2018
ms.locfileid: "33912740"
---
# <a name="nonamespace"></a>no_namespace
**C + + 专用**  
  
 指定命名空间的名称不由编译器生成。  
  
## <a name="syntax"></a>语法  
  
```  
no_namespace  
```  
  
## <a name="remarks"></a>备注  
 `#import` 标头文件中的类型库内容通常在命名空间中定义。 中指定的命名空间名称**库**原始 IDL 文件的语句。 如果指定了 `no_namespace` 特性，则编译器不生成此命名空间。  
  
 如果你想要使用不同的命名空间名称，然后使用[rename_namespace](../preprocessor/rename-namespace.md)特性。  
  
 **结束 c + + 专用**  
  
## <a name="see-also"></a>请参阅  
 [#import 属性](../preprocessor/hash-import-attributes-cpp.md)   
 [#import 指令](../preprocessor/hash-import-directive-cpp.md)