---
title: Lync Server 2013：媒体质量摘要报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Summary Report
ms:assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615012(v=OCS.15)
ms:contentKeyID: 48184776
ms.date: 06/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89a5046ba15534d40c81e1e3b8a4f310873a9e1b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-summary-report-in-lync-server-2013"></a><span data-ttu-id="3ea84-102">Lync Server 2013 中的媒体质量摘要报告</span><span class="sxs-lookup"><span data-stu-id="3ea84-102">Media Quality Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ea84-103">_**上次修改的主题：** 2016-06-29_</span><span class="sxs-lookup"><span data-stu-id="3ea84-103">_**Topic Last Modified:** 2016-06-29_</span></span>

<span data-ttu-id="3ea84-104">媒体质量摘要报告可能最适合用来分析组织内部的呼叫质量，此报告提供了分为以下几个类别的详细的用户体验质量 (QoE) 呼叫指标：</span><span class="sxs-lookup"><span data-stu-id="3ea84-104">The Media Quality Summary Report is perhaps your best bet for analyzing call quality in your organization: this report provides detailed Quality of Experience (QoE) call metrics broken down into the following categories:</span></span>

  - <span data-ttu-id="3ea84-105">UC 对等呼叫（如 Microsoft Lync 2013 至 Microsoft Lync 2013 呼叫）</span><span class="sxs-lookup"><span data-stu-id="3ea84-105">UC Peer to Peer Calls (such as a Microsoft Lync 2013 to Microsoft Lync 2013 call)</span></span>

  - <span data-ttu-id="3ea84-106">UC 会议会话</span><span class="sxs-lookup"><span data-stu-id="3ea84-106">UC Conference Sessions</span></span>

  - <span data-ttu-id="3ea84-107">PSTN 会议会话</span><span class="sxs-lookup"><span data-stu-id="3ea84-107">PSTN Conference Sessions</span></span>

  - <span data-ttu-id="3ea84-108">PSTN 呼叫: 媒体旁路</span><span class="sxs-lookup"><span data-stu-id="3ea84-108">PSTN Calls: Media Bypass</span></span>

  - <span data-ttu-id="3ea84-109">PSTN 呼叫(无旁路): UC 线路</span><span class="sxs-lookup"><span data-stu-id="3ea84-109">PSTN Calls (Non-Bypass): UC Leg</span></span>

  - <span data-ttu-id="3ea84-110">PSTN 呼叫(无旁路): 网关线路</span><span class="sxs-lookup"><span data-stu-id="3ea84-110">PSTN Calls (Non-Bypass): Gateway Leg</span></span>

  - <span data-ttu-id="3ea84-111">其他呼叫类型</span><span class="sxs-lookup"><span data-stu-id="3ea84-111">Other Call Types</span></span>

<span data-ttu-id="3ea84-112">一打开报告您就会看到有关所有这些类别的摘要信息。</span><span class="sxs-lookup"><span data-stu-id="3ea84-112">When you first open the report, you see summary information for each of these categories.</span></span> <span data-ttu-id="3ea84-113">在不离开报告的情况下，您可以展开每个类别，以查看子类别，例如从 Office Communicator 2007 R2 向 Lync 2013 发出的呼叫。</span><span class="sxs-lookup"><span data-stu-id="3ea84-113">Without leaving the report, you can expand each category to look at subcategories such as calls made from Office Communicator 2007 R2 to Lync 2013.</span></span> <span data-ttu-id="3ea84-114">反过来，您可以向下钻取这些子类别以查看有关在该类别中进行的每个呼叫的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3ea84-114">In turn, you can then drill down into these subcategories to see details about each call made within that subcategory.</span></span>

<span data-ttu-id="3ea84-115">在 Microsoft Lync Server 2013 中，媒体质量摘要报告进一步将数据分解为三种呼叫类型：音频呼叫、视频通话和应用程序共享呼叫。</span><span class="sxs-lookup"><span data-stu-id="3ea84-115">In Microsoft Lync Server 2013 the Media Quality Summary Report further breaks the data down into three call types: audio calls, video calls, and application sharing calls.</span></span> <span data-ttu-id="3ea84-116">每种呼叫类型在报告中都具有自己对应的部分，并具有自己的自定义呼叫指标集。</span><span class="sxs-lookup"><span data-stu-id="3ea84-116">Each call type has its own section in the report, and its own custom set of call metrics.</span></span>

<span data-ttu-id="3ea84-117">此外，可利用媒体质量摘要报告来应用一些筛选器，以便能够比较有线呼叫与无线呼叫的呼叫质量、内部呼叫与外部呼叫的呼叫质量以及 VPN 呼叫与非 VPN 呼叫的呼叫质量。</span><span class="sxs-lookup"><span data-stu-id="3ea84-117">The Media Quality Summary Report also allows you to apply filters that enable you to compare the call quality of wired calls vs. wireless calls, internal calls vs. external calls, and VPN calls vs. non-VPN calls.</span></span>

<div>

## <a name="accessing-the-media-quality-summary-report"></a><span data-ttu-id="3ea84-118">访问媒体质量摘要报告</span><span class="sxs-lookup"><span data-stu-id="3ea84-118">Accessing the Media Quality Summary Report</span></span>

<span data-ttu-id="3ea84-119">可从监控报告主页访问媒体质量摘要报告。</span><span class="sxs-lookup"><span data-stu-id="3ea84-119">The Media Quality Summary Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="3ea84-120">您可以通过单击以下任一指标深入到[Lync Server 2013 中的呼叫列表报告](lync-server-2013-call-list-report.md)：</span><span class="sxs-lookup"><span data-stu-id="3ea84-120">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="3ea84-121">呼叫量</span><span class="sxs-lookup"><span data-stu-id="3ea84-121">Call volume</span></span>

  - <span data-ttu-id="3ea84-122">质量欠佳的呼叫百分比</span><span class="sxs-lookup"><span data-stu-id="3ea84-122">Poor call percentage</span></span>

<span data-ttu-id="3ea84-123">此外，您可以通过单击以下任一音频呼叫指标来访问媒体质量指标分布报告：</span><span class="sxs-lookup"><span data-stu-id="3ea84-123">In addition, you can access the Media Quality Metrics Distribution Report by clicking any of the following audio call metrics:</span></span>

  - <span data-ttu-id="3ea84-124">来回行程(毫秒)</span><span class="sxs-lookup"><span data-stu-id="3ea84-124">Round trip (ms)</span></span>

  - <span data-ttu-id="3ea84-125">性能降低(MOS)</span><span class="sxs-lookup"><span data-stu-id="3ea84-125">Degradation (MOS)</span></span>

  - <span data-ttu-id="3ea84-126">数据包丢失</span><span class="sxs-lookup"><span data-stu-id="3ea84-126">Packet loss</span></span>

  - <span data-ttu-id="3ea84-127">抖动(毫秒)</span><span class="sxs-lookup"><span data-stu-id="3ea84-127">Jitter (ms)</span></span>

  - <span data-ttu-id="3ea84-128">修复程序隐藏比率</span><span class="sxs-lookup"><span data-stu-id="3ea84-128">Healer concealed ratio</span></span>

  - <span data-ttu-id="3ea84-129">修复程序拉伸比率</span><span class="sxs-lookup"><span data-stu-id="3ea84-129">Healer stretched ratio</span></span>

  - <span data-ttu-id="3ea84-130">修复程序压缩比率</span><span class="sxs-lookup"><span data-stu-id="3ea84-130">Healer compressed ratio</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="3ea84-131">筛选器</span><span class="sxs-lookup"><span data-stu-id="3ea84-131">Filters</span></span>

