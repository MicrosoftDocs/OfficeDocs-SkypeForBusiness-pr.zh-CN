---
title: 'Lync Server 2013: Lync Server 中的健康配置'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Health configuration in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48185305
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a719a5e8695dbbd0705aa649d72a32a2bfdc7d38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="health-configuration-in-lync-server-2013"></a><span data-ttu-id="1b51c-102">Lync Server 2013 中的健康配置</span><span class="sxs-lookup"><span data-stu-id="1b51c-102">Health configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b51c-103">_**主题上次修改时间:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="1b51c-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="1b51c-104">在各种网站、Microsoft 知识库文章和 Lync 服务器资源工具包工具之间, 在运行 Lync Server 时遇到问题的管理员永远不会从解决这些问题的方法开始。</span><span class="sxs-lookup"><span data-stu-id="1b51c-104">Between various websites, Microsoft Knowledge Base articles, and Lync Server Resource Kit tools, administrators who encounter problems when running Lync Server are never far from a way to solve those problems.</span></span>

<span data-ttu-id="1b51c-105">很明显, 没有办法保证 Lync Server 2013 不会遇到问题, 因为 Lync Server 可能受许多功能 (如网络崩溃和硬件故障) 的影响, 产品本身无法控制。</span><span class="sxs-lookup"><span data-stu-id="1b51c-105">Obviously there is no way to guarantee that you will never encounter problems with Lync Server 2013 because Lync Server can be affected by many things—like network crashes and hardware failures—that the product itself cannot control.</span></span> <span data-ttu-id="1b51c-106">通过执行运行状况监视, 管理员可以在转换为实际问题之前识别潜在问题。</span><span class="sxs-lookup"><span data-stu-id="1b51c-106">By implementing health monitoring, administrators can identify potential problems before they turn into actual problems.</span></span> <span data-ttu-id="1b51c-107">例如, 管理员可以使用 Lync Server monitoring 识别趋势和趋势。</span><span class="sxs-lookup"><span data-stu-id="1b51c-107">For example, administrators can use Lync Server monitoring to identify trends and tendencies.</span></span> <span data-ttu-id="1b51c-108">例如, 音频/视频会议数的稳定增加可能会建议在系统过载之前增加容量的需要。</span><span class="sxs-lookup"><span data-stu-id="1b51c-108">For example, a steady increase in the number of audio/video conferences might suggest a need to add capacity before the system becomes overloaded.</span></span>

<span data-ttu-id="1b51c-109">在类似方式下, 管理员可以使用 System Center Operations Manager 执行以下操作: 在发生指定事件时发出实时警报, 并运行主动测试系统的合成事务。</span><span class="sxs-lookup"><span data-stu-id="1b51c-109">In a similar fashion, administrators can use System Center Operations Manager to do such things as issue real-time alerts when specified events occur, and to run synthetic transactions that proactively test the system.</span></span> <span data-ttu-id="1b51c-110">在 Lync Server 中使用合成事务验证用户是否能够成功完成常见任务, 如登录到系统、交换即时消息或拨打位于公共交换电话网络 (PSTN) 的电话。</span><span class="sxs-lookup"><span data-stu-id="1b51c-110">Synthetic transactions are used in Lync Server to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="1b51c-111">例如, 定期运行这些测试可提醒你登录 Lync Server 时遇到潜在问题, 并让你有机会在你的支持团队遇到无法建立连接的呼叫的情况下解决问题。</span><span class="sxs-lookup"><span data-stu-id="1b51c-111">For example, periodically running these tests can alert you to potential problems with users logging on to Lync Server, and give you a chance to correct the problem before your support team is flooded with calls from users unable to make a connection.</span></span> <span data-ttu-id="1b51c-112">通过使用 System Center Operations Manager 运行这些合成事务, 管理员可以定期监控每天24小时内的 Lync Server 部署, 而无需对任何可能出现的警报执行任何其他操作。被颁发。</span><span class="sxs-lookup"><span data-stu-id="1b51c-112">By using System Center Operations Manager to run these synthetic transactions, administrators can routinely monitor their deployment of Lync Server continuously for 24 hours every day without having to do much of anything beyond responding to any alerts that might be issued.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1b51c-113">对于 Lync Server 2013, System Center Operations Manager 管理包还可以检测可能对 Lync Server 产生负面影响的 "外部" 问题。</span><span class="sxs-lookup"><span data-stu-id="1b51c-113">For Lync Server 2013, the Management Pack for System Center Operations Manager is also able to detect "external" issues that can adversely affect Lync Server.</span></span> <span data-ttu-id="1b51c-114">例如, 如果 Internet 信息服务 (IIS) 脱机、Lync Server 计算机上的系统资源低于指定的数量或 Lync 服务器计算机遇到硬件故障, 则可以通知管理员。</span><span class="sxs-lookup"><span data-stu-id="1b51c-114">For example, administrators can be notified if Internet Information Services (IIS) goes offline, system resources on a Lync Server computer fall below a specified amount, or a Lync Server computer experiences a hardware failure.</span></span>



</div>

<span data-ttu-id="1b51c-115">Lync Server 2013 中的健康配置是围绕 System Center Operations Manager 和 Lync Server 管理包的使用而构建的。</span><span class="sxs-lookup"><span data-stu-id="1b51c-115">Health configuration in Lync Server 2013 is built around System Center Operations Manager and the use of Lync Server Management Packs.</span></span> <span data-ttu-id="1b51c-116">这些管理包包含许多新功能和增强功能, 包括:</span><span class="sxs-lookup"><span data-stu-id="1b51c-116">These Management Packs include a number of new features and enhancements, including:</span></span>

  - <span data-ttu-id="1b51c-117">**任何位置的方案可用性。**</span><span class="sxs-lookup"><span data-stu-id="1b51c-117">**Scenario availability from any location.**</span></span> <span data-ttu-id="1b51c-118">Lync Server 2010 管理包引入了通过综合事务监视最终用户方案可用性的概念。</span><span class="sxs-lookup"><span data-stu-id="1b51c-118">The Lync Server 2010 Management Pack introduced the concept of monitoring end user scenario availability with synthetic transactions.</span></span> <span data-ttu-id="1b51c-119">在 Lync Server 2013 中, 这些代理具有更多综合事务, 并且可以从企业内的各种位置运行, 从企业外的远程地理位置, 再到分支机构装置和 Lync Server 2010用于将覆盖范围添加到旧版 Edge 部署的部署。</span><span class="sxs-lookup"><span data-stu-id="1b51c-119">In Lync Server 2013, these agents have more synthetic transactions and can be run from a variety of locations inside the enterprise, from remote geographic locations outside of the enterprise, against branch office appliances and against Lync Server 2010 deployments to add coverage to legacy Edge deployments.</span></span>

  - <span data-ttu-id="1b51c-120">**综合事务日志。**</span><span class="sxs-lookup"><span data-stu-id="1b51c-120">**Synthetic transaction logs.**</span></span> <span data-ttu-id="1b51c-121">当合成事务失败时, 管理员有权访问 HTML 日志以帮助确定失败的内容。</span><span class="sxs-lookup"><span data-stu-id="1b51c-121">When a synthetic transaction fails, administrators have access to HTML logs to help determine what failed.</span></span> <span data-ttu-id="1b51c-122">这包括了解哪些操作失败、每个操作的延迟、用于运行测试的命令行以及遇到的错误。</span><span class="sxs-lookup"><span data-stu-id="1b51c-122">This includes understanding which action failed, the latency of each action, the command-line used to run the test, and the error that was encountered.</span></span>

  - <span data-ttu-id="1b51c-123">**增加了通话可靠性覆盖范围。**</span><span class="sxs-lookup"><span data-stu-id="1b51c-123">**Increased call reliability coverage.**</span></span> <span data-ttu-id="1b51c-124">Lync Server 2010 管理包引入了调用可靠性警报以检测严重连接问题, 这些问题会影响最终用户的音频呼叫。</span><span class="sxs-lookup"><span data-stu-id="1b51c-124">The Lync Server 2010 Management Pack introduced call reliability alerting to detect severe connectivity issues that affect the audio calls of end users.</span></span> <span data-ttu-id="1b51c-125">Lync Server 2013 管理包添加对等即时消息 (IM) 和其他基本会议功能的覆盖范围, 以最大限度地减少干扰, 同时减少噪音。</span><span class="sxs-lookup"><span data-stu-id="1b51c-125">The Lync Server 2013 Management Packs add coverage for peer-to-peer instant messaging (IM) and other basic conferencing features to maximize coverage while reducing noise.</span></span>

  - <span data-ttu-id="1b51c-126">**依赖关系监视。**</span><span class="sxs-lookup"><span data-stu-id="1b51c-126">**Dependency monitoring.**</span></span> <span data-ttu-id="1b51c-127">由于各种外部因素 (如 IIS 处于离线状态、有限 CPU 和内存资源和磁盘问题), Lync Server 方案可能会失败。</span><span class="sxs-lookup"><span data-stu-id="1b51c-127">Lync Server scenarios can fail due to a variety of external factors such as IIS being offline, limited CPU and memory resources, and disk issues.</span></span> <span data-ttu-id="1b51c-128">新的管理包检查几个重要的依赖关系, 以确保管理员知道其影响。</span><span class="sxs-lookup"><span data-stu-id="1b51c-128">The new management packs check several critical dependencies to ensure administrators are aware of their impact.</span></span>

  - <span data-ttu-id="1b51c-129">**增强的报告。**</span><span class="sxs-lookup"><span data-stu-id="1b51c-129">**Enhanced reporting.**</span></span> <span data-ttu-id="1b51c-130">一组报表, 可帮助管理员估计方案可用性、计划容量, 并查看遇到最多问题的组件。</span><span class="sxs-lookup"><span data-stu-id="1b51c-130">A set of reports to help administrators estimate scenario availability, plan for capacity, and see which components are experiencing the most issues.</span></span>

<span data-ttu-id="1b51c-131">管理包中还包含多种功能, 可帮助检测和诊断你的 Lync Server 部署是否能够实时查看运行状况。</span><span class="sxs-lookup"><span data-stu-id="1b51c-131">The Management Packs also include a variety of features to help detect and diagnose provide real-time visibility into the health your Lync Server deployment.</span></span> <span data-ttu-id="1b51c-132">下表列出了这些功能。</span><span class="sxs-lookup"><span data-stu-id="1b51c-132">These features are listed in the following table.</span></span>

### <a name="management-pack-features"></a><span data-ttu-id="1b51c-133">管理包功能</span><span class="sxs-lookup"><span data-stu-id="1b51c-133">Management Pack Features</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b51c-134">功能</span><span class="sxs-lookup"><span data-stu-id="1b51c-134">Feature</span></span></th>
<th><span data-ttu-id="1b51c-135">说明</span><span class="sxs-lookup"><span data-stu-id="1b51c-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b51c-136">综合事务</span><span class="sxs-lookup"><span data-stu-id="1b51c-136">Synthetic Transactions</span></span></p></td>
<td><p><span data-ttu-id="1b51c-137">可从不同位置运行的 Windows PowerShell cmdlet, 以确保最终用户随时可以使用登录、联机状态、即时消息和会议等最终用户方案。</span><span class="sxs-lookup"><span data-stu-id="1b51c-137">Windows PowerShell cmdlets that can be run from various locations to ensure that end user scenarios such as sign-in, presence, IM, and conferencing are readily available to end users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b51c-138">呼叫可靠性警报</span><span class="sxs-lookup"><span data-stu-id="1b51c-138">Call Reliability Alerts</span></span></p></td>
<td><p><span data-ttu-id="1b51c-139">通话详细记录 (CDR) 的数据库查询。</span><span class="sxs-lookup"><span data-stu-id="1b51c-139">Database queries for Call Detail Records (CDR).</span></span> <span data-ttu-id="1b51c-140">这些记录由前端服务器编写, 用于反映最终用户是否能够连接到呼叫或终止通话的原因。</span><span class="sxs-lookup"><span data-stu-id="1b51c-140">These records are written by Front End Servers to reflect whether end users were able to connect to a call or why a call was terminated.</span></span> <span data-ttu-id="1b51c-141">这些查询将导致警告, 这些警报表明各种最终用户遇到连接性问题 (针对对等呼叫或基本会议功能)。</span><span class="sxs-lookup"><span data-stu-id="1b51c-141">These queries result in alerts that indicate when a wide range of end users are experiencing connectivity issues for peer-to-peer calls or basic conferencing functionality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b51c-142">媒体质量警报</span><span class="sxs-lookup"><span data-stu-id="1b51c-142">Media Quality Alerts</span></span></p></td>
<td><p><span data-ttu-id="1b51c-143">查看每次调用结束时客户端发布的体验质量 (QoE) 报告的数据库查询。</span><span class="sxs-lookup"><span data-stu-id="1b51c-143">Database queries that look at Quality of Experience (QoE) reports published by clients at the end of each call.</span></span> <span data-ttu-id="1b51c-144">这些查询将产生警报, 这些警报可查明用户在呼叫和会议期间可能遇到较差媒体质量的情况。</span><span class="sxs-lookup"><span data-stu-id="1b51c-144">These queries result in alerts that pinpoint scenarios where users are likely to be experiencing poor media quality during calls and conferences.</span></span> <span data-ttu-id="1b51c-145">数据基于关键指标 (如数据包延迟和丢失) 构建, 这些指标是直接参与通话质量的已知指标。</span><span class="sxs-lookup"><span data-stu-id="1b51c-145">The data is built upon key metrics such as packet latency and loss, metrics that are known to directly contribute to call quality.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b51c-146">组件运行状况</span><span class="sxs-lookup"><span data-stu-id="1b51c-146">Component Health</span></span></p></td>
<td><p><span data-ttu-id="1b51c-147">单个服务器组件通过使用事件日志和性能计数器来引发警报。</span><span class="sxs-lookup"><span data-stu-id="1b51c-147">Individual server components raise alerts by using event logs and performance counters.</span></span> <span data-ttu-id="1b51c-148">这些警报指示可能严重影响一个或多个最终用户方案的失败条件。</span><span class="sxs-lookup"><span data-stu-id="1b51c-148">These alerts indicate failure conditions that can severely impact one or more end user scenarios.</span></span> <span data-ttu-id="1b51c-149">这些警报还可以指示各种其他故障条件, 包括未运行的服务、高故障率、高消息延迟或连接问题。</span><span class="sxs-lookup"><span data-stu-id="1b51c-149">These alerts can also indicate a variety of other failure conditions, including services not running, high failure rates, high message latency, or connectivity issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b51c-150">依赖运行状况</span><span class="sxs-lookup"><span data-stu-id="1b51c-150">Dependency Health</span></span></p></td>
<td><p><span data-ttu-id="1b51c-151">由于各种外部原因, 可能会发生故障。</span><span class="sxs-lookup"><span data-stu-id="1b51c-151">Failures can occur for a variety of external reasons.</span></span> <span data-ttu-id="1b51c-152">管理包现在监视和收集一些关键外部依赖项的数据, 这些依赖项可能表明存在严重问题, 包括 IIS 可用性、服务器和进程的 CPU 和内存使用率以及磁盘指标。</span><span class="sxs-lookup"><span data-stu-id="1b51c-152">The management packs now monitor and collect data for some of the critical external dependencies that might indicate severe issues, including IIS availability, CPU and memory usage of servers and processes, and disk metrics.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1b51c-153">系统发出的通知分为三个常规类别:</span><span class="sxs-lookup"><span data-stu-id="1b51c-153">The alerts issued by the system have been classified into three general categories:</span></span>

  - <span data-ttu-id="1b51c-154">**高优先级警报。**</span><span class="sxs-lookup"><span data-stu-id="1b51c-154">**High-priority Alerts.**</span></span> <span data-ttu-id="1b51c-155">这些警报指示将导致大型用户组的服务中断的条件。</span><span class="sxs-lookup"><span data-stu-id="1b51c-155">These alerts indicate conditions that will cause service outages for large groups of users.</span></span> <span data-ttu-id="1b51c-156">例如, 单个计算机上的组件故障不是高优先级警报, 因为 Lync Server 2013 具有内置的高可用性功能。</span><span class="sxs-lookup"><span data-stu-id="1b51c-156">For example, a component failure on a single machine is not a high-priority alert because Lync Server 2013 has built-in high availability features.</span></span> <span data-ttu-id="1b51c-157">相反, 高优先级的警报表示的问题非常严重, 无法在晚间唤醒管理员。</span><span class="sxs-lookup"><span data-stu-id="1b51c-157">Instead, high-priority alerts represent problems serious enough “to wake up administrators at night.”</span></span> <span data-ttu-id="1b51c-158">综合事务和脱机服务 (例如, 音频/视频会议) 检测到的中断是高优先级的警报。</span><span class="sxs-lookup"><span data-stu-id="1b51c-158">Outages detected by synthetic transactions and offline services (for example, audio/video conferencing) qualify as high-priority alerts.</span></span>

  - <span data-ttu-id="1b51c-159">**中等优先级的警报 ...**</span><span class="sxs-lookup"><span data-stu-id="1b51c-159">**Medium-priority alerts.**.</span></span> <span data-ttu-id="1b51c-160">这些警报指示影响用户子集或指示通话质量降级的条件。</span><span class="sxs-lookup"><span data-stu-id="1b51c-160">These alerts indicate conditions that affect a subset of users or indicate call quality degradation.</span></span> <span data-ttu-id="1b51c-161">其中包括组件故障、呼叫建立延迟或通话中的音频质量下降等问题。</span><span class="sxs-lookup"><span data-stu-id="1b51c-161">That includes problems such as component failures, latency in call establishment, or degraded audio quality in call.</span></span> <span data-ttu-id="1b51c-162">此类别中的警报是有状态的, 表明问题的当前状态。</span><span class="sxs-lookup"><span data-stu-id="1b51c-162">Alerts in this category are stateful and indicate the current status of the issue.</span></span> <span data-ttu-id="1b51c-163">例如, 假设您的通话时间超过了报警阈值。</span><span class="sxs-lookup"><span data-stu-id="1b51c-163">For example, suppose your call establishment times exceed the alert threshold.</span></span> <span data-ttu-id="1b51c-164">如果通话建立时间返回到正常, 则系统中心运营经理将自动解决这些警报。</span><span class="sxs-lookup"><span data-stu-id="1b51c-164">If call establishment times return to normal, these alerts will be auto-resolved in System Center Operations Manager.</span></span> <span data-ttu-id="1b51c-165">这些警报的预期结果是管理员将在同一工作日查看。</span><span class="sxs-lookup"><span data-stu-id="1b51c-165">The expectation for these alerts is that an administrator will look at them on the same business day.</span></span>

  - <span data-ttu-id="1b51c-166">**其他通知。**</span><span class="sxs-lookup"><span data-stu-id="1b51c-166">**Other alerts.**</span></span> <span data-ttu-id="1b51c-167">这些是来自可能影响特定用户或用户子集的组件的警报。</span><span class="sxs-lookup"><span data-stu-id="1b51c-167">These are alerts from components that might affect a specific user or subset of users.</span></span> <span data-ttu-id="1b51c-168">例如, 通讯簿服务可能无法分析给定用户的 Active Directory 条目。</span><span class="sxs-lookup"><span data-stu-id="1b51c-168">For example, perhaps the Address Book service could not parse the Active Directory entry of a given user.</span></span> <span data-ttu-id="1b51c-169">这些警报的预期是, 管理员在有时间可用时就会访问他们。</span><span class="sxs-lookup"><span data-stu-id="1b51c-169">The expectation for these alerts is that administrators will get to them when they have time available.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1b51c-170">本节内容</span><span class="sxs-lookup"><span data-stu-id="1b51c-170">In This Section</span></span>

  - [<span data-ttu-id="1b51c-171">配置 Lync Server 2013 以与 System Center Operations Manager 配合使用</span><span class="sxs-lookup"><span data-stu-id="1b51c-171">Configuring Lync Server 2013 to work with System Center Operations Manager</span></span>](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [<span data-ttu-id="1b51c-172">在 Lync Server 2013 中对综合事务使用丰富日志记录</span><span class="sxs-lookup"><span data-stu-id="1b51c-172">Using rich logging for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [<span data-ttu-id="1b51c-173">使用 Microsoft SQL Server 2008 R2 作为 Lync Server 2013 的 System Center Operations Manager 数据库</span><span class="sxs-lookup"><span data-stu-id="1b51c-173">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

