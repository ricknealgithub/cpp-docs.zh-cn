---
title: binder2nd 类 | Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::binder2nd
dev_langs:
- C++
helpviewer_keywords:
- binder2nd class
ms.assetid: b2a9c1d1-dfc4-4ca9-a10e-ae84e195a62d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbd2f2c652c619a954b789a3b765fc636a03c33e
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "38962719"
---
# <a name="binder2nd-class"></a>binder2nd 类

一种模板类，用于提供构造函数，通过将二元函数的第二个自变量绑定到指定的值，将二元函数对象转换为一元函数对象。

## <a name="syntax"></a>语法

```cpp
template <class Operation>
class binder2nd
    : public unaryFunction <typename Operation::first_argument_type,
    typename Operation::result_type>
{
public:
    typedef typename Operation::argument_type argument_type;
    typedef typename Operation::result_type result_type;
    binder2nd(
        const Operation& Func,
        const typename Operation::second_argument_type& right);

    result_type operator()(const argument_type& left) const;
    result_type operator()(argument_type& left) const;

protected:
    Operation op;
    typename Operation::second_argument_type value;
};
```

### <a name="parameters"></a>参数

*func*二元函数对象转换为一元函数对象。

*右*二元函数对象的第二个参数是要绑定的值。

*左*改编的二元对象将与第二个参数的固定值进行比较的参数的值。

## <a name="return-value"></a>返回值

将二元函数对象的第二个参数绑定到值而得出的一元函数对象*右*。

## <a name="remarks"></a>备注

此模板类存储一份二元函数对象 _ *Func*中`op`，以及一份*右*中`value`。 它将其成员函数 `operator()` 定义为返回 **op**( `left`, **value**)。

如果`Func`是类型的对象`Operation`和 c 是常量，则[bind2nd](../standard-library/functional-functions.md#bind2nd) ( `Func`， `c` ) 等效于`binder2nd`类构造函数`binder2nd` \< **操作**> ( `Func`， `c` ) 且更为方便。

## <a name="example"></a>示例

```cpp
// functional_binder2nd.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 5; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( ";
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    // Count the number of integers > 10 in the vector
    vector<int>::iterator::difference_type result1;
    result1 = count_if(v1.begin(), v1.end(),
        binder2nd<greater<int> >(greater<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1 << "." << endl;

    // Compare using binder1st fixing 1st argument:
    // count the number of integers < 10 in the vector
    vector<int>::iterator::difference_type result2;
    result2 = count_if(v1.begin(), v1.end(),
        binder1st<greater<int> >(greater<int>(), 10));
    cout << "The number of elements in v1 less than 10 is: "
         << result2 << "." << endl;
}
/* Output:
The vector v1 = ( 0 5 10 15 20 25 )
The number of elements in v1 greater than 10 is: 3.
The number of elements in v1 less than 10 is: 2.
*/
```

## <a name="requirements"></a>要求

**标头：**\<functional>

**命名空间：** std

## <a name="see-also"></a>请参阅

[C++ 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 标准库参考](../standard-library/cpp-standard-library-reference.md)<br/>