<span data-ttu-id="3ea84-p104">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，媒体质量摘要报告使您能够按访问类型（即内部访问与外部访问）或有线/无线网络连接等条件来筛选返回的数据。您还可以选择数据的分组方式。在此示例中，将按小时、日、周或月对呼叫进行分组。</span><span class="sxs-lookup"><span data-stu-id="3ea84-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Media Quality Summary Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="3ea84-136">下表列出了可用于媒体质量摘要报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="3ea84-136">The following table lists the filters that you can use with the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-filters"></a><span data-ttu-id="3ea84-137">媒体质量摘要报告筛选器</span><span class="sxs-lookup"><span data-stu-id="3ea84-137">Media Quality Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3ea84-138">名称</span><span class="sxs-lookup"><span data-stu-id="3ea84-138">Name</span></span></th>
<th><span data-ttu-id="3ea84-139">说明</span><span class="sxs-lookup"><span data-stu-id="3ea84-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ea84-140"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-140"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-p105">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3ea84-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="3ea84-143">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="3ea84-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="3ea84-p106">如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="3ea84-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="3ea84-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="3ea84-146">7/7/2012</span></span></p>
<p><span data-ttu-id="3ea84-147">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="3ea84-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="3ea84-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="3ea84-148">7/3/2012</span></span></p>
<p><span data-ttu-id="3ea84-149">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="3ea84-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ea84-150"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-150"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-p107">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3ea84-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="3ea84-153">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="3ea84-153">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="3ea84-p108">如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="3ea84-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="3ea84-156">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="3ea84-156">7/7/2012</span></span></p>
<p><span data-ttu-id="3ea84-157">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="3ea84-157">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="3ea84-158">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="3ea84-158">7/3/2012</span></span></p>
<p><span data-ttu-id="3ea84-159">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="3ea84-159">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ea84-160"><strong>访问类型</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-160"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-p109">指示客户端在发起呼叫时已登录到内部网络还是外部网络。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="3ea84-p109">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="3ea84-163">各种</span><span class="sxs-lookup"><span data-stu-id="3ea84-163">[All]</span></span></p></li>
<li><p><span data-ttu-id="3ea84-164">内部</span><span class="sxs-lookup"><span data-stu-id="3ea84-164">Internal</span></span></p></li>
<li><p><span data-ttu-id="3ea84-165">外部</span><span class="sxs-lookup"><span data-stu-id="3ea84-165">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ea84-166"><strong>网络类型</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-166"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-p110">指示客户端在发起呼叫时已连接到的网络的类型。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="3ea84-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="3ea84-169">各种</span><span class="sxs-lookup"><span data-stu-id="3ea84-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="3ea84-170">有线</span><span class="sxs-lookup"><span data-stu-id="3ea84-170">Wired</span></span></p></li>
<li><p><span data-ttu-id="3ea84-171">无线</span><span class="sxs-lookup"><span data-stu-id="3ea84-171">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ea84-172"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-p111">指示外部客户端在发起呼叫时是否使用了虚拟专用网 (VPN) 连接。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="3ea84-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="3ea84-175">各种</span><span class="sxs-lookup"><span data-stu-id="3ea84-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="3ea84-176">VPN</span><span class="sxs-lookup"><span data-stu-id="3ea84-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="3ea84-177">非 VPN</span><span class="sxs-lookup"><span data-stu-id="3ea84-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="3ea84-178">指标</span><span class="sxs-lookup"><span data-stu-id="3ea84-178">Metrics</span></span>

