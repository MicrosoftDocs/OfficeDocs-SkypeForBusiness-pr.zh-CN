---
title: Microsoft Teams 如何使用内存
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: 了解 Microsoft 团队系统内存使用情况，以及桌面应用程序和 web 应用程序之间的内存使用情况。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: d218c71a0e3ecdde40559d67e1ad3a408d65a5d9
ms.sourcegitcommit: 43dc627e9fef31a2508f54acf741000551ff68b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2020
ms.locfileid: "48878716"
---
# <a name="how-microsoft-teams-uses-memory"></a>Microsoft Teams 如何使用内存

某些 Microsoft 团队用户对团队使用内存的方式有疑问。 本文介绍团队如何使用内存，以及团队桌面应用程序 (应用) 和团队 web app 不阻止同一台计算机上的其他应用和工作负荷以最佳运行的内存。 团队设计为使用新式 web 技术。 为了实现此目的，已在电子上开发了团队桌面客户端，该客户端使用 Chromium 进行呈现。 这是当今大多数最热门的浏览器（包括边缘和 Chrome）中的相同呈现引擎。

## <a name="how-teams-works"></a>团队的工作方式

在电子上设计的团队允许更快地进行开发，并且它还会在不同操作系统 (Windows、Mac 和 Linux) 之间保持不同团队版本之间的奇偶。 这种奇偶校验是可行的，因为电子和 Chromium 在所有版本中维护类似的基本代码。 此体系结构的另一个优点是，团队 web 应用和桌面版本之间存在类似的内存使用率配置文件。 Web 应用和桌面版本使用内存的方式与浏览器使用内存的方式类似。 有关电子的详细信息可在 [其网站](https://electronjs.org/)上使用。

有关详细信息，请参阅[Chrome 内存中](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md)的[Chromium 内存使用](https://www.chromium.org/developers/memory-usage-backgrounder)和关键概念。

下图显示了 Windows 和团队 Web app 的团队桌面应用的并行内存使用情况 (在本示例中，在 Google Chrome) 中运行。

![桌面应用和 Web 应用的团队内存使用情况](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a>团队中的内存使用情况

了解团队在系统内存方面的 *预期* 行为并了解真正有问题的系统内存问题的症状非常重要。

### <a name="expected-memory-usage-by-teams"></a>团队预期的内存使用情况

无论您正在运行的是团队桌面应用还是团队 web 应用，Chromium 都会检测出有多少系统内存可用，并充分利用该内存来优化呈现体验。 当其他应用或服务需要系统内存时，Chromium 将为这些进程提供内存。 Chromium 在不断调整团队内存使用情况，以便优化团队性能而不影响当前运行的任何其他内容。

这样，类似的 Chromium 工作负荷可以利用不同数量的内存，具体取决于可用的系统内存量。

下图介绍了两个独立系统上的团队内存使用情况，每个系统具有不同的可用内存量。 每个系统都处理类似的工作负荷 (相同的应用打开并运行) 。

![团队跨不同系统的内存使用量](media/teams-memory-usage.png)

当计算机有更多内存时，团队将使用该内存。 在内存不足的系统中，团队将占用较少的时间。

### <a name="symptoms-of-system-memory-issues"></a>系统内存问题的症状

如果你在计算机上看到以下一种或多种症状，可能会出现严重的系统内存问题：

- 高内存在多个大型应用程序同时运行时使用。
- 系统性能较慢或应用程序挂起。
- 所有应用的持续总系统内存使用率为90% 或更高。 使用此内存使用量，团队应将内存提供给其他应用和工作负荷。 90% 的持久内存使用意味着团队没有将内存提供给系统，这表示存在问题。

下面的图像显示了当系统内存使用异常高时，任务管理器中的视图示例。

![任务管理器中的工作组内存使用情况视图](media/teams-memory-high-mem-process-list.png)

![任务管理器中的团队内存使用图](media/teams-memory-high-mem-process-list2.png)
