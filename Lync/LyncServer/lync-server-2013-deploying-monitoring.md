---
title: 'Lync Server 2013: 部署监视'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying monitoring
ms:assetid: 117f4a3e-0670-4388-a553-b9854921145f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398199(v=OCS.15)
ms:contentKeyID: 48183442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 584b99b6e5fad72a07a35b748ab9bafa4116701a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-monitoring-in-lync-server-2013"></a><span data-ttu-id="f1c73-102">在 Lync Server 2013 中部署监视</span><span class="sxs-lookup"><span data-stu-id="f1c73-102">Deploying monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1c73-103">_**主题上次修改时间:** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="f1c73-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="f1c73-104">对 Microsoft Lync Server 2013 监视基础结构进行了重大更改, 从监视服务器角色已弃用这一事实开始。</span><span class="sxs-lookup"><span data-stu-id="f1c73-104">Major changes have been made to the Microsoft Lync Server 2013 monitoring infrastructure, beginning with the fact that the Monitoring Server role has been deprecated.</span></span> <span data-ttu-id="f1c73-105">现在, 在每个前端服务器上 collocated, 而不是单独的监视服务器角色 (通常需要组织才能设置专用计算机作为监视服务器)。</span><span class="sxs-lookup"><span data-stu-id="f1c73-105">Instead of separate Monitoring Server roles (which typically required organizations to set up dedicated computers to act as Monitoring servers) monitoring services are now collocated on each Front End server.</span></span> <span data-ttu-id="f1c73-106">此外, 此更改有助于:</span><span class="sxs-lookup"><span data-stu-id="f1c73-106">Among other things, this change helps to:</span></span>

  - <span data-ttu-id="f1c73-107">减少实现 Lync Server 2013 时所需的服务器角色数。</span><span class="sxs-lookup"><span data-stu-id="f1c73-107">Decrease the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="f1c73-108">在这种情况下, 降低监视服务器的角色还有助于通过消除维护专用服务器来进行监视来降低成本。</span><span class="sxs-lookup"><span data-stu-id="f1c73-108">In this case, decrementing the Monitoring Server server role also helps to reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="f1c73-109">降低 Lync 服务器设置和管理的复杂性。</span><span class="sxs-lookup"><span data-stu-id="f1c73-109">Reduce the complexity of Lync Server setup and administration.</span></span> <span data-ttu-id="f1c73-110">通过自动 collocating 每台前端服务器上的监视服务, 您不必再安装、配置和管理监视服务器角色。</span><span class="sxs-lookup"><span data-stu-id="f1c73-110">By automatically collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f1c73-111">在 Lync Server 2013 中, 存档服务器角色也已被弃用。</span><span class="sxs-lookup"><span data-stu-id="f1c73-111">The Archiving Server role has also been deprecated in Lync Server 2013.</span></span> <span data-ttu-id="f1c73-112">与监视服务一样, Lync Server 2013 存档服务现在在每个前端服务器上 collocated。</span><span class="sxs-lookup"><span data-stu-id="f1c73-112">Like the monitoring services, Lync Server 2013 archiving services are now collocated on each Front End server.</span></span> <span data-ttu-id="f1c73-113">请注意, 这一点很重要, 因为监视和存档通常共享相同的 SQL Server 数据库实例。</span><span class="sxs-lookup"><span data-stu-id="f1c73-113">This is important to note simply because monitoring and archiving often share the same SQL Server database instance.</span></span>



</div>

<span data-ttu-id="f1c73-114">正如你所料, 这些更改对如何安装和管理监视服务有重大影响。</span><span class="sxs-lookup"><span data-stu-id="f1c73-114">As you might expect, these changes have a major impact on how monitoring services are installed and managed.</span></span> <span data-ttu-id="f1c73-115">例如, 由于不再存在监视服务器角色, 已从 Lync Server 拓扑生成器中删除了 "监视服务器" 节点;这意味着你不再使用拓扑生成器的新监视服务器向导, 以便将新的监视服务器添加到你的拓扑。</span><span class="sxs-lookup"><span data-stu-id="f1c73-115">For example, because the Monitoring Server role no longer exists, the Monitoring Server node has been removed from the Lync Server Topology Builder; in turn, that means you no longer use Topology Builder's New Monitoring Server Wizard in order to add a new Monitoring Server to your topology.</span></span> <span data-ttu-id="f1c73-116">(该向导不再存在。)相反, 你通常会通过完成以下两个步骤来实现拓扑内的监视服务:</span><span class="sxs-lookup"><span data-stu-id="f1c73-116">(That wizard no longer exists.) Instead, you will typically implement monitoring services within your topology by completing the following two steps:</span></span>

