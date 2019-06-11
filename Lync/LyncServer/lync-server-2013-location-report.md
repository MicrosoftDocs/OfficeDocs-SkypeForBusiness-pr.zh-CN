---
title: 'Lync Server 2013: 位置报告'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Location Report
ms:assetid: cb2f1551-1e21-4f13-a39d-91f5f9010ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615035(v=OCS.15)
ms:contentKeyID: 48185641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ac5ab1d077acb8f96849b4ac44911a4c90786fa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-report-in-lync-server-2013"></a><span data-ttu-id="a2eeb-102">Lync Server 2013 中的位置报告</span><span class="sxs-lookup"><span data-stu-id="a2eeb-102">Location Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2eeb-103">_**主题上次修改时间:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="a2eeb-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="a2eeb-p101">位置报告提供按网络位置（即，按网络子网）分组的呼叫质量指标信息。如果您的用户在呼叫时遇到问题，此报告可帮助您确定这些问题是普遍存在还是主要限制在特定网段。</span><span class="sxs-lookup"><span data-stu-id="a2eeb-p101">The Location Report provides information about call quality metrics grouped by network location (that is, by network subnet). If your users are experiencing problems with their calls, this report can help you determine if those problems are widespread or if they are largely confined to a given network segment.</span></span>

<div>

## <a name="accessing-the-location-report"></a><span data-ttu-id="a2eeb-106">访问位置报告</span><span class="sxs-lookup"><span data-stu-id="a2eeb-106">Accessing the Location Report</span></span>

<span data-ttu-id="a2eeb-p102">可通过“监控报告”主页访问位置报告。您可以单击以下指标之一来深入研究呼叫列表报告：</span><span class="sxs-lookup"><span data-stu-id="a2eeb-p102">The Location Report is accessed from the Monitoring Reports home page. You can drill down to the Call List Report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="a2eeb-109">呼叫量</span><span class="sxs-lookup"><span data-stu-id="a2eeb-109">Call volume</span></span>

  - <span data-ttu-id="a2eeb-110">质量欠佳的呼叫百分比</span><span class="sxs-lookup"><span data-stu-id="a2eeb-110">Poor call percentage</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="a2eeb-111">筛选器</span><span class="sxs-lookup"><span data-stu-id="a2eeb-111">Filters</span></span>

<span data-ttu-id="a2eeb-112">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。</span><span class="sxs-lookup"><span data-stu-id="a2eeb-112">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="a2eeb-113">例如，你可以使用位置报告对呼叫发出位置或发生的连接（无线或有线）等内容进行筛选。</span><span class="sxs-lookup"><span data-stu-id="a2eeb-113">For example, the Location Report enables you to filter on such things as the location where a call was originated or whether the call took place on a wireless or a wired connection.</span></span> <span data-ttu-id="a2eeb-114">你还可以选择数据的分组方式。</span><span class="sxs-lookup"><span data-stu-id="a2eeb-114">You can also choose how data should be grouped.</span></span> <span data-ttu-id="a2eeb-115">在此示例中，将按小时、天、周或月对呼叫进行分组。</span><span class="sxs-lookup"><span data-stu-id="a2eeb-115">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="a2eeb-116">下表列出了可用于位置报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="a2eeb-116">The following table lists the filters that you can use with the Location Report.</span></span>

### <a name="location-report-filters"></a><span data-ttu-id="a2eeb-117">位置报告筛选器</span><span class="sxs-lookup"><span data-stu-id="a2eeb-117">Location Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a2eeb-118">名称</span><span class="sxs-lookup"><span data-stu-id="a2eeb-118">Name</span></span></th>
<th><span data-ttu-id="a2eeb-119">说明</span><span class="sxs-lookup"><span data-stu-id="a2eeb-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2eeb-120"><strong>从</strong></span><span class="sxs-lookup"><span data-stu-id="a2eeb-120"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="a2eeb-p104">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a2eeb-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="a2eeb-123">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="a2eeb-123">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="a2eeb-p105">如果您未输入开始时间，该报告会自动将将某个特定日期的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="a2eeb-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a2eeb-126">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="a2eeb-126">7/7/2012</span></span></p>
<p><span data-ttu-id="a2eeb-127">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="a2eeb-127">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a2eeb-128">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="a2eeb-128">7/3/2012</span></span></p>
<p><span data-ttu-id="a2eeb-129">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="a2eeb-129">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2eeb-130"><strong>到</strong></span><span class="sxs-lookup"><span data-stu-id="a2eeb-130"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="a2eeb-p106">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a2eeb-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="a2eeb-133">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="a2eeb-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="a2eeb-p107">如果您未输入结束时间，该报告会自动将某个特定日期的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="a2eeb-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a2eeb-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="a2eeb-136">7/7/2012</span></span></p>
<p><span data-ttu-id="a2eeb-137">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="a2eeb-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a2eeb-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="a2eeb-138">7/3/2012</span></span></p>
<p><span data-ttu-id="a2eeb-139">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="a2eeb-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2eeb-140"><strong>呼叫者位置</strong></span><span class="sxs-lookup"><span data-stu-id="a2eeb-140"><strong>Caller location</strong></span></span></p></td>
<td><p><span data-ttu-id="a2eeb-p108">发起呼叫的用户的 IP 子网。可以只选择“<strong>[所有]</strong>”来表示所有子网。</span><span class="sxs-lookup"><span data-stu-id="a2eeb-p108">IP subnet of the user who placed the call. You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2eeb-143"><strong>被叫方位置</strong></span><span class="sxs-lookup"><span data-stu-id="a2eeb-143"><strong>Callee location</strong></span></span></p></td>
<td><p><span data-ttu-id="a2eeb-p109">收到呼叫的用户的 IP 子网。可以只选择“<strong>[所有]</strong>”来表示所有子网。</span><span class="sxs-lookup"><span data-stu-id="a2eeb-p109">IP subnet of the user who received the call. You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2eeb-146"><strong>网络类型</strong></span><span class="sxs-lookup"><span data-stu-id="a2eeb-146"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="a2eeb-p110">指示客户端在发起呼叫时已连接到的网络的类型。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="a2eeb-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="a2eeb-149">[所有]</span><span class="sxs-lookup"><span data-stu-id="a2eeb-149">[All]</span></span></p></li>
<li><p><span data-ttu-id="a2eeb-150">有线</span><span class="sxs-lookup"><span data-stu-id="a2eeb-150">Wired</span></span></p></li>
<li><p><span data-ttu-id="a2eeb-151">无线</span><span class="sxs-lookup"><span data-stu-id="a2eeb-151">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2eeb-152"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="a2eeb-152"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="a2eeb-p111">指示外部客户端在发起呼叫时是否使用了虚拟专用网 (VPN) 连接。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="a2eeb-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="a2eeb-155">[所有]</span><span class="sxs-lookup"><span data-stu-id="a2eeb-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="a2eeb-156">VPN</span><span class="sxs-lookup"><span data-stu-id="a2eeb-156">VPN</span></span></p></li>
<li><p><span data-ttu-id="a2eeb-157">非 VPN</span><span class="sxs-lookup"><span data-stu-id="a2eeb-157">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="a2eeb-158">指标</span><span class="sxs-lookup"><span data-stu-id="a2eeb-158">Metrics</span></span>

<span data-ttu-id="a2eeb-159">下表列出了位置报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="a2eeb-159">The following table lists the information provided in the Location Report.</span></span>

### <a name="location-report-metrics"></a><span data-ttu-id="a2eeb-160">位置报告指标</span><span class="sxs-lookup"><span data-stu-id="a2eeb-160">Location Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a2eeb-161">名称</span><span class="sxs-lookup"><span data-stu-id="a2eeb-161">Name</span></span></th>
<th><span data-ttu-id="a2eeb-162">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="a2eeb-162">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a2eeb-163">描述</span><span class="sxs-lookup"><span data-stu-id="a2eeb-163">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2eeb-164"><strong>呼叫者子网</strong></span><span class="sxs-lookup"><span data-stu-id="a2eeb-164"><strong>Caller subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="a2eeb-165">否</span><span class="sxs-lookup"><span data-stu-id="a2eeb-165">No</span></span></p></td>
<td><p><span data-ttu-id="a2eeb-166">发起呼叫的用户的 IP 子网。</span><span class="sxs-lookup"><span data-stu-id="a2eeb-166">IP subnet of the user who placed the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2eeb-167"><strong>被叫方子网</strong></span><span class="sxs-lookup"><span data-stu-id="a2eeb-167"><strong>Callee subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="a2eeb-168">否</span><span class="sxs-lookup"><span data-stu-id="a2eeb-168">No</span></span></p></td>
<td><p><span data-ttu-id="a2eeb-169">收到呼叫的用户的 IP 子网。</span><span class="sxs-lookup"><span data-stu-id="a2eeb-169">IP subnet of the user who received the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2eeb-170"><strong>呼叫量</strong></span><span class="sxs-lookup"><span data-stu-id="a2eeb-170"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="a2eeb-171">是</span><span class="sxs-lookup"><span data-stu-id="a2eeb-171">Yes</span></span></p></td>
<td><p><span data-ttu-id="a2eeb-172">发起的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="a2eeb-172">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2eeb-173"><strong>质量欠佳的呼叫百分比</strong></span><span class="sxs-lookup"><span data-stu-id="a2eeb-173"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="a2eeb-174">是</span><span class="sxs-lookup"><span data-stu-id="a2eeb-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="a2eeb-p112">归类为质量欠佳呼叫的呼叫的百分比。质量欠佳的呼叫是指至少一项测量指标超过允许值的任何呼叫（例如，信号极不稳定的呼叫）。</span><span class="sxs-lookup"><span data-stu-id="a2eeb-p112">Percentage of calls classified as poor calls. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2eeb-177"><strong>来回行程（毫秒）</strong></span><span class="sxs-lookup"><span data-stu-id="a2eeb-177"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="a2eeb-178">是</span><span class="sxs-lookup"><span data-stu-id="a2eeb-178">Yes</span></span></p></td>
<td><p><span data-ttu-id="a2eeb-p113">实时传输协议 (RTP) 数据包来往于另一个终结点所需的平均时间量（以毫秒为单位）。来回行程的时间小于或等于 100 毫秒被视为质量可接受。</span><span class="sxs-lookup"><span data-stu-id="a2eeb-p113">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="a2eeb-p114">高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。</span><span class="sxs-lookup"><span data-stu-id="a2eeb-p114">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2eeb-183"><strong>性能降低 (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="a2eeb-183"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="a2eeb-184">是</span><span class="sxs-lookup"><span data-stu-id="a2eeb-184">Yes</span></span></p></td>
<td><p><span data-ttu-id="a2eeb-185">呼叫过程中遇到的性能降低的平均意见得分 (MOS) 的平均值。</span><span class="sxs-lookup"><span data-stu-id="a2eeb-185">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="a2eeb-186">性能降低值的范围介于 0.0 和 5.0 之间。</span><span class="sxs-lookup"><span data-stu-id="a2eeb-186">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="a2eeb-187">该值小于或等于 0.5 表示可接受的性能降低。</span><span class="sxs-lookup"><span data-stu-id="a2eeb-187">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="a2eeb-188">过去，平均意见得分是通过让用户对呼叫质量进行评级（范围为 1 到 5）来计算得出的。</span><span class="sxs-lookup"><span data-stu-id="a2eeb-188">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="a2eeb-189">在 Lync Server 中, Lync Server 使用一组算法来预测用户对呼叫进行评分的方式。</span><span class="sxs-lookup"><span data-stu-id="a2eeb-189">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="a2eeb-p116">高性能降低值可能是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器或终结点超载造成的，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="a2eeb-p116">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2eeb-192"><strong>数据包丢失</strong></span><span class="sxs-lookup"><span data-stu-id="a2eeb-192"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="a2eeb-193">是</span><span class="sxs-lookup"><span data-stu-id="a2eeb-193">Yes</span></span></p></td>
<td><p><span data-ttu-id="a2eeb-p117">平均 RTP 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时将发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="a2eeb-p117">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2eeb-197"><strong>抖动</strong></span><span class="sxs-lookup"><span data-stu-id="a2eeb-197"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="a2eeb-198">是</span><span class="sxs-lookup"><span data-stu-id="a2eeb-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="a2eeb-199">在 RTP 数据包到达之间检测到的平均抖动率。</span><span class="sxs-lookup"><span data-stu-id="a2eeb-199">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="a2eeb-200">(抖动是&quot;shakiness&quot;通话的衡量。)高抖动值通常由拥塞或过载的媒体服务器导致, 并导致失真或丢失的音频。</span><span class="sxs-lookup"><span data-stu-id="a2eeb-200">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2eeb-201"><strong>修复程序隐藏比率</strong></span><span class="sxs-lookup"><span data-stu-id="a2eeb-201"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="a2eeb-202">是</span><span class="sxs-lookup"><span data-stu-id="a2eeb-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="a2eeb-p119">隐藏的音频样本与样本总数的平均比率。（隐藏的音频样本是一项技术，用于消除通常由丢弃的网络数据包造成的意外转换。）高值指示数据包丢失或抖动造成的显著的丢失隐藏级别，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="a2eeb-p119">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2eeb-205"><strong>修复程序拉伸比率</strong></span><span class="sxs-lookup"><span data-stu-id="a2eeb-205"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="a2eeb-206">是</span><span class="sxs-lookup"><span data-stu-id="a2eeb-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="a2eeb-p120">拉伸的音频样本数与样本总数的平均比率。（拉伸的音频是一类已扩展的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本拉伸级别，从而导致音频听起来很机械或失真。</span><span class="sxs-lookup"><span data-stu-id="a2eeb-p120">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2eeb-209"><strong>修复程序压缩比率</strong></span><span class="sxs-lookup"><span data-stu-id="a2eeb-209"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="a2eeb-210">是</span><span class="sxs-lookup"><span data-stu-id="a2eeb-210">Yes</span></span></p></td>
<td><p><span data-ttu-id="a2eeb-p121">压缩的音频样本与样本总数的平均比率。（压缩的音频是一类已压缩的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本压缩级别，从而导致音频听起来像是已加速或失真。</span><span class="sxs-lookup"><span data-stu-id="a2eeb-p121">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

