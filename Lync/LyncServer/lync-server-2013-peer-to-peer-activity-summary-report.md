---
title: Lync Server 2013：对等活动摘要报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Summary Report
ms:assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615041(v=OCS.15)
ms:contentKeyID: 48185884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d55c3d84fe48158490473c31e9782dc63e298310
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a><span data-ttu-id="9979b-102">Lync Server 2013 中的对等活动摘要报告</span><span class="sxs-lookup"><span data-stu-id="9979b-102">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9979b-103">_**主题上次修改时间：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="9979b-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="9979b-104">对等活动摘要报告提供对等通信会话的整体视图。</span><span class="sxs-lookup"><span data-stu-id="9979b-104">The Peer-to-Peer Activity Summary Report provides an overall view of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="9979b-105">对等会话通常只涉及两个用户，不需要使用 Lync Server 会议服务。</span><span class="sxs-lookup"><span data-stu-id="9979b-105">A peer-to-peer session typically involves just two users, and does not require the use of the Lync Server conferencing services.</span></span> <span data-ttu-id="9979b-106">通过比较，会议通常涉及两个以上的用户，并且需要使用 Microsoft Lync Server 2013 会议服务。</span><span class="sxs-lookup"><span data-stu-id="9979b-106">By comparison, a conference typically involves more than two users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="9979b-107">会议活动在会议摘要报告上进行报告。</span><span class="sxs-lookup"><span data-stu-id="9979b-107">Conference activity is reported on the Conference Summary Report.</span></span>

