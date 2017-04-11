---
title: "CWordArray 类 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWordArray
- AFXCOLL/CWordArray
- AFXCOLL/CObArray::CObArray
- AFXCOLL/CObArray::Add
- AFXCOLL/CObArray::Append
- AFXCOLL/CObArray::Copy
- AFXCOLL/CObArray::ElementAt
- AFXCOLL/CObArray::FreeExtra
- AFXCOLL/CObArray::GetAt
- AFXCOLL/CObArray::GetCount
- AFXCOLL/CObArray::GetData
- AFXCOLL/CObArray::GetSize
- AFXCOLL/CObArray::GetUpperBound
- AFXCOLL/CObArray::InsertAt
- AFXCOLL/CObArray::IsEmpty
- AFXCOLL/CObArray::RemoveAll
- AFXCOLL/CObArray::RemoveAt
- AFXCOLL/CObArray::SetAt
- AFXCOLL/CObArray::SetAtGrow
- AFXCOLL/CObArray::SetSize
dev_langs:
- C++
helpviewer_keywords:
- INT
- UINT
- indexed arrays
- arrays [C++], indexed
- WORD data type
- CWordArray class
ms.assetid: 2ba2c194-2c6c-40ff-9db4-e9dbe57e1f57
caps.latest.revision: 26
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: cd6c26c49c6b46449ec6d7da42b9166d17d563da
ms.lasthandoff: 02/24/2017

---
# <a name="cwordarray-class"></a>CWordArray 类
支持 16 位数组。  
  
## <a name="syntax"></a>语法  
  
```  
class CWordArray : public CObject  
```  
  
## <a name="members"></a>成员  
 成员函数`CWordArray`类似于类的成员函数[CObArray](../../mfc/reference/cobarray-class.md)。 由于此相似性，因此你可以使用 `CObArray` 参考文档获取成员函数细节。 无论您在何处[CObject](../../mfc/reference/cobject-class.md)指针作为函数参数或返回值，替换**WORD**。  
  
 `CObject* CObArray::GetAt( int <nIndex> ) const;`  
  
 例如，转换为  
  
 `WORD CWordArray::GetAt( int <nIndex> ) const;`  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|说明|  
|----------|-----------------|  
|[CObArray::CObArray](../../mfc/reference/cobarray-class.md#cobarray)|构造一个空数组。|  
  
### <a name="public-methods"></a>公共方法  
  
|名称|描述|  
|----------|-----------------|  
|[CObArray::Add](../../mfc/reference/cobarray-class.md#add)|向数组的末尾添加一个元素；根据需要扩展该数组。|  
|[CObArray::Append](../../mfc/reference/cobarray-class.md#append)|将另一个数组追加到该数组中；根据需要扩展该数组。|  
|[CObArray::Copy](../../mfc/reference/cobarray-class.md#copy)|将另一个数组复制到该数组；根据需要扩展该数组。|  
|[CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)|在该数组中返回对元素指针的临时引用。|  
|[CObArray::FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|若高于当前的上限，则将释放所有未使用的内存。|  
|[CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)|返回给定索引位置处的值。|  
|[CObArray::GetCount](../../mfc/reference/cobarray-class.md#getcount)|获取此数组中的元素数。|  
|[CObArray::GetData](../../mfc/reference/cobarray-class.md#getdata)|允许访问该数组中的元素。 可以是**NULL**。|  
|[CObArray::GetSize](../../mfc/reference/cobarray-class.md#getsize)|获取此数组中的元素数。|  
|[CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)|返回最大的有效索引。|  
|[CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)|在指定索引处插入一个元素（或另一个数组中的所有元素）。|  
|[CObArray::IsEmpty](../../mfc/reference/cobarray-class.md#isempty)|确定数组是否为空。|  
|[CObArray::RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|从此数组中移除所有元素。|  
|[CObArray::RemoveAt](../../mfc/reference/cobarray-class.md#removeat)|移除特定索引处的元素。|  
|[CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat)|设置给定索引的值；不允许对该数组进行扩展。|  
|[CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)|设置给定索引的值；根据需要扩展该数组。|  
|[CObArray::SetSize](../../mfc/reference/cobarray-class.md#setsize)|设置要在该数组中包含的元素数。|  
  
### <a name="public-operators"></a>公共运算符  
  
|名称|说明|  
|----------|-----------------|  
|[CObArray::operator&#91;&#93;](../../mfc/reference/cobarray-class.md#operator_at)|设置或获取位于指定索引处的元素。|  
  
## <a name="remarks"></a>备注  
 `CWordArray`集成了[IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)宏来支持序列化和转储的它的元素。 如果单词的数组存储到存档中，使用重载的插入运算符或[cobject:: Serialize](../../mfc/reference/cobject-class.md#serialize)成员函数，每个元素，接下来序列化。  
  
> [!NOTE]
>  在使用数组之前，先使用 `SetSize` 建立其大小并为其分配内存。 如果不使用 `SetSize`，则向数组添加元素会导致它经常重新分配和复制。 经常重新分配和复制会降低效率而且会产生内存碎片。  
  
 如果您需要在数组中的各个元素的转储，必须将转储上下文的深度设置为 1 或更高。  
  
 有关详细信息使用`CWordArray`，请参阅文章[集合](../../mfc/collections.md)。  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CWordArray`  
  
## <a name="requirements"></a>要求  
 **标头︰** afxcoll.h  
  
##  <a name="icommandsource_interface"></a>ICommandSource 接口  
 管理命令从命令源对象发送到用户控件。  
  
```  
interface class ICommandSource  
```  
  
### <a name="remarks"></a>备注  
 当宿主中 MFC 视图的用户控件时[CWinFormsView 类](../../mfc/reference/cwinformsview-class.md)路由命令和更新命令 UI 向用户控件的消息以允许它处理 MFC 命令 （例如，框架菜单项和工具栏按钮）。 通过实现时，可以将用户控件的参考`ICommandSource`对象。  
  
 请参阅[如何︰ 向 Windows 窗体控件添加命令传送](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)以举例说明如何使用`ICommandTarget`。  
  
 有关使用 Windows 窗体的详细信息，请参阅[在 MFC 中使用 Windows 窗体用户控件](../../dotnet/using-a-windows-form-user-control-in-mfc.md)。  
  
##  <a name="addcommandhandler"></a>ICommandSource::AddCommandHandler  
 将命令处理程序添加到命令源对象。  
  
```  
void AddCommandHandler(
    unsigned int cmdID,  
    CommandHandler^ cmdHandler);
```  
  
### <a name="parameters"></a>参数  
 `cmdID`  
 命令 ID。  
  
 `cmdHandler`  
 命令处理程序方法的句柄。  
  
### <a name="remarks"></a>备注  
 此方法添加命令处理程序`cmdHandler`到命令源对象，并将映射到处理程序`cmdID`。  
  
 请参阅[如何︰ 向 Windows 窗体控件添加命令传送](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)以举例说明如何使用`AddCommandHandler`。  
  
##  <a name="addcommandrangehandler"></a>ICommandSource::AddCommandRangeHandler  
 将一组命令处理程序添加到命令源对象。  
  
```  
void AddCommandRangeHandler(
    unsigned int cmdIDMin,  
    unsigned int cmdIDMax,  
    CommandHandler^ cmdHandler);
```  
  
### <a name="parameters"></a>参数  
 `cmdIDMin`  
 命令 ID 范围的起始索引。  
  
 `cmdIDMax`  
 命令 ID 范围的结束索引。  
  
 `cmdHandler`  
 命令映射到的消息处理程序方法的句柄。  
  
### <a name="remarks"></a>备注  
 此方法将一组连续的命令 Id 映射到单个消息处理程序，并将其添加到命令源对象。 这适用于带有一种方法处理一组相关的按钮。  
  
##  <a name="addcommandrangeuihandler"></a>ICommandSource::AddCommandRangeUIHandler  
 将一组用户界面的命令消息处理程序添加到命令源对象。  
  
```  
void AddCommandRangeUIHandler(
    unsigned int cmdIDMin,   
    unsigned int cmdIDMax,   
    CommandUIHandler^ cmdUIHandler);
```  
  
### <a name="parameters"></a>参数  
 `cmdIDMin`  
 命令 ID 范围的起始索引。  
  
 `cmdIDMax`  
 命令 ID 范围的结束索引。  
  
 `cmdHandler`  
 命令映射到的消息处理程序方法的句柄。  
  
### <a name="remarks"></a>备注  
 此方法将一组连续的命令 Id 映射到单个用户界面命令消息处理程序，并将其添加到命令源对象。 这适用于带有一种方法处理一组相关的按钮。  
  
##  <a name="addcommanduihandler"></a>ICommandSource::AddCommandUIHandler  
 将用户界面命令消息处理程序添加到命令源对象。  
  
```  
void AddCommandUIHandler(
    unsigned int cmdID,   
    CommandUIHandler^ cmdUIHandler);
```  
  
### <a name="parameters"></a>参数  
 `cmdID`  
 命令 ID。  
  
 `cmdUIHandler`  
 用户界面命令消息处理程序方法的句柄。  
  
### <a name="remarks"></a>备注  
 此方法将添加的用户界面命令消息处理程序`cmdHandler`到命令源对象，并将映射到处理程序`cmdID`。  
  
##  <a name="postcommand"></a>ICommandSource::PostCommand  
 将消息发送而无需等待被处理。  
  
```  
void PostCommand(unsigned int command);
```  
  
### <a name="parameters"></a>参数  
 `command`  
 要发布的消息的命令 ID。  
  
### <a name="remarks"></a>备注  
 此方法以异步方式将映射到由指定 ID 的邮件投递`command`。 它将调用[CWnd::PostMessage](../../mfc/reference/cwnd-class.md#postmessage)将消息放入窗口的消息队列，然后又返回，而无需等待相应的窗口来处理该消息。  
  
##  <a name="removecommandhandler"></a>ICommandSource::RemoveCommandHandler  
 从命令源对象中删除命令处理程序。  
  
```  
void RemoveCommandHandler(unsigned int cmdID);
```  
  
### <a name="parameters"></a>参数  
 `cmdID`  
 命令 ID。  
  
### <a name="remarks"></a>备注  
 此方法可以删除命令处理程序映射到`cmdID`命令源对象中。  
  
##  <a name="removecommandrangehandler"></a>ICommandSource::RemoveCommandRangeHandler  
 从命令源对象中删除一组命令处理程序。  
  
```  
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,  
    unsigned int cmdIDMax);
```  
  
### <a name="parameters"></a>参数  
 `cmdIDMin`  
 命令 ID 范围的起始索引。  
  
 `cmdIDMax`  
 命令 ID 范围的结束索引。  
  
### <a name="remarks"></a>备注  
 此方法中删除一组映射到由指定的命令 Id 的消息处理程序`cmdIDMin`和`cmdIDMax`，从命令源对象。  
  
##  <a name="removecommandrangeuihandler"></a>ICommandSource::RemoveCommandRangeUIHandler  
 从命令源对象中删除一组用户界面的命令消息处理程序。  
  
```  
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,  
    unsigned int cmdIDMax);
```  
  
### <a name="parameters"></a>参数  
 `cmdIDMin`  
 命令 ID 范围的起始索引。  
  
 `cmdIDMax`  
 命令 ID 范围的结束索引。  
  
### <a name="remarks"></a>备注  
 此方法中删除一组用户界面命令消息处理程序，映射到由指定的命令 Id`cmdIDMin`和`cmdIDMax`，从命令源对象。  
  
##  <a name="removecommanduihandler"></a>ICommandSource::RemoveCommandUIHandler  
 从命令源对象中删除一个用户界面命令消息处理程序。  
  
```  
void RemoveCommandUIHandler(unsigned int cmdID);
```  
  
### <a name="parameters"></a>参数  
 `cmdID`  
 命令 ID。  
  
### <a name="remarks"></a>备注  
 此方法移除的用户界面命令消息处理程序映射到`cmdID`命令源对象中。  
  
##  <a name="sendcommand"></a>ICommandSource::SendCommand  
 发送一条消息并等待在返回之前要处理。  
  
```  
void SendCommand(unsigned int command);
```  
  
### <a name="parameters"></a>参数  
 `command`  
 要发送的消息的命令 ID。  
  
### <a name="remarks"></a>备注  
 此方法以同步方式将消息映射到由指定的 ID 发送`command`。 它将调用[CWnd::SendMessage](../../mfc/reference/cwnd-class.md#sendmessage)将消息放入窗口的消息队列并等待，直到该窗口过程在返回前处理消息。  
  
##  <a name="icommandtarget_interface"></a>ICommandTarget 接口  
 使用接口来接收命令源对象中的命令提供了一个用户控件。  
  
```  
interface class ICommandTarget  
```  
  
### <a name="remarks"></a>备注  
 当宿主中 MFC 视图的用户控件时[CWinFormsView](../../mfc/reference/cwinformsview-class.md)路由命令和更新命令 UI 向用户控件的消息以允许它处理 MFC 命令 （例如，框架菜单项和工具栏按钮）。 通过实现`ICommandTarget`，让用户能够控制对该对象的引用。  
  
 请参阅[如何︰ 向 Windows 窗体控件添加命令传送](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)以举例说明如何使用`ICommandTarget`。  
  
 有关使用 Windows 窗体的详细信息，请参阅[在 MFC 中使用 Windows 窗体用户控件](../../dotnet/using-a-windows-form-user-control-in-mfc.md)。  
  
##  <a name="initialize"></a>ICommandTarget::Initialize  
 初始化命令目标对象。  
  
```  
void Initialize(ICommandSource^ cmdSource);
```  
  
### <a name="parameters"></a>参数  
 `cmdSource`  
 命令源对象的句柄。  
  
### <a name="remarks"></a>备注  
 当宿主中 MFC 视图的用户控件时[CWinFormsView](../../mfc/reference/cwinformsview-class.md)路由命令和更新命令 UI 向用户控件的消息以允许它处理 MFC 命令。  
  
 此方法初始化命令目标对象，并将其与指定的命令源对象相关联`cmdSource`。 用户控件类实现中，应调用它。 在初始化时，你应该注册命令处理程序的命令源对象通过调用[ICommandSource::AddCommandHandler](../../mfc/reference/icommandsource-interface.md)中`Initialize`实现。 请参阅[如何︰ 向 Windows 窗体控件添加命令传送](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)以举例说明如何使用`Initialize`要这样做。  
  
##  <a name="icommandui_interface"></a>ICommandUI 接口  
 管理用户界面命令。  
  
```  
interface class ICommandUI  
```  
  
### <a name="remarks"></a>备注  
 此接口提供方法和属性，管理用户界面命令。 `ICommandUI`类似于[CCmdUI 类](../../mfc/reference/ccmdui-class.md)，只不过`ICommandUI`用于 MFC 应用程序与.NET 组件进行互操作。  
  
 `ICommandUI`在中使用`ON_UPDATE_COMMAND_UI`处理程序的派生类中。 当应用程序的用户激活 （选择或单击） 菜单上，每个菜单项将显示为已启用或禁用。 每个菜单命令的目标提供此信息通过实现`ON_UPDATE_COMMAND_UI`处理程序。 对于每个应用程序中的命令用户界面对象，使用属性窗口来创建消息映射项和每个处理程序的函数原型。  
  
 有关详细信息如何`ICommandUI`接口使用在命令路由，请参阅[如何︰ 向 Windows 窗体控件添加命令传送](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)。  
  
 有关使用 Windows 窗体的详细信息，请参阅[在 MFC 中使用 Windows 窗体用户控件](../../dotnet/using-a-windows-form-user-control-in-mfc.md)。  
  
 在 MFC 中如何管理用户界面命令的详细信息，请参阅[CCmdUI 类](../../mfc/reference/ccmdui-class.md)。  
  
##  <a name="check"></a>ICommandUI::Check  
 将此命令的用户界面项设置为相应的复选状态。  
  
```  
property UICheckState Check;  
```  
  
### <a name="remarks"></a>备注  
 此属性将此命令的用户界面项设置为相应的复选状态。 设置`Check`为下列值︰  
  
|术语|定义|  
|----------|----------------|  
|0|取消选中|  
|1|选中|  
|2|不确定的组|  
  
##  <a name="continuerouting"></a>ICommandUI::ContinueRouting  
 告知命令路由机制，继续传送当前消息的处理程序链的下方。  
  
```  
void ContinueRouting();
```  
  
### <a name="remarks"></a>备注  
 这是一个高级的成员函数，应结合使用[ON_COMMAND_EX](http://msdn.microsoft.com/library/0bb49090-aee8-4203-87c8-dd001d3dd26e)处理程序，它返回`FALSE`。 有关详细信息，请参阅技术说明[TN006︰ 消息映射](../../mfc/tn006-message-maps.md)。  
  
##  <a name="enabled"></a>ICommandUI::Enabled  
 启用或禁用此命令的用户界面项。  
  
```  
property bool Enabled;  
```  
  
### <a name="remarks"></a>备注  
 此属性启用或禁用此命令的用户界面项。 设置`Enabled`到`TRUE`以启用项，`FALSE`以将其禁用。  
  
##  <a name="id"></a>ICommandUI::ID  
 获取所表示的用户界面对象的 ID`ICommandUI`对象。  
  
```  
property unsigned int ID;  
```  
  
### <a name="remarks"></a>备注  
 此属性获取菜单项，工具栏按钮的 ID （句柄） 或由其他用户界面对象表示`ICommandUI`对象。  
  
##  <a name="index"></a>ICommandUI::Index  
 获取所表示的用户界面对象的索引`ICommandUI`对象。  
  
```  
property unsigned int Index;  
```  
  
### <a name="remarks"></a>备注  
 此属性获取菜单项，工具栏按钮的索引 （句柄） 或由其他用户界面对象表示`ICommandUI`对象。  
  
##  <a name="radio"></a>ICommandUI::Radio  
 将此命令的用户界面项设置为相应的复选状态。  
  
```  
property bool Radio;  
```  
  
### <a name="remarks"></a>备注  
 此属性将此命令的用户界面项设置为相应的复选状态。 设置`Radio`到`TRUE`以启用项; 否则为`FALSE`。  
  
##  <a name="text"></a>ICommandUI::Text  
 设置此命令的用户界面项的文本。  
  
```  
property String^ Text;  
```  
  
### <a name="remarks"></a>备注  
 此属性设置为此命令的用户界面项的文本。 设置`Text`文本字符串句柄。  
  
##  <a name="iview_interface"></a>IView 接口  
 实现几种方法， [CWinFormsView](../../mfc/reference/cwinformsview-class.md)用于向托管控件发送查看通知。  
  
```  
interface class IView  
```  
  
### <a name="remarks"></a>备注  
 `IView`实现几种方法，`CWinFormsView`用于转发到承载的托管控件的常见查看通知。 这些是[OnInitialUpdate](../../mfc/reference/iview-interface.md)， [OnUpdate](../../mfc/reference/iview-interface.md)和[OnActivateView](../../mfc/reference/iview-interface.md)。  
  
 `IView`类似于[CView](../../mfc/reference/cview-class.md)，但仅用于托管的视图和控件。  
  
 有关使用 Windows 窗体的详细信息，请参阅[在 MFC 中使用 Windows 窗体用户控件](../../dotnet/using-a-windows-form-user-control-in-mfc.md)。  
  
##  <a name="onactivateview"></a>IView::OnActivateView  
 激活或停用视图时由 MFC 调用。  
  
```  
void OnActivateView(bool activate);
```  
  
### <a name="parameters"></a>参数  
 `activate`  
 指示是否视图处于激活还是停用状态。  
  
##  <a name="oninitialupdate"></a>IView::OnInitialUpdate  
 查看第一次附加到文档之后, 但在最初显示的视图之前，由框架调用。  
  
```  
void OnInitialUpdate();
```  
  
##  <a name="onupdate"></a>IView::OnUpdate  
 由 MFC 视图的文档，修改后调用。  
  
```  
void OnUpdate();
```  
  
### <a name="remarks"></a>备注  
 使用此功能，要更新以反映修改其显示的视图。  
  
## <a name="see-also"></a>另请参阅  
 [MFC 示例收集](../../visual-cpp-samples.md)   
 [CObject 类](../../mfc/reference/cobject-class.md)   
 [层次结构图](../../mfc/hierarchy-chart.md)



