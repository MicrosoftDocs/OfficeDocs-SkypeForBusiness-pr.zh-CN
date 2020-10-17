---
title: Lync Server 2013：对等活动摘要报告
description: Lync Server 2013：对等活动摘要报告。
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
ms.openlocfilehash: 2f081f542a5063ed83be470d3e991c58e458b487
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557298"
---
# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a><span data-ttu-id="ba07e-103">Lync Server 2013 中的对等活动摘要报告</span><span class="sxs-lookup"><span data-stu-id="ba07e-103">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba07e-104">_**上次修改的主题：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="ba07e-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="ba07e-105">点对点活动摘要报告提供点对点通信会话的整体视图。</span><span class="sxs-lookup"><span data-stu-id="ba07e-105">The Peer-to-Peer Activity Summary Report provides an overall view of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="ba07e-106">对等会话通常只涉及两个用户，不需要使用 Lync Server 会议服务。</span><span class="sxs-lookup"><span data-stu-id="ba07e-106">A peer-to-peer session typically involves just two users, and does not require the use of the Lync Server conferencing services.</span></span> <span data-ttu-id="ba07e-107">相比之下，会议通常涉及两个以上的用户，并且需要使用 Microsoft Lync Server 2013 会议服务。</span><span class="sxs-lookup"><span data-stu-id="ba07e-107">By comparison, a conference typically involves more than two users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="ba07e-108">会议活动在会议摘要报告上进行报告。</span><span class="sxs-lookup"><span data-stu-id="ba07e-108">Conference activity is reported on the Conference Summary Report.</span></span>

