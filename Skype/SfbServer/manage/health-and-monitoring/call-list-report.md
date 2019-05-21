---
title: Skype for Business 服务器中的响应组呼叫列表报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
description: '摘要: 了解 Skype for Business 服务器中的 "响应组" 应用程序。'
ms.openlocfilehash: 216f07a81beaa962bf091e815c797611f9e236ac
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289334"
---
# <a name="response-group-call-list-report-in-skype-for-business-server"></a><span data-ttu-id="2c592-103">Skype for Business 服务器中的响应组呼叫列表报告</span><span class="sxs-lookup"><span data-stu-id="2c592-103">Response Group Call List Report in Skype for Business Server</span></span>

<span data-ttu-id="2c592-104">**摘要:** 了解 Skype for Business 服务器中的 "响应组" 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2c592-104">**Summary:** Learn about the Response Group application in Skype for Business Server.</span></span>

<span data-ttu-id="2c592-105">"响应组" 应用程序为 Skype for business 服务器提供了一种方法, 可根据所拨打的号码和呼叫者对一系列问题的响应 (可选) 应答和路由电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="2c592-105">The Response Group application provides a way for Skype for Business Server to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="2c592-106">通常，不会将响应组呼叫路由到个人，而是路由到称为代理组的一组人员。</span><span class="sxs-lookup"><span data-stu-id="2c592-106">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="2c592-107">例如, 如果某人呼叫帮助台的电话号码, Skype for Business 服务器可以自动将呼叫路由到第一个可用的技术支持代理。</span><span class="sxs-lookup"><span data-stu-id="2c592-107">For example, if someone calls the phone number for your help desk, Skype for Business Server can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="2c592-108">或者, 如果遇到硬件问题, Skype for business 服务器可能会询问一系列问题 ("按1。</span><span class="sxs-lookup"><span data-stu-id="2c592-108">Alternatively, Skype for Business Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="2c592-109">如果您有软件问题，请按 2。</span><span class="sxs-lookup"><span data-stu-id="2c592-109">Press 2 if you are having software problems.</span></span> <span data-ttu-id="2c592-110">如果出现网络问题, 请按3。)然后根据这些问题的答案, 将呼叫路由到最合适的技术支持代理。</span><span class="sxs-lookup"><span data-stu-id="2c592-110">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="2c592-p102">响应组呼叫列表报告代表针对指定的时间段和指定的呼叫类型所进行的呼叫集合。响应组使用报告（必需先打开该报告，才能打开响应组呼叫列表报告）可识别以下呼叫类型：</span><span class="sxs-lookup"><span data-stu-id="2c592-p102">The Response Group Call List Report represents a collection of calls made for a specified period of time and for a specified type of call. The Response Group Usage Report (which must be opened first before you can open the Response Group Call List Report) recognizes the following call types:</span></span>

- <span data-ttu-id="2c592-p103">**收到的呼叫**。响应组应用程序的所有实例收到的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="2c592-p103">**Received calls**. Total number of calls received by all instances of the Response Group application.</span></span>

- <span data-ttu-id="2c592-p104">**成功的呼叫**。响应组应用程序所接听的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="2c592-p104">**Successful calls**. Total number of calls that were picked up by the Response Group application.</span></span>

- <span data-ttu-id="2c592-p105">**提供的呼叫**。已转接给响应组代理的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="2c592-p105">**Offered calls**. Total number of calls that were transferred to a Response Group agent.</span></span>

- <span data-ttu-id="2c592-p106">**应答的呼叫**。响应组代理实际应答的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="2c592-p106">**Answered calls**. Total number of calls that were actually answered by a Response Group agent.</span></span>

- <span data-ttu-id="2c592-121">**已放弃通话的百分比。**</span><span class="sxs-lookup"><span data-stu-id="2c592-121">**Percentage of abandoned calls.**</span></span> <span data-ttu-id="2c592-122">响应组应用程序已收到但代理未应答的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="2c592-122">Percentage of calls that were received by the Response Group application but were never answered by an agent.</span></span> <span data-ttu-id="2c592-123">此值的计算方法是用“收到的呼叫数”减去“应答的呼叫数”，然后用所得的值除以收到的呼叫数。</span><span class="sxs-lookup"><span data-stu-id="2c592-123">This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls.</span></span> <span data-ttu-id="2c592-124">例如，如果收到 10 个呼叫，但应答了 7 个，则计算方法是 10 减去 7，得出未应答的呼叫是 3 个。</span><span class="sxs-lookup"><span data-stu-id="2c592-124">For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls.</span></span> <span data-ttu-id="2c592-125">然后用该值除以 10，得出放弃的呼叫的百分比为 30%。</span><span class="sxs-lookup"><span data-stu-id="2c592-125">That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

- <span data-ttu-id="2c592-p108">**转接的呼叫**。因队列超时或队列溢出而转接的响应组呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="2c592-p108">**Transferred calls**. Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

## <a name="accessing-the-response-group-call-list-report"></a><span data-ttu-id="2c592-128">访问响应组呼叫列表报告</span><span class="sxs-lookup"><span data-stu-id="2c592-128">Accessing the Response Group Call List Report</span></span>

<span data-ttu-id="2c592-129">仅可通过单击[Skype For Business 服务器的 "响应组使用情况" 报告中](response-group-usage-report.md)的以下指标之一来访问响应组呼叫列表报告:</span><span class="sxs-lookup"><span data-stu-id="2c592-129">The Response Group Call List Report can only be accessed by clicking one of the following metrics found on the [Response Group Usage Report in Skype for Business Server](response-group-usage-report.md):</span></span>

- <span data-ttu-id="2c592-130">收到的呼叫</span><span class="sxs-lookup"><span data-stu-id="2c592-130">Received calls</span></span>

- <span data-ttu-id="2c592-131">成功的呼叫</span><span class="sxs-lookup"><span data-stu-id="2c592-131">Successful calls</span></span>

- <span data-ttu-id="2c592-132">提供的呼叫</span><span class="sxs-lookup"><span data-stu-id="2c592-132">Offered calls</span></span>

- <span data-ttu-id="2c592-133">应答的呼叫</span><span class="sxs-lookup"><span data-stu-id="2c592-133">Answered calls</span></span>

- <span data-ttu-id="2c592-134">转接的呼叫</span><span class="sxs-lookup"><span data-stu-id="2c592-134">Transferred calls</span></span>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a><span data-ttu-id="2c592-135">充分利用响应组呼叫列表报告</span><span class="sxs-lookup"><span data-stu-id="2c592-135">Making the Best Use of the Response Group Call List Report</span></span>

<span data-ttu-id="2c592-p109">响应组呼叫列表报告允许您将所显示的数据限制为涉及特定响应组工作流的呼叫。为执行此操作，需要在“工作流 URI”框中输入工作流 URI（工作流的 SIP 地址）。但是，您必须实际上能够看到“工作流 URI”框，才能执行此操作。要显示响应组呼叫列表报告的筛选选项，请单击报告窗口左上部分的“显示/隐藏参数”按钮。</span><span class="sxs-lookup"><span data-stu-id="2c592-p109">The Response Group Call List Report allows you to limit the displayed data to calls involving a particular Response Group workflow. To do that, you need to enter the workflow URI (the workflow's SIP address) in the Workflow URI box. Before you can do that, however, you must actually be able to see the Workflow URI box. To display the filtering options for the Response Group Call List Report, click the Show/Hide Parameters button in the upper left-hand portion of the report window.</span></span>

<span data-ttu-id="2c592-140">请注意，如果将鼠标停留在其中任一指标上，响应组呼叫列表不会显示有关响应代码或诊断 ID 的信息。</span><span class="sxs-lookup"><span data-stu-id="2c592-140">Note that the Response Group Call List does not display information about either the Response code or the Diagnostic ID if you hold the mouse over either of those metrics.</span></span> <span data-ttu-id="2c592-141">如果你需要详细信息, 你可能会注意到响应代码和/或诊断 ID, 然后在[Skype for Business Server 的 "热门故障" 报告](top-failures-report.md)中搜索这些值。</span><span class="sxs-lookup"><span data-stu-id="2c592-141">If you need more information, you might note the Response code and/or Diagnostic ID, and then search for those values in the [Top Failures Report in Skype for Business Server](top-failures-report.md).</span></span>

<span data-ttu-id="2c592-142">对于类似如下的问题：“哪个个别工作流收到的呼叫数最多？”，您可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2c592-142">a question like this one: "Which individual workflow received the most calls?", you can do the following:</span></span>

1. <span data-ttu-id="2c592-p111">在“响应组使用报告”上，设置所需的时间段，然后单击“收到的呼叫”指标。这样即会打开“响应组呼叫列表报告”。</span><span class="sxs-lookup"><span data-stu-id="2c592-p111">On the Response Group Usage Report, set the desired time period and then click the Received Calls metric. That will open the Response Group Call List Report.</span></span>

2. <span data-ttu-id="2c592-p112">导出“响应组呼叫列表报告”上所显示的数据。例如，可以使用 Microsoft Excel 格式导出数据，然后使用 Excel 将该数据转换为逗号分隔值文件。</span><span class="sxs-lookup"><span data-stu-id="2c592-p112">Export the data shown on the Response Group Call List Report. For example, you might export the data in Microsoft Excel format, and then use Excel to convert that data to a comma-separated values file.</span></span>

3. <span data-ttu-id="2c592-147">使用 Windows PowerShell 运行您的分析。</span><span class="sxs-lookup"><span data-stu-id="2c592-147">Run your analyses using Windows PowerShell.</span></span>

<span data-ttu-id="2c592-148">例如，如果已将数据保存到名为 C:\Data\Response_Group_Call_List_Report.csv 的文件，则可以使用以下命令，针对报告中所列出的每个工作流返回收到的呼叫总数：</span><span class="sxs-lookup"><span data-stu-id="2c592-148">For example, if you have saved the data to a file named C:\Data\Response_Group_Call_List_Report.csv, you can then use the following command to return the total number of received calls for each workflow listed in the report:</span></span>

```
$calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
$calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending
```

<span data-ttu-id="2c592-149">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="2c592-149">That will information similar to this:</span></span>

<pre>
Count    Name
-----    ----
  160    Redmond Help Desk
   47    Dublin Help Desk
   31    North America Customer Support
   16    EMEA Customer Support
   14    Employment Opportunities
</pre>

## <a name="filters"></a><span data-ttu-id="2c592-150">筛选器</span><span class="sxs-lookup"><span data-stu-id="2c592-150">Filters</span></span>

<span data-ttu-id="2c592-p113">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于响应组呼叫列表报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="2c592-p113">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Response Group Call List Report.</span></span>

<span data-ttu-id="2c592-153">**响应组呼叫列表报告筛选器**</span><span class="sxs-lookup"><span data-stu-id="2c592-153">**Response Group Call List Report Filters**</span></span>


| <span data-ttu-id="2c592-154">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="2c592-154">**Name**</span></span>               | <span data-ttu-id="2c592-155">**说明**</span><span class="sxs-lookup"><span data-stu-id="2c592-155">**Description**</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="2c592-156">**从**</span><span class="sxs-lookup"><span data-stu-id="2c592-156">**From**</span></span> <br/>         | <span data-ttu-id="2c592-p114">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2c592-p114">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span>  <br/> <span data-ttu-id="2c592-159">2015/7/7 13:00</span><span class="sxs-lookup"><span data-stu-id="2c592-159">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="2c592-p115">如果您未输入开始时间，该报告会自动将将某个特定日期的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="2c592-p115">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="2c592-162">2015/7/7</span><span class="sxs-lookup"><span data-stu-id="2c592-162">7/7/2015</span></span>  <br/> <span data-ttu-id="2c592-163">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="2c592-163">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="2c592-164">2015/7/3</span><span class="sxs-lookup"><span data-stu-id="2c592-164">7/3/2015</span></span>  <br/> <span data-ttu-id="2c592-165">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="2c592-165">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
| <span data-ttu-id="2c592-166">**到**</span><span class="sxs-lookup"><span data-stu-id="2c592-166">**To**</span></span> <br/>           | <span data-ttu-id="2c592-p116">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2c592-p116">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span>  <br/> <span data-ttu-id="2c592-169">2015/7/7 13:00</span><span class="sxs-lookup"><span data-stu-id="2c592-169">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="2c592-p117">如果您未输入结束时间，该报告会自动将某个特定日期的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="2c592-p117">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="2c592-172">2015/7/7</span><span class="sxs-lookup"><span data-stu-id="2c592-172">7/7/2015</span></span>  <br/> <span data-ttu-id="2c592-173">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="2c592-173">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="2c592-174">2015/7/3</span><span class="sxs-lookup"><span data-stu-id="2c592-174">7/3/2015</span></span>  <br/> <span data-ttu-id="2c592-175">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="2c592-175">Weeks always run from Sunday through Saturday.</span></span>  <br/>        |
| <span data-ttu-id="2c592-176">**工作流 URI**</span><span class="sxs-lookup"><span data-stu-id="2c592-176">**Workflow URI**</span></span> <br/> | <span data-ttu-id="2c592-p118">允许您限制返回的数据，以便仅显示指定响应组工作流的数据。若要使用该筛选器，请输入工作流 SIP 地址。例如：</span><span class="sxs-lookup"><span data-stu-id="2c592-p118">Enables you to limit the returned data to the specified Response Group workflow. To use this filter, enter the Workflow SIP address. For example:</span></span>  <br/> <span data-ttu-id="2c592-180">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2c592-180">sip:helpdesk@litwareinc.com</span></span>  <br/>                                                                                                                                                                                                                                                                                                                                                                            |
| <span data-ttu-id="2c592-181">**呼叫**</span><span class="sxs-lookup"><span data-stu-id="2c592-181">**Calls**</span></span> <br/>        | <span data-ttu-id="2c592-182">可以选择以下呼叫类型之一：</span><span class="sxs-lookup"><span data-stu-id="2c592-182">You can select one of the following call types:</span></span> <br/>  <span data-ttu-id="2c592-183">收到的呼叫</span><span class="sxs-lookup"><span data-stu-id="2c592-183">Received Calls</span></span> <br/>  <span data-ttu-id="2c592-184">成功的呼叫</span><span class="sxs-lookup"><span data-stu-id="2c592-184">Successful Calls</span></span> <br/>  <span data-ttu-id="2c592-185">提供的呼叫</span><span class="sxs-lookup"><span data-stu-id="2c592-185">Offered Calls</span></span> <br/>  <span data-ttu-id="2c592-186">应答的呼叫</span><span class="sxs-lookup"><span data-stu-id="2c592-186">Answered Calls</span></span> <br/>  <span data-ttu-id="2c592-187">转接的呼叫</span><span class="sxs-lookup"><span data-stu-id="2c592-187">Transferred Calls</span></span> <br/>                                                                                                                                                                                                                                                                                                                                                                                                |

## <a name="metrics"></a><span data-ttu-id="2c592-188">指标</span><span class="sxs-lookup"><span data-stu-id="2c592-188">Metrics</span></span>

<span data-ttu-id="2c592-189">下表列出了响应组应用程序收到的每个呼叫的响应组呼叫列表报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="2c592-189">The following table lists the information provided in the Response Group Call List Report for each call received by the Response Group application.</span></span>

<span data-ttu-id="2c592-190">**响应组呼叫列表报告指标**</span><span class="sxs-lookup"><span data-stu-id="2c592-190">**Response Group Call List Report Metrics**</span></span>

|<span data-ttu-id="2c592-191">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="2c592-191">**Name**</span></span>|<span data-ttu-id="2c592-192">**是否可按此项排序？**</span><span class="sxs-lookup"><span data-stu-id="2c592-192">**Can you sort on this item?**</span></span>|<span data-ttu-id="2c592-193">**说明**</span><span class="sxs-lookup"><span data-stu-id="2c592-193">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2c592-194">**呼叫者**</span><span class="sxs-lookup"><span data-stu-id="2c592-194">**Caller**</span></span> <br/> |<span data-ttu-id="2c592-195">否</span><span class="sxs-lookup"><span data-stu-id="2c592-195">No</span></span>  <br/> |<span data-ttu-id="2c592-196">呼叫者的 SIP 地址</span><span class="sxs-lookup"><span data-stu-id="2c592-196">SIP address of the caller.</span></span>  <br/> |
|<span data-ttu-id="2c592-197">**工作流**</span><span class="sxs-lookup"><span data-stu-id="2c592-197">**Workflow**</span></span> <br/> |<span data-ttu-id="2c592-198">否</span><span class="sxs-lookup"><span data-stu-id="2c592-198">No</span></span>  <br/> |<span data-ttu-id="2c592-199">响应组工作流的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="2c592-199">SIP address of the Response Group workflow.</span></span>  <br/> |
|<span data-ttu-id="2c592-200">**开始时间**</span><span class="sxs-lookup"><span data-stu-id="2c592-200">**Start time**</span></span> <br/> |<span data-ttu-id="2c592-201">否</span><span class="sxs-lookup"><span data-stu-id="2c592-201">No</span></span>  <br/> |<span data-ttu-id="2c592-202">呼叫开始的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="2c592-202">Date and time that the call started.</span></span>  <br/> |
|<span data-ttu-id="2c592-203">**结束时间**</span><span class="sxs-lookup"><span data-stu-id="2c592-203">**End time**</span></span> <br/> |<span data-ttu-id="2c592-204">否</span><span class="sxs-lookup"><span data-stu-id="2c592-204">No</span></span>  <br/> |<span data-ttu-id="2c592-205">呼叫结束的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="2c592-205">Date and time that the call ended.</span></span>  <br/> |
|<span data-ttu-id="2c592-206">**响应代码**</span><span class="sxs-lookup"><span data-stu-id="2c592-206">**Response code**</span></span> <br/> |<span data-ttu-id="2c592-207">否</span><span class="sxs-lookup"><span data-stu-id="2c592-207">No</span></span>  <br/> |<span data-ttu-id="2c592-208">会话失败时发送的 SIP 响应代码。</span><span class="sxs-lookup"><span data-stu-id="2c592-208">SIP response code sent when the session failed.</span></span>  <br/> |
|<span data-ttu-id="2c592-209">**诊断 ID**</span><span class="sxs-lookup"><span data-stu-id="2c592-209">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="2c592-210">否</span><span class="sxs-lookup"><span data-stu-id="2c592-210">No</span></span>  <br/> |<span data-ttu-id="2c592-211">附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。</span><span class="sxs-lookup"><span data-stu-id="2c592-211">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |


