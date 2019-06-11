---
title: 'Lync Server 2013: 用户活动报表'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User Activity Report
ms:assetid: 3aa6fef2-ea02-4f0f-93e8-fa2e0a953d79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558638(v=OCS.15)
ms:contentKeyID: 48183862
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04a7dd3dd1f2a061a327cc2a0bac79ee05f21d82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-activity-report-in-lync-server-2013"></a><span data-ttu-id="47da8-102">Lync Server 2013 中的用户活动报表</span><span class="sxs-lookup"><span data-stu-id="47da8-102">User Activity Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47da8-103">_**主题上次修改时间:** 2015-02-27_</span><span class="sxs-lookup"><span data-stu-id="47da8-103">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="47da8-p101">用户活动报告提供了由用户在给定时间段内执行的对等会话和会议会话的详细列表。与很多监控报告不同，用户活动报告会将每个呼叫与单个用户绑定。例如，对等会话指定发起呼叫（源用户）的人员以及被呼叫（目标用户）的人员的 SIP URI。如果展开会议的信息，则会看到所有会议参与者及其在该会议中担任的角色的列表。</span><span class="sxs-lookup"><span data-stu-id="47da8-p101">The User Activity Report provides a detailed list of the peer-to-peer and conferencing sessions carried out by your users in a given time period. Unlike many of the Monitoring Reports, the User Activity Report ties each call to individual users. For example, peer-to-peer sessions specify the SIP URIs of the person who initiated the call (the From user) and the person who was being called (the To user). If you expand the information for a conference, you'll see a list of all the conference participants and the role they held for that conference.</span></span>

<span data-ttu-id="47da8-p102">用户活动报告有时候称为“技术支持”报告。这是因为该报告通常由技术支持人员用于检索特定用户的会话信息。您可以筛选来自或发往单个用户的呼叫，只需在“用户 URI”前缀框中键入该用户的 SIP URI 即可。</span><span class="sxs-lookup"><span data-stu-id="47da8-p102">The User Activity Report is sometimes referred to as the "help desk" report. That's because the report is often used by help desk personnel to retrieve session information for a specific user. You can filter for calls made to or made by an individual user simply by typing the user's SIP URI in the User URI prefix box.</span></span>

<span data-ttu-id="47da8-111">如果执行此操作, 则用户活动报表将返回其 SIP URI 以指定字符串开头的任何用户的信息。</span><span class="sxs-lookup"><span data-stu-id="47da8-111">If you do this, the User Activity Report will return information for any user whose SIP URI begins with the specified string.</span></span> <span data-ttu-id="47da8-112">例如，如果您在 URI 框中键入 **ken**，则用户活动报告将查找 **Ken**.Myer@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="47da8-112">For example, if you type **ken** in the URI box, the User Activity Report will locate **Ken**.Myer@litwareinc.com.</span></span> <span data-ttu-id="47da8-113">但是，它还会查找以下用户：</span><span class="sxs-lookup"><span data-stu-id="47da8-113">However, it will also locate these users:</span></span>

  - <span data-ttu-id="47da8-114">**ken**azi@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="47da8-114">**ken**azi@litwareinc.com</span></span>

  - <span data-ttu-id="47da8-115">**ken**burg@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="47da8-115">**ken**burg@litwareinc.com</span></span>

  - <span data-ttu-id="47da8-116">**Ken**.Sanchez@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="47da8-116">**Ken**.Sanchez@litwareinc.com</span></span>

  - <span data-ttu-id="47da8-117">**Ken**nedy@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="47da8-117">**Ken**nedy@litwareinc.com</span></span>

<span data-ttu-id="47da8-p104">为确保仅返回 Ken Myer 的信息，请在搜索框中键入其完整的 URI (Ken.Myer@litwareinc.com)，或者至少键入 Ken 的 URI 的类型以将其与您所在组织中的其他用户区分开来。例如：</span><span class="sxs-lookup"><span data-stu-id="47da8-p104">To ensure that information only for Ken Myer is returned, either type his full URI (Ken.Myer@litwareinc.com) in the search box or at least enough type of Ken’s URI to uniquely distinguish him from other users in your organization. For example:</span></span>

