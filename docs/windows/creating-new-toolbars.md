---
title: 创建新工具栏 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.toolbar
dev_langs:
- C++
helpviewer_keywords:
- toolbars [C++], creating
- Toolbar editor, creating new toolbars
- Insert Resource
ms.assetid: 1b28264b-0718-4df8-9f65-979805d2efef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b61d1c530272ecaba2cbeb36c21e158bd5a6b401
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2018
ms.locfileid: "33888075"
---
# <a name="creating-new-toolbars"></a>创建新工具栏
### <a name="to-create-a-new-toolbar"></a>若要创建新工具栏  
  
1.  在**资源**查看，右键单击.rc 文件，然后选择**添加资源**从快捷菜单。 (如果你在.rc 文件中有现有的工具栏上，只需可以右键单击**工具栏**文件夹，然后选择**插入工具栏**从快捷菜单。)  
  
     **注意：** 如果你的项目尚未包含 .rc 文件，请参阅 [创建新资源脚本文件](../windows/how-to-create-a-resource-script-file.md)。  
  
2.  在**添加资源**对话框中，选择**工具栏**中**资源类型**列表，然后单击**新建**。  
  
     如果旁边出现一个加号 （+）**工具栏**资源类型，这意味着工具栏模板都可用。 单击加号以便展开模板列表中的，选择一个模板，然后单击**新建**。  
  
     \- 或 -  
  
3.  [将现有的位图转换为工具栏](../windows/converting-bitmaps-to-toolbars.md)。  
  
 有关将资源添加到托管项目的信息，请参阅[桌面应用中的资源](/dotnet/framework/resources/index)中 *.NET Framework 开发指南。* 有关手动将资源文件添加到托管项目、 访问资源、 显示静态资源和将资源字符串分配给属性的信息，请参阅[对于桌面应用程序创建资源文件](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)。 全球化和本地化的资源在托管应用中的信息，请参阅[Globalizing 和本地化的.NET Framework 应用程序](/dotnet/standard/globalization-localization/index)。  
  
 要求  
  
 MFC 或 ATL  
  
## <a name="see-also"></a>请参阅  
 [工具栏编辑器](../windows/toolbar-editor.md)

