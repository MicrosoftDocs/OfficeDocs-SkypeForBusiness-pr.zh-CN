---
title: Lync Server 2013：监视操作系统
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring operating system
ms:assetid: 72406d3e-54c8-4796-8d6d-2144a5b6f030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720918(v=OCS.15)
ms:contentKeyID: 63969617
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea10d7dff41f310e41c1257fa858d0b5d9226bdc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-operating-system-in-lync-server-2013"></a><span data-ttu-id="251bb-102">在 Lync Server 2013 中监视操作系统</span><span class="sxs-lookup"><span data-stu-id="251bb-102">Monitoring operating system in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="251bb-103">_**上次修改的主题：** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="251bb-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="251bb-104">您必须监视 Lync Server 2013 中所有服务器和组件的性能。</span><span class="sxs-lookup"><span data-stu-id="251bb-104">You must monitor the performance of all servers and components in the Lync Server 2013.</span></span> <span data-ttu-id="251bb-105">显然，最重要的组件之一就是操作系统本身。</span><span class="sxs-lookup"><span data-stu-id="251bb-105">Obviously, one of the most important components is the operating system itself.</span></span> <span data-ttu-id="251bb-106">Lync Server 2013 支持 x64 版本：</span><span class="sxs-lookup"><span data-stu-id="251bb-106">Lync Server 2013 supports x64 editions of:</span></span>

  - <span data-ttu-id="251bb-107">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="251bb-107">Windows Server 2008 R2</span></span>

  - <span data-ttu-id="251bb-108">Windows Server 2012 和 Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="251bb-108">Windows Server 2012 and Windows Server 2012 R2</span></span>

<span data-ttu-id="251bb-109">监视操作系统的最透明方法是使用 Windows Server 操作系统管理包。</span><span class="sxs-lookup"><span data-stu-id="251bb-109">The most transparent way to monitor an operating system is by using Windows Server Operating System Management Pack.</span></span> <span data-ttu-id="251bb-110">它提供了有关运行 Windows Server 2012、Windows Server 2012 R2 和 Windows Server 2008 R2 的计算机的基本监控基础知识，如性能、运行状况和可用性。</span><span class="sxs-lookup"><span data-stu-id="251bb-110">It provides the fundamental monitoring basics, such as performance, health, and availability for computers that are running Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span>

<span data-ttu-id="251bb-111">通过检测、发出警报并自动响应重要的事件和性能指示器，这些管理包可减少问题的解决时间，并提高运行 Windows Server 的系统的总体可用性和性能操作系统。</span><span class="sxs-lookup"><span data-stu-id="251bb-111">By detecting, alerting, and automatically responding to important events and performance indicators, these management packs reduce resolution times for issues and increase the overall availability and performance of systems that are running the Windows Server operating systems.</span></span>

<span data-ttu-id="251bb-112">除了适用于 System Center Operations Manager 的相关 Windows Server 管理包之外，还可以使用以下系统工具和资源来监视操作系统的运行状况（具体取决于操作系统版本）。</span><span class="sxs-lookup"><span data-stu-id="251bb-112">Apart from relevant Windows Server management packs for System Center Operations Manager, the following system tools and resources can be used to monitor the health of the operating system (depending on the operating system version).</span></span>

<div>

## <a name="windows-server2008r2"></a><span data-ttu-id="251bb-113">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="251bb-113">Windows Server 2008 R2</span></span>