<span data-ttu-id="47da8-120">Ken.my</span><span class="sxs-lookup"><span data-stu-id="47da8-120">Ken.my</span></span>

<div>

## <a name="to-access-the-user-activity-report"></a><span data-ttu-id="47da8-121">访问用户活动报告</span><span class="sxs-lookup"><span data-stu-id="47da8-121">To access the user activity report</span></span>

<span data-ttu-id="47da8-122">用户活动报告是从“监控报告”主页访问的。</span><span class="sxs-lookup"><span data-stu-id="47da8-122">The User Activity Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="47da8-123">您也可以通过单击[Lync Server 2013 中的 "IP 电话清点" 报表](lync-server-2013-ip-phone-inventory-report.md)上的用户 URI 指标来访问用户活动报表。</span><span class="sxs-lookup"><span data-stu-id="47da8-123">You can also reach the User Activity Report by clicking the User URI metric on the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md).</span></span> <span data-ttu-id="47da8-124">在用户活动报告中，单击“会议 URI”（针对会议）会将您转到会议详细信息报告。</span><span class="sxs-lookup"><span data-stu-id="47da8-124">From within the User Activity Report, clicking the Conference URI (for a conference) takes you to the Conference Detail Report.</span></span> <span data-ttu-id="47da8-125">同样, 单击对等呼叫的详细指标将转到[Lync Server 2013 中的对等会话详细信息报告](lync-server-2013-peer-to-peer-session-detail-report.md)。</span><span class="sxs-lookup"><span data-stu-id="47da8-125">Similarly, clicking the Detail metric for a peer-to-peer call takes you to the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-activity-report"></a><span data-ttu-id="47da8-126">充分利用用户活动报告</span><span class="sxs-lookup"><span data-stu-id="47da8-126">Making the best use of the user activity report</span></span>

<span data-ttu-id="47da8-127">尽管用户活动报告中有很多有用的信息，但这些信息有时候可能很难找到。</span><span class="sxs-lookup"><span data-stu-id="47da8-127">Although there is a lot of good information in the User Activity Report, that information can sometimes be difficult to locate.</span></span> <span data-ttu-id="47da8-128">例如, 在指定期间内, 你的组织中发生的所有用户活动均包括在用户活动报表中;这意味着, 隐藏在报表内是有关哪些用户在某些方面实际使用过 Microsoft Lync Server 2013 的信息。</span><span class="sxs-lookup"><span data-stu-id="47da8-128">For example, all the user activity that takes place in your organization during a specified period is included in the User Activity Report; that means that, buried, within the report is information about which users actually used Microsoft Lync Server 2013 in some way.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="47da8-129">从技术上讲, 某些用户活动可能会 unrecorded: 尽管 Lync Server 努力保留有关所有电话呼叫的信息, 但如果没有有关该调用的信息正在写入数据库, 则可能会进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="47da8-129">Technically, it’s possible that some user activity might go unrecorded: while Lync Server strives to keep information about all phone calls it's possible that a call could have been made without the information about that call being written to the database.</span></span> <span data-ttu-id="47da8-130">Lync Server 旨在提供极其准确但不一定完全了解 Lync Server 2013 的使用方法。</span><span class="sxs-lookup"><span data-stu-id="47da8-130">Lync Server is designed to give an extremely accurate but not necessarily perfect look at how Lync Server 2013 is being used.</span></span> <span data-ttu-id="47da8-131">(不能保证所有通话的 100% 的记录都说明为什么不应将 Lync 服务器监视用作帐单系统。)</span><span class="sxs-lookup"><span data-stu-id="47da8-131">(The fact that there is no guarantee that 100% of all calls are recorded explains why Lync Server monitoring should not be used as a billing system.)</span></span><BR><span data-ttu-id="47da8-132">第二, 监视报告报告最多只能显示1000条记录。</span><span class="sxs-lookup"><span data-stu-id="47da8-132">Second, a Monitoring Report report can only display, at most, 1,000 records.</span></span> <span data-ttu-id="47da8-133">根据您具有的用户活动的数量以及您工作的时间段，这意味着您的查询可能无法返回数据库中实际存储的所有数据。</span><span class="sxs-lookup"><span data-stu-id="47da8-133">Depending on the amount of user activity you have, and depending on the time period you are working with, that means your query might not return all the data actually stored in the database.</span></span>



