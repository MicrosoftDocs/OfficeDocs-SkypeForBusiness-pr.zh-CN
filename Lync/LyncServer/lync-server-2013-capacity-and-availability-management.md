---
title: Lync Server 2013：容量和可用性管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity and availability management
ms:assetid: 207a2997-f482-4bee-892d-d2b112294481
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720325(v=OCS.15)
ms:contentKeyID: 63969586
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efef66bcac833bb67c67dc453c25f3e0f6d51ba1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512849"
---
# <a name="capacity-and-availability-management-in-lync-server-2013"></a><span data-ttu-id="1d3d5-102">Lync Server 2013 中的容量和可用性管理</span><span class="sxs-lookup"><span data-stu-id="1d3d5-102">Capacity and availability management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d3d5-103">_**上次修改的主题：** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="1d3d5-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="1d3d5-104">容量管理和可用性管理的目的是衡量和控制系统性能。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-104">The purpose of capacity management and availability management is to measure and control system performance.</span></span> <span data-ttu-id="1d3d5-105">我们建议您实施容量管理和可用性管理过程，以便您能够衡量和控制系统性能。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-105">We recommend that you implement capacity management and availability management procedures so that you can measure and control system performance.</span></span> <span data-ttu-id="1d3d5-106">您必须知道系统是否可用，以及是否可以通过设置基线并监视系统以查找趋势来处理当前和预期的需求。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-106">You have to know whether the system is available and if it can handle the current and the projected demands by setting baselines and monitoring the system to look for trends.</span></span>

<div>

## <a name="capacity-management"></a><span data-ttu-id="1d3d5-107">容量管理</span><span class="sxs-lookup"><span data-stu-id="1d3d5-107">Capacity management</span></span>

<span data-ttu-id="1d3d5-108">容量管理涉及规划、调整大小和控制服务容量，以帮助确保超出 SLA 中指定的最低性能级别。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-108">Capacity management involves planning, sizing, and controlling service capacity to help guarantee that the minimum performance levels specified in your SLA are exceeded.</span></span> <span data-ttu-id="1d3d5-109">良好的容量管理有助于确保您能够以合理的成本提供 IT 服务，并且仍能满足在客户端的 Sla 中定义的性能级别。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-109">Good capacity management helps ensure that you can provide IT services at a reasonable cost and still meet the levels of performance defined in your SLAs with the client.</span></span> <span data-ttu-id="1d3d5-110">这些条件可能包括：</span><span class="sxs-lookup"><span data-stu-id="1d3d5-110">These criteria can include the following:</span></span>

  - <span data-ttu-id="1d3d5-111">**系统响应时间**    这是系统执行典型操作所需的度量时间。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-111">**System Response Time**   This is the measured time that the system takes to do typical actions.</span></span> <span data-ttu-id="1d3d5-112">示例包括音频/视频服务器角色处理音频/视频流量所需的时间、客户端创建和加入会议所需的时间或在所有观察程序客户端中更新状态所需的时间。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-112">Examples include the time that is required for the audio/video server role to process audio/video traffic, the time that is required for a client to create and join a conference, or the time taken for presence to be updated in all watcher clients.</span></span>

  - <span data-ttu-id="1d3d5-113">**存储容量**    这是存储系统的容量，无论它是内容数据库、备份设备还是本地驱动器。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-113">**Storage Capacity**   This is the capacity of a storage system, whether it is a content database, a backup device, or a local drive.</span></span> <span data-ttu-id="1d3d5-114">示例包括每个站点要提供的最大存储空间量以及备份在覆盖之前应存储的时间。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-114">Examples include the maximum amount of storage space to be provided per site and the time that backups should be stored before they are overwritten.</span></span>

<span data-ttu-id="1d3d5-115">调整容量通常是指确保有足够的物理资源可用，如磁盘空间和网络带宽。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-115">Adjusting capacity is frequently a case of making sure that enough physical resources are available, such as disk space and network bandwidth.</span></span> <span data-ttu-id="1d3d5-116">下表列出了与容量相关的问题的典型解决方案。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-116">The following table lists typical resolutions for capacity-related issues.</span></span>

### <a name="typical-resolutions-for-capacity-related-issues"></a><span data-ttu-id="1d3d5-117">与容量相关的问题的典型解决方法</span><span class="sxs-lookup"><span data-stu-id="1d3d5-117">Typical resolutions for capacity-related issues</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d3d5-118">问题</span><span class="sxs-lookup"><span data-stu-id="1d3d5-118">Issue</span></span></th>
<th><span data-ttu-id="1d3d5-119">可能的解决方法</span><span class="sxs-lookup"><span data-stu-id="1d3d5-119">Possible resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d3d5-120">具有较差音频/视频性能的远程用户</span><span class="sxs-lookup"><span data-stu-id="1d3d5-120">Remote users having poor audio/video performance</span></span></p></td>
<td><p><span data-ttu-id="1d3d5-121">检查以查看 WAN 链路上是否有合适的带宽，以及是否已启用并正确配置了 QoS。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-121">Check to see whether appropriate bandwidth is available on the WAN links and if QoS is enabled and appropriately configured.</span></span> <span data-ttu-id="1d3d5-122">检查 QoE 数据。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-122">Check QoE data.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d3d5-123">Lync 环境的整体响应速度较慢。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-123">Overall response of the Lync environment is slow.</span></span></p></td>
<td><p><span data-ttu-id="1d3d5-124">运行测试以检查现有的前端服务器是否可以处理负载。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-124">Run tests to check that the existing front-end servers can deal with the load.</span></span> <span data-ttu-id="1d3d5-125">引入新的前端服务器（如果需要）。检查 SQL 数据库响应时间并修复延迟的原因 (例如，改善磁盘 i/o) 。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-125">Introduce a new front-end server if it is needed.Check SQL database response times and fix the causes for the delays (for example, improve disk I/O).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1d3d5-126">有关更多详细信息的疑难解答在 Lync Server 网络指南中进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-126">Troubleshooting in greater detail is covered in the Lync Server Networking Guide.</span></span>

<span data-ttu-id="1d3d5-127">容量受系统配置的影响，并取决于物理资源（如网络带宽）。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-127">Capacity is affected by system configuration and depends on physical resources such as network bandwidth.</span></span> <span data-ttu-id="1d3d5-128">例如，如果将 Lync 环境配置为在夜间执行完整备份，则必须小心谨慎，以确保最终用户所需的交互式性能影响最小。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-128">For example, if a Lync environment is configured to perform a full backup nightly, care must be taken to help guarantee that the effect on the interactive performance experienced by end-users is minimized.</span></span>

<span data-ttu-id="1d3d5-129">容量管理是在可接受的级别内保持系统容量的过程，并解决以下问题：</span><span class="sxs-lookup"><span data-stu-id="1d3d5-129">Capacity management is the process of keeping the capacity of a system within acceptable levels and addresses the following issues:</span></span>

  - <span data-ttu-id="1d3d5-130">**对要求**     中的更改做出反应必须调整容量要求以考虑系统或组织中的更改。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-130">**Reacting to changes in requirements**   Capacity requirements have to be adjusted to account for changes in the system or the organization.</span></span> <span data-ttu-id="1d3d5-131">例如，如果您的环境决定实现企业语音，中介服务器和公共交换电话网络的数量和位置 (PSTN) 网关将非常重要。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-131">For example, if your environment decides to implement Enterprise Voice, the number and placement of Mediation Servers and public switched telephone network (PSTN) gateways will be very important.</span></span> <span data-ttu-id="1d3d5-132">如果你将执行会话初始协议 (SIP) 中继或直接 SIP，整体设计将会显著改变，以提供最佳的企业语音性能。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-132">If you'll be doing Session Initiation Protocol (SIP) trunking or direct SIP, the overall design will be significantly changed to provide the best Enterprise Voice performance.</span></span>

  - <span data-ttu-id="1d3d5-133">**预测未来要求**    某些容量要求随时间的推移改变了预见性。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-133">**Predicting future requirements**   Some capacity requirements change predictably over time.</span></span> <span data-ttu-id="1d3d5-134">通过跟踪趋势，可以提前规划升级。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-134">By tracking trends you can plan upgrades in advance.</span></span> <span data-ttu-id="1d3d5-135">例如，必须监控各个 Lync 网站之间的可用带宽以创建基线。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-135">For example, available bandwidth between various Lync sites must be monitored to create a baseline.</span></span> <span data-ttu-id="1d3d5-136">此基准将允许您预测何时必须向这些链接添加更多的带宽，因为这些远程网站中的用户计数随着时间的推移而增加。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-136">This baseline will allow you to predict when you have to add more bandwidth to these links as user count in these remote sites increases with time.</span></span>

</div>

<div>

## <a name="availability-management"></a><span data-ttu-id="1d3d5-137">可用性管理</span><span class="sxs-lookup"><span data-stu-id="1d3d5-137">Availability management</span></span>

<span data-ttu-id="1d3d5-138">可用性管理是确保所有 IT 服务持续且经济高效地提供客户所需的一致、可靠服务级别的过程。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-138">Availability management is the process of making sure that any IT service consistently and cost effectively delivers the level of consistent, reliable service that is required by the customer.</span></span> <span data-ttu-id="1d3d5-139">可用性管理可尽量减少服务损失，并确保在服务丢失时采取适当的措施。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-139">Availability management deals with minimizing loss of service and with making sure that appropriate action is taken if service is lost.</span></span> <span data-ttu-id="1d3d5-140">在 Lync 环境中，您可能关心企业语音服务是否可用，用户是否可以加入预定会议，等等。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-140">In a Lync environment, you may be concerned about whether the Enterprise Voice service is available, whether users can join scheduled conferences, and so on.</span></span> <span data-ttu-id="1d3d5-141">SLA 定义了可接受的频率和中断长度，并且在系统不可用于规划维护的特定时段内允许。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-141">An SLA defines an acceptable frequency and length of outages and allows for certain periods when the system is unavailable for planned maintenance.</span></span>

<span data-ttu-id="1d3d5-142">如果您必须向管理层提供有关系统可用性的报告，或者如果您有财务或其他与缺少可用性目标相关的处罚，则必须记录可用性数据。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-142">If you have to provide reports to your management about the availability of systems, or if you have financial or other penalties associated with missing availability targets, you must record availability data.</span></span> <span data-ttu-id="1d3d5-143">即使您没有这种正式要求，也最好至少知道系统在特定时间段内出现故障的频率。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-143">Even if you do not have such formal requirements, it is a good idea to at least know how frequently a system has failed in a certain time period.</span></span> <span data-ttu-id="1d3d5-144">例如，最近12个月内的系统可用性以及从每个故障中恢复所需的时间。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-144">For example, system availability in the last 12 months and how long it took to recover from each failure.</span></span> <span data-ttu-id="1d3d5-145">此信息将帮助您衡量和提高您的团队对系统故障做出响应的有效性。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-145">This information will help you measure and improve your team’s effectiveness in responding to a system failure.</span></span> <span data-ttu-id="1d3d5-146">如果有争议，它还可以为你提供有用的信息。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-146">It can also give you useful information if there is a dispute.</span></span>

<span data-ttu-id="1d3d5-147">与可用性相关的度量标准如下所示：</span><span class="sxs-lookup"><span data-stu-id="1d3d5-147">Measures related to availability are as follows:</span></span>

  - <span data-ttu-id="1d3d5-148">**可用性**    这通常表示为系统或服务的访问时间与该时间的相对时间。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-148">**Availability**   This is typically expressed as the time that a system or service can be accessed compared to the time that it is down.</span></span> <span data-ttu-id="1d3d5-149">它通常表示为一个百分比。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-149">It is typically expressed as a percentage.</span></span> <span data-ttu-id="1d3d5-150"> (您可能会看到对 "三个九" 或 "五个九" 的引用。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-150">(You may see references to “three nines” or “five nines”.</span></span> <span data-ttu-id="1d3d5-151">它们指的是99.9% 或99.999% 的可用性。 ) </span><span class="sxs-lookup"><span data-stu-id="1d3d5-151">These refer to 99.9 percent or 99.999 percent availability.)</span></span>

  - <span data-ttu-id="1d3d5-152">**可靠性**    这是对系统故障之间的时间的度量，有时表示为平均 (或平均) 次失败之间的时间 (MTBF) 。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-152">**Reliability**   This is a measure of the time between failures of a system and is sometimes expressed as mean (or average) time between failures (MTBF).</span></span>

  - <span data-ttu-id="1d3d5-153">**修复时间**    这是在发生故障后恢复服务所需的时间，通常表示为 (表示修复 (MTTR) 的平均时间) 时间。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-153">**Time to Repair**   This is the time taken to recover a service after a failure has occurred and is often expressed as mean (meaning average) time to repair (MTTR).</span></span>

<span data-ttu-id="1d3d5-154">与修复相关的可用性、可靠性和时间如下所示：</span><span class="sxs-lookup"><span data-stu-id="1d3d5-154">Availability, reliability, and time to repair are related as follows:</span></span>

<span data-ttu-id="1d3d5-155">**可用性 = (MTBF – MTTR) /MTBF**    例如，如果服务器在六个月的时间段内失败两次，且平均不可用20分钟，则 MTBF 为三个月或90天，而 MTTR 为20分钟。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-155">**Availability = (MTBF – MTTR) / MTBF**   For example, if a server fails two times over a six-month period and is unavailable for an average of 20 minutes, the MTBF is three months or 90 days and the MTTR is 20 minutes.</span></span> <span data-ttu-id="1d3d5-156">因此，可用性 = (90 天–20分钟) /90 天 = 99.985%。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-156">Therefore, Availability = (90 days – 20 minutes) / 90 days = 99.985 percent.</span></span>

<span data-ttu-id="1d3d5-157">可用性管理是确保可用性已最大化并在 Sla 中定义的参数中保持不被充分利用的过程。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-157">Availability management is the process of making sure that availability is maximized and kept within the parameters that are defined in SLAs.</span></span> <span data-ttu-id="1d3d5-158">可用性管理包括以下过程：</span><span class="sxs-lookup"><span data-stu-id="1d3d5-158">Availability management includes the following processes:</span></span>

  - <span data-ttu-id="1d3d5-159">**监控**    检查服务不可用的时间和时间。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-159">**Monitoring**    Examining when and for how long services are unavailable.</span></span>

  - <span data-ttu-id="1d3d5-160">**报告**    应定期向管理、用户和操作团队提供可用性图。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-160">**Reporting**   Availability figures should be regularly provided to management, users, and operations teams.</span></span> <span data-ttu-id="1d3d5-161">这些报告应重点介绍趋势，并确定正在进行良好工作的领域以及需要注意的领域。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-161">These reports should highlight trends and identify areas that are doing well and areas that require attention.</span></span> <span data-ttu-id="1d3d5-162">该报告应汇总针对 Sla 中设置的目标的符合性。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-162">The report should summarize compliance with targets set in the SLAs.</span></span>

  - <span data-ttu-id="1d3d5-163">**改进**    如果可用性不满足在 Sla 中定义的目标或趋势在降低可用性的位置，则可用性管理过程应规划补救步骤。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-163">**Improvement**   If availability does not meet targets that are defined in the SLAs or where the trend is toward reduced availability, the availability management process should plan remedial steps.</span></span> <span data-ttu-id="1d3d5-164">这应包括与其他负责的团队合作，以突出显示中断的原因，并规划补救措施以防止中断的重复。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-164">This should include working with other responsible teams to highlight reasons for outages and to plan remedial actions to prevent a recurrence of the outages.</span></span>

<span data-ttu-id="1d3d5-165">容量和可用性指标是非常适合自动化工具和脚本的重复性任务，如 Microsoft System Center Operations Manager (以前的 Microsoft Operations Manager) ，本文档稍后将对此进行讨论。</span><span class="sxs-lookup"><span data-stu-id="1d3d5-165">Capacity and availability measurements are repetitive tasks that are ideally suited to automated tools and scripts such as Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which is discussed later in this document.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1d3d5-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d3d5-166">See Also</span></span>


[<span data-ttu-id="1d3d5-167">使用 System Center Operations Manager 监视 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d3d5-167">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

