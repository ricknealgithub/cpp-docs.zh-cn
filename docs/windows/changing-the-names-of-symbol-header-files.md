---
title: 更改符号头文件的名称 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.changing.header
dev_langs:
- C++
helpviewer_keywords:
- resource files, multiple
- Resource Includes dialog box
- symbol header files, changing names
- symbol header files
- header files, changing names
- names [C++], symbol header files
- symbols, symbol header files
- Resource.h
ms.assetid: b948284a-7899-402e-ab12-9f2c8480ca9d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 953ac59958748bd58fa7e9027c595bf7905e5f27
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2018
ms.locfileid: "33864224"
---
# <a name="changing-the-names-of-symbol-header-files"></a>更改符号头文件的名称
通常情况下所有符号定义都保存在 Resource.h 中。 但是，你可能需要更改此包含文件名，以便可以在同一个目录下使用多个资源文件。  
  
### <a name="to-change-the-name-of-the-resource-symbol-header-file"></a>更改资源符号头文件的名称  
  
1.  在[资源视图](../windows/resource-view-window.md)，右键单击.rc 文件，然后选择[资源包括](../windows/resource-includes-dialog-box.md)从快捷菜单。  
  
    > [!NOTE]
    >  如果你的项目尚未包含 .rc 文件，请参阅 [创建新的资源脚本文件](../windows/how-to-create-a-resource-script-file.md)。  
  
2.  在**符号头文件**框中，键入包含文件的新名称。  
  
 有关将资源添加到托管项目的信息，请参阅[桌面应用中的资源](/dotnet/framework/resources/index)中 *.NET Framework 开发指南。*  
  
 要求  
  
 Win32  
  
## <a name="see-also"></a>请参阅  
 [查看资源符号](../windows/viewing-resource-symbols.md)   
 [预定义的符号 ID](../windows/predefined-symbol-ids.md)