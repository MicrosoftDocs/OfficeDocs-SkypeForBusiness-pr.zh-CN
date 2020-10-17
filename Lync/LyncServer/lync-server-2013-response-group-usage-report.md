---
title: Lync Server 2013：响应组使用情况报告
description: Lync Server 2013：响应组使用情况报告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group Usage Report
ms:assetid: 3248b320-a552-400a-8485-6891af4eb0f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558632(v=OCS.15)
ms:contentKeyID: 48183811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e541a618e8578debc84630037d530c96f4e39ea3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553058"
---
# <a name="response-group-usage-report-in-lync-server-2013"></a><span data-ttu-id="ffdfe-103">Lync Server 2013 中的响应组使用情况报告</span><span class="sxs-lookup"><span data-stu-id="ffdfe-103">Response Group Usage Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffdfe-104">_**上次修改的主题：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="ffdfe-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="ffdfe-105">响应组应用程序为 Microsoft Lync Server 2013 提供了一种方法，以根据拨打的号码和呼叫者对一系列问题的响应（可选）应答和路由电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-105">The Response Group application provides a way for Microsoft Lync Server 2013 to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="ffdfe-106">通常，响应组呼叫不路由到单个人员，而是路由到称为代理组的一组人员。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-106">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="ffdfe-107">例如，如果有人呼叫帮助台的电话号码，Lync Server 2013 可以自动将该呼叫路由到第一个可用的技术支持代理。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-107">For example, if someone calls the phone number for your help desk, Lync Server 2013 can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="ffdfe-108">或者，如果遇到硬件问题，Lync Server 可以 ( "请按1来提出一系列问题。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-108">Alternatively, Lync Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="ffdfe-109">如果您有软件问题，请按 2。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-109">Press 2 if you are having software problems.</span></span> <span data-ttu-id="ffdfe-110">如果遇到网络问题，请按3。) ，然后根据这些问题的答案将呼叫路由到最合适的技术支持代理。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-110">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="ffdfe-111">响应组使用情况报告提供所有响应组工作流接收到的电话呼叫数的详细信息，然后将这些呼叫细分为更多有限类别，例如发起的呼叫、应答的呼叫和放弃的呼叫。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-111">The Response Group Usage Report provides a detailed look at the number of phone calls received by all your Response Group workflows, then breaks those calls down into more finite categories such as Offered calls, Answered calls, and Abandoned calls.</span></span>

<span data-ttu-id="ffdfe-112">使用响应组使用情况报告的关键是了解报告的呼叫类型之间的差别：</span><span class="sxs-lookup"><span data-stu-id="ffdfe-112">The key to working with the Response Group Usage Report is to understand the difference between the reported call types:</span></span>

  - <span data-ttu-id="ffdfe-p102">**收到的呼叫**。响应组应用程序的所有实例收到的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-p102">**Received calls**. Total number of calls received by all instances of the Response Group application.</span></span>

  - <span data-ttu-id="ffdfe-115">**成功呼叫**。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-115">**Successful calls**.</span></span> <span data-ttu-id="ffdfe-116">响应组应用程序选取的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-116">Total number of calls that were picked up by the Response Group application.</span></span>

  - <span data-ttu-id="ffdfe-p104">**发起的呼叫**。转接到响应组代理的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-p104">**Offered calls**. Total number of calls that were transferred to a Response Group agent.</span></span>

  - <span data-ttu-id="ffdfe-p105">**应答的呼叫**。响应组代理实际应答的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-p105">**Answered calls**. Total number of calls that were actually answered by a Response Group agent.</span></span>

  - <span data-ttu-id="ffdfe-p106">**放弃的呼叫的百分比**。响应组应用程序已收到但代理未应答的呼叫的百分比。此值的计算方法是用“收到的呼叫数”减去“应答的呼叫数”，然后用所得的值除以收到的呼叫数。例如，如果收到 10 个呼叫，但应答了 7 个，则计算方法是 10 减去 7，得出未应答的呼叫是 3 个。然后用该值除以 10，得出放弃的呼叫的百分比为 30%。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-p106">**Percentage of abandoned calls**. Percentage of calls that were received by the Response Group application but were never answered by an agent. This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls. For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls. That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

  - <span data-ttu-id="ffdfe-p107">**转接的呼叫**。因队列超时或队列溢出而转接的响应组呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-p107">**Transferred calls**. Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