<span data-ttu-id="9979b-108">对等活动摘要报告帮助您回答诸如下列问题：</span><span class="sxs-lookup"><span data-stu-id="9979b-108">The Peer-to-Peer Activity Summary Report helps you answer questions like the following:</span></span>

  - <span data-ttu-id="9979b-109">在特定某一天，我的用户发送了多少对等即时消息？</span><span class="sxs-lookup"><span data-stu-id="9979b-109">How many peer-to-peer instant messages do my users send on a typical day?</span></span>

  - <span data-ttu-id="9979b-110">是否有任何用户真正利用 Lync Server 应用程序共享和文件传输功能？</span><span class="sxs-lookup"><span data-stu-id="9979b-110">Are any of my users actually taking advantage of the Lync Server application sharing and file transfer capabilities?</span></span>

  - <span data-ttu-id="9979b-p102">用户曾报怨在一天的特定时间网络看上去很慢。在此期间对等音频和视频会话占用了多少分钟时间？</span><span class="sxs-lookup"><span data-stu-id="9979b-p102">Users have been complaining that the network seems slow at certain times of the day. How many minutes are devoted to peer-to-peer audio and video sessions during those time periods?</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="9979b-113">访问对等活动摘要报告</span><span class="sxs-lookup"><span data-stu-id="9979b-113">Accessing the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="9979b-114">可从监视报告主页访问对等活动摘要报告。</span><span class="sxs-lookup"><span data-stu-id="9979b-114">You access the Peer-to-Peer Activity Summary Report from the Monitoring Reports home page.</span></span> <span data-ttu-id="9979b-115">通过单击以下任一指标，[在 Lync Server 2013 中打开对等 IM 报告](lync-server-2013-peer-to-peer-im-report.md)：</span><span class="sxs-lookup"><span data-stu-id="9979b-115">You open the [Peer-to-Peer IM Report in Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="9979b-116">对等 IM 会话总数</span><span class="sxs-lookup"><span data-stu-id="9979b-116">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="9979b-117">对等 IM 消息总数</span><span class="sxs-lookup"><span data-stu-id="9979b-117">Total peer-to-peer IM messages</span></span>

<span data-ttu-id="9979b-118">同样，通过单击以下任何指标可打开对等语音和视频报告：</span><span class="sxs-lookup"><span data-stu-id="9979b-118">Likewise, you can open the Peer-to-Peer Voice and Video Report by clicking any of these metrics:</span></span>

  - <span data-ttu-id="9979b-119">对等音频会话总数</span><span class="sxs-lookup"><span data-stu-id="9979b-119">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="9979b-120">对等音频会话总分钟数</span><span class="sxs-lookup"><span data-stu-id="9979b-120">Total peer-to-peer audio session minutes</span></span>

  - <span data-ttu-id="9979b-121">对等音频会话总数</span><span class="sxs-lookup"><span data-stu-id="9979b-121">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="9979b-122">对等音频会话总分钟数</span><span class="sxs-lookup"><span data-stu-id="9979b-122">Total peer-to-peer audio session minutes</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="9979b-123">充分利用对等活动摘要报告</span><span class="sxs-lookup"><span data-stu-id="9979b-123">Making the Best Use of the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="9979b-p104">在对等活动摘要报告的底部，您将找到总标准数，例如，总对等 IM 会话数和总对等 IM 消息。这提供了报告正文中找到的详细信息的快速摘要。</span><span class="sxs-lookup"><span data-stu-id="9979b-p104">At the bottom of the Peer-to-Peer Activity Summary Report you'll find totals for metrics such as Total peer-to-peer IM sessions and Total peer-to-peer IM messages. This provides a quick summary of the detailed information found in the body of the report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="9979b-126">筛选器</span><span class="sxs-lookup"><span data-stu-id="9979b-126">Filters</span></span>

<span data-ttu-id="9979b-p105">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，对等活动摘要报告允许您选择数据的分组方式。在此示例中，将按小时、日、周或月对活动进行分组。</span><span class="sxs-lookup"><span data-stu-id="9979b-p105">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. For example, the Peer-to-Peer Activity Summary Report enables you to choose how data should be grouped. In this case, activity grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="9979b-130">下表列出了可用于对等活动摘要报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="9979b-130">The following table lists the filters that you can use with the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-filters"></a><span data-ttu-id="9979b-131">对等活动摘要报告筛选器</span><span class="sxs-lookup"><span data-stu-id="9979b-131">Peer-to-Peer Activity Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9979b-132">名称</span><span class="sxs-lookup"><span data-stu-id="9979b-132">Name</span></span></th>
<th><span data-ttu-id="9979b-133">说明</span><span class="sxs-lookup"><span data-stu-id="9979b-133">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9979b-134"><strong>从</strong></span><span class="sxs-lookup"><span data-stu-id="9979b-134"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="9979b-p106">时间范围的开始日期和时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9979b-p106">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="9979b-137">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="9979b-137">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="9979b-p107">如果您未输入开始时间，该报告会自动将将某个特定日期的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="9979b-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="9979b-140">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="9979b-140">7/17/12012</span></span></p>
<p><span data-ttu-id="9979b-141">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="9979b-141">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="9979b-142">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="9979b-142">7/13/2012</span></span></p>
<p><span data-ttu-id="9979b-143">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="9979b-143">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9979b-144"><strong>到</strong></span><span class="sxs-lookup"><span data-stu-id="9979b-144"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="9979b-p108">时间范围的结束日期和时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9979b-p108">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="9979b-147">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="9979b-147">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="9979b-p109">如果您未输入结束时间，该报告会自动将某个特定日期的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="9979b-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="9979b-150">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="9979b-150">7/17/12012</span></span></p>
<p><span data-ttu-id="9979b-151">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="9979b-151">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="9979b-152">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="9979b-152">7/13/2012</span></span></p>
<p><span data-ttu-id="9979b-153">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="9979b-153">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9979b-154"><strong>间隔</strong></span><span class="sxs-lookup"><span data-stu-id="9979b-154"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="9979b-p110">时间间隔。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="9979b-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="9979b-157">每小时（最多可显示 25 个小时）</span><span class="sxs-lookup"><span data-stu-id="9979b-157">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="9979b-158">每天（最多可显示 31 天）</span><span class="sxs-lookup"><span data-stu-id="9979b-158">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="9979b-159">每周（最多可显示 12 周）</span><span class="sxs-lookup"><span data-stu-id="9979b-159">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="9979b-160">每月（最多可显示 12 个月）</span><span class="sxs-lookup"><span data-stu-id="9979b-160">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="9979b-161">如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。</span><span class="sxs-lookup"><span data-stu-id="9979b-161">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="9979b-162">例如，如果选择 "开始日期 7/17/12012" 和 "结束日期 2/28/2012" 的 "每日间隔"，则会显示 8/7/12012 12:00 AM 到 9/7/12012 12:00 AM 的数据（即，总共31天的数据）。</span><span class="sxs-lookup"><span data-stu-id="9979b-162">For example, if you select the Daily interval with a start date of 7/17/12012 and an end date of 2/28/2012, data is displayed for the days 8/7/12012 12:00 AM to 9/7/12012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="9979b-163">指标</span><span class="sxs-lookup"><span data-stu-id="9979b-163">Metrics</span></span>

<span data-ttu-id="9979b-164">下表列出了对等活动摘要报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="9979b-164">The following table lists the information provided in the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-metrics"></a><span data-ttu-id="9979b-165">对等活动摘要报告指标</span><span class="sxs-lookup"><span data-stu-id="9979b-165">Peer-to-Peer Activity Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9979b-166">名称</span><span class="sxs-lookup"><span data-stu-id="9979b-166">Name</span></span></th>
<th><span data-ttu-id="9979b-167">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="9979b-167">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="9979b-168">描述</span><span class="sxs-lookup"><span data-stu-id="9979b-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9979b-169"><strong>每小时</strong></span><span class="sxs-lookup"><span data-stu-id="9979b-169"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="9979b-170"><strong>每天</strong></span><span class="sxs-lookup"><span data-stu-id="9979b-170"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="9979b-171"><strong>每周</strong></span><span class="sxs-lookup"><span data-stu-id="9979b-171"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="9979b-172"><strong>每月</strong></span><span class="sxs-lookup"><span data-stu-id="9979b-172"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="9979b-173">否</span><span class="sxs-lookup"><span data-stu-id="9979b-173">No</span></span></p></td>
<td><p><span data-ttu-id="9979b-174">指示在筛选器工具栏上选择的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="9979b-174">Indicates the time interval that you selected on the filter toolbar.</span></span> <span data-ttu-id="9979b-175">如果适用，可单击某一给定的时间间隔以查看该间隔的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9979b-175">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="9979b-176">例如，如果你使用的是每日间隔，并且单击 "7/17/12012"，你将看到该日期的用户注册活动的每小时细目。</span><span class="sxs-lookup"><span data-stu-id="9979b-176">For example, if you are using the Daily interval and you click 7/17/12012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9979b-177"><strong>对等会话总数</strong></span><span class="sxs-lookup"><span data-stu-id="9979b-177"><strong>Total peer-to-peer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="9979b-178">否</span><span class="sxs-lookup"><span data-stu-id="9979b-178">No</span></span></p></td>
<td><p><span data-ttu-id="9979b-179">发起的对等会话总数（无论是哪种会话类型）。</span><span class="sxs-lookup"><span data-stu-id="9979b-179">Total number of peer-to-peer sessions conducted, regardless of session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9979b-180"><strong>对等 IM 会话总数</strong></span><span class="sxs-lookup"><span data-stu-id="9979b-180"><strong>Total peer-to-peer IM sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="9979b-181">否</span><span class="sxs-lookup"><span data-stu-id="9979b-181">No</span></span></p></td>
<td><p><span data-ttu-id="9979b-p113">对等即时消息 (IM) 会话总数。单击此项时，报告将显示所选时间段的对等 IM 报告。</span><span class="sxs-lookup"><span data-stu-id="9979b-p113">Total number of peer-to-peer instant messaging (IM) sessions. When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9979b-184"><strong>对等 IM 消息总数</strong></span><span class="sxs-lookup"><span data-stu-id="9979b-184"><strong>Total peer-to-peer IM messages</strong></span></span></p></td>
<td><p><span data-ttu-id="9979b-185">否</span><span class="sxs-lookup"><span data-stu-id="9979b-185">No</span></span></p></td>
<td><p><span data-ttu-id="9979b-p114">在对等会话中发送的即时消息总数。单击此项时，报告将显示所选时间段的对等 IM 报告。</span><span class="sxs-lookup"><span data-stu-id="9979b-p114">Total number of instant messages sent in peer-to-peer sessions. When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9979b-188"><strong>对等音频会话总数</strong></span><span class="sxs-lookup"><span data-stu-id="9979b-188"><strong>Total peer-to-peer audio sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="9979b-189">否</span><span class="sxs-lookup"><span data-stu-id="9979b-189">No</span></span></p></td>
<td><p><span data-ttu-id="9979b-p115">对等音频呼叫总数。单击此字段时，报告将显示所选时间段的对等语音和视频报告。</span><span class="sxs-lookup"><span data-stu-id="9979b-p115">Total number of peer-to-peer audio calls. When you click this field, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9979b-192"><strong>对等音频会话总分钟数</strong></span><span class="sxs-lookup"><span data-stu-id="9979b-192"><strong>Total peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="9979b-193">否</span><span class="sxs-lookup"><span data-stu-id="9979b-193">No</span></span></p></td>
<td><p><span data-ttu-id="9979b-194">对等音频会话持续的总时间。</span><span class="sxs-lookup"><span data-stu-id="9979b-194">Total amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="9979b-195">单击此项时，报告将显示所选时间段的对等语音和视频报告。</span><span class="sxs-lookup"><span data-stu-id="9979b-195">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9979b-196"><strong>对等音频会话平均分钟数</strong></span><span class="sxs-lookup"><span data-stu-id="9979b-196"><strong>Average peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="9979b-197">否</span><span class="sxs-lookup"><span data-stu-id="9979b-197">No</span></span></p></td>
<td><p><span data-ttu-id="9979b-p117">对等音频会话持续的平均时间。计算方法是音频会话总时间除以音频会话总数。</span><span class="sxs-lookup"><span data-stu-id="9979b-p117">Average amount of time spent in peer-to-peer audio sessions. Calculated by dividing the total audio session time by the total number of audio sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9979b-200"><strong>对等视频会话总数</strong></span><span class="sxs-lookup"><span data-stu-id="9979b-200"><strong>Total peer-to-peer video sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="9979b-201">否</span><span class="sxs-lookup"><span data-stu-id="9979b-201">No</span></span></p></td>
<td><p><span data-ttu-id="9979b-p118">对等视频呼叫总数。请注意，视频会话还算作音频会话：每个视频会话算作一个视频会话和一个音频会话。单击此项时，报告将显示所选时间段的对等语音和视频报告。</span><span class="sxs-lookup"><span data-stu-id="9979b-p118">Total number of peer-to-peer video calls. Note that video sessions are also counted as audio sessions: each video session is counted as one video session and one audio session. When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9979b-205"><strong>对等视频会话总分钟数</strong></span><span class="sxs-lookup"><span data-stu-id="9979b-205"><strong>Total peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="9979b-206">否</span><span class="sxs-lookup"><span data-stu-id="9979b-206">No</span></span></p></td>
<td><p><span data-ttu-id="9979b-p119">对等视频会话持续的总时间。单击此项时，报告将显示所选时间段的对等语音和视频报告。</span><span class="sxs-lookup"><span data-stu-id="9979b-p119">Total amount of time spent in peer-to-peer video sessions. When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9979b-209"><strong>对等视频会话平均分钟数</strong></span><span class="sxs-lookup"><span data-stu-id="9979b-209"><strong>Average peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="9979b-210">否</span><span class="sxs-lookup"><span data-stu-id="9979b-210">No</span></span></p></td>
<td><p><span data-ttu-id="9979b-p120">对等视频会话持续的平均时间。计算方法是视频会话总时间除以视频会话总数。</span><span class="sxs-lookup"><span data-stu-id="9979b-p120">Average amount of time spent in peer-to-peer video sessions. Calculated by dividing the total video session time by the total number of video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9979b-213"><strong>对等文件传输会话总数</strong></span><span class="sxs-lookup"><span data-stu-id="9979b-213"><strong>Total peer-to-peer file transfer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="9979b-214">否</span><span class="sxs-lookup"><span data-stu-id="9979b-214">No</span></span></p></td>
<td><p><span data-ttu-id="9979b-215">包含文件传输的对等会话总数。</span><span class="sxs-lookup"><span data-stu-id="9979b-215">Total number of peer-to-peer sessions that included file transfers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9979b-216"><strong>对等应用程序共享会话总数</strong></span><span class="sxs-lookup"><span data-stu-id="9979b-216"><strong>Total peer-to-peer application sharing sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="9979b-217">否</span><span class="sxs-lookup"><span data-stu-id="9979b-217">No</span></span></p></td>
<td><p><span data-ttu-id="9979b-218">包含应用程序共享的对等会话总数。</span><span class="sxs-lookup"><span data-stu-id="9979b-218">Total number of peer-to-peer sessions that included application sharing.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

