---
title: ".NET Core SDK 概述 | Microsoft Docs"
description: ".NET Core SDK 概述"
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 26bc9822-e42b-48ec-b0d6-499dc604add7
ms.translationtype: Human Translation
ms.sourcegitcommit: 4437ce5d344cf06d30e31911def6287999fc6ffc
ms.openlocfilehash: 1b05b7e1a2d274f02cd1222c0a90a59583d37e92
ms.contentlocale: zh-cn
ms.lasthandoff: 05/23/2017

---

<a id="net-core-sdk-overview" class="xliff"></a>

# .NET Core SDK 概述 

<a id="introduction" class="xliff"></a>

## 介绍
.NET Core 软件开发工具包 (SDK) 是一组库和工具，使开发人员能够创建 .NET Core 应用程序和库。 这是开发人员最可能获取的包。 

它包含下列组件：

1. .NET Core 命令行工具，用于生成应用程序
2. .NET Core（库和运行时），用于生成并运行应用程序
3. `dotnet` 驱动程序，用于运行 [CLI 命令](tools/index.md)和应用程序


<a id="acquiring-the-net-core-sdk" class="xliff"></a>

## 获取 .NET Core SDK
与任何工具一样，首先应将工具安装到计算机上。 根据具体情况，可以使用本机安装程序安装 SDK 或使用 shell 脚本安装。

本机安装程序主要用于开发人员的计算机。 可以使用所有受支持的平台的本机安装机制发布 SDK，例如 Ubuntu 上的 DEB 或 Windows 上的 MSI 包。 这些安装程序将根据需要为用户安装并设置环境，以便在安装完成后可立即使用 SDK。 但是，这些安装程序也需要对计算机的管理权限。 可以在 [.NET Core 安装指南](https://aka.ms/dotnetcoregs)中查看安装说明。

另一方面，安装脚本不需要管理权限。 但是，它们也不会在计算机上安装任何系统必备组件；需要手动安装所有系统必备组件。 这些脚本主要用于设置生成服务器或希望安装工具但没有管理权限的情况（请务必注意上述系统必备组件注意事项）。 可以在[安装脚本引用主题](tools/dotnet-install-script.md)中找到详细信息。 如果对如何在 CI 生成服务器上设置 SDK 感兴趣，可以看一看 [CI 服务器的 SDK](tools/using-ci-with-cli.md) 文档。 

默认情况下，SDK 将以“并行”(SxS) 方式安装。 这意味着多个版本的 CLI 工具在任何给定时间内可在一台计算机上共存。 有关如何使用正确版本的详细信息，请参阅 .NET Core 命令行工具主题中的[驱动程序部分](tools/index.md#driver)。