</div>

  - <span data-ttu-id="47da8-134">哪些用户在此时间段内实际上使用了系统？</span><span class="sxs-lookup"><span data-stu-id="47da8-134">Which users actually used the system during this time period?</span></span>

  - <span data-ttu-id="47da8-135">我的哪些用户在此时间段内最活跃？</span><span class="sxs-lookup"><span data-stu-id="47da8-135">Which of my users were the most active during this time period?</span></span>

  - <span data-ttu-id="47da8-136">发出电话呼叫最多的用户是否也是参与即时消息会话最多的用户？</span><span class="sxs-lookup"><span data-stu-id="47da8-136">Are the users who make the most phone calls also the users who participate in the most instant messaging sessions?</span></span>

<span data-ttu-id="47da8-137">如果需要回答此类问题, 您可以将监视报告检索到的数据导出到 Excel 电子表格。</span><span class="sxs-lookup"><span data-stu-id="47da8-137">If you need to answer questions like this, you can export the data retrieved by the Monitoring Reports to an Excel spreadsheet.</span></span> <span data-ttu-id="47da8-138">然后, 使用该电子表格和/或逗号分隔的值文件以用户活动报告的方式分析数据。</span><span class="sxs-lookup"><span data-stu-id="47da8-138">You then use that spreadsheet and/or a comma-separated values file to analyze the data in ways that the User Activity Report.</span></span> <span data-ttu-id="47da8-139">例如, 假设您已将报告数据导出到 Excel, 然后导出到逗号分隔的值文件。</span><span class="sxs-lookup"><span data-stu-id="47da8-139">For example, suppose you have exported the report data to Excel and then to a comma-separated values file.</span></span> <span data-ttu-id="47da8-140">此时, 您可以从导入数据。CSV 文件到 Windows PowerShell, 方法是使用如下所示的命令:</span><span class="sxs-lookup"><span data-stu-id="47da8-140">At that point, you can import the data from the .CSV file to Windows PowerShell by using a command similar to this:</span></span>

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

<span data-ttu-id="47da8-141">导入数据后, 您可以使用简单的 Windows PowerShell 命令来帮助解答您的问题。</span><span class="sxs-lookup"><span data-stu-id="47da8-141">After the data has been imported you can then use simple Windows PowerShell commands to help answer your questions.</span></span> <span data-ttu-id="47da8-142">例如，以下命令将返回至少在一个会话中充当“源用户”的唯一用户的列表：</span><span class="sxs-lookup"><span data-stu-id="47da8-142">For example, this command returns a list of unique users who served as the "From user" in at least one session:</span></span>

    $x | Group-Object "From user" | Select Name | Sort-Object Name

<span data-ttu-id="47da8-143">换言之：</span><span class="sxs-lookup"><span data-stu-id="47da8-143">In other words:</span></span>

    Name
    ----
    David.Ahs@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Ken.Myer@litwareinc.com
    Pilar.Ackerman@litwareinc.com

