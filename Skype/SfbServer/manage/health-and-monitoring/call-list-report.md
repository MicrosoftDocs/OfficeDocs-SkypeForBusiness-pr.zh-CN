---
title: Skype for Business Server 中的响应组呼叫列表报告
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
description: 摘要：了解 Skype for Business Server 中的响应组应用程序。
ms.openlocfilehash: 416a0e7b7a7aebaeae84a00c04a7ab5c4e1a5bf8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826492"
---
# <a name="response-group-call-list-report-in-skype-for-business-server"></a><span data-ttu-id="8f68e-103">Skype for Business Server 中的响应组呼叫列表报告</span><span class="sxs-lookup"><span data-stu-id="8f68e-103">Response Group Call List Report in Skype for Business Server</span></span>

<span data-ttu-id="8f68e-104">**摘要：** 了解 Skype for Business Server 中的响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="8f68e-104">**Summary:** Learn about the Response Group application in Skype for Business Server.</span></span>

<span data-ttu-id="8f68e-105">响应组应用程序为 Skype for Business Server 提供了一种根据拨打的号码以及呼叫者对一系列问题的响应（可选）应答和路由电话呼叫的方法。</span><span class="sxs-lookup"><span data-stu-id="8f68e-105">The Response Group application provides a way for Skype for Business Server to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="8f68e-106">通常，响应组呼叫不路由到单个人员，而是路由到称为代理组的一组人员。</span><span class="sxs-lookup"><span data-stu-id="8f68e-106">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="8f68e-107">例如，如果有人呼叫技术支持的电话号码，Skype for Business Server 可以自动将呼叫路由到第一个可用的技术支持代理。</span><span class="sxs-lookup"><span data-stu-id="8f68e-107">For example, if someone calls the phone number for your help desk, Skype for Business Server can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="8f68e-108">或者，Skype for Business Server 可能会提出一系列问题 ("如果遇到硬件问题，请按 1。</span><span class="sxs-lookup"><span data-stu-id="8f68e-108">Alternatively, Skype for Business Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="8f68e-109">如果您有软件问题，请按 2。</span><span class="sxs-lookup"><span data-stu-id="8f68e-109">Press 2 if you are having software problems.</span></span> <span data-ttu-id="8f68e-110">如果您有网络问题，请按 3。") ，然后根据这些问题的回答将呼叫路由至最合适的技术支持代理。</span><span class="sxs-lookup"><span data-stu-id="8f68e-110">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="8f68e-p102">响应组呼叫列表报告代表针对指定的时间段和指定的呼叫类型所进行的呼叫集合。响应组使用报告（必需先打开该报告，才能打开响应组呼叫列表报告）可识别以下呼叫类型：</span><span class="sxs-lookup"><span data-stu-id="8f68e-p102">The Response Group Call List Report represents a collection of calls made for a specified period of time and for a specified type of call. The Response Group Usage Report (which must be opened first before you can open the Response Group Call List Report) recognizes the following call types:</span></span>

- <span data-ttu-id="8f68e-p103">**收到的呼叫**。响应组应用程序的所有实例收到的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="8f68e-p103">**Received calls**. Total number of calls received by all instances of the Response Group application.</span></span>

- <span data-ttu-id="8f68e-115">**成功呼叫**。</span><span class="sxs-lookup"><span data-stu-id="8f68e-115">**Successful calls**.</span></span> <span data-ttu-id="8f68e-116">响应组应用程序接听的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="8f68e-116">Total number of calls that were picked up by the Response Group application.</span></span>

- <span data-ttu-id="8f68e-p105">**发起的呼叫**。转接到响应组代理的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="8f68e-p105">**Offered calls**. Total number of calls that were transferred to a Response Group agent.</span></span>

- <span data-ttu-id="8f68e-p106">**应答的呼叫**。响应组代理实际应答的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="8f68e-p106">**Answered calls**. Total number of calls that were actually answered by a Response Group agent.</span></span>

