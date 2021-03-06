---
title: WINDOWPOS 结构 1 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- WINDOWPOS
dev_langs:
- C++
helpviewer_keywords:
- WINDOWPOS structure [MFC]
ms.assetid: a4ea7cd9-c4c2-4480-9c55-cbbff72195e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db51e8f9924d69406989b3a9ac12b45f0e55e870
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885957"
---
# <a name="windowpos-structure1"></a>WINDOWPOS 结构 1
`WINDOWPOS`结构包含有关大小和窗口位置信息。  
  
## <a name="syntax"></a>语法  
  
```  
typedef struct tagWINDOWPOS { /* wp */  
    HWND hwnd;  
    HWND hwndInsertAfter;  
    int x;  
    int y;  
    int cx;  
    int cy;  
    UINT flags;  
} WINDOWPOS;  
```  
  
#### <a name="parameters"></a>参数  
 *hwnd*  
 标识窗口。  
  
 *hwndInsertAfter*  
 标识其后放置此窗口的窗口。  
  
 *x*  
 指定窗口的左边缘的位置。  
  
 *y*  
 指定窗口的右边缘的位置。  
  
 *cx*  
 指定的窗口宽度，以像素为单位。  
  
 *cy*  
 以像素为单位指定窗口高度。  
  
 *flags*  
 指定窗口定位选项。 此成员可以是下列值之一：  
  
- SWP_DRAWFRAME 绘制的窗口周围帧 （在窗口类说明中定义）。 在窗口接收 WM_NCCALCSIZE 消息。  
  
- SWP_FRAMECHANGED 发送 WM_NCCALCSIZE 消息到窗口中，即使不会更改窗口的大小。 如果未指定此标志，该窗口的大小正在更改时才发送 WM_NCCALCSIZE。  
  
- SWP_HIDEWINDOW 隐藏窗口。  
  
- SWP_NOACTIVATE 不会激活窗口。  
  
- SWP_NOCOPYBITS 放弃的工作区的全部内容。 如果未指定此标志，客户端区域中的有效内容保存并复制到工作区后的窗口大小或重新定位。  
  
- SWP_NOMOVE 保留当前的位置 (将忽略`x`和`y`成员)。  
  
- SWP_NOOWNERZORDER 不会更改在 Z 顺序中的所有者窗口的位置。  
  
- SWP_NOSIZE 保留当前大小 (将忽略`cx`和`cy`成员)。  
  
- SWP_NOREDRAW 不重绘更改。  
  
- SWP_NOREPOSITION SWP_NOOWNERZORDER 与相同。  
  
- SWP_NOSENDCHANGING 会阻止接收 WM_WINDOWPOSCHANGING 消息窗口。  
  
- SWP_NOZORDER 保留当前的订购 (忽略`hwndInsertAfter`成员)。  
  
- SWP_SHOWWINDOW 显示窗口。  
  
## <a name="requirements"></a>要求  
 **标头：** winuser.h  
  
## <a name="see-also"></a>请参阅  
 [结构、 样式、 回调和消息映射](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging)

