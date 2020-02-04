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
ms.openlocfilehash: 26e7de821dee778d4b0b1e9aa105669635abaf6c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755806"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="operational-dependencies-in-lync-server-2013"></a><span data-ttu-id="e8775-102">Lync Server 2013 中的操作相关性</span><span class="sxs-lookup"><span data-stu-id="e8775-102">Operational dependencies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8775-103">_**主题上次修改时间：** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="e8775-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="e8775-104">本文档中讨论的参考体系结构将帮助确保你拥有的 Lync Server 2013 部署不仅可扩展到组织的要求，还可根据 Microsoft 最佳做法进行构建。</span><span class="sxs-lookup"><span data-stu-id="e8775-104">The Reference Architecture discussed in this document will help ensure that you have a Lync Server 2013 deployment that not only scales to the organization’s requirements but is architected as per Microsoft best practices.</span></span> <span data-ttu-id="e8775-105">请注意，它可能是 Lync Server 2013 实现是一种动态服务，与企业中的任何其他服务一样，它仍需要监视和主动管理，以便为企业保持高级别的服务可用性和服务质量。</span><span class="sxs-lookup"><span data-stu-id="e8775-105">Be that as it may the Lync Server 2013 implementation is a dynamic service and like any other service in the enterprise still requires monitoring and proactive management to maintain high level of service availability and service quality to the business.</span></span>

<span data-ttu-id="e8775-106">随着 Lync Server 2013 在组织的日常企业中变得更深 ingrained，该服务必须通过准确的有形服务级别管理来管理。</span><span class="sxs-lookup"><span data-stu-id="e8775-106">As Lync Server 2013 becomes deeply ingrained in the organization’s everyday business it is important that the service be managed by accurate and tangible service level management.</span></span> <span data-ttu-id="e8775-107">Lync 系统体系结构可能会变得复杂且非常集成，以便维护有效的服务级别管理并建立 Lync Server 2013 的 Sla，这对了解系统对其他平台和服务器的依赖非常重要。</span><span class="sxs-lookup"><span data-stu-id="e8775-107">The Lync system architecture can become complex and very integrated and in order to maintain effective service level management and establish SLAs for Lync Server 2013 it becomes critical to understand the system’s dependencies on other platforms and servers.</span></span> <span data-ttu-id="e8775-108">同样重要的是要注意哪些商业服务（如语音和 UC 集成应用程序）依赖于 Lync。</span><span class="sxs-lookup"><span data-stu-id="e8775-108">Equally important is to note which business services, such as voice and UC integrated applications, become dependent on Lync.</span></span>

<span data-ttu-id="e8775-109">必须建立 Lync Server 2013，注意所有所说的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="e8775-109">Lync Server 2013 must be established noting all the said dependencies.</span></span> <span data-ttu-id="e8775-110">服务地图将允许你在 Lync 及其依赖的服务之间制定一个 SLA，并提供 SLA 协商的起始位置。</span><span class="sxs-lookup"><span data-stu-id="e8775-110">The service map will allow you to formulate a SLA between Lync and its dependent service and provide a starting place for SLA negotiation.</span></span>

<span data-ttu-id="e8775-111">下表列出了 Lync 基础结构的典型依赖服务。</span><span class="sxs-lookup"><span data-stu-id="e8775-111">The following table lists the typical dependency services for a Lync infrastructure.</span></span> <span data-ttu-id="e8775-112">其中每种技术都应具有其自己的主动预防性监控。</span><span class="sxs-lookup"><span data-stu-id="e8775-112">Each of these technologies should have its own proactive monitoring.</span></span>

