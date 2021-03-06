---
title: 功能 (STL/CLR) |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- <cliext/functional>
- cliext::binary_delegate
- cliext::binary_delegate_noreturn
- cliext::binary_negate
- cliext::bind1st
- cliext::bind2nd
- cliext::binder1st
- cliext::binder2nd
- cliext::divides
- cliext::equal_to
- cliext::greater
- cliext::greater_equal
- cliext::less
- cliext::less_equal
- cliext::logical_and
- cliext::logical_not
- cliext::logical_or
- cliext::minus
- cliext::modulus
- cliext::multiplies
- cliext::negate
- cliext::not_equal_to
- cliext::not1
- cliext::not2
- cliext::plus
- cliext::unary_delegate
- cliext::unary_delegate_noreturn
- cliext::unary_negate
dev_langs:
- C++
helpviewer_keywords:
- <functional> header [STL/CLR]
- <cliext/functional> header [STL/CLR]
- functional functions [STL/CLR]
- binary_delegate function [STL/CLR]
- binary_delegate_noreturn function [STL/CLR]
- binary_negate function [STL/CLR]
- bind1st function [STL/CLR]
- bind2nd function [STL/CLR]
- binder1st function [STL/CLR]
- binder2nd function [STL/CLR]
- divides function [STL/CLR]
- equal_to function [STL/CLR]
- greater function [STL/CLR]
- greater_equal function [STL/CLR]
- less function [STL/CLR]
- less_equal function [STL/CLR]
- logical_and function [STL/CLR]
- logical_not function [STL/CLR]
- logical_or function [STL/CLR]
- minus function [STL/CLR]
- modulus function [STL/CLR]
- multiplies function [STL/CLR]
- negate function [STL/CLR]
- not_equal_to function [STL/CLR]
- not1 function [STL/CLR]
- not2 function [STL/CLR]
- plus function [STL/CLR]
- unary_delegate function [STL/CLR]
- unary_delegate_noreturn function [STL/CLR]
- unary_negate function [STL/CLR]
ms.assetid: 88738b8c-5d37-4375-970e-a4442bf5efde
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 04596cd043b90d8016cd0f9b1ebfe05a9bf82f72
ms.sourcegitcommit: 301bb19056e5bae84ff50f7d1df1e546efe225ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "36305899"
---
# <a name="functional-stlclr"></a>functional (STL/CLR)
包括 STL/CLR 标头`<cliext/functional>`定义大量的模板类和相关的模板委托和函数。  
  
## <a name="syntax"></a>语法  
  
```  
#include <functional>  
```  

## <a name="requirements"></a>要求  
 **标头：** \<功能 cliext/>  
  
 **Namespace:** cliext 

## <a name="declarations"></a>声明  
  
|委托|Description|  
|--------------|-----------------|  
|[binary_delegate (STL/CLR)](#binary_delegate)|两个参数的委托。|  
|[binary_delegate_noreturn (STL/CLR)](#binary_delegate_noreturn)|返回两个参数委托`void`。|  
|[unary_delegate (STL/CLR)](#unary_delegate)|一个参数的委托。|  
|[unary_delegate_noreturn (STL/CLR)](#unary_delegate_noreturn)|返回的单自变量委托`void`。|  
  
|类|Description|  
|-----------|-----------------|  
|[binary_negate (STL/CLR)](#binary_negate)|要求反的两个参数函子的函子。|  
|[binder1st (STL/CLR)](#binder1st)|若要将第一个自变量绑定到两个参数函子的函子。|  
|[binder2nd (STL/CLR)](#binder2nd)|若要将第二个参数绑定到两个参数函子的函子。|  
|[divides (STL/CLR)](#divides)|将划分函子。|  
|[equal_to (STL/CLR)](#equal_to)|相等比较函子。|  
|[greater (STL/CLR)](#greater)|更大的比较函子。|  
|[greater_equal (STL/CLR)](#greater_equal)|大于或等于比较函子。|  
|[less (STL/CLR)](#less)|小于比较函子。|  
|[less_equal (STL/CLR)](#less_equal)|小于或等于比较函子。|  
|[logical_and (STL/CLR)](#logical_and)|逻辑 AND 函子。|  
|[logical_not (STL/CLR)](#logical_not)|逻辑不函子。|  
|[logical_or (STL/CLR)](#logical_or)|逻辑 OR 函子。|  
|[minus (STL/CLR)](#minus)|减去函子。|  
|[modulus (STL/CLR)](#modulus)|取模函子。|  
|[multiplies (STL/CLR)](#multiplies)|乘函子。|  
|[negate (STL/CLR)](#negate)|返回求反后其自变量的函子。|  
|[not_equal_to (STL/CLR)](#not_equal_to)|不等于比较函子。|  
|[plus (STL/CLR)](#plus)|添加函子。|  
|[unary_negate (STL/CLR)](#unary_negate)|要求反单自变量函子的函子。|  
  
|函数|Description|  
|--------------|-----------------|  
|[bind1st (STL/CLR)](#bind1st)|生成自变量和函子的 binder1st。|  
|[bind2nd (STL/CLR)](#bind2nd)|生成自变量和函子的 binder2nd。|  
|[not1 (STL/CLR)](#not1)|生成函子 unary_negate。|  
|[not2 (STL/CLR)](#not2)|生成函子 binary_negate。|  
   
## <a name="members"></a>成员

## <a name="binary_delegate"></a> binary_delegate (STL/CLR)
Genereic 类描述两个参数的委托。 使用它指定根据其自变量和返回类型的委托。  
  
### <a name="syntax"></a>语法  
  
```  
generic<typename Arg1,  
    typename Arg2,  
    typename Result>  
    delegate Result binary_delegate(Arg1, Arg2);  
```  
  
#### <a name="parameters"></a>参数  
 arg1  
 第一个参数的类型。  
  
 arg2  
 第二个参数的类型。  
  
 结果  
 返回类型。  
  
### <a name="remarks"></a>备注  
 Genereic 委托介绍了两个参数的函数。  
  
 请注意，对于：  
  
 `binary_delegate<int, int, int> Fun1;`  
  
 `binary_delegate<int, int, int> Fun2;`  
  
 类型`Fun1`和`Fun2`是同义词，而为：  
  
 `delegate int Fun1(int, int);`  
  
 `delegate int Fun2(int, int);`  
  
 它们不是同一类型。  
  
### <a name="example"></a>示例  
  
```cpp  
// cliext_binary_delegate.cpp   
// compile with: /clr   
#include <cliext/functional>   
  
bool key_compare(wchar_t left, wchar_t right)   
    {   
    return (left < right);   
    }   
  
typedef cliext::binary_delegate<wchar_t, wchar_t, bool> Mydelegate;   
int main()   
    {   
    Mydelegate^ kcomp = gcnew Mydelegate(&key_compare);   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
compare(L'a', L'a') = False  
compare(L'a', L'b') = True  
compare(L'b', L'a') = False  
```  

## <a name="binary_delegate_noreturn"></a> binary_delegate_noreturn (STL/CLR)
Genereic 类描述两个参数委托，可返回`void`。 使用它指定根据其自变量的委托。  
  
### <a name="syntax"></a>语法  
  
```  
generic<typename Arg1,  
    typename Arg2>  
    delegate void binary_delegate(Arg1, Arg2);  
```  
  
#### <a name="parameters"></a>参数  
 arg1  
 第一个参数的类型。  
  
 arg2  
 第二个参数的类型。  
  
### <a name="remarks"></a>备注  
 Genereic 委托描述返回的两个参数函数`void`。  
  
 请注意，对于：  
  
 `binary_delegate_noreturn<int, int> Fun1;`  
  
 `binary_delegate_noreturn<int, int> Fun2;`  
  
 类型`Fun1`和`Fun2`是同义词，而为：  
  
 `delegate void Fun1(int, int);`  
  
 `delegate void Fun2(int, int);`  
  
 它们不是同一类型。  
  
### <a name="example"></a>示例  
  
```cpp  
// cliext_binary_delegate_noreturn.cpp   
// compile with: /clr   
#include <cliext/functional>   
  
void key_compare(wchar_t left, wchar_t right)   
    {   
    System::Console::WriteLine("compare({0}, {1}) = {2}",   
        left, right, left < right);   
    }   
  
typedef cliext::binary_delegate_noreturn<wchar_t, wchar_t> Mydelegate;   
int main()   
    {   
    Mydelegate^ kcomp = gcnew Mydelegate(&key_compare);   
  
    kcomp(L'a', L'a');   
    kcomp(L'a', L'b');   
    kcomp(L'b', L'a');   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
compare(a, a) = False  
compare(a, b) = True  
compare(b, a) = False  
```  

## <a name="binary_negate"></a> binary_negate (STL/CLR)
此模板类描述某个函数，当调用，返回的逻辑不其存储的两个参数函子。 使用它指定根据其存储的函子的函数对象。  
  
### <a name="syntax"></a>语法  
  
```  
template<typename Fun>  
    ref class binary_negate  
    { // wrap operator()  
public:  
    typedef Fun stored_function_type;  
    typedef typename Fun::first_argument_type first_argument_type;  
    typedef typename Fun::second_argument_type second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    explicit binary_negate(Fun% functor);  
    binary_negate(binary_negate<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>参数  
 有趣  
 存储函子的类型。  
  
## <a name="member-functions"></a>成员函数  
  
|类型定义|Description|  
|---------------------|-----------------|  
|delegate_type|泛型委托的类型。|  
|first_argument_type|函子的第一个自变量的类型。|  
|result_type|函子结果的类型。|  
|second_argument_type|函子的第二个自变量的类型。|  
|stored_function_type|函子的类型。|  
  
|成员|Description|  
|------------|-----------------|  
|binary_negate|构造函数。|  
  
|运算符|Description|  
|--------------|-----------------|  
|operator()|计算所需的函数。|  
|运算符 delegate_type^()|强制转换为委托的函子。|  
  
### <a name="remarks"></a>备注  
 此模板类描述存储其他两个参数函子的两个参数伪函数。 它定义了成员运算符`operator()`以便为函数调用时对象，它将返回逻辑的存储函子的不调用带有两个参数。  
  
 你还可以作为其类型函数自变量传递对象`delegate_type^`和它将会相应地进行转换。  
  
### <a name="example"></a>示例  
  
```cpp  
// cliext_binary_negate.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c2;   
    c2.push_back(4);   
    c2.push_back(4);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 4 4"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::less<int> less_op;   
  
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(),   
        cliext::binary_negate<cliext::less<int> >(less_op));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display with function   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::not2(less_op));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
4 4  
1 0  
1 0  
```  

## <a name="bind1st"></a> bind1st (STL/CLR)
生成`binder1st`有关自变量，以及函子。  
  
### <a name="syntax"></a>语法  
  
```  
template<typename Fun,  
    typename Arg>  
    binder1st<Fun> bind1st(Fun% functor,  
        Arg left);  
```  
  
#### <a name="template-parameters"></a>模板参数  
 Arg  
 自变量类型。  
  
 有趣  
 函子的类型。  
  
#### <a name="function-parameters"></a>函数参数  
 函子  
 包装函数。  
  
 左  
 要包装的第一个参数。  
  
### <a name="remarks"></a>备注  
 模板函数返回[binder1st (STL/CLR)](../dotnet/binder1st-stl-clr.md)`<Fun>(functor, left)`。 你将它用作一种简便方式中调用它与第二个参数的单自变量涵子包装两个参数函子和其第一个参数。  
  
### <a name="example"></a>示例  
  
```cpp  
// cliext_bind1st.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::minus<int> sub_op;   
    cliext::binder1st<cliext::minus<int> > subfrom3(sub_op, 3);   
  
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        subfrom3);   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display with function   
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        bind1st(sub_op, 3));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
-1 0  
-1 0  
```  

## <a name="bind2nd"></a> bind2nd (STL/CLR)
生成`binder2nd`有关自变量，以及函子。  
  
### <a name="syntax"></a>语法  
  
```  
template<typename Fun,  
    typename Arg>  
    binder2nd<Fun> bind2nd(Fun% functor,  
        Arg right);  
```  
  
#### <a name="template-parameters"></a>模板参数  
 Arg  
 自变量类型。  
  
 有趣  
 函子的类型。  
  
#### <a name="function-parameters"></a>函数参数  
 函子  
 包装函数。  
  
 右  
 要包装的第二个参数。  
  
### <a name="remarks"></a>备注  
 模板函数返回[binder2nd (STL/CLR)](../dotnet/binder2nd-stl-clr.md)`<Fun>(functor, right)`。 你将它用作一种简便方式将两个参数函子和其第二个自变量包装在使用第一个参数调用它的单自变量伪函数。  
  
### <a name="example"></a>示例  
  
```cpp  
// cliext_bind2nd.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::minus<int> sub_op;   
    cliext::binder2nd<cliext::minus<int> > sub4(sub_op, 4);   
  
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        sub4);   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display with function   
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        bind2nd(sub_op, 4));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
0 -1  
0 -1  
```  

## <a name="binder1st"></a> binder1st (STL/CLR)
此模板类描述一个自变量函子的当调用，返回其存储的第一个参数而提供的第二个自变量调用其存储两个参数函子。 使用它指定根据其存储的函子的函数对象。  
  
### <a name="syntax"></a>语法  
  
```  
template<typename Fun>  
    ref class binder1st  
    { // wrap operator()  
public:  
    typedef Fun stored_function_type;  
    typedef typename Fun::first_argument_type first_argument_type;  
    typedef typename Fun::second_argument_type second_argument_type;  
    typedef typename Fun:result_type result_type;  
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<  
        second_argument_type, result_type>  
        delegate_type;  
  
    binder1st(Fun% functor, first_argument_type left);  
    binder1st(binder1st<Arg>% right);  
  
    result_type operator()(second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>参数  
 有趣  
 存储函子的类型。  
  
### <a name="member-functions"></a>成员函数  
  
|类型定义|Description|  
|---------------------|-----------------|  
|delegate_type|泛型委托的类型。|  
|first_argument_type|函子的第一个自变量的类型。|  
|result_type|函子结果的类型。|  
|second_argument_type|函子的第二个自变量的类型。|  
|stored_function_type|函子的类型。|  
  
|成员|Description|  
|------------|-----------------|  
|binder1st|构造函数。|  
  
|运算符|Description|  
|--------------|-----------------|  
|operator()|计算所需的函数。|  
|运算符 delegate_type^()|强制转换为委托的函子。|  
  
### <a name="remarks"></a>备注  
 此模板类描述存储两个参数函子和的第一个参数的单自变量伪函数。 它定义了成员运算符`operator()`以便为函数调用时对象，它将返回调用存储的第一个参数而提供的第二个自变量的存储函子的结果。  
  
 你还可以作为其类型函数自变量传递对象`delegate_type^`和它将会相应地进行转换。  
  
### <a name="example"></a>示例  
  
```cpp  
// cliext_binder1st.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::minus<int> sub_op;   
    cliext::binder1st<cliext::minus<int> > subfrom3(sub_op, 3);   
  
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        subfrom3);   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display with function   
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        bind1st(sub_op, 3));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
-1 0  
-1 0  
```  

## <a name="binder2nd"></a> binder2nd (STL/CLR)
此模板类描述一个自变量函子的当调用，则返回存储其使用提供的第一个自变量和其存储的第二个自变量调用的两个参数函子。 使用它指定根据其存储的函子的函数对象。  
  
### <a name="syntax"></a>语法  
  
```  
template<typename Fun>  
    ref class binder2nd  
    { // wrap operator()  
public:  
    typedef Fun stored_function_type;  
    typedef typename Fun::first_argument_type first_argument_type;  
    typedef typename Fun::second_argument_type second_argument_type;  
    typedef typename Fun:result_type result_type;  
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<  
        first_argument_type, result_type>  
        delegate_type;  
  
    binder2nd(Fun% functor, second_argument_type left);  
    binder2nd(binder2nd<Arg>% right);  
  
    result_type operator()(first_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>参数  
 有趣  
 存储函子的类型。  
  
## <a name="member-functions"></a>成员函数  
  
|类型定义|Description|  
|---------------------|-----------------|  
|delegate_type|泛型委托的类型。|  
|first_argument_type|函子的第一个自变量的类型。|  
|result_type|函子结果的类型。|  
|second_argument_type|函子的第二个自变量的类型。|  
|stored_function_type|函子的类型。|  
  
|成员|Description|  
|------------|-----------------|  
|binder2nd|构造函数。|  
  
|运算符|Description|  
|--------------|-----------------|  
|operator()|计算所需的函数。|  
|运算符 delegate_type^()|强制转换为委托的函子。|  
  
### <a name="remarks"></a>备注  
 此模板类描述存储两个参数函子和第二个参数的单自变量伪函数。 它定义了成员运算符`operator()`以便为函数调用时对象，它将返回调用使用提供的第一个自变量和存储的第二个参数的存储函子的结果。  
  
 你还可以作为其类型函数自变量传递对象`delegate_type^`和它将会相应地进行转换。  
  
### <a name="example"></a>示例  
  
```cpp  
// cliext_binder2nd.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::minus<int> sub_op;   
    cliext::binder2nd<cliext::minus<int> > sub4(sub_op, 4);   
  
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        sub4);   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display with function   
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        bind2nd(sub_op, 4));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
0 -1  
0 -1  
```  
  
## <a name="divides"></a> 会将其划分 (STL/CLR)
此模板类描述某个函数，当调用，返回除以第二个的第一个参数。 使用它指定根据其自变量类型的函数对象。  
  
### <a name="syntax"></a>语法  
  
```  
template<typename Arg>  
    ref class divides  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef Arg result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    divides();  
    divides(divides<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>参数  
 Arg  
 参数和返回值的类型。  
  
### <a name="member-functions"></a>成员函数  
  
|类型定义|Description|  
|---------------------|-----------------|  
|delegate_type|泛型委托的类型。|  
|first_argument_type|函子的第一个自变量的类型。|  
|result_type|函子结果的类型。|  
|second_argument_type|函子的第二个自变量的类型。|  
  
|成员|Description|  
|------------|-----------------|  
|divides|构造函数。|  
  
|运算符|Description|  
|--------------|-----------------|  
|operator()|计算所需的函数。|  
|运算符 delegate_type^()|强制转换为委托的函子。|  
  
### <a name="remarks"></a>备注  
 此模板类描述两个参数函子。 它定义了成员运算符`operator()`以便为函数调用时对象，它将返回第一个参数除以第二个。  
  
 你还可以作为其类型函数自变量传递对象`delegate_type^`和它将会相应地进行转换。  
  
### <a name="example"></a>示例  
  
```cpp  
// cliext_divides.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c2;   
    c2.push_back(2);   
    c2.push_back(1);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 2 1"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::divides<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
2 1  
2 3  
```  

## <a name="equal_to"></a> equal_to (STL/CLR)
此模板类描述某个函数，当调用时，返回 true，仅当第一个参数是否等于第二个。 使用它指定根据其自变量类型的函数对象。  
  
### <a name="syntax"></a>语法  
  
```  
template<typename Arg>  
    ref class equal_to  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    equal_to();  
    equal_to(equal_to<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>参数  
 Arg  
 参数的类型。  
  
### <a name="member-functions"></a>成员函数  
  
|类型定义|Description|  
|---------------------|-----------------|  
|delegate_type|泛型委托的类型。|  
|first_argument_type|函子的第一个自变量的类型。|  
|result_type|函子结果的类型。|  
|second_argument_type|函子的第二个自变量的类型。|  
  
|成员|Description|  
|------------|-----------------|  
|equal_to|构造函数。|  
  
|运算符|Description|  
|--------------|-----------------|  
|operator()|计算所需的函数。|  
|运算符 delegate_type^()|强制转换为委托的函子。|  
  
### <a name="remarks"></a>备注  
 此模板类描述两个参数函子。 它定义了成员运算符`operator()`以便为函数调用时对象，它将返回 true 仅第一个参数是否等于第二个。  
  
 你还可以作为其类型函数自变量传递对象`delegate_type^`和它将会相应地进行转换。  
  
### <a name="example"></a>示例  
  
```cpp  
// cliext_equal_to.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c2;   
    c2.push_back(4);   
    c2.push_back(4);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 4 4"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::equal_to<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
4 4  
1 0  
```  

## <a name="greater"></a> 更高版本 (STL/CLR)
此模板类描述某个函数，当调用时，返回 true，仅当第一个参数为大于第二个。 使用它指定根据其自变量类型的函数对象。  
  
### <a name="syntax"></a>语法  
  
```  
template<typename Arg>  
    ref class greater  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    greater();  
    greater(greater<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>参数  
 Arg  
 参数的类型。  
  
### <a name="member-functions"></a>成员函数  
  
|类型定义|Description|  
|---------------------|-----------------|  
|delegate_type|泛型委托的类型。|  
|first_argument_type|函子的第一个自变量的类型。|  
|result_type|函子结果的类型。|  
|second_argument_type|函子的第二个自变量的类型。|  
  
|成员|Description|  
|------------|-----------------|  
|greater|构造函数。|  
  
|运算符|Description|  
|--------------|-----------------|  
|operator()|计算所需的函数。|  
|运算符 delegate_type ^|强制转换为委托的函子。|  
  
### <a name="remarks"></a>备注  
 此模板类描述两个参数函子。 它定义了成员运算符`operator()`以便为函数调用时对象，它将返回 true 仅第一个自变量是否大于第二个。  
  
 你还可以作为其类型函数自变量传递对象`delegate_type^`和它将会相应地进行转换。  
  
### <a name="example"></a>示例  
  
```cpp  
// cliext_greater.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c2;   
    c2.push_back(3);   
    c2.push_back(3);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 3 3"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::greater<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
3 3  
1 0  
```  

## <a name="greater_equal"></a> greater_equal (STL/CLR)
此模板类描述某个函数，当调用时，返回 true 仅第一个自变量是否大于或等于第二个。 使用它指定根据其自变量类型的函数对象。  
  
### <a name="syntax"></a>语法  
  
```  
template<typename Arg>  
    ref class greater_equal  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    greater_equal();  
    greater_equal(greater_equal<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>参数  
 Arg  
 参数的类型。  
  
### <a name="member-functions"></a>成员函数  
  
|类型定义|Description|  
|---------------------|-----------------|  
|delegate_type|泛型委托的类型。|  
|first_argument_type|函子的第一个自变量的类型。|  
|result_type|函子结果的类型。|  
|second_argument_type|函子的第二个自变量的类型。|  
  
|成员|Description|  
|------------|-----------------|  
|greater_equal|构造函数。|  
  
|运算符|Description|  
|--------------|-----------------|  
|operator()|计算所需的函数。|  
|运算符 delegate_type ^|强制转换为委托的函子。|  
  
### <a name="remarks"></a>备注  
 此模板类描述两个参数函子。 它定义了成员运算符`operator()`以便为函数调用时对象，它将返回 true 仅第一个自变量是否大于或等于第二个。  
  
 你还可以作为其类型函数自变量传递对象`delegate_type^`和它将会相应地进行转换。  
  
### <a name="example"></a>示例  
  
```cpp  
// cliext_greater_equal.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c2;   
    c2.push_back(4);   
    c2.push_back(4);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 4 4"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::greater_equal<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
4 4  
1 0  
```  

## <a name="less"></a> 较少的 (STL/CLR)
此模板类描述某个函数，当调用时，返回 true，仅当第一个参数小于第二个。 使用它指定根据其自变量类型的函数对象。  
  
### <a name="syntax"></a>语法  
  
```  
template<typename Arg>  
    ref class less  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    less();  
    less(less<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>参数  
 Arg  
 参数的类型。  
  
### <a name="member-functions"></a>成员函数  
  
|类型定义|Description|  
|---------------------|-----------------|  
|delegate_type|泛型委托的类型。|  
|first_argument_type|函子的第一个自变量的类型。|  
|result_type|函子结果的类型。|  
|second_argument_type|函子的第二个自变量的类型。|  
  
|成员|Description|  
|------------|-----------------|  
|less|构造函数。|  
  
|运算符|Description|  
|--------------|-----------------|  
|operator()|计算所需的函数。|  
|运算符 delegate_type ^|强制转换为委托的函子。|  
  
### <a name="remarks"></a>备注  
 此模板类描述两个参数函子。 它定义了成员运算符`operator()`以便为函数调用时对象，它将返回 true 仅第一个参数是否小于第二个。  
  
 你还可以作为其类型函数自变量传递对象`delegate_type^`和它将会相应地进行转换。  
  
### <a name="example"></a>示例  
  
```cpp  
// cliext_less.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c2;   
    c2.push_back(4);   
    c2.push_back(4);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 4 4"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::less<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
4 4  
0 1  
``` 

## <a name="less_equal"></a> less_equal (STL/CLR)
此模板类描述某个函数，当调用时，返回 true 仅第一个参数是否小于或等于第二个。 使用它指定根据其自变量类型的函数对象。  
  
### <a name="syntax"></a>语法  
  
```  
template<typename Arg>  
    ref class less_equal  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    less_equal();  
    less_equal(less_equal<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>参数  
 Arg  
 参数的类型。  
  
### <a name="member-functions"></a>成员函数  
  
|类型定义|Description|  
|---------------------|-----------------|  
|delegate_type|泛型委托的类型。|  
|first_argument_type|函子的第一个自变量的类型。|  
|result_type|函子结果的类型。|  
|second_argument_type|函子的第二个自变量的类型。|  
  
|成员|Description|  
|------------|-----------------|  
|less_equal|构造函数。|  
  
|运算符|Description|  
|--------------|-----------------|  
|operator()|计算所需的函数。|  
|运算符 delegate_type ^|强制转换为委托的函子。|  
  
### <a name="remarks"></a>备注  
 此模板类描述两个参数函子。 它定义了成员运算符`operator()`以便为函数调用时对象，它将返回 true 仅第一个参数是否小于或等于第二个。  
  
 你还可以作为其类型函数自变量传递对象`delegate_type^`和它将会相应地进行转换。  
  
### <a name="example"></a>示例  
  
```cpp  
// cliext_less_equal.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c2;   
    c2.push_back(3);   
    c2.push_back(3);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 3 3"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::less_equal<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
3 3  
0 1  
``` 

## <a name="logical_and"></a> logical_and (STL/CLR)
此模板类描述某个函数，当调用时，返回 true，仅当第一个参数，第二个测试可以为 true。 使用它指定根据其自变量类型的函数对象。  
  
### <a name="syntax"></a>语法  
  
```  
template<typename Arg>  
    ref class logical_and  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    logical_and();  
    logical_and(logical_and<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>参数  
 Arg  
 参数的类型。  
  
### <a name="member-functions"></a>成员函数  
  
|类型定义|Description|  
|---------------------|-----------------|  
|delegate_type|泛型委托的类型。|  
|first_argument_type|函子的第一个自变量的类型。|  
|result_type|函子结果的类型。|  
|second_argument_type|函子的第二个自变量的类型。|  
  
|成员|Description|  
|------------|-----------------|  
|logical_and|构造函数。|  
  
|运算符|Description|  
|--------------|-----------------|  
|operator()|计算所需的函数。|  
|运算符 delegate_type ^|强制转换为委托的函子。|  
  
### <a name="remarks"></a>备注  
 此模板类描述两个参数函子。 它定义了成员运算符`operator()`以便为函数调用时对象，它将返回 true 仅当第一个参数，第二个测试可以为 true。  
  
 你还可以作为其类型函数自变量传递对象`delegate_type^`和它将会相应地进行转换。  
  
### <a name="example"></a>示例  
  
```cpp  
// cliext_logical_and.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(2);   
    c1.push_back(0);   
    Myvector c2;   
    c2.push_back(3);   
    c2.push_back(0);   
    Myvector c3(2, 0);   
  
// display initial contents " 1 0" and " 1 0"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::logical_and<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
2 0  
3 0  
1 0  
``` 

## <a name="logical_not"></a> logical_not (STL/CLR)
此模板类描述某个函数，当调用时，返回 true，仅当任一其自变量测试为 false。 使用它指定根据其自变量类型的函数对象。  
  
### <a name="syntax"></a>语法  
  
```  
template<typename Arg>  
    ref class logical_not  
    { // wrap operator()  
public:  
    typedef Arg argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<  
        argument_type, result_type>  
        delegate_type;  
  
    logical_not();  
    logical_not(logical_not<Arg> %right);  
  
    result_type operator()(argument_type left);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>参数  
 Arg  
 参数的类型。  
  
### <a name="member-functions"></a>成员函数  
  
|类型定义|Description|  
|---------------------|-----------------|  
|argument_type|伪函数自变量的类型。|  
|delegate_type|泛型委托的类型。|  
|result_type|函子结果的类型。|  
  
|成员|Description|  
|------------|-----------------|  
|logical_not|构造函数。|  
  
|运算符|Description|  
|--------------|-----------------|  
|operator()|计算所需的函数。|  
|运算符 delegate_type ^|强制转换为委托的函子。|  
  
### <a name="remarks"></a>备注  
 此模板类描述一个自变量函子。 它定义了成员运算符`operator()`以便为函数调用时对象，它 true 仅返回其自变量如果测试为 false。  
  
 你还可以作为其类型函数自变量传递对象`delegate_type^`和它将会相应地进行转换。  
  
### <a name="example"></a>示例  
  
```cpp  
// cliext_logical_not.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(0);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 0"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c3.begin(), cliext::logical_not<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 0  
0 1  
``` 

## <a name="logical_or"></a> logical_or (STL/CLR)
此模板类描述某个函数，当调用时，返回 true，仅当第一个自变量或第二个测试为 true。 使用它指定根据其自变量类型的函数对象。  
  
### <a name="syntax"></a>语法  
  
```  
template<typename Arg>  
    ref class logical_or  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    logical_or();  
    logical_or(logical_or<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>参数  
 Arg  
 参数的类型。  
  
### <a name="member-functions"></a>成员函数  
  
|类型定义|Description|  
|---------------------|-----------------|  
|delegate_type|泛型委托的类型。|  
|first_argument_type|函子的第一个自变量的类型。|  
|result_type|函子结果的类型。|  
|second_argument_type|函子的第二个自变量的类型。|  
  
|成员|Description|  
|------------|-----------------|  
|logical_or|构造函数。|  
  
|运算符|Description|  
|--------------|-----------------|  
|operator()|计算所需的函数。|  
|运算符 delegate_type ^|强制转换为委托的函子。|  
  
### <a name="remarks"></a>备注  
 此模板类描述两个参数函子。 它定义了成员运算符`operator()`以便为函数调用时对象，它将返回 true 仅当 true 的第一个参数或作为第二个测试。  
  
 你还可以作为其类型函数自变量传递对象`delegate_type^`和它将会相应地进行转换。  
  
### <a name="example"></a>示例  
  
```cpp  
// cliext_logical_or.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(2);   
    c1.push_back(0);   
    Myvector c2;   
    c2.push_back(0);   
    c2.push_back(0);   
    Myvector c3(2, 0);   
  
// display initial contents " 2 0" and " 0 0"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::logical_or<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
2 0  
0 0  
1 0  
```      

## <a name="minus"></a> 减 (STL/CLR)
此模板类描述某个函数，当调用，则返回第一个减去第二个参数。 使用它指定根据其自变量类型的函数对象。  
  
### <a name="syntax"></a>语法  
  
```  
template<typename Arg>  
    ref class minus  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef Arg result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    minus();  
    minus(minus<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>参数  
 Arg  
 参数和返回值的类型。  
  
### <a name="member-functions"></a>成员函数  
  
|类型定义|Description|  
|---------------------|-----------------|  
|delegate_type|泛型委托的类型。|  
|first_argument_type|函子的第一个自变量的类型。|  
|result_type|函子结果的类型。|  
|second_argument_type|函子的第二个自变量的类型。|  
  
|成员|Description|  
|------------|-----------------|  
|minus|构造函数。|  
  
|运算符|Description|  
|--------------|-----------------|  
|operator()|计算所需的函数。|  
|运算符 delegate_type ^|强制转换为委托的函子。|  
  
### <a name="remarks"></a>备注  
 此模板类描述两个参数函子。 它定义了成员运算符`operator()`以便为函数调用时对象，它将返回第一个减去第二个参数。  
  
 你还可以作为其类型函数自变量传递对象`delegate_type^`和它将会相应地进行转换。  
  
### <a name="example"></a>示例  
  
```cpp  
// cliext_minus.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c2;   
    c2.push_back(2);   
    c2.push_back(1);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 2 1"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::minus<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
2 1  
2 2  
``` 

## <a name="modulus"></a> 取模 (STL/CLR)
此模板类描述某个函数，当调用，则返回第二个模的第一个参数。 使用它指定根据其自变量类型的函数对象。  
  
### <a name="syntax"></a>语法  
  
```  
template<typename Arg>  
    ref class modulus  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef Arg result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    modulus();  
    modulus(modulus<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>参数  
 Arg  
 参数和返回值的类型。  
  
### <a name="member-functions"></a>成员函数  
  
|类型定义|Description|  
|---------------------|-----------------|  
|delegate_type|泛型委托的类型。|  
|first_argument_type|函子的第一个自变量的类型。|  
|result_type|函子结果的类型。|  
|second_argument_type|函子的第二个自变量的类型。|  
  
|成员|Description|  
|------------|-----------------|  
|modulus|构造函数。|  
  
|运算符|Description|  
|--------------|-----------------|  
|operator()|计算所需的函数。|  
|运算符 delegate_type ^|强制转换为委托的函子。|  
  
### <a name="remarks"></a>备注  
 此模板类描述两个参数函子。 它定义了成员运算符`operator()`以便为函数调用时对象，它将返回第二个模的第一个参数。  
  
 你还可以作为其类型函数自变量传递对象`delegate_type^`和它将会相应地进行转换。  
  
### <a name="example"></a>示例  
  
```cpp  
// cliext_modulus.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(2);   
    Myvector c2;   
    c2.push_back(3);   
    c2.push_back(1);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 2" and " 3 1"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::modulus<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 2  
3 1  
1 0  
```   

## <a name="multiplies"></a> 乘以 (STL/CLR)
此模板类描述某个函数，当调用，则返回第二个时间的第一个参数。 使用它指定根据其自变量类型的函数对象。  
  
### <a name="syntax"></a>语法  
  
```  
template<typename Arg>  
    ref class multiplies  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef Arg result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    multiplies();  
    multiplies(multiplies<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>参数  
 Arg  
 参数和返回值的类型。  
  
### <a name="member-functions"></a>成员函数  
  
|类型定义|Description|  
|---------------------|-----------------|  
|delegate_type|泛型委托的类型。|  
|first_argument_type|函子的第一个自变量的类型。|  
|result_type|函子结果的类型。|  
|second_argument_type|函子的第二个自变量的类型。|  
  
|成员|Description|  
|------------|-----------------|  
|multiplies|构造函数。|  
  
|运算符|Description|  
|--------------|-----------------|  
|operator()|计算所需的函数。|  
|运算符 delegate_type ^|强制转换为委托的函子。|  
  
### <a name="remarks"></a>备注  
 此模板类描述两个参数函子。 它定义了成员运算符`operator()`以便为函数调用时对象，它将返回第二个时间的第一个参数。  
  
 你还可以作为其类型函数自变量传递对象`delegate_type^`和它将会相应地进行转换。  
  
### <a name="example"></a>示例  
  
```cpp  
// cliext_multiplies.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c2;   
    c2.push_back(2);   
    c2.push_back(1);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 2 1"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::multiplies<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
2 1  
8 3  
```  

## <a name="negate"></a> 要求反 (STL/CLR)
此模板类描述某个函数，当调用，返回求反后其自变量。 使用它指定根据其自变量类型的函数对象。  
  
### <a name="syntax"></a>语法  
  
```  
template<typename Arg>  
    ref class negate  
    { // wrap operator()  
public:  
    typedef Arg argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<  
        argument_type, result_type>  
        delegate_type;  
  
    negate();  
    negate(negate<Arg>% right);  
  
    result_type operator()(argument_type left);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>参数  
 Arg  
 参数的类型。  
  
### <a name="member-functions"></a>成员函数  
  
|类型定义|Description|  
|---------------------|-----------------|  
|argument_type|伪函数自变量的类型。|  
|delegate_type|泛型委托的类型。|  
|result_type|函子结果的类型。|  
  
|成员|Description|  
|------------|-----------------|  
|negate|构造函数。|  
  
|运算符|Description|  
|--------------|-----------------|  
|operator()|计算所需的函数。|  
|运算符 delegate_type ^|强制转换为委托的函子。|  
  
### <a name="remarks"></a>备注  
 此模板类描述一个自变量函子。 它定义了成员运算符`operator()`以便为函数调用时对象，它将返回求反后其自变量。  
  
 你还可以作为其类型函数自变量传递对象`delegate_type^`和它将会相应地进行转换。  
  
### <a name="example"></a>示例  
  
```cpp  
// cliext_negate.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(-3);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 -3"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c3.begin(), cliext::negate<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 -3  
-4 3  
``` 

## <a name="not_equal_to"></a> not_equal_to (STL/CLR)
此模板类描述某个函数，当调用时，返回 true，仅当第一个参数是否不等于第二个。 使用它指定根据其自变量类型的函数对象。  
  
### <a name="syntax"></a>语法  
  
```  
template<typename Arg>  
    ref class not_equal_to  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    not_equal_to();  
    not_equal_to(not_equal_to<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>参数  
 Arg  
 参数的类型。  
  
### <a name="member-functions"></a>成员函数  
  
|类型定义|Description|  
|---------------------|-----------------|  
|delegate_type|泛型委托的类型。|  
|first_argument_type|函子的第一个自变量的类型。|  
|result_type|函子结果的类型。|  
|second_argument_type|函子的第二个自变量的类型。|  
  
|成员|Description|  
|------------|-----------------|  
|not_equal_to|构造函数。|  
  
|运算符|Description|  
|--------------|-----------------|  
|operator()|计算所需的函数。|  
|运算符 delegate_type ^|强制转换为委托的函子。|  
  
### <a name="remarks"></a>备注  
 此模板类描述两个参数函子。 它定义了成员运算符`operator()`以便为函数调用时对象，它将返回 true 仅第一个参数是否不等于第二个。  
  
 你还可以作为其类型函数自变量传递对象`delegate_type^`和它将会相应地进行转换。  
  
### <a name="example"></a>示例  
  
```cpp  
// cliext_not_equal_to.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c2;   
    c2.push_back(4);   
    c2.push_back(4);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 4 4"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::not_equal_to<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
4 4  
0 1  
```   

## <a name="not1"></a> not1 (STL/CLR)
生成`unary_negate`函子的。  
  
### <a name="syntax"></a>语法  
  
```  
template<typename Fun>  
    unary_negate<Fun> not1(Fun% functor);  
```  
  
#### <a name="template-parameters"></a>模板参数  
 有趣  
 函子的类型。  
  
#### <a name="function-parameters"></a>函数参数  
 函子  
 包装函数。  
  
### <a name="remarks"></a>备注  
 模板函数返回[unary_negate (STL/CLR)](../dotnet/unary-negate-stl-clr.md)`<Fun>(functor)`。 您将其用作将单自变量函子包装在提供其逻辑非函子的简便方法。  
  
### <a name="example"></a>示例  
  
```cpp  
// cliext_not1.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(0);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 0"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::logical_not<int> not_op;   
  
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        cliext::unary_negate<cliext::logical_not<int> >(not_op));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display with function   
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        cliext::not1(not_op));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 0  
1 0  
1 0  
```  

## <a name="not2"></a> not2 (STL/CLR)
生成`binary_negate`函子的。  
  
### <a name="syntax"></a>语法  
  
```  
template<typename Fun>  
    binary_negate<Fun> not2(Fun% functor);  
```  
  
#### <a name="template-parameters"></a>模板参数  
 有趣  
 函子的类型。  
  
#### <a name="function-parameters"></a>函数参数  
 函子  
 包装函数。  
  
### <a name="remarks"></a>备注  
 模板函数返回[binary_negate (STL/CLR)](../dotnet/binary-negate-stl-clr.md)`<Fun>(functor)`。 你将它用作一种简便方式将两个参数函子包装在提供其逻辑非函子。  
  
### <a name="example"></a>示例  
  
```cpp  
// cliext_not2.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c2;   
    c2.push_back(4);   
    c2.push_back(4);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 4 4"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::less<int> less_op;   
  
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(),   
        cliext::binary_negate<cliext::less<int> >(less_op));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display with function   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::not2(less_op));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
4 4  
1 0  
1 0  
```  

## <a name="plus"></a> 加 (STL/CLR)
此模板类描述某个函数，当调用时，返回的第一个参数包括第二个。 使用它指定根据其自变量类型的函数对象。  
  
### <a name="syntax"></a>语法  
  
```  
template<typename Arg>  
    ref class plus  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef Arg result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    plus();  
    plus(plus<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>参数  
 Arg  
 参数和返回值的类型。  
  
### <a name="member-functions"></a>成员函数  
  
|类型定义|Description|  
|---------------------|-----------------|  
|delegate_type|泛型委托的类型。|  
|first_argument_type|函子的第一个自变量的类型。|  
|result_type|函子结果的类型。|  
|second_argument_type|函子的第二个自变量的类型。|  
  
|成员|Description|  
|------------|-----------------|  
|plus|构造函数。|  
  
|运算符|Description|  
|--------------|-----------------|  
|operator()|计算所需的函数。|  
|运算符 delegate_type ^|强制转换为委托的函子。|  
  
### <a name="remarks"></a>备注  
 此模板类描述两个参数函子。 它定义了成员运算符`operator()`以便为函数调用时对象，它将返回第一个自变量以及第二个。  
  
 你还可以作为其类型函数自变量传递对象`delegate_type^`和它将会相应地进行转换。  
  
### <a name="example"></a>示例  
  
```cpp  
// cliext_plus.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c2;   
    c2.push_back(2);   
    c2.push_back(1);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 2 1"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::plus<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
2 1  
6 4  
```  

## <a name="unary_delegate"></a> unary_delegate (STL/CLR)
Genereic 类描述一个单参数的委托。 使用它指定根据其自变量和返回类型的委托。  
  
### <a name="syntax"></a>语法  
  
```  
generic<typename Arg,  
    typename Result>  
    delegate Result unary_delegate(Arg);  
```  
  
#### <a name="parameters"></a>参数  
 Arg  
 参数类型。  
  
 结果  
 返回类型。  
  
### <a name="remarks"></a>备注  
 Genereic 委托介绍了一个自变量的函数。  
  
 请注意，对于：  
  
 `unary_delegare<int, int> Fun1;`  
  
 `unary_delegare<int, int> Fun2;`  
  
 类型`Fun1`和`Fun2`是同义词，而为：  
  
 `delegate int Fun1(int);`  
  
 `delegate int Fun2(int);`  
  
 它们不是同一类型。  
  
### <a name="example"></a>示例  
  
```cpp  
// cliext_unary_delegate.cpp   
// compile with: /clr   
#include <cliext/functional>   
  
int hash_val(wchar_t val)   
    {   
    return ((val * 17 + 31) % 67);   
    }   
  
typedef cliext::unary_delegate<wchar_t, int> Mydelegate;   
int main()   
    {   
    Mydelegate^ myhash = gcnew Mydelegate(&hash_val);   
  
    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));   
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));   
    return (0);   
    }  
  
```  
  
```Output  
hash(L'a') = 5  
hash(L'b') = 22  
```  

## <a name="unary_delegate_noreturn"></a> unary_delegate_noreturn (STL/CLR)
Genereic 类描述一个自变量委托，可返回`void`。 使用它指定根据其自变量类型的委托。  
  
### <a name="syntax"></a>语法  
  
```  
generic<typename Arg>  
    delegate void unary_delegate_noreturn(Arg);  
```  
  
#### <a name="parameters"></a>参数  
 Arg  
 自变量类型。  
  
### <a name="remarks"></a>备注  
 Genereic 委托描述返回的单自变量函数`void`。  
  
 请注意，对于：  
  
 `unary_delegare_noreturn<int> Fun1;`  
  
 `unary_delegare_noreturn<int> Fun2;`  
  
 类型`Fun1`和`Fun2`是同义词，而为：  
  
 `delegate void Fun1(int);`  
  
 `delegate void Fun2(int);`  
  
 它们不是同一类型。  
  
### <a name="example"></a>示例  
  
```cpp  
// cliext_unary_delegate_noreturn.cpp   
// compile with: /clr   
#include <cliext/functional>   
  
void hash_val(wchar_t val)   
    {   
    System::Console::WriteLine("hash({0}) = {1}",   
       val, (val * 17 + 31) % 67);   
    }   
  
typedef cliext::unary_delegate_noreturn<wchar_t> Mydelegate;   
int main()   
    {   
    Mydelegate^ myhash = gcnew Mydelegate(&hash_val);   
  
    myhash(L'a');   
    myhash(L'b');   
    return (0);   
    }  
  
```  
  
```Output  
hash(a) = 5  
hash(b) = 22  
```  

## <a name="unary_negate"></a> unary_negate (STL/CLR)
此模板类描述某个函数，当调用，返回的逻辑不其存储的单自变量函子。 使用它指定根据其存储的函子的函数对象。  
  
### <a name="syntax"></a>语法  
  
```  
template<typename Fun>  
    ref class unary_negate  
    { // wrap operator()  
public:  
    typedef Fun stored_function_type;  
    typedef typename Fun::argument_type argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<  
        argument_type, result_type>  
        delegate_type;  
  
    unary_negate(Fun% functor);  
    unary_negate(unary_negate<Fun>% right);  
  
    result_type operator()(argument_type left);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>参数  
 有趣  
 存储函子的类型。  
  
### <a name="member-functions"></a>成员函数  
  
|类型定义|Description|  
|---------------------|-----------------|  
|argument_type|伪函数自变量的类型。|  
|delegate_type|泛型委托的类型。|  
|result_type|函子结果的类型。|  
  
|成员|Description|  
|------------|-----------------|  
|unary_negate|构造函数。|  
  
|运算符|Description|  
|--------------|-----------------|  
|operator()|计算所需的函数。|  
|delegate_type ^|强制转换为委托的函子。|  
  
### <a name="remarks"></a>备注  
 此模板类描述存储另一个单自变量函子的单自变量伪函数。 它定义了成员运算符`operator()`以便为函数调用时对象，它将返回逻辑的存储函子的不使用参数调用。  
  
 你还可以作为其类型函数自变量传递对象`delegate_type^`和它将会相应地进行转换。  
  
### <a name="example"></a>示例  
  
```cpp  
// cliext_unary_negate.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(0);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 0"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::logical_not<int> not_op;   
  
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        cliext::unary_negate<cliext::logical_not<int> >(not_op));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display with function   
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        cliext::not1(not_op));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 0  
1 0  
1 0  
```  