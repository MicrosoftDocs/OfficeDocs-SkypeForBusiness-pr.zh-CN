---
title: Lync Server 2013：呼叫允许控制报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Admission Control Report
ms:assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615043(v=OCS.15)
ms:contentKeyID: 48185933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60a51a27a4aa5c6d0df5970da669bc1c67f068c2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-admission-control-report-in-lync-server-2013"></a><span data-ttu-id="920df-102">Lync Server 2013 中的呼叫允许控制报告</span><span class="sxs-lookup"><span data-stu-id="920df-102">Call Admission Control Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="920df-103">_**上次修改的主题：** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="920df-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="920df-104">呼叫允许控制报告提供有关点对点和由呼叫允许控制设置限制下举行的会议会话的信息。</span><span class="sxs-lookup"><span data-stu-id="920df-104">The Call Admission Control Report provides information about peer-to-peer and conferencing sessions that were conducted under restrictions set in place by Call Admission Control.</span></span> <span data-ttu-id="920df-105">Microsoft Lync Server 2010 中引入的呼叫允许控制为管理员提供了一种基于带宽限制允许（或不允许）通信会话的方法。</span><span class="sxs-lookup"><span data-stu-id="920df-105">Call Admission Control, introduced in Microsoft Lync Server 2010, provides a way for administrators to allow (or not allow) communication sessions based on bandwidth constraints.</span></span> <span data-ttu-id="920df-106">例如，管理员可创建对可用于语音和视频呼叫的带宽量施加限制的策略。</span><span class="sxs-lookup"><span data-stu-id="920df-106">For example, administrators can create policies that impose a limit on the amount of bandwidth available for voice and video calls.</span></span> <span data-ttu-id="920df-107">如果已达到该带宽限制，则可进行新的语音和视频呼叫，直到其中的一个当前呼叫结束并释放所需的网络资源为止。</span><span class="sxs-lookup"><span data-stu-id="920df-107">If that bandwidth limit has been reached, then no new voice or video calls can be placed until one of the current calls has ended and freed up the required network resources.</span></span>

<div>

## <a name="accessing-the-call-admission-control-report"></a><span data-ttu-id="920df-108">访问呼叫允许控制报告</span><span class="sxs-lookup"><span data-stu-id="920df-108">Accessing the Call Admission Control Report</span></span>

<span data-ttu-id="920df-p102">从监控报告主页可访问呼叫允许控制报告。从呼叫允许控制报告可深入到下列任何报告：</span><span class="sxs-lookup"><span data-stu-id="920df-p102">The Call Admission Control Report is accessed from the Monitoring Reports home page. From the Call Admission Control Report you can drill down to either of the following reports:</span></span>

  - <span data-ttu-id="920df-111">会议详细信息报告 - 要访问此报告，请从会议会话单击详细信息指标。</span><span class="sxs-lookup"><span data-stu-id="920df-111">Conference Detail Report – To access this report, click the Details metric from a conference session.</span></span>

  - <span data-ttu-id="920df-112">点对点会话详细信息报告 – 要访问此报告，请单击点对点会话的详细信息指标。</span><span class="sxs-lookup"><span data-stu-id="920df-112">Peer-to-Peer Session Detail Report – To access this report, click the Details metric for a peer-to-peer session.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a><span data-ttu-id="920df-113">充分利用呼叫允许控制报告</span><span class="sxs-lookup"><span data-stu-id="920df-113">Making the Best Use of the Call Admission Control Report</span></span>

<span data-ttu-id="920df-p103">要获得因带宽不足而失败的呼叫的列表，请从呼叫类别下拉列表选择因呼叫允许控制拒绝的呼叫。大多数返回的呼叫将可能具有 5 个诊断 ID 之一：</span><span class="sxs-lookup"><span data-stu-id="920df-p103">To get a list of calls that failed because of insufficient bandwidth, select Calls rejected because of call admission control from the Call category dropdown list. Most of the returned calls will likely have a diagnostic ID of 5:</span></span>

<span data-ttu-id="920df-p104">建立会话带宽不足。尝试 PSTN 重新路由。</span><span class="sxs-lookup"><span data-stu-id="920df-p104">Insufficient bandwidth to establish session. Attempt PSTN re-route.</span></span>

