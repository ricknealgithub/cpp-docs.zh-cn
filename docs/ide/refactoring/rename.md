---
title: 重命名 | Microsoft Docs
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: 64b42a88-3bd9-4399-8b96-75bceffc353b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7a064527f6afcbf91be3fb4e51180be647c1f506
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33339808"
---
# <a name="rename"></a>重命名
功能：重命名代码符号的标识符，例如字段、本地变量、方法、命名空间、属性和类型。

时机：想要安全地进行重命名（无需查找所有实例）并复制/粘贴新名称。  

原因：复制和粘贴整个项目的新名称可能会导致错误。  此重构工具将准确地执行重命名操作。

方法：

1. 突出显示要重命名的项，或将文本光标置于其中：

   ![突出显示的代码](images/rename_highlight.png)

1. 接下来，执行以下操作之一：
   * **键盘**
     * 按“Ctrl+R”，然后按“Ctrl+R”。  （请注意，键盘快捷方式可能因所选的配置文件而有所不同。）
   * **鼠标**
     * 选择“编辑 > 重构 > 重命名”。
     * 右键单击代码并选择“重命名”。

1. 在弹出的“重命名”窗口中，输入所选项的新名称，并单击“预览”按钮。  如果需要扩大或缩小重命名的范围，请更改“搜索范围”。

   ![“重命名”对话框](images/rename_dialog.png)

   > [!TIP]
   > 可以通过检查“如果确认了所有引用，则跳过预览更改”来跳过预览。

1. 当出现“预览更改 - 重命名”窗口时，请确保正确进行所请求的更改。  使用窗口上半部分的复选框，启用或禁用任何项的重命名。

   ![重命名预览](images/rename_preview.png)

1. 当一切都正常时，单击“应用”按钮，项将在源代码中重命名。
