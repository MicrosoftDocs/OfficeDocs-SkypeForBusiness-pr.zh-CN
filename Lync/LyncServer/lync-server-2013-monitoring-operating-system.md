---
title: Lync Server 2013：监视操作系统
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring operating system
ms:assetid: 72406d3e-54c8-4796-8d6d-2144a5b6f030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720918(v=OCS.15)
ms:contentKeyID: 63969617
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2f8124afcf2d1acbde3518ff625d528d6e34a3e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-operating-system-in-lync-server-2013"></a><span data-ttu-id="5acc3-102">在 Lync Server 2013 中监视操作系统</span><span class="sxs-lookup"><span data-stu-id="5acc3-102">Monitoring operating system in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5acc3-103">_**主题上次修改时间:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="5acc3-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="5acc3-104">您必须监视 Lync Server 2013 中所有服务器和组件的性能。</span><span class="sxs-lookup"><span data-stu-id="5acc3-104">You must monitor the performance of all servers and components in the Lync Server 2013.</span></span> <span data-ttu-id="5acc3-105">很明显，其中一个最重要的组件是操作系统本身。</span><span class="sxs-lookup"><span data-stu-id="5acc3-105">Obviously, one of the most important components is the operating system itself.</span></span> <span data-ttu-id="5acc3-106">Lync Server 2013 支持 x64 版本:</span><span class="sxs-lookup"><span data-stu-id="5acc3-106">Lync Server 2013 supports x64 editions of:</span></span>

  - <span data-ttu-id="5acc3-107">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="5acc3-107">Windows Server 2008 R2</span></span>

  - <span data-ttu-id="5acc3-108">Windows Server 2012 和 Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="5acc3-108">Windows Server 2012 and Windows Server 2012 R2</span></span>

<span data-ttu-id="5acc3-109">监视操作系统的最透明方法是使用 Windows Server 操作系统管理包。</span><span class="sxs-lookup"><span data-stu-id="5acc3-109">The most transparent way to monitor an operating system is by using Windows Server Operating System Management Pack.</span></span> <span data-ttu-id="5acc3-110">它提供了基本监视基础知识, 例如运行 Windows Server 2012、Windows Server 2012 R2 和 Windows Server 2008 R2 的计算机的性能、运行状况和可用性。</span><span class="sxs-lookup"><span data-stu-id="5acc3-110">It provides the fundamental monitoring basics, such as performance, health, and availability for computers that are running Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span>

<span data-ttu-id="5acc3-111">通过检测、报警和自动响应重要的事件和性能指示器, 这些管理包可减少问题的解决时间, 并提高运行 Windows Server 的系统的整体可用性和性能操作系统。</span><span class="sxs-lookup"><span data-stu-id="5acc3-111">By detecting, alerting, and automatically responding to important events and performance indicators, these management packs reduce resolution times for issues and increase the overall availability and performance of systems that are running the Windows Server operating systems.</span></span>

<span data-ttu-id="5acc3-112">除了适用于 System Center Operations Manager 的相关 Windows Server 管理包之外, 还可以使用以下系统工具和资源来监视操作系统的运行状况 (具体取决于操作系统版本)。</span><span class="sxs-lookup"><span data-stu-id="5acc3-112">Apart from relevant Windows Server management packs for System Center Operations Manager, the following system tools and resources can be used to monitor the health of the operating system (depending on the operating system version).</span></span>

<div>

## <a name="windows-server2008r2"></a><span data-ttu-id="5acc3-113">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="5acc3-113">Windows Server 2008 R2</span></span>

<span data-ttu-id="5acc3-114">Windows Server 2008 R2 包含以下附加功能和工具, 可帮助管理员进行基本的操作系统监视和管理:</span><span class="sxs-lookup"><span data-stu-id="5acc3-114">Windows Server 2008 R2 includes the following additional features and tools to help administrators with basic operating system monitoring and management:</span></span>

  - <span data-ttu-id="5acc3-p103">**Windows 资源监视器**是一种功能强大的工具，可用于了解进程和服务是如何使用系统资源的。除了实时监视资源使用状况之外，资源监视器可帮助分析无响应的进程、识别哪些应用程序正在使用文件以及控制进程和服务。</span><span class="sxs-lookup"><span data-stu-id="5acc3-p103">**Windows Resource Monitor** is a powerful tool for understanding how system resources are used by processes and services. In addition to monitoring resource usage in real time, a Resource Monitor can help analyze unresponsive processes, identify which applications are using files, and control processes and services.</span></span>

  - <span data-ttu-id="5acc3-p104">**可靠性分析组件**是一个内置代理，它提供有关系统使用和可靠性的详细体验信息。此信息通过 WMI 接口呈现，可供便携式阅读器系统使用。通过 WMI 接口呈现可靠性分析组件，开发人员可以监视和分析应用程序，从而提高可靠性和性能。</span><span class="sxs-lookup"><span data-stu-id="5acc3-p104">**Reliability Analysis Component** is an in-box agent that provides detailed experience information on system usage and reliability. This information is exposed through a WMI interface to make it available for consumption by Portable Readers Systems. By exposing Reliability Analysis Component through a WMI interface, developers can monitor and analyze applications, increasing reliability and performance.</span></span>

  - <span data-ttu-id="5acc3-120">**Windows Server 2008 R2**使用内置的可靠性分析组件来计算可靠性索引, 该索引提供有关一段时间内的整体系统使用情况和稳定性的信息。</span><span class="sxs-lookup"><span data-stu-id="5acc3-120">**Windows Server 2008 R2** uses the built-in Reliability Analysis Component to calculate a reliability index, which provides information about overall system usage and stability over time.</span></span> <span data-ttu-id="5acc3-121">The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.</span><span class="sxs-lookup"><span data-stu-id="5acc3-121">The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.</span></span>

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a><span data-ttu-id="5acc3-122">Windows Server 2008 Windows 可靠性和性能监视器</span><span class="sxs-lookup"><span data-stu-id="5acc3-122">Windows Server 2008 Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="5acc3-p106">Windows 可靠性和性能监视器是一个 MMC 管理单元，它融合了以前的独立工具（包括性能日志和警报、Server Performance Advisor 和系统监视器）的功能。它提供用于自定义性能数据收集和事件跟踪会话的图形界面。</span><span class="sxs-lookup"><span data-stu-id="5acc3-p106">Windows Reliability and Performance Monitor is an MMC Snap-in that combines the functionality of previous stand-alone tools including Performance Logs and Alerts, Server Performance Advisor, and System Monitor. It provides a graphical interface for customizing performance data collection and Event Trace Sessions.</span></span>

<span data-ttu-id="5acc3-125">它还包括可靠性监视器，该 MMC 管理单元跟踪系统更改并将它们与系统稳定性进行比较，提供其关系的图形视图。</span><span class="sxs-lookup"><span data-stu-id="5acc3-125">It also includes Reliability Monitor, an MMC Snap-in that tracks changes to the system and compares them to changes in system stability, and it provides a graphical view of their relationship.</span></span>

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a><span data-ttu-id="5acc3-126">Windows 可靠性和性能监视器</span><span class="sxs-lookup"><span data-stu-id="5acc3-126">Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="5acc3-127">虽然 Windows 可靠性和性能监视器结合了一些以前的独立工具 (如性能日志和警报) 和系统监视器和服务器性能顾问的功能, 但它还提供了 Windows Server 2008 的一些新功能和Windows Server 2008 R2, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="5acc3-127">While Windows Reliability and Performance Monitor combine functionalities of some former stand-alone tools such as Performance Logs and Alerts, and System Monitor and Server Performance Advisor, it also provides some new functionality to Windows Server 2008 and Windows Server 2008 R2, such as the following:</span></span>

  - <span data-ttu-id="5acc3-128">数据收集器集</span><span class="sxs-lookup"><span data-stu-id="5acc3-128">Data Collector Sets</span></span>

  - <span data-ttu-id="5acc3-129">资源视图</span><span class="sxs-lookup"><span data-stu-id="5acc3-129">Resource View</span></span>

  - <span data-ttu-id="5acc3-130">可靠性监视器</span><span class="sxs-lookup"><span data-stu-id="5acc3-130">Reliability Monitor</span></span>

  - <span data-ttu-id="5acc3-131">用于创建日志的向导和模板</span><span class="sxs-lookup"><span data-stu-id="5acc3-131">Wizards and templates for creating logs</span></span>

