---
title: IDBInitializeImpl 类 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IDBInitializeImpl<T>
- ATL::IDBInitializeImpl<T>
- IDBInitializeImpl
- ATL::IDBInitializeImpl
- ATL.IDBInitializeImpl
- IDBInitializeImpl.IDBInitializeImpl
- IDBInitializeImpl
- IDBInitializeImpl::IDBInitializeImpl
- Initialize
- IDBInitializeImpl::Initialize
- IDBInitializeImpl.Initialize
- IDBInitializeImpl.Uninitialize
- Uninitialize
- IDBInitializeImpl::Uninitialize
- ATL::IDBInitializeImpl::m_dwStatus
- IDBInitializeImpl.m_dwStatus
- ATL.IDBInitializeImpl.m_dwStatus
- IDBInitializeImpl::m_dwStatus
- IDBInitializeImpl<T>::m_dwStatus
- ATL.IDBInitializeImpl<T>.m_dwStatus
- ATL::IDBInitializeImpl<T>::m_dwStatus
- m_dwStatus
- ATL::IDBInitializeImpl<T>::m_pCUtlPropInfo
- m_pCUtlPropInfo
- IDBInitializeImpl::m_pCUtlPropInfo
- ATL.IDBInitializeImpl.m_pCUtlPropInfo
- IDBInitializeImpl<T>::m_pCUtlPropInfo
- IDBInitializeImpl.m_pCUtlPropInfo
- ATL::IDBInitializeImpl::m_pCUtlPropInfo
dev_langs:
- C++
helpviewer_keywords:
- IDBInitializeImpl class
- IDBInitializeImpl constructor
- Initialize method
- Uninitialize method
- m_dwStatus
- m_pCUtlPropInfo
ms.assetid: e4182f81-0443-44f5-a0d3-e7e075d6f883
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 69c7f92110312d4ae8cff427d1081853290919e9
ms.sourcegitcommit: b0d6777cf4b580d093eaf6104d80a888706e7578
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2018
ms.locfileid: "39269919"
---
# <a name="idbinitializeimpl-class"></a>IDBInitializeImpl 类
提供一个实现[IDBInitialize](https://msdn.microsoft.com/library/ms713706.aspx)接口。  
  
## <a name="syntax"></a>语法

```cpp
template <class T>  
class ATL_NO_VTABLE IDBInitializeImpl : public IDBInitialize  
```  
  
### <a name="parameters"></a>参数  
 *T*  
 您的类，派生自`IDBInitializeImpl`。  

## <a name="requirements"></a>要求  
 **标头：** atldb.h  
  
## <a name="members"></a>成员  
  
### <a name="methods"></a>方法  
  
|||  
|-|-|  
|[IDBInitializeImpl](#idbinitializeimpl)|构造函数。|  
  
### <a name="interface-methods"></a>接口方法  
  
|||  
|-|-|  
|[Initialize](#initialize)|启动提供程序。|  
|[取消初始化](#uninitialize)|停止提供程序。|  
  
### <a name="data-members"></a>数据成员  
  
|||  
|-|-|  
|[m_dwStatus](#dwstatus)|数据源的标志。|  
|[m_pCUtlPropInfo](#pcutlpropinfo)|指向实现 DB 属性信息的指针。|  
  
## <a name="remarks"></a>备注  
 数据源对象和枚举器上使用的可选接口上必需的接口。  

## <a name="idbinitializeimpl"></a> Idbinitializeimpl:: Idbinitializeimpl
构造函数。  
  
### <a name="syntax"></a>语法  
  
```cpp
IDBInitializeImpl();  
  
```  
  
### <a name="remarks"></a>备注  
 初始化所有数据成员。 
  
## <a name="initialize"></a> Idbinitializeimpl:: Initialize
通过准备数据源对象的属性支持来初始化该对象。  
  
### <a name="syntax"></a>语法  
  
```cpp
      STDMETHOD(Initialize)(void);  
```  
  
### <a name="remarks"></a>备注  
 请参阅[idbinitialize:: Initialize](https://msdn.microsoft.com/library/ms718026.aspx)中*OLE DB 程序员参考*。 

## <a name="uninitialize"></a> Idbinitializeimpl:: Uninitialize
位置数据源，因为内部资源，例如属性支持未初始化状态的对象。  
  
### <a name="syntax"></a>语法  
  
```cpp
      STDMETHOD(Uninitialize)(void);  
```  
  
### <a name="remarks"></a>备注  
 请参阅[IDBInitialize::Uninitialize](https://msdn.microsoft.com/library/ms719648.aspx)中*OLE DB 程序员参考*。

## <a name="dwstatus"></a> Idbinitializeimpl:: M_dwstatus
数据源的标志。  
  
### <a name="syntax"></a>语法  
  
```cpp
DWORD m_dwStatus;  
  
```  
  
### <a name="remarks"></a>备注  
 这些标志指定，或者表示为数据源对象的各种属性的状态。 包含一个或多个以下**枚举**值：  
  
```  
enum DATASOURCE_FLAGS {  
    DSF_MASK_INIT     = 0xFFFFF00F,  
    DSF_PERSIST_DIRTY = 0x00000001,  
    DSF_INITIALIZED   = 0x00000010,  
};  
```  
  
|||  
|-|-|  
|`DSF_MASK_INIT`|一个掩码，若要启用的未初始化状态还原。|  
|`DSF_PERSIST_DIRTY`|如果数据源对象 （即，如果进行了更改） 需要持久性，设置。|  
|`DSF_INITIALIZED`|如果初始化数据源，设置。|  

## <a name="pcutlpropinfo"></a> Idbinitializeimpl:: M_pcutlpropinfo
指向实现对象，用于 DB 属性信息的指针。  
  
### <a name="syntax"></a>语法  
  
```cpp
CUtlPropInfo<  
T  
>* m_pCUtlPropInfo;  
  
```  
  
## <a name="see-also"></a>请参阅  
 [OLE DB 提供程序模板](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 提供程序模板体系结构](../../data/oledb/ole-db-provider-template-architecture.md)
