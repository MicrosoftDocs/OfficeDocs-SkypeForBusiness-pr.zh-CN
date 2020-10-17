---
title: Lync Server 2013：监视网络性能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring network performance
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720923(v=OCS.15)
ms:contentKeyID: 63969647
ms.date: 04/27/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efeba476609ad293cd94e67f8dfdbe674b42f3f6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500639"
---
# <a name="monitoring-network-performance-in-lync-server-2013"></a><span data-ttu-id="e4337-102">在 Lync Server 2013 中监视网络性能</span><span class="sxs-lookup"><span data-stu-id="e4337-102">Monitoring network performance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4337-103">_**上次修改的主题：** 2016-04-27_</span><span class="sxs-lookup"><span data-stu-id="e4337-103">_**Topic Last Modified:** 2016-04-27_</span></span>

<span data-ttu-id="e4337-104">Lync Server 2013 是一种实时通信技术，它在很大程度上依赖于网络以启用用户之间的通信—通过即时消息 (IM) 、语音呼叫或视频通信。</span><span class="sxs-lookup"><span data-stu-id="e4337-104">Lync Server 2013 is a real-time communications technology that relies heavily on the network to enable communication between users—either through instant messaging (IM), voice calls, or video communication.</span></span> <span data-ttu-id="e4337-105">因此，不断监视网络性能以确保用户选择的通信模态能够提供最佳体验，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="e4337-105">It is therefore important to monitor the network performance continuously to help guarantee that a user’s chosen communication modality provides the best possible experience.</span></span>

<span data-ttu-id="e4337-106">可以在两个级别衡量网络性能：</span><span class="sxs-lookup"><span data-stu-id="e4337-106">Network performance can be measured at two levels:</span></span>

  - <span data-ttu-id="e4337-107">**总体网络性能**    这一级别的性能测量将允许组织创建网络的 "大图片" 视图，通常通过第三方网络监视系统实现。</span><span class="sxs-lookup"><span data-stu-id="e4337-107">**Overall network performance**   This level of performance measurement will allow an organization to create a "big-picture" view of their network and is usually implemented through third-party network monitoring systems.</span></span> <span data-ttu-id="e4337-108">这些系统将接收来自远程网络设备（如路由器）的性能和容量数据，并在整个网络中进行切换，使管理员能够在一天的任何时间确定任何给定网络组件的运行状况。</span><span class="sxs-lookup"><span data-stu-id="e4337-108">These systems will receive performance and capacity data from remote network devices such as routers and switched throughout the network to allow administrators to determine the health of any given network component at any time of day.</span></span>

  - <span data-ttu-id="e4337-109">**单个服务器性能**    此性能度量级别仅限于特定服务器，可帮助管理员将特定服务器的网络性能 gauging，以帮助解决特定的性能问题，或在指定时间段内评估其各个服务器的性能，作为容量规划过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="e4337-109">**Individual server performance**   This level of performance measurement is limited to a specific server and will help administrators with gauging the network performance of a specific server to either help with troubleshooting a specific performance issue or to gauge the respective server’s performance over a given period as part of a capacity planning process.</span></span>

<span data-ttu-id="e4337-110">您可以通过使用以下各节中介绍的工具来监视网络。</span><span class="sxs-lookup"><span data-stu-id="e4337-110">You can monitor the network by using the tools described in the following sections.</span></span>

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a><span data-ttu-id="e4337-111">总体网络性能监控工具</span><span class="sxs-lookup"><span data-stu-id="e4337-111">Tools for Overall Network Performance Monitoring</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="e4337-112">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="e4337-112">System Center Operations Manager 2012</span></span>