<span data-ttu-id="ba07e-109">点对点活动摘要报告帮助您回答诸如下列问题：</span><span class="sxs-lookup"><span data-stu-id="ba07e-109">The Peer-to-Peer Activity Summary Report helps you answer questions like the following:</span></span>

  - <span data-ttu-id="ba07e-110">在特定某一天，我的用户发送了多少点对点即时消息？</span><span class="sxs-lookup"><span data-stu-id="ba07e-110">How many peer-to-peer instant messages do my users send on a typical day?</span></span>

  - <span data-ttu-id="ba07e-111">我的任何用户是否确实利用 Lync Server 应用程序共享和文件传输功能？</span><span class="sxs-lookup"><span data-stu-id="ba07e-111">Are any of my users actually taking advantage of the Lync Server application sharing and file transfer capabilities?</span></span>

  - <span data-ttu-id="ba07e-p102">用户曾报怨在一天的特定时间网络看上去很慢。在此期间点对点音频和视频会话占用了多少分钟时间？</span><span class="sxs-lookup"><span data-stu-id="ba07e-p102">Users have been complaining that the network seems slow at certain times of the day. How many minutes are devoted to peer-to-peer audio and video sessions during those time periods?</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="ba07e-114">访问点对点活动摘要报告</span><span class="sxs-lookup"><span data-stu-id="ba07e-114">Accessing the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="ba07e-115">可从监视报告主页访问点对点活动摘要报告。</span><span class="sxs-lookup"><span data-stu-id="ba07e-115">You access the Peer-to-Peer Activity Summary Report from the Monitoring Reports home page.</span></span> <span data-ttu-id="ba07e-116">您可以通过单击以下任一指标 [在 Lync Server 2013 中打开对等 IM 报告](lync-server-2013-peer-to-peer-im-report.md) ：</span><span class="sxs-lookup"><span data-stu-id="ba07e-116">You open the [Peer-to-Peer IM Report in Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="ba07e-117">对等 IM 会话总数</span><span class="sxs-lookup"><span data-stu-id="ba07e-117">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="ba07e-118">点对点 IM 消息总数</span><span class="sxs-lookup"><span data-stu-id="ba07e-118">Total peer-to-peer IM messages</span></span>

<span data-ttu-id="ba07e-119">同样，通过单击以下任何指标可打开点对点语音和视频报告：</span><span class="sxs-lookup"><span data-stu-id="ba07e-119">Likewise, you can open the Peer-to-Peer Voice and Video Report by clicking any of these metrics:</span></span>

  - <span data-ttu-id="ba07e-120">点对点音频会话总数</span><span class="sxs-lookup"><span data-stu-id="ba07e-120">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="ba07e-121">点对点音频会话分钟总数</span><span class="sxs-lookup"><span data-stu-id="ba07e-121">Total peer-to-peer audio session minutes</span></span>

  - <span data-ttu-id="ba07e-122">点对点音频会话总数</span><span class="sxs-lookup"><span data-stu-id="ba07e-122">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="ba07e-123">点对点音频会话分钟总数</span><span class="sxs-lookup"><span data-stu-id="ba07e-123">Total peer-to-peer audio session minutes</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="ba07e-124">充分利用点对点活动摘要报告</span><span class="sxs-lookup"><span data-stu-id="ba07e-124">Making the Best Use of the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="ba07e-p104">在点对点活动摘要报告的底部，您将找到总标准数，例如，总点对点 IM 会话数和总点对点 IM 消息。这提供了报告正文中找到的详细信息的快速摘要。</span><span class="sxs-lookup"><span data-stu-id="ba07e-p104">At the bottom of the Peer-to-Peer Activity Summary Report you'll find totals for metrics such as Total peer-to-peer IM sessions and Total peer-to-peer IM messages. This provides a quick summary of the detailed information found in the body of the report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="ba07e-127">筛选器</span><span class="sxs-lookup"><span data-stu-id="ba07e-127">Filters</span></span>

<span data-ttu-id="ba07e-p105">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，点对点活动摘要报告允许您选择数据的分组方式。在此示例中，将按小时、日、周或月对活动进行分组。</span><span class="sxs-lookup"><span data-stu-id="ba07e-p105">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. For example, the Peer-to-Peer Activity Summary Report enables you to choose how data should be grouped. In this case, activity grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="ba07e-131">下表列出了可用于点对点活动摘要报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="ba07e-131">The following table lists the filters that you can use with the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-filters"></a><span data-ttu-id="ba07e-132">点对点活动摘要报告筛选器</span><span class="sxs-lookup"><span data-stu-id="ba07e-132">Peer-to-Peer Activity Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba07e-133">名称</span><span class="sxs-lookup"><span data-stu-id="ba07e-133">Name</span></span></th>
<th><span data-ttu-id="ba07e-134">说明</span><span class="sxs-lookup"><span data-stu-id="ba07e-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba07e-135"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="ba07e-135"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="ba07e-p106">时间范围的开始日期和时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ba07e-p106">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="ba07e-138">7/17/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="ba07e-138">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="ba07e-p107">如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="ba07e-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ba07e-141">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="ba07e-141">7/17/12012</span></span></p>
<p><span data-ttu-id="ba07e-142">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="ba07e-142">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ba07e-143">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="ba07e-143">7/13/2012</span></span></p>
<p><span data-ttu-id="ba07e-144">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="ba07e-144">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba07e-145"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="ba07e-145"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="ba07e-p108">时间范围的结束日期和时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ba07e-p108">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="ba07e-148">7/17/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="ba07e-148">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="ba07e-p109">如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="ba07e-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ba07e-151">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="ba07e-151">7/17/12012</span></span></p>
<p><span data-ttu-id="ba07e-152">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="ba07e-152">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ba07e-153">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="ba07e-153">7/13/2012</span></span></p>
<p><span data-ttu-id="ba07e-154">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="ba07e-154">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba07e-155"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="ba07e-155"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="ba07e-p110">时间间隔。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="ba07e-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ba07e-158">每小时（最多可显示 25 个小时）</span><span class="sxs-lookup"><span data-stu-id="ba07e-158">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="ba07e-159">每天（最多可显示 31 天）</span><span class="sxs-lookup"><span data-stu-id="ba07e-159">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="ba07e-160">每周（最多可显示 12 周）</span><span class="sxs-lookup"><span data-stu-id="ba07e-160">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="ba07e-161">每月（最多可显示 12 个月）</span><span class="sxs-lookup"><span data-stu-id="ba07e-161">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="ba07e-p111">如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。例如，如果选择的开始日期为 8/7/2012、结束日期为 9/28/2012、间隔为“每天”，则显示从 8/7/2012 12:00 AM 到 9/7/2012  12:00 AM 这些天的数据（即总共 31 天的数据）。</span><span class="sxs-lookup"><span data-stu-id="ba07e-p111">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/17/12012 and an end date of 2/28/2012, data is displayed for the days 8/7/12012 12:00 AM to 9/7/12012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="ba07e-164">指标</span><span class="sxs-lookup"><span data-stu-id="ba07e-164">Metrics</span></span>

<span data-ttu-id="ba07e-165">下表列出了点对点活动摘要报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="ba07e-165">The following table lists the information provided in the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-metrics"></a><span data-ttu-id="ba07e-166">点对点活动摘要报告指标</span><span class="sxs-lookup"><span data-stu-id="ba07e-166">Peer-to-Peer Activity Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba07e-167">名称</span><span class="sxs-lookup"><span data-stu-id="ba07e-167">Name</span></span></th>
<th><span data-ttu-id="ba07e-168">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="ba07e-168">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ba07e-169">说明</span><span class="sxs-lookup"><span data-stu-id="ba07e-169">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba07e-170"><strong>每小时</strong></span><span class="sxs-lookup"><span data-stu-id="ba07e-170"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="ba07e-171"><strong>每天</strong></span><span class="sxs-lookup"><span data-stu-id="ba07e-171"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="ba07e-172"><strong>每周</strong></span><span class="sxs-lookup"><span data-stu-id="ba07e-172"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="ba07e-173"><strong>每月</strong></span><span class="sxs-lookup"><span data-stu-id="ba07e-173"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="ba07e-174">否</span><span class="sxs-lookup"><span data-stu-id="ba07e-174">No</span></span></p></td>
<td><p><span data-ttu-id="ba07e-p112">指示在筛选器工具栏上选择的时间间隔。如果适用，可单击某一给定的时间间隔以查看该间隔的详细信息。例如，如果使用“每天”间隔并单击 7/17/2012，可查看当日用户注册活动的每小时细分信息。</span><span class="sxs-lookup"><span data-stu-id="ba07e-p112">Indicates the time interval that you selected on the filter toolbar. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/17/12012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba07e-178"><strong>点对点会话总数</strong></span><span class="sxs-lookup"><span data-stu-id="ba07e-178"><strong>Total peer-to-peer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="ba07e-179">否</span><span class="sxs-lookup"><span data-stu-id="ba07e-179">No</span></span></p></td>
<td><p><span data-ttu-id="ba07e-180">发起的点对点会话总数（无论是哪种会话类型）。</span><span class="sxs-lookup"><span data-stu-id="ba07e-180">Total number of peer-to-peer sessions conducted, regardless of session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba07e-181"><strong>点对点 IM 会话总数</strong></span><span class="sxs-lookup"><span data-stu-id="ba07e-181"><strong>Total peer-to-peer IM sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="ba07e-182">否</span><span class="sxs-lookup"><span data-stu-id="ba07e-182">No</span></span></p></td>
<td><p><span data-ttu-id="ba07e-p113">点对点即时消息 (IM) 会话总数。单击此项时，报告将显示所选时间段的点对点 IM 报告。</span><span class="sxs-lookup"><span data-stu-id="ba07e-p113">Total number of peer-to-peer instant messaging (IM) sessions. When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba07e-185"><strong>点对点 IM 消息总数</strong></span><span class="sxs-lookup"><span data-stu-id="ba07e-185"><strong>Total peer-to-peer IM messages</strong></span></span></p></td>
<td><p><span data-ttu-id="ba07e-186">否</span><span class="sxs-lookup"><span data-stu-id="ba07e-186">No</span></span></p></td>
<td><p><span data-ttu-id="ba07e-p114">在点对点会话中发送的即时消息总数。单击此项时，报告将显示所选时间段的点对点 IM 报告。</span><span class="sxs-lookup"><span data-stu-id="ba07e-p114">Total number of instant messages sent in peer-to-peer sessions. When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba07e-189"><strong>点对点音频会话总数</strong></span><span class="sxs-lookup"><span data-stu-id="ba07e-189"><strong>Total peer-to-peer audio sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="ba07e-190">否</span><span class="sxs-lookup"><span data-stu-id="ba07e-190">No</span></span></p></td>
<td><p><span data-ttu-id="ba07e-p115">点对点音频呼叫总数。单击此字段时，报告将显示所选时间段的点对点语音和视频报告。</span><span class="sxs-lookup"><span data-stu-id="ba07e-p115">Total number of peer-to-peer audio calls. When you click this field, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba07e-193"><strong>点对点音频会话总分钟数</strong></span><span class="sxs-lookup"><span data-stu-id="ba07e-193"><strong>Total peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="ba07e-194">否</span><span class="sxs-lookup"><span data-stu-id="ba07e-194">No</span></span></p></td>
<td><p><span data-ttu-id="ba07e-195">点对点音频会话持续的总时间。</span><span class="sxs-lookup"><span data-stu-id="ba07e-195">Total amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="ba07e-196">单击此项时，报告将显示所选时间段的点对点语音和视频报告。</span><span class="sxs-lookup"><span data-stu-id="ba07e-196">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba07e-197"><strong>点对点音频会话平均分钟数</strong></span><span class="sxs-lookup"><span data-stu-id="ba07e-197"><strong>Average peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="ba07e-198">否</span><span class="sxs-lookup"><span data-stu-id="ba07e-198">No</span></span></p></td>
<td><p><span data-ttu-id="ba07e-p117">点对点音频会话持续的平均时间。计算方法是音频会话总时间除以音频会话总数。</span><span class="sxs-lookup"><span data-stu-id="ba07e-p117">Average amount of time spent in peer-to-peer audio sessions. Calculated by dividing the total audio session time by the total number of audio sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba07e-201"><strong>点对点视频会话总数</strong></span><span class="sxs-lookup"><span data-stu-id="ba07e-201"><strong>Total peer-to-peer video sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="ba07e-202">否</span><span class="sxs-lookup"><span data-stu-id="ba07e-202">No</span></span></p></td>
<td><p><span data-ttu-id="ba07e-p118">点对点视频呼叫总数。请注意，视频会话还算作音频会话：每个视频会话算作一个视频会话和一个音频会话。单击此项时，报告将显示所选时间段的点对点语音和视频报告。</span><span class="sxs-lookup"><span data-stu-id="ba07e-p118">Total number of peer-to-peer video calls. Note that video sessions are also counted as audio sessions: each video session is counted as one video session and one audio session. When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba07e-206"><strong>点对点视频会话总分钟数</strong></span><span class="sxs-lookup"><span data-stu-id="ba07e-206"><strong>Total peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="ba07e-207">否</span><span class="sxs-lookup"><span data-stu-id="ba07e-207">No</span></span></p></td>
<td><p><span data-ttu-id="ba07e-p119">点对点视频会话持续的总时间。单击此项时，报告将显示所选时间段的点对点语音和视频报告。</span><span class="sxs-lookup"><span data-stu-id="ba07e-p119">Total amount of time spent in peer-to-peer video sessions. When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba07e-210"><strong>点对点视频会话平均分钟数</strong></span><span class="sxs-lookup"><span data-stu-id="ba07e-210"><strong>Average peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="ba07e-211">否</span><span class="sxs-lookup"><span data-stu-id="ba07e-211">No</span></span></p></td>
<td><p><span data-ttu-id="ba07e-p120">点对点视频会话持续的平均时间。计算方法是视频会话总时间除以视频会话总数。</span><span class="sxs-lookup"><span data-stu-id="ba07e-p120">Average amount of time spent in peer-to-peer video sessions. Calculated by dividing the total video session time by the total number of video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba07e-214"><strong>点对点文件传输会话总数</strong></span><span class="sxs-lookup"><span data-stu-id="ba07e-214"><strong>Total peer-to-peer file transfer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="ba07e-215">否</span><span class="sxs-lookup"><span data-stu-id="ba07e-215">No</span></span></p></td>
<td><p><span data-ttu-id="ba07e-216">包含文件传输的点对点会话总数。</span><span class="sxs-lookup"><span data-stu-id="ba07e-216">Total number of peer-to-peer sessions that included file transfers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba07e-217"><strong>点对点应用程序共享会话总数</strong></span><span class="sxs-lookup"><span data-stu-id="ba07e-217"><strong>Total peer-to-peer application sharing sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="ba07e-218">否</span><span class="sxs-lookup"><span data-stu-id="ba07e-218">No</span></span></p></td>
<td><p><span data-ttu-id="ba07e-219">包含应用程序共享的点对点会话总数。</span><span class="sxs-lookup"><span data-stu-id="ba07e-219">Total number of peer-to-peer sessions that included application sharing.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

