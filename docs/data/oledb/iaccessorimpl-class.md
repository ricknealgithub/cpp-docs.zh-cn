---
title: IAccessorImpl 类 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IAccessorImpl
- ATL.IAccessorImpl.IAccessorImpl
- ATL::IAccessorImpl::IAccessorImpl
- IAccessorImpl::IAccessorImpl
- IAccessorImpl.IAccessorImpl
- IAccessorImpl
- ATL::IAccessorImpl::AddRefAccessor
- AddRefAccessor
- IAccessorImpl::AddRefAccessor
- IAccessorImpl.AddRefAccessor
- ATL.IAccessorImpl.AddRefAccessor
- IAccessorImpl::CreateAccessor
- CreateAccessor
- ATL::IAccessorImpl::CreateAccessor
- IAccessorImpl.CreateAccessor
- ATL.IAccessorImpl.CreateAccessor
- IAccessorImpl.GetBindings
- ATL::IAccessorImpl::GetBindings
- IAccessorImpl::GetBindings
- GetBindings
- ATL.IAccessorImpl.GetBindings
- ReleaseAccessor
- IAccessorImpl::ReleaseAccessor
- ATL.IAccessorImpl.ReleaseAccessor
- ATL::IAccessorImpl::ReleaseAccessor
- IAccessorImpl.ReleaseAccessor
dev_langs:
- C++
helpviewer_keywords:
- IAccessorImpl class
- IAccessorImpl class, constructor
- IAccessorImpl constructor
- AddRefAccessor method
- CreateAccessor method
- GetBindings method
- ReleaseAccessor method
ms.assetid: 768606da-8b71-417c-a62c-88069ce7730d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0ac22d8ee45209ad6a20dcb34a75c06dd9b80b58
ms.sourcegitcommit: b0d6777cf4b580d093eaf6104d80a888706e7578
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2018
ms.locfileid: "39269883"
---
# <a name="iaccessorimpl-class"></a>IAccessorImpl 类
提供的实现[IAccessor](https://msdn.microsoft.com/library/ms719672.aspx)接口。  
  
## <a name="syntax"></a>语法

```cpp
template <class T, 
          class BindType = ATLBINDINGS,
          class BindingVector = CAtlMap <HACCESSOR hAccessor, BindType* pBindingsStructure>>  
class ATL_NO_VTABLE IAccessorImpl : public IAccessorImplBase<BindType>  
```  
  
### <a name="parameters"></a>参数  
 *T*  
 行集或命令对象类。  
  
 *BindType*  
 绑定信息的存储单位。 默认值是`ATLBINDINGS`结构 （请参阅 atldb.h）。  
  
 *BindingVector*  
 列信息的存储单元。 默认值是[CAtlMap](../../atl/reference/catlmap-class.md)其中的关键元素是 HACCESSOR 值，值元素是一个指向`BindType`结构。  
  
## <a name="requirements"></a>要求  
 **标头：** atldb.h  

## <a name="members"></a>成员  
  
### <a name="methods"></a>方法  
  
|||  
|-|-|  
|[IAccessorImpl](#iaccessorimpl)|构造函数。|  
  
### <a name="interface-methods"></a>接口方法  
  
|||  
|-|-|  
|[AddRefAccessor](#addrefaccessor)|将引用计数添加到现有的访问器。|  
|[CreateAccessor](#createaccessor)|从一组绑定创建取值函数。|  
|[GetBindings](#getbindings)|访问器中返回的绑定。|  
|[ReleaseAccessor](#releaseaccessor)|释放访问器。|  
  
## <a name="remarks"></a>备注  
 这是必需的对于行集和命令。 OLE DB 要求提供商实现 HACCESSOR，这是一种标记的数组[DBBINDING](https://msdn.microsoft.com/library/ms716845.aspx)结构。 提供的 HACCESSORs`IAccessorImpl`是地址`BindType`结构。 默认情况下`BindType`指`ATLBINDINGS`中`IAccessorImpl`的模板定义。 `BindType` 提供使用的一种机制`IAccessorImpl`跟踪中的元素数及其`DBBINDING`数组以及引用计数和访问器标志。  

## <a name="iaccessorimpl"></a> Iaccessorimpl:: Iaccessorimpl
构造函数。  
  
### <a name="syntax"></a>语法  
  
```cpp
IAccessorImpl();  
  
```  

## <a name="addrefaccessor"></a> Iaccessorimpl:: Addrefaccessor
将引用计数添加到现有的访问器。  
  
### <a name="syntax"></a>语法  
  
```cpp
      STDMETHOD(AddRefAccessor)(HACCESSOR hAccessor,  
   DBREFCOUNT* pcRefCount);  
```  
  
#### <a name="parameters"></a>参数  
 请参阅[IAccessor::AddRefAccessor](https://msdn.microsoft.com/library/ms714978.aspx)中*OLE DB 程序员参考*。

## <a name="createaccessor"></a> Iaccessorimpl:: Createaccessor
从一组绑定创建取值函数。  
  
### <a name="syntax"></a>语法  
  
```cpp
      STDMETHOD(CreateAccessor)(DBACCESSORFLAGS dwAccessorFlags,  
   DBCOUNTITEM cBindings,  
   const DBBINDING rgBindings[],  
   DBLENGTH cbRowSize,  
   HACCESSOR* phAccessor,  
   DBBINDSTATUS rgStatus[]);  
```  
  
#### <a name="parameters"></a>参数  
 请参阅[iaccessor:: Createaccessor](https://msdn.microsoft.com/library/ms720969.aspx)中*OLE DB 程序员参考*。  

## <a name="getbindings"></a> Iaccessorimpl:: Getbindings
从访问器中的使用者返回的基本列绑定。  
  
### <a name="syntax"></a>语法  
  
```cpp
      STDMETHOD(GetBindings)(HACCESSOR hAccessor,  
   DBACCESSORFLAGS* pdwAccessorFlags,  
   DBCOUNTITEM* pcBindings,  
   DBBINDING** prgBindings);  
```  
  
#### <a name="parameters"></a>参数  
 请参阅[IAccessor::GetBindings](https://msdn.microsoft.com/library/ms721253.aspx)中*OLE DB 程序员参考*。 

## <a name="releaseaccessor"></a> Iaccessorimpl:: Releaseaccessor
释放访问器。  
  
### <a name="syntax"></a>语法  
  
```cpp
      STDMETHOD(ReleaseAccessor)(HACCESSOR hAccessor,  
   DBREFCOUNT* pcRefCount);  
```  
  
#### <a name="parameters"></a>参数  
 请参阅[iaccessor:: Releaseaccessor](https://msdn.microsoft.com/library/ms719717.aspx)中*OLE DB 程序员参考*。
  
## <a name="see-also"></a>请参阅  
 [OLE DB 提供程序模板](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 提供程序模板体系结构](../../data/oledb/ole-db-provider-template-architecture.md)
