---
title: Lync Server 2013：媒体质量指标分布报告
description: Lync Server 2013：媒体质量指标分布报告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Metrics Distribution Report
ms:assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205262(v=OCS.15)
ms:contentKeyID: 48185409
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: def56580477dadf989268e1fc24fcec7776c00d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548148"
---
# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a><span data-ttu-id="480f8-103">Lync Server 2013 中的媒体质量指标分布报告</span><span class="sxs-lookup"><span data-stu-id="480f8-103">The Media Quality Metrics Distribution Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="480f8-104">_**上次修改的主题：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="480f8-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="480f8-105">通过媒体质量指标分布报告，可以查看显示 "体验质量" 指标（如抖动或数据包丢失）的分布值的图形。</span><span class="sxs-lookup"><span data-stu-id="480f8-105">The Media Quality Metrics Distribution Report enables you to see a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span> <span data-ttu-id="480f8-106">例如，假设您的用户总共拨打了10个电话呼叫;这10个呼叫报告以下往返时间：</span><span class="sxs-lookup"><span data-stu-id="480f8-106">For example, suppose your users make a total of 10 phone calls; those 10 calls report the following roundtrip times:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="480f8-107">呼叫号码</span><span class="sxs-lookup"><span data-stu-id="480f8-107">Call Number</span></span></th>
<th><span data-ttu-id="480f8-108">往返时间 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="480f8-108">Roundtrip Time (milliseconds)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="480f8-109">1</span><span class="sxs-lookup"><span data-stu-id="480f8-109">1</span></span></p></td>
<td><p><span data-ttu-id="480f8-110">50</span><span class="sxs-lookup"><span data-stu-id="480f8-110">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="480f8-111">双面</span><span class="sxs-lookup"><span data-stu-id="480f8-111">2</span></span></p></td>
<td><p><span data-ttu-id="480f8-112">50</span><span class="sxs-lookup"><span data-stu-id="480f8-112">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="480f8-113">第三章</span><span class="sxs-lookup"><span data-stu-id="480f8-113">3</span></span></p></td>
<td><p><span data-ttu-id="480f8-114">50</span><span class="sxs-lookup"><span data-stu-id="480f8-114">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="480f8-115">4 </span><span class="sxs-lookup"><span data-stu-id="480f8-115">4</span></span></p></td>
<td><p><span data-ttu-id="480f8-116">50</span><span class="sxs-lookup"><span data-stu-id="480f8-116">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="480f8-117">5 </span><span class="sxs-lookup"><span data-stu-id="480f8-117">5</span></span></p></td>
<td><p><span data-ttu-id="480f8-118">50</span><span class="sxs-lookup"><span data-stu-id="480f8-118">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="480f8-119">6 </span><span class="sxs-lookup"><span data-stu-id="480f8-119">6</span></span></p></td>
<td><p><span data-ttu-id="480f8-120">50</span><span class="sxs-lookup"><span data-stu-id="480f8-120">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="480f8-121">7 </span><span class="sxs-lookup"><span data-stu-id="480f8-121">7</span></span></p></td>
<td><p><span data-ttu-id="480f8-122">50</span><span class="sxs-lookup"><span data-stu-id="480f8-122">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="480f8-123">8 </span><span class="sxs-lookup"><span data-stu-id="480f8-123">8</span></span></p></td>
<td><p><span data-ttu-id="480f8-124">4550</span><span class="sxs-lookup"><span data-stu-id="480f8-124">4550</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="480f8-125">9 </span><span class="sxs-lookup"><span data-stu-id="480f8-125">9</span></span></p></td>
<td><p><span data-ttu-id="480f8-126">50</span><span class="sxs-lookup"><span data-stu-id="480f8-126">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="480f8-127">10  </span><span class="sxs-lookup"><span data-stu-id="480f8-127">10</span></span></p></td>
<td><p><span data-ttu-id="480f8-128">50</span><span class="sxs-lookup"><span data-stu-id="480f8-128">50</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="480f8-129">这些往返时间的平均值是500毫秒 (5000 除以 10) 。</span><span class="sxs-lookup"><span data-stu-id="480f8-129">The average for those roundtrip times is 500 milliseconds (5000 divided by 10).</span></span> <span data-ttu-id="480f8-130">500毫秒是往返时间非常长;因此，您可能认为网络拥塞存在严重问题。</span><span class="sxs-lookup"><span data-stu-id="480f8-130">Five hundred milliseconds is an extremely large roundtrip time; as a result, you might believe that you have a serious problem with network congestion.</span></span> <span data-ttu-id="480f8-131"> (长往返时间通常是超载网络的结果。 ) </span><span class="sxs-lookup"><span data-stu-id="480f8-131">(Long roundtrip times are typically the result of overloaded networks.)</span></span>

<span data-ttu-id="480f8-132">当然，事实上，90% 的呼叫中有很好的往返时间;您只是有一个错误的呼叫，它会将整体结果引起扭曲。</span><span class="sxs-lookup"><span data-stu-id="480f8-132">In reality, of course, 90% of your calls had excellent round trip times; you merely had one bad call that skewed the overall results.</span></span> <span data-ttu-id="480f8-133">如果您仅查看平均往返时间，可能会跳转到一个非常错误的结论。</span><span class="sxs-lookup"><span data-stu-id="480f8-133">If you only look at the average roundtrip time you might jump to a very wrong conclusion.</span></span>

