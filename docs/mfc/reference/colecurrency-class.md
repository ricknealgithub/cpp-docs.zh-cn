---
title: COleCurrency 类 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleCurrency
- AFXDISP/COleCurrency
- AFXDISP/COleCurrency::COleCurrency
- AFXDISP/COleCurrency::Format
- AFXDISP/COleCurrency::GetStatus
- AFXDISP/COleCurrency::ParseCurrency
- AFXDISP/COleCurrency::SetCurrency
- AFXDISP/COleCurrency::SetStatus
- AFXDISP/COleCurrency::m_cur
- AFXDISP/COleCurrency::m_status
dev_langs:
- C++
helpviewer_keywords:
- COleCurrency [MFC], COleCurrency
- COleCurrency [MFC], Format
- COleCurrency [MFC], GetStatus
- COleCurrency [MFC], ParseCurrency
- COleCurrency [MFC], SetCurrency
- COleCurrency [MFC], SetStatus
- COleCurrency [MFC], m_cur
- COleCurrency [MFC], m_status
ms.assetid: 3a36e345-303f-46fb-a57c-858274378a8d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 20e24c5286afbe20b1f5b71a67b0d10385f80874
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2018
ms.locfileid: "39208791"
---
# <a name="colecurrency-class"></a>COleCurrency 类
封装 OLE 自动化的 `CURRENCY` 数据类型。  
  
## <a name="syntax"></a>语法  
  
```  
class COleCurrency  
```  
  
