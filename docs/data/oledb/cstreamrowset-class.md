---
title: CStreamRowset 类 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CStreamRowset<TAccessor>
- ATL::CStreamRowset
- CStreamRowset
- ATL.CStreamRowset<TAccessor>
- ATL.CStreamRowset
- CStreamRowset::CStreamRowset
- CStreamRowset.CStreamRowset
- ATL.CStreamRowset.CStreamRowset
- ATL::CStreamRowset::CStreamRowset
- CStreamRowset
- CStreamRowset<TAccessor>::CStreamRowset
- ATL::CStreamRowset<TAccessor>::CStreamRowset
- CStreamRowset<TAccessor>.Close
- ATL.CStreamRowset<TAccessor>.Close
- CStreamRowset::Close
- CStreamRowset<TAccessor>::Close
- ATL::CStreamRowset::Close
- ATL.CStreamRowset.Close
- ATL::CStreamRowset<TAccessor>::Close
- CStreamRowset.Close
dev_langs:
- C++
helpviewer_keywords:
- CStreamRowset class
- CStreamRowset class, constructor
- Close method
ms.assetid: a106e953-a38a-464e-8ea5-28963d9e4811
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e0aad7fe25205d4cf31cbe76db3f1fb441858858
ms.sourcegitcommit: b217daee32d3413cf33753d9b4dc35a0022b1bfa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "39233394"
---
# <a name="cstreamrowset-class"></a>CStreamRowset 类
在中使用`CCommand`或`CTable`声明。  
  
## <a name="syntax"></a>语法

```cpp
template <class TAccessor = CAccessorBase>  
class CStreamRowset  
```  
  
### <a name="parameters"></a>参数  
 *TAccessor*  
 一个访问器类。  

## <a name="requirements"></a>要求  
 **标头:** atldbcli.h  
  
## <a name="members"></a>成员  
  
### <a name="methods"></a>方法  
  
|||  
|-|-|  
|[CStreamRowset](#cstreamrowset)|构造函数。 实例化并初始化`CStreamRowset`对象。|  
|[关闭](#close)|版本[ISequentialStream](https://msdn.microsoft.com/library/ms718035.aspx)类中的接口指针。|  
  
## <a name="remarks"></a>备注  
 使用`CStreamRowset`在您`CCommand`或`CTable`声明，例如：  
  
 [!code-cpp[NVC_OLEDB_Consumer#11](../../data/oledb/codesnippet/cpp/cstreamrowset-class_1.cpp)]  
  
 或  
  
 [!code-cpp[NVC_OLEDB_Consumer#12](../../data/oledb/codesnippet/cpp/cstreamrowset-class_2.cpp)]  
  
 `ICommand::Execute` 返回`ISequentialStream`指针，它存储在`m_spStream`。 然后，使用`Read`方法来检索 XML 格式 （Unicode 字符串） 的数据。 例如：  
  
 [!code-cpp[NVC_OLEDB_Consumer#13](../../data/oledb/codesnippet/cpp/cstreamrowset-class_3.cpp)]  
  
 SQL Server 2000 执行 XML 格式中，并将返回所有列和行集作为一个 XML 字符串的所有行。  
  
> [!NOTE]
>  此功能仅适用于 SQL Server 2000。  
  
## <a name="cstreamrowset"></a> Cstreamrowset:: Cstreamrowset
实例化并初始化`CStreamRowset`对象。  
  
### <a name="syntax"></a>语法  
  
```cpp
CStreamRowset();  
  
```  

## <a name="close"></a> Cstreamrowset:: Close
版本[ISequentialStream](https://msdn.microsoft.com/library/ms718035.aspx)类中的接口指针。  
  
### <a name="syntax"></a>语法  
  
```cpp
void Close();  
  
```  
  
## <a name="see-also"></a>请参阅  
 [OLE DB 使用者模板](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 使用者模板参考](../../data/oledb/ole-db-consumer-templates-reference.md)