<span data-ttu-id="5acc3-p107">**数据收集器集**将数据收集器组合成可重复使用的元素来用于不同的性能监视方案。在一组数据收集器存储为数据收集器集之后，日程排定等操作可以通过单个属性更改应用于整个集合。Windows 可靠性和性能监视器包括默认数据收集器集模板，可帮助系统管理员立即开始收集特定于服务角色或监视方案的性能数据。</span><span class="sxs-lookup"><span data-stu-id="5acc3-p107">**Data Collector Set** groups data collectors into reusable elements for use with different performance monitoring scenarios. After a group of data collectors are stored as a Data Collector Set, operations such as scheduling can be applied to the whole set through a single property change.Windows Reliability and Performance Monitor includes default Data Collector Set templates to help system administrators begin immediately collecting performance data that is specific to a server role or monitoring scenario.</span></span>

<span data-ttu-id="5acc3-p108">Windows 可靠性和性能监视器的主页是新的“资源视图”\*\*\*\* 屏幕，它提供 CPU、磁盘、网络和内存使用状况的实时图形视图。通过扩展这些受监控的元素，系统管理员可以识别哪些进程正在使用哪些资源。 在 Windows 的早期版本中，此特定于进程的实时数据只能以有限方式在任务管理器中使用。</span><span class="sxs-lookup"><span data-stu-id="5acc3-p108">The home page of Windows Reliability and Performance Monitor is the new **Resource View** screen, which provides a real-time graphical overview of CPU, disk, network, and memory usage. By expanding each of these monitored elements, system administrators can identify which processes are using which resources. In earlier versions of Windows, this real-time, process-specific data was available only in limited form in Task Manager.</span></span>

<span data-ttu-id="5acc3-p109">**可靠性监视器**计算性能稳定性指数，它反映非预期问题是否会降低系统的可靠性。一段时间内的稳定性指数图形会快速识别问题开始发生的日期。随附的系统可靠性报告提供的详细信息可帮助解决可靠性降低的原因。通过并排查看系统更改（安装或删除应用程序、更新操作系统或者添加或修改驱动程序）与故障（应用程序故障、操作系统崩溃或硬件故障），可以快速制定解决问题的战略。</span><span class="sxs-lookup"><span data-stu-id="5acc3-p109">**Reliability Monitor** calculates a System Stability Index that reflects whether unexpected issues reduced the reliability of the system. A graph of the Stability Index over time quickly identifies dates when issues began to occur. The accompanying System Stability Report provides details to help troubleshoot the cause of reduced reliability. By viewing changes to the system (installation or removal of applications, updates to the operating system, or addition or modification of drivers) side by side with failures (application failures, operating system crashes, or hardware failures), a strategy for addressing the issues can be developed quickly.</span></span>

<span data-ttu-id="5acc3-p110">将计数器添加到日志文件并计划其开始时间、停止时间和持续时间现在可通过**向导界面**执行。此外，将此配置另存为模板使系统管理员能够在其他计算机上收集相同日志，而不必重复数据收集器选择和计划过程。性能日志和警报功能已融合到 Windows 可靠性和性能监视器中，可对任何数据收集器集使用。</span><span class="sxs-lookup"><span data-stu-id="5acc3-p110">Adding counters to log files and scheduling their start, stop, and duration can now be performed through a **Wizard interface**. In addition, saving this configuration as a template enables system administrators to collect the same log on other computers without repeating the data collector selection and scheduling processes. Performance Logs and Alerts features were incorporated into the Windows Reliability and Performance Monitor for use with any Data Collector Set.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