1.  <span data-ttu-id="f1c73-117">在设置新的 Lync 服务器池的同时启用监视。</span><span class="sxs-lookup"><span data-stu-id="f1c73-117">Enabling monitoring at the same time you set up a new Lync Server pool.</span></span> <span data-ttu-id="f1c73-118">(在 Lync Server 2013 中, 监视功能在逐个池的基础上启用或禁用。)请注意, 你可以为池启用监视, 而无需实际收集监视数据, 此过程将在本文档的 "配置呼叫详细记录" 和 "体验设置质量" 部分中介绍。</span><span class="sxs-lookup"><span data-stu-id="f1c73-118">(In Lync Server 2013, monitoring is enabled or disabled on a pool-by-pool basis.) Note that you can enable monitoring for a pool without actually collecting monitoring data, a process explained in the Configuring Call Detail Recording and Quality of Experience Settings section of this documentation.</span></span>

2.  <span data-ttu-id="f1c73-p107">使监控存储（即，监控数据库）与新池关联。请注意，一个监控存储可与多个池关联。根据驻留在注册器池中的用户数，这意味着，您不必为每个池设置单独的监控数据库。一个监控存储可供多个池使用。</span><span class="sxs-lookup"><span data-stu-id="f1c73-p107">Associating a monitoring store (that is, a monitoring database) with the new pool. Note that a single monitoring store can be associated with multiple pools. Depending on the number of users homed on your Registrar pools, that means that you do not have to set up a separate monitoring database for each of your pools. Instead, single monitoring store can be used by multiple pools.</span></span>

<span data-ttu-id="f1c73-123">尽管在创建新池的同时启用监控通常更为简单，但也可以创建新池并禁用监控。</span><span class="sxs-lookup"><span data-stu-id="f1c73-123">Although it's often easier to enable monitoring at the same time that you create a new pool, it's also possible to create a new pool with monitoring disabled.</span></span> <span data-ttu-id="f1c73-124">如果执行此操作，以后可以使用拓扑生成器启用该服务：拓扑生成器提供为池启用或禁用监控或将池与不同监控存储关联的方式。</span><span class="sxs-lookup"><span data-stu-id="f1c73-124">If you do that, you can later use Topology Builder to enable the service: Topology Builder provides a way to enable or disable monitoring for a pool, or to associate a pool with a different monitoring store.</span></span> <span data-ttu-id="f1c73-125">请记住, 即使不再是监视服务器角色, 你仍然需要创建一个或多个监视存储: 后端数据库, 用于存储由监视服务收集的数据。</span><span class="sxs-lookup"><span data-stu-id="f1c73-125">Keep in mind that even though there is no longer a Monitoring Server role you will still need to create one or more monitoring stores: backend databases used to store the data gathered by the monitoring service.</span></span> <span data-ttu-id="f1c73-126">可以使用 Microsoft SQL Server 2008 R2 或 Microsoft SQL Server 2012 创建这些后端数据库。</span><span class="sxs-lookup"><span data-stu-id="f1c73-126">These backend databases can be created using either Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f1c73-127">如果已为池启用监视, 则可以禁用收集监视数据的过程, 而无需更改拓扑: Lync Server Management Shell 提供了一种禁用 (稍后重新启用) 呼叫详细记录 (CDR) 或质量的方法的体验 (QoE) 数据收集。</span><span class="sxs-lookup"><span data-stu-id="f1c73-127">If monitoring has been enabled for a pool you can disable the process of collecting monitoring data without having to change your topology: Lync Server Management Shell provides a way for you to disable (and then later re-enable) call detail recording (CDR) or Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="f1c73-128">有关详细信息，请参阅本文的“配置呼叫详细记录和用户体验质量设置”部分。</span><span class="sxs-lookup"><span data-stu-id="f1c73-128">For more information, see the Configuring Call Detail Recording and Quality of Experience Settings section of this document.</span></span>



