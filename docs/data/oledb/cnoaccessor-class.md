---
title: CNoAccessor 类 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CNoAccessor
- CNoAccessor
- ATL.CNoAccessor
dev_langs:
- C++
helpviewer_keywords:
- CNoAccessor class
ms.assetid: eb669ae5-0a56-49a3-9646-c4ae6239da31
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3110d20330d42fcb0816873ff3e8a25d1f8436ea
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33097349"
---
# <a name="cnoaccessor-class"></a>CNoAccessor 类
可用作模板自变量 (`TAccessor`) 的模板类，如`CCommand`和`CTable`，需要访问器类自变量。  
  
## <a name="syntax"></a>语法

```cpp
class CNoAccessor  
```  
  
## <a name="remarks"></a>备注  
 使用`CNoAccessor`作为模板参数时你不想要支持参数或输出列的类。  
  
 `CNoAccessor` 将实现以下存根方法，其中每个方法都对应于其他访问器类方法：  
  
-   **BindColumns** -将列绑定到访问器。  
  
-   `BindParameters` -将绑定到列的创建的参数。  
  
-   **将绑定**-创建绑定。  
  
-   **关闭**-关闭访问器。  
  
-   `ReleaseAccessors` -释放类创建的访问器。  
  
-   `FreeRecordMemory` -释放当前需要被释放的记录中的任何列。  
  
-   `GetColumnInfo` -从打开的行集中获取列信息。  
  
-   `GetNumAccessors` -检索类创建的取值函数的数目。  
  
-   `IsAutoAccessor` -如果数据计算机在移动操作期间访问器将自动检索返回 true。  
  
-   `GetHAccessor` -检索指定访问器的访问器句柄。  
  
-   `GetBuffer` -检索到的书签缓冲区的指针。  
  
-   **NoBindOnNullRowset** -阻止空的行集的数据绑定。  
  
## <a name="requirements"></a>要求  
 **标头:** atldbcli.h  
  
## <a name="see-also"></a>请参阅  
 [OLE DB 使用者模板](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 使用者模板参考](../../data/oledb/ole-db-consumer-templates-reference.md)