<span data-ttu-id="3ea84-179">下表列出了媒体质量摘要报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="3ea84-179">The following table lists the information provided in the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-metrics-audio-call-summary"></a><span data-ttu-id="3ea84-180">媒体质量摘要报告指标：音频呼叫摘要</span><span class="sxs-lookup"><span data-stu-id="3ea84-180">Media Quality Summary Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3ea84-181">名称</span><span class="sxs-lookup"><span data-stu-id="3ea84-181">Name</span></span></th>
<th><span data-ttu-id="3ea84-182">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="3ea84-182">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="3ea84-183">说明</span><span class="sxs-lookup"><span data-stu-id="3ea84-183">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ea84-184"><strong>呼叫类型/终结点类型</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-184"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-185">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-185">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-p112">当您单击此项时，该报告会显示有关基于这个类型的呼叫的详细信息。呼叫类型包括：</span><span class="sxs-lookup"><span data-stu-id="3ea84-p112">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="3ea84-188">UC 对等呼叫</span><span class="sxs-lookup"><span data-stu-id="3ea84-188">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="3ea84-189">UC 会议会话</span><span class="sxs-lookup"><span data-stu-id="3ea84-189">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="3ea84-190">PSTN 会议会话</span><span class="sxs-lookup"><span data-stu-id="3ea84-190">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="3ea84-191">PSTN 呼叫: 媒体旁路</span><span class="sxs-lookup"><span data-stu-id="3ea84-191">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="3ea84-192">PSTN 呼叫(无旁路): UC 线路</span><span class="sxs-lookup"><span data-stu-id="3ea84-192">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="3ea84-193">PSTN 呼叫(无旁路): 网关线路</span><span class="sxs-lookup"><span data-stu-id="3ea84-193">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="3ea84-194">其他呼叫类型</span><span class="sxs-lookup"><span data-stu-id="3ea84-194">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ea84-195"><strong>呼叫量</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-195"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-196">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-196">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-197">每个呼叫类型的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="3ea84-197">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ea84-198"><strong>质量欠佳的呼叫百分比</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-198"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-199">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-199">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-p113">归类为质量欠佳的呼叫的总数。质量欠佳的呼叫是指至少一项测量指标超过允许的值的任何呼叫（例如，信号极不稳定的呼叫）。</span><span class="sxs-lookup"><span data-stu-id="3ea84-p113">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ea84-202"><strong>呼叫量(无线呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-202"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-203">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-203">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-204">使用了无线连接的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="3ea84-204">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ea84-205"><strong>呼叫量(VPN 呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-205"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-206">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-206">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-207">使用了 VPN 连接的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="3ea84-207">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ea84-208"><strong>呼叫量(外部呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-208"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-209">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-209">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-210">使用了外部连接（即内部网络外部的连接）的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="3ea84-210">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ea84-211"><strong>来回行程(毫秒)</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-211"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-212">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-212">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-p114">实时传输协议 (RTP) 数据包来往于另一个终结点所需的平均时间量（以毫秒为单位）。来回行程的时间小于或等于 100 毫秒被视为质量可接受。</span><span class="sxs-lookup"><span data-stu-id="3ea84-p114">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="3ea84-p115">高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。</span><span class="sxs-lookup"><span data-stu-id="3ea84-p115">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ea84-217"><strong>性能降低(MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-217"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-218">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-218">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-219">呼叫过程中遇到的性能降低的平均意见得分 (MOS) 的平均值。</span><span class="sxs-lookup"><span data-stu-id="3ea84-219">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="3ea84-220">性能降低值的范围介于 0.0 和 5.0 之间。</span><span class="sxs-lookup"><span data-stu-id="3ea84-220">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="3ea84-221">该值小于或等于 0.5 表示可接受的性能降低。</span><span class="sxs-lookup"><span data-stu-id="3ea84-221">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="3ea84-222">过去，平均意见得分是通过让用户对呼叫质量进行评级（范围为 1 到 5）来计算得出的。</span><span class="sxs-lookup"><span data-stu-id="3ea84-222">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="3ea84-223">在 Lync Server 中，Lync Server 使用一组算法来预测用户对呼叫进行评级的方式。</span><span class="sxs-lookup"><span data-stu-id="3ea84-223">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="3ea84-p117">高性能降低值可能是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器或终结点超载造成的，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="3ea84-p117">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ea84-226"><strong>数据包丢失</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-226"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-227">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-227">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-p118">平均 RTP 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时将发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="3ea84-p118">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ea84-231"><strong>抖动(毫秒)</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-231"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-232">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-232">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-233">在 RTP 数据包到达之间检查到的平均抖动率。</span><span class="sxs-lookup"><span data-stu-id="3ea84-233">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="3ea84-234">（抖动是对&quot;shakiness&quot;的衡量。高抖动值通常是由拥塞或过载的媒体服务器引起的，并导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="3ea84-234">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ea84-235"><strong>修复程序隐藏比率</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-235"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-236">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-236">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-p120">隐藏的音频样本与样本总数的平均比率。（隐藏的音频样本是一项技术，用于消除通常由丢弃的网络数据包造成的意外转换。）高值指示数据包丢失或抖动造成的显著的丢失隐藏级别，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="3ea84-p120">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ea84-239"><strong>修复程序拉伸比率</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-239"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-240">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-240">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-p121">拉伸的音频样本数与样本总数的平均比率。（拉伸的音频是一类已扩展的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本拉伸级别，从而导致音频听起来很机械或失真。</span><span class="sxs-lookup"><span data-stu-id="3ea84-p121">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ea84-243"><strong>修复程序压缩比率</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-243"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-244">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-244">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-p122">压缩的音频样本与样本总数的平均比率。（压缩的音频是一类已压缩的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本压缩级别，从而导致音频听起来像是已加速或失真。</span><span class="sxs-lookup"><span data-stu-id="3ea84-p122">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-video-call-summary"></a><span data-ttu-id="3ea84-247">媒体质量摘要报告指标：视频呼叫摘要</span><span class="sxs-lookup"><span data-stu-id="3ea84-247">Media Quality Summary Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3ea84-248">名称</span><span class="sxs-lookup"><span data-stu-id="3ea84-248">Name</span></span></th>
<th><span data-ttu-id="3ea84-249">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="3ea84-249">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="3ea84-250">说明</span><span class="sxs-lookup"><span data-stu-id="3ea84-250">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ea84-251"><strong>呼叫类型/终结点类型</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-251"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-252">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-252">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-p123">当您单击此项时，该报告会显示有关基于这个类型的呼叫的详细信息。呼叫类型包括：</span><span class="sxs-lookup"><span data-stu-id="3ea84-p123">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="3ea84-255">UC 对等呼叫</span><span class="sxs-lookup"><span data-stu-id="3ea84-255">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="3ea84-256">UC 会议会话</span><span class="sxs-lookup"><span data-stu-id="3ea84-256">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="3ea84-257">PSTN 会议会话</span><span class="sxs-lookup"><span data-stu-id="3ea84-257">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="3ea84-258">PSTN 呼叫: 媒体旁路</span><span class="sxs-lookup"><span data-stu-id="3ea84-258">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="3ea84-259">PSTN 呼叫(无旁路): UC 线路</span><span class="sxs-lookup"><span data-stu-id="3ea84-259">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="3ea84-260">PSTN 呼叫(无旁路): 网关线路</span><span class="sxs-lookup"><span data-stu-id="3ea84-260">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="3ea84-261">其他呼叫类型</span><span class="sxs-lookup"><span data-stu-id="3ea84-261">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ea84-262"><strong>呼叫量</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-262"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-263">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-263">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-264">每个呼叫类型的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="3ea84-264">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ea84-265"><strong>质量欠佳的呼叫百分比</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-265"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-266">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-266">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-p124">归类为质量欠佳的呼叫的总数。质量欠佳的呼叫是指至少一项测量指标超过允许的值的任何呼叫（例如，信号极不稳定的呼叫）。</span><span class="sxs-lookup"><span data-stu-id="3ea84-p124">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ea84-269"><strong>呼叫量(无线呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-269"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-270">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-270">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-271">使用了无线连接的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="3ea84-271">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ea84-272"><strong>呼叫量(VPN 呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-272"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-273">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-273">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-274">使用了 VPN 连接的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="3ea84-274">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ea84-275"><strong>呼叫量(外部呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-275"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-276">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-276">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-277">使用了外部连接（即内部网络外部的连接）的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="3ea84-277">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ea84-278"><strong>平均比特率(Kb/s)</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-278"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-279">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-279">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-280">平均视频比特率 (Kb/s)。</span><span class="sxs-lookup"><span data-stu-id="3ea84-280">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ea84-281"><strong>低比特率百分比</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-281"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-282">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-282">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-283">比特率较低的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="3ea84-283">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ea84-284"><strong>出站数据包丢失</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-284"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-285">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-285">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-p125">出站数据包的实时传输协议 (RTP) 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时，即发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的。数据包丢失通常导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="3ea84-p125">Real-Time Transport Protocol (RTP) packet loss for outbound packets. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ea84-289"><strong>冻结帧百分比</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-289"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-290">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-290">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-p126">“冻结”帧的百分比。在一个冻结帧中，视频将停止前进，而呼叫的音频部分将继续。</span><span class="sxs-lookup"><span data-stu-id="3ea84-p126">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ea84-293"><strong>出站平均帧速率</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-293"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-294">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-294">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-295">呼叫期间的出站传输的平均帧速率。</span><span class="sxs-lookup"><span data-stu-id="3ea84-295">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ea84-296"><strong>入站平均帧速率</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-296"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-297">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-297">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-298">呼叫期间的入站传输的平均帧速率。</span><span class="sxs-lookup"><span data-stu-id="3ea84-298">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ea84-299"><strong>入站低帧速率(%)</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-299"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-300">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-300">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-301">传入视频的比特率较低的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="3ea84-301">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ea84-302"><strong>客户端健康状态百分比</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-302"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3ea84-303">指示呼叫期间客户端设备的相对健康状态。</span><span class="sxs-lookup"><span data-stu-id="3ea84-303">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="3ea84-304">媒体质量摘要报告指标：应用程序共享呼叫摘要</span><span class="sxs-lookup"><span data-stu-id="3ea84-304">Media Quality Summary Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3ea84-305">名称</span><span class="sxs-lookup"><span data-stu-id="3ea84-305">Name</span></span></th>
<th><span data-ttu-id="3ea84-306">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="3ea84-306">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="3ea84-307">说明</span><span class="sxs-lookup"><span data-stu-id="3ea84-307">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ea84-308"><strong>呼叫类型/终结点类型</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-308"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-309">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-309">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-p127">当您单击此项时，该报告会显示有关基于这个类型的呼叫的详细信息。呼叫类型包括：</span><span class="sxs-lookup"><span data-stu-id="3ea84-p127">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="3ea84-312">UC 对等呼叫</span><span class="sxs-lookup"><span data-stu-id="3ea84-312">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="3ea84-313">UC 会议会话</span><span class="sxs-lookup"><span data-stu-id="3ea84-313">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="3ea84-314">PSTN 会议会话</span><span class="sxs-lookup"><span data-stu-id="3ea84-314">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="3ea84-315">PSTN 呼叫: 媒体旁路</span><span class="sxs-lookup"><span data-stu-id="3ea84-315">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="3ea84-316">PSTN 呼叫(无旁路): UC 线路</span><span class="sxs-lookup"><span data-stu-id="3ea84-316">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="3ea84-317">PSTN 呼叫(无旁路): 网关线路</span><span class="sxs-lookup"><span data-stu-id="3ea84-317">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="3ea84-318">其他呼叫类型</span><span class="sxs-lookup"><span data-stu-id="3ea84-318">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ea84-319"><strong>呼叫量</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-319"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-320">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-320">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-321">每个呼叫类型的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="3ea84-321">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ea84-322"><strong>质量欠佳的呼叫百分比</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-322"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-323">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-323">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-p128">归类为质量欠佳的呼叫的总数。质量欠佳的呼叫是指至少一项测量指标超过允许的值的任何呼叫（例如，信号极不稳定的呼叫）。</span><span class="sxs-lookup"><span data-stu-id="3ea84-p128">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ea84-326"><strong>呼叫量(无线呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-326"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-327">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-327">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-328">使用了无线连接的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="3ea84-328">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ea84-329"><strong>呼叫量(VPN 呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-329"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-330">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-330">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-331">使用了 VPN 连接的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="3ea84-331">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ea84-332"><strong>呼叫量(外部呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-332"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-333">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-333">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-334">使用了外部连接（即内部网络外部的连接）的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="3ea84-334">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ea84-335"><strong>抖动(毫秒)</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-335"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-336">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-336">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-337">在 RTP 数据包到达之间检查到的平均抖动率。</span><span class="sxs-lookup"><span data-stu-id="3ea84-337">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="3ea84-338">（抖动是对&quot;shakiness&quot;的衡量。高抖动值通常是由拥塞或过载的媒体服务器引起的，并导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="3ea84-338">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ea84-339"><strong>相对单向平均值</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-339"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-340">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-340">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-p130">两个媒体终结点之间的平均相对单向延迟。这是单跃点延迟度量。</span><span class="sxs-lookup"><span data-stu-id="3ea84-p130">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ea84-343"><strong>平均 RDP 图块处理延迟</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-343"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-344">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-344">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-345">查看会话持续时间内 AS 会议服务器中的平均 RDP 图块处理延迟。</span><span class="sxs-lookup"><span data-stu-id="3ea84-345">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="3ea84-346">较高的平均值反映了查看体验中的延迟较长，并且包括网络延迟。</span><span class="sxs-lookup"><span data-stu-id="3ea84-346">A high average reflects a longer delay in the viewing experience, and includes network latency.</span></span> <span data-ttu-id="3ea84-347">过载的会议服务器可能会遇到更长的平均延迟。</span><span class="sxs-lookup"><span data-stu-id="3ea84-347">An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ea84-348"><strong>总损坏图块百分比</strong></span><span class="sxs-lookup"><span data-stu-id="3ea84-348"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="3ea84-349">否</span><span class="sxs-lookup"><span data-stu-id="3ea84-349">No</span></span></p></td>
<td><p><span data-ttu-id="3ea84-350">已损坏 RDP 图块的总百分比。</span><span class="sxs-lookup"><span data-stu-id="3ea84-350">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

