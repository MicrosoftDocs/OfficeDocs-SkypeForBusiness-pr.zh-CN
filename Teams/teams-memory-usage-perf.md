---
title: Microsoft Teams 如何使用内存
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: 了解 Microsoft Teams 系统内存使用情况，以及为什么桌面应用程序和 Web 应用程序之间的内存使用情况相同。
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 0d55caf2a1642b28ccc63e3be1cf3eccc69bb260
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2022
ms.locfileid: "66605671"
---
# <a name="how-microsoft-teams-uses-memory"></a>Microsoft Teams 如何使用内存

某些 Microsoft Teams 用户对 Teams 如何使用内存有疑问。 本文介绍 Teams 如何使用内存，以及 Teams 桌面应用程序 (应用) 和 Teams Web 应用无法阻止同一台计算机上的其他应用和工作负荷有足够的内存以以最佳方式运行的原因。 Teams 旨在使用新式 Web 技术。 为此，Teams 桌面客户端是在使用Chromium进行渲染的电子版上开发的。 这是当今许多最受欢迎的浏览器（包括 Edge 和 Chrome）背后的相同呈现引擎。

## <a name="how-teams-works"></a>Teams 的工作原理

在电子版上设计的 Teams 可以更快地进行开发，它还在不同操作系统 (Windows、Mac 和 Linux) 之间保持 Teams 版本的奇偶校验。 这种奇偶校验是可能的，因为电子和Chromium在所有版本中都保持类似的代码库。 此体系结构的另一个优点是 Teams Web 应用与桌面版本之间存在类似的内存使用情况配置文件。 Web 应用和桌面版本使用内存的方式与浏览器的使用方式类似。 有关电子的详细信息，请参阅 [其网站](https://electronjs.org/)。

有关详细信息，请参阅 [Chromium Chrome 内存中的](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md)[内存使用](https://www.chromium.org/developers/memory-usage-backgrounder)情况和关键概念。

下图显示了在 Google Chrome) 中运行的适用于 Windows 的 Teams 桌面应用和 Teams Web 应用 (的并行内存使用情况。

![桌面应用和 Web 应用的 Teams 内存使用情况。](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a>Teams 中的内存使用情况

了解 Teams 在系统内存方面 *的预期* 行为并了解真正有问题的系统内存问题的症状非常重要。

### <a name="expected-memory-usage-by-teams"></a>Teams 的预期内存使用情况

无论你是运行 Teams 桌面应用还是 Teams Web 应用，Chromium检测有多少系统内存可用，并利用足够的内存来优化呈现体验。 当其他应用或服务需要系统内存时，Chromium向这些进程放弃内存。 Chromium不断优化 Teams 内存使用量，以优化 Teams 性能，而不会影响当前运行的任何其他内容。

这样，类似的Chromium工作负荷可以利用不同的内存量，具体取决于可用的系统内存量。

下图描述了 Teams 在四个单独的系统上的内存使用情况，每个系统都有不同数量的可用内存。 每个系统都在处理类似的工作负荷， (打开并运行) 的相同应用。

![跨不同系统的 Teams 内存使用情况。](media/teams-memory-usage.png)

当计算机具有更多内存时，Teams 将使用该内存。 在内存稀缺的系统中，Teams 将使用更少。

### <a name="symptoms-of-system-memory-issues"></a>系统内存问题的症状

如果在计算机上看到以下一个或多个症状，则可能会出现严重的系统内存问题：

- 多个大型应用程序同时运行时使用高内存。
- 系统性能缓慢或应用程序挂起。
- 所有应用的总体系统内存使用率持续为 90% 或更高。 使用此内存量时，Teams 应将内存还原到其他应用和工作负荷。 持续内存使用率为 90% 可能意味着 Teams 不会将内存还给系统，这表示存在问题。

下图显示了当系统内存使用率异常高时任务管理器中的视图示例。

![任务管理器中的 Teams 内存使用情况视图。](media/teams-memory-high-mem-process-list.png)

![任务管理器中的 Teams 内存使用情况图。](media/teams-memory-high-mem-process-list2.png)
