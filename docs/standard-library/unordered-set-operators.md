---
title: '&lt;unordered_set&gt; 运算符 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- unordered_set/std::operator!=
- unordered_set/std::operator==
dev_langs:
- C++
ms.assetid: 8653eea6-12f2-4dd7-aa2f-db38a71599a0
ms.openlocfilehash: 6edd8cb33aaf5cc90ead3a3d327f8222e4410443
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "38962304"
---
# <a name="ltunorderedsetgt-operators"></a>&lt;unordered_set&gt; 运算符

|||||
|-|-|-|-|
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|[operator!=](#op_neq_unordered_multiset)|[operator==](#op_eq_eq_unordered_multiset)|

## <a name="op_neq"></a>operator!=

测试位于运算符左侧的 [unordered_set](../standard-library/unordered-set-class.md) 对象是否与位于右侧的 unordered_set 对象不相等。

```cpp
bool operator!=(const unordered_set <Key, Hash, Pred, Allocator>& left, const unordered_set <Key, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>参数

*left*  
 一个 `unordered_set` 类型的对象。

*right*  
 一个 `unordered_set` 类型的对象。

### <a name="return-value"></a>返回值

**true**如果 unordered_set 不相等，则**false**如果它们相等。

### <a name="remarks"></a>备注

在其中存储元素的二元顺序不会影响 unordered_set 对象之间的比较。 如果两个 unordered_set 具有相同的元素数，并且一个容器中的元素是另一个容器中的元素的排列，则这两个 unordered_set 相等。 否则，它们不相等。

### <a name="example"></a>示例

```cpp
// unordered_set_ne.cpp
// compile by using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_set>
#include <iostream>
#include <ios>

int main()
{
    using namespace std;

    unordered_set<char> c1, c2, c3;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    c2.insert('c');
    c2.insert('a');
    c2.insert('d');

    c3.insert('c');
    c3.insert('a');
    c3.insert('b');

   cout << boolalpha;
   cout << "c1 != c2: " << (c1 != c2) << endl;
   cout << "c1 != c3: " << (c1 != c3) << endl;
   cout << "c2 != c3: " << (c2 != c3) << endl;

    return (0);
}

```

**输出：**

`c1 != c2: true`

`c1 != c3: false`

`c2 != c3: true`

## <a name="op_eq_eq"></a>operator==

测试位于运算符左侧的 [unordered_set](../standard-library/unordered-set-class.md) 对象是否与位于右侧的 unordered_set 对象相等。

```cpp
bool operator==(const unordered_set <Key, Hash, Pred, Allocator>& left, const unordered_set <Key, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>参数

*left*  
 一个 `unordered_set` 类型的对象。

*right*  
 一个 `unordered_set` 类型的对象。

### <a name="return-value"></a>返回值

**true**如果 unordered_set 相等，则**false**如果它们不相等。

### <a name="remarks"></a>备注

在其中存储元素的二元顺序不会影响 unordered_set 对象之间的比较。 如果两个 unordered_set 具有相同的元素数，并且一个容器中的元素是另一个容器中的元素的排列，则这两个 unordered_set 相等。 否则，它们不相等。

### <a name="example"></a>示例

```cpp
// unordered_set_eq.cpp
// compile by using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_set>
#include <iostream>
#include <ios>

int main()
{
    using namespace std;

    unordered_set<char> c1, c2, c3;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    c2.insert('c');
    c2.insert('a');
    c2.insert('d');

    c3.insert('c');
    c3.insert('a');
    c3.insert('b');

   cout << boolalpha;
   cout << "c1 == c2: " << (c1 == c2) << endl;
   cout << "c1 == c3: " << (c1 == c3) << endl;
   cout << "c2 == c3: " << (c2 == c3) << endl;

    return (0);
}

```

**输出：**

`c1 == c2: false`

`c1 == c3: true`

`c2 == c3: false`

## <a name="op_neq_unordered_multiset"></a>operator!=

测试位于运算符左侧的 [unordered_multiset](../standard-library/unordered-multiset-class.md) 对象是否与位于右侧的 unordered_multiset 对象不相等。

```cpp
bool operator!=(const unordered_multiset <Key, Hash, Pred, Allocator>& left, const unordered_multiset <Key, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>参数

*left*  
 一个 `unordered_multiset` 类型的对象。

*right*  
 一个 `unordered_multiset` 类型的对象。

### <a name="return-value"></a>返回值

**true**如果 unordered_multiset 不相等，则**false**如果它们相等。

### <a name="remarks"></a>备注

在其中存储元素的二元顺序不会影响 unordered_multiset 对象之间的比较。 如果两个 unordered_multiset 具有相同的元素数，并且一个容器中的元素是另一个容器中的元素的排列，则这两个 unordered_multiset 相等。 否则，它们不相等。

### <a name="example"></a>示例

```cpp
// unordered_multiset_ne.cpp
// compile by using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_set>
#include <iostream>
#include <ios>

int main()
{
    using namespace std;

    unordered_multiset<char> c1, c2, c3;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');
    c1.insert('c');

    c2.insert('c');
    c2.insert('c');
    c2.insert('a');
    c2.insert('d');

    c3.insert('c');
    c3.insert('c');
    c3.insert('a');
    c3.insert('b');

   cout << boolalpha;
   cout << "c1 != c2: " << (c1 != c2) << endl;
   cout << "c1 != c3: " << (c1 != c3) << endl;
   cout << "c2 != c3: " << (c2 != c3) << endl;

    return (0);
}

```

**输出：**

`c1 != c2: true`

`c1 != c3: false`

`c2 != c3: true`

## <a name="op_eq_eq_unordered_multiset"></a>operator==

测试位于运算符左侧的 [unordered_multiset](../standard-library/unordered-multiset-class.md) 对象是否与位于右侧的 unordered_multiset 对象相等。

```cpp
bool operator==(const unordered_multiset <Key, Hash, Pred, Allocator>& left, const unordered_multiset <Key, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>参数

*left*  
 一个 `unordered_multiset` 类型的对象。

*right*  
 一个 `unordered_multiset` 类型的对象。

### <a name="return-value"></a>返回值

**true**如果 unordered_multiset 相等，则**false**如果它们不相等。

### <a name="remarks"></a>备注

在其中存储元素的二元顺序不会影响 unordered_multiset 对象之间的比较。 如果两个 unordered_multiset 具有相同的元素数，并且一个容器中的元素是另一个容器中的元素的排列，则这两个 unordered_multiset 相等。 否则，它们不相等。

### <a name="example"></a>示例

```cpp
// unordered_multiset_eq.cpp
// compile by using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_set>
#include <iostream>
#include <ios>

int main()
{
    using namespace std;

    unordered_multiset<char> c1, c2, c3;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');
    c1.insert('c');

    c2.insert('c');
    c2.insert('c');
    c2.insert('a');
    c2.insert('d');

    c3.insert('c');
    c3.insert('c');
    c3.insert('a');
    c3.insert('b');

   cout << boolalpha;
   cout << "c1 == c2: " << (c1 == c2) << endl;
   cout << "c1 == c3: " << (c1 == c3) << endl;
   cout << "c2 == c3: " << (c2 == c3) << endl;

    return (0);
}

```

**输出：**

`c1 == c2: false`

`c1 == c3: true`

`c2 == c3: false`

## <a name="see-also"></a>请参阅

[<unordered_set>](../standard-library/unordered-set.md)<br/>
