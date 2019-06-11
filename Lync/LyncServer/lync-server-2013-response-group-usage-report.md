---
title: 'Lync Server 2013: 响应组使用情况报告'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response Group Usage Report
ms:assetid: 3248b320-a552-400a-8485-6891af4eb0f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558632(v=OCS.15)
ms:contentKeyID: 48183811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9334fea5bded88b4f2453f46a0848819743766d9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-usage-report-in-lync-server-2013"></a><span data-ttu-id="0df0d-102">Lync Server 2013 中的 "响应组使用情况" 报表</span><span class="sxs-lookup"><span data-stu-id="0df0d-102">Response Group Usage Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0df0d-103">_**主题上次修改时间:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="0df0d-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="0df0d-104">"响应组" 应用程序为 Microsoft Lync Server 2013 提供了一种方法, 可根据所拨打的号码和呼叫者对一系列问题的响应 (可选) 应答和路由电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="0df0d-104">The Response Group application provides a way for Microsoft Lync Server 2013 to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="0df0d-105">通常，不会将响应组呼叫路由到个人，而是路由到称为代理组的一组人员。</span><span class="sxs-lookup"><span data-stu-id="0df0d-105">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="0df0d-106">例如, 如果某人呼叫帮助台的电话号码, 则 Lync Server 2013 可以自动将呼叫路由到第一个可用的技术支持代理。</span><span class="sxs-lookup"><span data-stu-id="0df0d-106">For example, if someone calls the phone number for your help desk, Lync Server 2013 can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="0df0d-107">或者, Lync Server 可以询问一系列问题 (如果遇到硬件问题, 请按1。</span><span class="sxs-lookup"><span data-stu-id="0df0d-107">Alternatively, Lync Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="0df0d-108">如果您有软件问题，请按 2。</span><span class="sxs-lookup"><span data-stu-id="0df0d-108">Press 2 if you are having software problems.</span></span> <span data-ttu-id="0df0d-109">如果出现网络问题, 请按3。)然后根据这些问题的答案, 将呼叫路由到最合适的技术支持代理。</span><span class="sxs-lookup"><span data-stu-id="0df0d-109">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="0df0d-110">响应组使用情况报告提供所有响应组工作流接收到的电话呼叫数的详细信息，然后将这些呼叫细分为更多有限类别，例如发起的呼叫、应答的呼叫和放弃的呼叫。</span><span class="sxs-lookup"><span data-stu-id="0df0d-110">The Response Group Usage Report provides a detailed look at the number of phone calls received by all your Response Group workflows, then breaks those calls down into more finite categories such as Offered calls, Answered calls, and Abandoned calls.</span></span>

<span data-ttu-id="0df0d-111">使用响应组使用情况报告的关键是了解报告的呼叫类型之间的差别：</span><span class="sxs-lookup"><span data-stu-id="0df0d-111">The key to working with the Response Group Usage Report is to understand the difference between the reported call types:</span></span>

  - <span data-ttu-id="0df0d-p102">**收到的呼叫**。响应组应用程序的所有实例收到的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="0df0d-p102">**Received calls**. Total number of calls received by all instances of the Response Group application.</span></span>

  - <span data-ttu-id="0df0d-p103">**成功的呼叫**。响应组应用程序所接听的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="0df0d-p103">**Successful calls**. Total number of calls that were picked up by the Response Group application.</span></span>

  - <span data-ttu-id="0df0d-p104">**提供的呼叫**。已转接给响应组代理的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="0df0d-p104">**Offered calls**. Total number of calls that were transferred to a Response Group agent.</span></span>

  - <span data-ttu-id="0df0d-p105">**应答的呼叫**。响应组代理实际应答的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="0df0d-p105">**Answered calls**. Total number of calls that were actually answered by a Response Group agent.</span></span>

  - <span data-ttu-id="0df0d-p106">**放弃的呼叫的百分比**。响应组应用程序已收到但代理未应答的呼叫的百分比。此值的计算方法是用“收到的呼叫数”减去“应答的呼叫数”，然后用所得的值除以收到的呼叫数。例如，如果收到 10 个呼叫，但应答了 7 个，则计算方法是 10 减去 7，得出未应答的呼叫是 3 个。然后用该值除以 10，得出放弃的呼叫的百分比为 30%。</span><span class="sxs-lookup"><span data-stu-id="0df0d-p106">**Percentage of abandoned calls**. Percentage of calls that were received by the Response Group application but were never answered by an agent. This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls. For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls. That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

  - <span data-ttu-id="0df0d-p107">**转接的呼叫**。因队列超时或队列溢出而转接的响应组呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="0df0d-p107">**Transferred calls**. Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