<span data-ttu-id="e4337-113">System Center Operations Manager 提供了端到端服务管理，可轻松进行自定义和扩展，以在 IT 环境中改进服务级别。</span><span class="sxs-lookup"><span data-stu-id="e4337-113">System Center Operations Manager provides end-to-end service management that is easy to customize and extend for improved service levels across an IT environment.</span></span> <span data-ttu-id="e4337-114">这使操作和 IT 管理团队能够识别和解决影响分布式 IT 服务运行状况的问题。</span><span class="sxs-lookup"><span data-stu-id="e4337-114">This enables Operations and IT Management teams to identify, and resolve issues affecting the health of distributed IT services.</span></span> <span data-ttu-id="e4337-115">端到端服务管理不限于基于 Microsoft 的环境。</span><span class="sxs-lookup"><span data-stu-id="e4337-115">End-to-end service management is not restricted to Microsoft-based environments.</span></span> <span data-ttu-id="e4337-116">支持 Web Services for Management (WS-MANAGEMENT) ，简单网络管理协议 (SNMP) 和合作伙伴解决方案允许未运行 Microsoft 操作系统和硬件的系统包含在 System Center Operations Manager 2012 中的服务监视中。</span><span class="sxs-lookup"><span data-stu-id="e4337-116">Support for Web Services for Management (WS-Management), Simple Network Management Protocol (SNMP), and partner solutions allow for systems that do not run Microsoft operating systems and hardware to be included in service monitoring within System Center Operations Manager 2012.</span></span>

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a><span data-ttu-id="e4337-117">System Center Operations Manager 2012 和第三方网络管理解决方案</span><span class="sxs-lookup"><span data-stu-id="e4337-117">System Center Operations Manager 2012 and Third-Party Network Management Solutions</span></span>

<span data-ttu-id="e4337-118">**EMC Smarts**    EMC 针对 Operations Manager 的解决方案可帮助您在整个中快速解决影响服务级别的问题。</span><span class="sxs-lookup"><span data-stu-id="e4337-118">**EMC Smarts**   EMC Solutions for Operations Manager help you quickly resolve issues affecting service levels throughout.</span></span> <span data-ttu-id="e4337-119">通过使用 EMC 针对 Operations Manager 的解决方案，您可以使用一个集成、自动化的解决方案管理和监控整个 IT 服务链。</span><span class="sxs-lookup"><span data-stu-id="e4337-119">By using EMC Solutions for Operations Manager, you can manage and monitor your whole IT service chain with one integrated, automated solution.</span></span> <span data-ttu-id="e4337-120">您可以轻松地确定性能和可用性问题的根本原因，并更快地解决这些问题，从而降低影响和成本。</span><span class="sxs-lookup"><span data-stu-id="e4337-120">You'll easily identify the root causes of performance and availability issues, and resolve them faster which reduces effects and costs.</span></span> <span data-ttu-id="e4337-121">主要优点包括：</span><span class="sxs-lookup"><span data-stu-id="e4337-121">Key benefits include the following:</span></span>

  - <span data-ttu-id="e4337-122">高级、易于使用的管理将重点放在提供战略业务价值上，而不是手动排序和筛选混乱警报。</span><span class="sxs-lookup"><span data-stu-id="e4337-122">Advanced, easy-to-use management   Focus on delivering strategic business value instead of manually sorting and filtering confusing alerts.</span></span>

  - <span data-ttu-id="e4337-123">**更快的分辨率**    解决 IT 问题并更快地响应业务需求，从而降低影响和成本。</span><span class="sxs-lookup"><span data-stu-id="e4337-123">**Faster resolution**   Solve IT issues and respond to business needs faster, reducing effect and cost.</span></span>

  - <span data-ttu-id="e4337-124">**简化的操作**    通过组合多个管理工具、应用程序和终端避免 IT 复杂性。</span><span class="sxs-lookup"><span data-stu-id="e4337-124">**Streamlined operations**   Avoid IT complexity by combining multiple management tools, applications, and terminals.</span></span>

<span data-ttu-id="e4337-125">可在以下位置找到详细信息：</span><span class="sxs-lookup"><span data-stu-id="e4337-125">More information can be found here:</span></span>

