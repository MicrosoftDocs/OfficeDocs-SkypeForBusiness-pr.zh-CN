---
title: Lync Server 2013： PSTN 会议摘要报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN Conference Summary Report
ms:assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615014(v=OCS.15)
ms:contentKeyID: 48184764
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa902b9e4d53bf0ebbedf835296a371437860095
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043454"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-conference-summary-report-in-lync-server-2013"></a><span data-ttu-id="a28b8-102">Lync Server 2013 中的 PSTN 会议摘要报告</span><span class="sxs-lookup"><span data-stu-id="a28b8-102">PSTN Conference Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a28b8-103">_**上次修改的主题：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="a28b8-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="a28b8-104">在 Microsoft Lync Server 2013 中，PSTN 会议是指至少有一个参与者通过使用 PSTN （公用电话交换网）电话拨打到音频部分的任何会议。</span><span class="sxs-lookup"><span data-stu-id="a28b8-104">In Microsoft Lync Server 2013, a PSTN conference is any conference in which at least one participant dials in to the audio portion by a using a PSTN (public switched telephone network) phone.</span></span> <span data-ttu-id="a28b8-105">（PSTN 电话是一种 "座机"、一种蜂窝电话，或任何其他不使用 IP 语音的电话）。尽管这些会议在监控报告中称为 PSTN 会议，但这些会议可能更常称为电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="a28b8-105">(A PSTN phone is a "landline," a cell phone, or any other phone which does not make use of Voice over IP.) Although referred to as PSTN conferences in the Monitoring Reports, these conferences are perhaps more-commonly known as dial-in conferences.</span></span>

<span data-ttu-id="a28b8-p102">PSTN 会议摘要报告提供了有关您组织中召开的所有 PSTN 会议（即，所有至少有一个电话拨入式用户的会议）的信息。此报告包括有关 PSTN 会议总数和参与这些会议的人员总数的信息，并且可能包括有关电话拨入式用户的总数（PSTN 参与者指标总计）的信息（此信息最重要）。</span><span class="sxs-lookup"><span data-stu-id="a28b8-p102">The PSTN Conference Summary Report provides information about all the PSTN conferences held in your organization (that is, all the conferences that had at least one dial-in user). The report includes information about the total number of PSTN conferences, the total number of people who participated in those conferences, and, perhaps, most important, the total number of dial-in users (the Total PSTN participants metric).</span></span>

<div>

## <a name="accessing-the-pstn-conference-summary-report"></a><span data-ttu-id="a28b8-108">访问 PSTN 会议摘要报告</span><span class="sxs-lookup"><span data-stu-id="a28b8-108">Accessing the PSTN Conference Summary Report</span></span>

<span data-ttu-id="a28b8-p103">只能从监控报告主页访问 PSTN 会议摘要报告。此报告未链接到任何其他报告。请注意，您无法检索 PSTN 会议的详细呼叫信息，部分原因在于单个终结点负责提交此信息。PSTN 电话无法跟踪或提交呼叫详细信息。</span><span class="sxs-lookup"><span data-stu-id="a28b8-p103">The PSTN Conference Summary Report can only be accessed from the Monitoring Reports home page. This report is not linked to any other reports. Note that you cannot retrieve detailed call information for a PSTN conference, in part because individual endpoints are responsible for submitting this information. PSTN phones are not capable of tracking or submitting call detail information.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a><span data-ttu-id="a28b8-113">最充分地利用 PSTN 会议摘要报告</span><span class="sxs-lookup"><span data-stu-id="a28b8-113">Making the Best Use of the PSTN Conference Summary Report</span></span>

<span data-ttu-id="a28b8-114">若要确定包括拨入用户的所有会议的百分比，请将 "PSTN 会议总数" 的值与[Lync Server 2013 中 "会议摘要" 报告中](lync-server-2013-conference-summary-report.md)找到的 "总会议" 指标进行比较。</span><span class="sxs-lookup"><span data-stu-id="a28b8-114">To determine the percentage of all your conferences that include dial-in users, compare the value of the Total PSTN conferences metric with the Total conferences metric found on the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md).</span></span>

<span data-ttu-id="a28b8-p104">如果您未看到所预计数目的 PSTN 会议，请记住，组织允许电话拨入式用户的会议的能力取决于已分配给用户的会议策略：如果仅允许几个用户主持 PSTN 会议，则可以明显看到 PSTN 会议的数目极少。您可以快速确定哪个会议策略（如果有）允许用户通过从 Lync Server 命令行管理程序中运行以下命令来计划 PSTN 会议：</span><span class="sxs-lookup"><span data-stu-id="a28b8-p104">If you don't see as many PSTN conferences as you might have expected to see, keep in mind that the ability to organize a conference that allows dial-in users depends on the conferencing policy that has been assigned to a user: if very few of your users are allowed to hold PSTN conferences you would obviously see very few PSTN conferences. You can quickly verify which of your conferencing policies (if any) allow users to schedule PSTN conferences by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing

<span data-ttu-id="a28b8-117">这将返回与以下内容类似的数据：</span><span class="sxs-lookup"><span data-stu-id="a28b8-117">That will return data similar to this:</span></span>

    Identity                                EnableDialInConferencing
    --------                                ------------------------
    Global                                                      True
    site:Redmond                                               False
    site:Dublin                                                False
    Tag:RedmondDialInUsers                                      True
    Tag:DublinDialInUsers                                       True

<span data-ttu-id="a28b8-118">这将返回与以下内容类似的数据：</span><span class="sxs-lookup"><span data-stu-id="a28b8-118">That will return data similar to this:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="a28b8-119">筛选器</span><span class="sxs-lookup"><span data-stu-id="a28b8-119">Filters</span></span>

<span data-ttu-id="a28b8-p105">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，PSTN 会议摘要报告允许您选择数据的分组方式。在此示例中，将按小时、日、周或月对会议进行分组。</span><span class="sxs-lookup"><span data-stu-id="a28b8-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the PSTN Conference Summary Report enables you to choose how data should be grouped. In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="a28b8-123">下表列出了可用于 PSTN 会议摘要报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="a28b8-123">The following table lists the filters that you can use with the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-filters"></a><span data-ttu-id="a28b8-124">PSTN 会议摘要报告筛选器</span><span class="sxs-lookup"><span data-stu-id="a28b8-124">PSTN Conference Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a28b8-125">名称</span><span class="sxs-lookup"><span data-stu-id="a28b8-125">Name</span></span></th>
<th><span data-ttu-id="a28b8-126">说明</span><span class="sxs-lookup"><span data-stu-id="a28b8-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a28b8-127"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="a28b8-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="a28b8-p106">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a28b8-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="a28b8-130">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="a28b8-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="a28b8-p107">如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="a28b8-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a28b8-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="a28b8-133">7/7/2012</span></span></p>
<p><span data-ttu-id="a28b8-134">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="a28b8-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a28b8-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="a28b8-135">7/3/2012</span></span></p>
<p><span data-ttu-id="a28b8-136">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="a28b8-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a28b8-137"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="a28b8-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="a28b8-p108">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a28b8-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="a28b8-140">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="a28b8-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="a28b8-p109">如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="a28b8-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a28b8-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="a28b8-143">7/7/2012</span></span></p>
<p><span data-ttu-id="a28b8-144">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="a28b8-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a28b8-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="a28b8-145">7/3/2012</span></span></p>
<p><span data-ttu-id="a28b8-146">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="a28b8-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a28b8-147"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="a28b8-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="a28b8-p110">时间间隔。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="a28b8-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="a28b8-150">每小时（最多可显示 25 个小时）</span><span class="sxs-lookup"><span data-stu-id="a28b8-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="a28b8-151">每天（最多可显示 31 天）</span><span class="sxs-lookup"><span data-stu-id="a28b8-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="a28b8-152">每周（最多可显示 12 周）</span><span class="sxs-lookup"><span data-stu-id="a28b8-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="a28b8-153">每月（最多可显示 12 个月）</span><span class="sxs-lookup"><span data-stu-id="a28b8-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="a28b8-p111">如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。例如，如果选择的开始日期为 8/7/2012、结束日期为 9/28/2012、间隔为“每天”，则显示从 8/7/2012 12:00 AM 到 9/7/2012 12:00 AM 这些天的数据（即总共 31 天的数据）。</span><span class="sxs-lookup"><span data-stu-id="a28b8-p111">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="a28b8-156">指标</span><span class="sxs-lookup"><span data-stu-id="a28b8-156">Metrics</span></span>