<span data-ttu-id="0df0d-p108">如果您在查看响应组使用情况报告时想不起来其中任何呼叫类型的定义，只需将鼠标放在相应的呼叫类型标签上。将显示工具提示来提供呼叫类型的简要说明。</span><span class="sxs-lookup"><span data-stu-id="0df0d-p108">If you are looking at the Response Group Usage Report and can't remember the definition for any of these call types, simply hold your mouse over the appropriate call type label. A tooltip will appear that offers a brief description of the call type.</span></span>

<span data-ttu-id="0df0d-p109">可通过响应组使用情况报告筛选工作流 URI（与该工作流关联的 SIP 地址）。不过，该报告中实际上并不显示工作流 URI。如果您希望了解哪些工作流应答最多的呼叫或哪些工作流遇到最多的转接呼叫等事项，请单击相应指标以打开该给定时间段内的响应组呼叫列表报告。该报告列出了工作流 URI。</span><span class="sxs-lookup"><span data-stu-id="0df0d-p109">The Response Group Usage Report allows you to filter on a workflow URI (the SIP address associated with that workflow). However, workflow URIs do not actually appear on the report itself. If you would like to know things such as which workflows are answering the most calls or which workflows are experiencing the most transferred calls, click the appropriate metric to open the Response Group Call List Report for that given time period. That reports does list the workflow URIs.</span></span>

<div>

## <a name="accessing-the-response-group-usage-report"></a><span data-ttu-id="0df0d-133">访问响应组使用情况报告</span><span class="sxs-lookup"><span data-stu-id="0df0d-133">Accessing the Response Group Usage Report</span></span>

<span data-ttu-id="0df0d-134">可从监控报告主页访问响应组使用情况报告。</span><span class="sxs-lookup"><span data-stu-id="0df0d-134">The Response Group Usage Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="0df0d-135">通过单击以下任一指标, 可以向下钻取到[Lync Server 2013 中的 "响应组呼叫列表" 报告](lync-server-2013-response-group-call-list-report.md):</span><span class="sxs-lookup"><span data-stu-id="0df0d-135">You can drill down to the [Response Group Call List Report in Lync Server 2013](lync-server-2013-response-group-call-list-report.md) by clicking any of the following metrics:</span></span>

  - <span data-ttu-id="0df0d-136">收到的呼叫</span><span class="sxs-lookup"><span data-stu-id="0df0d-136">Received calls</span></span>

  - <span data-ttu-id="0df0d-137">成功的呼叫</span><span class="sxs-lookup"><span data-stu-id="0df0d-137">Successful calls</span></span>

  - <span data-ttu-id="0df0d-138">提供的呼叫</span><span class="sxs-lookup"><span data-stu-id="0df0d-138">Offered calls</span></span>

  - <span data-ttu-id="0df0d-139">应答的呼叫</span><span class="sxs-lookup"><span data-stu-id="0df0d-139">Answered calls</span></span>

  - <span data-ttu-id="0df0d-140">转接的呼叫</span><span class="sxs-lookup"><span data-stu-id="0df0d-140">Transferred calls</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-usage-report"></a><span data-ttu-id="0df0d-141">充分利用响应组使用情况报告</span><span class="sxs-lookup"><span data-stu-id="0df0d-141">Making the Best Use of the Response Group Usage Report</span></span>

