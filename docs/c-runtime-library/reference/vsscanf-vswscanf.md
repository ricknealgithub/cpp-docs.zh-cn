---
title: vsscanf、vswscanf | Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- vsscanf
- vswscanf
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _vstscanf
- vsscanf
- vswscanf
dev_langs:
- C++
helpviewer_keywords:
- vswscanf function
- vsscanf function
ms.assetid: e96180f2-df46-423d-b4eb-0a49ab819bde
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7267e308f8b75a0e040e3fe33d51a9bdeea3914f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32415886"
---
# <a name="vsscanf-vswscanf"></a>vsscanf、vswscanf

从字符串中读取格式化数据。 提供这些函数的更多安全版本；请参阅 [vsscanf_s、vswscanf_s](vsscanf-s-vswscanf-s.md)。

## <a name="syntax"></a>语法

```C
int vsscanf(
   const char *buffer,
   const char *format,
   va_list arglist
);
int vswscanf(
   const wchar_t *buffer,
   const wchar_t *format,
   va_list arglist
);
```

### <a name="parameters"></a>参数

*buffer*<br/>
存储的数据

*format*<br/>
窗体控件字符串。 有关详细信息，请参阅[格式规范字段：scanf 和 wscanf 函数](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md)。

*arglist*<br/>
变量参数列表。

## <a name="return-value"></a>返回值

每个函数都将返回成功转换并分配的字段数；返回值不包括已读取但未分配的字段。 返回值为 0 表示没有分配任何字段。 返回值是**EOF**是否有错误或如果在第一次转换之前到达字符串的末尾。

如果*缓冲区*或*格式*是**NULL**指针，无效参数处理程序调用中所述，[参数验证](../../c-runtime-library/parameter-validation.md)。 如果允许执行继续，则这些函数将返回-1 并设置**errno**到**EINVAL**。

有关这些及其他错误代码的信息，请参阅 [errno、_doserrno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。

## <a name="remarks"></a>备注

**Vsscanf**函数将读取从数据*缓冲区*到提供的每个自变量中的位置*arglist*自变量列表。 列表中的每个参数必须是指向具有中的类型说明符对应的类型的变量的指针*格式*。 *格式*参数控件的输入解释字段，并具有相同形式和函数与*格式*参数**scanf**函数。 如果复制出现在重叠的字符串之间，则该行为不确定。

> [!IMPORTANT]
> 当你使用**vsscanf**以读取的字符串，始终指定宽度 **%s**格式 (例如， **"%32s"** 而不是 **"%s"**);否则，格式不正确的输入可能导致缓冲区溢出。

**vswscanf**是宽字符版本的**vsscanf**; 的自变量**vswscanf**是宽字符字符串。 **vsscanf**不处理多字节的十六进制字符。 **vswscanf**不处理 Unicode 全角十六进制或"兼容性区域"字符。 否则为**vswscanf**和**vsscanf**具有相同行为。

### <a name="generic-text-routine-mappings"></a>一般文本例程映射

|TCHAR.H 例程|未定义 _UNICODE 和 _MBCS|已定义 _MBCS|已定义 _UNICODE|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vstscanf**|**vsscanf**|**vsscanf**|**vswscanf**|

## <a name="requirements"></a>要求

|例程|必需的标头|
|-------------|---------------------|
|**vsscanf**|\<stdio.h>|
|**vswscanf**|\<stdio.h> 或 \<wchar.h>|

有关其他兼容性信息，请参阅 [兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

```C
// crt_vsscanf.c
// compile with: /W3
// This program uses vsscanf to read data items
// from a string named tokenstring, then displays them.

#include <stdio.h>
#include <stdarg.h>

int call_vsscanf(char *tokenstring, char *format, ...)
{
    int result;
    va_list arglist;
    va_start(arglist, format);
    result = vsscanf(tokenstring, format, arglist);
    va_end(arglist);
    return result;
}

int main( void )
{
    char  tokenstring[] = "15 12 14...";
    char  s[81];
    char  c;
    int   i;
    float fp;

    // Input various data from tokenstring:
    // max 80 character string:
    call_vsscanf(tokenstring, "%80s", s);
    call_vsscanf(tokenstring, "%c", &c);
    call_vsscanf(tokenstring, "%d", &i);
    call_vsscanf(tokenstring, "%f", &fp);

    // Output the data read
    printf("String    = %s\n", s);
    printf("Character = %c\n", c);
    printf("Integer:  = %d\n", i);
    printf("Real:     = %f\n", fp);
}
```

```Output
String    = 15
Character = 1
Integer:  = 15
Real:     = 15.000000
```

## <a name="see-also"></a>请参阅

[流 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[scanf、_scanf_l、wscanf、_wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf、_sscanf_l、swscanf、_swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[sprintf、_sprintf_l、swprintf、_swprintf_l、\__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[vsscanf_s、vswscanf_s](vsscanf-s-vswscanf-s.md)<br/>
