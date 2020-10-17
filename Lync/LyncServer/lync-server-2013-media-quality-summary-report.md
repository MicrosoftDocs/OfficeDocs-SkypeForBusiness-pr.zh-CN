---
title: Lync Server 2013：媒体质量摘要报告
description: Lync Server 2013：媒体质量摘要报告。
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
ms.openlocfilehash: 2616b7e3cdea9df7b004745a5c407188870903c7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558068"
---
# <a name="media-quality-summary-report-in-lync-server-2013"></a><span data-ttu-id="978ed-103">Lync Server 2013 中的媒体质量摘要报告</span><span class="sxs-lookup"><span data-stu-id="978ed-103">Media Quality Summary Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="978ed-104">_**上次修改的主题：** 2016-06-29_</span><span class="sxs-lookup"><span data-stu-id="978ed-104">_**Topic Last Modified:** 2016-06-29_</span></span>

<span data-ttu-id="978ed-105">媒体质量摘要报告可能最适合用来分析组织内部的呼叫质量，此报告提供了分为以下几个类别的详细的用户体验质量 (QoE) 呼叫指标：</span><span class="sxs-lookup"><span data-stu-id="978ed-105">The Media Quality Summary Report is perhaps your best bet for analyzing call quality in your organization: this report provides detailed Quality of Experience (QoE) call metrics broken down into the following categories:</span></span>

  - <span data-ttu-id="978ed-106">UC 对等呼叫 (例如 Microsoft Lync 2013 to Microsoft Lync 2013 呼叫) </span><span class="sxs-lookup"><span data-stu-id="978ed-106">UC Peer to Peer Calls (such as a Microsoft Lync 2013 to Microsoft Lync 2013 call)</span></span>

  - <span data-ttu-id="978ed-107">UC 会议会话</span><span class="sxs-lookup"><span data-stu-id="978ed-107">UC Conference Sessions</span></span>

  - <span data-ttu-id="978ed-108">PSTN 会议会话</span><span class="sxs-lookup"><span data-stu-id="978ed-108">PSTN Conference Sessions</span></span>

  - <span data-ttu-id="978ed-109">PSTN 呼叫: 媒体旁路</span><span class="sxs-lookup"><span data-stu-id="978ed-109">PSTN Calls: Media Bypass</span></span>

  - <span data-ttu-id="978ed-110">PSTN 呼叫(无旁路): UC 线路</span><span class="sxs-lookup"><span data-stu-id="978ed-110">PSTN Calls (Non-Bypass): UC Leg</span></span>

  - <span data-ttu-id="978ed-111">PSTN 呼叫(无旁路): 网关线路</span><span class="sxs-lookup"><span data-stu-id="978ed-111">PSTN Calls (Non-Bypass): Gateway Leg</span></span>

  - <span data-ttu-id="978ed-112">其他呼叫类型</span><span class="sxs-lookup"><span data-stu-id="978ed-112">Other Call Types</span></span>

<span data-ttu-id="978ed-113">一打开报告您就会看到有关所有这些类别的摘要信息。</span><span class="sxs-lookup"><span data-stu-id="978ed-113">When you first open the report, you see summary information for each of these categories.</span></span> <span data-ttu-id="978ed-114">在不离开报告的情况下，您可以展开每个类别，以查看子类别，例如从 Office Communicator 2007 R2 向 Lync 2013 发出的呼叫。</span><span class="sxs-lookup"><span data-stu-id="978ed-114">Without leaving the report, you can expand each category to look at subcategories such as calls made from Office Communicator 2007 R2 to Lync 2013.</span></span> <span data-ttu-id="978ed-115">反过来，您可以向下钻取这些子类别以查看有关在该类别中进行的每个呼叫的详细信息。</span><span class="sxs-lookup"><span data-stu-id="978ed-115">In turn, you can then drill down into these subcategories to see details about each call made within that subcategory.</span></span>