- <span data-ttu-id="8f68e-121">**放弃的呼叫的百分比。**</span><span class="sxs-lookup"><span data-stu-id="8f68e-121">**Percentage of abandoned calls.**</span></span> <span data-ttu-id="8f68e-122">响应组应用程序已收到但代理未应答的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="8f68e-122">Percentage of calls that were received by the Response Group application but were never answered by an agent.</span></span> <span data-ttu-id="8f68e-123">此值的计算方法是用“收到的呼叫数”减去“应答的呼叫数”，然后用所得的值除以收到的呼叫数。</span><span class="sxs-lookup"><span data-stu-id="8f68e-123">This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls.</span></span> <span data-ttu-id="8f68e-124">例如，如果收到 10 个呼叫，但应答了 7 个，则计算方法是 10 减去 7，得出未应答的呼叫是 3 个。</span><span class="sxs-lookup"><span data-stu-id="8f68e-124">For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls.</span></span> <span data-ttu-id="8f68e-125">然后用该值除以 10，得出放弃的呼叫的百分比为 30%。</span><span class="sxs-lookup"><span data-stu-id="8f68e-125">That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

- <span data-ttu-id="8f68e-p108">**转接的呼叫**。因队列超时或队列溢出而转接的响应组呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="8f68e-p108">**Transferred calls**. Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

## <a name="accessing-the-response-group-call-list-report"></a><span data-ttu-id="8f68e-128">访问响应组呼叫列表报告</span><span class="sxs-lookup"><span data-stu-id="8f68e-128">Accessing the Response Group Call List Report</span></span>

<span data-ttu-id="8f68e-129">只有单击 Skype for Business Server 中响应组使用情况报告中的下列指标之一，才能访问响应组 [呼叫列表报告](response-group-usage-report.md)：</span><span class="sxs-lookup"><span data-stu-id="8f68e-129">The Response Group Call List Report can only be accessed by clicking one of the following metrics found on the [Response Group Usage Report in Skype for Business Server](response-group-usage-report.md):</span></span>

- <span data-ttu-id="8f68e-130">收到的呼叫</span><span class="sxs-lookup"><span data-stu-id="8f68e-130">Received calls</span></span>

- <span data-ttu-id="8f68e-131">成功呼叫</span><span class="sxs-lookup"><span data-stu-id="8f68e-131">Successful calls</span></span>

- <span data-ttu-id="8f68e-132">发起的呼叫</span><span class="sxs-lookup"><span data-stu-id="8f68e-132">Offered calls</span></span>

- <span data-ttu-id="8f68e-133">应答的呼叫</span><span class="sxs-lookup"><span data-stu-id="8f68e-133">Answered calls</span></span>

- <span data-ttu-id="8f68e-134">转接的呼叫</span><span class="sxs-lookup"><span data-stu-id="8f68e-134">Transferred calls</span></span>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a><span data-ttu-id="8f68e-135">充分利用响应组呼叫列表报告</span><span class="sxs-lookup"><span data-stu-id="8f68e-135">Making the Best Use of the Response Group Call List Report</span></span>

