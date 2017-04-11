---
title: "编译器警告 （等级 3） C4996 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4996
dev_langs:
- C++
helpviewer_keywords:
- C4996
ms.assetid: 926c7cc2-921d-43ed-ae75-634f560dd317
caps.latest.revision: 34
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: b790beb88de009e1c7161f3c9af6b3e21c22fd8e
ms.openlocfilehash: aa9586bd0abed0b1fa1d24c777eea8c82c5cedc0
ms.lasthandoff: 03/29/2017

---
# <a name="compiler-warning-level-3-c4996"></a>编译器警告 （等级 3） C4996
编译器遇到弃用声明。  
  
 此警告或错误有几种可能的含义。  
  
 `C4996`当编译器遇到函数或变量的标记为时发生[弃用](../../cpp/deprecated-cpp.md)。 多个函数、成员函数、模板函数和 Visual Studio 的库中的全局变量标记为已弃用。 这些函数可能具有不同的首选名称，可能不安全或具有更加安全的变体，或可能已过时。 错误消息可能包括已弃用函数或全局变量的建议替换项。 你可以关闭此警告与[警告](../../preprocessor/warning.md)杂注或**/wd4996**命令行选项。 你也可以使用预处理器宏关闭弃用警告的某些类。 

当您尝试访问函数、 类成员或具有 C + + 14 的 typedef 时，还将发出此警告`[[deprecated]]`属性。 有关详细信息，请参阅[c + + 标准特性](../../cpp/attributes2.md)。 
  
 **此项的 POSIX 名称已弃用。请改用 ISO C 和 c + + 一致的名称︰** new_name**。请参阅联机帮助了解详细信息。**  
  
 CRT 中的一些 POSIX 函数已重命名，以符合适用于实现定义的全局函数名称的 C99 和 C++03 规则。 在大多数情况下，前导下划线已添加到 POSIX 函数名称，以创建符合标准的名称。 编译器会发出对原始函数名称的弃用警告，并建议首选名称。 仅会弃用原始名称，而不会弃用函数本身。 若要关闭这些函数的弃用警告，请定义预处理器宏 **_CRT_NONSTDC_NO_WARNINGS**。 你可以通过包括选项 `/D_CRT_NONSTDC_NO_WARNINGS`在命令行定义此宏。 若要在 Visual Studio 中定义此宏，请打开项目的  “属性页”对话框。 展开“配置属性” 、“C/C++” 、“预处理器” 。 在“预处理器定义” 中，添加 `_CRT_NONSTDC_NO_WARNINGS`。 选择“确定”  进行保存，然后重新生成项目。 若要仅在特定源文件中定义此宏，请将行 `#define _CRT_NONSTDC_NO_WARNINGS` 添加到包括标头文件的任意行之前。  
  
 **此函数或变量可能不安全。请考虑使用**safe_version**相反。若要禁用弃用，请使用 _CRT_SECURE_NO_WARNINGS。请参阅联机帮助了解详细信息。**  
  
 新的、 更安全的函数已弃用某些 CRT 和 c + + 标准库函数和全局变量。 编译器会发出对这些函数的弃用警告，并建议首选函数。 若要在 CRT 中关闭这些函数的弃用警告，请定义 **_CRT_SECURE_NO_WARNINGS**。 若要关闭有关弃用的全局变量的警告，请定义 **_CRT_SECURE_NO_WARNINGS_GLOBALS**。 有关这些不推荐使用的函数和全局变量的详细信息，请参阅[CRT 中的安全功能](../../c-runtime-library/security-features-in-the-crt.md)和[安全库︰ c + + 标准库](../../standard-library/safe-libraries-cpp-standard-library.md)。  
  
 **具有参数，可能不安全的参数的函数调用此调用依靠调用方检查传递的值正确。若要禁用此警告，请使用 -D_SCL_SECURE_NO_WARNINGS。有关如何使用 Visual c + + 检查迭代器，请参阅文档**  
  
 某些 C++ 标准库模板函数不会检查参数的正确性。 此警告有助于标识这些函数的用法。 若要关闭这些函数的警告，请定义 **_SCL_SECURE_NO_WARNINGS**。 有关详细信息，请参阅[经过检查的迭代器](../../standard-library/checked-iterators.md)。  
  
 **此函数或变量已被较新的库或操作系统功能取代。请考虑使用**new_item**相反。请参阅联机帮助了解详细信息。**  
  
 某些库函数和全局变量由于过时已弃用。 可能会在未来版本的库中删除这些函数和变量。 编译器会发出对这些项的弃用警告，并建议首选备用项。 若要关闭这些项的弃用警告，请定义 **_CRT_OBSOLETE_NO_WARNINGS**。 有关详细信息，请参阅弃用的函数或变量的文档。  
  
 **在 MFC 或 ATL 代码中的各种消息**  
  
 如果出于安全原因使用了否决的 MFC 或 ATL 函数，也可能发生 `C4996`。 若要禁止显示这些警告，请参阅[_afx_secure_no_warnings，则](http://msdn.microsoft.com/Library/97dcfd41-1e56-41d5-bf7e-d240b950134b)和[_ATL_SECURE_NO_WARNINGS](http://msdn.microsoft.com/Library/587d29d8-a75a-44a3-bec8-f724087e5e73)。  
  
 **CLR 代码中的封送处理错误**  
  
 在使用封送处理库时也可能会发生 `C4996`。 在这种情况下，C4996 是错误，而非警告。 当你使用时，将出现此错误[marshal_as](../../dotnet/marshal-as.md)需要的两个数据类型之间进行转换[marshal_context 类](../../dotnet/marshal-context-class.md)。 如果封送处理库不支持转换，您也会收到此错误。 有关封送处理库的详细信息，请参阅[概述的封送处理在 c + +](../../dotnet/overview-of-marshaling-in-cpp.md)。  
  
 **生成 C4996 的示例**  
  
 在第一个示例中，为在其中声明了函数的行和在其中使用了函数的行生成 `C4996` 。  
  
## <a name="example"></a>示例  
 以下示例生成 C4996。  
  
```cpp  
// C4996.cpp  
// compile with: /W3  
// C4996 warning expected  
#include <stdio.h>  
  
// #pragma warning(disable : 4996)  
void func1(void) {  
   printf_s("\nIn func1");  
}  
  
__declspec(deprecated) void func1(int) {  
   printf_s("\nIn func2");  
}  
  
int main() {  
   func1();  
   func1(1);  
}  
```  
  
## <a name="example"></a>示例  
 如果在使用定义的 `_ITERATOR_DEBUG_LEVEL` （对于调试模式生成，默认情况下设置为 1）进行编译时未使用经过检查的迭代器，也可能发生 C4996。  有关详细信息，请参阅[经过检查的迭代器](../../standard-library/checked-iterators.md)。  
  
 下面的 c + + 标准库代码示例生成 C4996。  
  
```cpp  
// C4996_b.cpp  
// compile with: /EHsc /W3 /c  
#define _ITERATOR_DEBUG_LEVEL 1  
  
#include <algorithm>  
#include <iterator>  
  
using namespace std;  
using namespace stdext;  
  
int main() {  
    int a[] = { 1, 2, 3 };  
    int b[] = { 10, 11, 12 };  
    copy(a, a + 3, b + 1);   // C4996  
    // try the following line instead  
    //   copy(a, a + 3, b);  
    copy(a, a + 3, checked_array_iterator<int *>(b, 3));   // OK  
}  
  
```  
  
## <a name="example"></a>示例  
 下面的 c + + 标准库代码示例生成 C4996 作为警告。 注释是内联的。  
  
```cpp  
#include <algorithm>  
#include <array>  
#include <iostream>  
#include <iterator>  
#include <numeric>  
#include <string>  
#include <vector>  
  
using namespace std;  
  
template <typename C> void print(const string& s, const C& c) {  
    cout << s;  
  
    for (const auto& e : c) {  
        cout << e << " ";  
    }  
  
    cout << endl;  
}  
  
int main()  
{  
    vector<int> v(16);  
    iota(v.begin(), v.end(), 0);  
    print("v: ", v);  
  
    // OK: vector::iterator is checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    vector<int> v2(16);  
    transform(v.begin(), v.end(), v2.begin(), [](int n) { return n * 2; });  
    print("v2: ", v2);  
  
    // OK: back_insert_iterator is marked as checked in debug mode  
    // (i.e. an overrun is impossible)  
    vector<int> v3;  
    transform(v.begin(), v.end(), back_inserter(v3), [](int n) { return n * 3; });  
    print("v3: ", v3);  
  
    // OK: array::iterator is checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    array<int, 16> a4;  
    transform(v.begin(), v.end(), a4.begin(), [](int n) { return n * 4; });  
    print("a4: ", a4);  
  
    // OK: Raw arrays are checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    // NOTE: This applies only when raw arrays are given to C++ Standard Library algorithms!  
    int a5[16];  
    transform(v.begin(), v.end(), a5, [](int n) { return n * 5; });  
    print("a5: ", a5);  
  
    // WARNING C4996: Pointers cannot be checked in debug mode  
    // (i.e. an overrun will trigger undefined behavior)  
    int a6[16];  
    int * p6 = a6;  
    transform(v.begin(), v.end(), p6, [](int n) { return n * 6; });  
    print("a6: ", a6);  
  
    // OK: stdext::checked_array_iterator is checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    int a7[16];  
    int * p7 = a7;  
    transform(v.begin(), v.end(), stdext::make_checked_array_iterator(p7, 16), [](int n) { return n * 7; });  
    print("a7: ", a7);  
  
    // WARNING SILENCED: stdext::unchecked_array_iterator is marked as checked in debug mode  
    // (i.e. it performs no checking, so an overrun will trigger undefined behavior)  
    int a8[16];  
    int * p8 = a8;  
    transform(v.begin(), v.end(), stdext::make_unchecked_array_iterator(p8), [](int n) { return n * 8; });  
    print("a8: ", a8);  
}  
  
```  
  
## <a name="example"></a>示例  
 下面的示例生成 C4996，因为封送处理库需要上下文才能从 `System::String` 转换为 `const char *`。  
  
```cpp  
// C4996_Marshal.cpp  
// compile with: /clr   
// C4996 expected  
#include <stdlib.h>  
#include <string.h>  
#include <msclr\marshal.h>  
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {  
   String^ message = gcnew String("Test String to Marshal");  
   const char* result;  
   result = marshal_as<const char*>( message );  
   return 0;  
}  
```