<span data-ttu-id="0df0d-142">响应组使用情况报告的值得关注的用途之一可能不是显而易见的：能够检索单个响应组工作流的使用情况信息。</span><span class="sxs-lookup"><span data-stu-id="0df0d-142">One of the more interesting uses of the Response Group Usage Report might not be readily apparent: the ability to retrieve usage information for a single Response Group workflow.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="0df0d-143">响应组工作流基本上是一组说明, 用于确定当用户拨打特定电话号码时 Lync 服务器的功能。</span><span class="sxs-lookup"><span data-stu-id="0df0d-143">A Response Group workflow is basically a set of instructions that determines what Lync Server does when a user dials a particular phone number.</span></span> <span data-ttu-id="0df0d-144">为此, 每个工作流都与一个电话号码唯一关联。</span><span class="sxs-lookup"><span data-stu-id="0df0d-144">To that end, each workflow is uniquely associated with a phone number.</span></span> <span data-ttu-id="0df0d-145">当有人调用该号码时, 工作流会确定如何处理通话。</span><span class="sxs-lookup"><span data-stu-id="0df0d-145">When someone calls that number, the workflow determines how the call will be handled.</span></span> <span data-ttu-id="0df0d-146">例如, 工作流可能会导致呼叫路由到一系列交互式语音响应 (IVR) 问题, 提示呼叫者输入其他信息 ("按1以获得硬件支持。</span><span class="sxs-lookup"><span data-stu-id="0df0d-146">For example, the workflow might cause the call to be routed to a series of interactive voice response (IVR) questions that prompt the caller to enter additional information ("Press 1 for hardware support.</span></span> <span data-ttu-id="0df0d-147">按2获得软件支持。 ")。</span><span class="sxs-lookup"><span data-stu-id="0df0d-147">Press 2 for software support.").</span></span> <span data-ttu-id="0df0d-148">或者, 该工作流可能会导致呼叫放置在队列中, 并且呼叫者将置于保持状态, 直到有可用的代理接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="0df0d-148">Alternatively, the workflow might cause the call to be placed in a queue , with the caller put on hold until an agent is available to answer the call.</span></span> <span data-ttu-id="0df0d-149">工作流还规定了用于应答呼叫的代理的可用性: 工作流用于配置工作时间 (一周的天数) 和假日 (当工程师可以接听呼叫时的天数) 和假日 (在没有代理可供应答的情况中)。通话)。</span><span class="sxs-lookup"><span data-stu-id="0df0d-149">The availability of agents to answer calls is also dictated by the workflow: workflows are used to configure both business hours (the days of the week and the times of day when agents are available to answer calls) and holidays (days when no agents are available to answer calls).</span></span> <span data-ttu-id="0df0d-150">无论何时拨打属于响应组应用程序的电话号码, 您实际上都是在呼叫响应组工作流。</span><span class="sxs-lookup"><span data-stu-id="0df0d-150">Any time you dial a phone number that belongs to the Response Group application you are essentially calling a Response Group workflow.</span></span>



</div>

<span data-ttu-id="0df0d-p112">虽然工作流 URI 不显示在响应组使用情况报告中，但仍可以查看单个工作流的使用情况统计信息，这通常极其有用。例如，假定您最近开展了一项新的广告活动并很想知道人们是否通过电话询问该产品。如果您已将响应组工作流与广告活动中提供的电话号码相关联，则可以轻松地查看有多少人（如果有）呼叫了该号码。</span><span class="sxs-lookup"><span data-stu-id="0df0d-p112">Although workflow URIs do not appear in the Response Group Usage Report, it's still possible to view the usage statistics for a single workflow, something that is often extremely useful. For example, suppose you recently unveiled a new ad campaign and are curious to know whether people are calling in to ask about that product. If you have associated a Response Group workflow with the phone number given in the ad campaign, you can easily check to see how many people (if any) are calling that number.</span></span>

<span data-ttu-id="0df0d-154">您可能还使用类似的方法来测量内部技术支持或客户服务部门处理的呼叫数。</span><span class="sxs-lookup"><span data-stu-id="0df0d-154">You might also use a similar approach to gauge the number of calls being handled by your internal help desk or your customer service department.</span></span>

