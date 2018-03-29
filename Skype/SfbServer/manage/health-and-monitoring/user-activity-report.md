---
title: Skype for Business Server 2015 中的用户活动报告
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3aa6fef2-ea02-4f0f-93e8-fa2e0a953d79
description: 摘要： 了解业务服务器 2015年在 Skype 的用户活动报告。
ms.openlocfilehash: b3a69f067f2acbc27b84b58c7ebc9ba53c979f92
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="user-activity-report-in-skype-for-business-server-2015"></a><span data-ttu-id="666e7-103">Skype for Business Server 2015 中的用户活动报告</span><span class="sxs-lookup"><span data-stu-id="666e7-103">User Activity Report in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="666e7-104">**摘要：**了解业务服务器 2015年在 Skype 的用户活动报告。</span><span class="sxs-lookup"><span data-stu-id="666e7-104">**Summary:** Learn about the User Activity Report in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="666e7-p101">用户活动报告提供了由用户在给定时间段内执行的对等会话和会议会话的详细列表。与很多监控报告不同，用户活动报告会将每个呼叫与单个用户绑定。例如，对等会话指定发起呼叫（源用户）的人员以及被呼叫（目标用户）的人员的 SIP URI。如果展开会议的信息，则会看到所有会议参与者及其在该会议中担任的角色的列表。</span><span class="sxs-lookup"><span data-stu-id="666e7-p101">The User Activity Report provides a detailed list of the peer-to-peer and conferencing sessions carried out by your users in a given time period. Unlike many of the Monitoring Reports, the User Activity Report ties each call to individual users. For example, peer-to-peer sessions specify the SIP URIs of the person who initiated the call (the From user) and the person who was being called (the To user). If you expand the information for a conference, you'll see a list of all the conference participants and the role they held for that conference.</span></span>
  
<span data-ttu-id="666e7-p102">用户活动报告有时候称为“技术支持”报告。这是因为该报告通常由技术支持人员用于检索特定用户的会话信息。您可以筛选来自或发往单个用户的呼叫，只需在“用户 URI”前缀框中键入该用户的 SIP URI 即可。</span><span class="sxs-lookup"><span data-stu-id="666e7-p102">The User Activity Report is sometimes referred to as the "help desk" report. That's because the report is often used by help desk personnel to retrieve session information for a specific user. You can filter for calls made to or made by an individual user simply by typing the user's SIP URI in the User URI prefix box.</span></span>
  
<span data-ttu-id="666e7-112">如果您执行此操作，用户活动报告将返回任何用户的 SIP URI 以指定字符串开头的信息。</span><span class="sxs-lookup"><span data-stu-id="666e7-112">If you do this, the User Activity Report will return information for any user whose SIP URI begins with the specified string.</span></span> <span data-ttu-id="666e7-113">例如，如果您在 URI 框中键入**ken** ，用户活动报告将找到**Ken**。Myer@litwareinc.com。 但是，它将查找用户：</span><span class="sxs-lookup"><span data-stu-id="666e7-113">For example, if you type **ken** in the URI box, the User Activity Report will locate **Ken**.Myer@litwareinc.com. However, it will also locate these users:</span></span>
  
- <span data-ttu-id="666e7-114">**ken** azi@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="666e7-114">**ken** azi@litwareinc.com</span></span>
    
- <span data-ttu-id="666e7-115">**ken** burg@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="666e7-115">**ken** burg@litwareinc.com</span></span>
    
- <span data-ttu-id="666e7-116">**Ken**。Sanchez@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="666e7-116">**Ken**.Sanchez@litwareinc.com</span></span>
    
- <span data-ttu-id="666e7-117">**Ken** nedy@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="666e7-117">**Ken** nedy@litwareinc.com</span></span>
    
<span data-ttu-id="666e7-118">以确保该信息只是返回的 Ken Myer，键入他完整的 URI (Ken.Myer@litwareinc.com) 在搜索框中或至少足够类型的 Ken 的 URI 唯一区分他和其他用户在您的组织中。</span><span class="sxs-lookup"><span data-stu-id="666e7-118">To ensure that information only for Ken Myer is returned, either type his full URI (Ken.Myer@litwareinc.com) in the search box or at least enough type of Ken's URI to uniquely distinguish him from other users in your organization.</span></span> <span data-ttu-id="666e7-119">例如：</span><span class="sxs-lookup"><span data-stu-id="666e7-119">For example:</span></span>
  
