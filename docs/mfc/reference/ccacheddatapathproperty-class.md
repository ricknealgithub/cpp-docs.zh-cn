---
title: CCachedDataPathProperty 类 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::m_Cache
dev_langs:
- C++
helpviewer_keywords:
- CCachedDataPathProperty [MFC], CCachedDataPathProperty
- CCachedDataPathProperty [MFC], m_Cache
ms.assetid: 0d81356b-4fe5-43f6-aed2-2eb5a5485706
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f0a3f632f2da327dea698722177ba6a3b3ebe42d
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37339782"
---
# <a name="ccacheddatapathproperty-class"></a>CCachedDataPathProperty 类
实现异步传输并在内存文件中缓冲的 OLE 控件属性。  
  
## <a name="syntax"></a>语法  
  
```  
class CCachedDataPathProperty : public CDataPathProperty  
```  
  
## <a name="members"></a>成员  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|描述|  
|----------|-----------------|  
|[CCachedDataPathProperty::CCachedDataPathProperty](#ccacheddatapathproperty)|构造 `CCachedDataPathProperty` 对象。|  
  
### <a name="public-data-members"></a>公共数据成员  
  
|名称|描述|  
|----------|-----------------|  
|[CCachedDataPathProperty::m_Cache](#m_cache)|`CMemFile` 在其中缓存数据的对象。|  
  
## <a name="remarks"></a>备注  
 内存文件存储在 RAM 中，而不是磁盘上，可用于快速临时传输。  
  
 连同`CAysncMonikerFile`并`CDataPathProperty`，`CCachedDataPathProperty`为使用异步名字对象中 OLE 控件提供功能。 与`CCachedDataPathProperty`对象，可以从 URL 或文件的源以异步方式传输数据，并将其存储在内存文件通过`m_Cache`公共变量。 所有数据都存储在内存文件中，并且没有无需重写[OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable)除非你想要监视通知和响应。 例如，如果要传输较大。GIF 文件并想要更多的数据已到达，它应重绘自己，通知您的控件重写`OnDataAvailable`进行通知。  
  
 该类`CCachedDataPathProperty`派生自`CDataPathProperty`。  
  
 有关如何在 Internet 应用程序中使用异步名字对象和 ActiveX 控件的详细信息，请参阅以下主题：  
  
- [Internet 前几个步骤： ActiveX 控件](../../mfc/activex-controls-on-the-internet.md)  
  
- [异步名字对象 Internet 前几个步骤：](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 [CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)  
  
 [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)  
  
 `CCachedDataPathProperty`  
  
## <a name="requirements"></a>要求  
 **标头：** afxctl.h  
  
##  <a name="ccacheddatapathproperty"></a>  CCachedDataPathProperty::CCachedDataPathProperty  
 构造 `CCachedDataPathProperty` 对象。  
  
```  
CCachedDataPathProperty(COleControl* pControl = NULL);

 
CCachedDataPathProperty(
    LPCTSTR lpszPath,  
    COleControl* pControl = NULL);
```  
  
### <a name="parameters"></a>参数  
 *pControl*  
 指向要与此相关联的 ActiveX 控件对象的指针`CCachedDataPathProperty`对象。  
  
 *lpszPath*  
 路径可以是绝对或相对，用于创建异步名字对象引用的属性的实际绝对位置。 `CCachedDataPathProperty` 使用 Url，不是文件名。 如果你想`CCachedDataPathProperty`对象文件中，在前面添加到路径的 file://。  
  
### <a name="remarks"></a>备注  
 `COleControl`指向对象*pControl*由[打开](../../mfc/reference/cdatapathproperty-class.md#open)和派生类来检索。 如果*pControl*为 NULL，与所使用的控件`Open`应与设置[SetControl](../../mfc/reference/cdatapathproperty-class.md#setcontrol)。 如果*lpszPath*为 NULL，可以在路径中，通过传递`Open`或将其与设置[SetPath](../../mfc/reference/cdatapathproperty-class.md#setpath)。  
  
##  <a name="m_cache"></a>  CCachedDataPathProperty::m_Cache  
 包含在其中缓存数据的内存文件的类名称。  
  
```  
CMemFile m_Cache;  
```  
  
### <a name="remarks"></a>备注  
 在 RAM 中，而不是磁盘上存储的内存文件。  
  
## <a name="see-also"></a>请参阅  
 [CDataPathProperty 类](../../mfc/reference/cdatapathproperty-class.md)   
 [层次结构图表](../../mfc/hierarchy-chart.md)   
 [CDataPathProperty 类](../../mfc/reference/cdatapathproperty-class.md)
