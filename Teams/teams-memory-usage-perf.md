---
title: Microsoft Teams 如何使用内存
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: 了解Microsoft Teams内存使用情况，以及为什么桌面应用程序和 Web 应用程序的内存使用量相同。
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

某些Microsoft Teams用户对如何使用内存Teams有疑问。 本文介绍 Teams 如何使用内存，以及 Teams 桌面应用程序 (应用) 和 Teams Web 应用为何不会阻止同一计算机上其他应用和工作负荷有足够的内存以最佳方式运行。 Teams旨在使用现代 Web 技术。 为实现此目的，Teams在 Electron 上开发桌面客户端，该客户端Chromium呈现。 这是许多当今最受欢迎的浏览器（包括 Edge 和 Chrome）背后的相同呈现引擎。

## <a name="how-teams-works"></a>如何Teams工作

Teams在 Electron 上设计的版本可以加快开发速度，并且它还在不同操作系统（ (Windows、Mac 和 Linux) ）之间保持 Teams 版本之间的奇偶) 。 这种奇偶校验的可能原因是，Electron 和 Chromium在所有版本之间保持类似的代码库。 此体系结构的另一个优点是，Web 应用和桌面版本Teams类似的内存使用情况配置文件。 Web 应用和桌面版本使用内存的方式与浏览器使用内存的方式类似。 有关 Electron 详细信息，请参阅 [其网站](https://electronjs.org/)。

有关详细信息[Chromium](https://www.chromium.org/developers/memory-usage-backgrounder) Chrome 内存中[的内存使用情况](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md)和关键概念。

下图显示了在 Google Chrome) 中运行的 Teams 桌面应用 Windows 和 Teams Web 应用 (的并排内存使用情况。

![Teams应用和 Web 应用的内存使用情况](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a>内存中的内存Teams

必须了解系统内存Teams预期行为，并了解真正有问题的系统内存问题的症状。

### <a name="expected-memory-usage-by-teams"></a>按数据表示的预期Teams

无论是运行 Teams 桌面应用还是 Teams Web 应用，Chromium 检测有多少系统内存可用，并充分利用该内存来优化呈现体验。 当其他应用或服务需要系统内存时，Chromium为这些进程提供内存。 Chromium持续Teams优化内存使用量，以便优化Teams性能，而不会影响当前正在运行的任何其他内容。

这样，Chromium工作负荷可以利用不同的内存量，具体取决于可用的系统内存量。

下图描绘了在四个单独的系统上Teams内存使用情况，每个系统上都有不同的可用内存量。 每个系统正在处理类似的工作负荷， (打开并运行相同的) 。

![Teams不同系统的内存使用情况](media/teams-memory-usage.png)

当计算机具有更多内存时，Teams使用该内存。 在内存不足的系统中，Teams消耗更少。

### <a name="symptoms-of-system-memory-issues"></a>系统内存问题的症状

如果在计算机上看到以下一种或多个症状，则可能是系统内存问题严重：

- 当多个大型应用程序同时运行时，内存使用较高。
- 系统性能缓慢或应用程序挂起。
- 在所有应用之间持续使用 90% 或更高的系统内存。 如果内存使用量达到此Teams，应该会向其他应用和工作负荷提供内存。 持续的内存使用率为 90% 可能意味着Teams不会向系统提供内存，这表示出现问题。

下图显示了当系统内存使用率异常较高时任务管理器中的视图示例。

![Teams管理器中的内存使用情况视图](media/teams-memory-high-mem-process-list.png)

![Teams管理器中的内存使用情况图](media/teams-memory-high-mem-process-list2.png)