<span data-ttu-id="920df-118">这指示呼叫允许控制限制阻止在 VoIP 网络上进行的呼叫。</span><span class="sxs-lookup"><span data-stu-id="920df-118">That indicates that Call Admission Control limitations were preventing the call from being made on the VoIP network.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="920df-119">筛选器</span><span class="sxs-lookup"><span data-stu-id="920df-119">Filters</span></span>

<span data-ttu-id="920df-p105">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，呼叫允许控制报告允许您按发起呼叫的用户或按被呼叫的用户筛选呼叫。您还可以选择数据的分组方式。在此示例中，将按小时、天、周或月对呼叫进行分组。</span><span class="sxs-lookup"><span data-stu-id="920df-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Call Admission Control Report enables you to filter calls by the user who initiated the call or by the user who was being called. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="920df-124">下表列出了可用于呼叫允许控制报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="920df-124">The following table lists the filters that you can use with the Call Admission Control Report.</span></span>

### <a name="call-admission-control-report-filters"></a><span data-ttu-id="920df-125">呼叫允许控制报告的筛选器</span><span class="sxs-lookup"><span data-stu-id="920df-125">Call Admission Control Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="920df-126">名称</span><span class="sxs-lookup"><span data-stu-id="920df-126">Name</span></span></th>
<th><span data-ttu-id="920df-127">说明</span><span class="sxs-lookup"><span data-stu-id="920df-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="920df-128"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="920df-128"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="920df-p106">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="920df-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="920df-131">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="920df-131">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="920df-p107">如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="920df-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="920df-134">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="920df-134">7/17/12012</span></span></p>
<p><span data-ttu-id="920df-135">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="920df-135">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="920df-136">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="920df-136">7/13/2012</span></span></p>
<p><span data-ttu-id="920df-137">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="920df-137">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="920df-138"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="920df-138"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="920df-p108">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="920df-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="920df-141">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="920df-141">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="920df-p109">如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="920df-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="920df-144">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="920df-144">7/17/12012</span></span></p>
<p><span data-ttu-id="920df-145">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="920df-145">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="920df-146">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="920df-146">7/13/2012</span></span></p>
<p><span data-ttu-id="920df-147">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="920df-147">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="920df-148"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="920df-148"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="920df-p110">注册器池或边缘服务器的完全限定域名 (FQDN)。可以选择单个池，也可以单击“[所有]”<strong></strong>查看所有池的数据。系统根据数据库中的记录自动为您填充该下拉列表。</span><span class="sxs-lookup"><span data-stu-id="920df-p110">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="920df-152"><strong>活动类型</strong></span><span class="sxs-lookup"><span data-stu-id="920df-152"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="920df-p111">活动的类型。选择下列活动之一：</span><span class="sxs-lookup"><span data-stu-id="920df-p111">Type of activity. Select one of the following activities:</span></span></p>
<ul>
<li><p><span data-ttu-id="920df-155">各种</span><span class="sxs-lookup"><span data-stu-id="920df-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="920df-156">对等</span><span class="sxs-lookup"><span data-stu-id="920df-156">Peer-to-Peer</span></span></p></li>
<li><p><span data-ttu-id="920df-157">发布会</span><span class="sxs-lookup"><span data-stu-id="920df-157">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="920df-158"><strong>呼叫类别</strong></span><span class="sxs-lookup"><span data-stu-id="920df-158"><strong>Call category</strong></span></span></p></td>
<td><p><span data-ttu-id="920df-p112">指示对呼叫使用 CAC 的原因。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="920df-p112">Indicates the reason that CAC was used for the call. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="920df-161">各种</span><span class="sxs-lookup"><span data-stu-id="920df-161">[All]</span></span></p></li>
<li><p><span data-ttu-id="920df-162">由于呼叫允许控制，呼叫被拒绝</span><span class="sxs-lookup"><span data-stu-id="920df-162">Call rejected because of call admission control</span></span></p></li>
<li><p><span data-ttu-id="920df-163">由于呼叫允许控制，呼叫通过 PSTN 重新路由</span><span class="sxs-lookup"><span data-stu-id="920df-163">Calls rerouted through PSTN because of call admission control</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="920df-164">点对点会话的指标</span><span class="sxs-lookup"><span data-stu-id="920df-164">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="920df-165">下表列出了点对点会话（即，只涉及两个参与者的会话）的呼叫允许控制报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="920df-165">The following table lists the information provided in the Call Admission Control Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="920df-166">点对点会话的指标</span><span class="sxs-lookup"><span data-stu-id="920df-166">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="920df-167">名称</span><span class="sxs-lookup"><span data-stu-id="920df-167">Name</span></span></th>
<th><span data-ttu-id="920df-168">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="920df-168">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="920df-169">说明</span><span class="sxs-lookup"><span data-stu-id="920df-169">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="920df-170"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="920df-170"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="920df-171">否</span><span class="sxs-lookup"><span data-stu-id="920df-171">No</span></span></p></td>
<td><p><span data-ttu-id="920df-172">单击此项时，报告将显示指定会话的点对点会话详细信息报告。</span><span class="sxs-lookup"><span data-stu-id="920df-172">When you click this item, the report shows you a Peer-to-Peer Session Detail Report for the specified session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="920df-173"><strong>来源用户</strong></span><span class="sxs-lookup"><span data-stu-id="920df-173"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="920df-174">是</span><span class="sxs-lookup"><span data-stu-id="920df-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="920df-175">发起会话的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="920df-175">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="920df-176"><strong>目标用户</strong></span><span class="sxs-lookup"><span data-stu-id="920df-176"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="920df-177">是</span><span class="sxs-lookup"><span data-stu-id="920df-177">Yes</span></span></p></td>
<td><p><span data-ttu-id="920df-178">受邀加入会话的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="920df-178">SIP address of the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="920df-179"><strong>形式</strong></span><span class="sxs-lookup"><span data-stu-id="920df-179"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="920df-180">是</span><span class="sxs-lookup"><span data-stu-id="920df-180">Yes</span></span></p></td>
<td><p><span data-ttu-id="920df-181">会话期间使用的通信形式（如音频和视频）。</span><span class="sxs-lookup"><span data-stu-id="920df-181">Communication modalities (such as audio and video) that were used during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="920df-182"><strong>邀请时间</strong></span><span class="sxs-lookup"><span data-stu-id="920df-182"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="920df-183">是</span><span class="sxs-lookup"><span data-stu-id="920df-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="920df-184">向源用户发送初始会话邀请的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="920df-184">Date and time the initial session invitation was sent to the From user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="920df-185"><strong>响应时间</strong></span><span class="sxs-lookup"><span data-stu-id="920df-185"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="920df-186">是</span><span class="sxs-lookup"><span data-stu-id="920df-186">Yes</span></span></p></td>
<td><p><span data-ttu-id="920df-187">收到邀请接受函的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="920df-187">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="920df-188"><strong>结束时间</strong></span><span class="sxs-lookup"><span data-stu-id="920df-188"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="920df-189">是</span><span class="sxs-lookup"><span data-stu-id="920df-189">Yes</span></span></p></td>
<td><p><span data-ttu-id="920df-190">会话结束的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="920df-190">Date and time that the session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="920df-191"><strong>诊断 ID</strong></span><span class="sxs-lookup"><span data-stu-id="920df-191"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="920df-192">是</span><span class="sxs-lookup"><span data-stu-id="920df-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="920df-p113">附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。诊断标头是可选的（SIP 会话可以不包含这些标头），并且只对遇到此类问题的会话报告诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="920df-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="920df-195">会议会话的指标</span><span class="sxs-lookup"><span data-stu-id="920df-195">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="920df-196">下表列出了会议会话（即，涉及三个或更多参与者的会话）的呼叫允许控制报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="920df-196">The following table lists the information provided in the Call Admission Control Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="920df-197">会议会话的指标</span><span class="sxs-lookup"><span data-stu-id="920df-197">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="920df-198">名称</span><span class="sxs-lookup"><span data-stu-id="920df-198">Name</span></span></th>
<th><span data-ttu-id="920df-199">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="920df-199">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="920df-200">说明</span><span class="sxs-lookup"><span data-stu-id="920df-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="920df-201"><strong>会议 URI</strong></span><span class="sxs-lookup"><span data-stu-id="920df-201"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="920df-202">是</span><span class="sxs-lookup"><span data-stu-id="920df-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="920df-p114">会议的唯一标识符。单击此项时，报告将显示单个会议参与者。</span><span class="sxs-lookup"><span data-stu-id="920df-p114">Unique identifier for the conference. When you click this item, the report shows the individual conference participants.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="920df-205"><strong>Organizer</strong></span><span class="sxs-lookup"><span data-stu-id="920df-205"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="920df-206">是</span><span class="sxs-lookup"><span data-stu-id="920df-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="920df-207">组织会议的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="920df-207">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="920df-208"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="920df-208"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="920df-209">是</span><span class="sxs-lookup"><span data-stu-id="920df-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="920df-210">会议中使用的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="920df-210">Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="920df-211"><strong>开始时间</strong></span><span class="sxs-lookup"><span data-stu-id="920df-211"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="920df-212">是</span><span class="sxs-lookup"><span data-stu-id="920df-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="920df-213">会议开始的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="920df-213">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="920df-214"><strong>结束时间</strong></span><span class="sxs-lookup"><span data-stu-id="920df-214"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="920df-215">是</span><span class="sxs-lookup"><span data-stu-id="920df-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="920df-216">会议结束的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="920df-216">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="920df-217">单个会议参与者的指标</span><span class="sxs-lookup"><span data-stu-id="920df-217">Metrics for Individual Conference Participants</span></span>