<span data-ttu-id="ffdfe-p108">如果您在查看响应组使用情况报告时想不起来其中任何呼叫类型的定义，只需将鼠标放在相应的呼叫类型标签上。将显示工具提示来提供呼叫类型的简要说明。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-p108">If you are looking at the Response Group Usage Report and can't remember the definition for any of these call types, simply hold your mouse over the appropriate call type label. A tooltip will appear that offers a brief description of the call type.</span></span>

<span data-ttu-id="ffdfe-p109">可通过响应组使用情况报告筛选工作流 URI（与该工作流关联的 SIP 地址）。不过，该报告中实际上并不显示工作流 URI。如果您希望了解哪些工作流应答最多的呼叫或哪些工作流遇到最多的转接呼叫等事项，请单击相应指标以打开该给定时间段内的响应组呼叫列表报告。该报告列出了工作流 URI。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-p109">The Response Group Usage Report allows you to filter on a workflow URI (the SIP address associated with that workflow). However, workflow URIs do not actually appear on the report itself. If you would like to know things such as which workflows are answering the most calls or which workflows are experiencing the most transferred calls, click the appropriate metric to open the Response Group Call List Report for that given time period. That reports does list the workflow URIs.</span></span>

<div>

## <a name="accessing-the-response-group-usage-report"></a><span data-ttu-id="ffdfe-134">访问响应组使用情况报告</span><span class="sxs-lookup"><span data-stu-id="ffdfe-134">Accessing the Response Group Usage Report</span></span>

<span data-ttu-id="ffdfe-135">可从监控报告主页访问响应组使用情况报告。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-135">The Response Group Usage Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="ffdfe-136">您可以通过单击以下任一指标深入到 [Lync Server 2013 中的响应组呼叫列表报告](lync-server-2013-response-group-call-list-report.md) ：</span><span class="sxs-lookup"><span data-stu-id="ffdfe-136">You can drill down to the [Response Group Call List Report in Lync Server 2013](lync-server-2013-response-group-call-list-report.md) by clicking any of the following metrics:</span></span>

  - <span data-ttu-id="ffdfe-137">收到的呼叫</span><span class="sxs-lookup"><span data-stu-id="ffdfe-137">Received calls</span></span>

  - <span data-ttu-id="ffdfe-138">成功呼叫</span><span class="sxs-lookup"><span data-stu-id="ffdfe-138">Successful calls</span></span>

  - <span data-ttu-id="ffdfe-139">发起的呼叫</span><span class="sxs-lookup"><span data-stu-id="ffdfe-139">Offered calls</span></span>

  - <span data-ttu-id="ffdfe-140">应答的呼叫</span><span class="sxs-lookup"><span data-stu-id="ffdfe-140">Answered calls</span></span>

  - <span data-ttu-id="ffdfe-141">转接的呼叫</span><span class="sxs-lookup"><span data-stu-id="ffdfe-141">Transferred calls</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-usage-report"></a><span data-ttu-id="ffdfe-142">充分利用响应组使用情况报告</span><span class="sxs-lookup"><span data-stu-id="ffdfe-142">Making the Best Use of the Response Group Usage Report</span></span>

