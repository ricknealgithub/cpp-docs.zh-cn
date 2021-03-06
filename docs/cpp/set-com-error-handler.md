---
title: _set_com_error_handler |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- _set_com_error_handler function
ms.assetid: 49fe4fca-5e37-4d83-abaf-15be5ce37f94
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1f516114dbaa9e507491cf669c3371b6b8fbaf11
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2018
ms.locfileid: "37942506"
---
# <a name="setcomerrorhandler"></a>_set_com_error_handler
**Microsoft 专用**  
  
 替换用于 COM 错误处理的默认函数。  
  
## <a name="syntax"></a>语法  
  
```  
void __stdcall _set_com_error_handler(  
   void (__stdcall *pHandler)(  
      HRESULT hr,   
      IErrorInfo* perrinfo  
   )  
);  
```  
  
#### <a name="parameters"></a>参数  
 *pHandler*  
 指向替换函数的指针。  
  
 *hr*  
 HRESULT 的信息。  
  
 *perrinfo*  
 `IErrorInfo` 对象。  
  
## <a name="remarks"></a>备注  
 默认情况下[_com_raise_error](../cpp/com-raise-error.md)处理所有 COM 错误。 您可以通过使用 `_set_com_error_handler` 调用您自己的错误处理函数来更改此行为。  
  
 替换函数必须具有与 `_com_raise_error` 的签名等效的签名。  
  
## <a name="example"></a>示例  
  
```cpp 
// _set_com_error_handler.cpp  
// compile with /EHsc  
#include <stdio.h>  
#include <comdef.h>  
#include <comutil.h>  
  
// Importing ado dll to attempt to establish an ado connection.  
// Not related to _set_com_error_handler   
#import "C:\Program Files\Common Files\System\ado\msado15.dll" no_namespace rename("EOF", "adoEOF")  
  
void __stdcall _My_com_raise_error(HRESULT hr, IErrorInfo* perrinfo)  
{  
   throw "Unable to establish the connection!";  
}  
  
int main()  
{  
   _set_com_error_handler(_My_com_raise_error);  
   _bstr_t bstrEmpty(L"");  
   _ConnectionPtr Connection = NULL;  
   try  
   {  
      Connection.CreateInstance(__uuidof(Connection));  
      Connection->Open(bstrEmpty, bstrEmpty, bstrEmpty, 0);   
   }  
   catch(char* errorMessage)  
   {  
      printf("Exception raised: %s\n", errorMessage);  
   }  
  
   return 0;  
}  
```  
  
```Output  
Exception raised: Unable to establish the connection!  
```  
  
## <a name="requirements"></a>要求  
 **标头：** \<comdef.h >  
  
 **Lib:** 如果**wchar_t 是本机类型**编译器选项已打开，请使用 comsuppw.lib 或 comsuppwd.lib。 如果**wchar_t 是本机类型**未启用，请使用 comsupp.lib。 有关详细信息，请参阅 [/Zc:wchar_t（wchar_t 是本机类型）](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)。  
  
## <a name="see-also"></a>请参阅  
 [编译器 COM 全局函数](../cpp/compiler-com-global-functions.md)