<span data-ttu-id="666e7-120">Ken.my</span><span class="sxs-lookup"><span data-stu-id="666e7-120">Ken.my</span></span>
  
## <a name="to-access-the-user-activity-report"></a><span data-ttu-id="666e7-121">访问用户活动报告</span><span class="sxs-lookup"><span data-stu-id="666e7-121">To access the user activity report</span></span>

<span data-ttu-id="666e7-122">用户活动报告是从“监控报告”主页访问的。</span><span class="sxs-lookup"><span data-stu-id="666e7-122">The User Activity Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="666e7-123">您还可以通过单击[IP 电话库存报表中的业务服务器 2015 Skype](ip-phone-inventory-report.md)的用户 URI 跃点数来访问用户活动报告。</span><span class="sxs-lookup"><span data-stu-id="666e7-123">You can also reach the User Activity Report by clicking the User URI metric on the [IP Phone Inventory Report in Skype for Business Server 2015](ip-phone-inventory-report.md).</span></span> <span data-ttu-id="666e7-124">在用户活动报告中，单击“会议 URI”（针对会议）会将您转到会议详细信息报告。</span><span class="sxs-lookup"><span data-stu-id="666e7-124">From within the User Activity Report, clicking the Conference URI (for a conference) takes you to the Conference Detail Report.</span></span> <span data-ttu-id="666e7-125">同样，单击的点到点调用的详细指标转到[业务服务器 2015年的 Skype 在对等会话详细信息报告](peer-to-peer-session-detail-report.md)。</span><span class="sxs-lookup"><span data-stu-id="666e7-125">Similarly, clicking the Detail metric for a peer-to-peer call takes you to the [Peer-to-Peer Session Detail Report in Skype for Business Server 2015](peer-to-peer-session-detail-report.md).</span></span>
  
## <a name="making-the-best-use-of-the-user-activity-report"></a><span data-ttu-id="666e7-126">充分利用用户活动报告</span><span class="sxs-lookup"><span data-stu-id="666e7-126">Making the best use of the user activity report</span></span>

<span data-ttu-id="666e7-127">尽管用户活动报告中有很多有用的信息，但这些信息有时候可能很难找到。</span><span class="sxs-lookup"><span data-stu-id="666e7-127">Although there is a lot of good information in the User Activity Report, that information can sometimes be difficult to locate.</span></span> <span data-ttu-id="666e7-128">例如，在您的组织在一个指定的期间内进行的用户活动纳入用户活动报告;表示、 埋、 报表内的报表是有关哪些用户实际使用 Skype 业务服务器 2015年以某种方式的信息。</span><span class="sxs-lookup"><span data-stu-id="666e7-128">For example, all the user activity that takes place in your organization during a specified period is included in the User Activity Report; that means that, buried, within the report is information about which users actually used Skype for Business Server 2015 in some way.</span></span>
  
> [!NOTE]
> <span data-ttu-id="666e7-129">从技术上讲，有可能某些用户操作可能转债务： 尽管 Skype 的努力保持它是调用可能已做的信息写入到该调用不可能所有的电话信息业务服务器数据库。</span><span class="sxs-lookup"><span data-stu-id="666e7-129">Technically, it's possible that some user activity might go unrecorded: while Skype for Business Server strives to keep information about all phone calls it's possible that a call could have been made without the information about that call being written to the database.</span></span> <span data-ttu-id="666e7-130">Skype 业务服务器用于提供非常准确，但不是一定完全看业务服务器 2015年的 Skype 的使用方式。</span><span class="sxs-lookup"><span data-stu-id="666e7-130">Skype for Business Server is designed to give an extremely accurate but not necessarily perfect look at how Skype for Business Server 2015 is being used.</span></span> <span data-ttu-id="666e7-131">（所以并不能保证 100%的所有调用都记录情况解释为什么 Skype 业务服务器的监控不应作为计费系统）。第二，监视报告可以仅显示，顶多 1000 个记录。</span><span class="sxs-lookup"><span data-stu-id="666e7-131">(The fact that there is no guarantee that 100% of all calls are recorded explains why Skype for Business Server monitoring should not be used as a billing system.) Second, a Monitoring Report can only display, at most, 1,000 records.</span></span> <span data-ttu-id="666e7-132">根据您具有的用户活动的数量以及您工作的时间段，这意味着您的查询可能无法返回数据库中实际存储的所有数据。</span><span class="sxs-lookup"><span data-stu-id="666e7-132">Depending on the amount of user activity you have, and depending on the time period you are working with, that means your query might not return all the data actually stored in the database.</span></span> 
  
- <span data-ttu-id="666e7-133">哪些用户在此时间段内实际上使用了系统？</span><span class="sxs-lookup"><span data-stu-id="666e7-133">Which users actually used the system during this time period?</span></span>
    
- <span data-ttu-id="666e7-134">我的哪些用户在此时间段内最活跃？</span><span class="sxs-lookup"><span data-stu-id="666e7-134">Which of my users were the most active during this time period?</span></span>
    
- <span data-ttu-id="666e7-135">发出电话呼叫最多的用户是否也是参与即时消息会话最多的用户？</span><span class="sxs-lookup"><span data-stu-id="666e7-135">Are the users who make the most phone calls also the users who participate in the most instant messaging sessions?</span></span>
    
<span data-ttu-id="666e7-136">如果您需要回答这样的问题，您可以导出由监视 Excel 电子表格报告中检索的数据。</span><span class="sxs-lookup"><span data-stu-id="666e7-136">If you need to answer questions like this, you can export the data retrieved by the Monitoring Reports to an Excel spreadsheet.</span></span> <span data-ttu-id="666e7-137">然后您使用该电子表格和/或逗号分隔值文件以分析该数据的用户活动报告的方式。</span><span class="sxs-lookup"><span data-stu-id="666e7-137">You then use that spreadsheet and/or a comma-separated values file to analyze the data in ways that the User Activity Report.</span></span> <span data-ttu-id="666e7-138">例如，假设已报告数据导出到 Excel，然后到一个逗号分隔值文件。</span><span class="sxs-lookup"><span data-stu-id="666e7-138">For example, suppose you have exported the report data to Excel and then to a comma-separated values file.</span></span> <span data-ttu-id="666e7-139">此时，您可以导入的数据。CSV 文件到 Windows PowerShell 使用与以下类似的命令：</span><span class="sxs-lookup"><span data-stu-id="666e7-139">At that point, you can import the data from the .CSV file to Windows PowerShell by using a command similar to this:</span></span>
  
```
$x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"
```

<span data-ttu-id="666e7-140">已导入数据后可再用于简单 Windows PowerShell 命令帮助回答您的问题。</span><span class="sxs-lookup"><span data-stu-id="666e7-140">After the data has been imported you can then use simple Windows PowerShell commands to help answer your questions.</span></span> <span data-ttu-id="666e7-141">例如，以下命令将返回至少在一个会话中充当“源用户”的唯一用户的列表：</span><span class="sxs-lookup"><span data-stu-id="666e7-141">For example, this command returns a list of unique users who served as the "From user" in at least one session:</span></span>
  
```
$x | Group-Object "From user" | Select Name | Sort-Object Name
```

<span data-ttu-id="666e7-142">换言之：</span><span class="sxs-lookup"><span data-stu-id="666e7-142">In other words:</span></span>
  
```
Name
----
David.Ahs@litwareinc.com
Gilead.Amosnino@litwareinc.com
Henrik.Jensen@litwareinc.com
Ken.Myer@litwareinc.com
Pilar.Ackerman@litwareinc.com
```

<span data-ttu-id="666e7-143">以下命令将根据唯一用户参与的会话的总数列出这些用户：</span><span class="sxs-lookup"><span data-stu-id="666e7-143">This command lists the unique users (based on the total number of sessions that they participated in:</span></span>
  
```
$x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending
```

<span data-ttu-id="666e7-144">这将返回类似于下面的数据：</span><span class="sxs-lookup"><span data-stu-id="666e7-144">That returns data similar to this:</span></span>
  
```
Count    Name
-----    ----
  523    Ken.Myer@litwareinc.com
   63    David.Ahs@litwareinc.com
   29    Pilar.Ackerman@litwareinc.com
   17    Gilead.Amosnino@litwareinc.com
   10    Henrik.Jensen@litwareinc.com
```

<span data-ttu-id="666e7-145">以下命令会将报告的会话限制为将音频作为一种形式包含的会话：</span><span class="sxs-lookup"><span data-stu-id="666e7-145">This command limits the reported sessions to those that included audio as a modality:</span></span>
  
```
$x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending
```

<span data-ttu-id="666e7-146">如果将鼠标悬停在报告上显示的任何诊断 ID 上，则会出现一个描述该 ID 的工具提示。</span><span class="sxs-lookup"><span data-stu-id="666e7-146">If you hold your mouse over any Diagnostic ID shown on the report, a tooltip will appear describing that ID.</span></span>
  
## <a name="filters"></a><span data-ttu-id="666e7-147">筛选器</span><span class="sxs-lookup"><span data-stu-id="666e7-147">Filters</span></span>

<span data-ttu-id="666e7-p110">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，用户活动报告允许您基于活动类型（即对等会话还是会议会话）或用户的 SIP 地址（允许您查看一个用户的活动）筛选返回的数据。您还可以选择数据的分组方式。在此示例中，将按小时、日、周或月对使用情况进行分组。</span><span class="sxs-lookup"><span data-stu-id="666e7-p110">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the User Activity Report enables you to filter the returned data based on such things as activity type (that is, peer-to-peer sessions or conferencing sessions) or by the user's SIP address (allowing you to view the activities for one user). You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>
  
<span data-ttu-id="666e7-152">下表列出了可用于用户活动报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="666e7-152">The following table lists the filters that you can use with the User Activity Report.</span></span>
  
<span data-ttu-id="666e7-153">**用户活动报告筛选器**</span><span class="sxs-lookup"><span data-stu-id="666e7-153">**User activity report filters**</span></span>

|<span data-ttu-id="666e7-154">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="666e7-154">**Name**</span></span>|<span data-ttu-id="666e7-155">**说明**</span><span class="sxs-lookup"><span data-stu-id="666e7-155">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="666e7-156">**从**</span><span class="sxs-lookup"><span data-stu-id="666e7-156">**From**</span></span> <br/> |<span data-ttu-id="666e7-p111">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="666e7-p111">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span>  <br/> <span data-ttu-id="666e7-159">7/17/12015 13:00</span><span class="sxs-lookup"><span data-stu-id="666e7-159">7/17/12015 1:00 PM</span></span>  <br/> <span data-ttu-id="666e7-p112">如果您未输入开始时间，该报告会自动将将某个特定日期的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="666e7-p112">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="666e7-162">7/17/12015</span><span class="sxs-lookup"><span data-stu-id="666e7-162">7/17/12015</span></span>  <br/> <span data-ttu-id="666e7-163">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="666e7-163">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="666e7-164">2015/7/13</span><span class="sxs-lookup"><span data-stu-id="666e7-164">7/13/2015</span></span>  <br/> <span data-ttu-id="666e7-165">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="666e7-165">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="666e7-166">**到**</span><span class="sxs-lookup"><span data-stu-id="666e7-166">**To**</span></span> <br/> |<span data-ttu-id="666e7-p113">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="666e7-p113">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span>  <br/> <span data-ttu-id="666e7-169">7/17/12015 13:00</span><span class="sxs-lookup"><span data-stu-id="666e7-169">7/17/12015 1:00 PM</span></span>  <br/> <span data-ttu-id="666e7-p114">如果您未输入结束时间，该报告会自动将某个特定日期的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="666e7-p114">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="666e7-172">7/17/12015</span><span class="sxs-lookup"><span data-stu-id="666e7-172">7/17/12015</span></span>  <br/> <span data-ttu-id="666e7-173">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="666e7-173">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="666e7-174">2015/7/13</span><span class="sxs-lookup"><span data-stu-id="666e7-174">7/13/2015</span></span>  <br/> <span data-ttu-id="666e7-175">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="666e7-175">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="666e7-176">**活动类型**</span><span class="sxs-lookup"><span data-stu-id="666e7-176">**Activity type**</span></span> <br/> | <span data-ttu-id="666e7-p115">活动的类型。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="666e7-p115">Type of activity. Select one of the following:</span></span> <br/>  <span data-ttu-id="666e7-179">[所有]</span><span class="sxs-lookup"><span data-stu-id="666e7-179">[All]</span></span> <br/>  <span data-ttu-id="666e7-180">对等</span><span class="sxs-lookup"><span data-stu-id="666e7-180">Peer-to-peer</span></span> <br/>  <span data-ttu-id="666e7-181">会议</span><span class="sxs-lookup"><span data-stu-id="666e7-181">Conference</span></span> <br/> |
|<span data-ttu-id="666e7-182">**形式**</span><span class="sxs-lookup"><span data-stu-id="666e7-182">**Modality**</span></span> <br/> |<span data-ttu-id="666e7-183">可用的形式取决于选择的“活动类型”。</span><span class="sxs-lookup"><span data-stu-id="666e7-183">The Modality available to you varies depending on the select Activity Type.</span></span> <span data-ttu-id="666e7-184">如果活动类型是对等的则可选择即时消息;文件传输;应用程序共享;声音。或作为模态的视频。</span><span class="sxs-lookup"><span data-stu-id="666e7-184">If the Activity Type is Peer-to-Peer, you can select IM; File Transfer; Application Sharing; Voice; or Video as the modality.</span></span>  <br/> <span data-ttu-id="666e7-185">如果“活动类型”是“会议”，您可以选择“IM 电话会议”、“Web 会议”、“应用程序共享”、“语音/视频会议”或“电话会议”。</span><span class="sxs-lookup"><span data-stu-id="666e7-185">If the Activity Type is Conference, you can select IM Phone conference; Web conference; Application Sharing; Voice/Video conference; or Telephony conference.</span></span>  <br/> |
|<span data-ttu-id="666e7-186">**会话类别**</span><span class="sxs-lookup"><span data-stu-id="666e7-186">**Session category**</span></span> <br/> | <span data-ttu-id="666e7-p117">指示相应活动已成功还是失败。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="666e7-p117">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span> <br/>  <span data-ttu-id="666e7-189">[所有]</span><span class="sxs-lookup"><span data-stu-id="666e7-189">[All]</span></span> <br/>  <span data-ttu-id="666e7-190">成功</span><span class="sxs-lookup"><span data-stu-id="666e7-190">Success</span></span> <br/>  <span data-ttu-id="666e7-191">预期失败</span><span class="sxs-lookup"><span data-stu-id="666e7-191">Expected failure</span></span> <br/>  <span data-ttu-id="666e7-192">意外失败</span><span class="sxs-lookup"><span data-stu-id="666e7-192">Unexpected failure</span></span> <br/>  <span data-ttu-id="666e7-p118">“预期失败”是指预计会出现的失败情况；例如，如果用户将其状态设置为“请勿打扰”，那么向该用户发出的任何呼叫应该都会失败。“意外失败”是指在本该正常运行的系统中出现的失败情况。例如，如果呼叫者处于呼叫等待状态，则不应该终止呼叫。如果终止，则会被标记为意外失败。</span><span class="sxs-lookup"><span data-stu-id="666e7-p118">An "expected failure" is a failure that is expected to happen; for example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail. An "unexpected failure" is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span> <br/> |
|<span data-ttu-id="666e7-197">**用户 URI 前缀**</span><span class="sxs-lookup"><span data-stu-id="666e7-197">**User URI prefix**</span></span> <br/> |<span data-ttu-id="666e7-p119">用户的 SIP 地址。要仅查看用户 Ken Myer 的记录，您需要输入 Ken Myer 的 SIP 地址。例如：</span><span class="sxs-lookup"><span data-stu-id="666e7-p119">SIP address for the user. To view records only for the user Ken Myer you need to enter Ken Myer's SIP address. For example:</span></span>  <br/> <span data-ttu-id="666e7-201">sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="666e7-201">sip:kenmyer@litwareinc.com</span></span>  <br/> |
   
## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="666e7-202">对等会话的指标</span><span class="sxs-lookup"><span data-stu-id="666e7-202">Metrics for peer-to-peer sessions</span></span>

<span data-ttu-id="666e7-203">下表列出了对等会话（即，只涉及两个参与者的会话）的用户活动报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="666e7-203">The following table lists the information provided in the User Activity Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>
  
<span data-ttu-id="666e7-204">**对等会话的指标**</span><span class="sxs-lookup"><span data-stu-id="666e7-204">**Metrics for peer-to-peer sessions**</span></span>

|<span data-ttu-id="666e7-205">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="666e7-205">**Name**</span></span>|<span data-ttu-id="666e7-206">**可以在此项上进行排序？**</span><span class="sxs-lookup"><span data-stu-id="666e7-206">**Can you sort on this item?**</span></span>|<span data-ttu-id="666e7-207">**说明**</span><span class="sxs-lookup"><span data-stu-id="666e7-207">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="666e7-208">**详情**</span><span class="sxs-lookup"><span data-stu-id="666e7-208">**Detail**</span></span> <br/> |<span data-ttu-id="666e7-209">否</span><span class="sxs-lookup"><span data-stu-id="666e7-209">No</span></span>  <br/> |<span data-ttu-id="666e7-210">单击此项时，报告将显示所选会话的对等会话详细信息报告。</span><span class="sxs-lookup"><span data-stu-id="666e7-210">When you click this item, the report shows you the Peer-to-Peer Session Detail Report for the selected session.</span></span>  <br/> |
|<span data-ttu-id="666e7-211">**来源用户**</span><span class="sxs-lookup"><span data-stu-id="666e7-211">**From user**</span></span> <br/> |<span data-ttu-id="666e7-212">是</span><span class="sxs-lookup"><span data-stu-id="666e7-212">Yes</span></span>  <br/> |<span data-ttu-id="666e7-213">发起对等会话的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="666e7-213">SIP address of the user who initiated the peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="666e7-214">**目标用户**</span><span class="sxs-lookup"><span data-stu-id="666e7-214">**To user**</span></span> <br/> |<span data-ttu-id="666e7-215">是</span><span class="sxs-lookup"><span data-stu-id="666e7-215">Yes</span></span>  <br/> |<span data-ttu-id="666e7-216">加入对等会话的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="666e7-216">SIP address of the user who joined the peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="666e7-217">**形式**</span><span class="sxs-lookup"><span data-stu-id="666e7-217">**Modalities**</span></span> <br/> |<span data-ttu-id="666e7-218">是</span><span class="sxs-lookup"><span data-stu-id="666e7-218">Yes</span></span>  <br/> |<span data-ttu-id="666e7-p120">会话中使用的通信类型。例如，IM、音频或文件传输。</span><span class="sxs-lookup"><span data-stu-id="666e7-p120">Type of communication used in the session. For example, IM, audio, or file transfer.</span></span>  <br/> |
|<span data-ttu-id="666e7-221">**邀请时间**</span><span class="sxs-lookup"><span data-stu-id="666e7-221">**Invite time**</span></span> <br/> |<span data-ttu-id="666e7-222">是</span><span class="sxs-lookup"><span data-stu-id="666e7-222">Yes</span></span>  <br/> |<span data-ttu-id="666e7-223">发送加入对等会话的初始邀请的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="666e7-223">Date and time the initial invitation to join the peer-to-peer session was sent.</span></span>  <br/> |
|<span data-ttu-id="666e7-224">**响应时间**</span><span class="sxs-lookup"><span data-stu-id="666e7-224">**Response time**</span></span> <br/> |<span data-ttu-id="666e7-225">是</span><span class="sxs-lookup"><span data-stu-id="666e7-225">Yes</span></span>  <br/> |<span data-ttu-id="666e7-226">“目标”用户接受会话邀请的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="666e7-226">Date and time that the "To" user accepted the session invitation.</span></span>  <br/> |
|<span data-ttu-id="666e7-227">**结束时间**</span><span class="sxs-lookup"><span data-stu-id="666e7-227">**End time**</span></span> <br/> |<span data-ttu-id="666e7-228">是</span><span class="sxs-lookup"><span data-stu-id="666e7-228">Yes</span></span>  <br/> |<span data-ttu-id="666e7-229">对等会话结束的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="666e7-229">Date and time the peer-to-peer session ended.</span></span>  <br/> |
|<span data-ttu-id="666e7-230">**诊断 ID**</span><span class="sxs-lookup"><span data-stu-id="666e7-230">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="666e7-231">是</span><span class="sxs-lookup"><span data-stu-id="666e7-231">Yes</span></span>  <br/> |<span data-ttu-id="666e7-p121">附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。诊断标头是可选的（SIP 会话可以不包含这些标头），并且只对遇到此类问题的会话报告诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="666e7-p121">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span>  <br/> |
   
## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="666e7-234">会议会话的指标</span><span class="sxs-lookup"><span data-stu-id="666e7-234">Metrics for conferencing sessions</span></span>

<span data-ttu-id="666e7-235">下表列出了会议会话（即，涉及三个或更多参与者的会话）的用户活动报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="666e7-235">The following table lists the information provided in the User Activity Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>
  
<span data-ttu-id="666e7-236">**会议会话的度量标准**</span><span class="sxs-lookup"><span data-stu-id="666e7-236">**Metrics for conferencing sessions**</span></span>

|<span data-ttu-id="666e7-237">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="666e7-237">**Name**</span></span>|<span data-ttu-id="666e7-238">**可以在此项上进行排序？**</span><span class="sxs-lookup"><span data-stu-id="666e7-238">**Can you sort on this item?**</span></span>|<span data-ttu-id="666e7-239">**说明**</span><span class="sxs-lookup"><span data-stu-id="666e7-239">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="666e7-240">**会议 URI**</span><span class="sxs-lookup"><span data-stu-id="666e7-240">**Conference URI**</span></span> <br/> |<span data-ttu-id="666e7-241">是</span><span class="sxs-lookup"><span data-stu-id="666e7-241">Yes</span></span>  <br/> |<span data-ttu-id="666e7-p122">唯一会议标识符。单击此项时，报告将显示所选会话的会议详细信息报告。展开此项时，报告将显示有关会议参与者的信息。有关详细信息，请参阅本主题后面的“会议参与者的指标”一节。</span><span class="sxs-lookup"><span data-stu-id="666e7-p122">Unique conference identifier. When you click this item, the report shows you the Conference Detail Report for the selected session. When you expand this item, the report shows you information about the conference participants. For details, see the "Metrics for Conference Participants" section later in this topic.</span></span>  <br/> |
|<span data-ttu-id="666e7-246">**组织者**</span><span class="sxs-lookup"><span data-stu-id="666e7-246">**Organizer**</span></span> <br/> |<span data-ttu-id="666e7-247">是</span><span class="sxs-lookup"><span data-stu-id="666e7-247">Yes</span></span>  <br/> |<span data-ttu-id="666e7-248">组织会议的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="666e7-248">SIP address of the user who organized the conference.</span></span>  <br/> |
|<span data-ttu-id="666e7-249">**池**</span><span class="sxs-lookup"><span data-stu-id="666e7-249">**Pool**</span></span> <br/> |<span data-ttu-id="666e7-250">是</span><span class="sxs-lookup"><span data-stu-id="666e7-250">Yes</span></span>  <br/> |<span data-ttu-id="666e7-251">会议中使用的边缘服务器（如果有）的名称。</span><span class="sxs-lookup"><span data-stu-id="666e7-251">Name of the Edge Server (if any) used in the conference.</span></span>  <br/> |
|<span data-ttu-id="666e7-252">**开始时间**</span><span class="sxs-lookup"><span data-stu-id="666e7-252">**Start time**</span></span> <br/> |<span data-ttu-id="666e7-253">是</span><span class="sxs-lookup"><span data-stu-id="666e7-253">Yes</span></span>  <br/> |<span data-ttu-id="666e7-254">会议开始的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="666e7-254">Date and time that the conference began.</span></span>  <br/> |
|<span data-ttu-id="666e7-255">**结束时间**</span><span class="sxs-lookup"><span data-stu-id="666e7-255">**End time**</span></span> <br/> |<span data-ttu-id="666e7-256">是</span><span class="sxs-lookup"><span data-stu-id="666e7-256">Yes</span></span>  <br/> |<span data-ttu-id="666e7-257">会议结束的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="666e7-257">Date and time that the conference ended.</span></span>  <br/> |
   
## <a name="metrics-for-conference-participants"></a><span data-ttu-id="666e7-258">会议参与者的指标</span><span class="sxs-lookup"><span data-stu-id="666e7-258">Metrics for conference participants</span></span>

<span data-ttu-id="666e7-259">下表列出了会议的每个参与者的用户活动报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="666e7-259">The following table lists the information provided in the User Activity Report provides for each participant in a conference.</span></span>
  
<span data-ttu-id="666e7-260">**会议参与者的度量标准**</span><span class="sxs-lookup"><span data-stu-id="666e7-260">**Metrics for conference participants**</span></span>

|<span data-ttu-id="666e7-261">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="666e7-261">**Name**</span></span>|<span data-ttu-id="666e7-262">**可以在此项上进行排序？**</span><span class="sxs-lookup"><span data-stu-id="666e7-262">**Can you sort on this item?**</span></span>|<span data-ttu-id="666e7-263">**说明**</span><span class="sxs-lookup"><span data-stu-id="666e7-263">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="666e7-264">**角色**</span><span class="sxs-lookup"><span data-stu-id="666e7-264">**Role**</span></span> <br/> |<span data-ttu-id="666e7-265">否</span><span class="sxs-lookup"><span data-stu-id="666e7-265">No</span></span>  <br/> |<span data-ttu-id="666e7-266">用户的会议角色（例如，演示者）。</span><span class="sxs-lookup"><span data-stu-id="666e7-266">Conference role (for example, Presenter) for the user.</span></span>  <br/> |
|<span data-ttu-id="666e7-267">**参与者**</span><span class="sxs-lookup"><span data-stu-id="666e7-267">**Participant**</span></span> <br/> |<span data-ttu-id="666e7-268">否</span><span class="sxs-lookup"><span data-stu-id="666e7-268">No</span></span>  <br/> |<span data-ttu-id="666e7-269">用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="666e7-269">SIP address of the user.</span></span>  <br/> |
|<span data-ttu-id="666e7-270">**连接**</span><span class="sxs-lookup"><span data-stu-id="666e7-270">**Connectivity**</span></span> <br/> |<span data-ttu-id="666e7-271">否</span><span class="sxs-lookup"><span data-stu-id="666e7-271">No</span></span>  <br/> |<span data-ttu-id="666e7-p123">网络连接类型。例如，“来自内部”表示内部连接，“来自 PSTN”表示拨入用户。</span><span class="sxs-lookup"><span data-stu-id="666e7-p123">Network connection type. For example "From Internal" for internal connection or "From PSTN" for dial-in users.</span></span>  <br/> |
|<span data-ttu-id="666e7-274">**加入时间**</span><span class="sxs-lookup"><span data-stu-id="666e7-274">**Join time**</span></span> <br/> |<span data-ttu-id="666e7-275">否</span><span class="sxs-lookup"><span data-stu-id="666e7-275">No</span></span>  <br/> |<span data-ttu-id="666e7-276">用户加入会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="666e7-276">Date and time that the user joined the conference.</span></span>  <br/> |
|<span data-ttu-id="666e7-277">**离开时间**</span><span class="sxs-lookup"><span data-stu-id="666e7-277">**Leave time**</span></span> <br/> |<span data-ttu-id="666e7-278">否</span><span class="sxs-lookup"><span data-stu-id="666e7-278">No</span></span>  <br/> |<span data-ttu-id="666e7-279">用户离开会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="666e7-279">Date and time that the user left the conference.</span></span>  <br/> |
|<span data-ttu-id="666e7-280">**诊断 ID**</span><span class="sxs-lookup"><span data-stu-id="666e7-280">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="666e7-281">否</span><span class="sxs-lookup"><span data-stu-id="666e7-281">No</span></span>  <br/> |<span data-ttu-id="666e7-p124">附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。诊断标头是可选的（SIP 会话可以不包含这些标头），并且只对遇到此类问题的会话报告诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="666e7-p124">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span>  <br/> |
   