<span data-ttu-id="47da8-144">以下命令将根据唯一用户参与的会话的总数列出这些用户：</span><span class="sxs-lookup"><span data-stu-id="47da8-144">This command lists the unique users (based on the total number of sessions that they participated in:</span></span>

    $x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="47da8-145">这将返回类似于下面的数据：</span><span class="sxs-lookup"><span data-stu-id="47da8-145">That returns data similar to this:</span></span>

    Count    Name
    -----    ----
      523    Ken.Myer@litwareinc.com
       63    David.Ahs@litwareinc.com
       29    Pilar.Ackerman@litwareinc.com
       17    Gilead.Amosnino@litwareinc.com
       10    Henrik.Jensen@litwareinc.com

<span data-ttu-id="47da8-146">以下命令会将报告的会话限制为将音频作为一种形式包含的会话：</span><span class="sxs-lookup"><span data-stu-id="47da8-146">This command limits the reported sessions to those that included audio as a modality:</span></span>

    $x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="47da8-147">如果将鼠标悬停在报告上显示的任何诊断 ID 上，则会出现一个描述该 ID 的工具提示。</span><span class="sxs-lookup"><span data-stu-id="47da8-147">If you hold your mouse over any Diagnostic ID shown on the report, a tooltip will appear describing that ID.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="47da8-148">筛选器</span><span class="sxs-lookup"><span data-stu-id="47da8-148">Filters</span></span>

<span data-ttu-id="47da8-p111">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，用户活动报告允许您基于活动类型（即对等会话还是会议会话）或用户的 SIP 地址（允许您查看一个用户的活动）筛选返回的数据。您还可以选择数据的分组方式。在此示例中，将按小时、日、周或月对使用情况进行分组。</span><span class="sxs-lookup"><span data-stu-id="47da8-p111">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the User Activity Report enables you to filter the returned data based on such things as activity type (that is, peer-to-peer sessions or conferencing sessions) or by the user's SIP address (allowing you to view the activities for one user). You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="47da8-153">下表列出了可用于用户活动报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="47da8-153">The following table lists the filters that you can use with the User Activity Report.</span></span>

### <a name="user-activity-report-filters"></a><span data-ttu-id="47da8-154">用户活动报告筛选器</span><span class="sxs-lookup"><span data-stu-id="47da8-154">User activity report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47da8-155">名称</span><span class="sxs-lookup"><span data-stu-id="47da8-155">Name</span></span></th>
<th><span data-ttu-id="47da8-156">说明</span><span class="sxs-lookup"><span data-stu-id="47da8-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47da8-157"><strong>从</strong></span><span class="sxs-lookup"><span data-stu-id="47da8-157"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="47da8-p112">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="47da8-p112">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="47da8-160">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="47da8-160">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="47da8-p113">如果您未输入开始时间，该报告会自动将将某个特定日期的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="47da8-p113">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="47da8-163">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="47da8-163">7/17/12012</span></span></p>
<p><span data-ttu-id="47da8-164">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="47da8-164">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="47da8-165">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="47da8-165">7/13/2012</span></span></p>
<p><span data-ttu-id="47da8-166">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="47da8-166">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47da8-167"><strong>到</strong></span><span class="sxs-lookup"><span data-stu-id="47da8-167"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="47da8-p114">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="47da8-p114">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="47da8-170">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="47da8-170">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="47da8-p115">如果您未输入结束时间，该报告会自动将某个特定日期的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="47da8-p115">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="47da8-173">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="47da8-173">7/17/12012</span></span></p>
<p><span data-ttu-id="47da8-174">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="47da8-174">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="47da8-175">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="47da8-175">7/13/2012</span></span></p>
<p><span data-ttu-id="47da8-176">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="47da8-176">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47da8-177"><strong>活动类型</strong></span><span class="sxs-lookup"><span data-stu-id="47da8-177"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="47da8-p116">活动的类型。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="47da8-p116">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="47da8-180">[所有]</span><span class="sxs-lookup"><span data-stu-id="47da8-180">[All]</span></span></p></li>
<li><p><span data-ttu-id="47da8-181">对等</span><span class="sxs-lookup"><span data-stu-id="47da8-181">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="47da8-182">会议</span><span class="sxs-lookup"><span data-stu-id="47da8-182">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47da8-183"><strong>形式</strong></span><span class="sxs-lookup"><span data-stu-id="47da8-183"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="47da8-184">可用的形式取决于选择的“活动类型”。</span><span class="sxs-lookup"><span data-stu-id="47da8-184">The Modality available to you varies depending on the select Activity Type.</span></span> <span data-ttu-id="47da8-185">如果活动类型是对等, 则可以选择 "IM";文件传输;应用程序共享;语态或视频作为模态。</span><span class="sxs-lookup"><span data-stu-id="47da8-185">If the Activity Type is Peer-to-Peer, you can select IM; File Transfer; Application Sharing; Voice; or Video as the modality.</span></span></p>
<p><span data-ttu-id="47da8-186">如果“活动类型”是“会议”，您可以选择“IM 电话会议”、“Web 会议”、“应用程序共享”、“语音/视频会议”或“电话会议”。</span><span class="sxs-lookup"><span data-stu-id="47da8-186">If the Activity Type is Conference, you can select IM Phone conference; Web conference; Application Sharing; Voice/Video conference; or Telephony conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47da8-187"><strong>会话类别</strong></span><span class="sxs-lookup"><span data-stu-id="47da8-187"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="47da8-p118">指示相应活动已成功还是失败。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="47da8-p118">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="47da8-190">[所有]</span><span class="sxs-lookup"><span data-stu-id="47da8-190">[All]</span></span></p></li>
<li><p><span data-ttu-id="47da8-191">成功</span><span class="sxs-lookup"><span data-stu-id="47da8-191">Success</span></span></p></li>
<li><p><span data-ttu-id="47da8-192">预期失败</span><span class="sxs-lookup"><span data-stu-id="47da8-192">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="47da8-193">意外失败</span><span class="sxs-lookup"><span data-stu-id="47da8-193">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="47da8-194">&quot;预期的故障&quot;是预期发生的故障;例如, 如果用户已将其状态设置为 "请勿打扰", 则你可能会对该用户的任何调用失败。</span><span class="sxs-lookup"><span data-stu-id="47da8-194">An &quot;expected failure&quot; is a failure that is expected to happen; for example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="47da8-195">&quot;意外故障&quot;是指出现在其他正常运行的系统中的故障。</span><span class="sxs-lookup"><span data-stu-id="47da8-195">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="47da8-196">例如，如果呼叫者处于呼叫等待状态，则不应该终止呼叫。</span><span class="sxs-lookup"><span data-stu-id="47da8-196">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="47da8-197">如果终止，则会被标记为意外失败。</span><span class="sxs-lookup"><span data-stu-id="47da8-197">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47da8-198"><strong>用户 URI 前缀</strong></span><span class="sxs-lookup"><span data-stu-id="47da8-198"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="47da8-p120">用户的 SIP 地址。要仅查看用户 Ken Myer 的记录，您需要输入 Ken Myer 的 SIP 地址。例如：</span><span class="sxs-lookup"><span data-stu-id="47da8-p120">SIP address for the user. To view records only for the user Ken Myer you need to enter Ken Myer's SIP address. For example:</span></span></p>
<p><span data-ttu-id="47da8-202">sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="47da8-202">sip:kenmyer@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="47da8-203">对等会话的指标</span><span class="sxs-lookup"><span data-stu-id="47da8-203">Metrics for peer-to-peer sessions</span></span>

<span data-ttu-id="47da8-204">下表列出了对等会话（即，只涉及两个参与者的会话）的用户活动报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="47da8-204">The following table lists the information provided in the User Activity Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="47da8-205">对等会话的指标</span><span class="sxs-lookup"><span data-stu-id="47da8-205">Metrics for peer-to-peer sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47da8-206">名称</span><span class="sxs-lookup"><span data-stu-id="47da8-206">Name</span></span></th>
<th><span data-ttu-id="47da8-207">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="47da8-207">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="47da8-208">描述</span><span class="sxs-lookup"><span data-stu-id="47da8-208">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47da8-209"><strong>详情</strong></span><span class="sxs-lookup"><span data-stu-id="47da8-209"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="47da8-210">否</span><span class="sxs-lookup"><span data-stu-id="47da8-210">No</span></span></p></td>
<td><p><span data-ttu-id="47da8-211">单击此项时，报告将显示所选会话的对等会话详细信息报告。</span><span class="sxs-lookup"><span data-stu-id="47da8-211">When you click this item, the report shows you the Peer-to-Peer Session Detail Report for the selected session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47da8-212"><strong>来源用户</strong></span><span class="sxs-lookup"><span data-stu-id="47da8-212"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="47da8-213">是</span><span class="sxs-lookup"><span data-stu-id="47da8-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="47da8-214">发起对等会话的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="47da8-214">SIP address of the user who initiated the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47da8-215"><strong>目标用户</strong></span><span class="sxs-lookup"><span data-stu-id="47da8-215"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="47da8-216">是</span><span class="sxs-lookup"><span data-stu-id="47da8-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="47da8-217">加入对等会话的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="47da8-217">SIP address of the user who joined the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47da8-218"><strong>形式</strong></span><span class="sxs-lookup"><span data-stu-id="47da8-218"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="47da8-219">是</span><span class="sxs-lookup"><span data-stu-id="47da8-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="47da8-p121">会话中使用的通信类型。例如，IM、音频或文件传输。</span><span class="sxs-lookup"><span data-stu-id="47da8-p121">Type of communication used in the session. For example, IM, audio, or file transfer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47da8-222"><strong>邀请时间</strong></span><span class="sxs-lookup"><span data-stu-id="47da8-222"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="47da8-223">是</span><span class="sxs-lookup"><span data-stu-id="47da8-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="47da8-224">发送加入对等会话的初始邀请的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="47da8-224">Date and time the initial invitation to join the peer-to-peer session was sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47da8-225"><strong>响应时间</strong></span><span class="sxs-lookup"><span data-stu-id="47da8-225"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="47da8-226">是</span><span class="sxs-lookup"><span data-stu-id="47da8-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="47da8-227">用户接受会话邀请的日期和时间&quot;&quot;</span><span class="sxs-lookup"><span data-stu-id="47da8-227">Date and time that the &quot;To&quot; user accepted the session invitation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47da8-228"><strong>结束时间</strong></span><span class="sxs-lookup"><span data-stu-id="47da8-228"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="47da8-229">是</span><span class="sxs-lookup"><span data-stu-id="47da8-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="47da8-230">对等会话结束的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="47da8-230">Date and time the peer-to-peer session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47da8-231"><strong>诊断 ID</strong></span><span class="sxs-lookup"><span data-stu-id="47da8-231"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="47da8-232">是</span><span class="sxs-lookup"><span data-stu-id="47da8-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="47da8-p122">附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。诊断标头是可选的（SIP 会话可以不包含这些标头），并且只对遇到此类问题的会话报告诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="47da8-p122">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="47da8-235">会议会话的指标</span><span class="sxs-lookup"><span data-stu-id="47da8-235">Metrics for conferencing sessions</span></span>

<span data-ttu-id="47da8-236">下表列出了会议会话（即，涉及三个或更多参与者的会话）的用户活动报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="47da8-236">The following table lists the information provided in the User Activity Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="47da8-237">会议会话的指标</span><span class="sxs-lookup"><span data-stu-id="47da8-237">Metrics for conferencing sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47da8-238">名称</span><span class="sxs-lookup"><span data-stu-id="47da8-238">Name</span></span></th>
<th><span data-ttu-id="47da8-239">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="47da8-239">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="47da8-240">描述</span><span class="sxs-lookup"><span data-stu-id="47da8-240">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47da8-241"><strong>会议 URI</strong></span><span class="sxs-lookup"><span data-stu-id="47da8-241"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="47da8-242">是</span><span class="sxs-lookup"><span data-stu-id="47da8-242">Yes</span></span></p></td>
<td><p><span data-ttu-id="47da8-243">唯一会议标识符。</span><span class="sxs-lookup"><span data-stu-id="47da8-243">Unique conference identifier.</span></span> <span data-ttu-id="47da8-244">单击此项时，报告将显示所选会话的会议详细信息报告。</span><span class="sxs-lookup"><span data-stu-id="47da8-244">When you click this item, the report shows you the Conference Detail Report for the selected session.</span></span> <span data-ttu-id="47da8-245">展开此项时，报告将显示有关会议参与者的信息。</span><span class="sxs-lookup"><span data-stu-id="47da8-245">When you expand this item, the report shows you information about the conference participants.</span></span> <span data-ttu-id="47da8-246">有关详细信息, 请&quot;参阅本主题后面&quot;部分的会议参与者的 "指标" 部分。</span><span class="sxs-lookup"><span data-stu-id="47da8-246">For details, see the &quot;Metrics for Conference Participants&quot; section later in this topic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47da8-247"><strong>组织者</strong></span><span class="sxs-lookup"><span data-stu-id="47da8-247"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="47da8-248">是</span><span class="sxs-lookup"><span data-stu-id="47da8-248">Yes</span></span></p></td>
<td><p><span data-ttu-id="47da8-249">组织会议的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="47da8-249">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47da8-250"><strong>池</strong></span><span class="sxs-lookup"><span data-stu-id="47da8-250"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="47da8-251">是</span><span class="sxs-lookup"><span data-stu-id="47da8-251">Yes</span></span></p></td>
<td><p><span data-ttu-id="47da8-252">会议中使用的边缘服务器（如果有）的名称。</span><span class="sxs-lookup"><span data-stu-id="47da8-252">Name of the Edge Server (if any) used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47da8-253"><strong>开始时间</strong></span><span class="sxs-lookup"><span data-stu-id="47da8-253"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="47da8-254">是</span><span class="sxs-lookup"><span data-stu-id="47da8-254">Yes</span></span></p></td>
<td><p><span data-ttu-id="47da8-255">会议开始的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="47da8-255">Date and time that the conference began.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47da8-256"><strong>结束时间</strong></span><span class="sxs-lookup"><span data-stu-id="47da8-256"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="47da8-257">是</span><span class="sxs-lookup"><span data-stu-id="47da8-257">Yes</span></span></p></td>
<td><p><span data-ttu-id="47da8-258">会议结束的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="47da8-258">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conference-participants"></a><span data-ttu-id="47da8-259">会议参与者的指标</span><span class="sxs-lookup"><span data-stu-id="47da8-259">Metrics for conference participants</span></span>

<span data-ttu-id="47da8-260">下表列出了会议的每个参与者的用户活动报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="47da8-260">The following table lists the information provided in the User Activity Report provides for each participant in a conference.</span></span>

### <a name="metrics-for-conference-participants"></a><span data-ttu-id="47da8-261">会议参与者的指标</span><span class="sxs-lookup"><span data-stu-id="47da8-261">Metrics for conference participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47da8-262">名称</span><span class="sxs-lookup"><span data-stu-id="47da8-262">Name</span></span></th>
<th><span data-ttu-id="47da8-263">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="47da8-263">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="47da8-264">描述</span><span class="sxs-lookup"><span data-stu-id="47da8-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47da8-265"><strong>角色</strong></span><span class="sxs-lookup"><span data-stu-id="47da8-265"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="47da8-266">否</span><span class="sxs-lookup"><span data-stu-id="47da8-266">No</span></span></p></td>
<td><p><span data-ttu-id="47da8-267">用户的会议角色（例如，演示者）。</span><span class="sxs-lookup"><span data-stu-id="47da8-267">Conference role (for example, Presenter) for the user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47da8-268"><strong>参与者</strong></span><span class="sxs-lookup"><span data-stu-id="47da8-268"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="47da8-269">否</span><span class="sxs-lookup"><span data-stu-id="47da8-269">No</span></span></p></td>
<td><p><span data-ttu-id="47da8-270">用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="47da8-270">SIP address of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47da8-271"><strong>连接</strong></span><span class="sxs-lookup"><span data-stu-id="47da8-271"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="47da8-272">否</span><span class="sxs-lookup"><span data-stu-id="47da8-272">No</span></span></p></td>
<td><p><span data-ttu-id="47da8-273">网络连接类型。</span><span class="sxs-lookup"><span data-stu-id="47da8-273">Network connection type.</span></span> <span data-ttu-id="47da8-274">例如&quot;, 内部连接&quot;内部的内部连接&quot;或来自&quot; PSTN 的电话拨入用户。</span><span class="sxs-lookup"><span data-stu-id="47da8-274">For example &quot;From Internal&quot; for internal connection or &quot;From PSTN&quot; for dial-in users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47da8-275"><strong>加入时间</strong></span><span class="sxs-lookup"><span data-stu-id="47da8-275"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="47da8-276">否</span><span class="sxs-lookup"><span data-stu-id="47da8-276">No</span></span></p></td>
<td><p><span data-ttu-id="47da8-277">用户加入会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="47da8-277">Date and time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47da8-278"><strong>离开时间</strong></span><span class="sxs-lookup"><span data-stu-id="47da8-278"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="47da8-279">否</span><span class="sxs-lookup"><span data-stu-id="47da8-279">No</span></span></p></td>
<td><p><span data-ttu-id="47da8-280">用户离开会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="47da8-280">Date and time that the user left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47da8-281"><strong>诊断 ID</strong></span><span class="sxs-lookup"><span data-stu-id="47da8-281"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="47da8-282">否</span><span class="sxs-lookup"><span data-stu-id="47da8-282">No</span></span></p></td>
<td><p><span data-ttu-id="47da8-p125">附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。诊断标头是可选的（SIP 会话可以不包含这些标头），并且只对遇到此类问题的会话报告诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="47da8-p125">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

