---
title: Lync Server 2013：媒体质量比较报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Comparison Report
ms:assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205236(v=OCS.15)
ms:contentKeyID: 48185317
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c45f2d238d2ffd8df058e31bfa50a51f26c1caf5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-comparison-report-in-lync-server-2013"></a><span data-ttu-id="c61f5-102">Lync Server 2013 中的媒体质量比较报告</span><span class="sxs-lookup"><span data-stu-id="c61f5-102">Media Quality Comparison Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c61f5-103">_**上次修改的主题：** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="c61f5-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="c61f5-104">媒体质量比较报告使您能够比较不同类型的音频呼叫（例如，通过无线网络发出的呼叫与通过有线连接发出的呼叫）的呼叫质量值。</span><span class="sxs-lookup"><span data-stu-id="c61f5-104">The Media Quality Comparison Report enables you to compare call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

<div>

## <a name="accessing-the-media-quality-comparison-report"></a><span data-ttu-id="c61f5-105">访问媒体质量比较报告</span><span class="sxs-lookup"><span data-stu-id="c61f5-105">Accessing the Media Quality Comparison Report</span></span>

<span data-ttu-id="c61f5-106">媒体质量比较报告可以从“监控报告”主页进行访问。</span><span class="sxs-lookup"><span data-stu-id="c61f5-106">The Media Quality Comparison Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="c61f5-107">筛选器</span><span class="sxs-lookup"><span data-stu-id="c61f5-107">Filters</span></span>

<span data-ttu-id="c61f5-p101">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于媒体质量比较报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="c61f5-p101">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-filters"></a><span data-ttu-id="c61f5-110">媒体质量比较报告筛选器</span><span class="sxs-lookup"><span data-stu-id="c61f5-110">Media Quality Comparison Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c61f5-111">名称</span><span class="sxs-lookup"><span data-stu-id="c61f5-111">Name</span></span></th>
<th><span data-ttu-id="c61f5-112">说明</span><span class="sxs-lookup"><span data-stu-id="c61f5-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c61f5-113"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="c61f5-113"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="c61f5-p102">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c61f5-p102">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="c61f5-116">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="c61f5-116">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c61f5-p103">如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="c61f5-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c61f5-119">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c61f5-119">7/7/2012</span></span></p>
<p><span data-ttu-id="c61f5-120">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="c61f5-120">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c61f5-121">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c61f5-121">7/3/2012</span></span></p>
<p><span data-ttu-id="c61f5-122">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="c61f5-122">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c61f5-123"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="c61f5-123"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="c61f5-p104">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c61f5-p104">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="c61f5-126">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="c61f5-126">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c61f5-p105">如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="c61f5-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c61f5-129">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c61f5-129">7/7/2012</span></span></p>
<p><span data-ttu-id="c61f5-130">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="c61f5-130">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c61f5-131">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c61f5-131">7/3/2012</span></span></p>
<p><span data-ttu-id="c61f5-132">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="c61f5-132">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c61f5-133"><strong>呼叫</strong></span><span class="sxs-lookup"><span data-stu-id="c61f5-133"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="c61f5-p106">要用作主要比较项目的呼叫类型。允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="c61f5-p106">Type of call to be used as the main comparison item. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="c61f5-136">各种</span><span class="sxs-lookup"><span data-stu-id="c61f5-136">[All]</span></span></p></li>
<li><p><span data-ttu-id="c61f5-137">外部</span><span class="sxs-lookup"><span data-stu-id="c61f5-137">External</span></span></p></li>
<li><p><span data-ttu-id="c61f5-138">内部</span><span class="sxs-lookup"><span data-stu-id="c61f5-138">Internal</span></span></p></li>
<li><p><span data-ttu-id="c61f5-139">VPN</span><span class="sxs-lookup"><span data-stu-id="c61f5-139">VPN</span></span></p></li>
<li><p><span data-ttu-id="c61f5-140">非 VPN</span><span class="sxs-lookup"><span data-stu-id="c61f5-140">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="c61f5-141">有线</span><span class="sxs-lookup"><span data-stu-id="c61f5-141">Wired</span></span></p></li>
<li><p><span data-ttu-id="c61f5-142">无线</span><span class="sxs-lookup"><span data-stu-id="c61f5-142">Wireless</span></span></p></li>
<li><p><span data-ttu-id="c61f5-143">外部和有线</span><span class="sxs-lookup"><span data-stu-id="c61f5-143">External and wired</span></span></p></li>
<li><p><span data-ttu-id="c61f5-144">外部和无线</span><span class="sxs-lookup"><span data-stu-id="c61f5-144">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="c61f5-145">外部和 VPN</span><span class="sxs-lookup"><span data-stu-id="c61f5-145">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="c61f5-146">外部和非 VPN</span><span class="sxs-lookup"><span data-stu-id="c61f5-146">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="c61f5-147">内部和有线</span><span class="sxs-lookup"><span data-stu-id="c61f5-147">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="c61f5-148">内部和无线</span><span class="sxs-lookup"><span data-stu-id="c61f5-148">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c61f5-149"><strong>与呼叫进行比较</strong></span><span class="sxs-lookup"><span data-stu-id="c61f5-149"><strong>Compare with calls</strong></span></span></p></td>
<td><p><span data-ttu-id="c61f5-p107">要用作次要比较项目的呼叫类型，允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="c61f5-p107">Type of call to be used as the secondary comparison item. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="c61f5-152">各种</span><span class="sxs-lookup"><span data-stu-id="c61f5-152">[All]</span></span></p></li>
<li><p><span data-ttu-id="c61f5-153">外部</span><span class="sxs-lookup"><span data-stu-id="c61f5-153">External</span></span></p></li>
<li><p><span data-ttu-id="c61f5-154">内部</span><span class="sxs-lookup"><span data-stu-id="c61f5-154">Internal</span></span></p></li>
<li><p><span data-ttu-id="c61f5-155">VPN</span><span class="sxs-lookup"><span data-stu-id="c61f5-155">VPN</span></span></p></li>
<li><p><span data-ttu-id="c61f5-156">非 VPN</span><span class="sxs-lookup"><span data-stu-id="c61f5-156">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="c61f5-157">有线</span><span class="sxs-lookup"><span data-stu-id="c61f5-157">Wired</span></span></p></li>
<li><p><span data-ttu-id="c61f5-158">无线</span><span class="sxs-lookup"><span data-stu-id="c61f5-158">Wireless</span></span></p></li>
<li><p><span data-ttu-id="c61f5-159">外部和有线</span><span class="sxs-lookup"><span data-stu-id="c61f5-159">External and wired</span></span></p></li>
<li><p><span data-ttu-id="c61f5-160">外部和无线</span><span class="sxs-lookup"><span data-stu-id="c61f5-160">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="c61f5-161">外部和 VPN</span><span class="sxs-lookup"><span data-stu-id="c61f5-161">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="c61f5-162">外部和非 VPN</span><span class="sxs-lookup"><span data-stu-id="c61f5-162">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="c61f5-163">内部和有线</span><span class="sxs-lookup"><span data-stu-id="c61f5-163">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="c61f5-164">内部和无线</span><span class="sxs-lookup"><span data-stu-id="c61f5-164">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c61f5-165"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="c61f5-165"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="c61f5-p108">时间间隔。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="c61f5-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c61f5-168">每小时（最多可显示 25 个小时）</span><span class="sxs-lookup"><span data-stu-id="c61f5-168">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c61f5-169">每天（最多可显示 31 天）</span><span class="sxs-lookup"><span data-stu-id="c61f5-169">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c61f5-170">每周（最多可显示 12 周）</span><span class="sxs-lookup"><span data-stu-id="c61f5-170">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="c61f5-p109">如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。例如，如果选择的开始日期为 8/7/2012、结束日期为 9/28/2012、间隔为“每天”，则显示从 8/7/2012 12:00 AM 到 9/7/2012 12:00 AM 这些天的数据（即总共 31 天的数据）。</span><span class="sxs-lookup"><span data-stu-id="c61f5-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="c61f5-173">指标</span><span class="sxs-lookup"><span data-stu-id="c61f5-173">Metrics</span></span>

<span data-ttu-id="c61f5-174">下表列出了媒体质量比较报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="c61f5-174">The following table lists the information provided in the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-metrics"></a><span data-ttu-id="c61f5-175">媒体质量比较报告指标</span><span class="sxs-lookup"><span data-stu-id="c61f5-175">Media Quality Comparison Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c61f5-176">名称</span><span class="sxs-lookup"><span data-stu-id="c61f5-176">Name</span></span></th>
<th><span data-ttu-id="c61f5-177">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="c61f5-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c61f5-178">说明</span><span class="sxs-lookup"><span data-stu-id="c61f5-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c61f5-179"><strong>呼叫量</strong></span><span class="sxs-lookup"><span data-stu-id="c61f5-179"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="c61f5-180">否</span><span class="sxs-lookup"><span data-stu-id="c61f5-180">No</span></span></p></td>
<td><p><span data-ttu-id="c61f5-181">呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="c61f5-181">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c61f5-182"><strong>性能降低(MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="c61f5-182"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="c61f5-183">否</span><span class="sxs-lookup"><span data-stu-id="c61f5-183">No</span></span></p></td>
<td><p><span data-ttu-id="c61f5-184">通话过程中 MOS 的平均数量（平均意见得分）。</span><span class="sxs-lookup"><span data-stu-id="c61f5-184">Average amount of MOS (mean opinion score) degradation experienced during a call.</span></span> <span data-ttu-id="c61f5-185">性能降低值的范围介于 0.0 和 5.0 之间；该值小于或等于 0.5 表示可接受的性能降低。</span><span class="sxs-lookup"><span data-stu-id="c61f5-185">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="c61f5-186">在过去，平均意见得分是通过让用户对呼叫质量进行评级（范围为1到5）来计算得出的。</span><span class="sxs-lookup"><span data-stu-id="c61f5-186">Historically, mean opinion scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="c61f5-187">Lync Server 使用一组算法来预测用户对呼叫进行评级的方式。</span><span class="sxs-lookup"><span data-stu-id="c61f5-187">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="c61f5-p111">高性能降低值可能是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器或终结点超载造成的，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="c61f5-p111">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c61f5-190"><strong>质量欠佳的呼叫百分比</strong></span><span class="sxs-lookup"><span data-stu-id="c61f5-190"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="c61f5-191">否</span><span class="sxs-lookup"><span data-stu-id="c61f5-191">No</span></span></p></td>
<td><p><span data-ttu-id="c61f5-p112">归类为质量欠佳的呼叫的总数。质量欠佳的呼叫是指至少一项测量指标超过允许的值的任何呼叫（例如，信号极不稳定的呼叫）。</span><span class="sxs-lookup"><span data-stu-id="c61f5-p112">The total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c61f5-194"><strong>来回行程(毫秒)</strong></span><span class="sxs-lookup"><span data-stu-id="c61f5-194"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="c61f5-195">否</span><span class="sxs-lookup"><span data-stu-id="c61f5-195">No</span></span></p></td>
<td><p><span data-ttu-id="c61f5-p113">实时传输协议数据包来往于另一个终结点所需的平均时间量（以毫秒为单位）。来回行程的时间小于或等于 200 毫秒被视为质量可接受。</span><span class="sxs-lookup"><span data-stu-id="c61f5-p113">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="c61f5-p114">高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。</span><span class="sxs-lookup"><span data-stu-id="c61f5-p114">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c61f5-200"><strong>数据包丢失</strong></span><span class="sxs-lookup"><span data-stu-id="c61f5-200"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="c61f5-201">否</span><span class="sxs-lookup"><span data-stu-id="c61f5-201">No</span></span></p></td>
<td><p><span data-ttu-id="c61f5-p115">平均 RTP 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时将发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="c61f5-p115">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c61f5-205"><strong>抖动(毫秒)</strong></span><span class="sxs-lookup"><span data-stu-id="c61f5-205"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="c61f5-206">否</span><span class="sxs-lookup"><span data-stu-id="c61f5-206">No</span></span></p></td>
<td><p><span data-ttu-id="c61f5-207">在 RTP 数据包到达之间检查到的平均抖动率。</span><span class="sxs-lookup"><span data-stu-id="c61f5-207">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="c61f5-208">（抖动是对&quot;shakiness&quot;的衡量。高抖动值通常是由拥塞或过载的媒体服务器引起的，并导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="c61f5-208">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c61f5-209"><strong>修复程序隐藏比率</strong></span><span class="sxs-lookup"><span data-stu-id="c61f5-209"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="c61f5-210">否</span><span class="sxs-lookup"><span data-stu-id="c61f5-210">No</span></span></p></td>
<td><p><span data-ttu-id="c61f5-p117">隐藏的音频样本与样本总数的平均比率。（隐藏的音频样本是一项技术，用于消除通常由丢弃的网络数据包造成的意外转换。）高值指示数据包丢失或抖动造成的显著的丢失隐藏级别，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="c61f5-p117">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c61f5-213"><strong>修复程序拉伸比率</strong></span><span class="sxs-lookup"><span data-stu-id="c61f5-213"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="c61f5-214">否</span><span class="sxs-lookup"><span data-stu-id="c61f5-214">No</span></span></p></td>
<td><p><span data-ttu-id="c61f5-p118">拉伸的音频样本数与样本总数的平均比率。（拉伸的音频是一类已扩展的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本拉伸级别，从而导致音频听起来很机械或失真。</span><span class="sxs-lookup"><span data-stu-id="c61f5-p118">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c61f5-217"><strong>修复程序压缩比率</strong></span><span class="sxs-lookup"><span data-stu-id="c61f5-217"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="c61f5-218">否</span><span class="sxs-lookup"><span data-stu-id="c61f5-218">No</span></span></p></td>
<td><p><span data-ttu-id="c61f5-p119">压缩的音频样本与样本总数的平均比率。（压缩的音频是一类已压缩的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本压缩级别，从而导致音频听起来像是已加速或失真。</span><span class="sxs-lookup"><span data-stu-id="c61f5-p119">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