<span data-ttu-id="978ed-116">在 Microsoft Lync Server 2013 中，媒体质量摘要报告进一步将数据分解为三种呼叫类型：音频呼叫、视频通话和应用程序共享呼叫。</span><span class="sxs-lookup"><span data-stu-id="978ed-116">In Microsoft Lync Server 2013 the Media Quality Summary Report further breaks the data down into three call types: audio calls, video calls, and application sharing calls.</span></span> <span data-ttu-id="978ed-117">每种呼叫类型在报告中都具有自己对应的部分，并具有自己的自定义呼叫指标集。</span><span class="sxs-lookup"><span data-stu-id="978ed-117">Each call type has its own section in the report, and its own custom set of call metrics.</span></span>

<span data-ttu-id="978ed-118">此外，可利用媒体质量摘要报告来应用一些筛选器，以便能够比较有线呼叫与无线呼叫的呼叫质量、内部呼叫与外部呼叫的呼叫质量以及 VPN 呼叫与非 VPN 呼叫的呼叫质量。</span><span class="sxs-lookup"><span data-stu-id="978ed-118">The Media Quality Summary Report also allows you to apply filters that enable you to compare the call quality of wired calls vs. wireless calls, internal calls vs. external calls, and VPN calls vs. non-VPN calls.</span></span>

<div>

## <a name="accessing-the-media-quality-summary-report"></a><span data-ttu-id="978ed-119">访问媒体质量摘要报告</span><span class="sxs-lookup"><span data-stu-id="978ed-119">Accessing the Media Quality Summary Report</span></span>

<span data-ttu-id="978ed-120">可从监控报告主页访问媒体质量摘要报告。</span><span class="sxs-lookup"><span data-stu-id="978ed-120">The Media Quality Summary Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="978ed-121">您可以通过单击以下任一指标深入到 [Lync Server 2013 中的呼叫列表报告](lync-server-2013-call-list-report.md) ：</span><span class="sxs-lookup"><span data-stu-id="978ed-121">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="978ed-122">呼叫量</span><span class="sxs-lookup"><span data-stu-id="978ed-122">Call volume</span></span>

  - <span data-ttu-id="978ed-123">质量欠佳的呼叫百分比</span><span class="sxs-lookup"><span data-stu-id="978ed-123">Poor call percentage</span></span>

<span data-ttu-id="978ed-124">此外，您可以通过单击以下任一音频呼叫指标来访问媒体质量指标分布报告：</span><span class="sxs-lookup"><span data-stu-id="978ed-124">In addition, you can access the Media Quality Metrics Distribution Report by clicking any of the following audio call metrics:</span></span>

  - <span data-ttu-id="978ed-125">来回行程(毫秒)</span><span class="sxs-lookup"><span data-stu-id="978ed-125">Round trip (ms)</span></span>

  - <span data-ttu-id="978ed-126">性能降低(MOS)</span><span class="sxs-lookup"><span data-stu-id="978ed-126">Degradation (MOS)</span></span>

  - <span data-ttu-id="978ed-127">数据包丢失</span><span class="sxs-lookup"><span data-stu-id="978ed-127">Packet loss</span></span>

  - <span data-ttu-id="978ed-128">抖动(毫秒)</span><span class="sxs-lookup"><span data-stu-id="978ed-128">Jitter (ms)</span></span>

  - <span data-ttu-id="978ed-129">修复程序隐藏比率</span><span class="sxs-lookup"><span data-stu-id="978ed-129">Healer concealed ratio</span></span>

  - <span data-ttu-id="978ed-130">修复程序拉伸比率</span><span class="sxs-lookup"><span data-stu-id="978ed-130">Healer stretched ratio</span></span>

  - <span data-ttu-id="978ed-131">修复程序压缩比率</span><span class="sxs-lookup"><span data-stu-id="978ed-131">Healer compressed ratio</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="978ed-132">筛选器</span><span class="sxs-lookup"><span data-stu-id="978ed-132">Filters</span></span>

