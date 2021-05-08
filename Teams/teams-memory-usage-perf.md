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
# <a name="how-microsoft-teams-uses-memory"></a><span data-ttu-id="2af8e-103">Microsoft Teams 如何使用内存</span><span class="sxs-lookup"><span data-stu-id="2af8e-103">How Microsoft Teams uses memory</span></span>

<span data-ttu-id="2af8e-104">某些Microsoft Teams用户对如何使用内存Teams有疑问。</span><span class="sxs-lookup"><span data-stu-id="2af8e-104">Some Microsoft Teams users have questions about how Teams uses memory.</span></span> <span data-ttu-id="2af8e-105">本文介绍 Teams 如何使用内存，以及 Teams 桌面应用程序 (应用) 和 Teams Web 应用为何不会阻止同一计算机上其他应用和工作负荷有足够的内存以最佳方式运行。</span><span class="sxs-lookup"><span data-stu-id="2af8e-105">This article describes how memory is used by Teams, and why the Teams desktop application (app) and the Teams web app do not prevent other apps and workloads on the same computer from having enough memory to run optimally.</span></span> <span data-ttu-id="2af8e-106">Teams旨在使用现代 Web 技术。</span><span class="sxs-lookup"><span data-stu-id="2af8e-106">Teams is designed to use modern web technology.</span></span> <span data-ttu-id="2af8e-107">为实现此目的，Teams在 Electron 上开发桌面客户端，该客户端Chromium呈现。</span><span class="sxs-lookup"><span data-stu-id="2af8e-107">To achieve this, the Teams desktop client was developed on Electron, which uses Chromium for rendering.</span></span> <span data-ttu-id="2af8e-108">这是许多当今最受欢迎的浏览器（包括 Edge 和 Chrome）背后的相同呈现引擎。</span><span class="sxs-lookup"><span data-stu-id="2af8e-108">This is the same rendering engine behind many of today's most popular browsers, including Edge and Chrome.</span></span>

## <a name="how-teams-works"></a><span data-ttu-id="2af8e-109">如何Teams工作</span><span class="sxs-lookup"><span data-stu-id="2af8e-109">How Teams works</span></span>

<span data-ttu-id="2af8e-110">Teams在 Electron 上设计的版本可以加快开发速度，并且它还在不同操作系统（ (Windows、Mac 和 Linux) ）之间保持 Teams 版本之间的奇偶) 。</span><span class="sxs-lookup"><span data-stu-id="2af8e-110">Teams being designed on Electron allows for faster development, and it also maintains parity between Teams versions across different operating systems (Windows, Mac, and Linux).</span></span> <span data-ttu-id="2af8e-111">这种奇偶校验的可能原因是，Electron 和 Chromium在所有版本之间保持类似的代码库。</span><span class="sxs-lookup"><span data-stu-id="2af8e-111">This parity is possible because Electron and Chromium maintain a similar code base across all versions.</span></span> <span data-ttu-id="2af8e-112">此体系结构的另一个优点是，Web 应用和桌面版本Teams类似的内存使用情况配置文件。</span><span class="sxs-lookup"><span data-stu-id="2af8e-112">Another advantage of this architecture is there's a similar memory usage profile between the Teams web app and the desktop version.</span></span> <span data-ttu-id="2af8e-113">Web 应用和桌面版本使用内存的方式与浏览器使用内存的方式类似。</span><span class="sxs-lookup"><span data-stu-id="2af8e-113">Both the web app and the desktop versions use memory in a similar way to how a browser would use it.</span></span> <span data-ttu-id="2af8e-114">有关 Electron 详细信息，请参阅 [其网站](https://electronjs.org/)。</span><span class="sxs-lookup"><span data-stu-id="2af8e-114">More information about Electron is available at [their Web site](https://electronjs.org/).</span></span>