<span data-ttu-id="251bb-114">Windows Server 2008 R2 包括以下附加功能和工具，可帮助管理员进行基本的操作系统监视和管理：</span><span class="sxs-lookup"><span data-stu-id="251bb-114">Windows Server 2008 R2 includes the following additional features and tools to help administrators with basic operating system monitoring and management:</span></span>

  - <span data-ttu-id="251bb-115">**Windows 资源监视器**是一种功能强大的工具，可用于了解进程和服务如何使用系统资源。</span><span class="sxs-lookup"><span data-stu-id="251bb-115">**Windows Resource Monitor** is a powerful tool for understanding how system resources are used by processes and services.</span></span> <span data-ttu-id="251bb-116">除了实时监视资源使用情况之外，资源监视器还有助于分析无响应的进程，确定哪些应用程序正在使用文件，并控制进程和服务。</span><span class="sxs-lookup"><span data-stu-id="251bb-116">In addition to monitoring resource usage in real time, a Resource Monitor can help analyze unresponsive processes, identify which applications are using files, and control processes and services.</span></span>

  - <span data-ttu-id="251bb-117">**可靠性分析组件**是一个提供有关系统使用情况和可靠性的详细体验信息的内置代理。</span><span class="sxs-lookup"><span data-stu-id="251bb-117">**Reliability Analysis Component** is an in-box agent that provides detailed experience information on system usage and reliability.</span></span> <span data-ttu-id="251bb-118">此信息通过 WMI 接口公开，以使其可供便携式阅读器系统使用。</span><span class="sxs-lookup"><span data-stu-id="251bb-118">This information is exposed through a WMI interface to make it available for consumption by Portable Readers Systems.</span></span> <span data-ttu-id="251bb-119">通过 WMI 接口公开可靠性分析组件，开发人员可以监视和分析应用程序，从而提高可靠性和性能。</span><span class="sxs-lookup"><span data-stu-id="251bb-119">By exposing Reliability Analysis Component through a WMI interface, developers can monitor and analyze applications, increasing reliability and performance.</span></span>

  - <span data-ttu-id="251bb-120">**Windows Server 2008 R2**使用内置的可靠性分析组件来计算可靠性索引，它提供有关一段时间内的总体系统使用情况和稳定性的信息。</span><span class="sxs-lookup"><span data-stu-id="251bb-120">**Windows Server 2008 R2** uses the built-in Reliability Analysis Component to calculate a reliability index, which provides information about overall system usage and stability over time.</span></span> <span data-ttu-id="251bb-121">可靠性分析组件还会跟踪对系统有可能影响稳定性的任何重要更改，如 Windows 更新和应用程序安装。</span><span class="sxs-lookup"><span data-stu-id="251bb-121">The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.</span></span>

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a><span data-ttu-id="251bb-122">Windows Server 2008 Windows 可靠性和性能监视器</span><span class="sxs-lookup"><span data-stu-id="251bb-122">Windows Server 2008 Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="251bb-123">Windows 可靠性和性能监视器是一个 MMC 管理单元，它结合了以前独立工具的功能，包括性能日志和警报、服务器性能顾问和系统监视器。</span><span class="sxs-lookup"><span data-stu-id="251bb-123">Windows Reliability and Performance Monitor is an MMC Snap-in that combines the functionality of previous stand-alone tools including Performance Logs and Alerts, Server Performance Advisor, and System Monitor.</span></span> <span data-ttu-id="251bb-124">它提供了用于自定义性能数据收集和事件跟踪会话的图形界面。</span><span class="sxs-lookup"><span data-stu-id="251bb-124">It provides a graphical interface for customizing performance data collection and Event Trace Sessions.</span></span>

<span data-ttu-id="251bb-125">此外，它还包括可靠性监视器、跟踪系统更改并将其与系统稳定性的变化进行比较的 MMC 管理单元，并提供其关系的图形视图。</span><span class="sxs-lookup"><span data-stu-id="251bb-125">It also includes Reliability Monitor, an MMC Snap-in that tracks changes to the system and compares them to changes in system stability, and it provides a graphical view of their relationship.</span></span>

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a><span data-ttu-id="251bb-126">Windows 可靠性和性能监视器</span><span class="sxs-lookup"><span data-stu-id="251bb-126">Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="251bb-127">虽然 Windows 可靠性和性能监视器组合了一些以前的独立工具（如性能日志和警报）和系统监视器和服务器性能顾问的功能，但它还提供了 Windows Server 2008 的一些新功能，Windows Server 2008 R2，如下所示：</span><span class="sxs-lookup"><span data-stu-id="251bb-127">While Windows Reliability and Performance Monitor combine functionalities of some former stand-alone tools such as Performance Logs and Alerts, and System Monitor and Server Performance Advisor, it also provides some new functionality to Windows Server 2008 and Windows Server 2008 R2, such as the following:</span></span>

  - <span data-ttu-id="251bb-128">数据收集器集</span><span class="sxs-lookup"><span data-stu-id="251bb-128">Data Collector Sets</span></span>

  - <span data-ttu-id="251bb-129">资源视图</span><span class="sxs-lookup"><span data-stu-id="251bb-129">Resource View</span></span>

  - <span data-ttu-id="251bb-130">可靠性监视器</span><span class="sxs-lookup"><span data-stu-id="251bb-130">Reliability Monitor</span></span>

  - <span data-ttu-id="251bb-131">用于创建日志的向导和模板</span><span class="sxs-lookup"><span data-stu-id="251bb-131">Wizards and templates for creating logs</span></span>

