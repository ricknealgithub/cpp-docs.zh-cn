---
title: "C++ 安全性最佳做法 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "securitybestpracticesVC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "安全性 [C++]"
  - "安全性 [C++], 最佳做法"
  - "Visual C++, 安全性"
ms.assetid: 86acaccf-cdb4-4517-bd58-553618e3ec42
caps.latest.revision: 45
caps.handback.revision: 45
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# C++ 安全性最佳做法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

本文包含有关安全工具和做法的信息。  使用这些工具和做法并不会使应用程序免受攻击，但能降低攻击成功的可能性。  
  
## Visual C\+\+ 安全功能  
 这些安全功能内置于 Visual C\+\+ 编译器和链接器中：  
  
 [\/guard（启用控制流保护）](../build/reference/guard-enable-control-flow-guard.md)  
 使编译器在编译时为间接调用目标分析控制流，然后插入代码，以验证运行时的目标。  
  
 [\/GS（缓冲区安全检查）](../build/reference/gs-buffer-security-check.md)  
 指示编译器将溢出检测代码插入到面临被利用风险的函数中。  检测到溢出时，则停止执行。  默认情况下，此选项处于启用状态。  
  
 [\/SAFESEH（图像具有安全异常处理程序）](../build/reference/safeseh-image-has-safe-exception-handlers.md)  
 指示链接器在输出映像中包括一个包含每个异常处理程序的地址的表。  在运行时，操作系统使用此表来确保只执行合法的异常处理程序。  这有助于防止在运行时执行由恶意攻击引入的异常处理程序。  默认情况下关闭此选项。  
  
 [\/NXCOMPAT](../build/reference/nxcompat.md)，[\/NXCOMPAT（与数据执行保护兼容）](../build/reference/nxcompat-compatible-with-data-execution-prevention.md)  
 这些编译器和链接器选项启用数据执行保护 \(DEP\) 兼容性。  DEP 可防止 CPU 执行非代码页。  
  
 [\/analyze（代码分析）](../build/reference/analyze-code-analysis.md)  
 此编译器选项将激活报告潜在安全问题（比如缓冲区溢出、未初始化的内存、null 指针取消引用和内存泄漏）的代码分析。  默认情况下关闭此选项。  有关详细信息，请参阅 [C\/C\+\+ 代码分析概述](../Topic/Code%20Analysis%20for%20C-C++%20Overview.md)。  
  
 [\/DYNAMICBASE（使用地址空间布局随机化功能）](../build/reference/dynamicbase-use-address-space-layout-randomization.md)  
 通过使用此链接器选项，可以生成一个在执行开始时可在内存的不同位置加载的可执行映像。  此选项还使内存中的堆栈位置更加不可预测。  
  
## 增强了安全性的 CRT  
 已扩充 C 运行库 \(CRT\) 以包括面临安全风险的函数的安全版本（例如，未经检查的 `strcpy` 字符串复制函数）。  由于这些函数的早期、不安全版本现已被弃用，因此它们将导致编译时警告。  建议您使用这些 CRT 函数的安全版本，而不是选择禁止显示编译警告。  有关详细信息，请参阅 [CRT 中的安全功能](../c-runtime-library/security-features-in-the-crt.md)。  
  
## SafeInt 库  
 [SafeInt 库](../windows/safeint-library.md)有助于防止整数溢出以及在应用程序执行数学运算时可能发生的其他可被利用的错误。  `SafeInt` 库包括 [SafeInt 类](../windows/safeint-class.md)、[SafeIntException 类](../windows/safeintexception-class.md)以及几个 [SafeInt 函数](../windows/safeint-functions.md)。  
  
 `SafeInt` 类可防止整数溢出和被零除攻击。  您可以使用它处理不同类型的值之间的比较。  我将提供两个错误处理策略。  默认策略是针对引发 `SafeIntException` 类异常的 `SafeInt` 类，以报告无法完成数学运算的原因。  第二个策略针对 `SafeInt` 类，用以停止程序的执行。  还可以定义自定义策略。  
  
 每个 `SafeInt` 函数各保护一个数学运算免于出现可被利用的错误。  您可使用两种不同的参数，而不必将它们转换为相同类型。  若要保护多个数学运算，请使用 `SafeInt` 类。  
  
## 经过检查的迭代器  
 经过检查的迭代器强制实施容器边界。  默认情况下，当检查的迭代器超出范围时，它将生成异常并终止程序的执行。  经过检查的迭代器提供其他级别的响应，这些响应将根据分配给预处理器定义（例如 **\_SECURE\_SCL\_THROWS** 和 **\_ITERATOR\_DEBUG\_LEVEL**）的值而定。  例如，对于 **\_ITERATOR\_DEBUG\_LEVEL\=2** 的情况，经过检查的迭代器在调试模式中提供全面的正确性检查，这些检查可通过使用断言来执行。  有关详细信息，请参阅[经过检查的迭代器](../standard-library/checked-iterators.md)。  
  
## 托管代码的代码分析  
 托管代码的代码分析，又称 FxCop，是检查程序集与 .NET Framework 设计准则的一致性的工具。  FxCop 分析各个程序集中的代码和元数据以检查下列区域的缺陷：  
  
-   库设计  
  
-   本地化  
  
-   命名约定  
  
-   性能  
  
-   安全性  
  
## Windows 应用程序验证工具  
 应用程序验证工具 \(AppVerifier\) 可帮助您识别潜在应用程序兼容性、稳定性和安全性问题。  
  
 AppVerifier 可监视应用程序使用操作系统的方式。  在应用程序运行的过程中，此工具会监视文件系统、注册表、内存和 API，并针对它发现的问题给出源代码修复的建议。  
  
 您可以使用 AppVerifier 来：  
  
-   检测由常见编程错误导致的潜在应用程序兼容性错误。  
  
-   检查应用程序是否存在内存相关问题。  
  
-   确定应用程序中的潜在安全问题。  
  
 AppVerifier 是应用程序兼容性工具包的一部分，该工具包可从 TechNet 网站上的[应用程序兼容性](http://go.microsoft.com/fwlink/?LinkId=91277)中下载。  
  
## .NET Framework 安全功能  
 [NIB: Configuring Security Policy](http://msdn.microsoft.com/zh-cn/0f130bcd-1bba-4346-b231-0bcca7dab1a4)介绍了用于调整 .NET Framework 安全策略的准则和工具。  
  
## Windows 用户帐户  
 使用属于管理员组的 Windows 用户帐户将使开发人员和引申到的相关客户暴露在安全风险下。  有关详细信息，请参阅[作为用户组的成员运行](../top/running-as-a-member-of-the-users-group.md)和[用户帐户控制 \(UAC\) 如何影响应用程序](../top/how-user-account-control-uac-affects-your-application.md)。  
  
## 请参阅  
 <xref:System.Security>   
 [安全性](../Topic/Security%20in%20the%20.NET%20Framework.md)   
 [用户帐户控制 \(UAC\) 如何影响应用程序](../top/how-user-account-control-uac-affects-your-application.md)