---
title: '&lt;new&gt; 运算符 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- new/std::operator delete
- new/std::operator new
ms.assetid: d1af4b56-9a95-4c65-ab01-bf43e982c7bd
ms.openlocfilehash: 5f21ec03bd36d889c6fbd8d24a2726fb7f18024f
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "38956106"
---
# <a name="ltnewgt-operators"></a>&lt;new&gt; 运算符

||||
|-|-|-|
|[运算符 delete](#op_delete)|[运算符 delete[]](#op_delete_arr)|[运算符 new](#op_new)|
|[运算符 new[]](#op_new_arr)|

## <a name="op_delete"></a>运算符 delete

由 delete 表达式调用来解除单个对象的存储空间分配的函数。

```cpp
void operator delete(void* ptr) throw();

void operator delete(void *,
    void*) throw();

void operator delete(void* ptr,
    const std::nothrow_t&) throw();
```

### <a name="parameters"></a>参数

*ptr*其值将呈现无效的删除操作的指针。

### <a name="remarks"></a>备注

第一个函数调用由 delete 表达式的值呈现*ptr*无效。 该程序可以通过替换 C++ 标准库定义的默认版本的函数签名定义函数。 所需的行为就是接受的值*ptr* ，它是 null 或返回到以前通过调用[运算符 new](../standard-library/new-operators.md#op_new)(**size_t**)。

Null 值的默认行为*ptr*是不执行任何操作。 任何其他值*ptr*必须按前面所述的调用之前返回的值。 此类非 null 的值的默认行为*ptr*是回收早期调用分配的存储空间。 未指定在什么条件下部分或全部此类回收的存储分配到的后续调用`operator new`(**size_t**)，或任何`calloc`( **size_t**)， `malloc`( **size_t**)，或`realloc`( **void\***， **size_t**)。

第二个函数由对应于 **new**( **std::size_t**) 形式的新表达式的 placement delete 表达式调用。 它不执行任何操作。

第三个函数由对应于 **new**( **std::size_t**, **conststd::nothrow_t&**) 形式的新表达式的 placement delete 表达式调用。 该程序可以通过替换 C++ 标准库定义的默认版本的函数签名定义函数。 所需行为接受 `ptr` 的值，该值为 NULL 或由对 `operator new`(**size_t**) 的早期调用返回。 默认行为是评估**删除**(`ptr`)。

### <a name="example"></a>示例

请参阅[运算符 new](../standard-library/new-operators.md#op_new)有关的示例，使用**运算符 delete**。

## <a name="op_delete_arr"></a>运算符 delete[]

由 delete 表达式调用来解除对象数组的存储空间分配的函数。

```cpp
void operator delete[](void* ptr) throw();

void operator delete[](void *,
    void*) throw();

void operator delete[](void* ptr,
    const std::nothrow_t&) throw();
```

### <a name="parameters"></a>参数

*ptr*其值将呈现无效的删除操作的指针。

### <a name="remarks"></a>备注

第一个函数调用`delete[]`表达式的值呈现*ptr*无效。 该函数为可替换，因为该程序可以通过替换 C++ 标准库定义的默认版本的函数签名定义函数。 所需的行为就是接受的值*ptr* ，它是 null 或返回到以前通过调用[new 运算符&#91;&#93;](../standard-library/new-operators.md#op_new_arr)(**size_t**)。 Null 值的默认行为*ptr*是不执行任何操作。 任何其他值*ptr*必须按前面所述的调用之前返回的值。 此类非 null 的值的默认行为*ptr*是回收早期调用分配的存储空间。 未指定在什么条件下部分或全部此类回收的存储分配到的后续调用[运算符 new](../standard-library/new-operators.md#op_new)(**size_t**)，或任何`calloc`(**size_t**)， `malloc`(**size_t**)，或`realloc`( **void\***， **size_t**)。

第二个函数调用的 placement`delete[]`表达式对应于`new[]`形式的表达式`new[]`(**std:: size_t**)。 它不执行任何操作。

第三个函数由对应于 `new[]`( **std::size_t**, **const std::nothrow_t&**) 形式的 `new[]` 表达式的 placement delete 表达式调用。 该程序可以通过替换 C++ 标准库定义的默认版本的函数签名定义函数。 所需的行为就是接受的值*ptr* ，它是运算符的早期调用返回 null 或`new[]`(**size_t**)。 默认行为是评估 `delete[]`( `ptr`)。

### <a name="example"></a>示例

有关 `operator delete[]` 的使用示例，请参阅[运算符 new&#91;&#93;](../standard-library/new-operators.md#op_new_arr)。

## <a name="op_new"></a>运算符 new

由 new 表达式调用来为单个对象分配存储空间的函数。

```cpp
void* operator new(std::size_t count) throw(bad_alloc);

void* operator new(std::size_t count,
    const std::nothrow_t&) throw();

void* operator new(std::size_t count,
    void* ptr) throw();
```

### <a name="parameters"></a>参数

*计数*存储并将其分配的字节数。

*ptr*要返回的指针。

### <a name="return-value"></a>返回值

指向新分配内存的最小字节地址的指针。 或者*ptr*。

### <a name="remarks"></a>备注

第一个函数由 new 表达式调用，以便分配 `count` 个字节的存储，适当对齐该存储以表示该大小的任何对象。 该程序可以通过替换 C++ 标准库定义的默认版本的函数签名定义 alternate 函数，因此该程序为可替换。

仅在按照请求分配存储时，所需的行为才为返回非空指针。 每个此类分配都会向不与任何其他已分配的存储连接的存储生成指针。 未指定连续调用分配的存储的顺序和连续性。 未指定存储的初始值。 返回的指针指向已分配的存储的开始（最小字节地址）。 如果计数为零，则返回的值不与该函数返回的任何其他值相等。

默认行为是执行一个循环。 在此循环中，该函数会首先尝试分配请求的存储。 未指定该尝试是否涉及调用 `malloc`( **size_t**)。 如果尝试成功，则该函数将返回已分配存储的指针。 否则，该函数将调用指定的[新处理程序](../standard-library/new-typedefs.md#new_handler)。 返回被调用的函数时，将重复该循环。 尝试分配请求的存储成功时或未返回被调用的函数时，循环将终止。

新处理程序所需的行为是执行以下操作之一：

- 使更多存储可用于分配，然后返回。

- 调用**中止**或**退出**(`int`)。

- 引发一个 **bad_alloc** 类型的对象。

[新处理程序](../standard-library/new-typedefs.md#new_handler)的默认行为是引发一个 `bad_alloc` 类型的对象。 空指针指定新的默认处理程序。

顺序和连续性通过连续调用分配的存储`operator new`(**size_t**) 未指定，因为初始值存储在此处。

第一个函数由 placement new 表达式调用，以便分配 `count` 个字节的存储，适当对齐该存储以表示该大小的任何对象。 该程序可以通过替换 C++ 标准库定义的默认版本的函数签名定义 alternate 函数，因此该程序为可替换。

默认行为是返回`operator new`(`count`) 如果该函数成功。 否则，它返回空指针。

第三个函数由 **new** ( *args*) T 形式的 placement **new** 表达式调用。此处，*args* 包含单个对象指针。 这可用于构造已知地址的对象。 该函数返回 *ptr*。

若要释放分配的存储**运算符 new**，调用[运算符 delete](../standard-library/new-operators.md#op_delete)。

有关 new 的引发或非引发行为的信息，请参阅 [new 和 delete 运算符](../cpp/new-and-delete-operators.md)。

### <a name="example"></a>示例

```cpp
// new_op_new.cpp
// compile with: /EHsc
#include<new>
#include<iostream>

using namespace std;

class MyClass
{
public:
   MyClass( )
   {
      cout << "Construction MyClass." << this << endl;
   };

   ~MyClass( )
   {
      imember = 0; cout << "Destructing MyClass." << this << endl;
   };
   int imember;
};

int main( )
{
   // The first form of new delete
   MyClass* fPtr = new MyClass;
   delete fPtr;

   // The second form of new delete
   MyClass* fPtr2 = new( nothrow ) MyClass;
   delete fPtr2;

   // The third form of new delete
   char x[sizeof( MyClass )];
   MyClass* fPtr3 = new( &x[0] ) MyClass;
   fPtr3 -> ~MyClass();
   cout << "The address of x[0] is : " << ( void* )&x[0] << endl;
}
```

## <a name="op_new_arr"></a>operator new[]

由 new 表达式调用来为对象数组分配存储空间的分配函数。

```cpp
void* operator new[](std::size_t count) throw(std::bad_alloc);

void* operator new[](std::size_t count,
    const std::nothrow_t&) throw();

void* operator new[](std::size_t count,
    void* ptr) throw();
```

### <a name="parameters"></a>参数

*计数*存储为数组对象分配的字节数。

*ptr*要返回的指针。

### <a name="return-value"></a>返回值

指向新分配内存的最小字节地址的指针。 或者*ptr*。

### <a name="remarks"></a>备注

第一个函数由 `new[]` 表达式调用，以便分配 `count` 个字节的存储，适当对齐该存储以表示该大小或更小的任何数组对象。 该程序可以通过替换 C++ 标准库定义的默认版本的函数签名定义函数。 所需的行为是相同[运算符 new](../standard-library/new-operators.md#op_new)(**size_t**)。 默认行为是返回 `operator new`( `count`)。

第二个函数由 placement `new[]` 表达式调用，以便分配 `count` 个字节的存储，适当对齐该存储以表示该大小的任何数组对象。 该程序可以通过替换 C++ 标准库定义的默认版本的函数签名定义函数。 默认行为是返回**operatornew**(`count`) 如果该函数成功。 否则，它返回空指针。

第三个函数由 **new** ( *args*) **T**[ **N**] 形式的 placement `new[]` 函数调用。 此处，*args* 包含单个对象指针。 该函数返回 `ptr`。

若要释放 `operator new[]` 分配的存储，请调用[运算符 delete&#91;&#93;](../standard-library/new-operators.md#op_delete_arr)。

有关 new 的引发或非引发行为的信息，请参阅 [new 和 delete 运算符](../cpp/new-and-delete-operators.md)。

### <a name="example"></a>示例

```cpp
// new_op_alloc.cpp
// compile with: /EHsc
#include <new>
#include <iostream>

using namespace std;

class MyClass {
public:
   MyClass() {
      cout << "Construction MyClass." << this << endl;
   };

   ~MyClass() {
      imember = 0; cout << "Destructing MyClass." << this << endl;
      };
   int imember;
};

int main() {
   // The first form of new delete
   MyClass* fPtr = new MyClass[2];
   delete[ ] fPtr;

   // The second form of new delete
   char x[2 * sizeof( MyClass ) + sizeof(int)];

   MyClass* fPtr2 = new( &x[0] ) MyClass[2];
   fPtr2[1].~MyClass();
   fPtr2[0].~MyClass();
   cout << "The address of x[0] is : " << ( void* )&x[0] << endl;

   // The third form of new delete
   MyClass* fPtr3 = new( nothrow ) MyClass[2];
   delete[ ] fPtr3;
}
```

## <a name="see-also"></a>请参阅

[\<new>](../standard-library/new.md)<br/>