<span data-ttu-id="ffdfe-143">响应组使用情况报告的值得关注的用途之一可能不是显而易见的：能够检索单个响应组工作流的使用情况信息。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-143">One of the more interesting uses of the Response Group Usage Report might not be readily apparent: the ability to retrieve usage information for a single Response Group workflow.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="ffdfe-144">响应组工作流基本上是一组指示用户拨打特定电话号码时的 Lync Server 应执行的操作的说明。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-144">A Response Group workflow is basically a set of instructions that determines what Lync Server does when a user dials a particular phone number.</span></span> <span data-ttu-id="ffdfe-145">为此，每个工作流都与一个电话号码唯一关联。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-145">To that end, each workflow is uniquely associated with a phone number.</span></span> <span data-ttu-id="ffdfe-146">当某人调用该号码时，工作流会确定如何处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-146">When someone calls that number, the workflow determines how the call will be handled.</span></span> <span data-ttu-id="ffdfe-147">例如，工作流可能会导致呼叫路由到一系列互动语音响应 (IVR) 提示呼叫者输入其他信息的问题 ( "按1以获得硬件支持。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-147">For example, the workflow might cause the call to be routed to a series of interactive voice response (IVR) questions that prompt the caller to enter additional information ("Press 1 for hardware support.</span></span> <span data-ttu-id="ffdfe-148">按 2 以获取软件支持”）。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-148">Press 2 for software support.").</span></span> <span data-ttu-id="ffdfe-149">或者，工作流可能会导致呼叫放置在队列中，呼叫者将保留在队列中，直到有代理可用于应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-149">Alternatively, the workflow might cause the call to be placed in a queue , with the caller put on hold until an agent is available to answer the call.</span></span> <span data-ttu-id="ffdfe-150">工作流也可指示是否有代理能够应答呼叫：工作流用于配置工作时间（代理在一周中的哪几天、一天中的哪些时段能够应答呼叫）和假日（代理无法应答呼叫的日期）。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-150">The availability of agents to answer calls is also dictated by the workflow: workflows are used to configure both business hours (the days of the week and the times of day when agents are available to answer calls) and holidays (days when no agents are available to answer calls).</span></span> <span data-ttu-id="ffdfe-151">无论何时拨打属于响应组应用程序的电话号码，实际上都会调用响应组工作流。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-151">Any time you dial a phone number that belongs to the Response Group application you are essentially calling a Response Group workflow.</span></span>



</div>

<span data-ttu-id="ffdfe-p112">虽然工作流 URI 不显示在响应组使用情况报告中，但仍可以查看单个工作流的使用情况统计信息，这通常极其有用。例如，假定您最近开展了一项新的广告活动并很想知道人们是否通过电话询问该产品。如果您已将响应组工作流与广告活动中提供的电话号码相关联，则可以轻松地查看有多少人（如果有）呼叫了该号码。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-p112">Although workflow URIs do not appear in the Response Group Usage Report, it's still possible to view the usage statistics for a single workflow, something that is often extremely useful. For example, suppose you recently unveiled a new ad campaign and are curious to know whether people are calling in to ask about that product. If you have associated a Response Group workflow with the phone number given in the ad campaign, you can easily check to see how many people (if any) are calling that number.</span></span>

<span data-ttu-id="ffdfe-155">您可能还使用类似的方法来测量内部技术支持或客户服务部门处理的呼叫数。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-155">You might also use a similar approach to gauge the number of calls being handled by your internal help desk or your customer service department.</span></span>

<span data-ttu-id="ffdfe-156">若要查看特定工作流的使用情况统计信息，请在“工作流 URI”框中输入工作流 URI。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-156">To review usage statistics for a particular workflow, enter the workflow URI in the Workflow URI box.</span></span> <span data-ttu-id="ffdfe-157">当然，正如上文所述，工作流 URI（与工作流关联的 SIP 地址）不显示在报告上。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-157">Of course, as noted, workflow URIs (the SIP address associated with a workflow) do not appear on the report.</span></span> <span data-ttu-id="ffdfe-158">这意味着您需要查找某种其他方法来确定工作流的 URI。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-158">That means you need to find some other way to determine the URI of a workflow.</span></span> <span data-ttu-id="ffdfe-159">执行此操作的一种方法是使用 Windows PowerShell 和 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-159">One way to do this is to use Windows PowerShell and the Lync Server Management Shell.</span></span> <span data-ttu-id="ffdfe-160">例如，以下命令返回您的所有响应组工作流的 URI：</span><span class="sxs-lookup"><span data-stu-id="ffdfe-160">For example, this command returns the URIs for all your Response Group workflows:</span></span>

    Get-CsRgsWorkflow | Select-Object Name, PrimaryUri

<span data-ttu-id="ffdfe-161">它将返回类似以下内容的数据：</span><span class="sxs-lookup"><span data-stu-id="ffdfe-161">That will return data similar to this:</span></span>

    Name                            PrimaryUri
    ----                            ----------
    Customer Support                sip:support@litwareinc.com
    Help Desk                       sip:helpdesk@litwareinc.com
    New Ad Campaign                 sip:newads@litwareinc.com

<span data-ttu-id="ffdfe-162">以下命令返回名为“New Ad Campaign”的单个工作流的信息：</span><span class="sxs-lookup"><span data-stu-id="ffdfe-162">This command returns information for a single workflow, the one with the name New Ad Campaign:</span></span>

    Get-CsRgsWorkflow -Name "New Ad Campaign" | Select-Object Name, PrimaryUri

</div>

<div>

## <a name="filters"></a><span data-ttu-id="ffdfe-163">筛选器</span><span class="sxs-lookup"><span data-stu-id="ffdfe-163">Filters</span></span>

<span data-ttu-id="ffdfe-p114">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，通过响应组使用情况报告，您可以查看所有响应组工作流的数据，也可以查看单个工作流的数据。您还可以选择数据的分组方式。在此示例中，将按小时、日、周或月对使用情况进行分组。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-p114">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Response Group Usage Report enables you to view data for all your Response Group workflows or to view data for an individual workflow. You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="ffdfe-168">下表列出了可用于响应组使用情况报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-168">The following table lists the filters that you can use with the Response Group Usage Report.</span></span>

### <a name="response-group-usage-report-filters"></a><span data-ttu-id="ffdfe-169">响应组使用情况报告筛选器</span><span class="sxs-lookup"><span data-stu-id="ffdfe-169">Response Group Usage Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ffdfe-170">名称</span><span class="sxs-lookup"><span data-stu-id="ffdfe-170">Name</span></span></th>
<th><span data-ttu-id="ffdfe-171">说明</span><span class="sxs-lookup"><span data-stu-id="ffdfe-171">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffdfe-172"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="ffdfe-172"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="ffdfe-p115">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ffdfe-p115">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="ffdfe-175">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="ffdfe-175">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="ffdfe-p116">如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="ffdfe-p116">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ffdfe-178">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="ffdfe-178">7/7/2012</span></span></p>
<p><span data-ttu-id="ffdfe-179">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="ffdfe-179">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ffdfe-180">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="ffdfe-180">7/3/2012</span></span></p>
<p><span data-ttu-id="ffdfe-181">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-181">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffdfe-182"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="ffdfe-182"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="ffdfe-p117">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ffdfe-p117">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="ffdfe-185">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="ffdfe-185">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="ffdfe-p118">如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="ffdfe-p118">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ffdfe-188">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="ffdfe-188">7/7/2012</span></span></p>
<p><span data-ttu-id="ffdfe-189">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="ffdfe-189">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ffdfe-190">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="ffdfe-190">7/3/2012</span></span></p>
<p><span data-ttu-id="ffdfe-191">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-191">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffdfe-192"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="ffdfe-192"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="ffdfe-p119">时间间隔。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="ffdfe-p119">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ffdfe-195">每小时（最多可显示 25 个小时）</span><span class="sxs-lookup"><span data-stu-id="ffdfe-195">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="ffdfe-196">每天（最多可显示 31 天）</span><span class="sxs-lookup"><span data-stu-id="ffdfe-196">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="ffdfe-197">每周（最多可显示 12 周）</span><span class="sxs-lookup"><span data-stu-id="ffdfe-197">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="ffdfe-198">每月（最多可显示 12 个月）</span><span class="sxs-lookup"><span data-stu-id="ffdfe-198">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="ffdfe-p120">如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。例如，如果选择的开始日期为 8/7/2012、结束日期为 9/28/2012、间隔为“每天”，则显示从 8/7/2012 12:00 AM 到 9/7/2012 12:00 AM 这些天的数据（即总共 31 天的数据）。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-p120">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffdfe-201"><strong>工作流 URI</strong></span><span class="sxs-lookup"><span data-stu-id="ffdfe-201"><strong>Workflow URI</strong></span></span></p></td>
<td><p><span data-ttu-id="ffdfe-p121">允许您限制返回的数据，以便仅显示指定响应组工作流的数据。若要使用该筛选器，请输入工作流 SIP 地址。例如：</span><span class="sxs-lookup"><span data-stu-id="ffdfe-p121">Enables you to limit the returned data to the specified Response Group workflow. To use this filter, enter the Workflow SIP address. For example:</span></span></p>
<p><span data-ttu-id="ffdfe-205">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ffdfe-205">sip:helpdesk@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="ffdfe-206">指标</span><span class="sxs-lookup"><span data-stu-id="ffdfe-206">Metrics</span></span>

<span data-ttu-id="ffdfe-207">下表列出了响应组使用情况报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-207">The following table lists the information provided in the Response Group Usage Report.</span></span>

### <a name="response-group-usage-report-metrics"></a><span data-ttu-id="ffdfe-208">响应组使用情况报告指标</span><span class="sxs-lookup"><span data-stu-id="ffdfe-208">Response Group Usage Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ffdfe-209">名称</span><span class="sxs-lookup"><span data-stu-id="ffdfe-209">Name</span></span></th>
<th><span data-ttu-id="ffdfe-210">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="ffdfe-210">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ffdfe-211">说明</span><span class="sxs-lookup"><span data-stu-id="ffdfe-211">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffdfe-212"><strong>每小时</strong></span><span class="sxs-lookup"><span data-stu-id="ffdfe-212"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="ffdfe-213"><strong>每天</strong></span><span class="sxs-lookup"><span data-stu-id="ffdfe-213"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="ffdfe-214"><strong>每周</strong></span><span class="sxs-lookup"><span data-stu-id="ffdfe-214"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="ffdfe-215"><strong>每月</strong></span><span class="sxs-lookup"><span data-stu-id="ffdfe-215"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="ffdfe-216">否</span><span class="sxs-lookup"><span data-stu-id="ffdfe-216">No</span></span></p></td>
<td><p><span data-ttu-id="ffdfe-p122">指示所选的时间间隔。如果适用，可单击某一给定的时间间隔以查看该间隔的详细信息。例如，如果使用“每天”间隔并单击 7/7/2012，可查看当日用户注册活动的每小时细分信息。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-p122">Indicates the selected time interval. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffdfe-220"><strong>收到的呼叫</strong></span><span class="sxs-lookup"><span data-stu-id="ffdfe-220"><strong>Received calls</strong></span></span></p></td>
<td><p><span data-ttu-id="ffdfe-221">否</span><span class="sxs-lookup"><span data-stu-id="ffdfe-221">No</span></span></p></td>
<td><p><span data-ttu-id="ffdfe-p123">响应组应用程序的所有实例收到的呼叫总数。单击此项时，报告向您显示所选时间段的响应组呼叫列表报告。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-p123">Total number of calls received by all instances of the Response Group application. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffdfe-224"><strong>成功呼叫</strong></span><span class="sxs-lookup"><span data-stu-id="ffdfe-224"><strong>Successful calls</strong></span></span></p></td>
<td><p><span data-ttu-id="ffdfe-225">否</span><span class="sxs-lookup"><span data-stu-id="ffdfe-225">No</span></span></p></td>
<td><p><span data-ttu-id="ffdfe-p124">响应组应用程序接听的呼叫总数。单击此项时，报告向您显示所选时间段的响应组呼叫列表报告。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-p124">Total number of calls that were picked up the Response Group application. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffdfe-228"><strong>提供的呼叫</strong></span><span class="sxs-lookup"><span data-stu-id="ffdfe-228"><strong>Offered calls</strong></span></span></p></td>
<td><p><span data-ttu-id="ffdfe-229">否</span><span class="sxs-lookup"><span data-stu-id="ffdfe-229">No</span></span></p></td>
<td><p><span data-ttu-id="ffdfe-p125">转接到响应组代理的呼叫总数。单击此项时，报告向您显示所选时间段的响应组呼叫列表报告。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-p125">Total number of calls that were transferred to a Response Group agent. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffdfe-232"><strong>应答的呼叫</strong></span><span class="sxs-lookup"><span data-stu-id="ffdfe-232"><strong>Answered calls</strong></span></span></p></td>
<td><p><span data-ttu-id="ffdfe-233">否</span><span class="sxs-lookup"><span data-stu-id="ffdfe-233">No</span></span></p></td>
<td><p><span data-ttu-id="ffdfe-p126">响应组代理实际应答的呼叫总数。单击此项时，报告向您显示所选时间段的响应组呼叫列表报告。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-p126">Total number of calls that were actually answered by a Response Group agent. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffdfe-236"><strong>放弃的呼叫的百分比</strong></span><span class="sxs-lookup"><span data-stu-id="ffdfe-236"><strong>Percentage of abandoned calls</strong></span></span></p></td>
<td><p><span data-ttu-id="ffdfe-237">否</span><span class="sxs-lookup"><span data-stu-id="ffdfe-237">No</span></span></p></td>
<td><p><span data-ttu-id="ffdfe-p127">响应组应用程序已收到但代理未应答的呼叫总数。它的计算方法是“收到的呼叫”减去“应答的呼叫”，然后用所得的值除以收到的呼叫数。例如，如果收到了 10 个呼叫，但应答了 7 个，则计算方式是 10 减去 7，得出未应答的呼叫是 3 个。然后用该值除以 10，得出放弃的呼叫的百分比为 30%。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-p127">Total number of calls that were received by the Response Group application but were never answered by an agent. This is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of received calls. For example, if you have 10 received calls and seven were answered, you would subtract seven from 10, leaving three unanswered calls. That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffdfe-242"><strong>代理的平均呼叫分钟数</strong></span><span class="sxs-lookup"><span data-stu-id="ffdfe-242"><strong>Average call minutes by agent</strong></span></span></p></td>
<td><p><span data-ttu-id="ffdfe-243">否</span><span class="sxs-lookup"><span data-stu-id="ffdfe-243">No</span></span></p></td>
<td><p><span data-ttu-id="ffdfe-244">响应组代理应答一个呼叫平均所用的时间。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-244">Average amount of time a Response Group agent spent on a call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffdfe-245"><strong>转接的呼叫</strong></span><span class="sxs-lookup"><span data-stu-id="ffdfe-245"><strong>Transferred calls</strong></span></span></p></td>
<td><p><span data-ttu-id="ffdfe-246">否</span><span class="sxs-lookup"><span data-stu-id="ffdfe-246">No</span></span></p></td>
<td><p><span data-ttu-id="ffdfe-p128">因队列超时或队列溢出而转接的响应组呼叫总数。单击此项时，报告向您显示所选时间段的响应组呼叫列表报告。</span><span class="sxs-lookup"><span data-stu-id="ffdfe-p128">Total number of Response Group calls that were transferred because of a queue timeout or queue overflow. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

