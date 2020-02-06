---
title: 在 Skype for Business 服务器中呼叫诊断报告（每用户）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9da13470-001e-415f-b8c5-29b1f3b531ba
description: 摘要：了解 Skype for Business 服务器中使用的每用户呼叫诊断报告。
ms.openlocfilehash: dbe9fc3e9140619f3c0f6015a313f84d2e8cbdaf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818133"
---
# <a name="call-diagnostic-reports-per-user-in-skype-for-business-server"></a><span data-ttu-id="08ec9-103">在 Skype for Business 服务器中呼叫诊断报告（每用户）</span><span class="sxs-lookup"><span data-stu-id="08ec9-103">Call Diagnostic Reports (per user) in Skype for Business Server</span></span>
  
<span data-ttu-id="08ec9-104">呼叫诊断报告提供有关失败的点对点会话和会议会话的每用户信息。</span><span class="sxs-lookup"><span data-stu-id="08ec9-104">The Call Diagnostic Reports provide per-user information about failed peer-to-peer and conferencing sessions.</span></span> <span data-ttu-id="08ec9-105">此时，只有一个报表，即**用户活动报表**。</span><span class="sxs-lookup"><span data-stu-id="08ec9-105">At this time there is only one report, the **User Activity Report**.</span></span>

<span data-ttu-id="08ec9-p102">用户活动报告提供了由用户在给定时间段内执行的对等会话和会议会话的详细列表。与很多监控报告不同，用户活动报告会将每个呼叫与单个用户绑定。例如，对等会话指定发起呼叫（源用户）的人员以及被呼叫（目标用户）的人员的 SIP URI。如果展开会议的信息，则会看到所有会议参与者及其在该会议中担任的角色的列表。</span><span class="sxs-lookup"><span data-stu-id="08ec9-p102">The User Activity Report provides a detailed list of the peer-to-peer and conferencing sessions carried out by your users in a given time period. Unlike many of the Monitoring Reports, the User Activity Report ties each call to individual users. For example, peer-to-peer sessions specify the SIP URIs of the person who initiated the call (the From user) and the person who was being called (the To user). If you expand the information for a conference, you'll see a list of all the conference participants and the role they held for that conference.</span></span>

<span data-ttu-id="08ec9-p103">用户活动报告有时候称为“技术支持”报告。这是因为该报告通常由技术支持人员用于检索特定用户的会话信息。您可以筛选来自或发往单个用户的呼叫，只需在“用户 URI”前缀框中键入该用户的 SIP URI 即可。</span><span class="sxs-lookup"><span data-stu-id="08ec9-p103">The User Activity Report is sometimes referred to as the "help desk" report. That's because the report is often used by help desk personnel to retrieve session information for a specific user. You can filter for calls made to or made by an individual user simply by typing the user's SIP URI in the User URI prefix box.</span></span>

<span data-ttu-id="08ec9-113">如果执行此操作，则用户活动报表将返回其 SIP URI 以指定字符串开头的任何用户的信息。</span><span class="sxs-lookup"><span data-stu-id="08ec9-113">If you do this, the User Activity Report will return information for any user whose SIP URI begins with the specified string.</span></span> <span data-ttu-id="08ec9-114">例如，如果您在 URI 框中键入 **ken**，则用户活动报告将查找 **Ken**.Myer@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="08ec9-114">For example, if you type **ken** in the URI box, the User Activity Report will locate **Ken**.Myer@litwareinc.com.</span></span> <span data-ttu-id="08ec9-115">但是，它还会查找以下用户：</span><span class="sxs-lookup"><span data-stu-id="08ec9-115">However, it will also locate these users:</span></span>

- <span data-ttu-id="08ec9-116">**ken** azi@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="08ec9-116">**ken** azi@litwareinc.com</span></span>

- <span data-ttu-id="08ec9-117">**ken** burg@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="08ec9-117">**ken** burg@litwareinc.com</span></span>

- <span data-ttu-id="08ec9-118">**Ken**.Sanchez@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="08ec9-118">**Ken**.Sanchez@litwareinc.com</span></span>

- <span data-ttu-id="08ec9-119">**Ken** nedy@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="08ec9-119">**Ken** nedy@litwareinc.com</span></span>

