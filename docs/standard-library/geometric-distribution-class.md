---
title: "geometric_distribution 类 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- geometric_distribution
- std::geometric_distribution
- random/std::geometric_distribution
- std::geometric_distribution::reset
- random/std::geometric_distribution::reset
- std::geometric_distribution::p
- random/std::geometric_distribution::p
- std::geometric_distribution::param
- random/std::geometric_distribution::param
- std::geometric_distribution::min
- random/std::geometric_distribution::min
- std::geometric_distribution::max
- random/std::geometric_distribution::max
- std::geometric_distribution::operator()
- random/std::geometric_distribution::operator()
- std::geometric_distribution::param_type
- random/std::geometric_distribution::param_type
- std::geometric_distribution::param_type::p
- random/std::geometric_distribution::param_type::p
- std::geometric_distribution::param_type::operator==
- random/std::geometric_distribution::param_type::operator==
- std::geometric_distribution::param_type::operator!=
- random/std::geometric_distribution::param_type::operator!=
dev_langs:
- C++
helpviewer_keywords:
- geometric_distribution class
- geometric_distribution
ms.assetid: 38f933af-3b49-492e-9d26-b6b272a60013
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 02dd887f1b20b42145ccc83165570b9f682e693c
ms.openlocfilehash: 51952b8649f73120b6a017ae9b64e3e01f42f70e
ms.lasthandoff: 02/24/2017

---
# <a name="geometricdistribution-class"></a>geometric_distribution 类
生成几何分布。  
  
## <a name="syntax"></a>语法  
  
```  
template<class IntType = int>
class geometric_distribution {
public:    
    // types 
    typedef IntType result_type; 
    struct param_type;   
    
    // constructors and reset functions 
    explicit geometric_distribution(double p = 0.5);
    explicit geometric_distribution(const param_type& parm);
    void reset();
    
    // generating functions 
    template <class URNG>  
    result_type operator()(URNG& gen);
    template <class URNG>
    result_type operator()(URNG& gen, const param_type& parm);
    
    // property functions 
    double p() const;
    param_type param() const;
    void param(const param_type& parm);
    result_type min() const;
    result_type max() const;
}; 
```  
#### <a name="parameters"></a>参数  
*IntType*  
整数结果类型，默认为 `int`。 有关可能的类型，请参阅 [\<random>](../standard-library/random.md)。  
  
*URNG* 均匀随机数生成器引擎。 有关可能的类型，请参阅 [\<random>](../standard-library/random.md)。  
  
## <a name="remarks"></a>备注  
模板类描述了使用几何分布产生用户指定的整型值的分布。 下表链接到有关各个成员的文章。  
  