<span data-ttu-id="2af8e-115">有关详细信息[Chromium](https://www.chromium.org/developers/memory-usage-backgrounder) Chrome 内存中[的内存使用情况](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md)和关键概念。</span><span class="sxs-lookup"><span data-stu-id="2af8e-115">See [Chromium Memory Usage](https://www.chromium.org/developers/memory-usage-backgrounder) and [Key Concepts in Chrome Memory](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) for more information.</span></span>

<span data-ttu-id="2af8e-116">下图显示了在 Google Chrome) 中运行的 Teams 桌面应用 Windows 和 Teams Web 应用 (的并排内存使用情况。</span><span class="sxs-lookup"><span data-stu-id="2af8e-116">The following image shows side-by-side memory usages of the Teams desktop app for Windows and the Teams Web app (in this example, running in Google Chrome).</span></span>

![Teams应用和 Web 应用的内存使用情况](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a><span data-ttu-id="2af8e-118">内存中的内存Teams</span><span class="sxs-lookup"><span data-stu-id="2af8e-118">Memory usage in Teams</span></span>

<span data-ttu-id="2af8e-119">必须了解系统内存Teams预期行为，并了解真正有问题的系统内存问题的症状。</span><span class="sxs-lookup"><span data-stu-id="2af8e-119">It is important to understand the *expected* behavior of Teams when it comes to system memory, and to know the symptoms of truly problematic system memory issues.</span></span>

### <a name="expected-memory-usage-by-teams"></a><span data-ttu-id="2af8e-120">按数据表示的预期Teams</span><span class="sxs-lookup"><span data-stu-id="2af8e-120">Expected memory usage by Teams</span></span>

<span data-ttu-id="2af8e-121">无论是运行 Teams 桌面应用还是 Teams Web 应用，Chromium 检测有多少系统内存可用，并充分利用该内存来优化呈现体验。</span><span class="sxs-lookup"><span data-stu-id="2af8e-121">Whether you're running the Teams desktop app or the Teams web app, Chromium detects how much system memory is available and utilizes enough of that memory to optimize the rendering experience.</span></span> <span data-ttu-id="2af8e-122">当其他应用或服务需要系统内存时，Chromium为这些进程提供内存。</span><span class="sxs-lookup"><span data-stu-id="2af8e-122">When other apps or services require system memory, Chromium gives up memory to those processes.</span></span> <span data-ttu-id="2af8e-123">Chromium持续Teams优化内存使用量，以便优化Teams性能，而不会影响当前正在运行的任何其他内容。</span><span class="sxs-lookup"><span data-stu-id="2af8e-123">Chromium tunes Teams memory usage on an ongoing basis in order to optimize Teams performance without impacting anything else currently running.</span></span>

<span data-ttu-id="2af8e-124">这样，Chromium工作负荷可以利用不同的内存量，具体取决于可用的系统内存量。</span><span class="sxs-lookup"><span data-stu-id="2af8e-124">In this way, similar Chromium workloads can utilize varying amounts of memory, depending on the amount of system memory that is available.</span></span>

<span data-ttu-id="2af8e-125">下图描绘了在四个单独的系统上Teams内存使用情况，每个系统上都有不同的可用内存量。</span><span class="sxs-lookup"><span data-stu-id="2af8e-125">The following graph depicts memory usage by Teams on four separate systems, each with different amounts of memory available.</span></span> <span data-ttu-id="2af8e-126">每个系统正在处理类似的工作负荷， (打开并运行相同的) 。</span><span class="sxs-lookup"><span data-stu-id="2af8e-126">Each of the systems is processing similar workloads (same apps open and running).</span></span>

![Teams不同系统的内存使用情况](media/teams-memory-usage.png)

<span data-ttu-id="2af8e-128">当计算机具有更多内存时，Teams使用该内存。</span><span class="sxs-lookup"><span data-stu-id="2af8e-128">When computers have more memory, Teams will use that memory.</span></span> <span data-ttu-id="2af8e-129">在内存不足的系统中，Teams消耗更少。</span><span class="sxs-lookup"><span data-stu-id="2af8e-129">In systems where memory is scarce, Teams will use less.</span></span>

### <a name="symptoms-of-system-memory-issues"></a><span data-ttu-id="2af8e-130">系统内存问题的症状</span><span class="sxs-lookup"><span data-stu-id="2af8e-130">Symptoms of system memory issues</span></span>

<span data-ttu-id="2af8e-131">如果在计算机上看到以下一种或多个症状，则可能是系统内存问题严重：</span><span class="sxs-lookup"><span data-stu-id="2af8e-131">If you see one or more of the following symptoms on your computer, you could have a serious system memory issue:</span></span>

- <span data-ttu-id="2af8e-132">当多个大型应用程序同时运行时，内存使用较高。</span><span class="sxs-lookup"><span data-stu-id="2af8e-132">High memory use when multiple large applications are running simultaneously.</span></span>
- <span data-ttu-id="2af8e-133">系统性能缓慢或应用程序挂起。</span><span class="sxs-lookup"><span data-stu-id="2af8e-133">Slow system performance or applications hanging.</span></span>
- <span data-ttu-id="2af8e-134">在所有应用之间持续使用 90% 或更高的系统内存。</span><span class="sxs-lookup"><span data-stu-id="2af8e-134">Sustained overall system memory usage of 90% or higher across all apps.</span></span> <span data-ttu-id="2af8e-135">如果内存使用量达到此Teams，应该会向其他应用和工作负荷提供内存。</span><span class="sxs-lookup"><span data-stu-id="2af8e-135">With this amount of memory usage, Teams should be giving memory back to other apps and workloads.</span></span> <span data-ttu-id="2af8e-136">持续的内存使用率为 90% 可能意味着Teams不会向系统提供内存，这表示出现问题。</span><span class="sxs-lookup"><span data-stu-id="2af8e-136">Sustained memory usage of 90% could mean Teams isn't giving memory back to the system, which indicates a problem.</span></span>

<span data-ttu-id="2af8e-137">下图显示了当系统内存使用率异常较高时任务管理器中的视图示例。</span><span class="sxs-lookup"><span data-stu-id="2af8e-137">The following images show examples of views in Task Manager when system memory usage is abnormally high.</span></span>

![Teams管理器中的内存使用情况视图](media/teams-memory-high-mem-process-list.png)

![Teams管理器中的内存使用情况图](media/teams-memory-high-mem-process-list2.png)