<span data-ttu-id="a28b8-157">下表列出了 PSTN 会议摘要报告中的信息。</span><span class="sxs-lookup"><span data-stu-id="a28b8-157">The following table lists the information in the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-metrics"></a><span data-ttu-id="a28b8-158">PSTN 会议摘要报告指标</span><span class="sxs-lookup"><span data-stu-id="a28b8-158">PSTN Conference Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a28b8-159">名称</span><span class="sxs-lookup"><span data-stu-id="a28b8-159">Name</span></span></th>
<th><span data-ttu-id="a28b8-160">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="a28b8-160">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a28b8-161">描述</span><span class="sxs-lookup"><span data-stu-id="a28b8-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a28b8-162"><strong>每小时</strong></span><span class="sxs-lookup"><span data-stu-id="a28b8-162"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="a28b8-163"><strong>每天</strong></span><span class="sxs-lookup"><span data-stu-id="a28b8-163"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="a28b8-164"><strong>每周</strong></span><span class="sxs-lookup"><span data-stu-id="a28b8-164"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="a28b8-165"><strong>每月</strong></span><span class="sxs-lookup"><span data-stu-id="a28b8-165"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="a28b8-166">否</span><span class="sxs-lookup"><span data-stu-id="a28b8-166">No</span></span></p></td>
<td><p><span data-ttu-id="a28b8-p112">指示所选的时间间隔。如果适用，可单击某一给定的时间间隔以查看该间隔的详细信息。例如，如果使用“每天”间隔并单击 7/7/2012，则可查看当日用户注册活动的每小时细分信息。</span><span class="sxs-lookup"><span data-stu-id="a28b8-p112">Indicates the selected time interval. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a28b8-170"><strong>PSTN 会议总数</strong></span><span class="sxs-lookup"><span data-stu-id="a28b8-170"><strong>Total PSTN conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="a28b8-171">否</span><span class="sxs-lookup"><span data-stu-id="a28b8-171">No</span></span></p></td>
<td><p><span data-ttu-id="a28b8-172">允许拨入访问的会议总数。</span><span class="sxs-lookup"><span data-stu-id="a28b8-172">Total number conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a28b8-173"><strong>参与者总数</strong></span><span class="sxs-lookup"><span data-stu-id="a28b8-173"><strong>Total participants</strong></span></span></p></td>
<td><p><span data-ttu-id="a28b8-174">否</span><span class="sxs-lookup"><span data-stu-id="a28b8-174">No</span></span></p></td>
<td><p><span data-ttu-id="a28b8-175">参与允许拨入访问的会议的人员总数。</span><span class="sxs-lookup"><span data-stu-id="a28b8-175">Total number of people who participated in conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a28b8-176"><strong>A/V 会议总分钟数</strong></span><span class="sxs-lookup"><span data-stu-id="a28b8-176"><strong>Total A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="a28b8-177">否</span><span class="sxs-lookup"><span data-stu-id="a28b8-177">No</span></span></p></td>
<td><p><span data-ttu-id="a28b8-178">音频/视频会议时间的总长度。</span><span class="sxs-lookup"><span data-stu-id="a28b8-178">Total amount of audio/visual conference time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a28b8-179"><strong>A/V 会议参与者总分钟数</strong></span><span class="sxs-lookup"><span data-stu-id="a28b8-179"><strong>Total A/V conference participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="a28b8-180">否</span><span class="sxs-lookup"><span data-stu-id="a28b8-180">No</span></span></p></td>
<td><p><span data-ttu-id="a28b8-p113">音频/视频参与者时间的总长度。例如，如果一个参与者在 A/V 会议中花费了 5 分钟，另一个参与者在相同的会议中花费了 3 分钟，则 A/V 会议参与者总时间将为 8 分钟。</span><span class="sxs-lookup"><span data-stu-id="a28b8-p113">Total amount of audio/visual participant time. For example, if one participant spent five minutes in an A/V conference and another participant spent three minutes in the same conference, the total A/V conference participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a28b8-183"><strong>PSTN 参与者总数</strong></span><span class="sxs-lookup"><span data-stu-id="a28b8-183"><strong>Total PSTN participants</strong></span></span></p></td>
<td><p><span data-ttu-id="a28b8-184">否</span><span class="sxs-lookup"><span data-stu-id="a28b8-184">No</span></span></p></td>
<td><p><span data-ttu-id="a28b8-185">拨入允许拨入访问的会议的用户的总数。</span><span class="sxs-lookup"><span data-stu-id="a28b8-185">Total number of users who dialed in to conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a28b8-186"><strong>PSTN 参与者总分钟数</strong></span><span class="sxs-lookup"><span data-stu-id="a28b8-186"><strong>Total PSTN participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="a28b8-187">否</span><span class="sxs-lookup"><span data-stu-id="a28b8-187">No</span></span></p></td>
<td><p><span data-ttu-id="a28b8-p114">拨入用户花费的总会议时间长度。例如，如果一个拨入参与者在会议中花费了 5 分钟，另一个参与者在相同的会议中花费了 3 分钟，则 PSTN 参与者总时间将为 8 分钟。</span><span class="sxs-lookup"><span data-stu-id="a28b8-p114">Total amount of conference time spent by dial-in users. For example, if one dial-in participant spent five minutes in a conference and another participant spent three minutes in the same conference, the total PSTN participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a28b8-190"><strong>唯一会议组织者</strong></span><span class="sxs-lookup"><span data-stu-id="a28b8-190"><strong>Unique conference organizers</strong></span></span></p></td>
<td><p><span data-ttu-id="a28b8-191">否</span><span class="sxs-lookup"><span data-stu-id="a28b8-191">No</span></span></p></td>
<td><p><span data-ttu-id="a28b8-p115">至少组织过一次允许拨入访问的会议的用户总数。与仅组织过一次会议的用户一样，组织过多次会议的用户算作一个唯一组织者。</span><span class="sxs-lookup"><span data-stu-id="a28b8-p115">Total number of users who organized at least one conference that allowed dial-in access. Users who organized more than one conference are counted as one unique organizer, just like users who only organized a single conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