||||  
|-|-|-|  
|[geometric_distribution::geometric_distribution](#geometric_distribution__geometric_distribution)|`geometric_distribution::p`|`geometric_distribution::param`|  
|`geometric_distribution::operator()`||[geometric_distribution::param_type](#geometric_distribution__param_type)|  
  
属性函数 `p()` 将返回存储的分布参数 `p` 的值。  
  
属性成员 `param()` 将设置或返回 `param_type` 存储的分布参数包。  

`min()` 和 `max()` 成员函数将分别返回最小可能结果和最大可能结果。  
  
`reset()` 成员函数将放弃所有缓存的值，使下一个对 `operator()` 的调用的结果不取决于在调用之前从引擎获得的任何值。  
  
`operator()` 成员函数将根据 URNG 引擎，从当前参数包或指定参数包返回下一个生成的值。
  
若要深入了解分布类及其成员，请参阅 [\<random>](../standard-library/random.md)。  
  
有关卡方分布的详细信息，请参阅 Wolfram MathWorld 文章[几何分布](http://go.microsoft.com/fwlink/LinkId=400529)。  
  
## <a name="example"></a>示例  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const double p, const int s) {  
  
    // uncomment to use a non-deterministic generator  
    //    std::random_device gen;  
    std::mt19937 gen(1701);  
  
    std::geometric_distribution<> distr(p);  
  
    std::cout << std::endl;  
    std::cout << "min() == " << distr.min() << std::endl;  
    std::cout << "max() == " << distr.max() << std::endl;  
    std::cout << "p() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.p() << std::endl;  
  
    // generate the distribution as a histogram  
    std::map<int, int> histogram;  
    for (int i = 0; i < s; ++i) {  
        ++histogram[distr(gen)];  
    }  
  
    // print results  
    std::cout << "Distribution for " << s << " samples:" << std::endl;  
    for (const auto& elem : histogram) {  
        std::cout << std::setw(5) << elem.first << ' ' << std::string(elem.second, ':') << std::endl;  
    }  
    std::cout << std::endl;  
}  
  
int main()  
{  
    double p_dist = 0.5;  
  
    int samples = 100;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter a floating point value for the \'p\' distribution parameter: ";  
    std::cin >> p_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(p_dist, samples);  
}  
```  
  
首次测试：  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.
Enter a floating point value for the 'p' distribution parameter: .5
Enter an integer value for the sample count: 100

min() == 0
max() == 2147483647
p() == 0.5000000000
Distribution for 100 samples:
    0 :::::::::::::::::::::::::::::::::::::::::::::::::::::
    1 ::::::::::::::::::::::::::
    2 ::::::::::::
    3 ::::::
    4 ::
    5 :
```  
  
第二次测试：  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.
Enter a floating point value for the 'p' distribution parameter: .1
Enter an integer value for the sample count: 100

min() == 0
max() == 2147483647
p() == 0.1000000000
Distribution for 100 samples:
    0 :::::::::
    1 :::::::::::
    2 ::::::::::
    3 :::::::
    4 :::::
    5 ::::::::
    6 :::
    7 ::::::
    8 :::::::
    9 :::::
   10 :::
   11 :::
   12 ::
   13 :
   14 :::
   15 ::
   16 :::
   17 :::
   20 :::::
   21 :
   29 :
   32 :
   35 :
```  
  
## <a name="requirements"></a>要求  
**标头：**\<random>  
  
**命名空间：** std  
  
##  <a name="a-namegeometricdistributiongeometricdistributiona--geometricdistributiongeometricdistribution"></a><a name="geometric_distribution__geometric_distribution"></a>geometric_distribution::geometric_distribution  
构造分布。  
  
```  
explicit geometric_distribution(double p = 0.5);
explicit geometric_distribution(const param_type& parm);
```  
  
### <a name="parameters"></a>参数  
p  
`p` 分布参数。  
  
*parm*  
用于构造分布的参数结构。  
  
### <a name="remarks"></a>备注  
**前置条件：**`0.0 < p && p < 1.0`  
  
第一个构造函数将构造一个其存储的 `p` 值保留值 *p* 的对象。  
  
第二个构造函数将构造一个从 parm 初始化其存储的参数的对象。 通过调用 `param()` 成员函数，可获取和设置当前的现有分发参数。  
  
##  <a name="a-namegeometricdistributionparamtypea--geometricdistributionparamtype"></a><a name="geometric_distribution__param_type"></a>geometric_distribution::param_type  
存储分布的参数。  
  
```  
struct param_type {  
   typedef geometric_distribution<result_type> distribution_type;  
   param_type(double p = 0.5);
   double p() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };  
```  
  
### <a name="parameters"></a>参数  
p  
`p` 分布参数。  
  
right  
与此比较的 `param_type` 实例。  
  
### <a name="remarks"></a>备注  
**前置条件：**`0.0 < p && p < 1.0`  
  
在实例化时，可将此结构传递给分布的类构造函数、传递给 `param()` 成员函数以设置现有分布的存储参数，并传递给 `operator()` 以代替存储参数使用。  
  
## <a name="see-also"></a>另请参阅  
[\<random>](../standard-library/random.md)


