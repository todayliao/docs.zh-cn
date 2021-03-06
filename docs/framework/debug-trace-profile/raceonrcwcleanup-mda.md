---
title: "raceOnRCWCleanup MDA | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "RCW"
  - "managed debugging assistants (MDAs), RCWs"
  - "race on RCW cleanup"
  - "MDAs (managed debugging assistants), RCWs"
  - "RaceOnRCWCleanup MDA"
  - "runtime callable wrappers"
ms.assetid: bee1e9b1-50a8-4c89-9cd9-7dd6b2458187
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# raceOnRCWCleanup MDA
当使用命令（如 <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=fullName> 方法）发出一个调用来发布[运行时可调用包装](../../../docs/framework/interop/runtime-callable-wrapper.md) \(RCW\) 时，如果公共语言运行时 \(CLR\) 检测到该包装正在使用中，则激活 `raceOnRCWCleanup` 托管调试助手 \(MDA\)。  
  
## 症状  
 使用 <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> 或类似方法释放 RCW 期间或之后发生访问冲突或内存损坏。  
  
## 原因  
 正在另一个线程中或释放线程堆栈中使用 RCW。  无法释放使用中的 RCW。  
  
## 解决方法  
 不要释放在当前或在其他线程中可能使用的 RCW。  
  
## 对运行时的影响  
 此 MDA 对 CLR 无任何影响。  
  
## 输出  
 描述错误的消息。  
  
## 配置  
  
```  
<mdaConfig>  
  <assistants>  
    <raceOnRCWCleanup/>  
  </assistants>  
</mdaConfig>  
```  
  
## 请参阅  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [互操作封送处理](../../../docs/framework/interop/interop-marshaling.md)