<span data-ttu-id="251bb-132">**数据收集器集将**数据收集器分组为可重用的元素，以用于不同的性能监视方案。</span><span class="sxs-lookup"><span data-stu-id="251bb-132">**Data Collector Set** groups data collectors into reusable elements for use with different performance monitoring scenarios.</span></span> <span data-ttu-id="251bb-133">将一组数据收集器存储为数据收集器集后，可以通过单个属性更改将诸如计划等操作应用于整个集。Windows 可靠性和性能监视器包含默认的数据收集器集模板，可帮助系统管理员立即开始收集特定于服务器角色或监视方案的性能数据。</span><span class="sxs-lookup"><span data-stu-id="251bb-133">After a group of data collectors are stored as a Data Collector Set, operations such as scheduling can be applied to the whole set through a single property change.Windows Reliability and Performance Monitor includes default Data Collector Set templates to help system administrators begin immediately collecting performance data that is specific to a server role or monitoring scenario.</span></span>

<span data-ttu-id="251bb-134">Windows 可靠性和性能监视器的主页是新的 "**资源视图**" 屏幕，它提供了 CPU、磁盘、网络和内存使用率的实时图形概述。</span><span class="sxs-lookup"><span data-stu-id="251bb-134">The home page of Windows Reliability and Performance Monitor is the new **Resource View** screen, which provides a real-time graphical overview of CPU, disk, network, and memory usage.</span></span> <span data-ttu-id="251bb-135">通过展开其中的每个受监视的元素，系统管理员可以确定哪些进程正在使用哪些资源。</span><span class="sxs-lookup"><span data-stu-id="251bb-135">By expanding each of these monitored elements, system administrators can identify which processes are using which resources.</span></span> <span data-ttu-id="251bb-136">在 Windows 的早期版本中，此实时特定于进程的数据仅在任务管理器的有限窗体中可用。</span><span class="sxs-lookup"><span data-stu-id="251bb-136">In earlier versions of Windows, this real-time, process-specific data was available only in limited form in Task Manager.</span></span>

<span data-ttu-id="251bb-137">**可靠性监视器**会计算系统稳定性指数，以反映是否因降低了系统的可靠性而引起的意外问题。</span><span class="sxs-lookup"><span data-stu-id="251bb-137">**Reliability Monitor** calculates a System Stability Index that reflects whether unexpected issues reduced the reliability of the system.</span></span> <span data-ttu-id="251bb-138">随着时间的推移，稳定性指数的图形会快速标识问题开始发生的日期。</span><span class="sxs-lookup"><span data-stu-id="251bb-138">A graph of the Stability Index over time quickly identifies dates when issues began to occur.</span></span> <span data-ttu-id="251bb-139">随附的系统稳定性报告提供了有助于解决可靠性降低的原因的详细信息。</span><span class="sxs-lookup"><span data-stu-id="251bb-139">The accompanying System Stability Report provides details to help troubleshoot the cause of reduced reliability.</span></span> <span data-ttu-id="251bb-140">通过查看对系统的更改（应用程序的安装或删除、操作系统的更新、操作系统的新增或修改）以及故障（应用程序故障、操作系统崩溃或硬件故障），策略解决问题可以快速制定。</span><span class="sxs-lookup"><span data-stu-id="251bb-140">By viewing changes to the system (installation or removal of applications, updates to the operating system, or addition or modification of drivers) side by side with failures (application failures, operating system crashes, or hardware failures), a strategy for addressing the issues can be developed quickly.</span></span>

<span data-ttu-id="251bb-141">现在可以通过**向导界面**将计数器添加到日志文件，并安排它们的启动、停止和持续时间。</span><span class="sxs-lookup"><span data-stu-id="251bb-141">Adding counters to log files and scheduling their start, stop, and duration can now be performed through a **Wizard interface**.</span></span> <span data-ttu-id="251bb-142">此外，将此配置另存为模板使系统管理员能够在其他计算机上收集相同的日志，而无需重复数据收集器选择和计划过程。</span><span class="sxs-lookup"><span data-stu-id="251bb-142">In addition, saving this configuration as a template enables system administrators to collect the same log on other computers without repeating the data collector selection and scheduling processes.</span></span> <span data-ttu-id="251bb-143">性能日志和警报功能并入了 Windows 可靠性和性能监视器中，可用于任何数据收集器集。</span><span class="sxs-lookup"><span data-stu-id="251bb-143">Performance Logs and Alerts features were incorporated into the Windows Reliability and Performance Monitor for use with any Data Collector Set.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