[<span data-ttu-id="e4337-126">Microsoft System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="e4337-126">Microsoft System Center Operations Manager</span></span>](https://go.microsoft.com/fwlink/p/?linkid=243651)

[<span data-ttu-id="e4337-127">Microsoft System Center Operations Manager 解决方案</span><span class="sxs-lookup"><span data-stu-id="e4337-127">Solutions for Microsoft System Center Operations Manager</span></span>](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a><span data-ttu-id="e4337-128">第三方解决方案</span><span class="sxs-lookup"><span data-stu-id="e4337-128">Third-Party Solutions</span></span>

<span data-ttu-id="e4337-129">\*\*Hp 网络管理中心 (之前称为 Hp OpenView) \*\*    [Hp 网络管理中心](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__)提供集成的故障和性能管理，以提高网络可用性和性能。</span><span class="sxs-lookup"><span data-stu-id="e4337-129">**HP Network Management Center (previously known as HP OpenView)**   [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) provides integrated fault and performance management to improve network availability and performance.</span></span> <span data-ttu-id="e4337-130">网络管理中心是 HP 自动化网络管理解决方案的一部分，可统一执行故障、性能、配置和更改管理。</span><span class="sxs-lookup"><span data-stu-id="e4337-130">Network Management Center is part of the HP automated network management solution that unifies fault, performance, configuration, and change management.</span></span>

<span data-ttu-id="e4337-131">**Cisco 网络管理和自动化产品**    对于企业版，Cisco 拥有几个可提供的管理产品，包括 CiscoWorks LAN Management 解决方案和 Cisco 网络分析模块，以帮助提高运营效率并减少网络故障时间。</span><span class="sxs-lookup"><span data-stu-id="e4337-131">**Cisco Network Management and Automation products**   For the Enterprise, Cisco has several management products available including CiscoWorks LAN Management Solution and Cisco Network Analysis Module, to help improve operational efficiency and reduce network downtime.</span></span> <span data-ttu-id="e4337-132">有关这些产品的其他数据，请参阅位于的 Cisco 网站 [https://www.cisco.com/en/US/products/sw/netmgtsw/index.html](https://www.cisco.com/en/us/products/sw/netmgtsw/index.html) 。</span><span class="sxs-lookup"><span data-stu-id="e4337-132">For additional data on these products, refer to the Cisco website at [https://www.cisco.com/en/US/products/sw/netmgtsw/index.html](https://www.cisco.com/en/us/products/sw/netmgtsw/index.html).</span></span>

<span data-ttu-id="e4337-133">简单网络管理协议 (SNMP) 简单网络管理协议 (SNMP) 是一种网络管理标准，用于定义 TCP/IP 网络的管理策略。</span><span class="sxs-lookup"><span data-stu-id="e4337-133">Simple Network Management Protocol (SNMP)   Simple Network Management Protocol (SNMP) is a network management standard that defines a strategy for managing TCP/IP networks.</span></span> <span data-ttu-id="e4337-134">SNMP 使您能够捕获有关网络的配置和状态信息，并将信息发送到指定的计算机进行事件监视。</span><span class="sxs-lookup"><span data-stu-id="e4337-134">SNMP enables you to capture configuration and status information about the network, and send the information to a designated computer for event monitoring.</span></span> <span data-ttu-id="e4337-135">此基于标准的网络管理协议使用分布式体系结构，其中包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="e4337-135">This standards based network management protocol uses a distributed architecture that includes the following:</span></span>

  - <span data-ttu-id="e4337-136">多个托管节点，每个节点都有一个称为代理的 SNMP 实体，可提供对管理规范的远程访问。</span><span class="sxs-lookup"><span data-stu-id="e4337-136">Multiple managed nodes, each with an SNMP entity called an agent which provides remote access to management instrumentation.</span></span>

  - <span data-ttu-id="e4337-137">至少一个名为 manager 的 SNMP 实体，它运行管理应用程序来监视和控制托管元素。</span><span class="sxs-lookup"><span data-stu-id="e4337-137">At least one SNMP entity known as a manager which runs management applications to monitor and control managed elements.</span></span> <span data-ttu-id="e4337-138">托管元素为设备，如主机、路由器等。</span><span class="sxs-lookup"><span data-stu-id="e4337-138">Managed elements are devices such as hosts, routers, and so on.</span></span> <span data-ttu-id="e4337-139">通过访问其管理信息来监视和控制这些用户。</span><span class="sxs-lookup"><span data-stu-id="e4337-139">They are monitored and controlled by accessing their management information.</span></span>

  - <span data-ttu-id="e4337-140">管理协议（SNMP）用于在管理工作站和代理之间传递管理信息。</span><span class="sxs-lookup"><span data-stu-id="e4337-140">A management protocol, SNMP, is used to communicate management information between the management stations and agents.</span></span> <span data-ttu-id="e4337-141">管理信息指的是驻留在虚拟信息存储中的托管对象的集合，该集合称为 "管理信息基本 (MIB) "。</span><span class="sxs-lookup"><span data-stu-id="e4337-141">Management information refers to a collection of managed objects that live in a virtual information store called a Management Information Base (MIB).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e4337-142">上面提供了第三方网络监视解决方案的示例。</span><span class="sxs-lookup"><span data-stu-id="e4337-142">Examples of third-party network monitoring solutions are provided above.</span></span> <span data-ttu-id="e4337-143">此列表不是明确的，Microsoft 不支持任何特定的供应商解决方案。</span><span class="sxs-lookup"><span data-stu-id="e4337-143">This list is not definitive and Microsoft does not favor any specific vendor solution.</span></span> <span data-ttu-id="e4337-144">请咨询网络服务提供商和或相应的技术提供商，以确定您的组织的最佳网络监控解决方案。</span><span class="sxs-lookup"><span data-stu-id="e4337-144">Consult with a network service provider and or your respective technology provider to determine the best network monitoring solution for your organization.</span></span>



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a><span data-ttu-id="e4337-145">用于监视单个服务器网络性能的工具</span><span class="sxs-lookup"><span data-stu-id="e4337-145">Tools for Monitoring Individual Server Network Performance</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="e4337-146">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="e4337-146">System Center Operations Manager 2012</span></span>

<span data-ttu-id="e4337-147">System Center Operations Manager 2012 允许管理员通过 Windows Server 2012 管理包查看各个服务器的网络性能： Windows Server 操作系统管理包包含一个 "性能" 管理包，允许管理员监视网络适配器的性能和适配器运行状况。</span><span class="sxs-lookup"><span data-stu-id="e4337-147">System Center Operations Manager 2012 would allow administrators to view network performance of individual servers through the Windows Server 2012 Management Pack: The Windows Server operating system management pack includes a "Performance" management pack that would allow administrators to monitor Network Adapter performance and adapter health.</span></span>

</div>

<div>

## <a name="windows-network-monitor"></a><span data-ttu-id="e4337-148">Windows 网络监视器</span><span class="sxs-lookup"><span data-stu-id="e4337-148">Windows Network Monitor</span></span>

<span data-ttu-id="e4337-149">收集、显示、分析服务器上的资源使用情况，并衡量网络流量。</span><span class="sxs-lookup"><span data-stu-id="e4337-149">Collects, displays, analyzes resource usage on a server, and measures network traffic.</span></span> <span data-ttu-id="e4337-150">网络监视器仅监视网络活动。</span><span class="sxs-lookup"><span data-stu-id="e4337-150">Network Monitor exclusively monitors network activity.</span></span> <span data-ttu-id="e4337-151">通过捕获和分析网络数据，并将此数据与性能日志结合使用，可以确定网络使用情况，识别网络问题，并预测未来的网络需求。</span><span class="sxs-lookup"><span data-stu-id="e4337-151">By capturing and analyzing network data, and using this data with performance logs, you can determine the network usage, identify network issues, and forecast future network needs.</span></span>

<span data-ttu-id="e4337-152">有关网络监视器3.4 的详细信息，并了解如何安装和配置网络监视器以及捕获和分析数据，请查看此会话：网络监视器3.3 概述。</span><span class="sxs-lookup"><span data-stu-id="e4337-152">For more information about Network Monitor 3.4, and to learn how to install and configure Network Monitor and capture and analyze data, review this session: Network Monitor 3.3 Overview.</span></span> <span data-ttu-id="e4337-153">此外，请查看 [网络监视器博客](https://blogs.technet.com/b/netmon/)。</span><span class="sxs-lookup"><span data-stu-id="e4337-153">Also, review the [Network Monitor blog](https://blogs.technet.com/b/netmon/).</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