</div>

<span data-ttu-id="f1c73-129">在 Lync Server 2013 中进行监视的另一个重要增强是 Lync Server 监视报告现在支持 IPv6: 使用 "IP 地址" 字段的报表将显示 IPv4 或 IPv6 地址, 具体取决于: 1) 正在使用的 SQL 查询;和 (2) 将 IPv6 地址存储在监视数据库中的位置。</span><span class="sxs-lookup"><span data-stu-id="f1c73-129">One other important enhancement to monitoring in Lync Server 2013 is the fact that Lync Server Monitoring Reports now support IPv6: reports that use the IP Address field will display either IPv4 or IPv6 addresses depending on : 1) the SQL query being used; and, 2) where or not the IPv6 address is stored in the monitoring database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f1c73-130">确保 SQL Server 代理服务启动类型为“自动”，并且 SQL Server 代理服务正在针对容纳监控数据库的 SQL 实例运行，以便默认监控 SQL Server 维护作业在 SQL Server 代理服务的控制下按计划运行。</span><span class="sxs-lookup"><span data-stu-id="f1c73-130">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Monitoring databases, so that the Default Monitoring SQL Server Maintenance Jobs can run on their scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

<span data-ttu-id="f1c73-131">本文档将指导你完成安装和配置 Lync Server 2013 的监视和监视报告的过程。</span><span class="sxs-lookup"><span data-stu-id="f1c73-131">This documentation walks you through the process of installing and configuring monitoring and Monitoring Reports for Lync Server 2013.</span></span> <span data-ttu-id="f1c73-132">本文提供了会对您有所帮助的分步说明：</span><span class="sxs-lookup"><span data-stu-id="f1c73-132">The documentation provides step-by-step instructions that will help you to:</span></span>

  - <span data-ttu-id="f1c73-133">在拓扑中启用监控并使监控存储与前端池关联。</span><span class="sxs-lookup"><span data-stu-id="f1c73-133">Enable monitoring in your topology and associate a monitoring store with a Front End pool.</span></span>

  - <span data-ttu-id="f1c73-134">安装 SQL Server Reporting Services 和 Lync Server Monitoring 报表。</span><span class="sxs-lookup"><span data-stu-id="f1c73-134">Install SQL Server Reporting Services and the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="f1c73-135">监控报告是预配置的报告，其中提供不同视图，便于查看监控数据库中存储的信息。</span><span class="sxs-lookup"><span data-stu-id="f1c73-135">Monitoring Reports are preconfigured reports that provide different views into the information stored in a monitoring database.</span></span>

  - <span data-ttu-id="f1c73-136">配置呼叫详细记录 (CDR) 和体验质量 (QoE) 数据收集。</span><span class="sxs-lookup"><span data-stu-id="f1c73-136">Configure call detail recording (CDR) and Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="f1c73-137">呼叫详细记录为您提供了一种跟踪 Lync 服务器功能 (如 IP 语音电话 (VoIP) 电话呼叫) 的使用方式的方式。即时消息 (IM);文件传输;音频/视频 (A/V) 会议;和应用程序共享会话。</span><span class="sxs-lookup"><span data-stu-id="f1c73-137">Call detail recording provides a way for you to track usage of Lync Server capabilities such as Voice over IP (VoIP) phone calls; instant messaging (IM); file transfers; audio/video (A/V) conferencing; and application sharing sessions.</span></span> <span data-ttu-id="f1c73-138">QoE 指标跟踪在组织内进行的音频和视频呼叫的质量，包括丢失的网络数据包数、背景噪音和“抖动”量（数据包延迟的差异）等内容。</span><span class="sxs-lookup"><span data-stu-id="f1c73-138">QoE metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span>

  - <span data-ttu-id="f1c73-139">从监控数据库中手动清除 CDR 和/或 QoE 记录。</span><span class="sxs-lookup"><span data-stu-id="f1c73-139">Manually purge CDR and/or QoE records from the monitoring database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

