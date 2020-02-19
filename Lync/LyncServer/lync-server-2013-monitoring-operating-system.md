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

# <a name="monitoring-operating-system-in-lync-server-2013"></a>在 Lync Server 2013 中监视操作系统

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2015-01-26_

您必须监视 Lync Server 2013 中所有服务器和组件的性能。 显然，最重要的组件之一就是操作系统本身。 Lync Server 2013 支持 x64 版本：

  - Windows Server 2008 R2

  - Windows Server 2012 和 Windows Server 2012 R2

监视操作系统的最透明方法是使用 Windows Server 操作系统管理包。 它提供了有关运行 Windows Server 2012、Windows Server 2012 R2 和 Windows Server 2008 R2 的计算机的基本监控基础知识，如性能、运行状况和可用性。

通过检测、发出警报并自动响应重要的事件和性能指示器，这些管理包可减少问题的解决时间，并提高运行 Windows Server 的系统的总体可用性和性能操作系统。

除了适用于 System Center Operations Manager 的相关 Windows Server 管理包之外，还可以使用以下系统工具和资源来监视操作系统的运行状况（具体取决于操作系统版本）。

<div>

## <a name="windows-server2008r2"></a>Windows Server 2008 R2

Windows Server 2008 R2 包括以下附加功能和工具，可帮助管理员进行基本的操作系统监视和管理：

  - **Windows 资源监视器**是一种功能强大的工具，可用于了解进程和服务如何使用系统资源。 除了实时监视资源使用情况之外，资源监视器还有助于分析无响应的进程，确定哪些应用程序正在使用文件，并控制进程和服务。

  - **可靠性分析组件**是一个提供有关系统使用情况和可靠性的详细体验信息的内置代理。 此信息通过 WMI 接口公开，以使其可供便携式阅读器系统使用。 通过 WMI 接口公开可靠性分析组件，开发人员可以监视和分析应用程序，从而提高可靠性和性能。

  - **Windows Server 2008 R2**使用内置的可靠性分析组件来计算可靠性索引，它提供有关一段时间内的总体系统使用情况和稳定性的信息。 可靠性分析组件还会跟踪对系统有可能影响稳定性的任何重要更改，如 Windows 更新和应用程序安装。

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a>Windows Server 2008 Windows 可靠性和性能监视器

Windows 可靠性和性能监视器是一个 MMC 管理单元，它结合了以前独立工具的功能，包括性能日志和警报、服务器性能顾问和系统监视器。 它提供了用于自定义性能数据收集和事件跟踪会话的图形界面。

此外，它还包括可靠性监视器、跟踪系统更改并将其与系统稳定性的变化进行比较的 MMC 管理单元，并提供其关系的图形视图。

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a>Windows 可靠性和性能监视器

虽然 Windows 可靠性和性能监视器组合了一些以前的独立工具（如性能日志和警报）和系统监视器和服务器性能顾问的功能，但它还提供了 Windows Server 2008 的一些新功能，Windows Server 2008 R2，如下所示：

  - 数据收集器集

  - 资源视图

  - 可靠性监视器

  - 用于创建日志的向导和模板

**数据收集器集将**数据收集器分组为可重用的元素，以用于不同的性能监视方案。 将一组数据收集器存储为数据收集器集后，可以通过单个属性更改将诸如计划等操作应用于整个集。Windows 可靠性和性能监视器包含默认的数据收集器集模板，可帮助系统管理员立即开始收集特定于服务器角色或监视方案的性能数据。

Windows 可靠性和性能监视器的主页是新的 "**资源视图**" 屏幕，它提供了 CPU、磁盘、网络和内存使用率的实时图形概述。 通过展开其中的每个受监视的元素，系统管理员可以确定哪些进程正在使用哪些资源。 在 Windows 的早期版本中，此实时特定于进程的数据仅在任务管理器的有限窗体中可用。

**可靠性监视器**会计算系统稳定性指数，以反映是否因降低了系统的可靠性而引起的意外问题。 随着时间的推移，稳定性指数的图形会快速标识问题开始发生的日期。 随附的系统稳定性报告提供了有助于解决可靠性降低的原因的详细信息。 通过查看对系统的更改（应用程序的安装或删除、操作系统的更新、操作系统的新增或修改）以及故障（应用程序故障、操作系统崩溃或硬件故障），策略解决问题可以快速制定。

现在可以通过**向导界面**将计数器添加到日志文件，并安排它们的启动、停止和持续时间。 此外，将此配置另存为模板使系统管理员能够在其他计算机上收集相同的日志，而无需重复数据收集器选择和计划过程。 性能日志和警报功能并入了 Windows 可靠性和性能监视器中，可用于任何数据收集器集。

</div>

</div>

<span> </span>

</div>

</div>

</div>