<span data-ttu-id="08ec9-120">若要确保仅返回 Ken Myer 的信息，请在 "搜索" 框中键入他的完整 URI （Ken.Myer@litwareinc.com）或最少的 Ken URI，以唯一地将其与组织中的其他用户区分开来。</span><span class="sxs-lookup"><span data-stu-id="08ec9-120">To ensure that information only for Ken Myer is returned, either type his full URI (Ken.Myer@litwareinc.com) in the search box or at least enough type of Ken's URI to uniquely distinguish him from other users in your organization.</span></span> <span data-ttu-id="08ec9-121">例如：</span><span class="sxs-lookup"><span data-stu-id="08ec9-121">For example:</span></span>

<span data-ttu-id="08ec9-122">Ken.my</span><span class="sxs-lookup"><span data-stu-id="08ec9-122">Ken.my</span></span>

## <a name="to-access-the-user-activity-report"></a><span data-ttu-id="08ec9-123">访问用户活动报告</span><span class="sxs-lookup"><span data-stu-id="08ec9-123">To access the user activity report</span></span>

<span data-ttu-id="08ec9-124">用户活动报告是从“监控报告”主页访问的。</span><span class="sxs-lookup"><span data-stu-id="08ec9-124">The User Activity Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="08ec9-125">您也可以通过单击[Skype For Business 服务器的 IP 电话清单报告](ip-phone-inventory-report.md)上的用户 URI 指标来访问用户活动报表。</span><span class="sxs-lookup"><span data-stu-id="08ec9-125">You can also reach the User Activity Report by clicking the User URI metric on the [IP Phone Inventory Report in Skype for Business Server](ip-phone-inventory-report.md).</span></span> <span data-ttu-id="08ec9-126">在用户活动报告中，单击“会议 URI”（针对会议）会将您转到会议详细信息报告。</span><span class="sxs-lookup"><span data-stu-id="08ec9-126">From within the User Activity Report, clicking the Conference URI (for a conference) takes you to the Conference Detail Report.</span></span> <span data-ttu-id="08ec9-127">同样，单击对等呼叫的详细指标将转到[Skype For Business Server 中的对等会话详细信息报告](peer-to-peer-session-detail-report.md)。</span><span class="sxs-lookup"><span data-stu-id="08ec9-127">Similarly, clicking the Detail metric for a peer-to-peer call takes you to the [Peer-to-Peer Session Detail Report in Skype for Business Server](peer-to-peer-session-detail-report.md).</span></span>

## <a name="making-the-best-use-of-the-user-activity-report"></a><span data-ttu-id="08ec9-128">充分利用用户活动报告</span><span class="sxs-lookup"><span data-stu-id="08ec9-128">Making the best use of the user activity report</span></span>

<span data-ttu-id="08ec9-129">尽管用户活动报告中有很多有用的信息，但这些信息有时候可能很难找到。</span><span class="sxs-lookup"><span data-stu-id="08ec9-129">Although there is a lot of good information in the User Activity Report, that information can sometimes be difficult to locate.</span></span> <span data-ttu-id="08ec9-130">例如，在指定期间内，你的组织中发生的所有用户活动均包括在用户活动报表中;这意味着，隐藏在报表内是有关哪些用户在某些方面实际使用 Skype for Business 服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="08ec9-130">For example, all the user activity that takes place in your organization during a specified period is included in the User Activity Report; that means that, buried, within the report is information about which users actually used Skype for Business Server in some way.</span></span>

> [!NOTE]
> <span data-ttu-id="08ec9-131">从技术上讲，某些用户活动可能会 unrecorded：尽管 Skype for Business 服务器努力保留有关所有电话呼叫的信息，但如果未将该呼叫的相关信息写入数据库.</span><span class="sxs-lookup"><span data-stu-id="08ec9-131">Technically, it's possible that some user activity might go unrecorded: while Skype for Business Server strives to keep information about all phone calls it's possible that a call could have been made without the information about that call being written to the database.</span></span> <span data-ttu-id="08ec9-132">Skype for business 服务器旨在提供极其准确但不一定完全了解 Skype for business 服务器的使用方法。</span><span class="sxs-lookup"><span data-stu-id="08ec9-132">Skype for Business Server is designed to give an extremely accurate but not necessarily perfect look at how Skype for Business Server is being used.</span></span> <span data-ttu-id="08ec9-133">（不能保证所有通话的100% 的记录都说明为什么不应将 Skype for Business 服务器监视用作帐单系统。）第二，监视报告最多只能显示1000条记录。</span><span class="sxs-lookup"><span data-stu-id="08ec9-133">(The fact that there is no guarantee that 100% of all calls are recorded explains why Skype for Business Server monitoring should not be used as a billing system.) Second, a Monitoring Report can only display, at most, 1,000 records.</span></span> <span data-ttu-id="08ec9-134">根据您具有的用户活动的数量以及您工作的时间段，这意味着您的查询可能无法返回数据库中实际存储的所有数据。</span><span class="sxs-lookup"><span data-stu-id="08ec9-134">Depending on the amount of user activity you have, and depending on the time period you are working with, that means your query might not return all the data actually stored in the database.</span></span> 

- <span data-ttu-id="08ec9-135">哪些用户在此时间段内实际上使用了系统？</span><span class="sxs-lookup"><span data-stu-id="08ec9-135">Which users actually used the system during this time period?</span></span>

- <span data-ttu-id="08ec9-136">我的哪些用户在此时间段内最活跃？</span><span class="sxs-lookup"><span data-stu-id="08ec9-136">Which of my users were the most active during this time period?</span></span>

- <span data-ttu-id="08ec9-137">发出电话呼叫最多的用户是否也是参与即时消息会话最多的用户？</span><span class="sxs-lookup"><span data-stu-id="08ec9-137">Are the users who make the most phone calls also the users who participate in the most instant messaging sessions?</span></span>

<span data-ttu-id="08ec9-138">如果需要回答此类问题，您可以将监视报告检索到的数据导出到 Excel 电子表格。</span><span class="sxs-lookup"><span data-stu-id="08ec9-138">If you need to answer questions like this, you can export the data retrieved by the Monitoring Reports to an Excel spreadsheet.</span></span> <span data-ttu-id="08ec9-139">然后，使用该电子表格和/或逗号分隔的值文件以用户活动报告的方式分析数据。</span><span class="sxs-lookup"><span data-stu-id="08ec9-139">You then use that spreadsheet and/or a comma-separated values file to analyze the data in ways that the User Activity Report.</span></span> <span data-ttu-id="08ec9-140">例如，假设您已将报告数据导出到 Excel，然后导出到逗号分隔的值文件。</span><span class="sxs-lookup"><span data-stu-id="08ec9-140">For example, suppose you have exported the report data to Excel and then to a comma-separated values file.</span></span> <span data-ttu-id="08ec9-141">此时，您可以从导入数据。CSV 文件到 Windows PowerShell，方法是使用如下所示的命令：</span><span class="sxs-lookup"><span data-stu-id="08ec9-141">At that point, you can import the data from the .CSV file to Windows PowerShell by using a command similar to this:</span></span>

```PowerShell
$x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"
```

<span data-ttu-id="08ec9-142">导入数据后，您可以使用简单的 Windows PowerShell 命令来帮助解答您的问题。</span><span class="sxs-lookup"><span data-stu-id="08ec9-142">After the data has been imported you can then use simple Windows PowerShell commands to help answer your questions.</span></span> <span data-ttu-id="08ec9-143">例如，以下命令将返回至少在一个会话中充当“源用户”的唯一用户的列表：</span><span class="sxs-lookup"><span data-stu-id="08ec9-143">For example, this command returns a list of unique users who served as the "From user" in at least one session:</span></span>

```PowerShell
$x | Group-Object "From user" | Select Name | Sort-Object Name
```

<span data-ttu-id="08ec9-144">换言之：</span><span class="sxs-lookup"><span data-stu-id="08ec9-144">In other words:</span></span>

<pre>
Name
----
David.Ahs@litwareinc.com
Gilead.Amosnino@litwareinc.com
Henrik.Jensen@litwareinc.com
Ken.Myer@litwareinc.com
Pilar.Ackerman@litwareinc.com
</pre>

<span data-ttu-id="08ec9-145">以下命令将根据唯一用户参与的会话的总数列出这些用户：</span><span class="sxs-lookup"><span data-stu-id="08ec9-145">This command lists the unique users (based on the total number of sessions that they participated in:</span></span>

```PowerShell
$x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending
```

<span data-ttu-id="08ec9-146">这将返回类似于下面的数据：</span><span class="sxs-lookup"><span data-stu-id="08ec9-146">That returns data similar to this:</span></span>

<pre>
Count    Name
-----    ----
  523    Ken.Myer@litwareinc.com
   63    David.Ahs@litwareinc.com
   29    Pilar.Ackerman@litwareinc.com
   17    Gilead.Amosnino@litwareinc.com
   10    Henrik.Jensen@litwareinc.com
</pre>

<span data-ttu-id="08ec9-147">以下命令会将报告的会话限制为将音频作为一种形式包含的会话：</span><span class="sxs-lookup"><span data-stu-id="08ec9-147">This command limits the reported sessions to those that included audio as a modality:</span></span>

```PowerShell
$x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending
```

<span data-ttu-id="08ec9-148">如果将鼠标悬停在报告上显示的任何诊断 ID 上，则会出现一个描述该 ID 的工具提示。</span><span class="sxs-lookup"><span data-stu-id="08ec9-148">If you hold your mouse over any Diagnostic ID shown on the report, a tooltip will appear describing that ID.</span></span>

## <a name="filters"></a><span data-ttu-id="08ec9-149">筛选器</span><span class="sxs-lookup"><span data-stu-id="08ec9-149">Filters</span></span>

<span data-ttu-id="08ec9-p111">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，用户活动报告允许您基于活动类型（即对等会话还是会议会话）或用户的 SIP 地址（允许您查看一个用户的活动）筛选返回的数据。您还可以选择数据的分组方式。在此示例中，将按小时、日、周或月对使用情况进行分组。</span><span class="sxs-lookup"><span data-stu-id="08ec9-p111">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the User Activity Report enables you to filter the returned data based on such things as activity type (that is, peer-to-peer sessions or conferencing sessions) or by the user's SIP address (allowing you to view the activities for one user). You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="08ec9-154">下表列出了可用于用户活动报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="08ec9-154">The following table lists the filters that you can use with the User Activity Report.</span></span>

<span data-ttu-id="08ec9-155">**用户活动报告筛选器**</span><span class="sxs-lookup"><span data-stu-id="08ec9-155">**User activity report filters**</span></span>


| <span data-ttu-id="08ec9-156">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="08ec9-156">**Name**</span></span>   | <span data-ttu-id="08ec9-157">**说明**</span><span class="sxs-lookup"><span data-stu-id="08ec9-157">**Description**</span></span>  |
|:-----------|:--------|
| <span data-ttu-id="08ec9-158">**从**</span><span class="sxs-lookup"><span data-stu-id="08ec9-158">**From**</span></span> <br/>             | <span data-ttu-id="08ec9-p112">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="08ec9-p112">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span>  <br/> <span data-ttu-id="08ec9-161">7/17/12015 13:00</span><span class="sxs-lookup"><span data-stu-id="08ec9-161">7/17/12015 1:00 PM</span></span>  <br/> <span data-ttu-id="08ec9-p113">如果您未输入开始时间，该报告会自动将将某个特定日期的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="08ec9-p113">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="08ec9-164">7/17/12015</span><span class="sxs-lookup"><span data-stu-id="08ec9-164">7/17/12015</span></span>  <br/> <span data-ttu-id="08ec9-165">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="08ec9-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="08ec9-166">2015/7/13</span><span class="sxs-lookup"><span data-stu-id="08ec9-166">7/13/2015</span></span>  <br/> <span data-ttu-id="08ec9-167">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="08ec9-167">Weeks always run from Sunday through Saturday.</span></span>  <br/>                                                      |
| <span data-ttu-id="08ec9-168">**到**</span><span class="sxs-lookup"><span data-stu-id="08ec9-168">**To**</span></span> <br/>               | <span data-ttu-id="08ec9-p114">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="08ec9-p114">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span>  <br/> <span data-ttu-id="08ec9-171">7/17/12015 13:00</span><span class="sxs-lookup"><span data-stu-id="08ec9-171">7/17/12015 1:00 PM</span></span>  <br/> <span data-ttu-id="08ec9-p115">如果您未输入结束时间，该报告会自动将某个特定日期的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="08ec9-p115">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="08ec9-174">7/17/12015</span><span class="sxs-lookup"><span data-stu-id="08ec9-174">7/17/12015</span></span>  <br/> <span data-ttu-id="08ec9-175">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="08ec9-175">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="08ec9-176">2015/7/13</span><span class="sxs-lookup"><span data-stu-id="08ec9-176">7/13/2015</span></span>  <br/> <span data-ttu-id="08ec9-177">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="08ec9-177">Weeks always run from Sunday through Saturday.</span></span>  <br/>                                                             |
| <span data-ttu-id="08ec9-178">**活动类型**</span><span class="sxs-lookup"><span data-stu-id="08ec9-178">**Activity type**</span></span> <br/>    | <span data-ttu-id="08ec9-p116">活动的类型。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="08ec9-p116">Type of activity. Select one of the following:</span></span> <br/>  <span data-ttu-id="08ec9-181">[所有]</span><span class="sxs-lookup"><span data-stu-id="08ec9-181">[All]</span></span> <br/>  <span data-ttu-id="08ec9-182">对等</span><span class="sxs-lookup"><span data-stu-id="08ec9-182">Peer-to-peer</span></span> <br/>  <span data-ttu-id="08ec9-183">会议</span><span class="sxs-lookup"><span data-stu-id="08ec9-183">Conference</span></span> <br/>      |
| <span data-ttu-id="08ec9-184">**形式**</span><span class="sxs-lookup"><span data-stu-id="08ec9-184">**Modality**</span></span> <br/>         | <span data-ttu-id="08ec9-185">可用的形式取决于选择的“活动类型”。</span><span class="sxs-lookup"><span data-stu-id="08ec9-185">The Modality available to you varies depending on the select Activity Type.</span></span> <span data-ttu-id="08ec9-186">如果活动类型是对等，则可以选择 "IM";文件传输;应用程序共享;语态或视频作为模态。</span><span class="sxs-lookup"><span data-stu-id="08ec9-186">If the Activity Type is Peer-to-Peer, you can select IM; File Transfer; Application Sharing; Voice; or Video as the modality.</span></span>  <br/> <span data-ttu-id="08ec9-187">如果“活动类型”是“会议”，您可以选择“IM 电话会议”、“Web 会议”、“应用程序共享”、“语音/视频会议”或“电话会议”。</span><span class="sxs-lookup"><span data-stu-id="08ec9-187">If the Activity Type is Conference, you can select IM Phone conference; Web conference; Application Sharing; Voice/Video conference; or Telephony conference.</span></span>  <br/>         |
| <span data-ttu-id="08ec9-188">**会话类别**</span><span class="sxs-lookup"><span data-stu-id="08ec9-188">**Session category**</span></span> <br/> | <span data-ttu-id="08ec9-p118">指示相应活动已成功还是失败。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="08ec9-p118">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span> <br/>  <span data-ttu-id="08ec9-191">[所有]</span><span class="sxs-lookup"><span data-stu-id="08ec9-191">[All]</span></span> <br/>  <span data-ttu-id="08ec9-192">成功</span><span class="sxs-lookup"><span data-stu-id="08ec9-192">Success</span></span> <br/>  <span data-ttu-id="08ec9-193">预期失败</span><span class="sxs-lookup"><span data-stu-id="08ec9-193">Expected failure</span></span> <br/>  <span data-ttu-id="08ec9-194">意外失败</span><span class="sxs-lookup"><span data-stu-id="08ec9-194">Unexpected failure</span></span> <br/>  <span data-ttu-id="08ec9-p119">“预期失败”是指预计会出现的失败情况；例如，如果用户将其状态设置为“请勿打扰”，那么向该用户发出的任何呼叫应该都会失败。“意外失败”是指在本该正常运行的系统中出现的失败情况。例如，如果呼叫者处于呼叫等待状态，则不应该终止呼叫。如果终止，则会被标记为意外失败。</span><span class="sxs-lookup"><span data-stu-id="08ec9-p119">An "expected failure" is a failure that is expected to happen; for example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail. An "unexpected failure" is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span> <br/> |
| <span data-ttu-id="08ec9-199">**用户 URI 前缀**</span><span class="sxs-lookup"><span data-stu-id="08ec9-199">**User URI prefix**</span></span> <br/>  | <span data-ttu-id="08ec9-p120">用户的 SIP 地址。要仅查看用户 Ken Myer 的记录，您需要输入 Ken Myer 的 SIP 地址。例如：</span><span class="sxs-lookup"><span data-stu-id="08ec9-p120">SIP address for the user. To view records only for the user Ken Myer you need to enter Ken Myer's SIP address. For example:</span></span>  <br/> <span data-ttu-id="08ec9-203">sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="08ec9-203">sip:kenmyer@litwareinc.com</span></span>  <br/>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="08ec9-204">对等会话的指标</span><span class="sxs-lookup"><span data-stu-id="08ec9-204">Metrics for peer-to-peer sessions</span></span>

<span data-ttu-id="08ec9-205">下表列出了对等会话（即，只涉及两个参与者的会话）的用户活动报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="08ec9-205">The following table lists the information provided in the User Activity Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

<span data-ttu-id="08ec9-206">**对等会话的指标**</span><span class="sxs-lookup"><span data-stu-id="08ec9-206">**Metrics for peer-to-peer sessions**</span></span>

|<span data-ttu-id="08ec9-207">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="08ec9-207">**Name**</span></span>|<span data-ttu-id="08ec9-208">**是否可按此项排序？**</span><span class="sxs-lookup"><span data-stu-id="08ec9-208">**Can you sort on this item?**</span></span>|<span data-ttu-id="08ec9-209">**说明**</span><span class="sxs-lookup"><span data-stu-id="08ec9-209">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="08ec9-210">**详情**</span><span class="sxs-lookup"><span data-stu-id="08ec9-210">**Detail**</span></span> <br/> |<span data-ttu-id="08ec9-211">否</span><span class="sxs-lookup"><span data-stu-id="08ec9-211">No</span></span>  <br/> |<span data-ttu-id="08ec9-212">单击此项时，报告将显示所选会话的对等会话详细信息报告。</span><span class="sxs-lookup"><span data-stu-id="08ec9-212">When you click this item, the report shows you the Peer-to-Peer Session Detail Report for the selected session.</span></span>  <br/> |
|<span data-ttu-id="08ec9-213">**来源用户**</span><span class="sxs-lookup"><span data-stu-id="08ec9-213">**From user**</span></span> <br/> |<span data-ttu-id="08ec9-214">是</span><span class="sxs-lookup"><span data-stu-id="08ec9-214">Yes</span></span>  <br/> |<span data-ttu-id="08ec9-215">发起对等会话的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="08ec9-215">SIP address of the user who initiated the peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="08ec9-216">**目标用户**</span><span class="sxs-lookup"><span data-stu-id="08ec9-216">**To user**</span></span> <br/> |<span data-ttu-id="08ec9-217">是</span><span class="sxs-lookup"><span data-stu-id="08ec9-217">Yes</span></span>  <br/> |<span data-ttu-id="08ec9-218">加入对等会话的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="08ec9-218">SIP address of the user who joined the peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="08ec9-219">**形式**</span><span class="sxs-lookup"><span data-stu-id="08ec9-219">**Modalities**</span></span> <br/> |<span data-ttu-id="08ec9-220">是</span><span class="sxs-lookup"><span data-stu-id="08ec9-220">Yes</span></span>  <br/> |<span data-ttu-id="08ec9-p121">会话中使用的通信类型。例如，IM、音频或文件传输。</span><span class="sxs-lookup"><span data-stu-id="08ec9-p121">Type of communication used in the session. For example, IM, audio, or file transfer.</span></span>  <br/> |
|<span data-ttu-id="08ec9-223">**邀请时间**</span><span class="sxs-lookup"><span data-stu-id="08ec9-223">**Invite time**</span></span> <br/> |<span data-ttu-id="08ec9-224">是</span><span class="sxs-lookup"><span data-stu-id="08ec9-224">Yes</span></span>  <br/> |<span data-ttu-id="08ec9-225">发送加入对等会话的初始邀请的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="08ec9-225">Date and time the initial invitation to join the peer-to-peer session was sent.</span></span>  <br/> |
|<span data-ttu-id="08ec9-226">**响应时间**</span><span class="sxs-lookup"><span data-stu-id="08ec9-226">**Response time**</span></span> <br/> |<span data-ttu-id="08ec9-227">是</span><span class="sxs-lookup"><span data-stu-id="08ec9-227">Yes</span></span>  <br/> |<span data-ttu-id="08ec9-228">“目标”用户接受会话邀请的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="08ec9-228">Date and time that the "To" user accepted the session invitation.</span></span>  <br/> |
|<span data-ttu-id="08ec9-229">**结束时间**</span><span class="sxs-lookup"><span data-stu-id="08ec9-229">**End time**</span></span> <br/> |<span data-ttu-id="08ec9-230">是</span><span class="sxs-lookup"><span data-stu-id="08ec9-230">Yes</span></span>  <br/> |<span data-ttu-id="08ec9-231">对等会话结束的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="08ec9-231">Date and time the peer-to-peer session ended.</span></span>  <br/> |
|<span data-ttu-id="08ec9-232">**诊断 ID**</span><span class="sxs-lookup"><span data-stu-id="08ec9-232">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="08ec9-233">是</span><span class="sxs-lookup"><span data-stu-id="08ec9-233">Yes</span></span>  <br/> |<span data-ttu-id="08ec9-p122">附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。诊断标头是可选的（SIP 会话可以不包含这些标头），并且只对遇到此类问题的会话报告诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="08ec9-p122">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span>  <br/> |

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="08ec9-236">会议会话的指标</span><span class="sxs-lookup"><span data-stu-id="08ec9-236">Metrics for conferencing sessions</span></span>

<span data-ttu-id="08ec9-237">下表列出了会议会话（即，涉及三个或更多参与者的会话）的用户活动报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="08ec9-237">The following table lists the information provided in the User Activity Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

<span data-ttu-id="08ec9-238">**会议会话的指标**</span><span class="sxs-lookup"><span data-stu-id="08ec9-238">**Metrics for conferencing sessions**</span></span>

|<span data-ttu-id="08ec9-239">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="08ec9-239">**Name**</span></span>|<span data-ttu-id="08ec9-240">**是否可按此项排序？**</span><span class="sxs-lookup"><span data-stu-id="08ec9-240">**Can you sort on this item?**</span></span>|<span data-ttu-id="08ec9-241">**说明**</span><span class="sxs-lookup"><span data-stu-id="08ec9-241">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="08ec9-242">**会议 URI**</span><span class="sxs-lookup"><span data-stu-id="08ec9-242">**Conference URI**</span></span> <br/> |<span data-ttu-id="08ec9-243">是</span><span class="sxs-lookup"><span data-stu-id="08ec9-243">Yes</span></span>  <br/> |<span data-ttu-id="08ec9-p123">唯一会议标识符。单击此项时，报告将显示所选会话的会议详细信息报告。展开此项时，报告将显示有关会议参与者的信息。有关详细信息，请参阅本主题后面的“会议参与者的指标”一节。</span><span class="sxs-lookup"><span data-stu-id="08ec9-p123">Unique conference identifier. When you click this item, the report shows you the Conference Detail Report for the selected session. When you expand this item, the report shows you information about the conference participants. For details, see the "Metrics for Conference Participants" section later in this topic.</span></span>  <br/> |
|<span data-ttu-id="08ec9-248">**组织者**</span><span class="sxs-lookup"><span data-stu-id="08ec9-248">**Organizer**</span></span> <br/> |<span data-ttu-id="08ec9-249">是</span><span class="sxs-lookup"><span data-stu-id="08ec9-249">Yes</span></span>  <br/> |<span data-ttu-id="08ec9-250">组织会议的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="08ec9-250">SIP address of the user who organized the conference.</span></span>  <br/> |
|<span data-ttu-id="08ec9-251">**池**</span><span class="sxs-lookup"><span data-stu-id="08ec9-251">**Pool**</span></span> <br/> |<span data-ttu-id="08ec9-252">是</span><span class="sxs-lookup"><span data-stu-id="08ec9-252">Yes</span></span>  <br/> |<span data-ttu-id="08ec9-253">会议中使用的边缘服务器（如果有）的名称。</span><span class="sxs-lookup"><span data-stu-id="08ec9-253">Name of the Edge Server (if any) used in the conference.</span></span>  <br/> |
|<span data-ttu-id="08ec9-254">**开始时间**</span><span class="sxs-lookup"><span data-stu-id="08ec9-254">**Start time**</span></span> <br/> |<span data-ttu-id="08ec9-255">是</span><span class="sxs-lookup"><span data-stu-id="08ec9-255">Yes</span></span>  <br/> |<span data-ttu-id="08ec9-256">会议开始的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="08ec9-256">Date and time that the conference began.</span></span>  <br/> |
|<span data-ttu-id="08ec9-257">**结束时间**</span><span class="sxs-lookup"><span data-stu-id="08ec9-257">**End time**</span></span> <br/> |<span data-ttu-id="08ec9-258">是</span><span class="sxs-lookup"><span data-stu-id="08ec9-258">Yes</span></span>  <br/> |<span data-ttu-id="08ec9-259">会议结束的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="08ec9-259">Date and time that the conference ended.</span></span>  <br/> |

## <a name="metrics-for-conference-participants"></a><span data-ttu-id="08ec9-260">会议参与者的指标</span><span class="sxs-lookup"><span data-stu-id="08ec9-260">Metrics for conference participants</span></span>

<span data-ttu-id="08ec9-261">下表列出了会议的每个参与者的用户活动报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="08ec9-261">The following table lists the information provided in the User Activity Report provides for each participant in a conference.</span></span>

<span data-ttu-id="08ec9-262">**会议参与者的指标**</span><span class="sxs-lookup"><span data-stu-id="08ec9-262">**Metrics for conference participants**</span></span>

|<span data-ttu-id="08ec9-263">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="08ec9-263">**Name**</span></span>|<span data-ttu-id="08ec9-264">**是否可按此项排序？**</span><span class="sxs-lookup"><span data-stu-id="08ec9-264">**Can you sort on this item?**</span></span>|<span data-ttu-id="08ec9-265">**说明**</span><span class="sxs-lookup"><span data-stu-id="08ec9-265">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="08ec9-266">**角色**</span><span class="sxs-lookup"><span data-stu-id="08ec9-266">**Role**</span></span> <br/> |<span data-ttu-id="08ec9-267">否</span><span class="sxs-lookup"><span data-stu-id="08ec9-267">No</span></span>  <br/> |<span data-ttu-id="08ec9-268">用户的会议角色（例如，演示者）。</span><span class="sxs-lookup"><span data-stu-id="08ec9-268">Conference role (for example, Presenter) for the user.</span></span>  <br/> |
|<span data-ttu-id="08ec9-269">**参与者**</span><span class="sxs-lookup"><span data-stu-id="08ec9-269">**Participant**</span></span> <br/> |<span data-ttu-id="08ec9-270">否</span><span class="sxs-lookup"><span data-stu-id="08ec9-270">No</span></span>  <br/> |<span data-ttu-id="08ec9-271">用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="08ec9-271">SIP address of the user.</span></span>  <br/> |
|<span data-ttu-id="08ec9-272">**连接**</span><span class="sxs-lookup"><span data-stu-id="08ec9-272">**Connectivity**</span></span> <br/> |<span data-ttu-id="08ec9-273">否</span><span class="sxs-lookup"><span data-stu-id="08ec9-273">No</span></span>  <br/> |<span data-ttu-id="08ec9-p124">网络连接类型。例如，“来自内部”表示内部连接，“来自 PSTN”表示拨入用户。</span><span class="sxs-lookup"><span data-stu-id="08ec9-p124">Network connection type. For example "From Internal" for internal connection or "From PSTN" for dial-in users.</span></span>  <br/> |
|<span data-ttu-id="08ec9-276">**加入时间**</span><span class="sxs-lookup"><span data-stu-id="08ec9-276">**Join time**</span></span> <br/> |<span data-ttu-id="08ec9-277">否</span><span class="sxs-lookup"><span data-stu-id="08ec9-277">No</span></span>  <br/> |<span data-ttu-id="08ec9-278">用户加入会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="08ec9-278">Date and time that the user joined the conference.</span></span>  <br/> |
|<span data-ttu-id="08ec9-279">**离开时间**</span><span class="sxs-lookup"><span data-stu-id="08ec9-279">**Leave time**</span></span> <br/> |<span data-ttu-id="08ec9-280">否</span><span class="sxs-lookup"><span data-stu-id="08ec9-280">No</span></span>  <br/> |<span data-ttu-id="08ec9-281">用户离开会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="08ec9-281">Date and time that the user left the conference.</span></span>  <br/> |
|<span data-ttu-id="08ec9-282">**诊断 ID**</span><span class="sxs-lookup"><span data-stu-id="08ec9-282">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="08ec9-283">否</span><span class="sxs-lookup"><span data-stu-id="08ec9-283">No</span></span>  <br/> |<span data-ttu-id="08ec9-p125">附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。诊断标头是可选的（SIP 会话可以不包含这些标头），并且只对遇到此类问题的会话报告诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="08ec9-p125">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span>  <br/> |