<span data-ttu-id="0df0d-155">若要查看特定工作流的使用情况统计信息，请在“工作流 URI”框中输入工作流 URI。</span><span class="sxs-lookup"><span data-stu-id="0df0d-155">To review usage statistics for a particular workflow, enter the workflow URI in the Workflow URI box.</span></span> <span data-ttu-id="0df0d-156">当然，正如上文所述，工作流 URI（与工作流关联的 SIP 地址）不显示在报告上。</span><span class="sxs-lookup"><span data-stu-id="0df0d-156">Of course, as noted, workflow URIs (the SIP address associated with a workflow) do not appear on the report.</span></span> <span data-ttu-id="0df0d-157">这意味着您需要查找某种其他方法来确定工作流的 URI。</span><span class="sxs-lookup"><span data-stu-id="0df0d-157">That means you need to find some other way to determine the URI of a workflow.</span></span> <span data-ttu-id="0df0d-158">执行此操作的一种方法是使用 Windows PowerShell 和 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="0df0d-158">One way to do this is to use Windows PowerShell and the Lync Server Management Shell.</span></span> <span data-ttu-id="0df0d-159">例如，以下命令返回您的所有响应组工作流的 URI：</span><span class="sxs-lookup"><span data-stu-id="0df0d-159">For example, this command returns the URIs for all your Response Group workflows:</span></span>

    Get-CsRgsWorkflow | Select-Object Name, PrimaryUri

<span data-ttu-id="0df0d-160">这将返回与以下类似的数据：</span><span class="sxs-lookup"><span data-stu-id="0df0d-160">That will return data similar to this:</span></span>

    Name                            PrimaryUri
    ----                            ----------
    Customer Support                sip:support@litwareinc.com
    Help Desk                       sip:helpdesk@litwareinc.com
    New Ad Campaign                 sip:newads@litwareinc.com

<span data-ttu-id="0df0d-161">以下命令返回名为“New Ad Campaign”的单个工作流的信息：</span><span class="sxs-lookup"><span data-stu-id="0df0d-161">This command returns information for a single workflow, the one with the name New Ad Campaign:</span></span>

    Get-CsRgsWorkflow -Name "New Ad Campaign" | Select-Object Name, PrimaryUri

</div>

<div>

## <a name="filters"></a><span data-ttu-id="0df0d-162">筛选器</span><span class="sxs-lookup"><span data-stu-id="0df0d-162">Filters</span></span>

<span data-ttu-id="0df0d-p114">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，通过响应组使用情况报告，您可以查看所有响应组工作流的数据，也可以查看单个工作流的数据。您还可以选择数据的分组方式。在此示例中，将按小时、日、周或月对使用情况进行分组。</span><span class="sxs-lookup"><span data-stu-id="0df0d-p114">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Response Group Usage Report enables you to view data for all your Response Group workflows or to view data for an individual workflow. You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="0df0d-167">下表列出了可用于响应组使用情况报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="0df0d-167">The following table lists the filters that you can use with the Response Group Usage Report.</span></span>

### <a name="response-group-usage-report-filters"></a><span data-ttu-id="0df0d-168">响应组使用情况报告筛选器</span><span class="sxs-lookup"><span data-stu-id="0df0d-168">Response Group Usage Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0df0d-169">名称</span><span class="sxs-lookup"><span data-stu-id="0df0d-169">Name</span></span></th>
<th><span data-ttu-id="0df0d-170">说明</span><span class="sxs-lookup"><span data-stu-id="0df0d-170">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0df0d-171"><strong>从</strong></span><span class="sxs-lookup"><span data-stu-id="0df0d-171"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="0df0d-p115">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0df0d-p115">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="0df0d-174">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="0df0d-174">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="0df0d-p116">如果您未输入开始时间，该报告会自动将将某个特定日期的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="0df0d-p116">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0df0d-177">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="0df0d-177">7/7/2012</span></span></p>
<p><span data-ttu-id="0df0d-178">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="0df0d-178">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0df0d-179">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="0df0d-179">7/3/2012</span></span></p>
<p><span data-ttu-id="0df0d-180">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="0df0d-180">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0df0d-181"><strong>到</strong></span><span class="sxs-lookup"><span data-stu-id="0df0d-181"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="0df0d-p117">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0df0d-p117">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="0df0d-184">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="0df0d-184">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="0df0d-p118">如果您未输入结束时间，该报告会自动将某个特定日期的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="0df0d-p118">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0df0d-187">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="0df0d-187">7/7/2012</span></span></p>
<p><span data-ttu-id="0df0d-188">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="0df0d-188">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0df0d-189">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="0df0d-189">7/3/2012</span></span></p>
<p><span data-ttu-id="0df0d-190">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="0df0d-190">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0df0d-191"><strong>间隔</strong></span><span class="sxs-lookup"><span data-stu-id="0df0d-191"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="0df0d-p119">时间间隔。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="0df0d-p119">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0df0d-194">每小时（最多可显示 25 个小时）</span><span class="sxs-lookup"><span data-stu-id="0df0d-194">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0df0d-195">每天（最多可显示 31 天）</span><span class="sxs-lookup"><span data-stu-id="0df0d-195">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0df0d-196">每周（最多可显示 12 周）</span><span class="sxs-lookup"><span data-stu-id="0df0d-196">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0df0d-197">每月（最多可显示 12 个月）</span><span class="sxs-lookup"><span data-stu-id="0df0d-197">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="0df0d-198">如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。</span><span class="sxs-lookup"><span data-stu-id="0df0d-198">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="0df0d-199">例如, 如果选择 "开始日期 7/7/2012" 和 "结束日期 2/28/2012" 的 "每日间隔", 则会显示 8/7/2012 12:00 AM 到 9/7/2012 12:00 AM 的数据 (即, 总共31天的数据)。</span><span class="sxs-lookup"><span data-stu-id="0df0d-199">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0df0d-200"><strong>工作流 URI</strong></span><span class="sxs-lookup"><span data-stu-id="0df0d-200"><strong>Workflow URI</strong></span></span></p></td>
<td><p><span data-ttu-id="0df0d-p121">允许您限制返回的数据，以便仅显示指定响应组工作流的数据。若要使用该筛选器，请输入工作流 SIP 地址。例如：</span><span class="sxs-lookup"><span data-stu-id="0df0d-p121">Enables you to limit the returned data to the specified Response Group workflow. To use this filter, enter the Workflow SIP address. For example:</span></span></p>
<p><span data-ttu-id="0df0d-204">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0df0d-204">sip:helpdesk@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="0df0d-205">指标</span><span class="sxs-lookup"><span data-stu-id="0df0d-205">Metrics</span></span>

<span data-ttu-id="0df0d-206">下表列出了响应组使用情况报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="0df0d-206">The following table lists the information provided in the Response Group Usage Report.</span></span>

### <a name="response-group-usage-report-metrics"></a><span data-ttu-id="0df0d-207">响应组使用情况报告指标</span><span class="sxs-lookup"><span data-stu-id="0df0d-207">Response Group Usage Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0df0d-208">名称</span><span class="sxs-lookup"><span data-stu-id="0df0d-208">Name</span></span></th>
<th><span data-ttu-id="0df0d-209">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="0df0d-209">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0df0d-210">描述</span><span class="sxs-lookup"><span data-stu-id="0df0d-210">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0df0d-211"><strong>每小时</strong></span><span class="sxs-lookup"><span data-stu-id="0df0d-211"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="0df0d-212"><strong>每天</strong></span><span class="sxs-lookup"><span data-stu-id="0df0d-212"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="0df0d-213"><strong>每周</strong></span><span class="sxs-lookup"><span data-stu-id="0df0d-213"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="0df0d-214"><strong>每月</strong></span><span class="sxs-lookup"><span data-stu-id="0df0d-214"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="0df0d-215">否</span><span class="sxs-lookup"><span data-stu-id="0df0d-215">No</span></span></p></td>
<td><p><span data-ttu-id="0df0d-216">指示所选的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="0df0d-216">Indicates the selected time interval.</span></span> <span data-ttu-id="0df0d-217">如果适用，可单击某一给定的时间间隔以查看该间隔的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0df0d-217">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="0df0d-218">例如, 如果你使用的是每日间隔, 并且单击 "7/7/2012", 你将看到该日期的用户注册活动的每小时细目。</span><span class="sxs-lookup"><span data-stu-id="0df0d-218">For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0df0d-219"><strong>收到的呼叫</strong></span><span class="sxs-lookup"><span data-stu-id="0df0d-219"><strong>Received calls</strong></span></span></p></td>
<td><p><span data-ttu-id="0df0d-220">否</span><span class="sxs-lookup"><span data-stu-id="0df0d-220">No</span></span></p></td>
<td><p><span data-ttu-id="0df0d-p123">响应组应用程序的所有实例收到的呼叫总数。单击此项时，报告向您显示所选时间段的响应组呼叫列表报告。</span><span class="sxs-lookup"><span data-stu-id="0df0d-p123">Total number of calls received by all instances of the Response Group application. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0df0d-223"><strong>成功的呼叫</strong></span><span class="sxs-lookup"><span data-stu-id="0df0d-223"><strong>Successful calls</strong></span></span></p></td>
<td><p><span data-ttu-id="0df0d-224">否</span><span class="sxs-lookup"><span data-stu-id="0df0d-224">No</span></span></p></td>
<td><p><span data-ttu-id="0df0d-p124">响应组应用程序接听的呼叫总数。单击此项时，报告向您显示所选时间段的响应组呼叫列表报告。</span><span class="sxs-lookup"><span data-stu-id="0df0d-p124">Total number of calls that were picked up the Response Group application. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0df0d-227"><strong>提供的呼叫</strong></span><span class="sxs-lookup"><span data-stu-id="0df0d-227"><strong>Offered calls</strong></span></span></p></td>
<td><p><span data-ttu-id="0df0d-228">否</span><span class="sxs-lookup"><span data-stu-id="0df0d-228">No</span></span></p></td>
<td><p><span data-ttu-id="0df0d-p125">转接到响应组代理的呼叫总数。单击此项时，报告向您显示所选时间段的响应组呼叫列表报告。</span><span class="sxs-lookup"><span data-stu-id="0df0d-p125">Total number of calls that were transferred to a Response Group agent. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0df0d-231"><strong>应答的呼叫</strong></span><span class="sxs-lookup"><span data-stu-id="0df0d-231"><strong>Answered calls</strong></span></span></p></td>
<td><p><span data-ttu-id="0df0d-232">否</span><span class="sxs-lookup"><span data-stu-id="0df0d-232">No</span></span></p></td>
<td><p><span data-ttu-id="0df0d-p126">响应组代理实际应答的呼叫总数。单击此项时，报告向您显示所选时间段的响应组呼叫列表报告。</span><span class="sxs-lookup"><span data-stu-id="0df0d-p126">Total number of calls that were actually answered by a Response Group agent. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0df0d-235"><strong>放弃的呼叫的百分比</strong></span><span class="sxs-lookup"><span data-stu-id="0df0d-235"><strong>Percentage of abandoned calls</strong></span></span></p></td>
<td><p><span data-ttu-id="0df0d-236">否</span><span class="sxs-lookup"><span data-stu-id="0df0d-236">No</span></span></p></td>
<td><p><span data-ttu-id="0df0d-p127">响应组应用程序已收到但代理未应答的呼叫总数。它的计算方法是“收到的呼叫”减去“应答的呼叫”，然后用所得的值除以收到的呼叫数。例如，如果收到了 10 个呼叫，但应答了 7 个，则计算方式是 10 减去 7，得出未应答的呼叫是 3 个。然后用该值除以 10，得出放弃的呼叫的百分比为 30%。</span><span class="sxs-lookup"><span data-stu-id="0df0d-p127">Total number of calls that were received by the Response Group application but were never answered by an agent. This is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of received calls. For example, if you have 10 received calls and seven were answered, you would subtract seven from 10, leaving three unanswered calls. That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0df0d-241"><strong>代理的平均呼叫分钟数</strong></span><span class="sxs-lookup"><span data-stu-id="0df0d-241"><strong>Average call minutes by agent</strong></span></span></p></td>
<td><p><span data-ttu-id="0df0d-242">否</span><span class="sxs-lookup"><span data-stu-id="0df0d-242">No</span></span></p></td>
<td><p><span data-ttu-id="0df0d-243">响应组代理应答一个呼叫平均所用的时间。</span><span class="sxs-lookup"><span data-stu-id="0df0d-243">Average amount of time a Response Group agent spent on a call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0df0d-244"><strong>转接的呼叫</strong></span><span class="sxs-lookup"><span data-stu-id="0df0d-244"><strong>Transferred calls</strong></span></span></p></td>
<td><p><span data-ttu-id="0df0d-245">否</span><span class="sxs-lookup"><span data-stu-id="0df0d-245">No</span></span></p></td>
<td><p><span data-ttu-id="0df0d-p128">因队列超时或队列溢出而转接的响应组呼叫总数。单击此项时，报告向您显示所选时间段的响应组呼叫列表报告。</span><span class="sxs-lookup"><span data-stu-id="0df0d-p128">Total number of Response Group calls that were transferred because of a queue timeout or queue overflow. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