<span data-ttu-id="978ed-p104">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，媒体质量摘要报告使您能够按访问类型（即内部访问与外部访问）或有线/无线网络连接等条件来筛选返回的数据。您还可以选择数据的分组方式。在此示例中，将按小时、日、周或月对呼叫进行分组。</span><span class="sxs-lookup"><span data-stu-id="978ed-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Media Quality Summary Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="978ed-137">下表列出了可用于媒体质量摘要报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="978ed-137">The following table lists the filters that you can use with the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-filters"></a><span data-ttu-id="978ed-138">媒体质量摘要报告筛选器</span><span class="sxs-lookup"><span data-stu-id="978ed-138">Media Quality Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="978ed-139">名称</span><span class="sxs-lookup"><span data-stu-id="978ed-139">Name</span></span></th>
<th><span data-ttu-id="978ed-140">说明</span><span class="sxs-lookup"><span data-stu-id="978ed-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="978ed-141"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-141"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-p105">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="978ed-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="978ed-144">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="978ed-144">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="978ed-p106">如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="978ed-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="978ed-147">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="978ed-147">7/7/2012</span></span></p>
<p><span data-ttu-id="978ed-148">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="978ed-148">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="978ed-149">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="978ed-149">7/3/2012</span></span></p>
<p><span data-ttu-id="978ed-150">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="978ed-150">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="978ed-151"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-151"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-p107">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="978ed-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="978ed-154">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="978ed-154">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="978ed-p108">如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="978ed-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="978ed-157">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="978ed-157">7/7/2012</span></span></p>
<p><span data-ttu-id="978ed-158">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="978ed-158">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="978ed-159">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="978ed-159">7/3/2012</span></span></p>
<p><span data-ttu-id="978ed-160">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="978ed-160">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="978ed-161"><strong>访问类型</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-161"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-p109">指示客户端在发起呼叫时已登录到内部网络还是外部网络。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="978ed-p109">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="978ed-164">各种</span><span class="sxs-lookup"><span data-stu-id="978ed-164">[All]</span></span></p></li>
<li><p><span data-ttu-id="978ed-165">内部</span><span class="sxs-lookup"><span data-stu-id="978ed-165">Internal</span></span></p></li>
<li><p><span data-ttu-id="978ed-166">外部</span><span class="sxs-lookup"><span data-stu-id="978ed-166">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="978ed-167"><strong>网络类型</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-167"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-p110">指示客户端在发起呼叫时已连接到的网络的类型。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="978ed-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="978ed-170">各种</span><span class="sxs-lookup"><span data-stu-id="978ed-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="978ed-171">有线</span><span class="sxs-lookup"><span data-stu-id="978ed-171">Wired</span></span></p></li>
<li><p><span data-ttu-id="978ed-172">无线</span><span class="sxs-lookup"><span data-stu-id="978ed-172">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="978ed-173"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-173"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-p111">指示外部客户端在发起呼叫时是否使用了虚拟专用网 (VPN) 连接。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="978ed-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="978ed-176">各种</span><span class="sxs-lookup"><span data-stu-id="978ed-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="978ed-177">VPN</span><span class="sxs-lookup"><span data-stu-id="978ed-177">VPN</span></span></p></li>
<li><p><span data-ttu-id="978ed-178">非 VPN</span><span class="sxs-lookup"><span data-stu-id="978ed-178">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="978ed-179">指标</span><span class="sxs-lookup"><span data-stu-id="978ed-179">Metrics</span></span>

