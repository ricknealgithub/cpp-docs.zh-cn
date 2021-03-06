---
title: CArrayRowset 类 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CArrayRowset<TAccessor>
- ATL.CArrayRowset
- CArrayRowset
- ATL::CArrayRowset
- ATL::CArrayRowset<TAccessor>
- ATL::CArrayRowset::CArrayRowset
- CArrayRowset.CArrayRowset
- ATL.CArrayRowset.CArrayRowset
- ATL.CArrayRowset<TAccessor>.CArrayRowset
- CArrayRowset::CArrayRowset
- CArrayRowset
- CArrayRowset<TAccessor>::CArrayRowset
- ATL::CArrayRowset<TAccessor>::CArrayRowset
- CArrayRowset<TAccessor>.Snapshot
- ATL::CArrayRowset::Snapshot
- Snapshot
- CArrayRowset<TAccessor>::Snapshot
- ATL.CArrayRowset.Snapshot
- ATL.CArrayRowset<TAccessor>.Snapshot
- ATL::CArrayRowset<TAccessor>::Snapshot
- CArrayRowset::Snapshot
- CArrayRowset.Snapshot
- CArrayRowset::operator[]
- CArrayRowset.operator[]
- ATL::CArrayRowset::m_nRowsRead
- ATL::CArrayRowset<TAccessor>::m_nRowsRead
- CArrayRowset<TAccessor>::m_nRowsRead
- ATL.CArrayRowset<TAccessor>.m_nRowsRead
- CArrayRowset.m_nRowsRead
- m_nRowsRead
- ATL.CArrayRowset.m_nRowsRead
- CArrayRowset::m_nRowsRead
dev_langs:
- C++
helpviewer_keywords:
- CArrayRowset class
- CArrayRowset class, constructor
- Snapshot method
- operator [], arrays
- '[] operator'
- operator[], arrays
- m_nRowsRead
ms.assetid: 511427e1-73ca-4fd8-9ba1-ae9463557cb6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3b367fc74fdbb03a6e5193f3fc9be08f74111a09
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2018
ms.locfileid: "39207482"
---
# <a name="carrayrowset-class"></a>CArrayRowset 类
使用数组语法访问行集的元素。  
  
## <a name="syntax"></a>语法

```cpp
template < class TAccessor >  
class CArrayRowset :   
   public CVirtualBuffer <TAccessor>,   
   protected CBulkRowset <TAccessor>  
```  
  
### <a name="parameters"></a>参数  
 *TAccessor*  
 希望集合使用的访问器类的类型。  

## <a name="requirements"></a>要求  
 **标头:** atldbcli.h  
  
## <a name="members"></a>成员  
  
### <a name="methods"></a>方法  
  
|||  
|-|-|  
|[CArrayRowset](#carrayrowset)|构造函数。|  
|[快照](#snapshot)|将整个行集读入内存。|  
  
### <a name="operators"></a>运算符  
  
|||  
|-|-|  
|[Operator&#91;&#93;](#operator)|访问行集合的元素。|  
  
### <a name="data-members"></a>数据成员  
  
|||  
|-|-|  
|[CArrayRowset::m_nRowsRead](#nrowsread)|已读取的行数。|  
  
## <a name="carrayrowset"></a> Carrayrowset:: Carrayrowset
创建一个新的 `CArrayRowset` 对象。  
  
### <a name="syntax"></a>语法  
  
```cpp
      CArrayRowset(int nMax = 100000);  
```  
  
#### <a name="parameters"></a>参数  
 *最*  
 [in] 行集中的最大行数。 

## <a name="snapshot"></a> Carrayrowset:: Snapshot
将整个行集读入内存，并创建该行集的图像或快照。  
  
### <a name="syntax"></a>语法  
  
```cpp
HRESULT Snapshot() throw();  
  
```  

## <a name="operator"></a> Carrayrowset:: Operator
提供用于访问行集中的行的类似数组的语法。  
  
### <a name="syntax"></a>语法  
  
```cpp
      TAccessor  
      & operator[](int nrow);  
```  
  
#### <a name="parameters"></a>参数  
 *TAccessor*  
 一个指定存储在行集中的访问器类型的模板化参数。  
  
 *nRow*  
 [in] 要访问的行号（数组元素）。  
  
### <a name="return-value"></a>返回值  
 请求行的内容。  
  
### <a name="remarks"></a>备注  
 如果*nRow*超过行集中的行数，将引发异常。  

## <a name="nrowsread"></a> Carrayrowset:: M_nrowsread
包含已读取的行集中的行数。  
  
### <a name="syntax"></a>语法  
  
```cpp
ULONG m_nRowsRead;  
  
```  
  
## <a name="see-also"></a>请参阅  
 [OLE DB 使用者模板](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 使用者模板参考](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CRowset 类](../../data/oledb/crowset-class.md)