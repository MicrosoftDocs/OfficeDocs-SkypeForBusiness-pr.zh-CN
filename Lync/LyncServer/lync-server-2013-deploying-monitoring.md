---
title: Lync Server 2013：部署监控
description: Lync Server 2013：部署监控。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying monitoring
ms:assetid: 117f4a3e-0670-4388-a553-b9854921145f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398199(v=OCS.15)
ms:contentKeyID: 48183442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1821198ddd0b4164f6932122aa9cf00ac34aada
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561538"
---
# <a name="deploying-monitoring-in-lync-server-2013"></a><span data-ttu-id="727ee-103">在 Lync Server 2013 中部署监控</span><span class="sxs-lookup"><span data-stu-id="727ee-103">Deploying monitoring in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="727ee-104">_**上次修改的主题：** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="727ee-104">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="727ee-105">对 Microsoft Lync Server 2013 监视基础结构进行了重大更改，从监视服务器角色已弃用这一事实开始。</span><span class="sxs-lookup"><span data-stu-id="727ee-105">Major changes have been made to the Microsoft Lync Server 2013 monitoring infrastructure, beginning with the fact that the Monitoring Server role has been deprecated.</span></span> <span data-ttu-id="727ee-106">不再采用不同的监控服务器角色（通常需要组织设置专用计算机来充当监控服务器），现在监控服务已并置到每台前端服务器中。</span><span class="sxs-lookup"><span data-stu-id="727ee-106">Instead of separate Monitoring Server roles (which typically required organizations to set up dedicated computers to act as Monitoring servers) monitoring services are now collocated on each Front End server.</span></span> <span data-ttu-id="727ee-107">除了其他优点外，此更改还有助于：</span><span class="sxs-lookup"><span data-stu-id="727ee-107">Among other things, this change helps to:</span></span>

  - <span data-ttu-id="727ee-108">减少实现 Lync Server 2013 时所需的服务器角色数。</span><span class="sxs-lookup"><span data-stu-id="727ee-108">Decrease the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="727ee-109">在此情况下，减少监控服务器角色数还可帮助降低成本，因为无需维护用于监控的专用服务器。</span><span class="sxs-lookup"><span data-stu-id="727ee-109">In this case, decrementing the Monitoring Server server role also helps to reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="727ee-110">降低 Lync Server 安装和管理的复杂性。</span><span class="sxs-lookup"><span data-stu-id="727ee-110">Reduce the complexity of Lync Server setup and administration.</span></span> <span data-ttu-id="727ee-111">通过自动在每台前端服务器上并置监控服务，您不必再安装、配置和管理监控服务器角色。</span><span class="sxs-lookup"><span data-stu-id="727ee-111">By automatically collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="727ee-112">在 Lync Server 2013 中，存档服务器角色也已被弃用。</span><span class="sxs-lookup"><span data-stu-id="727ee-112">The Archiving Server role has also been deprecated in Lync Server 2013.</span></span> <span data-ttu-id="727ee-113">与监视服务一样，Lync Server 2013 存档服务现已在每台前端服务器上并置。</span><span class="sxs-lookup"><span data-stu-id="727ee-113">Like the monitoring services, Lync Server 2013 archiving services are now collocated on each Front End server.</span></span> <span data-ttu-id="727ee-114">注意到这一点非常重要，只是因为监控和存档通常共享同一 SQL Server 数据库实例。</span><span class="sxs-lookup"><span data-stu-id="727ee-114">This is important to note simply because monitoring and archiving often share the same SQL Server database instance.</span></span>



</div>

<span data-ttu-id="727ee-115">正如您可能预料的那样，这些更改对监控服务的安装和管理方式具有重要影响。</span><span class="sxs-lookup"><span data-stu-id="727ee-115">As you might expect, these changes have a major impact on how monitoring services are installed and managed.</span></span> <span data-ttu-id="727ee-116">例如，因为不再存在监视服务器角色，所以已从 Lync Server 拓扑生成器中删除了监视服务器节点;反过来，这意味着您不再使用拓扑生成器的新监视服务器向导，以便将新的监视服务器添加到拓扑中。</span><span class="sxs-lookup"><span data-stu-id="727ee-116">For example, because the Monitoring Server role no longer exists, the Monitoring Server node has been removed from the Lync Server Topology Builder; in turn, that means you no longer use Topology Builder's New Monitoring Server Wizard in order to add a new Monitoring Server to your topology.</span></span> <span data-ttu-id="727ee-117"> (该向导不再存在。 ) 相反，您将通过完成以下两个步骤来在拓扑中实现监视服务：</span><span class="sxs-lookup"><span data-stu-id="727ee-117">(That wizard no longer exists.) Instead, you will typically implement monitoring services within your topology by completing the following two steps:</span></span>

1.  <span data-ttu-id="727ee-118">在设置新的 Lync Server 池的同时启用监控。</span><span class="sxs-lookup"><span data-stu-id="727ee-118">Enabling monitoring at the same time you set up a new Lync Server pool.</span></span> <span data-ttu-id="727ee-119"> (在 Lync Server 2013 中，监视功能在池的基础上启用或禁用。 ) 请注意，您可以在不实际收集监控数据的情况下为池启用监控，此过程在本文档的配置呼叫详细信息记录和体验质量设置一节中进行了说明。</span><span class="sxs-lookup"><span data-stu-id="727ee-119">(In Lync Server 2013, monitoring is enabled or disabled on a pool-by-pool basis.) Note that you can enable monitoring for a pool without actually collecting monitoring data, a process explained in the Configuring Call Detail Recording and Quality of Experience Settings section of this documentation.</span></span>

2.  <span data-ttu-id="727ee-p107">使监控存储（即，监控数据库）与新池关联。请注意，一个监控存储可与多个池关联。根据驻留在注册器池中的用户数，这意味着，您不必为每个池设置单独的监控数据库。一个监控存储可供多个池使用。</span><span class="sxs-lookup"><span data-stu-id="727ee-p107">Associating a monitoring store (that is, a monitoring database) with the new pool. Note that a single monitoring store can be associated with multiple pools. Depending on the number of users homed on your Registrar pools, that means that you do not have to set up a separate monitoring database for each of your pools. Instead, single monitoring store can be used by multiple pools.</span></span>

<span data-ttu-id="727ee-p108">尽管在创建新池的同时启用监控通常更为简单，但也可以创建新池并禁用监控。如果执行此操作，以后可以使用拓扑生成器启用该服务：拓扑生成器提供为池启用或禁用监控或将池与不同监控存储关联的方式。请记住，即使不再存在监控服务器角色，您仍需要创建一个或多个监控存储：用于存储监控服务所收集数据的后端数据库。可以使用 Microsoft SQL Server 2008 R2 或 Microsoft SQL Server 2012 创建这些后端数据库。</span><span class="sxs-lookup"><span data-stu-id="727ee-p108">Although it's often easier to enable monitoring at the same time that you create a new pool, it's also possible to create a new pool with monitoring disabled. If you do that, you can later use Topology Builder to enable the service: Topology Builder provides a way to enable or disable monitoring for a pool, or to associate a pool with a different monitoring store. Keep in mind that even though there is no longer a Monitoring Server role you will still need to create one or more monitoring stores: backend databases used to store the data gathered by the monitoring service. These backend databases can be created using either Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="727ee-128">如果已为池启用监控，则可以禁用收集监控数据的过程，而无需更改拓扑： Lync Server 命令行管理程序提供了一种禁用 (的方法，然后重新启用) 呼叫详细记录 (CDR) 或 (QoE) 数据集的体验质量。</span><span class="sxs-lookup"><span data-stu-id="727ee-128">If monitoring has been enabled for a pool you can disable the process of collecting monitoring data without having to change your topology: Lync Server Management Shell provides a way for you to disable (and then later re-enable) call detail recording (CDR) or Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="727ee-129">有关详细信息，请参阅本文的“配置呼叫详细记录和用户体验质量设置”部分。</span><span class="sxs-lookup"><span data-stu-id="727ee-129">For more information, see the Configuring Call Detail Recording and Quality of Experience Settings section of this document.</span></span>



</div>

<span data-ttu-id="727ee-130">在 Lync Server 2013 中进行监视的另一个重要增强是，Lync Server 监视报告现在支持 IPv6：使用 IP 地址字段的报表将显示 IPv4 或 IPv6 地址，具体取决于： 1) 正在使用的 SQL 查询;和，2) IPv6 地址存储在监控数据库中的位置。</span><span class="sxs-lookup"><span data-stu-id="727ee-130">One other important enhancement to monitoring in Lync Server 2013 is the fact that Lync Server Monitoring Reports now support IPv6: reports that use the IP Address field will display either IPv4 or IPv6 addresses depending on : 1) the SQL query being used; and, 2) where or not the IPv6 address is stored in the monitoring database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="727ee-131">确保 SQL Server 代理服务启动类型为 "自动"，并且 SQL Server 代理服务正在为包含监视数据库的 SQL 实例运行，以便默认的监视 SQL Server 维护作业可以按 SQL Server 代理服务的控制顺序在计划的基础上运行。</span><span class="sxs-lookup"><span data-stu-id="727ee-131">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Monitoring databases, so that the Default Monitoring SQL Server Maintenance Jobs can run on their scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

<span data-ttu-id="727ee-132">本文档将引导您完成为 Lync Server 2013 安装和配置监控和监控报告的过程。</span><span class="sxs-lookup"><span data-stu-id="727ee-132">This documentation walks you through the process of installing and configuring monitoring and Monitoring Reports for Lync Server 2013.</span></span> <span data-ttu-id="727ee-133">本文提供了会对您有所帮助的分步说明：</span><span class="sxs-lookup"><span data-stu-id="727ee-133">The documentation provides step-by-step instructions that will help you to:</span></span>

  - <span data-ttu-id="727ee-134">在拓扑中启用监控并使监控存储与前端池关联。</span><span class="sxs-lookup"><span data-stu-id="727ee-134">Enable monitoring in your topology and associate a monitoring store with a Front End pool.</span></span>

  - <span data-ttu-id="727ee-135">安装 SQL Server Reporting Services 和 Lync Server Monitoring 报告。</span><span class="sxs-lookup"><span data-stu-id="727ee-135">Install SQL Server Reporting Services and the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="727ee-136">监控报告是预配置的报告，其中提供不同视图，便于查看监控数据库中存储的信息。</span><span class="sxs-lookup"><span data-stu-id="727ee-136">Monitoring Reports are preconfigured reports that provide different views into the information stored in a monitoring database.</span></span>

  - <span data-ttu-id="727ee-137">配置呼叫详细记录 (CDR) 和用户体验质量 (QoE) 数据收集。</span><span class="sxs-lookup"><span data-stu-id="727ee-137">Configure call detail recording (CDR) and Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="727ee-138">呼叫详细信息记录提供了一种跟踪 Lync Server 功能（如 IP 语音 (VoIP) 电话呼叫）的使用方式的方法。即时消息 (IM) ;文件传输;音频/视频 (A/V) 会议;和应用程序共享会话。</span><span class="sxs-lookup"><span data-stu-id="727ee-138">Call detail recording provides a way for you to track usage of Lync Server capabilities such as Voice over IP (VoIP) phone calls; instant messaging (IM); file transfers; audio/video (A/V) conferencing; and application sharing sessions.</span></span> <span data-ttu-id="727ee-139">QoE 指标跟踪在组织内进行的音频和视频呼叫的质量，包括丢失的网络数据包数、背景噪音和“抖动”量（数据包延迟的差异）等内容。</span><span class="sxs-lookup"><span data-stu-id="727ee-139">QoE metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span>

  - <span data-ttu-id="727ee-140">从监控数据库中手动清除 CDR 和/或 QoE 记录。</span><span class="sxs-lookup"><span data-stu-id="727ee-140">Manually purge CDR and/or QoE records from the monitoring database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