<span data-ttu-id="978ed-180">下表列出了媒体质量摘要报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="978ed-180">The following table lists the information provided in the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-metrics-audio-call-summary"></a><span data-ttu-id="978ed-181">媒体质量摘要报告指标：音频呼叫摘要</span><span class="sxs-lookup"><span data-stu-id="978ed-181">Media Quality Summary Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="978ed-182">名称</span><span class="sxs-lookup"><span data-stu-id="978ed-182">Name</span></span></th>
<th><span data-ttu-id="978ed-183">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="978ed-183">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="978ed-184">说明</span><span class="sxs-lookup"><span data-stu-id="978ed-184">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="978ed-185"><strong>呼叫类型/终结点类型</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-185"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-186">否</span><span class="sxs-lookup"><span data-stu-id="978ed-186">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-p112">当您单击此项时，该报告会显示有关基于这个类型的呼叫的详细信息。呼叫类型包括：</span><span class="sxs-lookup"><span data-stu-id="978ed-p112">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="978ed-189">UC 对等呼叫</span><span class="sxs-lookup"><span data-stu-id="978ed-189">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="978ed-190">UC 会议会话</span><span class="sxs-lookup"><span data-stu-id="978ed-190">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="978ed-191">PSTN 会议会话</span><span class="sxs-lookup"><span data-stu-id="978ed-191">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="978ed-192">PSTN 呼叫: 媒体旁路</span><span class="sxs-lookup"><span data-stu-id="978ed-192">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="978ed-193">PSTN 呼叫(无旁路): UC 线路</span><span class="sxs-lookup"><span data-stu-id="978ed-193">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="978ed-194">PSTN 呼叫(无旁路): 网关线路</span><span class="sxs-lookup"><span data-stu-id="978ed-194">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="978ed-195">其他呼叫类型</span><span class="sxs-lookup"><span data-stu-id="978ed-195">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="978ed-196"><strong>呼叫量</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-196"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-197">否</span><span class="sxs-lookup"><span data-stu-id="978ed-197">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-198">每个呼叫类型的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="978ed-198">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="978ed-199"><strong>质量欠佳的呼叫百分比</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-199"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-200">否</span><span class="sxs-lookup"><span data-stu-id="978ed-200">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-p113">归类为质量欠佳的呼叫的总数。质量欠佳的呼叫是指至少一项测量指标超过允许的值的任何呼叫（例如，信号极不稳定的呼叫）。</span><span class="sxs-lookup"><span data-stu-id="978ed-p113">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="978ed-203"><strong>呼叫量(无线呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-203"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-204">否</span><span class="sxs-lookup"><span data-stu-id="978ed-204">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-205">使用了无线连接的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="978ed-205">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="978ed-206"><strong>呼叫量(VPN 呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-206"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-207">否</span><span class="sxs-lookup"><span data-stu-id="978ed-207">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-208">使用了 VPN 连接的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="978ed-208">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="978ed-209"><strong>呼叫量(外部呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-209"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-210">否</span><span class="sxs-lookup"><span data-stu-id="978ed-210">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-211">使用了外部连接（即内部网络外部的连接）的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="978ed-211">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="978ed-212"><strong>来回行程(毫秒)</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-212"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-213">否</span><span class="sxs-lookup"><span data-stu-id="978ed-213">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-p114">实时传输协议 (RTP) 数据包来往于另一个终结点所需的平均时间量（以毫秒为单位）。来回行程的时间小于或等于 100 毫秒被视为质量可接受。</span><span class="sxs-lookup"><span data-stu-id="978ed-p114">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="978ed-p115">高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。</span><span class="sxs-lookup"><span data-stu-id="978ed-p115">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="978ed-218"><strong>性能降低(MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-218"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-219">否</span><span class="sxs-lookup"><span data-stu-id="978ed-219">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-220">呼叫过程中遇到的性能降低的平均意见得分 (MOS) 的平均值。</span><span class="sxs-lookup"><span data-stu-id="978ed-220">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="978ed-221">性能降低值的范围介于 0.0 和 5.0 之间。</span><span class="sxs-lookup"><span data-stu-id="978ed-221">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="978ed-222">该值小于或等于 0.5 表示可接受的性能降低。</span><span class="sxs-lookup"><span data-stu-id="978ed-222">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="978ed-223">过去，平均意见得分是通过让用户对呼叫质量进行评级（范围为 1 到 5）来计算得出的。</span><span class="sxs-lookup"><span data-stu-id="978ed-223">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="978ed-224">在 Lync Server 中，Lync Server 使用一组算法来预测用户对呼叫进行评级的方式。</span><span class="sxs-lookup"><span data-stu-id="978ed-224">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="978ed-p117">高性能降低值可能是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器或终结点超载造成的，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="978ed-p117">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="978ed-227"><strong>数据包丢失</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-227"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-228">否</span><span class="sxs-lookup"><span data-stu-id="978ed-228">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-p118">平均 RTP 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时将发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="978ed-p118">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="978ed-232"><strong>抖动(毫秒)</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-232"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-233">否</span><span class="sxs-lookup"><span data-stu-id="978ed-233">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-234">在 RTP 数据包到达之间检查到的平均抖动率。</span><span class="sxs-lookup"><span data-stu-id="978ed-234">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="978ed-235"> (抖动是 shakiness 的衡量指标 &quot; &quot; 。 ) 高抖动值通常由拥塞或过载的媒体服务器引起，并导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="978ed-235">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="978ed-236"><strong>修复程序隐藏比率</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-236"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-237">否</span><span class="sxs-lookup"><span data-stu-id="978ed-237">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-p120">隐藏的音频样本与样本总数的平均比率。（隐藏的音频样本是一项技术，用于消除通常由丢弃的网络数据包造成的意外转换。）高值指示数据包丢失或抖动造成的显著的丢失隐藏级别，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="978ed-p120">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="978ed-240"><strong>修复程序拉伸比率</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-240"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-241">否</span><span class="sxs-lookup"><span data-stu-id="978ed-241">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-p121">拉伸的音频样本数与样本总数的平均比率。（拉伸的音频是一类已扩展的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本拉伸级别，从而导致音频听起来很机械或失真。</span><span class="sxs-lookup"><span data-stu-id="978ed-p121">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="978ed-244"><strong>修复程序压缩比率</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-244"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-245">否</span><span class="sxs-lookup"><span data-stu-id="978ed-245">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-p122">压缩的音频样本与样本总数的平均比率。（压缩的音频是一类已压缩的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本压缩级别，从而导致音频听起来像是已加速或失真。</span><span class="sxs-lookup"><span data-stu-id="978ed-p122">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-video-call-summary"></a><span data-ttu-id="978ed-248">媒体质量摘要报告指标：视频呼叫摘要</span><span class="sxs-lookup"><span data-stu-id="978ed-248">Media Quality Summary Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="978ed-249">名称</span><span class="sxs-lookup"><span data-stu-id="978ed-249">Name</span></span></th>
<th><span data-ttu-id="978ed-250">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="978ed-250">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="978ed-251">说明</span><span class="sxs-lookup"><span data-stu-id="978ed-251">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="978ed-252"><strong>呼叫类型/终结点类型</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-252"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-253">否</span><span class="sxs-lookup"><span data-stu-id="978ed-253">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-p123">当您单击此项时，该报告会显示有关基于这个类型的呼叫的详细信息。呼叫类型包括：</span><span class="sxs-lookup"><span data-stu-id="978ed-p123">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="978ed-256">UC 对等呼叫</span><span class="sxs-lookup"><span data-stu-id="978ed-256">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="978ed-257">UC 会议会话</span><span class="sxs-lookup"><span data-stu-id="978ed-257">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="978ed-258">PSTN 会议会话</span><span class="sxs-lookup"><span data-stu-id="978ed-258">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="978ed-259">PSTN 呼叫: 媒体旁路</span><span class="sxs-lookup"><span data-stu-id="978ed-259">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="978ed-260">PSTN 呼叫(无旁路): UC 线路</span><span class="sxs-lookup"><span data-stu-id="978ed-260">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="978ed-261">PSTN 呼叫(无旁路): 网关线路</span><span class="sxs-lookup"><span data-stu-id="978ed-261">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="978ed-262">其他呼叫类型</span><span class="sxs-lookup"><span data-stu-id="978ed-262">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="978ed-263"><strong>呼叫量</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-263"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-264">否</span><span class="sxs-lookup"><span data-stu-id="978ed-264">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-265">每个呼叫类型的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="978ed-265">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="978ed-266"><strong>质量欠佳的呼叫百分比</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-266"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-267">否</span><span class="sxs-lookup"><span data-stu-id="978ed-267">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-p124">归类为质量欠佳的呼叫的总数。质量欠佳的呼叫是指至少一项测量指标超过允许的值的任何呼叫（例如，信号极不稳定的呼叫）。</span><span class="sxs-lookup"><span data-stu-id="978ed-p124">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="978ed-270"><strong>呼叫量(无线呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-270"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-271">否</span><span class="sxs-lookup"><span data-stu-id="978ed-271">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-272">使用了无线连接的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="978ed-272">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="978ed-273"><strong>呼叫量(VPN 呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-273"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-274">否</span><span class="sxs-lookup"><span data-stu-id="978ed-274">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-275">使用了 VPN 连接的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="978ed-275">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="978ed-276"><strong>呼叫量(外部呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-276"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-277">否</span><span class="sxs-lookup"><span data-stu-id="978ed-277">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-278">使用了外部连接（即内部网络外部的连接）的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="978ed-278">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="978ed-279"><strong>平均比特率(Kb/s)</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-279"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-280">否</span><span class="sxs-lookup"><span data-stu-id="978ed-280">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-281">平均视频比特率 (Kb/s)。</span><span class="sxs-lookup"><span data-stu-id="978ed-281">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="978ed-282"><strong>低比特率百分比</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-282"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-283">否</span><span class="sxs-lookup"><span data-stu-id="978ed-283">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-284">比特率较低的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="978ed-284">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="978ed-285"><strong>出站数据包丢失</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-285"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-286">否</span><span class="sxs-lookup"><span data-stu-id="978ed-286">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-p125">出站数据包的实时传输协议 (RTP) 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时，即发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的。数据包丢失通常导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="978ed-p125">Real-Time Transport Protocol (RTP) packet loss for outbound packets. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="978ed-290"><strong>冻结帧百分比</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-290"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-291">否</span><span class="sxs-lookup"><span data-stu-id="978ed-291">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-p126">“冻结”帧的百分比。在一个冻结帧中，视频将停止前进，而呼叫的音频部分将继续。</span><span class="sxs-lookup"><span data-stu-id="978ed-p126">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="978ed-294"><strong>出站平均帧速率</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-294"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-295">否</span><span class="sxs-lookup"><span data-stu-id="978ed-295">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-296">呼叫期间的出站传输的平均帧速率。</span><span class="sxs-lookup"><span data-stu-id="978ed-296">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="978ed-297"><strong>入站平均帧速率</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-297"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-298">否</span><span class="sxs-lookup"><span data-stu-id="978ed-298">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-299">呼叫期间的入站传输的平均帧速率。</span><span class="sxs-lookup"><span data-stu-id="978ed-299">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="978ed-300"><strong>入站低帧速率(%)</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-300"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-301">否</span><span class="sxs-lookup"><span data-stu-id="978ed-301">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-302">传入视频的比特率较低的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="978ed-302">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="978ed-303"><strong>客户端健康状态百分比</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-303"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="978ed-304">指示呼叫期间客户端设备的相对健康状态。</span><span class="sxs-lookup"><span data-stu-id="978ed-304">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="978ed-305">媒体质量摘要报告指标：应用程序共享呼叫摘要</span><span class="sxs-lookup"><span data-stu-id="978ed-305">Media Quality Summary Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="978ed-306">名称</span><span class="sxs-lookup"><span data-stu-id="978ed-306">Name</span></span></th>
<th><span data-ttu-id="978ed-307">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="978ed-307">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="978ed-308">说明</span><span class="sxs-lookup"><span data-stu-id="978ed-308">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="978ed-309"><strong>呼叫类型/终结点类型</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-309"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-310">否</span><span class="sxs-lookup"><span data-stu-id="978ed-310">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-p127">当您单击此项时，该报告会显示有关基于这个类型的呼叫的详细信息。呼叫类型包括：</span><span class="sxs-lookup"><span data-stu-id="978ed-p127">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="978ed-313">UC 对等呼叫</span><span class="sxs-lookup"><span data-stu-id="978ed-313">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="978ed-314">UC 会议会话</span><span class="sxs-lookup"><span data-stu-id="978ed-314">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="978ed-315">PSTN 会议会话</span><span class="sxs-lookup"><span data-stu-id="978ed-315">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="978ed-316">PSTN 呼叫: 媒体旁路</span><span class="sxs-lookup"><span data-stu-id="978ed-316">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="978ed-317">PSTN 呼叫(无旁路): UC 线路</span><span class="sxs-lookup"><span data-stu-id="978ed-317">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="978ed-318">PSTN 呼叫(无旁路): 网关线路</span><span class="sxs-lookup"><span data-stu-id="978ed-318">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="978ed-319">其他呼叫类型</span><span class="sxs-lookup"><span data-stu-id="978ed-319">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="978ed-320"><strong>呼叫量</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-320"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-321">否</span><span class="sxs-lookup"><span data-stu-id="978ed-321">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-322">每个呼叫类型的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="978ed-322">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="978ed-323"><strong>质量欠佳的呼叫百分比</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-323"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-324">否</span><span class="sxs-lookup"><span data-stu-id="978ed-324">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-p128">归类为质量欠佳的呼叫的总数。质量欠佳的呼叫是指至少一项测量指标超过允许的值的任何呼叫（例如，信号极不稳定的呼叫）。</span><span class="sxs-lookup"><span data-stu-id="978ed-p128">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="978ed-327"><strong>呼叫量(无线呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-327"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-328">否</span><span class="sxs-lookup"><span data-stu-id="978ed-328">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-329">使用了无线连接的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="978ed-329">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="978ed-330"><strong>呼叫量(VPN 呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-330"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-331">否</span><span class="sxs-lookup"><span data-stu-id="978ed-331">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-332">使用了 VPN 连接的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="978ed-332">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="978ed-333"><strong>呼叫量(外部呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-333"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-334">否</span><span class="sxs-lookup"><span data-stu-id="978ed-334">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-335">使用了外部连接（即内部网络外部的连接）的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="978ed-335">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="978ed-336"><strong>抖动(毫秒)</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-336"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-337">否</span><span class="sxs-lookup"><span data-stu-id="978ed-337">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-338">在 RTP 数据包到达之间检查到的平均抖动率。</span><span class="sxs-lookup"><span data-stu-id="978ed-338">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="978ed-339"> (抖动是 shakiness 的衡量指标 &quot; &quot; 。 ) 高抖动值通常由拥塞或过载的媒体服务器引起，并导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="978ed-339">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="978ed-340"><strong>相对单向平均值</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-340"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-341">否</span><span class="sxs-lookup"><span data-stu-id="978ed-341">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-p130">两个媒体终结点之间的平均相对单向延迟。这是单跃点延迟度量。</span><span class="sxs-lookup"><span data-stu-id="978ed-p130">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="978ed-344"><strong>平均 RDP 图块处理延迟</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-344"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-345">否</span><span class="sxs-lookup"><span data-stu-id="978ed-345">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-346">查看会话持续时间内 AS 会议服务器中的平均 RDP 图块处理延迟。</span><span class="sxs-lookup"><span data-stu-id="978ed-346">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="978ed-347">较高的平均值反映了查看体验中的延迟较长，并且包括网络延迟。</span><span class="sxs-lookup"><span data-stu-id="978ed-347">A high average reflects a longer delay in the viewing experience, and includes network latency.</span></span> <span data-ttu-id="978ed-348">过载的会议服务器可能会遇到更长的平均延迟。</span><span class="sxs-lookup"><span data-stu-id="978ed-348">An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="978ed-349"><strong>总损坏图块百分比</strong></span><span class="sxs-lookup"><span data-stu-id="978ed-349"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="978ed-350">否</span><span class="sxs-lookup"><span data-stu-id="978ed-350">No</span></span></p></td>
<td><p><span data-ttu-id="978ed-351">已损坏 RDP 图块的总百分比。</span><span class="sxs-lookup"><span data-stu-id="978ed-351">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