<span data-ttu-id="480f8-134">媒体质量指标分布报告通过向您显示指定 (指标的图形分布（如往返行程时间) ），帮助您避免跳转到错误的结论。</span><span class="sxs-lookup"><span data-stu-id="480f8-134">The Media Quality Metrics Distribution Report helps you avoid jumping to wrong conclusions by showing you a graphical distribution of a specified metric (such as round trip time).</span></span> <span data-ttu-id="480f8-135">这些关系图可帮助您清楚您有九个良好的呼叫和一个非常坏的呼叫。</span><span class="sxs-lookup"><span data-stu-id="480f8-135">These graphs can help make it clear that you had nine very good calls and one very bad call.</span></span> <span data-ttu-id="480f8-136">无可否认，您可能仍希望进一步调查一个呼叫;但是，10个呼叫中的9个事实非常良好，这意味着没有理由对网络进行任何重大更改（至少在此时间点）。</span><span class="sxs-lookup"><span data-stu-id="480f8-136">Admittedly, you might still want to further investigate that one call; however, the fact that 9 out of the 10 calls were very good suggests that there is no reason to make any drastic changes to your network, at least not at this point in time.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="480f8-137">筛选器</span><span class="sxs-lookup"><span data-stu-id="480f8-137">Filters</span></span>

<span data-ttu-id="480f8-138">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。</span><span class="sxs-lookup"><span data-stu-id="480f8-138">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="480f8-139">下表列出了可用于媒体质量指标分布报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="480f8-139">The following table lists the filters that you can use with the Media Quality Metrics Distribution Report.</span></span>

### <a name="media-quality-metrics-distribution-report-filters"></a><span data-ttu-id="480f8-140">媒体质量指标分布报告筛选器</span><span class="sxs-lookup"><span data-stu-id="480f8-140">Media Quality Metrics Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="480f8-141">名称</span><span class="sxs-lookup"><span data-stu-id="480f8-141">Name</span></span></th>
<th><span data-ttu-id="480f8-142">说明</span><span class="sxs-lookup"><span data-stu-id="480f8-142">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="480f8-143"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="480f8-143"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="480f8-p106">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="480f8-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="480f8-146">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="480f8-146">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="480f8-p107">如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="480f8-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="480f8-149">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="480f8-149">7/7/2012</span></span></p>
<p><span data-ttu-id="480f8-150">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="480f8-150">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="480f8-151">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="480f8-151">7/3/2012</span></span></p>
<p><span data-ttu-id="480f8-152">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="480f8-152">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="480f8-153"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="480f8-153"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="480f8-p108">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="480f8-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="480f8-156">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="480f8-156">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="480f8-p109">如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="480f8-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="480f8-159">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="480f8-159">7/7/2012</span></span></p>
<p><span data-ttu-id="480f8-160">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="480f8-160">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="480f8-161">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="480f8-161">7/3/2012</span></span></p>
<p><span data-ttu-id="480f8-162">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="480f8-162">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="480f8-163"><strong>X 轴中的最小值</strong></span><span class="sxs-lookup"><span data-stu-id="480f8-163"><strong>Minimum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="480f8-164">要在图的 X 轴上显示的最小值。</span><span class="sxs-lookup"><span data-stu-id="480f8-164">Lowest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="480f8-165"><strong>X 轴中的最大值</strong></span><span class="sxs-lookup"><span data-stu-id="480f8-165"><strong>Maximum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="480f8-166">要在图的 X 轴上显示的最大值。</span><span class="sxs-lookup"><span data-stu-id="480f8-166">Highest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="480f8-167"><strong>访问类型</strong></span><span class="sxs-lookup"><span data-stu-id="480f8-167"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="480f8-p110">指示客户端在发起呼叫时已登录到内部网络还是外部网络。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="480f8-p110">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="480f8-170">各种</span><span class="sxs-lookup"><span data-stu-id="480f8-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="480f8-171">内部</span><span class="sxs-lookup"><span data-stu-id="480f8-171">Internal</span></span></p></li>
<li><p><span data-ttu-id="480f8-172">外部</span><span class="sxs-lookup"><span data-stu-id="480f8-172">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="480f8-173"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="480f8-173"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="480f8-p111">指示外部客户端在发起呼叫时是否使用了虚拟专用网 (VPN) 连接。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="480f8-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="480f8-176">各种</span><span class="sxs-lookup"><span data-stu-id="480f8-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="480f8-177">VPN</span><span class="sxs-lookup"><span data-stu-id="480f8-177">VPN</span></span></p></li>
<li><p><span data-ttu-id="480f8-178">非 VPN</span><span class="sxs-lookup"><span data-stu-id="480f8-178">Non-VPN</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="480f8-179"><strong>网络类型</strong></span><span class="sxs-lookup"><span data-stu-id="480f8-179"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="480f8-p112">指示客户端在发起呼叫时已连接到的网络的类型。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="480f8-p112">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="480f8-182">各种</span><span class="sxs-lookup"><span data-stu-id="480f8-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="480f8-183">有线</span><span class="sxs-lookup"><span data-stu-id="480f8-183">Wired</span></span></p></li>
<li><p><span data-ttu-id="480f8-184">无线</span><span class="sxs-lookup"><span data-stu-id="480f8-184">Wireless</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