## <a name="members"></a>成员  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|描述|  
|----------|-----------------|  
|[COleCurrency::COleCurrency](#colecurrency)|构造 `COleCurrency` 对象。|  
  
### <a name="public-methods"></a>公共方法  
  
|名称|描述|  
|----------|-----------------|  
|[COleCurrency::Format](#format)|生成带格式的字符串表示形式的`COleCurrency`对象。|  
|[COleCurrency::GetStatus](#getstatus)|获取此状态 （有效期）`COleCurrency`对象。|  
|[COleCurrency::ParseCurrency](#parsecurrency)|从字符串中读取的货币值，并设置的值`COleCurrency`。|  
|[COleCurrency::SetCurrency](#setcurrency)|设置此值`COleCurrency`对象。|  
|[COleCurrency::SetStatus](#setstatus)|设置此状态 （有效期）`COleCurrency`对象。|  
  
### <a name="public-operators"></a>公共运算符  
  
|名称|描述|  
|----------|-----------------|  
|[operator =](#operator_eq)|副本`COleCurrency`值。|  
|[运算符 +、-](#operator_plus_minus)|添加、 相减，并且更改的符号`COleCurrency`值。|  
|[运算符 + =、 =](#operator_plus_minus_eq)|将添加并减去`COleCurrency`从此值`COleCurrency`对象。|  
|[运算符 * /](#operator_star)|刻度`COleCurrency`的整数值的值。|  
|[运算符 * =、 / =](#operator_star_div_eq)|缩放此`COleCurrency`的整数值的值。|  
|[运算符 <<](#operator_stream)|输出`COleCurrency`值设为`CArchive`或`CDumpContext`。|  
|[运算符 >>](#operator_stream)|输入`COleCurrency`对象从`CArchive`。|  
|[运算符货币](#operator_currency)|将转换`COleCurrency`为货币值。|  
|[运算符 = =、 <、 < =，等等。](#colecurrency_relational_operators)|比较两个`COleCurrency`值。|  
  
### <a name="public-data-members"></a>公共数据成员  
  
|名称|描述|  
|----------|-----------------|  
|[COleCurrency::m_cur](#m_cur)|包含此基础货币`COleCurrency`对象。|  
|[COleCurrency::m_status](#m_status)|包含此状态`COleCurrency`对象。|  
  
## <a name="remarks"></a>备注  
 `COleCurrency` 没有基类。  
  
 货币作为一个 8 字节，按 10,000 缩放的 2 的补数的整数值。 这产生了一个定点数数字，小数点左侧有 15 位数，右侧有 4 位数。 货币数据类型是非常有用的计算涉及到货币或任何定点计算精确度至关重要。 它是之一的可能类型`VARIANT`的 OLE 自动化的数据类型。  
  
 `COleCurrency` 此外将实现此定点类型一些基本算术运算。 已选择支持的操作以控制定点计算过程就会进行舍入误差。  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 `COleCurrency`  
  
## <a name="requirements"></a>要求  
 **标头：** afxdisp.h  
  
##  <a name="colecurrency"></a>  COleCurrency::COleCurrency  
 构造 `COleCurrency` 对象。  
  
```  
COleCurrency();  
COleCurrency(CURRENCY cySrc);  
  COleCurrency(const COleCurrency& curSrc);  
COleCurrency(const VARIANT& varSrc);

 
COleCurrency(
    long nUnits,  
    long nFractionalUnits);
```  
  
### <a name="parameters"></a>参数  
 *cySrc*  
 要复制到新的货币值`COleCurrency`对象。  
  
 *curSrc*  
 将现有`COleCurrency`对象复制到新`COleCurrency`对象。  
  
 *varSrc*  
 将现有`VARIANT`数据结构 (可能`COleVariant`对象) 转换为货币值 (VT_CY) 并复制到新`COleCurrency`对象。  
  
 *nUnits*， *nFractionalUnits*  
 指示要复制到新的单位和小数部分 （在 1/万为单位） 的值的`COleCurrency`对象。  
  
### <a name="remarks"></a>备注  
 所有这些构造函数创建新`COleCurrency`对象初始化为指定的值。 遵循这些构造函数的简要说明。 除非另有说明，新的状态`COleCurrency`项将被设置为有效。  
  
- COleCurrency() 构造`COleCurrency`对象初始化为 0 （零）。  
  
- COleCurrency (`cySrc`) 构造`COleCurrency`对象从[货币](http://msdn.microsoft.com/5e81273c-7289-45c7-93c0-32c1553f708e)值。  
  
- COleCurrency (`curSrc`) 构造`COleCurrency`从现有对象`COleCurrency`对象。 新对象具有与源对象相同的状态。  
  
- COleCurrency (`varSrc`) 构造`COleCurrency`对象。 尝试将转换[VARIANT](http://msdn.microsoft.com/e305240e-9e11-4006-98cc-26f4932d2118)结构或`COleVariant`为货币 (VT_CY) 值的对象。 如果此转换成功，转换后的值复制到新`COleCurrency`对象。 如果还没有，则`COleCurrency`对象设置为零 (0)，并且其状态设置为无效。  
  
- `COleCurrency(`nUnits`, `nFractionalUnits`) Constructs a `COleCurrency 中指定的数字部分对象。 如果值的小数部分的绝对值大于 10000，将的单位进行适当的调整。 请注意，由指定的单位和小数部分有符号长值。  
  
 有关详细信息，请参阅[货币](http://msdn.microsoft.com/5e81273c-7289-45c7-93c0-32c1553f708e)并[变体](http://msdn.microsoft.com/e305240e-9e11-4006-98cc-26f4932d2118)Windows SDK 中的条目。  
  
### <a name="example"></a>示例  
 以下示例显示的零参数和两个参数构造函数的效果：  
  
 [!code-cpp[NVC_MFCOleContainer#10](../../mfc/codesnippet/cpp/colecurrency-class_1.cpp)]  
  
##  <a name="format"></a>  COleCurrency::Format  
 调用此成员函数以创建货币值的格式化表示形式。  
  
```  
CString Format(DWORD  dwFlags = 0, LCID  lcid = LANG_USER_DEFAULT) const; 
```  
  
### <a name="parameters"></a>参数  
 *dwFlags*  
 指示区域设置的标志。 仅以下标志是与货币相关：  
  
- LOCALE_NOUSEROVERRIDE 使用系统默认区域设置，而不是自定义用户设置。  
  
 *lcid*  
 指示要使用用于转换的区域设置 ID。  
  
### <a name="return-value"></a>返回值  
 一个`CString`，其中包含格式的货币值。  
  
### <a name="remarks"></a>备注  
 它使用本地语言规范 （区域设置 Id） 值的格式。 中返回的值不包括货币符号。 如果此状态`COleCurrency`对象为 null，则返回值为空字符串。 如果状态为无效，由字符串资源 IDS_INVALID_CURRENCY 指定返回的字符串。  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_MFCOleContainer#11](../../mfc/codesnippet/cpp/colecurrency-class_2.cpp)]  
  
##  <a name="getstatus"></a>  COleCurrency::GetStatus  
 调用此成员函数以获取状态 （有效期） 的给定`COleCurrency`对象。  
  
```  
CurrencyStatus GetStatus() const;  
```  
  
### <a name="return-value"></a>返回值  
 返回此状态`COleCurrency`值。  
  
### <a name="remarks"></a>备注  
 由定义的返回值`CurrencyStatus`枚举中定义的类型`COleCurrency`类。  
  
```  
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };  
```  
  
 有关这些状态的值的简要说明，请参阅下面的列表：  
  
  - `COleCurrency::valid` 指示此`COleCurrency`对象是否有效。  
  
  - `COleCurrency::invalid` 指示此`COleCurrency`对象无效; 即，其值可能不正确。  
  
  - `COleCurrency::null` 指示此`COleCurrency`对象为 null，也即，已为此对象提供任何值。 （此为"null"数据库意义上的"无任何值，"，而不 c + + 为 NULL。）  
  
 状态`COleCurrency`对象是在以下情况下无效：  
  
-   如果其值设置从一个变体或`COleVariant`无法转换为货币值的值。  
  
-   如果此对象已溢出或下溢在过程中遇到算术赋值运算，例如`+=`或**\* =**。  
  
-   如果无效的值分配给此对象。  
  
-   如果已显式设置该对象的状态为无效的使用[SetStatus](#setstatus)。  
  
 有关可能会将状态设置为无效的请参阅以下成员函数的操作的详细信息：  
  
 - [COleCurrency](#colecurrency)  
  
 - [operator =](#operator_eq)  
  
 - [运算符 +-](#operator_plus_minus)  
  
 - [operator + = 和 =](#operator_plus_minus_eq)  
  
 - [运算符 * /](#operator_star)  
  
 - [运算符 * = 和 / =](#operator_star_div_eq)  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_MFCOleContainer#12](../../mfc/codesnippet/cpp/colecurrency-class_3.cpp)]  
  
##  <a name="m_cur"></a>  COleCurrency::m_cur  
 基础[货币](http://msdn.microsoft.com/5e81273c-7289-45c7-93c0-32c1553f708e)此结构`COleCurrency`对象。  
  
### <a name="remarks"></a>备注  
  
> [!CAUTION]
>  更改中的值`CURRENCY`访问此函数返回的指针的结构将更改此设置的值`COleCurrency`对象。 它不会更改此状态`COleCurrency`对象。  
  
 有关详细信息，请参阅[货币](http://msdn.microsoft.com/5e81273c-7289-45c7-93c0-32c1553f708e)Windows SDK 中的条目。  
  
##  <a name="m_status"></a>  COleCurrency::m_status  
 此数据成员的类型是枚举的类型`CurrencyStatus`，其定义内`COleCurrency`类。  
  
```  
enum CurrencyStatus{  
    valid = 0,  
    invalid = 1,  
    null = 2,  
};  
```  
  
### <a name="remarks"></a>备注  
有关这些状态的值的简要说明，请参阅下面的列表：  
  
 - `COleCurrency::valid` 指示此`COleCurrency`对象是否有效。  
      
 - `COleCurrency::invalid` 指示此`COleCurrency`对象无效; 即，其值可能不正确。  
      
 - `COleCurrency::null` 指示此`COleCurrency`对象为 null，也即，已为此对象提供任何值。 （此为"null"数据库意义上的"无任何值，"，而不 c + + 为 NULL。）  
  
状态`COleCurrency`对象是在以下情况下无效：  
  
 - 如果其值设置从一个变体或`COleVariant`无法转换为货币值的值。  
      
 - 如果此对象已溢出或下溢在过程中遇到算术赋值运算，例如`+=`或**\* =**。  
      
 - 如果无效的值分配给此对象。  
      
 - 如果已显式设置该对象的状态为无效的使用[SetStatus](#setstatus)。  
  
有关可能会将状态设置为无效的请参阅以下成员函数的操作的详细信息：  
  
 - [COleCurrency](#colecurrency)  
      
 - [operator =](#operator_eq)  
      
 - [运算符 +、-](#operator_plus_minus)  
      
 - [运算符 + =、 =](#operator_plus_minus_eq)  
      
 - [运算符 * /](#operator_star)  
      
 - [运算符 * =、 / =](#operator_star_div_eq)  
  
> [!CAUTION]
>  此数据成员是针对高级编程情况。 应使用的内联成员函数[GetStatus](#getstatus)并[SetStatus](#setstatus)。 请参阅`SetStatus`有关显式设置此数据成员的其他注意事项。  
  
##  <a name="operator_eq"></a>  COleCurrency::operator =  
 这些重载的赋值运算符将源货币值复制到此`COleCurrency`对象。  
  
```  
const COleCurrency& operator=(CURRENCY cySrc);  
const COleCurrency& operator=(const COleCurrency& curSrc);  
  const COleCurrency& operator=(const VARIANT& varSrc);
```  
  
### <a name="remarks"></a>备注  
 每个运算符的简短说明如下所示：  
  
- **运算符 = (** `cySrc` **)** `CURRENCY`值复制到`COleCurrency`对象并将其状态设置为有效。  
  
- **运算符 = (** `curSrc` **)** 的值和状态的现有操作数`COleCurrency`对象复制到此`COleCurrency`对象。  
  
- **运算符 = (** *varSrc* **)** 如果的转换`VARIANT`值 (或[COleVariant](../../mfc/reference/colevariant-class.md)对象) 的货币 ( `VT_CY`) 是成功，转换后的值复制到此`COleCurrency`对象并将其状态设置为有效。 如果不成功，则转换的值`COleCurrency`对象设置为 0，其状态设置为无效。  
  
 有关详细信息，请参阅[货币](http://msdn.microsoft.com/5e81273c-7289-45c7-93c0-32c1553f708e)并[变体](http://msdn.microsoft.com/e305240e-9e11-4006-98cc-26f4932d2118)Windows SDK 中的条目。  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_MFCOleContainer#15](../../mfc/codesnippet/cpp/colecurrency-class_4.cpp)]  
  
##  <a name="operator_plus_minus"></a>  COleCurrency::operator +、-  
 这些运算符使您得以，加法和减法两个`COleCurrency`值到和从每个其他和更改的登录`COleCurrency`值。  
  
```  
COleCurrency operator+(const COleCurrency& cur) const;  
COleCurrency operator-(const COleCurrency& cur) const;  
COleCurrency operator-() const;  
```  
  
### <a name="remarks"></a>备注  
 如果任一操作数是 null，生成的状态`COleCurrency`值为 null。  
  
 如果算术运算溢出，从而`COleCurrency`值无效。  
  
 如果操作数为无效，另一个是不为 null，生成的状态`COleCurrency`值无效。  
  
 有关有效、 无效和 null 的状态值的详细信息，请参阅[m_status](#m_status)成员变量。  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_MFCOleContainer#16](../../mfc/codesnippet/cpp/colecurrency-class_5.cpp)]  
  
##  <a name="operator_plus_minus_eq"></a>  COleCurrency::operator + =、 =  
 可以，加法和减法`COleCurrency`值到和从该`COleCurrency`对象。  
  
```  
const COleCurrency& operator+=(const COleCurrency& cur);  
const COleCurrency& operator-=(const COleCurrency& cur);
```  
  
### <a name="remarks"></a>备注  
 如果任一操作数是 null，此状态`COleCurrency`对象设置为 null。  
  
 如果算术运算溢出，此状态`COleCurrency`对象设置为无效。  
  
 如果任一操作数是无效的并且另一个则不为 null，此状态`COleCurrency`对象设置为无效。  
  
 有关有效、 无效和 null 的状态值的详细信息，请参阅[m_status](#m_status)成员变量。  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_MFCOleContainer#17](../../mfc/codesnippet/cpp/colecurrency-class_6.cpp)]  
  
##  <a name="operator_star"></a>  COleCurrency::operator\*和 /  
 可用于缩放`COleCurrency`的整数值的值。  
  
```  
COleCurrency operator*(long nOperand) const;  
COleCurrency operator/(long nOperand) const;  
```  
  
### <a name="remarks"></a>备注  
 如果`COleCurrency`操作数为 null，生成的状态`COleCurrency`值为 null。  
  
 如果算术运算溢出或下溢，生成的状态`COleCurrency`值无效。  
  
 如果`COleCurrency`操作数是无效的所生成的状态`COleCurrency`值无效。  
  
 有关有效、 无效和 null 的状态值的详细信息，请参阅[m_status](#m_status)成员变量。  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_MFCOleContainer#18](../../mfc/codesnippet/cpp/colecurrency-class_7.cpp)]  
  
##  <a name="operator_star_div_eq"></a>  COleCurrency::operator \*=、 / =  
 允许你可以扩展这`COleCurrency`的整数值的值。  
  
```  
const COleCurrency& operator*=(long nOperand);  
const COleCurrency& operator/=(long nOperand);
```  
  
### <a name="remarks"></a>备注  
 如果`COleCurrency`操作数为 null，此状态`COleCurrency`对象设置为 null。  
  
 如果算术运算溢出，此状态`COleCurrency`对象设置为无效。  
  
 如果`COleCurrency`操作数是无效的此状态`COleCurrency`对象设置为无效。  
  
 有关有效、 无效和 null 的状态值的详细信息，请参阅[m_status](#m_status)成员变量。  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_MFCOleContainer#19](../../mfc/codesnippet/cpp/colecurrency-class_8.cpp)]  
  
##  <a name="operator_stream"></a>  COleCurrency::operator &lt; &lt;， &gt;&gt;  
 支持诊断转储和存储到存档。  
  
```  
friend CDumpContext& operator<<(
    CDumpContext& dc,  
    COleCurrency curSrc);
 
friend CArchive& operator<<(
    CArchive& ar,  
    COleCurrency curSrc);
 
friend CArchive& operator>>(
    CArchive& ar,  
    COleCurrency& curSrc);
```  
  
### <a name="remarks"></a>备注  
 提取 ( **>>**) 运算符支持加载从存档。  
  
##  <a name="operator_currency"></a>  COleCurrency::operator 货币  
 返回`CURRENCY`其值将复制从该结构`COleCurrency`对象。  
  
```  
operator CURRENCY() const; 
```  
  
### <a name="remarks"></a>备注  
  
##  <a name="parsecurrency"></a>  COleCurrency::ParseCurrency  
 调用此成员函数可分析要读取的货币值的字符串。  
  
```  
BOOL ParseCurrency(
    LPCTSTR lpszCurrency,  
    DWORD dwFlags = 0,  
    LCID lcid = LANG_USER_DEFAULT);
 
throw(CMemoryException*); 
throw(COleException*);
```  
  
### <a name="parameters"></a>参数  
 *lpszCurrency*  
 指向以 null 结尾的字符串，这是要分析的指针。  
  
 *dwFlags*  
 指示区域设置，可能是以下标志的标志：  
  
- LOCALE_NOUSEROVERRIDE 使用系统默认区域设置，而不是自定义用户设置。  
  
 *lcid*  
 指示要使用用于转换的区域设置 ID。  
  
### <a name="return-value"></a>返回值  
 如果字符串是否成功转换为货币值，否则为 0，非零值。  
  
### <a name="remarks"></a>备注  
 它使用本地语言规范 （区域设置 Id） 的源字符串中的非数字字符含义。  
  
 有关区域设置 ID 值的讨论，请参阅[支持多种语言](http://msdn.microsoft.com/47dc5add-232c-4268-b977-43e12da81ede)。  
  
 如果字符串是否已成功转换为货币值，此设置的值`COleCurrency`对象设置为该值，并且其状态设置为有效。  
  
 如果字符串无法转换为货币值或数值溢出，此状态时出现`COleCurrency`对象无效。  
  
 如果字符串转换失败，因为内存分配错误，此函数将引发[CMemoryException](../../mfc/reference/cmemoryexception-class.md)。 在任何其他错误状态下，此函数将引发[COleException](../../mfc/reference/coleexception-class.md)。  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_MFCOleContainer#13](../../mfc/codesnippet/cpp/colecurrency-class_9.cpp)]  
  
##  <a name="colecurrency_relational_operators"></a>  COleCurrency 关系运算符  
 比较两个货币值，并返回非零，如果条件为 true;否则为 0。  
  
```  
BOOL operator==(const COleCurrency& cur) const;  
BOOL operator!=(const COleCurrency& cur) const;  
BOOL operator<(const COleCurrency& cur) const;  
BOOL operator>(const COleCurrency& cur) const;  
BOOL operator<=(const COleCurrency& cur) const;  
BOOL operator>=(const COleCurrency& cur) const;  
```  
  
### <a name="remarks"></a>备注  
  
> [!NOTE]
>  排序操作的返回值 ( **<**， **\< =**， **>**， **>=**) 是不确定，如果其中一个操作数的状态为 null 或无效。 相等运算符 ( `==`， `!=`) 考虑操作数的状态。  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_MFCOleContainer#20](../../mfc/codesnippet/cpp/colecurrency-class_10.cpp)]  
  
##  <a name="setcurrency"></a>  COleCurrency::SetCurrency  
 调用此成员函数可设置的单位和小数部分的这`COleCurrency`对象。  
  
```  
void SetCurrency(
    long nUnits,  
    long nFractionalUnits);
```  
  
### <a name="parameters"></a>参数  
 *nUnits*， *nFractionalUnits*  
 指示要复制到此的单位和小数部分 （在 1/万为单位） 的值的`COleCurrency`对象。  
  
### <a name="remarks"></a>备注  
 如果值的小数部分的绝对值大于 10000，适当调整发出单元中的第三个以下的示例所示。  
  
 请注意，由指定的单位和小数部分有符号长值。 下面的示例的第四个演示当参数具有不同的符号时，会发生什么情况。  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_MFCOleContainer#14](../../mfc/codesnippet/cpp/colecurrency-class_11.cpp)]  
  
##  <a name="setstatus"></a>  COleCurrency::SetStatus  
 调用此成员函数可设置的状态 （有效期）`COleCurrency`对象。  
  
```  
void SetStatus(CurrencyStatus  status  );
```  
  
### <a name="parameters"></a>参数  
 *status*  
 为此新的状态`COleCurrency`对象。  
  
### <a name="remarks"></a>备注  
 *状态*参数值由定义`CurrencyStatus`枚举中定义的类型`COleCurrency`类。  
  
```  
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };  
```  
  
 有关这些状态的值的简要说明，请参阅下面的列表：  
  
- `COleCurrency::valid` 指示此`COleCurrency`对象是否有效。  
  
- `COleCurrency::invalid` 指示此`COleCurrency`对象无效; 即，其值可能不正确。  
  
- `COleCurrency::null` 指示此`COleCurrency`对象为 null，也即，已为此对象提供任何值。 （此为"null"数据库意义上的"无任何值，"，而不 c + + 为 NULL。）  
  
> [!CAUTION]
>  此函数是针对高级编程情况。 此函数不会更改此对象中的数据。 通常将用于将状态设置为 null 或无效的。 请注意，赋值运算符 ([运算符 =](#operator_eq)) 和[SetCurrency](#setcurrency)设置到的源值所基于的对象的状态。  
  
## <a name="see-also"></a>请参阅  
 [层次结构图表](../../mfc/hierarchy-chart.md)   
 [COleVariant 类](../../mfc/reference/colevariant-class.md)