### <a name="typical-dependency-services"></a><span data-ttu-id="e8775-113">典型的依赖服务</span><span class="sxs-lookup"><span data-stu-id="e8775-113">Typical dependency services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8775-114">依赖服务</span><span class="sxs-lookup"><span data-stu-id="e8775-114">Dependency Service</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8775-115">操作系统</span><span class="sxs-lookup"><span data-stu-id="e8775-115">Operating systems</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8775-116">服务器硬件</span><span class="sxs-lookup"><span data-stu-id="e8775-116">Server Hardware</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8775-117">Active Directory</span><span class="sxs-lookup"><span data-stu-id="e8775-117">Active Directory</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8775-118">公钥基础结构</span><span class="sxs-lookup"><span data-stu-id="e8775-118">Public Key Infrastructure</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8775-119">域命名服务</span><span class="sxs-lookup"><span data-stu-id="e8775-119">Domain Naming Service</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8775-120">数据库服务</span><span class="sxs-lookup"><span data-stu-id="e8775-120">Database Services</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8775-121">存储服务</span><span class="sxs-lookup"><span data-stu-id="e8775-121">Storage Services</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8775-122">系统管理-监视和分发</span><span class="sxs-lookup"><span data-stu-id="e8775-122">System Management – Monitoring and distribution</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8775-123">安全服务-防病毒</span><span class="sxs-lookup"><span data-stu-id="e8775-123">Security Services - Antivirus</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8775-124">网络基础结构-Internet</span><span class="sxs-lookup"><span data-stu-id="e8775-124">Network Infrastructure - Internet</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8775-125">网络基础结构-内部（LAN/WAN）</span><span class="sxs-lookup"><span data-stu-id="e8775-125">Network Infrastructure – Internal (LAN/WAN)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8775-126">电话服务基础结构-IP-PBX 和网关</span><span class="sxs-lookup"><span data-stu-id="e8775-126">Telephony Infrastructure – IP-PBX and Gateways</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8775-127">云服务</span><span class="sxs-lookup"><span data-stu-id="e8775-127">Cloud Services</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e8775-128">假定组织在使用由 MOF 规定的基本服务级别管理功能（如更改、事件和发布管理）中运行成熟。</span><span class="sxs-lookup"><span data-stu-id="e8775-128">It is assumed that the organization is operationally mature in exercising basic service level management functions such as change, incident and release management as prescribed by the MOF.</span></span> <span data-ttu-id="e8775-129">Lync 解决方案应由这些函数采纳，并遵循相同的操作管理过程。</span><span class="sxs-lookup"><span data-stu-id="e8775-129">The Lync solution should be adopted by these functions and become subject to the same operational management processes.</span></span>

<span data-ttu-id="e8775-130">根据以上获取的信息构建，我们现在更深入地了解对企业中的 Lync 服务有哪些影响。</span><span class="sxs-lookup"><span data-stu-id="e8775-130">Building on the information obtained above we now have a greater understanding of what can impact the Lync service in the enterprise.</span></span> <span data-ttu-id="e8775-131">为了帮助确保 Lync Server 2013 服务可用性和质量，以下监视工具必须附带参考体系结构部署：</span><span class="sxs-lookup"><span data-stu-id="e8775-131">To help ensure Lync Server 2013 service availability and quality, the following monitoring tools must accompany the reference architecture deployment:</span></span>

### <a name="monitoring-tools"></a><span data-ttu-id="e8775-132">监视工具</span><span class="sxs-lookup"><span data-stu-id="e8775-132">Monitoring tools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8775-133">组件</span><span class="sxs-lookup"><span data-stu-id="e8775-133">Component</span></span></th>
<th><span data-ttu-id="e8775-134">说明</span><span class="sxs-lookup"><span data-stu-id="e8775-134">Description</span></span></th>
<th><span data-ttu-id="e8775-135">适用网站</span><span class="sxs-lookup"><span data-stu-id="e8775-135">Applicable Site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8775-136">Lync Server 2013 监视服务器</span><span class="sxs-lookup"><span data-stu-id="e8775-136">Lync Server 2013 Monitoring Server</span></span></p></td>
<td><p><span data-ttu-id="e8775-137">每个中心站点至少部署一个 Lync Server 2013 监视服务器角色，并配置体验质量（QoE）报告包。</span><span class="sxs-lookup"><span data-stu-id="e8775-137">Deploy at least one Lync Server 2013 Monitoring Server role per Central site and configure Quality of Experience (QoE) Reporting Pack.</span></span></p>
<p><span data-ttu-id="e8775-138">有关详细信息，请参阅 Lync Server 2013 部署文档：</span><span class="sxs-lookup"><span data-stu-id="e8775-138">Refer to the Lync Server 2013 Deployment documentation for further details:</span></span></p>
<p><span data-ttu-id="e8775-139"><a href="lync-server-2013-deploying-monitoring.md">在 Lync Server 2013 中部署监视</a></span><span class="sxs-lookup"><span data-stu-id="e8775-139"><a href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e8775-140">中心网站</span><span class="sxs-lookup"><span data-stu-id="e8775-140">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="e8775-141">将每个池 Tether 到最接近的监视服务器角色实例。</span><span class="sxs-lookup"><span data-stu-id="e8775-141">Tether each pool to its nearest instance of the Monitoring Server role.</span></span></p></td>
<td><p><span data-ttu-id="e8775-142">中心网站</span><span class="sxs-lookup"><span data-stu-id="e8775-142">Central sites</span></span></p>
<p><span data-ttu-id="e8775-143">分支站点</span><span class="sxs-lookup"><span data-stu-id="e8775-143">Branch sites</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8775-144">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="e8775-144">System Center Operations Manager 2012</span></span></p></td>
<td><p><span data-ttu-id="e8775-145">已导入 Microsoft Lync Server 2013 管理包（MP）的 System Center Operations Manager 2012。</span><span class="sxs-lookup"><span data-stu-id="e8775-145">System Center Operations Manager 2012 with the Microsoft Lync Server 2013 Management Pack (MP) imported.</span></span></p>
<p><span data-ttu-id="e8775-146">管理包实现传统事件日志和基于性能计数器的检测使用，并在 Lync Server 2013 中启用新可用的检测。</span><span class="sxs-lookup"><span data-stu-id="e8775-146">The Management Pack implements traditional Event Log and Performance counter based instrumentation is utilized as well as enabling newly available instrumentation in Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="e8775-147">中心网站</span><span class="sxs-lookup"><span data-stu-id="e8775-147">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="e8775-148">确保基于用于读取管理中心数据库中发布的拓扑文档的中心发现脚本，自动完成发现需要监视的角色和组件的集中发现。</span><span class="sxs-lookup"><span data-stu-id="e8775-148">Make sure that Central Discovery to discovery of roles and components that need to be monitored are automatically completed based on a central discovery script that reads the topology document published in Central Management Database.</span></span></p></td>
<td><p><span data-ttu-id="e8775-149">中央站点</span><span class="sxs-lookup"><span data-stu-id="e8775-149">Central Site</span></span></p>
<p><span data-ttu-id="e8775-150">分支站点</span><span class="sxs-lookup"><span data-stu-id="e8775-150">Branch Site</span></span></p>
<p><span data-ttu-id="e8775-151">边缘网站</span><span class="sxs-lookup"><span data-stu-id="e8775-151">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="e8775-152">将 System 中心 Operations Manager 2007 代理部署到运行 Lync Server 的所有已部署服务器。</span><span class="sxs-lookup"><span data-stu-id="e8775-152">Deploy System Centre Operations Manager 2007 agents to all deployed servers running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="e8775-153">中央站点</span><span class="sxs-lookup"><span data-stu-id="e8775-153">Central Site</span></span></p>
<p><span data-ttu-id="e8775-154">分支站点</span><span class="sxs-lookup"><span data-stu-id="e8775-154">Branch Site</span></span></p>
<p><span data-ttu-id="e8775-155">边缘网站</span><span class="sxs-lookup"><span data-stu-id="e8775-155">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="e8775-156">请确保为通知配置了优先警报：</span><span class="sxs-lookup"><span data-stu-id="e8775-156">Make sure Prioritized Alerts are configured for notification:</span></span></p>
<p><span data-ttu-id="e8775-157">高优先级警报</span><span class="sxs-lookup"><span data-stu-id="e8775-157">High Priority Alerts</span></span></p>
<p><span data-ttu-id="e8775-158">中等优先级的警报</span><span class="sxs-lookup"><span data-stu-id="e8775-158">Medium Priority Alerts</span></span></p>
<p><span data-ttu-id="e8775-159">其他通知。</span><span class="sxs-lookup"><span data-stu-id="e8775-159">Other Alerts.</span></span></p></td>
<td><p><span data-ttu-id="e8775-160">中央站点</span><span class="sxs-lookup"><span data-stu-id="e8775-160">Central Site</span></span></p>
<p><span data-ttu-id="e8775-161">分支站点</span><span class="sxs-lookup"><span data-stu-id="e8775-161">Branch Site</span></span></p>
<p><span data-ttu-id="e8775-162">边缘网站</span><span class="sxs-lookup"><span data-stu-id="e8775-162">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="e8775-163">为你的部署配置端口监视。</span><span class="sxs-lookup"><span data-stu-id="e8775-163">Configure Port monitoring for your deployment.</span></span></p></td>
<td><p><span data-ttu-id="e8775-164">中央站点</span><span class="sxs-lookup"><span data-stu-id="e8775-164">Central Site</span></span></p>
<p><span data-ttu-id="e8775-165">分支站点</span><span class="sxs-lookup"><span data-stu-id="e8775-165">Branch Site</span></span></p>
<p><span data-ttu-id="e8775-166">边缘网站</span><span class="sxs-lookup"><span data-stu-id="e8775-166">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="e8775-167">为你的部署配置 URL 监视</span><span class="sxs-lookup"><span data-stu-id="e8775-167">Configure URL monitoring for your deployment</span></span></p></td>
<td><p><span data-ttu-id="e8775-168">中央站点</span><span class="sxs-lookup"><span data-stu-id="e8775-168">Central Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8775-169">Lync 和 System Center Operations Manager 集成</span><span class="sxs-lookup"><span data-stu-id="e8775-169">Lync and System Center Operations Manager integration</span></span></p></td>
<td><p><span data-ttu-id="e8775-170">部署通话可靠性和媒体质量 MonitoringCall 可靠性和媒体质量监视将监视服务器计算机用作其观察程序节点，以监视 Lync 服务器的调用可靠性和媒体质量。</span><span class="sxs-lookup"><span data-stu-id="e8775-170">Deploy Call Reliability and Media Quality MonitoringCall reliability and media quality monitoring use the Monitoring Server computer as their watcher node to monitor call reliability and media quality of Lync Server.</span></span> <span data-ttu-id="e8775-171">这两个功能都可查询监视服务器数据库以进行分析。</span><span class="sxs-lookup"><span data-stu-id="e8775-171">Both of these features query the Monitoring Server databases to do analysis.</span></span></p></td>
<td><p><span data-ttu-id="e8775-172">中央站点</span><span class="sxs-lookup"><span data-stu-id="e8775-172">Central Site</span></span></p>
<p><span data-ttu-id="e8775-173">分支站点</span><span class="sxs-lookup"><span data-stu-id="e8775-173">Branch Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="e8775-174">确保准确配置媒体质量警告阈值。</span><span class="sxs-lookup"><span data-stu-id="e8775-174">Ensure Media Quality warning thresholds are accurately configured.</span></span> <span data-ttu-id="e8775-175">下表显示了编解码器的最大网络平均观点。</span><span class="sxs-lookup"><span data-stu-id="e8775-175">The following table indicates the maximum Network Mean Opinion Scores by Codec.</span></span> <span data-ttu-id="e8775-176">在生产中，这些分数应针对设定的时间段进行监视，并且必须根据组织特定的 NMOS 分数来建立可接受的阈值。</span><span class="sxs-lookup"><span data-stu-id="e8775-176">In production these scores should be monitored for a set period and acceptable thresholds must be established based on the organization specific NMOS scores.</span></span></p></td>
<td><p><span data-ttu-id="e8775-177">中央站点</span><span class="sxs-lookup"><span data-stu-id="e8775-177">Central Site</span></span></p>
<p><span data-ttu-id="e8775-178">分支站点</span><span class="sxs-lookup"><span data-stu-id="e8775-178">Branch Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8775-179">Lync Server 2013 合成事务观察程序</span><span class="sxs-lookup"><span data-stu-id="e8775-179">Lync Server 2013 Synthetic Transaction Watcher</span></span></p></td>
<td><p><span data-ttu-id="e8775-180">将专用 Lync 服务器部署为合成事务观察程序。</span><span class="sxs-lookup"><span data-stu-id="e8775-180">Deploy a dedicated Lync Server to be a synthetic transaction watcher.</span></span></p>
<p><span data-ttu-id="e8775-181">合成事务是 Lync Server 2013 Windows PowerShell cmdlet，这些 cmdlet 由管理包在预定义的时间间隔内自动触发。</span><span class="sxs-lookup"><span data-stu-id="e8775-181">Synthetic transactions are Lync Server 2013 Windows PowerShell cmdlets that are automatically triggered by the management pack on a predefined interval.</span></span> <span data-ttu-id="e8775-182">这些操作在综合事务观察程序节点上执行，该节点是管理员指定的服务器，负责为每个池发现和执行 STs。</span><span class="sxs-lookup"><span data-stu-id="e8775-182">These are executed on a synthetic transaction watcher node which is an administrator designated server responsible for discovery and execution of STs for each pool.</span></span></p>
<p><span data-ttu-id="e8775-183">我们不建议使用现有的 Microsoft Lync Server 2013 服务器作为合成事务观察程序节点。</span><span class="sxs-lookup"><span data-stu-id="e8775-183">We do not recommend that you use an existing Microsoft Lync Server 2013 server as a synthetic transaction watcher node.</span></span> <span data-ttu-id="e8775-184">这是由于运行 STs 的 CPU/内存使用要求较高。</span><span class="sxs-lookup"><span data-stu-id="e8775-184">This is due to the high CPU/memory usage requirements for running STs.</span></span> <span data-ttu-id="e8775-185">将新的服务器计算机（或虚拟服务器）用于合成事务观察程序节点。</span><span class="sxs-lookup"><span data-stu-id="e8775-185">Use a new server computer (or a virtual server) for the synthetic transaction watcher node.</span></span></p></td>
<td><p><span data-ttu-id="e8775-186">中央站点</span><span class="sxs-lookup"><span data-stu-id="e8775-186">Central Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="e8775-187">部署合成事务观察程序节点。</span><span class="sxs-lookup"><span data-stu-id="e8775-187">Deploying synthetic transactions watcher node.</span></span></p>
<p><span data-ttu-id="e8775-188">请参阅 UCTAP connect 文档中的 MonitoringCS_withSCOM .docx 文档。</span><span class="sxs-lookup"><span data-stu-id="e8775-188">Refer to the MonitoringCS_withSCOM.docx document from UCTAP connect documentation.</span></span></p></td>
<td><p><span data-ttu-id="e8775-189">中央站点</span><span class="sxs-lookup"><span data-stu-id="e8775-189">Central Site</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a><span data-ttu-id="e8775-190">每个编解码器的最大网络 MOS 分数</span><span class="sxs-lookup"><span data-stu-id="e8775-190">Maximum Network MOS scores per codec</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8775-191">应用场景</span><span class="sxs-lookup"><span data-stu-id="e8775-191">Scenario</span></span></th>
<th><span data-ttu-id="e8775-192">编解码器</span><span class="sxs-lookup"><span data-stu-id="e8775-192">Codec</span></span></th>
<th><span data-ttu-id="e8775-193">最大 NMOS</span><span class="sxs-lookup"><span data-stu-id="e8775-193">Max NMOS</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8775-194">UC-UC 呼叫</span><span class="sxs-lookup"><span data-stu-id="e8775-194">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="e8775-195">RTAudio WB</span><span class="sxs-lookup"><span data-stu-id="e8775-195">RTAudio WB</span></span></p></td>
<td><p><span data-ttu-id="e8775-196">4.10</span><span class="sxs-lookup"><span data-stu-id="e8775-196">4.10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8775-197">UC-UC 呼叫</span><span class="sxs-lookup"><span data-stu-id="e8775-197">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="e8775-198">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="e8775-198">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="e8775-199">2.95</span><span class="sxs-lookup"><span data-stu-id="e8775-199">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8775-200">电话会议</span><span class="sxs-lookup"><span data-stu-id="e8775-200">Conference call</span></span></p></td>
<td><p><span data-ttu-id="e8775-201">Siren</span><span class="sxs-lookup"><span data-stu-id="e8775-201">Siren</span></span></p></td>
<td><p><span data-ttu-id="e8775-202">3.72</span><span class="sxs-lookup"><span data-stu-id="e8775-202">3.72</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8775-203">UC-PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="e8775-203">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="e8775-204">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="e8775-204">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="e8775-205">2.95</span><span class="sxs-lookup"><span data-stu-id="e8775-205">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8775-206">UC-PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="e8775-206">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="e8775-207">G-711</span><span class="sxs-lookup"><span data-stu-id="e8775-207">G-711</span></span></p></td>
<td><p><span data-ttu-id="e8775-208">3.61</span><span class="sxs-lookup"><span data-stu-id="e8775-208">3.61</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e8775-209">在以前的 pro 活动监视活动之前和之后，应根据 Lync RA 操作指南中定义的每天、每周和每月定期执行维护任务。</span><span class="sxs-lookup"><span data-stu-id="e8775-209">Over and above the previous pro-active monitoring activities, maintenance tasks should be executed for Central, Edge and Branch sites on a recurring daily, weekly and monthly basis as defined in the Lync RA Operations Guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

