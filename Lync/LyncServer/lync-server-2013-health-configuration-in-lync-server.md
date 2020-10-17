---
title: Lync Server 2013： Lync Server 中的运行状况配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Health configuration in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48185305
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa0164a9e3003c130bc7b14a4312397a4559843c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528239"
---
# <a name="health-configuration-in-lync-server-2013"></a><span data-ttu-id="ad6d8-102">Lync Server 2013 中的运行状况配置</span><span class="sxs-lookup"><span data-stu-id="ad6d8-102">Health configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad6d8-103">_**上次修改的主题：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="ad6d8-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="ad6d8-104">在各种网站、Microsoft 知识库文章和 Lync Server 资源工具包工具之间，在运行 Lync Server 时遇到问题的管理员永远不会从解决这些问题的方法开始。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-104">Between various websites, Microsoft Knowledge Base articles, and Lync Server Resource Kit tools, administrators who encounter problems when running Lync Server are never far from a way to solve those problems.</span></span>

<span data-ttu-id="ad6d8-105">显然，无法保证 Lync Server 2013 不会遇到问题，因为 Lync Server 可能会受到许多功能（如网络故障和硬件故障）的影响，产品本身无法控制这些内容。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-105">Obviously there is no way to guarantee that you will never encounter problems with Lync Server 2013 because Lync Server can be affected by many things—like network crashes and hardware failures—that the product itself cannot control.</span></span> <span data-ttu-id="ad6d8-106">通过实施运行状况监控，管理员可以先确认潜在的问题，然后再进入实际问题。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-106">By implementing health monitoring, administrators can identify potential problems before they turn into actual problems.</span></span> <span data-ttu-id="ad6d8-107">例如，管理员可以使用 Lync Server monitoring 识别趋势和 tendencies。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-107">For example, administrators can use Lync Server monitoring to identify trends and tendencies.</span></span> <span data-ttu-id="ad6d8-108">例如，在音频/视频会议数目方面的稳定增长可能暗示着在系统超载之前需要添加容量。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-108">For example, a steady increase in the number of audio/video conferences might suggest a need to add capacity before the system becomes overloaded.</span></span>

<span data-ttu-id="ad6d8-109">与此类似，管理员可以使用 System Center Operations Manager 执行在指定事件发生时发出实时警报等操作，并运行主动测试系统的综合事务。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-109">In a similar fashion, administrators can use System Center Operations Manager to do such things as issue real-time alerts when specified events occur, and to run synthetic transactions that proactively test the system.</span></span> <span data-ttu-id="ad6d8-110">在 Lync Server 中使用综合事务，以验证用户是否能够成功完成常见任务，如登录系统、交换即时消息或呼叫位于公用电话交换网 (PSTN) 的电话。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-110">Synthetic transactions are used in Lync Server to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="ad6d8-111">例如，定期运行这些测试可能会提醒您登录到 Lync Server 时遇到的潜在问题，并使您有机会在您的支持团队耗尽来自用户无法建立连接的呼叫之前解决此问题。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-111">For example, periodically running these tests can alert you to potential problems with users logging on to Lync Server, and give you a chance to correct the problem before your support team is flooded with calls from users unable to make a connection.</span></span> <span data-ttu-id="ad6d8-112">通过使用 System Center Operations Manager 运行这些综合事务，管理员可以定期监视每日连续24小时的 Lync Server 部署，而无需执行任何可能发出的任何警报。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-112">By using System Center Operations Manager to run these synthetic transactions, administrators can routinely monitor their deployment of Lync Server continuously for 24 hours every day without having to do much of anything beyond responding to any alerts that might be issued.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ad6d8-113">对于 Lync Server 2013，System Center Operations Manager 管理包还能够检测可能对 Lync Server 产生负面影响的 "外部" 问题。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-113">For Lync Server 2013, the Management Pack for System Center Operations Manager is also able to detect "external" issues that can adversely affect Lync Server.</span></span> <span data-ttu-id="ad6d8-114">例如，如果 Internet 信息服务 (IIS) 脱机、Lync Server 计算机上的系统资源低于指定的数量或 Lync Server 计算机遇到硬件故障，则可以通知管理员。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-114">For example, administrators can be notified if Internet Information Services (IIS) goes offline, system resources on a Lync Server computer fall below a specified amount, or a Lync Server computer experiences a hardware failure.</span></span>



</div>

<span data-ttu-id="ad6d8-115">Lync Server 2013 中的运行状况配置是围绕 System Center Operations Manager 和 Lync Server 管理包的使用而构建的。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-115">Health configuration in Lync Server 2013 is built around System Center Operations Manager and the use of Lync Server Management Packs.</span></span> <span data-ttu-id="ad6d8-116">这些管理包包括许多新的功能和增强功能，其中包括：</span><span class="sxs-lookup"><span data-stu-id="ad6d8-116">These Management Packs include a number of new features and enhancements, including:</span></span>

  - <span data-ttu-id="ad6d8-117">**任何位置的方案可用性。**</span><span class="sxs-lookup"><span data-stu-id="ad6d8-117">**Scenario availability from any location.**</span></span> <span data-ttu-id="ad6d8-118">Lync Server 2010 管理包引入了使用综合事务监视最终用户方案可用性的概念。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-118">The Lync Server 2010 Management Pack introduced the concept of monitoring end user scenario availability with synthetic transactions.</span></span> <span data-ttu-id="ad6d8-119">在 Lync Server 2013 中，这些代理具有更多的综合事务，并且可以从企业内的各种位置运行，从企业外部的远程地理位置，针对分支机构设备和 Lync Server 2010 部署，以将覆盖范围添加到旧版边缘部署中。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-119">In Lync Server 2013, these agents have more synthetic transactions and can be run from a variety of locations inside the enterprise, from remote geographic locations outside of the enterprise, against branch office appliances and against Lync Server 2010 deployments to add coverage to legacy Edge deployments.</span></span>

  - <span data-ttu-id="ad6d8-120">**综合事务日志。**</span><span class="sxs-lookup"><span data-stu-id="ad6d8-120">**Synthetic transaction logs.**</span></span> <span data-ttu-id="ad6d8-121">当综合事务失败时，管理员可以访问 HTML 日志以帮助确定什么失败了。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-121">When a synthetic transaction fails, administrators have access to HTML logs to help determine what failed.</span></span> <span data-ttu-id="ad6d8-122">这包括了解哪个操作失败、每个操作的延迟、用来运行测试的命令行，以及所遇到的错误。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-122">This includes understanding which action failed, the latency of each action, the command-line used to run the test, and the error that was encountered.</span></span>

  - <span data-ttu-id="ad6d8-123">**增加呼叫可靠性范围。**</span><span class="sxs-lookup"><span data-stu-id="ad6d8-123">**Increased call reliability coverage.**</span></span> <span data-ttu-id="ad6d8-124">Lync Server 2010 管理包引入了呼叫可靠性警报，以检测影响最终用户的音频呼叫的严重连接问题。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-124">The Lync Server 2010 Management Pack introduced call reliability alerting to detect severe connectivity issues that affect the audio calls of end users.</span></span> <span data-ttu-id="ad6d8-125">Lync Server 2013 管理包为对等即时消息 (IM) 和其他基本会议功能添加了覆盖范围，以在降低噪音的同时最大限度地提高覆盖范围。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-125">The Lync Server 2013 Management Packs add coverage for peer-to-peer instant messaging (IM) and other basic conferencing features to maximize coverage while reducing noise.</span></span>

  - <span data-ttu-id="ad6d8-126">**依赖关系监控。**</span><span class="sxs-lookup"><span data-stu-id="ad6d8-126">**Dependency monitoring.**</span></span> <span data-ttu-id="ad6d8-127">由于各种外部因素（如 IIS 处于脱机状态、有限的 CPU 和内存资源以及磁盘问题），Lync Server 方案可能会失败。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-127">Lync Server scenarios can fail due to a variety of external factors such as IIS being offline, limited CPU and memory resources, and disk issues.</span></span> <span data-ttu-id="ad6d8-128">新的管理包会检查多个重要的依赖关系，以确保管理员注意到它们的影响。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-128">The new management packs check several critical dependencies to ensure administrators are aware of their impact.</span></span>

  - <span data-ttu-id="ad6d8-129">**增强的报告。**</span><span class="sxs-lookup"><span data-stu-id="ad6d8-129">**Enhanced reporting.**</span></span> <span data-ttu-id="ad6d8-130">可帮助管理员估计方案可用性、规划容量并查看哪些组件遇到最多问题的一组报告。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-130">A set of reports to help administrators estimate scenario availability, plan for capacity, and see which components are experiencing the most issues.</span></span>

<span data-ttu-id="ad6d8-131">管理包中还包含多种功能，可帮助检测和诊断您的 Lync Server 部署的运行状况的实时可见性。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-131">The Management Packs also include a variety of features to help detect and diagnose provide real-time visibility into the health your Lync Server deployment.</span></span> <span data-ttu-id="ad6d8-132">这些功能在下表中列出。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-132">These features are listed in the following table.</span></span>

### <a name="management-pack-features"></a><span data-ttu-id="ad6d8-133">管理包功能</span><span class="sxs-lookup"><span data-stu-id="ad6d8-133">Management Pack Features</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad6d8-134">功能</span><span class="sxs-lookup"><span data-stu-id="ad6d8-134">Feature</span></span></th>
<th><span data-ttu-id="ad6d8-135">说明</span><span class="sxs-lookup"><span data-stu-id="ad6d8-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad6d8-136">综合事务</span><span class="sxs-lookup"><span data-stu-id="ad6d8-136">Synthetic Transactions</span></span></p></td>
<td><p><span data-ttu-id="ad6d8-137">可从不同位置运行的 Windows PowerShell cmdlet，以确保最终用户随时可以使用登录、状态、即时消息和会议等最终用户方案。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-137">Windows PowerShell cmdlets that can be run from various locations to ensure that end user scenarios such as sign-in, presence, IM, and conferencing are readily available to end users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad6d8-138">呼叫可靠性警报</span><span class="sxs-lookup"><span data-stu-id="ad6d8-138">Call Reliability Alerts</span></span></p></td>
<td><p><span data-ttu-id="ad6d8-139">呼叫详细记录 (CDR) 的数据库查询。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-139">Database queries for Call Detail Records (CDR).</span></span> <span data-ttu-id="ad6d8-140">前端服务器写入这些记录，以反映最终用户能否连接到呼叫或终止呼叫的原因。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-140">These records are written by Front End Servers to reflect whether end users were able to connect to a call or why a call was terminated.</span></span> <span data-ttu-id="ad6d8-141">这些查询会产生警报，指示大量的最终用户面向对等呼叫或基本会议功能何时遇到连接问题。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-141">These queries result in alerts that indicate when a wide range of end users are experiencing connectivity issues for peer-to-peer calls or basic conferencing functionality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad6d8-142">媒体质量警报</span><span class="sxs-lookup"><span data-stu-id="ad6d8-142">Media Quality Alerts</span></span></p></td>
<td><p><span data-ttu-id="ad6d8-p112">查看每个呼叫结束时由客户端发布的体验质量 (QoE) 报告的数据库查询。这些查询会产生警报，以准确找出用户可能在呼叫和会议期间遇到较差的媒体质量的方案。数据构建在诸如数据包延迟和丢失之类的关键指标，以及已知直接促成呼叫质量的指标的基础之上。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-p112">Database queries that look at Quality of Experience (QoE) reports published by clients at the end of each call. These queries result in alerts that pinpoint scenarios where users are likely to be experiencing poor media quality during calls and conferences. The data is built upon key metrics such as packet latency and loss, metrics that are known to directly contribute to call quality.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad6d8-146">组件运行状况</span><span class="sxs-lookup"><span data-stu-id="ad6d8-146">Component Health</span></span></p></td>
<td><p><span data-ttu-id="ad6d8-p113">个别服务器组件会使用事件日志和性能计数器发出警报。这些警报指出可能会对一个或多个最终用户方案造成负面影响的失败条件。这些警报还可以指出各种其他失败条件，包括服务未运行、很高的失败率、很高的消息延迟或连接问题。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-p113">Individual server components raise alerts by using event logs and performance counters. These alerts indicate failure conditions that can severely impact one or more end user scenarios. These alerts can also indicate a variety of other failure conditions, including services not running, high failure rates, high message latency, or connectivity issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad6d8-150">依赖关系运行状况</span><span class="sxs-lookup"><span data-stu-id="ad6d8-150">Dependency Health</span></span></p></td>
<td><p><span data-ttu-id="ad6d8-151">有多种外部原因可能导致失败。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-151">Failures can occur for a variety of external reasons.</span></span> <span data-ttu-id="ad6d8-152">管理包现在监控并收集可能指示严重问题的一些重要外部依赖关系的数据，包括 IIS 可用性、服务器和处理程序的 CPU 和内存使用情况，以及磁盘指标。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-152">The management packs now monitor and collect data for some of the critical external dependencies that might indicate severe issues, including IIS availability, CPU and memory usage of servers and processes, and disk metrics.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ad6d8-153">已将系统所发出的警报分为三种一般类别：</span><span class="sxs-lookup"><span data-stu-id="ad6d8-153">The alerts issued by the system have been classified into three general categories:</span></span>

  - <span data-ttu-id="ad6d8-154">**高优先级警报。**</span><span class="sxs-lookup"><span data-stu-id="ad6d8-154">**High-priority Alerts.**</span></span> <span data-ttu-id="ad6d8-155">这些警报指出将导致大型用户组的服务中断的条件。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-155">These alerts indicate conditions that will cause service outages for large groups of users.</span></span> <span data-ttu-id="ad6d8-156">例如，一台计算机上的组件故障不是高优先级的警报，因为 Lync Server 2013 具有内置的高可用性功能。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-156">For example, a component failure on a single machine is not a high-priority alert because Lync Server 2013 has built-in high availability features.</span></span> <span data-ttu-id="ad6d8-157">而高优先级警报代表严重性程度达到足以“在夜晚唤醒管理员”的问题。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-157">Instead, high-priority alerts represent problems serious enough “to wake up administrators at night.”</span></span> <span data-ttu-id="ad6d8-158">综合事务和脱机服务（例如，音频/视频会议）所检测到的中断会被鉴定为高优先级警报。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-158">Outages detected by synthetic transactions and offline services (for example, audio/video conferencing) qualify as high-priority alerts.</span></span>

  - <span data-ttu-id="ad6d8-159">**中等优先级警报。**。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-159">**Medium-priority alerts.**.</span></span> <span data-ttu-id="ad6d8-160">这些警报表示影响用户子集或指示呼叫质量降级的条件。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-160">These alerts indicate conditions that affect a subset of users or indicate call quality degradation.</span></span> <span data-ttu-id="ad6d8-161">其中包括组件故障、呼叫中的延迟或呼叫中的音频质量下降等问题。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-161">That includes problems such as component failures, latency in call establishment, or degraded audio quality in call.</span></span> <span data-ttu-id="ad6d8-162">此类别中的警报是有状态的，指示问题的当前状态。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-162">Alerts in this category are stateful and indicate the current status of the issue.</span></span> <span data-ttu-id="ad6d8-163">例如，假设您的呼叫建立时间超过了警报阈值。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-163">For example, suppose your call establishment times exceed the alert threshold.</span></span> <span data-ttu-id="ad6d8-164">如果呼叫建立时间返回到正常，则会在 System Center Operations Manager 中自动解决这些警报。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-164">If call establishment times return to normal, these alerts will be auto-resolved in System Center Operations Manager.</span></span> <span data-ttu-id="ad6d8-165">这些警报的预期是管理员将在同一工作日查看。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-165">The expectation for these alerts is that an administrator will look at them on the same business day.</span></span>

  - <span data-ttu-id="ad6d8-166">**其他警报。**</span><span class="sxs-lookup"><span data-stu-id="ad6d8-166">**Other alerts.**</span></span> <span data-ttu-id="ad6d8-167">这些是指来自组件且可能影响特定用户或用户子集的警报。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-167">These are alerts from components that might affect a specific user or subset of users.</span></span> <span data-ttu-id="ad6d8-168">例如，也许通讯簿服务无法分析给定用户的 Active Directory 条目。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-168">For example, perhaps the Address Book service could not parse the Active Directory entry of a given user.</span></span> <span data-ttu-id="ad6d8-169">对这些警报的期望值是管理员在有可用时间时对它们进行处理。</span><span class="sxs-lookup"><span data-stu-id="ad6d8-169">The expectation for these alerts is that administrators will get to them when they have time available.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ad6d8-170">本节内容</span><span class="sxs-lookup"><span data-stu-id="ad6d8-170">In This Section</span></span>

  - [<span data-ttu-id="ad6d8-171">配置 Lync Server 2013 以使用 System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="ad6d8-171">Configuring Lync Server 2013 to work with System Center Operations Manager</span></span>](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [<span data-ttu-id="ad6d8-172">在 Lync Server 2013 中对综合事务使用丰富日志记录</span><span class="sxs-lookup"><span data-stu-id="ad6d8-172">Using rich logging for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [<span data-ttu-id="ad6d8-173">使用 Microsoft SQL Server 2008 R2 作为 Lync Server 2013 的 System Center Operations Manager 数据库</span><span class="sxs-lookup"><span data-stu-id="ad6d8-173">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

