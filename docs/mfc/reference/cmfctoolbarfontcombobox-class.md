---
title: CMFCToolBarFontComboBox 类 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::GetFontDesc
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::SetFont
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarFontComboBox [MFC], CMFCToolBarFontComboBox
- CMFCToolBarFontComboBox [MFC], GetFontDesc
- CMFCToolBarFontComboBox [MFC], SetFont
ms.assetid: 25f8e08c-aadd-4cb5-9581-a99d49d444b1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2625316aa731e658d9d45e495809d2402a3cb4c5
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/05/2018
ms.locfileid: "37849745"
---
# <a name="cmfctoolbarfontcombobox-class"></a>CMFCToolBarFontComboBox 类
包含使用户能够从系统字体的列表中选择一种字体组合框控件的工具栏按钮。  
  
## <a name="syntax"></a>语法  
  
```  
class CMFCToolBarFontComboBox : public CMFCToolBarComboBoxButton  
```  
  
## <a name="members"></a>成员  
  
### <a name="protected-constructors"></a>受保护的构造函数  
  
|名称|描述|  
|----------|-----------------|  
|[CMFCToolBarFontComboBox::CMFCToolBarFontComboBox](#cmfctoolbarfontcombobox)|构造 `CMFCToolBarFontComboBox` 对象。|  
  
### <a name="public-methods"></a>公共方法  
  
|名称|描述|  
|----------|-----------------|  
|[CMFCToolBarFontComboBox::GetFontDesc](#getfontdesc)|返回一个指向`CMFCFontInfo`组合框中指定索引的对象。|  
|[CMFCToolBarFontComboBox::SetFont](#setfont)|根据任何一个字体组合框中选择一种字体，字体的名称或前缀和字符的字体集。|  
  
### <a name="data-members"></a>数据成员  
 [CMFCToolBarFontComboBox::m_nFontHeight](#m_nfontheight)  
 字体组合框中字符的高度。  
  
## <a name="remarks"></a>备注  
 若要将字体组合框按钮添加到工具栏，请按照下列步骤：  
  
1.  在父级工具栏资源中保留该按钮的虚拟资源 ID。  
  
2.  构造`CMFCToolBarFontComboBox`对象。  
  
3.  在处理 AFX_WM_RESETTOOLBAR 消息的消息处理程序，原始按钮将替换为新组合框按钮通过使用[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)。  
  
4.  同步选择组合框中使用文档中字体使用的字体[CMFCToolBarFontComboBox::SetFont](#setfont)方法。  
  
 若要同步使用字体组合框中选定文档的字体，请使用[CMFCToolBarFontComboBox::GetFontDesc](#getfontdesc)方法以检索所选字体属性并使用这些属性创建[CFont 类](../../mfc/reference/cfont-class.md)对象。  
  
 字体组合框按钮调用 Win32 函数[EnumFontFamiliesEx](http://msdn.microsoft.com/library/windows/desktop/dd162620)来确定可用于系统的屏幕和打印机字体。  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)  
  
 [CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md)  
  
## <a name="requirements"></a>要求  
 **标头：** afxtoolbarfontcombobox.h  
  
##  <a name="cmfctoolbarfontcombobox"></a>  CMFCToolBarFontComboBox::CMFCToolBarFontComboBox  
 构造[CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md)对象。  
  
```  
public:  
CMFCToolBarFontComboBox(
    UINT uiID,  
    int iImage,  
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,  
    BYTE nCharSet = DEFAULT_CHARSET,  
    DWORD dwStyle = CBS_DROPDOWN,  
    int iWidth = 0,  
    BYTE nPitchAndFamily = DEFAULT_PITCH);

 
protected:  
CMFCToolBarFontComboBox(
    CObList* pLstFontsExternal,  
    int nFontType,  
    BYTE nCharSet,  
    BYTE nPitchAndFamily);  
  
CMFCToolBarFontComboBox();
```  
  
### <a name="parameters"></a>参数  
 [in]*uiID*  
 组合框命令 ID。  
  
 [in]*iImage*  
 工具栏图像的从零开始的索引。 映像位于[CMFCToolBarImages 类](../../mfc/reference/cmfctoolbarimages-class.md)对象的[CMFCToolBar 类](../../mfc/reference/cmfctoolbar-class.md)类维护。  
  
 [in]*nFontType*  
 字体组合框包含的类型。 此参数可以是以下值的组合 (布尔 OR):  
  
 是 DEVICE_FONTTYPE  
  
 RASTER_FONTTYPE  
  
 TRUETYPE_FONTTYPE  
  
 [in]*nCharSet*  
 如果设置为 DEFAULT_CHARSET，组合框包含所有唯一命名的字体中字符的所有集。 （如果有两个具有相同名称的字体，组合框包含其中一个。）如果设置为有效的字符设置值，组合框包含仅在指定的字符集的字体。 请参阅[LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)有关可能的字符的列表设置。  
  
 [in]*dwStyle*  
 组合框的样式。 (请参阅[组合框样式](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles))  
  
 [in]*iWidth*  
 以像素为单位在编辑控件的宽度。  
  
 [in]*nPitchAndFamily*  
 如果设置为 DEFAULT_PITCH，组合框包含而不考虑间距字体。 如果设置为 FIXED_PITCH 或 VARIABLE_PITCH，组合框包含仅与该间距类型的字体。 当前不支持基于字体系列的筛选。  
  
 [out]*pLstFontsExternal*  
 指向[CObList 类](../../mfc/reference/coblist-class.md)对象，它存储的可用字体。  
  
### <a name="remarks"></a>备注  
 通常情况下，`CMFCToolBarFontComboBox`对象在单个共享存储的可用字体列表`CObList`对象。 如果使用构造函数的第二个重载并提供指向的有效指针*pLstFontsExternal*，则该`CMFCToolBarFontComboBox`对象将改为填充`CObList`的*pLstFontsExternal*指向以，可用的字体。  
  
### <a name="example"></a>示例  
 下面的示例演示如何构造`CMFCToolBarFontComboBox`对象。 此代码片段属于 [Word Pad 示例](../../visual-cpp-samples.md)。  
  
 [!code-cpp[NVC_MFC_WordPad#7](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontcombobox-class_1.cpp)]  
  
##  <a name="getfontdesc"></a>  CMFCToolBarFontComboBox::GetFontDesc  
 返回一个指向`CMFCFontInfo`组合框中指定索引的对象。  
  
```  
const CMFCFontInfo* GetFontDesc(int iIndex=-1) const;  
```  
  
### <a name="parameters"></a>参数  
 [in]*iIndex*  
 指定组合框项的从零开始索引。  
  
### <a name="return-value"></a>返回值  
 一个指向`CMFCFontInfo`对象。 如果*iIndex*不指定一个有效的项的索引，返回值为 NULL。  
  
##  <a name="m_nfontheight"></a>  CMFCToolBarFontComboBox::m_nFontHeight  
 指定高度，以像素为单位，字体组合框中，如果该组合框具有所有者绘制样式中的字符。  
  
```  
static int m_nFontHeight  
```  
  
### <a name="remarks"></a>备注  
 如果`m_nFontHeight`变量为 0，则根据在组合框的默认字体高度自动计算。 高度提供包括到基线以上的字符的上升和基线下方的字符的下移量。  
  
##  <a name="setfont"></a>  CMFCToolBarFontComboBox::SetFont  
 根据字体名称和字符的字体组合框中的字体设置的选择是在参数中指定的。  
  
```  
BOOL SetFont(
    LPCTSTR lpszName,  
    BYTE nCharSet=DEFAULT_CHARSET,  
    BOOL bExact=FALSE);
```  
  
### <a name="parameters"></a>参数  
 [in]*lpszName*  
 指定的字体名称或前缀。  
  
 [in]*nCharSet*  
 指定的字符集。  
  
 [in]*bExact*  
 指定是否*lpszName*包含字体名称或字体前缀。  
  
### <a name="return-value"></a>返回值  
 如果成功，则选择字体，则非零值否则为 0。  
  
### <a name="remarks"></a>备注  
 如果*bExact*为 TRUE 时，此方法选择指定为该名称完全匹配的字体*lpszName*。 如果*bExact*为 FALSE 时，此方法选择以指定文本开头的字体*lpszName* ，并使用指定为字符集*nCharSet*。 如果*nCharSet*设置的字符集将到 DEFAULT_CHARSET，是忽略，并且只*lpszName*将用于选择一种字体。  
  
## <a name="see-also"></a>请参阅  
 [层次结构图表](../../mfc/hierarchy-chart.md)   
 [类](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar 类](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton 类](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBarComboBoxButton 类](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [CMFCFontInfo 类](../../mfc/reference/cmfcfontinfo-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [演练：将控件置于工具栏上](../../mfc/walkthrough-putting-controls-on-toolbars.md)