<span data-ttu-id="8f68e-p109">响应组呼叫列表报告允许您将所显示的数据限制为涉及特定响应组工作流的呼叫。为执行此操作，需要在“工作流 URI”框中输入工作流 URI（工作流的 SIP 地址）。但是，您必须实际上能够看到“工作流 URI”框，才能执行此操作。要显示响应组呼叫列表报告的筛选选项，请单击报告窗口左上部分的“显示/隐藏参数”按钮。</span><span class="sxs-lookup"><span data-stu-id="8f68e-p109">The Response Group Call List Report allows you to limit the displayed data to calls involving a particular Response Group workflow. To do that, you need to enter the workflow URI (the workflow's SIP address) in the Workflow URI box. Before you can do that, however, you must actually be able to see the Workflow URI box. To display the filtering options for the Response Group Call List Report, click the Show/Hide Parameters button in the upper left-hand portion of the report window.</span></span>

<span data-ttu-id="8f68e-140">请注意，如果将鼠标停留在其中任一指标上，响应组呼叫列表不会显示有关响应代码或诊断 ID 的信息。</span><span class="sxs-lookup"><span data-stu-id="8f68e-140">Note that the Response Group Call List does not display information about either the Response code or the Diagnostic ID if you hold the mouse over either of those metrics.</span></span> <span data-ttu-id="8f68e-141">如果你需要更多信息，你可以记下响应代码和/或诊断 ID，然后在 [Skype for Business Server](top-failures-report.md)中的"顶级故障报告"中搜索这些值。</span><span class="sxs-lookup"><span data-stu-id="8f68e-141">If you need more information, you might note the Response code and/or Diagnostic ID, and then search for those values in the [Top Failures Report in Skype for Business Server](top-failures-report.md).</span></span>

<span data-ttu-id="8f68e-142">对于类似如下的问题：“哪个个别工作流收到的呼叫数最多？”，您可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8f68e-142">a question like this one: "Which individual workflow received the most calls?", you can do the following:</span></span>

1. <span data-ttu-id="8f68e-p111">在“响应组使用报告”上，设置所需的时间段，然后单击“收到的呼叫”指标。这样即会打开“响应组呼叫列表报告”。</span><span class="sxs-lookup"><span data-stu-id="8f68e-p111">On the Response Group Usage Report, set the desired time period and then click the Received Calls metric. That will open the Response Group Call List Report.</span></span>

2. <span data-ttu-id="8f68e-p112">导出“响应组呼叫列表报告”上所显示的数据。例如，可以使用 Microsoft Excel 格式导出数据，然后使用 Excel 将该数据转换为逗号分隔值文件。</span><span class="sxs-lookup"><span data-stu-id="8f68e-p112">Export the data shown on the Response Group Call List Report. For example, you might export the data in Microsoft Excel format, and then use Excel to convert that data to a comma-separated values file.</span></span>

3. <span data-ttu-id="8f68e-147">使用 Windows PowerShell 运行您的分析。</span><span class="sxs-lookup"><span data-stu-id="8f68e-147">Run your analyses using Windows PowerShell.</span></span>

<span data-ttu-id="8f68e-148">例如，如果已将数据保存到名为 C:\Data\Response_Group_Call_List_Report.csv 的文件，则可以使用以下命令，针对报告中所列出的每个工作流返回收到的呼叫总数：</span><span class="sxs-lookup"><span data-stu-id="8f68e-148">For example, if you have saved the data to a file named C:\Data\Response_Group_Call_List_Report.csv, you can then use the following command to return the total number of received calls for each workflow listed in the report:</span></span>

```PowerShell
$calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
$calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending
```

<span data-ttu-id="8f68e-149">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="8f68e-149">That will information similar to this:</span></span>

<pre>
Count    Name
-----    ----
  160    Redmond Help Desk
   47    Dublin Help Desk
   31    North America Customer Support
   16    EMEA Customer Support
   14    Employment Opportunities
</pre>

## <a name="filters"></a><span data-ttu-id="8f68e-150">筛选器</span><span class="sxs-lookup"><span data-stu-id="8f68e-150">Filters</span></span>

<span data-ttu-id="8f68e-p113">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于响应组呼叫列表报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="8f68e-p113">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Response Group Call List Report.</span></span>

<span data-ttu-id="8f68e-153">**响应组呼叫列表报告筛选器**</span><span class="sxs-lookup"><span data-stu-id="8f68e-153">**Response Group Call List Report Filters**</span></span>


| <span data-ttu-id="8f68e-154">**名称**</span><span class="sxs-lookup"><span data-stu-id="8f68e-154">**Name**</span></span>               | <span data-ttu-id="8f68e-155">**说明**</span><span class="sxs-lookup"><span data-stu-id="8f68e-155">**Description**</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="8f68e-156">**From**</span><span class="sxs-lookup"><span data-stu-id="8f68e-156">**From**</span></span> <br/>         | <span data-ttu-id="8f68e-p114">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8f68e-p114">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span>  <br/> <span data-ttu-id="8f68e-159">7/7/2015 1：00 PM</span><span class="sxs-lookup"><span data-stu-id="8f68e-159">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="8f68e-p115">如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="8f68e-p115">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="8f68e-162">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="8f68e-162">7/7/2015</span></span>  <br/> <span data-ttu-id="8f68e-163">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="8f68e-163">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="8f68e-164">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="8f68e-164">7/3/2015</span></span>  <br/> <span data-ttu-id="8f68e-165">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="8f68e-165">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
| <span data-ttu-id="8f68e-166">"自"</span><span class="sxs-lookup"><span data-stu-id="8f68e-166">**To**</span></span> <br/>           | <span data-ttu-id="8f68e-p116">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8f68e-p116">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span>  <br/> <span data-ttu-id="8f68e-169">7/7/2015 1：00 PM</span><span class="sxs-lookup"><span data-stu-id="8f68e-169">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="8f68e-p117">如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="8f68e-p117">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="8f68e-172">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="8f68e-172">7/7/2015</span></span>  <br/> <span data-ttu-id="8f68e-173">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="8f68e-173">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="8f68e-174">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="8f68e-174">7/3/2015</span></span>  <br/> <span data-ttu-id="8f68e-175">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="8f68e-175">Weeks always run from Sunday through Saturday.</span></span>  <br/>        |
| <span data-ttu-id="8f68e-176">**工作流 URI**</span><span class="sxs-lookup"><span data-stu-id="8f68e-176">**Workflow URI**</span></span> <br/> | <span data-ttu-id="8f68e-p118">允许您限制返回的数据，以便仅显示指定响应组工作流的数据。若要使用该筛选器，请输入工作流 SIP 地址。例如：</span><span class="sxs-lookup"><span data-stu-id="8f68e-p118">Enables you to limit the returned data to the specified Response Group workflow. To use this filter, enter the Workflow SIP address. For example:</span></span>  <br/> <span data-ttu-id="8f68e-180">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8f68e-180">sip:helpdesk@litwareinc.com</span></span>  <br/>                                                                                                                                                                                                                                                                                                                                                                            |
| <span data-ttu-id="8f68e-181">**通话**</span><span class="sxs-lookup"><span data-stu-id="8f68e-181">**Calls**</span></span> <br/>        | <span data-ttu-id="8f68e-182">可以选择以下呼叫类型之一：</span><span class="sxs-lookup"><span data-stu-id="8f68e-182">You can select one of the following call types:</span></span> <br/>  <span data-ttu-id="8f68e-183">收到的呼叫</span><span class="sxs-lookup"><span data-stu-id="8f68e-183">Received Calls</span></span> <br/>  <span data-ttu-id="8f68e-184">成功呼叫</span><span class="sxs-lookup"><span data-stu-id="8f68e-184">Successful Calls</span></span> <br/>  <span data-ttu-id="8f68e-185">提供的呼叫</span><span class="sxs-lookup"><span data-stu-id="8f68e-185">Offered Calls</span></span> <br/>  <span data-ttu-id="8f68e-186">应答的呼叫</span><span class="sxs-lookup"><span data-stu-id="8f68e-186">Answered Calls</span></span> <br/>  <span data-ttu-id="8f68e-187">转接的呼叫</span><span class="sxs-lookup"><span data-stu-id="8f68e-187">Transferred Calls</span></span> <br/>                                                                                                                                                                                                                                                                                                                                                                                                |

## <a name="metrics"></a><span data-ttu-id="8f68e-188">指标</span><span class="sxs-lookup"><span data-stu-id="8f68e-188">Metrics</span></span>

<span data-ttu-id="8f68e-189">下表列出了响应组应用程序收到的每个呼叫的响应组呼叫列表报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="8f68e-189">The following table lists the information provided in the Response Group Call List Report for each call received by the Response Group application.</span></span>

<span data-ttu-id="8f68e-190">**响应组呼叫列表报告指标**</span><span class="sxs-lookup"><span data-stu-id="8f68e-190">**Response Group Call List Report Metrics**</span></span>

|<span data-ttu-id="8f68e-191">**名称**</span><span class="sxs-lookup"><span data-stu-id="8f68e-191">**Name**</span></span>|<span data-ttu-id="8f68e-192">**是否可按此项排序？**</span><span class="sxs-lookup"><span data-stu-id="8f68e-192">**Can you sort on this item?**</span></span>|<span data-ttu-id="8f68e-193">**说明**</span><span class="sxs-lookup"><span data-stu-id="8f68e-193">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8f68e-194">**Caller**</span><span class="sxs-lookup"><span data-stu-id="8f68e-194">**Caller**</span></span> <br/> |<span data-ttu-id="8f68e-195">否</span><span class="sxs-lookup"><span data-stu-id="8f68e-195">No</span></span>  <br/> |<span data-ttu-id="8f68e-196">呼叫者的 SIP 地址</span><span class="sxs-lookup"><span data-stu-id="8f68e-196">SIP address of the caller.</span></span>  <br/> |
|<span data-ttu-id="8f68e-197">**工作流**</span><span class="sxs-lookup"><span data-stu-id="8f68e-197">**Workflow**</span></span> <br/> |<span data-ttu-id="8f68e-198">否</span><span class="sxs-lookup"><span data-stu-id="8f68e-198">No</span></span>  <br/> |<span data-ttu-id="8f68e-199">响应组工作流的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="8f68e-199">SIP address of the Response Group workflow.</span></span>  <br/> |
|<span data-ttu-id="8f68e-200">**开始时间**</span><span class="sxs-lookup"><span data-stu-id="8f68e-200">**Start time**</span></span> <br/> |<span data-ttu-id="8f68e-201">否</span><span class="sxs-lookup"><span data-stu-id="8f68e-201">No</span></span>  <br/> |<span data-ttu-id="8f68e-202">呼叫开始的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="8f68e-202">Date and time that the call started.</span></span>  <br/> |
|<span data-ttu-id="8f68e-203">**结束时间**</span><span class="sxs-lookup"><span data-stu-id="8f68e-203">**End time**</span></span> <br/> |<span data-ttu-id="8f68e-204">否</span><span class="sxs-lookup"><span data-stu-id="8f68e-204">No</span></span>  <br/> |<span data-ttu-id="8f68e-205">呼叫结束的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="8f68e-205">Date and time that the call ended.</span></span>  <br/> |
|<span data-ttu-id="8f68e-206">**响应代码**</span><span class="sxs-lookup"><span data-stu-id="8f68e-206">**Response code**</span></span> <br/> |<span data-ttu-id="8f68e-207">否</span><span class="sxs-lookup"><span data-stu-id="8f68e-207">No</span></span>  <br/> |<span data-ttu-id="8f68e-208">会话失败时发送的 SIP 响应代码。</span><span class="sxs-lookup"><span data-stu-id="8f68e-208">SIP response code sent when the session failed.</span></span>  <br/> |
|<span data-ttu-id="8f68e-209">**诊断 ID**</span><span class="sxs-lookup"><span data-stu-id="8f68e-209">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="8f68e-210">否</span><span class="sxs-lookup"><span data-stu-id="8f68e-210">No</span></span>  <br/> |<span data-ttu-id="8f68e-211">附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。</span><span class="sxs-lookup"><span data-stu-id="8f68e-211">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |


