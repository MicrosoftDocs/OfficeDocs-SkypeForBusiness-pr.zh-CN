---
title: Lync Server 2013：操作依赖项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Operational dependencies
ms:assetid: 450b6be2-7fb3-47d7-8b0b-c05faa331e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720559(v=OCS.15)
ms:contentKeyID: 63969597
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2403fde7387c1ef5af7d402ad9bc859aa95fe6d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="operational-dependencies-in-lync-server-2013"></a><span data-ttu-id="377cc-102">Lync Server 2013 中的操作依赖项</span><span class="sxs-lookup"><span data-stu-id="377cc-102">Operational dependencies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="377cc-103">_**上次修改的主题：** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="377cc-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="377cc-104">本文档中讨论的参考体系结构可帮助确保你具有 Lync Server 2013 部署，该部署不仅可扩展到组织的要求，而且根据 Microsoft 最佳做法进行了构建。</span><span class="sxs-lookup"><span data-stu-id="377cc-104">The Reference Architecture discussed in this document will help ensure that you have a Lync Server 2013 deployment that not only scales to the organization’s requirements but is architected as per Microsoft best practices.</span></span> <span data-ttu-id="377cc-105">请注意，它可能会导致 Lync Server 2013 实现是一个动态服务，与企业中的任何其他服务一样，仍需要监控和主动管理来维护企业的高级别服务可用性和服务质量。</span><span class="sxs-lookup"><span data-stu-id="377cc-105">Be that as it may the Lync Server 2013 implementation is a dynamic service and like any other service in the enterprise still requires monitoring and proactive management to maintain high level of service availability and service quality to the business.</span></span>

<span data-ttu-id="377cc-106">随着 Lync Server 2013 在组织的日常业务中变得深度更深，此服务应由准确而有形的服务级别管理来管理，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="377cc-106">As Lync Server 2013 becomes deeply ingrained in the organization’s everyday business it is important that the service be managed by accurate and tangible service level management.</span></span> <span data-ttu-id="377cc-107">Lync 系统体系结构可能会变得复杂且非常集成，以便维护有效的服务级别管理并为 Lync Server 2013 建立 Sla。了解系统在其他平台和服务器上的依赖关系至关重要。</span><span class="sxs-lookup"><span data-stu-id="377cc-107">The Lync system architecture can become complex and very integrated and in order to maintain effective service level management and establish SLAs for Lync Server 2013 it becomes critical to understand the system’s dependencies on other platforms and servers.</span></span> <span data-ttu-id="377cc-108">同等重要的是，请注意哪些业务服务（如语音和 UC 集成应用程序）依赖 Lync。</span><span class="sxs-lookup"><span data-stu-id="377cc-108">Equally important is to note which business services, such as voice and UC integrated applications, become dependent on Lync.</span></span>

<span data-ttu-id="377cc-109">必须建立 Lync Server 2013，以记录所有已说出的依赖项。</span><span class="sxs-lookup"><span data-stu-id="377cc-109">Lync Server 2013 must be established noting all the said dependencies.</span></span> <span data-ttu-id="377cc-110">服务映射将允许您在 Lync 及其相关服务之间制定 SLA，并提供 SLA 协商的起始位置。</span><span class="sxs-lookup"><span data-stu-id="377cc-110">The service map will allow you to formulate a SLA between Lync and its dependent service and provide a starting place for SLA negotiation.</span></span>

<span data-ttu-id="377cc-111">下表列出了 Lync 基础结构的典型依赖项服务。</span><span class="sxs-lookup"><span data-stu-id="377cc-111">The following table lists the typical dependency services for a Lync infrastructure.</span></span> <span data-ttu-id="377cc-112">其中的每种技术都应具有自己的主动监控。</span><span class="sxs-lookup"><span data-stu-id="377cc-112">Each of these technologies should have its own proactive monitoring.</span></span>

### <a name="typical-dependency-services"></a><span data-ttu-id="377cc-113">典型的依赖项服务</span><span class="sxs-lookup"><span data-stu-id="377cc-113">Typical dependency services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="377cc-114">依赖项服务</span><span class="sxs-lookup"><span data-stu-id="377cc-114">Dependency Service</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="377cc-115">操作系统</span><span class="sxs-lookup"><span data-stu-id="377cc-115">Operating systems</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="377cc-116">服务器硬件</span><span class="sxs-lookup"><span data-stu-id="377cc-116">Server Hardware</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="377cc-117">Active Directory</span><span class="sxs-lookup"><span data-stu-id="377cc-117">Active Directory</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="377cc-118">公钥基础结构</span><span class="sxs-lookup"><span data-stu-id="377cc-118">Public Key Infrastructure</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="377cc-119">域命名服务</span><span class="sxs-lookup"><span data-stu-id="377cc-119">Domain Naming Service</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="377cc-120">数据库服务</span><span class="sxs-lookup"><span data-stu-id="377cc-120">Database Services</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="377cc-121">存储服务</span><span class="sxs-lookup"><span data-stu-id="377cc-121">Storage Services</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="377cc-122">系统管理–监控和分发</span><span class="sxs-lookup"><span data-stu-id="377cc-122">System Management – Monitoring and distribution</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="377cc-123">安全服务-防病毒</span><span class="sxs-lookup"><span data-stu-id="377cc-123">Security Services - Antivirus</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="377cc-124">网络基础结构-Internet</span><span class="sxs-lookup"><span data-stu-id="377cc-124">Network Infrastructure - Internet</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="377cc-125">网络基础结构–内部（LAN/WAN）</span><span class="sxs-lookup"><span data-stu-id="377cc-125">Network Infrastructure – Internal (LAN/WAN)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="377cc-126">电话服务基础结构– IP-PBX 和网关</span><span class="sxs-lookup"><span data-stu-id="377cc-126">Telephony Infrastructure – IP-PBX and Gateways</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="377cc-127">云服务</span><span class="sxs-lookup"><span data-stu-id="377cc-127">Cloud Services</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="377cc-128">假定组织在执行基本服务级别管理功能（如由 MOF 规定的更改、事件和发布管理）中执行成熟的操作。</span><span class="sxs-lookup"><span data-stu-id="377cc-128">It is assumed that the organization is operationally mature in exercising basic service level management functions such as change, incident and release management as prescribed by the MOF.</span></span> <span data-ttu-id="377cc-129">Lync 解决方案应由这些函数采用，并遵循相同的操作管理过程。</span><span class="sxs-lookup"><span data-stu-id="377cc-129">The Lync solution should be adopted by these functions and become subject to the same operational management processes.</span></span>

<span data-ttu-id="377cc-130">根据上面获取的信息构建，我们可以更好地了解对企业中的 Lync 服务有何影响。</span><span class="sxs-lookup"><span data-stu-id="377cc-130">Building on the information obtained above we now have a greater understanding of what can impact the Lync service in the enterprise.</span></span> <span data-ttu-id="377cc-131">为了帮助确保 Lync Server 2013 服务可用性和质量，以下监控工具必须附带参考体系结构部署：</span><span class="sxs-lookup"><span data-stu-id="377cc-131">To help ensure Lync Server 2013 service availability and quality, the following monitoring tools must accompany the reference architecture deployment:</span></span>

