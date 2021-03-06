---
title: CD2DSolidColorBrush 类 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DSolidColorBrush
- AFXRENDERTARGET/CD2DSolidColorBrush
- AFXRENDERTARGET/CD2DSolidColorBrush::CD2DSolidColorBrush
- AFXRENDERTARGET/CD2DSolidColorBrush::Attach
- AFXRENDERTARGET/CD2DSolidColorBrush::Create
- AFXRENDERTARGET/CD2DSolidColorBrush::Destroy
- AFXRENDERTARGET/CD2DSolidColorBrush::Detach
- AFXRENDERTARGET/CD2DSolidColorBrush::Get
- AFXRENDERTARGET/CD2DSolidColorBrush::GetColor
- AFXRENDERTARGET/CD2DSolidColorBrush::SetColor
- AFXRENDERTARGET/CD2DSolidColorBrush::m_colorSolid
- AFXRENDERTARGET/CD2DSolidColorBrush::m_pSolidColorBrush
dev_langs:
- C++
helpviewer_keywords:
- CD2DSolidColorBrush [MFC], CD2DSolidColorBrush
- CD2DSolidColorBrush [MFC], Attach
- CD2DSolidColorBrush [MFC], Create
- CD2DSolidColorBrush [MFC], Destroy
- CD2DSolidColorBrush [MFC], Detach
- CD2DSolidColorBrush [MFC], Get
- CD2DSolidColorBrush [MFC], GetColor
- CD2DSolidColorBrush [MFC], SetColor
- CD2DSolidColorBrush [MFC], m_colorSolid
- CD2DSolidColorBrush [MFC], m_pSolidColorBrush
ms.assetid: d4506637-acce-4f74-8a9b-f0a45571a735
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9cf3f78624761b364bf192876cb8368c73507e86
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951570"
---
# <a name="cd2dsolidcolorbrush-class"></a>CD2DSolidColorBrush 类
ID2D1SolidColorBrush 包装器。  
  
## <a name="syntax"></a>语法  
  
```  
class CD2DSolidColorBrush : public CD2DBrush;  
```  
  