<span data-ttu-id="920df-218">下表列出了单个会议参与者的呼叫允许控制报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="920df-218">The following table lists the information provided in the Call Admission Control Report for individual conference participants.</span></span>

### <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="920df-219">单个会议参与者的指标</span><span class="sxs-lookup"><span data-stu-id="920df-219">Metrics for Individual Conference Participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="920df-220">名称</span><span class="sxs-lookup"><span data-stu-id="920df-220">Name</span></span></th>
<th><span data-ttu-id="920df-221">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="920df-221">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="920df-222">说明</span><span class="sxs-lookup"><span data-stu-id="920df-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="920df-223"><strong>角色</strong></span><span class="sxs-lookup"><span data-stu-id="920df-223"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="920df-224">否</span><span class="sxs-lookup"><span data-stu-id="920df-224">No</span></span></p></td>
<td><p><span data-ttu-id="920df-225">会议参与者扮演的角色（例如“演示者”）。</span><span class="sxs-lookup"><span data-stu-id="920df-225">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="920df-226"><strong>参与者</strong></span><span class="sxs-lookup"><span data-stu-id="920df-226"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="920df-227">否</span><span class="sxs-lookup"><span data-stu-id="920df-227">No</span></span></p></td>
<td><p><span data-ttu-id="920df-228">会议参与者的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="920df-228">SIP address of the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="920df-229"><strong>连接</strong></span><span class="sxs-lookup"><span data-stu-id="920df-229"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="920df-230">否</span><span class="sxs-lookup"><span data-stu-id="920df-230">No</span></span></p></td>
<td><p><span data-ttu-id="920df-231">参与者的网络连接（通常为“来自内部”或“来自外部”）。</span><span class="sxs-lookup"><span data-stu-id="920df-231">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="920df-232"><strong>模态</strong></span><span class="sxs-lookup"><span data-stu-id="920df-232"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="920df-233">否</span><span class="sxs-lookup"><span data-stu-id="920df-233">No</span></span></p></td>
<td><p><span data-ttu-id="920df-234">会议类型（例如 A/V 会议）。</span><span class="sxs-lookup"><span data-stu-id="920df-234">Conference type (for example, A/V conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="920df-235"><strong>加入时间</strong></span><span class="sxs-lookup"><span data-stu-id="920df-235"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="920df-236">否</span><span class="sxs-lookup"><span data-stu-id="920df-236">No</span></span></p></td>
<td><p><span data-ttu-id="920df-237">参与者加入会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="920df-237">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="920df-238"><strong>离开时间</strong></span><span class="sxs-lookup"><span data-stu-id="920df-238"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="920df-239">否</span><span class="sxs-lookup"><span data-stu-id="920df-239">No</span></span></p></td>
<td><p><span data-ttu-id="920df-240">参与者离开会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="920df-240">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="920df-241"><strong>诊断 ID</strong></span><span class="sxs-lookup"><span data-stu-id="920df-241"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="920df-242">否</span><span class="sxs-lookup"><span data-stu-id="920df-242">No</span></span></p></td>
<td><p><span data-ttu-id="920df-p115">附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。诊断标头是可选的（SIP 会话可以不包含这些标头），并且只对遇到此类问题的会话报告诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="920df-p115">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

