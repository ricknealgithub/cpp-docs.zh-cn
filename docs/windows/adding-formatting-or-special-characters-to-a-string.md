---
title: 为字符串添加格式设置或特殊字符 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- special characters, adding to strings
- ASCII characters, adding to strings
- strings [C++], formatting
- strings [C++], special characters
ms.assetid: c40f394a-8b2c-4896-ab30-6922863ddbb5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 429ba8d836579bd3bc1d1dd8844494bf9cd17a7a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2018
ms.locfileid: "33864592"
---
# <a name="adding-formatting-or-special-characters-to-a-string"></a>为字符串添加格式设置或特殊字符
### <a name="to-add-formatting-or-special-characters-to-a-string"></a>若要添加为字符串的格式设置或特殊字符  
  
1.  通过双击图标中的将其打开字符串表[资源视图](../windows/resource-view-window.md)。  
  
    > [!NOTE]
    >  如果你的项目尚未包含 .rc 文件，请参阅 [创建新的资源脚本文件](../windows/how-to-create-a-resource-script-file.md)。  
  
2.  选择你想要修改的字符串。  
  
3.  在[属性窗口](/visualstudio/ide/reference/properties-window)，添加任何标准的转义序列中的文本到下列**标题**框中，然后按**ENTER**。  
  
    |若要获取这|键入这|  
    |-----------------|---------------|  
    |换行|\n|  
    |回车|\r|  
    |Tab|\t|  
    |反斜杠 (\\)|\\\|  
    |ASCII 字符|\ddd （八进制表示法）|  
    |警报 （响铃）|\a|  
  
> [!NOTE]
>  字符串编辑器不支持转义 ASCI 字符的完整集。 你可以只使用上面所列。  
  
 有关将资源添加到托管项目 （那些针对公共语言运行时） 的信息，请参阅[桌面应用中的资源](/dotnet/framework/resources/index)中 *.NET Framework 开发指南。* 。有关手动将资源文件添加到托管项目、访问资源、显示静态资源和将资源字符串分配给属性的信息，请参阅 [演练：本地化 Windows 窗体](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5) 和 [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6)。  
  
 **要求**  
  
 Win32  
  
## <a name="see-also"></a>请参阅  
 [字符串编辑器](../windows/string-editor.md)   

