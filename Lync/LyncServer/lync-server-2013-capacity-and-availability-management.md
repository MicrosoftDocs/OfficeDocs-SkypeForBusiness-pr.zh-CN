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
ms.openlocfilehash: 169c2e383a1799f5f3ab7ca810de32f86350e51b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-and-availability-management-in-lync-server-2013"></a><span data-ttu-id="59431-102">Lync Server 2013 中的容量和可用性管理</span><span class="sxs-lookup"><span data-stu-id="59431-102">Capacity and availability management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59431-103">_**主题上次修改时间：** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="59431-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="59431-104">容量管理和可用性管理的目的是衡量和控制系统性能。</span><span class="sxs-lookup"><span data-stu-id="59431-104">The purpose of capacity management and availability management is to measure and control system performance.</span></span> <span data-ttu-id="59431-105">我们建议你实施容量管理和可用性管理过程，以便你可以测量和控制系统性能。</span><span class="sxs-lookup"><span data-stu-id="59431-105">We recommend that you implement capacity management and availability management procedures so that you can measure and control system performance.</span></span> <span data-ttu-id="59431-106">你必须知道系统是否可用，以及它是否可以通过设置基线并监视系统以查找趋势来处理当前和所投影的请求。</span><span class="sxs-lookup"><span data-stu-id="59431-106">You have to know whether the system is available and if it can handle the current and the projected demands by setting baselines and monitoring the system to look for trends.</span></span>

<div>

## <a name="capacity-management"></a><span data-ttu-id="59431-107">容量管理</span><span class="sxs-lookup"><span data-stu-id="59431-107">Capacity management</span></span>

<span data-ttu-id="59431-108">容量管理涉及规划、调整大小和控制服务容量，以帮助确保超过你的 SLA 中指定的最低性能级别。</span><span class="sxs-lookup"><span data-stu-id="59431-108">Capacity management involves planning, sizing, and controlling service capacity to help guarantee that the minimum performance levels specified in your SLA are exceeded.</span></span> <span data-ttu-id="59431-109">良好的容量管理有助于确保你能够以合理的成本提供 IT 服务，并且仍能满足你在你的 Sla 中定义的性能级别和客户端。</span><span class="sxs-lookup"><span data-stu-id="59431-109">Good capacity management helps ensure that you can provide IT services at a reasonable cost and still meet the levels of performance defined in your SLAs with the client.</span></span> <span data-ttu-id="59431-110">这些条件可以包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="59431-110">These criteria can include the following:</span></span>

  - <span data-ttu-id="59431-111">**系统响应时间**   这是系统执行典型操作所需的测量时间。</span><span class="sxs-lookup"><span data-stu-id="59431-111">**System Response Time**   This is the measured time that the system takes to do typical actions.</span></span> <span data-ttu-id="59431-112">示例包括音频/视频服务器角色处理音频/视频流量所需的时间、客户创建和加入会议所需的时间或在所有观察者客户端中更新状态所需的时间。</span><span class="sxs-lookup"><span data-stu-id="59431-112">Examples include the time that is required for the audio/video server role to process audio/video traffic, the time that is required for a client to create and join a conference, or the time taken for presence to be updated in all watcher clients.</span></span>

  - <span data-ttu-id="59431-113">**存储容量**   这是存储系统的容量，无论它是内容数据库、备份设备还是本地驱动器。</span><span class="sxs-lookup"><span data-stu-id="59431-113">**Storage Capacity**   This is the capacity of a storage system, whether it is a content database, a backup device, or a local drive.</span></span> <span data-ttu-id="59431-114">示例包括每个网站提供的最大存储空间量以及备份在覆盖之前应存储的时间。</span><span class="sxs-lookup"><span data-stu-id="59431-114">Examples include the maximum amount of storage space to be provided per site and the time that backups should be stored before they are overwritten.</span></span>

<span data-ttu-id="59431-115">调整容量通常是指确保有足够的物理资源可用，例如磁盘空间和网络带宽。</span><span class="sxs-lookup"><span data-stu-id="59431-115">Adjusting capacity is frequently a case of making sure that enough physical resources are available, such as disk space and network bandwidth.</span></span> <span data-ttu-id="59431-116">下表列出了与容量相关的问题的典型分辨率。</span><span class="sxs-lookup"><span data-stu-id="59431-116">The following table lists typical resolutions for capacity-related issues.</span></span>

### <a name="typical-resolutions-for-capacity-related-issues"></a><span data-ttu-id="59431-117">与容量相关的问题的典型解决方案</span><span class="sxs-lookup"><span data-stu-id="59431-117">Typical resolutions for capacity-related issues</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59431-118">问题</span><span class="sxs-lookup"><span data-stu-id="59431-118">Issue</span></span></th>
<th><span data-ttu-id="59431-119">可能的解决方法</span><span class="sxs-lookup"><span data-stu-id="59431-119">Possible resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59431-120">音频/视频性能较差的远程用户</span><span class="sxs-lookup"><span data-stu-id="59431-120">Remote users having poor audio/video performance</span></span></p></td>
<td><p><span data-ttu-id="59431-121">检查以查看 WAN 链接是否提供合适的带宽，以及是否已启用和正确配置 QoS。</span><span class="sxs-lookup"><span data-stu-id="59431-121">Check to see whether appropriate bandwidth is available on the WAN links and if QoS is enabled and appropriately configured.</span></span> <span data-ttu-id="59431-122">检查 QoE 数据。</span><span class="sxs-lookup"><span data-stu-id="59431-122">Check QoE data.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59431-123">Lync 环境的整体响应速度较慢。</span><span class="sxs-lookup"><span data-stu-id="59431-123">Overall response of the Lync environment is slow.</span></span></p></td>
<td><p><span data-ttu-id="59431-124">运行测试以检查现有前端服务器是否可以处理负载。</span><span class="sxs-lookup"><span data-stu-id="59431-124">Run tests to check that the existing front-end servers can deal with the load.</span></span> <span data-ttu-id="59431-125">引入新的前端服务器（如果需要）。检查 SQL 数据库响应时间并修复延迟的原因（例如，改善磁盘输入/输出）。</span><span class="sxs-lookup"><span data-stu-id="59431-125">Introduce a new front-end server if it is needed.Check SQL database response times and fix the causes for the delays (for example, improve disk I/O).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="59431-126">有关更多详细信息的疑难解答将在 Lync Server 网络指南中介绍。</span><span class="sxs-lookup"><span data-stu-id="59431-126">Troubleshooting in greater detail is covered in the Lync Server Networking Guide.</span></span>

<span data-ttu-id="59431-127">容量受系统配置的影响，取决于物理资源（如网络带宽）。</span><span class="sxs-lookup"><span data-stu-id="59431-127">Capacity is affected by system configuration and depends on physical resources such as network bandwidth.</span></span> <span data-ttu-id="59431-128">例如，如果将 Lync 环境配置为在夜间执行完整备份，则必须小心，以帮助确保对最终用户体验的交互式性能的影响最小。</span><span class="sxs-lookup"><span data-stu-id="59431-128">For example, if a Lync environment is configured to perform a full backup nightly, care must be taken to help guarantee that the effect on the interactive performance experienced by end-users is minimized.</span></span>

<span data-ttu-id="59431-129">容量管理是在可接受的级别内保持系统容量并解决以下问题的过程：</span><span class="sxs-lookup"><span data-stu-id="59431-129">Capacity management is the process of keeping the capacity of a system within acceptable levels and addresses the following issues:</span></span>

  - <span data-ttu-id="59431-130">**对需求**   产能要求做出的更改必须进行调整，以考虑系统或组织中的更改。</span><span class="sxs-lookup"><span data-stu-id="59431-130">**Reacting to changes in requirements**   Capacity requirements have to be adjusted to account for changes in the system or the organization.</span></span> <span data-ttu-id="59431-131">例如，如果你的环境决定实现企业语音，则中介服务器和公共交换电话网络（PSTN）网关的数量和位置将非常重要。</span><span class="sxs-lookup"><span data-stu-id="59431-131">For example, if your environment decides to implement Enterprise Voice, the number and placement of Mediation Servers and public switched telephone network (PSTN) gateways will be very important.</span></span> <span data-ttu-id="59431-132">如果你将执行会话初始协议（SIP）中继或直接 SIP，整体设计将显著改变，以提供最佳的企业语音性能。</span><span class="sxs-lookup"><span data-stu-id="59431-132">If you'll be doing Session Initiation Protocol (SIP) trunking or direct SIP, the overall design will be significantly changed to provide the best Enterprise Voice performance.</span></span>

  - <span data-ttu-id="59431-133">**预测未来需求**   某些容量要求随时间的推移而变化。</span><span class="sxs-lookup"><span data-stu-id="59431-133">**Predicting future requirements**   Some capacity requirements change predictably over time.</span></span> <span data-ttu-id="59431-134">通过跟踪趋势，你可以提前规划升级。</span><span class="sxs-lookup"><span data-stu-id="59431-134">By tracking trends you can plan upgrades in advance.</span></span> <span data-ttu-id="59431-135">例如，必须监视各种 Lync 网站之间的可用带宽才能创建基线。</span><span class="sxs-lookup"><span data-stu-id="59431-135">For example, available bandwidth between various Lync sites must be monitored to create a baseline.</span></span> <span data-ttu-id="59431-136">此基线将允许你预测何时必须为这些链接添加更多带宽，因为这些远程网站中的用户计数会随着时间的增加而增加。</span><span class="sxs-lookup"><span data-stu-id="59431-136">This baseline will allow you to predict when you have to add more bandwidth to these links as user count in these remote sites increases with time.</span></span>

</div>

<div>

## <a name="availability-management"></a><span data-ttu-id="59431-137">可用性管理</span><span class="sxs-lookup"><span data-stu-id="59431-137">Availability management</span></span>

<span data-ttu-id="59431-138">可用性管理是确保任何 IT 服务一致、经济高效地提供客户所需的一致、可靠服务级别的过程。</span><span class="sxs-lookup"><span data-stu-id="59431-138">Availability management is the process of making sure that any IT service consistently and cost effectively delivers the level of consistent, reliable service that is required by the customer.</span></span> <span data-ttu-id="59431-139">可用性管理处理的服务损失最小，并确保在服务丢失时采取相应措施。</span><span class="sxs-lookup"><span data-stu-id="59431-139">Availability management deals with minimizing loss of service and with making sure that appropriate action is taken if service is lost.</span></span> <span data-ttu-id="59431-140">在 Lync 环境中，你可能关心企业语音服务是否可用、用户是否可以加入计划的会议等。</span><span class="sxs-lookup"><span data-stu-id="59431-140">In a Lync environment, you may be concerned about whether the Enterprise Voice service is available, whether users can join scheduled conferences, and so on.</span></span> <span data-ttu-id="59431-141">SLA 定义了可接受的频率和中断长度，并允许在系统不可用于计划维护时获得特定时间段。</span><span class="sxs-lookup"><span data-stu-id="59431-141">An SLA defines an acceptable frequency and length of outages and allows for certain periods when the system is unavailable for planned maintenance.</span></span>

<span data-ttu-id="59431-142">如果你必须向管理层提供有关系统可用性的报表，或者如果你有财务或与缺少可用性目标相关的其他处罚，则必须记录可用性数据。</span><span class="sxs-lookup"><span data-stu-id="59431-142">If you have to provide reports to your management about the availability of systems, or if you have financial or other penalties associated with missing availability targets, you must record availability data.</span></span> <span data-ttu-id="59431-143">即使你没有这种正式的要求，也最好至少知道系统在特定时间段内失败的频率。</span><span class="sxs-lookup"><span data-stu-id="59431-143">Even if you do not have such formal requirements, it is a good idea to at least know how frequently a system has failed in a certain time period.</span></span> <span data-ttu-id="59431-144">例如，过去12个月中的系统可用性以及从每次失败恢复所需的时间。</span><span class="sxs-lookup"><span data-stu-id="59431-144">For example, system availability in the last 12 months and how long it took to recover from each failure.</span></span> <span data-ttu-id="59431-145">此信息将帮助你衡量和改进你的团队对系统故障做出响应的有效性。</span><span class="sxs-lookup"><span data-stu-id="59431-145">This information will help you measure and improve your team’s effectiveness in responding to a system failure.</span></span> <span data-ttu-id="59431-146">如果存在争议，它还可以提供有用的信息。</span><span class="sxs-lookup"><span data-stu-id="59431-146">It can also give you useful information if there is a dispute.</span></span>

<span data-ttu-id="59431-147">与可用性相关的度量标准如下所示：</span><span class="sxs-lookup"><span data-stu-id="59431-147">Measures related to availability are as follows:</span></span>

  - <span data-ttu-id="59431-148">**可用性**   通常表示为系统或服务可以访问的时间，与它处于关闭状态的时间相比较。</span><span class="sxs-lookup"><span data-stu-id="59431-148">**Availability**   This is typically expressed as the time that a system or service can be accessed compared to the time that it is down.</span></span> <span data-ttu-id="59431-149">它通常表示为百分比。</span><span class="sxs-lookup"><span data-stu-id="59431-149">It is typically expressed as a percentage.</span></span> <span data-ttu-id="59431-150">（你可能会看到 "三个 9" 或 "五个 9" 的引用。</span><span class="sxs-lookup"><span data-stu-id="59431-150">(You may see references to “three nines” or “five nines”.</span></span> <span data-ttu-id="59431-151">这是99.9% 或99.999% 的可用容量。）</span><span class="sxs-lookup"><span data-stu-id="59431-151">These refer to 99.9 percent or 99.999 percent availability.)</span></span>

  - <span data-ttu-id="59431-152">**可靠性**   这是一个系统故障之间的时间度量，有时在两次失败之间（MTBF）表示为平均值（或平均）时间。</span><span class="sxs-lookup"><span data-stu-id="59431-152">**Reliability**   This is a measure of the time between failures of a system and is sometimes expressed as mean (or average) time between failures (MTBF).</span></span>

  - <span data-ttu-id="59431-153">**修复时间这**   是在发生故障后恢复服务所用的时间，通常表示为平均修复时间（即 "MTTR"）。</span><span class="sxs-lookup"><span data-stu-id="59431-153">**Time to Repair**   This is the time taken to recover a service after a failure has occurred and is often expressed as mean (meaning average) time to repair (MTTR).</span></span>

<span data-ttu-id="59431-154">可用性、可靠性和修复时间相关，如下所示：</span><span class="sxs-lookup"><span data-stu-id="59431-154">Availability, reliability, and time to repair are related as follows:</span></span>

<span data-ttu-id="59431-155">**可用性 = （MTBF-MTTR）/MTBF**   例如，如果服务器在六个月的时间段内失败两次，并且平均不超过20分钟，则 MTBF 为3个月或90天，并且 MTTR 为20分钟。</span><span class="sxs-lookup"><span data-stu-id="59431-155">**Availability = (MTBF – MTTR) / MTBF**   For example, if a server fails two times over a six-month period and is unavailable for an average of 20 minutes, the MTBF is three months or 90 days and the MTTR is 20 minutes.</span></span> <span data-ttu-id="59431-156">因此，可用性 = （90天-20 分钟）/90 days = 99.985%。</span><span class="sxs-lookup"><span data-stu-id="59431-156">Therefore, Availability = (90 days – 20 minutes) / 90 days = 99.985 percent.</span></span>

<span data-ttu-id="59431-157">可用性管理是确保可用性最大化并保留在 Sla 中定义的参数中的过程。</span><span class="sxs-lookup"><span data-stu-id="59431-157">Availability management is the process of making sure that availability is maximized and kept within the parameters that are defined in SLAs.</span></span> <span data-ttu-id="59431-158">可用性管理包括以下过程：</span><span class="sxs-lookup"><span data-stu-id="59431-158">Availability management includes the following processes:</span></span>

  - <span data-ttu-id="59431-159">**监视**   检查服务不可用的时间和时间。</span><span class="sxs-lookup"><span data-stu-id="59431-159">**Monitoring**    Examining when and for how long services are unavailable.</span></span>

  - <span data-ttu-id="59431-160">**报告**   可用性数据应定期提供给管理层、用户和操作团队。</span><span class="sxs-lookup"><span data-stu-id="59431-160">**Reporting**   Availability figures should be regularly provided to management, users, and operations teams.</span></span> <span data-ttu-id="59431-161">这些报表应突出显示趋势并确定正在进行良好工作的区域以及需要注意的区域。</span><span class="sxs-lookup"><span data-stu-id="59431-161">These reports should highlight trends and identify areas that are doing well and areas that require attention.</span></span> <span data-ttu-id="59431-162">该报告应总结 Sla 中设置的目标合规性。</span><span class="sxs-lookup"><span data-stu-id="59431-162">The report should summarize compliance with targets set in the SLAs.</span></span>

  - <span data-ttu-id="59431-163">**改进**   如果可用性不满足在 sla 中定义的目标或趋势在降低可用性的位置，则可用性管理过程应计划补救步骤。</span><span class="sxs-lookup"><span data-stu-id="59431-163">**Improvement**   If availability does not meet targets that are defined in the SLAs or where the trend is toward reduced availability, the availability management process should plan remedial steps.</span></span> <span data-ttu-id="59431-164">这应包括与其他责任团队协作，以突出显示中断的原因并计划补救措施以防止中断的重复。</span><span class="sxs-lookup"><span data-stu-id="59431-164">This should include working with other responsible teams to highlight reasons for outages and to plan remedial actions to prevent a recurrence of the outages.</span></span>

<span data-ttu-id="59431-165">容量和可用性度量是重复性任务，非常适合于自动工具和脚本，如 Microsoft System Center Operations Manager （以前称为 Microsoft Operations Manager），本文档后面部分将进行讨论。</span><span class="sxs-lookup"><span data-stu-id="59431-165">Capacity and availability measurements are repetitive tasks that are ideally suited to automated tools and scripts such as Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which is discussed later in this document.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="59431-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59431-166">See Also</span></span>


[<span data-ttu-id="59431-167">通过 System Center Operations Manager 监视 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59431-167">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

