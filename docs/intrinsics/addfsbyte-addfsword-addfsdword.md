---
title: __addfsbyte、 __addfsword、 __addfsdword |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __addfsbyte_cpp
- __addfsdword
- __addfsword_cpp
- __addfsbyte
- __addfsword
- __addfsdword_cpp
dev_langs:
- C++
helpviewer_keywords:
- __addfsdword intrinsic
- __addfsword intrinsic
- __addfsbyte intrinsic
ms.assetid: 706c70df-6b52-4401-9268-2977ed8ad715
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f4c2b4a9e185f709ff829a3b88ea9cb67741fa1c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33330241"
---
# <a name="addfsbyte-addfsword-addfsdword"></a>__addfsbyte, __addfsword, __addfsdword
**Microsoft 专用**  
  
 将值添加到指定的偏移量相对于开始的内存位置`FS`段。  
  
## <a name="syntax"></a>语法  
  
```  
void __addfsbyte(   
   unsigned long Offset,   
   unsigned char Data   
);  
void __addfsword(   
   unsigned long Offset,   
   unsigned short Data   
);  
void __addfsdword(   
   unsigned long Offset,   
   unsigned long Data   
);  
```  
  
#### <a name="parameters"></a>参数  
 [in] `Offset`  
 从开始处的偏移量`FS`。  
  
 [in] `Data`  
 要添加到的内存位置的值。  
  
## <a name="requirements"></a>要求  
  
|内部函数|体系结构|  
|---------------|------------------|  
|`__addfsbyte`|x86|  
|`__addfsword`|x86|  
|`__addfsdword`|x86|  
  
## <a name="remarks"></a>备注  
 这些例程只能用作内部函数不可用。  
  
**结束 Microsoft 专用**  
  
## <a name="see-also"></a>请参阅  
 [__incfsbyte、 \__incfsword， \__incfsdword](../intrinsics/incfsbyte-incfsword-incfsdword.md)   
 [__readfsbyte， \__readfsdword， \__readfsqword， \__readfsword](../intrinsics/readfsbyte-readfsdword-readfsqword-readfsword.md)   
 [__writefsbyte， \__writefsdword， \__writefsqword， \__writefsword](../intrinsics/writefsbyte-writefsdword-writefsqword-writefsword.md)   
 [编译器内部函数](../intrinsics/compiler-intrinsics.md)