### <a name="monitoring-tools"></a><span data-ttu-id="377cc-132">监视工具</span><span class="sxs-lookup"><span data-stu-id="377cc-132">Monitoring tools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="377cc-133">组件</span><span class="sxs-lookup"><span data-stu-id="377cc-133">Component</span></span></th>
<th><span data-ttu-id="377cc-134">说明</span><span class="sxs-lookup"><span data-stu-id="377cc-134">Description</span></span></th>
<th><span data-ttu-id="377cc-135">适用的网站</span><span class="sxs-lookup"><span data-stu-id="377cc-135">Applicable Site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="377cc-136">Lync Server 2013 监视服务器</span><span class="sxs-lookup"><span data-stu-id="377cc-136">Lync Server 2013 Monitoring Server</span></span></p></td>
<td><p><span data-ttu-id="377cc-137">每个中心站点至少部署一个 Lync Server 2013 监视服务器角色，并配置体验质量（QoE）报告包。</span><span class="sxs-lookup"><span data-stu-id="377cc-137">Deploy at least one Lync Server 2013 Monitoring Server role per Central site and configure Quality of Experience (QoE) Reporting Pack.</span></span></p>
<p><span data-ttu-id="377cc-138">有关详细信息，请参阅 Lync Server 2013 部署文档：</span><span class="sxs-lookup"><span data-stu-id="377cc-138">Refer to the Lync Server 2013 Deployment documentation for further details:</span></span></p>
<p><span data-ttu-id="377cc-139"><a href="lync-server-2013-deploying-monitoring.md">在 Lync Server 2013 中部署监控</a></span><span class="sxs-lookup"><span data-stu-id="377cc-139"><a href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="377cc-140">中央站点</span><span class="sxs-lookup"><span data-stu-id="377cc-140">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="377cc-141">将每个池 Tether 为其最接近的监视服务器角色实例。</span><span class="sxs-lookup"><span data-stu-id="377cc-141">Tether each pool to its nearest instance of the Monitoring Server role.</span></span></p></td>
<td><p><span data-ttu-id="377cc-142">中央站点</span><span class="sxs-lookup"><span data-stu-id="377cc-142">Central sites</span></span></p>
<p><span data-ttu-id="377cc-143">分支站点</span><span class="sxs-lookup"><span data-stu-id="377cc-143">Branch sites</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="377cc-144">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="377cc-144">System Center Operations Manager 2012</span></span></p></td>
<td><p><span data-ttu-id="377cc-145">导入了 Microsoft Lync Server 2013 管理包（MP）的 System Center Operations Manager 2012。</span><span class="sxs-lookup"><span data-stu-id="377cc-145">System Center Operations Manager 2012 with the Microsoft Lync Server 2013 Management Pack (MP) imported.</span></span></p>
<p><span data-ttu-id="377cc-146">管理包实现传统事件日志和基于性能计数器的规范，并在 Lync Server 2013 中启用新可用的检测。</span><span class="sxs-lookup"><span data-stu-id="377cc-146">The Management Pack implements traditional Event Log and Performance counter based instrumentation is utilized as well as enabling newly available instrumentation in Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="377cc-147">中央站点</span><span class="sxs-lookup"><span data-stu-id="377cc-147">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="377cc-148">请确保基于读取中央管理数据库中发布的拓扑文档的中央发现脚本自动完成发现需要监视的角色和组件的集中发现。</span><span class="sxs-lookup"><span data-stu-id="377cc-148">Make sure that Central Discovery to discovery of roles and components that need to be monitored are automatically completed based on a central discovery script that reads the topology document published in Central Management Database.</span></span></p></td>
<td><p><span data-ttu-id="377cc-149">中央站点</span><span class="sxs-lookup"><span data-stu-id="377cc-149">Central Site</span></span></p>
<p><span data-ttu-id="377cc-150">分支站点</span><span class="sxs-lookup"><span data-stu-id="377cc-150">Branch Site</span></span></p>
<p><span data-ttu-id="377cc-151">边缘网站</span><span class="sxs-lookup"><span data-stu-id="377cc-151">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="377cc-152">将 System 中心 Operations Manager 2007 代理部署到运行 Lync Server 的所有已部署服务器。</span><span class="sxs-lookup"><span data-stu-id="377cc-152">Deploy System Centre Operations Manager 2007 agents to all deployed servers running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="377cc-153">中央站点</span><span class="sxs-lookup"><span data-stu-id="377cc-153">Central Site</span></span></p>
<p><span data-ttu-id="377cc-154">分支站点</span><span class="sxs-lookup"><span data-stu-id="377cc-154">Branch Site</span></span></p>
<p><span data-ttu-id="377cc-155">边缘网站</span><span class="sxs-lookup"><span data-stu-id="377cc-155">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="377cc-156">请确保为通知配置了已设置优先级的警报：</span><span class="sxs-lookup"><span data-stu-id="377cc-156">Make sure Prioritized Alerts are configured for notification:</span></span></p>
<p><span data-ttu-id="377cc-157">高优先级警报</span><span class="sxs-lookup"><span data-stu-id="377cc-157">High Priority Alerts</span></span></p>
<p><span data-ttu-id="377cc-158">中等优先级警报</span><span class="sxs-lookup"><span data-stu-id="377cc-158">Medium Priority Alerts</span></span></p>
<p><span data-ttu-id="377cc-159">其他警报。</span><span class="sxs-lookup"><span data-stu-id="377cc-159">Other Alerts.</span></span></p></td>
<td><p><span data-ttu-id="377cc-160">中央站点</span><span class="sxs-lookup"><span data-stu-id="377cc-160">Central Site</span></span></p>
<p><span data-ttu-id="377cc-161">分支站点</span><span class="sxs-lookup"><span data-stu-id="377cc-161">Branch Site</span></span></p>
<p><span data-ttu-id="377cc-162">边缘网站</span><span class="sxs-lookup"><span data-stu-id="377cc-162">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="377cc-163">为您的部署配置端口监视。</span><span class="sxs-lookup"><span data-stu-id="377cc-163">Configure Port monitoring for your deployment.</span></span></p></td>
<td><p><span data-ttu-id="377cc-164">中央站点</span><span class="sxs-lookup"><span data-stu-id="377cc-164">Central Site</span></span></p>
<p><span data-ttu-id="377cc-165">分支站点</span><span class="sxs-lookup"><span data-stu-id="377cc-165">Branch Site</span></span></p>
<p><span data-ttu-id="377cc-166">边缘网站</span><span class="sxs-lookup"><span data-stu-id="377cc-166">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="377cc-167">为您的部署配置 URL 监视</span><span class="sxs-lookup"><span data-stu-id="377cc-167">Configure URL monitoring for your deployment</span></span></p></td>
<td><p><span data-ttu-id="377cc-168">中央站点</span><span class="sxs-lookup"><span data-stu-id="377cc-168">Central Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="377cc-169">Lync 和 System Center Operations Manager 集成</span><span class="sxs-lookup"><span data-stu-id="377cc-169">Lync and System Center Operations Manager integration</span></span></p></td>
<td><p><span data-ttu-id="377cc-170">部署呼叫可靠性和媒体质量 MonitoringCall 可靠性和媒体质量监控使用监视服务器计算机作为其观察程序节点来监视 Lync Server 的呼叫可靠性和媒体质量。</span><span class="sxs-lookup"><span data-stu-id="377cc-170">Deploy Call Reliability and Media Quality MonitoringCall reliability and media quality monitoring use the Monitoring Server computer as their watcher node to monitor call reliability and media quality of Lync Server.</span></span> <span data-ttu-id="377cc-171">这两种功能都可查询监视服务器数据库以进行分析。</span><span class="sxs-lookup"><span data-stu-id="377cc-171">Both of these features query the Monitoring Server databases to do analysis.</span></span></p></td>
<td><p><span data-ttu-id="377cc-172">中央站点</span><span class="sxs-lookup"><span data-stu-id="377cc-172">Central Site</span></span></p>
<p><span data-ttu-id="377cc-173">分支站点</span><span class="sxs-lookup"><span data-stu-id="377cc-173">Branch Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="377cc-174">确保正确配置媒体质量警告阈值。</span><span class="sxs-lookup"><span data-stu-id="377cc-174">Ensure Media Quality warning thresholds are accurately configured.</span></span> <span data-ttu-id="377cc-175">下表显示编解码器的最大网络平均观点得分。</span><span class="sxs-lookup"><span data-stu-id="377cc-175">The following table indicates the maximum Network Mean Opinion Scores by Codec.</span></span> <span data-ttu-id="377cc-176">在生产中，应在设定的期限内监控这些分数，并且必须根据组织特定的 NMOS 得分来建立可接受的阈值。</span><span class="sxs-lookup"><span data-stu-id="377cc-176">In production these scores should be monitored for a set period and acceptable thresholds must be established based on the organization specific NMOS scores.</span></span></p></td>
<td><p><span data-ttu-id="377cc-177">中央站点</span><span class="sxs-lookup"><span data-stu-id="377cc-177">Central Site</span></span></p>
<p><span data-ttu-id="377cc-178">分支站点</span><span class="sxs-lookup"><span data-stu-id="377cc-178">Branch Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="377cc-179">Lync Server 2013 综合事务观察程序</span><span class="sxs-lookup"><span data-stu-id="377cc-179">Lync Server 2013 Synthetic Transaction Watcher</span></span></p></td>
<td><p><span data-ttu-id="377cc-180">将专用 Lync Server 部署为综合事务观察程序。</span><span class="sxs-lookup"><span data-stu-id="377cc-180">Deploy a dedicated Lync Server to be a synthetic transaction watcher.</span></span></p>
<p><span data-ttu-id="377cc-181">综合事务是由管理包根据预定义间隔自动触发的 Lync Server 2013 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="377cc-181">Synthetic transactions are Lync Server 2013 Windows PowerShell cmdlets that are automatically triggered by the management pack on a predefined interval.</span></span> <span data-ttu-id="377cc-182">这些操作在综合事务观察程序节点上执行，这是一种管理员指定的服务器，负责为每个池发现和执行 STs。</span><span class="sxs-lookup"><span data-stu-id="377cc-182">These are executed on a synthetic transaction watcher node which is an administrator designated server responsible for discovery and execution of STs for each pool.</span></span></p>
<p><span data-ttu-id="377cc-183">建议您不要将现有的 Microsoft Lync Server 2013 服务器用作综合事务观察程序节点。</span><span class="sxs-lookup"><span data-stu-id="377cc-183">We do not recommend that you use an existing Microsoft Lync Server 2013 server as a synthetic transaction watcher node.</span></span> <span data-ttu-id="377cc-184">这是因为运行 STs 的 CPU/内存使用率要求较高。</span><span class="sxs-lookup"><span data-stu-id="377cc-184">This is due to the high CPU/memory usage requirements for running STs.</span></span> <span data-ttu-id="377cc-185">为综合事务观察程序节点使用新的服务器计算机（或虚拟服务器）。</span><span class="sxs-lookup"><span data-stu-id="377cc-185">Use a new server computer (or a virtual server) for the synthetic transaction watcher node.</span></span></p></td>
<td><p><span data-ttu-id="377cc-186">中央站点</span><span class="sxs-lookup"><span data-stu-id="377cc-186">Central Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="377cc-187">部署综合事务观察程序节点。</span><span class="sxs-lookup"><span data-stu-id="377cc-187">Deploying synthetic transactions watcher node.</span></span></p>
<p><span data-ttu-id="377cc-188">请参阅 UCTAP connect 文档中的 MonitoringCS_withSCOM .docx 文档。</span><span class="sxs-lookup"><span data-stu-id="377cc-188">Refer to the MonitoringCS_withSCOM.docx document from UCTAP connect documentation.</span></span></p></td>
<td><p><span data-ttu-id="377cc-189">中央站点</span><span class="sxs-lookup"><span data-stu-id="377cc-189">Central Site</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a><span data-ttu-id="377cc-190">每个编解码器的最大网络 MOS 分数</span><span class="sxs-lookup"><span data-stu-id="377cc-190">Maximum Network MOS scores per codec</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="377cc-191">方案</span><span class="sxs-lookup"><span data-stu-id="377cc-191">Scenario</span></span></th>
<th><span data-ttu-id="377cc-192">编解码器</span><span class="sxs-lookup"><span data-stu-id="377cc-192">Codec</span></span></th>
<th><span data-ttu-id="377cc-193">最大 NMOS</span><span class="sxs-lookup"><span data-stu-id="377cc-193">Max NMOS</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="377cc-194">UC-UC 呼叫</span><span class="sxs-lookup"><span data-stu-id="377cc-194">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="377cc-195">RTAudio WB</span><span class="sxs-lookup"><span data-stu-id="377cc-195">RTAudio WB</span></span></p></td>
<td><p><span data-ttu-id="377cc-196">4.10</span><span class="sxs-lookup"><span data-stu-id="377cc-196">4.10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="377cc-197">UC-UC 呼叫</span><span class="sxs-lookup"><span data-stu-id="377cc-197">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="377cc-198">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="377cc-198">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="377cc-199">2.95</span><span class="sxs-lookup"><span data-stu-id="377cc-199">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="377cc-200">电话会议</span><span class="sxs-lookup"><span data-stu-id="377cc-200">Conference call</span></span></p></td>
<td><p><span data-ttu-id="377cc-201">Siren</span><span class="sxs-lookup"><span data-stu-id="377cc-201">Siren</span></span></p></td>
<td><p><span data-ttu-id="377cc-202">3.72</span><span class="sxs-lookup"><span data-stu-id="377cc-202">3.72</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="377cc-203">UC-PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="377cc-203">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="377cc-204">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="377cc-204">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="377cc-205">2.95</span><span class="sxs-lookup"><span data-stu-id="377cc-205">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="377cc-206">UC-PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="377cc-206">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="377cc-207">G-711</span><span class="sxs-lookup"><span data-stu-id="377cc-207">G-711</span></span></p></td>
<td><p><span data-ttu-id="377cc-208">3.61</span><span class="sxs-lookup"><span data-stu-id="377cc-208">3.61</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="377cc-209">在以前的主动预防性监视活动中，应根据 Lync RA 操作指南中定义的每日、每周和每月定期执行维护任务。</span><span class="sxs-lookup"><span data-stu-id="377cc-209">Over and above the previous pro-active monitoring activities, maintenance tasks should be executed for Central, Edge and Branch sites on a recurring daily, weekly and monthly basis as defined in the Lync RA Operations Guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