## <a name="members"></a>成员  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|描述|  
|----------|-----------------|  
|[CD2DSolidColorBrush::CD2DSolidColorBrush](#cd2dsolidcolorbrush)|已重载。 构造 CD2DSolidColorBrush 对象。|  
|[CD2DSolidColorBrush:: ~ CD2DSolidColorBrush](#cd2dsolidcolorbrush__~cd2dsolidcolorbrush)|析构函数。 当 D2D 实心画笔对象被销毁时调用。|  
  
### <a name="public-methods"></a>公共方法  
  
|名称|描述|  
|----------|-----------------|  
|[CD2DSolidColorBrush::Attach](#attach)|附加现有的资源的对象的接口|  
|[CD2DSolidColorBrush::Create](#create)|创建 CD2DSolidColorBrush。 (重写[CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create)。)|  
|[CD2DSolidColorBrush::Destroy](#destroy)|销毁 CD2DSolidColorBrush 对象。 (重写[CD2DBrush::Destroy](../../mfc/reference/cd2dbrush-class.md#destroy)。)|  
|[CD2DSolidColorBrush::Detach](#detach)|分离资源接口从该对象|  
|[CD2DSolidColorBrush::Get](#get)|返回 ID2D1SolidColorBrush 接口|  
|[CD2DSolidColorBrush::GetColor](#getcolor)|检索纯色画笔的颜色|  
|[CD2DSolidColorBrush::SetColor](#setcolor)|指定此纯色画笔的颜色|  
  
### <a name="public-operators"></a>公共运算符  
  
|名称|描述|  
|----------|-----------------|  
|[CD2DSolidColorBrush::operator ID2D1SolidColorBrush *](#operator_id2d1solidcolorbrush_star)|返回 ID2D1SolidColorBrush 接口|  
  
### <a name="protected-data-members"></a>受保护的数据成员  
  
|name|描述|  
|----------|-----------------|  
|[CD2DSolidColorBrush::m_colorSolid](#m_colorsolid)|画笔的纯色。|  
|[CD2DSolidColorBrush::m_pSolidColorBrush](#m_psolidcolorbrush)|将存储指向 ID2D1SolidColorBrush 对象的指针。|  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 [CD2DSolidColorBrush](../../mfc/reference/cd2dsolidcolorbrush-class.md)  
  
## <a name="requirements"></a>要求  
 **标头：** afxrendertarget.h  
  
##  <a name="_dtorcd2dsolidcolorbrush"></a>  CD2DSolidColorBrush:: ~ CD2DSolidColorBrush  
 析构函数。 当 D2D 实心画笔对象被销毁时调用。  
  
```  
virtual ~CD2DSolidColorBrush();
```  
  
##  <a name="attach"></a>  CD2DSolidColorBrush::Attach  
 附加现有的资源的对象的接口  
  
```  
void Attach(ID2D1SolidColorBrush* pResource);
```  
  
### <a name="parameters"></a>参数  
 *pResource*  
 现有资源接口。 不能为 NULL  
  
##  <a name="cd2dsolidcolorbrush"></a>  CD2DSolidColorBrush::CD2DSolidColorBrush  
 构造 CD2DSolidColorBrush 对象。  
  
```  
CD2DSolidColorBrush(
    CRenderTarget* pParentTarget,  
    D2D1_COLOR_F color,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);

 
CD2DSolidColorBrush(
    CRenderTarget* pParentTarget,  
    COLORREF color,  
    int nAlpha = 255,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>参数  
 *pParentTarget*  
 指向该呈现器目标的指针。  
  
 *颜色*  
 画笔的颜色红、 绿、 蓝方和 alpha 值。  
  
 *pBrushProperties*  
 指向不透明度和画笔的转换的指针。  
  
 *bAutoDestroy*  
 指示该对象将销毁所有者 (pParentTarget)。  
  
 *nAlpha*  
 画笔的颜色的不透明度。  
  
##  <a name="create"></a>  CD2DSolidColorBrush::Create  
 创建 CD2DSolidColorBrush。  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>参数  
 *pRenderTarget*  
 指向该呈现器目标的指针。  
  
### <a name="return-value"></a>返回值  
 如果该方法成功，则返回，则为 S_OK。 否则，它返回一个 HRESULT 错误代码。  
  
##  <a name="destroy"></a>  CD2DSolidColorBrush::Destroy  
 销毁 CD2DSolidColorBrush 对象。  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>  CD2DSolidColorBrush::Detach  
 分离资源接口从该对象  
  
```  
ID2D1SolidColorBrush* Detach();
```  
  
### <a name="return-value"></a>返回值  
 指向分离的资源接口指针。  
  
##  <a name="get"></a>  CD2DSolidColorBrush::Get  
 返回 ID2D1SolidColorBrush 接口  
  
```  
ID2D1SolidColorBrush* Get();
```  
  
### <a name="return-value"></a>返回值  
 指向 ID2D1SolidColorBrush 接口或如果尚未初始化对象的 NULL 指针。  
  
##  <a name="getcolor"></a>  CD2DSolidColorBrush::GetColor  
 检索纯色画笔的颜色  
  
```  
D2D1_COLOR_F GetColor() const;  
```  
  
### <a name="return-value"></a>返回值  
 此纯色画笔的颜色  
  
##  <a name="m_colorsolid"></a>  CD2DSolidColorBrush::m_colorSolid  
 画笔的纯色。  
  
```  
D2D1_COLOR_F m_colorSolid;  
```  
  
##  <a name="m_psolidcolorbrush"></a>  CD2DSolidColorBrush::m_pSolidColorBrush  
 将存储指向 ID2D1SolidColorBrush 对象的指针。  
  
```  
ID2D1SolidColorBrush* m_pSolidColorBrush;  
```  
  
##  <a name="operator_id2d1solidcolorbrush_star"></a>  CD2DSolidColorBrush::operator ID2D1SolidColorBrush *  
 返回 ID2D1SolidColorBrush 接口  
  
```  
operator ID2D1SolidColorBrush*();
```   
  
### <a name="return-value"></a>返回值  
 指向 ID2D1SolidColorBrush 接口或如果尚未初始化对象的 NULL 指针。  
  
##  <a name="setcolor"></a>  CD2DSolidColorBrush::SetColor  
 指定此纯色画笔的颜色  
  
```  
void SetColor(D2D1_COLOR_F color);
```  
  
### <a name="parameters"></a>参数  
 *颜色*  
 此纯色画笔的颜色  
  
## <a name="see-also"></a>请参阅  
 [类](../../mfc/reference/mfc-classes.md)
