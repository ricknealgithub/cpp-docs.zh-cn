---
title: IRowsetImpl 类 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetImpl
- IRowsetImpl::AddRefRows
- AddRefRows
- IRowsetImpl.AddRefRows
- ATL::IRowsetImpl::AddRefRows
- ATL.IRowsetImpl.AddRefRows
- IRowsetImpl.CreateRow
- ATL.IRowsetImpl.CreateRow
- ATL::IRowsetImpl::CreateRow
- CreateRow
- IRowsetImpl::CreateRow
- ATL.IRowsetImpl.GetData
- ATL::IRowsetImpl::GetData
- IRowsetImpl::GetData
- IRowsetImpl.GetData
- GetDBStatus
- IRowsetImpl.GetDBStatus
- IRowsetImpl::GetDBStatus
- GetNextRows
- ATL.IRowsetImpl.GetNextRows
- ATL::IRowsetImpl::GetNextRows
- IRowsetImpl::GetNextRows
- IRowsetImpl.GetNextRows
- IRowsetImpl.IRowsetImpl
- ATL::IRowsetImpl::IRowsetImpl
- ATL.IRowsetImpl.IRowsetImpl
- IRowsetImpl::IRowsetImpl
- IRowsetImpl
- ATL::IRowsetImpl::RefRows
- ATL.IRowsetImpl.RefRows
- IRowsetImpl.RefRows
- RefRows
- IRowsetImpl::RefRows
- ATL.IRowsetImpl.ReleaseRows
- ReleaseRows
- IRowsetImpl::ReleaseRows
- ATL::IRowsetImpl::ReleaseRows
- IRowsetImpl.ReleaseRows
- ATL.IRowsetImpl.RestartPosition
- IRowsetImpl::RestartPosition
- RestartPosition
- ATL::IRowsetImpl::RestartPosition
- IRowsetImpl.RestartPosition
- IRowsetImpl.SetDBStatus
- IRowsetImpl::SetDBStatus
- SetDBStatus
- ATL.IRowsetImpl.m_bCanFetchBack
- ATL::IRowsetImpl::m_bCanFetchBack
- IRowsetImpl.m_bCanFetchBack
- IRowsetImpl::m_bCanFetchBack
- m_bCanFetchBack
- IRowsetImpl::m_bCanScrollBack
- ATL::IRowsetImpl::m_bCanScrollBack
- IRowsetImpl.m_bCanScrollBack
- ATL.IRowsetImpl.m_bCanScrollBack
- m_bCanScrollBack
- ATL.IRowsetImpl.m_bReset
- IRowsetImpl.m_bReset
- m_bReset
- IRowsetImpl::m_bReset
- ATL::IRowsetImpl::m_bReset
- IRowsetImpl::m_iRowset
- IRowsetImpl.m_iRowset
- ATL::IRowsetImpl::m_iRowset
- ATL.IRowsetImpl.m_iRowset
- m_iRowset
- IRowsetImpl::m_rgRowHandles
- IRowsetImpl.m_rgRowHandles
- m_rgRowHandles
- ATL::IRowsetImpl::m_rgRowHandles
- ATL.IRowsetImpl.m_rgRowHandles
dev_langs:
- C++
helpviewer_keywords:
- IRowsetImpl class
- AddRefRows method
- CreateRow method
- GetData method [OLE DB]
- GetDBStatus method
- GetNextRows method
- IRowsetImpl constructor
- RefRows method
- ReleaseRows method
- RestartPosition method
- SetDBStatus method
- m_bCanFetchBack
- m_bCanScrollBack
- m_bReset
- m_iRowset
- m_rgRowHandles
ms.assetid: 6a9189af-7556-45b1-adcb-9d62bb36704c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 59793d206f8b53d57347070cbfccd6d98ff2c005
ms.sourcegitcommit: e5792fcb89b9ba64c401f90f4f26a8e45d4a2359
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2018
ms.locfileid: "39321950"
---
# <a name="irowsetimpl-class"></a>IRowsetImpl 类
提供 `IRowset` 接口的实现。  
  
## <a name="syntax"></a>语法

