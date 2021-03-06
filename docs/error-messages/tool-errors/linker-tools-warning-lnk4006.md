---
title: 链接器工具警告 LNK4006 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4006
dev_langs:
- C++
helpviewer_keywords:
- LNK4006
ms.assetid: 3a637d17-1676-4ea6-bd8b-290137d28d3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 261d5dcc27c44291ddc6de4a6440cde040a84ed7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302550"
---
# <a name="linker-tools-warning-lnk4006"></a>链接器工具警告 LNK4006
中的对象; 已定义符号忽略的第二个定义  
  
 以修饰形式显示的给定 `symbol` 被多次定义。 当遇到此警告时，`symbol`将添加两次，但将使用只有其第一个窗体。  
  
 如果你尝试将两个导入 libs 合并为一个，你可以收到此警告。  
  
 如果你正在重新生成的 C 运行时库，你可以忽略此消息。  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>使用以下可能的解决方案进行修复  
  
1.  给定`symbol`可能封装的函数，通过使用编译创建[/Gy](../../build/reference/gy-enable-function-level-linking.md)。 此符号已包含在多个文件，但各编译间已改变。 重新编译包含的所有文件`symbol`。  
  
2.  给定`symbol`可能以不同方式定义不同的库中的两个成员对象中。  
  
3.  某个绝对符号可能已定义了两次，每个定义中的不同值。  
  
4.  如果在组合库时收到错误消息，则`symbol`添加到库中已存在。