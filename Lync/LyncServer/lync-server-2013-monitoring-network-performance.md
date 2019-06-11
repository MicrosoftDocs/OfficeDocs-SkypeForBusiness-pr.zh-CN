---
title: Lync Server 2013：监视网络性能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring network performance
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720923(v=OCS.15)
ms:contentKeyID: 63969647
ms.date: 04/27/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2fa3c2685b4da32d5f2e3f123a938920b5ce9f7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826715"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-network-performance-in-lync-server-2013"></a><span data-ttu-id="c444c-102">在  Lync Server 2013 中监视网络性能</span><span class="sxs-lookup"><span data-stu-id="c444c-102">Monitoring network performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c444c-103">_**主题上次修改时间:** 2016-04-27_</span><span class="sxs-lookup"><span data-stu-id="c444c-103">_**Topic Last Modified:** 2016-04-27_</span></span>

<span data-ttu-id="c444c-104">Lync Server 2013 是一种实时通信技术, 它在很大程度上依赖于网络来启用用户之间的通信-通过即时消息 (IM)、语音呼叫或视频通信。</span><span class="sxs-lookup"><span data-stu-id="c444c-104">Lync Server 2013 is a real-time communications technology that relies heavily on the network to enable communication between users—either through instant messaging (IM), voice calls, or video communication.</span></span> <span data-ttu-id="c444c-105">因此, 不断监视网络性能以帮助确保用户选择的通信模态可提供最佳体验非常重要。</span><span class="sxs-lookup"><span data-stu-id="c444c-105">It is therefore important to monitor the network performance continuously to help guarantee that a user’s chosen communication modality provides the best possible experience.</span></span>

<span data-ttu-id="c444c-106">可以在两个级别测量网络性能:</span><span class="sxs-lookup"><span data-stu-id="c444c-106">Network performance can be measured at two levels:</span></span>

  - <span data-ttu-id="c444c-107">**总体网络性能**   这一级别的性能测量将使组织能够创建其网络的 "大型图片" 视图, 并且通常通过第三方网络监视系统实现。</span><span class="sxs-lookup"><span data-stu-id="c444c-107">**Overall network performance**   This level of performance measurement will allow an organization to create a "big-picture" view of their network and is usually implemented through third-party network monitoring systems.</span></span> <span data-ttu-id="c444c-108">这些系统将从远程网络设备 (如路由器) 接收性能和容量数据, 并在整个网络中切换, 从而允许管理员确定任何给定网络组件在一天内的运行状况。</span><span class="sxs-lookup"><span data-stu-id="c444c-108">These systems will receive performance and capacity data from remote network devices such as routers and switched throughout the network to allow administrators to determine the health of any given network component at any time of day.</span></span>

  - <span data-ttu-id="c444c-109">**单个服务器性能**   此级别的性能测量值限制为特定服务器, 并将帮助管理员评估特定服务器的网络性能, 以帮助解决特定性能在某一给定时间段内处理其各个服务器的性能, 作为容量计划过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="c444c-109">**Individual server performance**   This level of performance measurement is limited to a specific server and will help administrators with gauging the network performance of a specific server to either help with troubleshooting a specific performance issue or to gauge the respective server’s performance over a given period as part of a capacity planning process.</span></span>

<span data-ttu-id="c444c-110">你可以使用以下部分中所述的工具监视网络。</span><span class="sxs-lookup"><span data-stu-id="c444c-110">You can monitor the network by using the tools described in the following sections.</span></span>

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a><span data-ttu-id="c444c-111">用于总体网络性能监视的工具</span><span class="sxs-lookup"><span data-stu-id="c444c-111">Tools for Overall Network Performance Monitoring</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="c444c-112">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="c444c-112">System Center Operations Manager 2012</span></span>

<span data-ttu-id="c444c-113">System Center Operations Manager 提供了可轻松自定义和扩展的端到端服务管理, 可在 IT 环境中提高服务级别。</span><span class="sxs-lookup"><span data-stu-id="c444c-113">System Center Operations Manager provides end-to-end service management that is easy to customize and extend for improved service levels across an IT environment.</span></span> <span data-ttu-id="c444c-114">这使操作和 IT 管理团队能够识别和解决影响分布式 IT 服务运行状况的问题。</span><span class="sxs-lookup"><span data-stu-id="c444c-114">This enables Operations and IT Management teams to identify, and resolve issues affecting the health of distributed IT services.</span></span> <span data-ttu-id="c444c-115">端到端服务管理不限于基于 Microsoft 的环境。</span><span class="sxs-lookup"><span data-stu-id="c444c-115">End-to-end service management is not restricted to Microsoft-based environments.</span></span> <span data-ttu-id="c444c-116">支持用于管理的 Web 服务 (WS-MANAGEMENT)、简单网络管理协议 (SNMP) 和合作伙伴解决方案允许不运行 Microsoft 操作系统和硬件的系统包含在系统中心内的服务监视中Operations Manager 2012。</span><span class="sxs-lookup"><span data-stu-id="c444c-116">Support for Web Services for Management (WS-Management), Simple Network Management Protocol (SNMP), and partner solutions allow for systems that do not run Microsoft operating systems and hardware to be included in service monitoring within System Center Operations Manager 2012.</span></span>

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a><span data-ttu-id="c444c-117">System Center Operations Manager 2012 和第三方网络管理解决方案</span><span class="sxs-lookup"><span data-stu-id="c444c-117">System Center Operations Manager 2012 and Third-Party Network Management Solutions</span></span>

<span data-ttu-id="c444c-118">**Emc Smarts**   面向 Operations Manager 的解决方案可帮助你在整个服务级别中快速解决影响服务级别的问题。</span><span class="sxs-lookup"><span data-stu-id="c444c-118">**EMC Smarts**   EMC Solutions for Operations Manager help you quickly resolve issues affecting service levels throughout.</span></span> <span data-ttu-id="c444c-119">通过使用 EMC 针对 Operations Manager 的解决方案, 你可以使用一个集成、自动化的解决方案管理和监控整个 IT 服务链。</span><span class="sxs-lookup"><span data-stu-id="c444c-119">By using EMC Solutions for Operations Manager, you can manage and monitor your whole IT service chain with one integrated, automated solution.</span></span> <span data-ttu-id="c444c-120">你可以轻松地确定性能和可用性问题的根本原因, 并更快地解决这些问题, 从而降低效果和成本。</span><span class="sxs-lookup"><span data-stu-id="c444c-120">You'll easily identify the root causes of performance and availability issues, and resolve them faster which reduces effects and costs.</span></span> <span data-ttu-id="c444c-121">关键好处包括以下几项:</span><span class="sxs-lookup"><span data-stu-id="c444c-121">Key benefits include the following:</span></span>

  - <span data-ttu-id="c444c-122">高级、易于使用的管理侧重于提供战略商业价值, 而不是手动排序和筛选混乱的警报。</span><span class="sxs-lookup"><span data-stu-id="c444c-122">Advanced, easy-to-use management   Focus on delivering strategic business value instead of manually sorting and filtering confusing alerts.</span></span>

  - <span data-ttu-id="c444c-123">**更快的解决方案**   解决 IT 问题并更快地响应业务需求, 降低了影响和成本。</span><span class="sxs-lookup"><span data-stu-id="c444c-123">**Faster resolution**   Solve IT issues and respond to business needs faster, reducing effect and cost.</span></span>

  - <span data-ttu-id="c444c-124">**简化的操作**   通过组合多个管理工具、应用程序和终端来避免 IT 复杂性。</span><span class="sxs-lookup"><span data-stu-id="c444c-124">**Streamlined operations**   Avoid IT complexity by combining multiple management tools, applications, and terminals.</span></span>

<span data-ttu-id="c444c-125">详细信息可在此处找到:</span><span class="sxs-lookup"><span data-stu-id="c444c-125">More information can be found here:</span></span>

[<span data-ttu-id="c444c-126">Microsoft System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="c444c-126">Microsoft System Center Operations Manager</span></span>](http://go.microsoft.com/fwlink/p/?linkid=243651)

[<span data-ttu-id="c444c-127">Microsoft System Center Operations Manager 解决方案</span><span class="sxs-lookup"><span data-stu-id="c444c-127">Solutions for Microsoft System Center Operations Manager</span></span>](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a><span data-ttu-id="c444c-128">第三方解决方案</span><span class="sxs-lookup"><span data-stu-id="c444c-128">Third-Party Solutions</span></span>

<span data-ttu-id="c444c-129">**Hp 网络管理中心 (以前称为 HP OpenView)**   [HP 网络管理中心](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__)提供集成的故障和性能管理, 以提高网络可用性和性能。</span><span class="sxs-lookup"><span data-stu-id="c444c-129">**HP Network Management Center (previously known as HP OpenView)**   [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) provides integrated fault and performance management to improve network availability and performance.</span></span> <span data-ttu-id="c444c-130">网络管理中心是 HP 自动化网络管理解决方案的一部分, 它统一了故障、性能、配置和更改管理。</span><span class="sxs-lookup"><span data-stu-id="c444c-130">Network Management Center is part of the HP automated network management solution that unifies fault, performance, configuration, and change management.</span></span>

<span data-ttu-id="c444c-131">**适用于企业的 cisco 网络管理和自动化产品**   , cisco 拥有多种管理产品, 包括 CiscoWorks LAN 管理解决方案和 Cisco 网络分析模块, 以帮助提高运营效率和减少网络停机时间。</span><span class="sxs-lookup"><span data-stu-id="c444c-131">**Cisco Network Management and Automation products**   For the Enterprise, Cisco has several management products available including CiscoWorks LAN Management Solution and Cisco Network Analysis Module, to help improve operational efficiency and reduce network downtime.</span></span> <span data-ttu-id="c444c-132">有关这些产品的其他数据, 请参阅 Cisco 网站[http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html)。</span><span class="sxs-lookup"><span data-stu-id="c444c-132">For additional data on these products, refer to the Cisco website at [http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html).</span></span>

<span data-ttu-id="c444c-133">简单网络管理协议 (SNMP) 简单网络管理协议 (SNMP) 是一种网络管理标准, 用于定义管理 TCP/IP 网络的策略。</span><span class="sxs-lookup"><span data-stu-id="c444c-133">Simple Network Management Protocol (SNMP)   Simple Network Management Protocol (SNMP) is a network management standard that defines a strategy for managing TCP/IP networks.</span></span> <span data-ttu-id="c444c-134">SNMP 使你能够捕获有关网络的配置和状态信息, 并将信息发送到指定的计算机以进行事件监视。</span><span class="sxs-lookup"><span data-stu-id="c444c-134">SNMP enables you to capture configuration and status information about the network, and send the information to a designated computer for event monitoring.</span></span> <span data-ttu-id="c444c-135">此基于标准的网络管理协议使用分布式体系结构, 包括以下内容:</span><span class="sxs-lookup"><span data-stu-id="c444c-135">This standards based network management protocol uses a distributed architecture that includes the following:</span></span>

  - <span data-ttu-id="c444c-136">多个托管节点, 每个节点都有一个称为代理的 SNMP 实体, 可提供对管理规范的远程访问。</span><span class="sxs-lookup"><span data-stu-id="c444c-136">Multiple managed nodes, each with an SNMP entity called an agent which provides remote access to management instrumentation.</span></span>

  - <span data-ttu-id="c444c-137">至少一个名为 manager 的 SNMP 实体, 它运行管理应用程序来监视和控制托管元素。</span><span class="sxs-lookup"><span data-stu-id="c444c-137">At least one SNMP entity known as a manager which runs management applications to monitor and control managed elements.</span></span> <span data-ttu-id="c444c-138">托管元素是诸如主机、路由器等设备。</span><span class="sxs-lookup"><span data-stu-id="c444c-138">Managed elements are devices such as hosts, routers, and so on.</span></span> <span data-ttu-id="c444c-139">通过访问其管理信息来监视和控制它们。</span><span class="sxs-lookup"><span data-stu-id="c444c-139">They are monitored and controlled by accessing their management information.</span></span>

  - <span data-ttu-id="c444c-140">管理协议 SNMP 用于在管理工作站和代理之间交流管理信息。</span><span class="sxs-lookup"><span data-stu-id="c444c-140">A management protocol, SNMP, is used to communicate management information between the management stations and agents.</span></span> <span data-ttu-id="c444c-141">管理信息指的是驻留在虚拟信息存储中的托管对象的集合, 称为管理信息基础 (MIB)。</span><span class="sxs-lookup"><span data-stu-id="c444c-141">Management information refers to a collection of managed objects that live in a virtual information store called a Management Information Base (MIB).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c444c-142">上面提供了第三方网络监视解决方案的示例。</span><span class="sxs-lookup"><span data-stu-id="c444c-142">Examples of third-party network monitoring solutions are provided above.</span></span> <span data-ttu-id="c444c-143">此列表不是明确的, Microsoft 不支持任何特定的供应商解决方案。</span><span class="sxs-lookup"><span data-stu-id="c444c-143">This list is not definitive and Microsoft does not favor any specific vendor solution.</span></span> <span data-ttu-id="c444c-144">咨询网络服务提供商和您的相应技术提供商, 以确定您的组织的最佳网络监控解决方案。</span><span class="sxs-lookup"><span data-stu-id="c444c-144">Consult with a network service provider and or your respective technology provider to determine the best network monitoring solution for your organization.</span></span>



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a><span data-ttu-id="c444c-145">用于监视个人服务器网络性能的工具</span><span class="sxs-lookup"><span data-stu-id="c444c-145">Tools for Monitoring Individual Server Network Performance</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="c444c-146">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="c444c-146">System Center Operations Manager 2012</span></span>

<span data-ttu-id="c444c-147">System Center Operations Manager 2012 允许管理员通过 Windows Server 2012 管理包查看单个服务器的网络性能: Windows Server 操作系统管理包包含 "性能" 管理包这将允许管理员监视网络适配器性能和适配器运行状况。</span><span class="sxs-lookup"><span data-stu-id="c444c-147">System Center Operations Manager 2012 would allow administrators to view network performance of individual servers through the Windows Server 2012 Management Pack: The Windows Server operating system management pack includes a "Performance" management pack that would allow administrators to monitor Network Adapter performance and adapter health.</span></span>

</div>

<div>

## <a name="windows-network-monitor"></a><span data-ttu-id="c444c-148">Windows 网络监视器</span><span class="sxs-lookup"><span data-stu-id="c444c-148">Windows Network Monitor</span></span>

<span data-ttu-id="c444c-149">收集、显示、分析服务器上的资源使用情况, 并测量网络流量。</span><span class="sxs-lookup"><span data-stu-id="c444c-149">Collects, displays, analyzes resource usage on a server, and measures network traffic.</span></span> <span data-ttu-id="c444c-150">网络监视器以独占方式监视网络活动。</span><span class="sxs-lookup"><span data-stu-id="c444c-150">Network Monitor exclusively monitors network activity.</span></span> <span data-ttu-id="c444c-151">通过捕获和分析网络数据并将此数据与性能日志配合使用, 你可以确定网络使用情况、识别网络问题并预测未来的网络需求。</span><span class="sxs-lookup"><span data-stu-id="c444c-151">By capturing and analyzing network data, and using this data with performance logs, you can determine the network usage, identify network issues, and forecast future network needs.</span></span>

<span data-ttu-id="c444c-152">有关网络监视器3.4 的详细信息, 以及了解如何安装和配置网络监视器以及捕获和分析数据, 请查看此会话: 网络监视器3.3 概述。</span><span class="sxs-lookup"><span data-stu-id="c444c-152">For more information about Network Monitor 3.4, and to learn how to install and configure Network Monitor and capture and analyze data, review this session: Network Monitor 3.3 Overview.</span></span> <span data-ttu-id="c444c-153">此外, 还可查看[网络监视器博客](http://blogs.technet.com/b/netmon/)。</span><span class="sxs-lookup"><span data-stu-id="c444c-153">Also, review the [Network Monitor blog](http://blogs.technet.com/b/netmon/).</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