```cpp
template <  
   class T,   
   class RowsetInterface,  
   class RowClass = CSimpleRow,  
   class MapClass = CAtlMap <  
      RowClass::KeyType,  
      RowClass*>>  
class ATL_NO_VTABLE IRowsetImpl : public RowsetInterface  
```  
  
### <a name="parameters"></a>参数  
 *T*  
 您的类，派生自`IRowsetImpl`。  
  
 *RowsetInterface*  
 一个类派生自`IRowsetImpl`。  
  
 *RowClass*  
 存储单位`HROW`。  
  
 *MapClass*  
 持有的提供程序的所有行句柄的存储单元。  

## <a name="requirements"></a>要求  
 **标头：** atldb.h  
  
## <a name="members"></a>成员  
  
### <a name="methods"></a>方法  
  
|||  
|-|-|  
|[AddRefRows](#addrefrows)|将引用计数添加到现有的行控点。|  
|[CreateRow](#createrow)|调用[GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)分配新`HROW`。 不直接由用户调用。|  
|[GetData](#getdata)|从行的行集的副本检索数据。|  
|[GetDBStatus](#getdbstatus)|返回指定字段的状态。|  
|[GetNextRows](#getnextrows)|记住的以前的位置按顺序提取行。|  
|[IRowsetImpl](#irowsetimpl)|构造函数。 不直接由用户调用。|  
|[RefRows](#refrows)|调用[AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md)并[ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md)。 不直接由用户调用。|  
|[ReleaseRows](#releaserows)|释放行。|  
|[RestartPosition](#restartposition)|将下次提取位置重新定位到其初始位置;也就是说，其位置，第一个行集时创建。|  
|[SetDBStatus](#setdbstatus)|设置指定字段的状态标志。|  
  
### <a name="data-members"></a>数据成员  
  
|||  
|-|-|  
|[m_bCanFetchBack](#bcanfetchback)|指示提供程序是否支持向后提取。|  
|[m_bCanScrollBack](#bcanscrollback)|指示提供程序是否可以向后具有其游标滚动。|  
|[m_bReset](#breset)|指示提供程序是否已重置其光标位置。 这具有特殊含义时向后滚动或向后在提取[GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)。|  
|[m_iRowset](#irowset)|表示光标的行集的索引。|  
|[m_rgRowHandles](#rgrowhandles)|行句柄的列表。|  
  
## <a name="remarks"></a>备注  
 [IRowset](https://msdn.microsoft.com/library/ms720986.aspx)是基础行集接口。  

## <a name="addrefrows"></a> Irowsetimpl:: Addrefrows
将引用计数添加到现有的行控点。  
  
### <a name="syntax"></a>语法  
  
```cpp
      STDMETHOD(AddRefRows )(DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBREFCOUNT rgRefCounts[],  
   DBROWSTATUS rgRowStatus[]);  
```  
  
#### <a name="parameters"></a>参数  
 请参阅[irowset:: Addrefrows](https://msdn.microsoft.com/library/ms719619.aspx)中*OLE DB 程序员参考*。  

## <a name="createrow"></a> Irowsetimpl:: Createrow
调用的帮助器方法[GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)分配新`HROW`。  
  
### <a name="syntax"></a>语法  
  
```cpp
HRESULT CreateRow(DBROWOFFSET lRowsOffset,  
  DBCOUNTITEM& cRowsObtained,  
   HROW* rgRows);  
```  
  
#### <a name="parameters"></a>参数  
 *lRowsOffset*  
 正在创建的行的游标位置。  
  
 *cRowsObtained*  
 返回给用户创建的行数，该值指示传递的引用。  
  
 *rgRows*  
 一个数组`HROW`返回给调用方具有新创建的行句柄。  
  
### <a name="remarks"></a>备注  
 如果存在行，此方法会调用[AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) ，并返回。 否则为它分配 RowClass 模板变量的新实例并将其添加到[m_rgRowHandles](../../data/oledb/irowsetimpl-m-rgrowhandles.md)。  
  
## <a name="getdata"></a> Irowsetimpl:: Getdata
从行的行集的副本检索数据。  
  
### <a name="syntax"></a>语法  
  
```cpp
      STDMETHOD(GetData )(HROW hRow,  
   HACCESSOR hAccessor,  
   void* pDstData);  
```  
  
#### <a name="parameters"></a>参数  
 请参阅[irowset:: Getdata](https://msdn.microsoft.com/library/ms716988.aspx)中*OLE DB 程序员参考*。  
  
 某些参数对应于*OLE DB 程序员参考*中所述的不同名称的参数`IRowset::GetData`:  
  
|OLE DB 模板参数|*OLE DB 程序员参考*参数|  
|--------------------------------|------------------------------------------------|  
|*pDstData*|*pData*|  
  
### <a name="remarks"></a>备注  
 此外可以处理数据转换使用 OLE DB 数据转换 DLL。 

## <a name="getdbstatus"></a> Irowsetimpl:: Getdbstatus
返回指定字段的 DBSTATUS 状态标志。  
  
### <a name="syntax"></a>语法  
  
```cpp
      virtual DBSTATUS GetDBStatus(RowClass* currentRow,  
   ATLCOLUMNINFO* columnNames);  
```  
  
#### <a name="parameters"></a>参数  
 [in]*currentRow*  
 当前行。  
  
 [in]*columnNames*  
 正在为其请求状态列。  
  
### <a name="return-value"></a>返回值  
 [DBSTATUS](https://msdn.microsoft.com/library/ms722617.aspx)该列的标志。 

## <a name="getnextrows"></a> Irowsetimpl:: Getnextrows
记住的以前的位置按顺序提取行。  
  
### <a name="syntax"></a>语法  
  
```cpp
      STDMETHOD(GetNextRows )(HCHAPTER hReserved,  
   DBROWOFFSET lRowsOffset,  
   DBROWCOUNT cRows,  
   DBCOUNTITEM* pcRowsObtained,  
   HROW** prghRows);  
```  
  
#### <a name="parameters"></a>参数  
 请参阅[irowset:: Getnextrows](https://msdn.microsoft.com/library/ms709827.aspx)中*OLE DB 程序员参考*。 

## <a name="irowsetimpl"></a> Irowsetimpl:: Irowsetimpl
构造函数。  
  
### <a name="syntax"></a>语法  
  
```cpp
IRowsetImpl();  
  
```  
  
### <a name="remarks"></a>备注  
 通常不需要直接调用此方法。  

## <a name="refrows"></a> Irowsetimpl:: Refrows
调用[AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md)并[ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md)要递增或发布到现有的行句柄的引用计数。  
  
### <a name="syntax"></a>语法  
  
```cpp
HRESULT RefRows(DBCOUNTITEM cRows,  
   const HROWrghRows[],  
   DBREFCOUNT rgRefCounts[],  
   DBROWSTATUS rgRowStatus[],  
   BOOL bAdd);  
```  
  
#### <a name="parameters"></a>参数  
 请参阅[irowset:: Addrefrows](https://msdn.microsoft.com/library/ms719619.aspx)中*OLE DB 程序员参考*。  
  
### <a name="return-value"></a>返回值  
 标准的 HRESULT 值。  

## <a name="releaserows"></a> Irowsetimpl:: Releaserows
释放行。  
  
### <a name="syntax"></a>语法  
  
```cpp
      STDMETHOD(ReleaseRows )(DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBROWOPTIONS rgRowOptions[],  
   DBREFCOUNT rgRefCounts[],  
   DBROWSTATUS rgRowStatus[]);  
```  
  
#### <a name="parameters"></a>参数  
 请参阅[irowset:: Releaserows](https://msdn.microsoft.com/library/ms719771.aspx)中*OLE DB 程序员参考*。  

## <a name="restartposition"></a> Irowsetimpl:: Restartposition
将下次提取位置重新定位到其初始位置;也就是说，其位置，第一个行集时创建。  
  
### <a name="syntax"></a>语法  
  
```cpp
      STDMETHOD(RestartPosition )(HCHAPTER /* hReserved */);  
```  
  
#### <a name="parameters"></a>参数  
 请参阅[irowset:: Restartposition](https://msdn.microsoft.com/library/ms712877.aspx)中*OLE DB 程序员参考*。  
  
### <a name="remarks"></a>备注  
 行集位置之前未定义`GetNextRow`调用。 您可以向后移动 rowet 中通过调用`RestartPosition`然后提取或向后滚动。  

## <a name="setdbstatus"></a> Irowsetimpl:: Setdbstatus
设置指定字段的 DBSTATUS 状态标志。  
  
### <a name="syntax"></a>语法  
  
```cpp
      virtual HRESULT SetDBStatus(DBSTATUS* statusFlags,  
   RowClass* currentRow,  
   ATLCOLUMNINFO* columnInfo);  
```  
  
#### <a name="parameters"></a>参数  
 *statusFlags*  
 [DBSTATUS](https://msdn.microsoft.com/library/ms722617.aspx)标志设置为列。  
  
 *currentRow*  
 当前行。  
  
 *columnInfo*  
 为其设置状态列。  
  
### <a name="return-value"></a>返回值  
 标准的 HRESULT 值。  
  
### <a name="remarks"></a>备注  
 提供程序重写此函数可提供 DBSTATUS_S_ISNULL 和 DBSTATUS_S_DEFAULT 的特殊处理。 

## <a name="bcanfetchback"></a> Irowsetimpl:: M_bcanfetchback
指示提供程序是否支持向后提取。  
  
### <a name="syntax"></a>语法  
  
```cpp
unsigned m_bCanFetchBack:1;  
  
```  
  
### <a name="remarks"></a>备注  
 链接到`DBPROP_CANFETCHBACKWARDS`中的属性`DBPROPSET_ROWSET`组。 提供程序必须支持`DBPROP_CANFETCHBACKWARDS`有关`m_bCanFetchBackwards`要**true**。  

## <a name="bcanscrollback"></a> Irowsetimpl:: M_bcanscrollback
指示提供程序是否可以向后具有其游标滚动。  
  
### <a name="syntax"></a>语法  
  
```cpp
unsigned  m_bCanScrollBack:1;  
  
```  
  
### <a name="remarks"></a>备注  
 链接到`DBPROP_CANSCROLLBACKWARDS`中的属性`DBPROPSET_ROWSET`组。 提供程序必须支持`DBPROP_CANSCROLLBACKWARDS`有关`m_bCanFetchBackwards`要**true**。 

## <a name="breset"></a> Irowsetimpl:: M_breset
一个位标志，用于确定是否在行集上定义的游标位置。  
  
### <a name="syntax"></a>语法  
  
```cpp
unsigned m_bReset:1;  
  
```  
  
### <a name="remarks"></a>备注  
 如果使用者调用[GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)与负`lOffset`或*cRows*并`m_bReset`为 true，`GetNextRows`将移动到行集结尾。 如果`m_bReset`为 false，使用者接收错误代码，为了符合 OLE DB 规范。 `m_bReset`标志获取设置为**true**首次创建行集时，当使用者调用[irowsetimpl:: Restartposition](../../data/oledb/irowsetimpl-restartposition.md)。 获取设置为**false**当你调用`GetNextRows`。 

## <a name="irowset"></a> Irowsetimpl:: M_irowset
表示光标的行集的索引。  
  
### <a name="syntax"></a>语法  
  
```cpp
DBROWOFFSET m_iRowset;  
  
```  

## <a name="rgrowhandles"></a> Irowsetimpl:: M_rgrowhandles
当前提供程序在响应中包含的行句柄映射`GetNextRows`。  
  
### <a name="syntax"></a>语法  
  
```cpp
MapClass  
 m_rgRowHandles;  
  
```  
  
### <a name="remarks"></a>备注  
 行句柄已通过调用`ReleaseRows`。 请参阅[IRowsetImpl 概述](../../data/oledb/irowsetimpl-class.md)的定义*MapClass*。  

## <a name="see-also"></a>请参阅  
 [OLE DB 提供程序模板](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 提供程序模板体系结构](../../data/oledb/ole-db-provider-template-architecture.md)    
 [CSimpleRow 类](../../data/oledb/csimplerow-class.md)
