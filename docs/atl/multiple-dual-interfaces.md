---
title: 多个双重接口 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- multiple dual interfaces
- COM_INTERFACE_ENTRY2 macro
- dual interfaces, exposing multiple
- multiple dual interfaces, exposing with ATL
- IDispatchImpl class, multiple dual interfaces
- COM_INTERFACE_ENTRY_IID macro
ms.assetid: 7fea86e6-247f-4063-be6e-85588a9e3719
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ace347148f3a339c75fd9a1069be368c7373d351
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "38952924"
---
# <a name="multiple-dual-interfaces"></a>多个双重接口
您可能想要将双重接口 （即，灵活性的 vtable 和后期绑定，从而使类可用于脚本编写语言，以及 c + +） 的优点组合使用多个继承的技术。  
  
 尽管可以公开多个双重接口上的单个 COM 对象，但不建议。 如果有多个双重接口，必须有一个`IDispatch`公开接口。 方法可确保这种情况执行如降低函数或提高的代码复杂性的损失。 优点和缺点，应仔细权衡考虑这种方法，开发人员。  
  
## <a name="exposing-a-single-idispatch-interface"></a>公开一个 IDispatch 接口  
 可以通过从两个或多个专用化的派生来公开单个对象上的多个双重接口`IDispatchImpl`。 但是，如果你允许客户端查询`IDispatch`接口，您将需要使用[COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2)宏 (或[COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid))) 来指定要用于哪个基类实现`IDispatch`。  
  
 [!code-cpp[NVC_ATL_COM#23](../atl/codesnippet/cpp/multiple-dual-interfaces_1.h)]  
  
 因为只有一个`IDispatch`接口公开，只能访问通过您的对象的客户端`IDispatch`接口将无法再访问方法或任何其他接口中的属性。  
  
## <a name="combining-multiple-dual-interfaces-into-a-single-implementation-of-idispatch"></a>将多个双重接口组合成 IDispatch 的单一实现  
 ATL 不提供任何支持将多个双重接口组合成单个实现的`IDispatch`。 但是，有几个已知的方法手动合并接口，例如，创建一个包含单独的并集的模板化类的方法`IDispatch`接口，创建一个新对象来执行`QueryInterface`函数，或使用要创建的嵌套对象的类型信息基于实现`IDispatch`接口。  
  
 这些方法具有与潜在的命名空间冲突、 代码复杂性和可维护性问题。 建议不要创建多个双重接口。  
  
## <a name="see-also"></a>请参阅  
 [双重接口和 ATL](../atl/dual-interfaces-and-atl.md)

