---
title: 'Lync Server 2013: 媒体质量指标分布报告'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media Quality Metrics Distribution Report
ms:assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205262(v=OCS.15)
ms:contentKeyID: 48185409
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1d814fd001f3510a7ae83e63746bdc1265932e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a><span data-ttu-id="45884-102">Lync Server 2013 中的媒体质量指标分布报告</span><span class="sxs-lookup"><span data-stu-id="45884-102">The Media Quality Metrics Distribution Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45884-103">_**主题上次修改时间:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="45884-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="45884-p101">通过媒体质量指标分布报告可以查看显示用户体验质量指标（如抖动或数据包丢失）分布值的图形。例如，假设您的用户总共进行 10 次电话呼叫；这 10 次呼叫报告以下往返时间：</span><span class="sxs-lookup"><span data-stu-id="45884-p101">The Media Quality Metrics Distribution Report enables you to see a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss. For example, suppose your users make a total of 10 phone calls; those 10 calls report the following roundtrip times:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45884-106">呼叫编号</span><span class="sxs-lookup"><span data-stu-id="45884-106">Call Number</span></span></th>
<th><span data-ttu-id="45884-107">往返时间 (毫秒)</span><span class="sxs-lookup"><span data-stu-id="45884-107">Roundtrip Time (milliseconds)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45884-108">1</span><span class="sxs-lookup"><span data-stu-id="45884-108">1</span></span></p></td>
<td><p><span data-ttu-id="45884-109">50</span><span class="sxs-lookup"><span data-stu-id="45884-109">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45884-110">2</span><span class="sxs-lookup"><span data-stu-id="45884-110">2</span></span></p></td>
<td><p><span data-ttu-id="45884-111">50</span><span class="sxs-lookup"><span data-stu-id="45884-111">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45884-112">3</span><span class="sxs-lookup"><span data-stu-id="45884-112">3</span></span></p></td>
<td><p><span data-ttu-id="45884-113">50</span><span class="sxs-lookup"><span data-stu-id="45884-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45884-114">4</span><span class="sxs-lookup"><span data-stu-id="45884-114">4</span></span></p></td>
<td><p><span data-ttu-id="45884-115">50</span><span class="sxs-lookup"><span data-stu-id="45884-115">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45884-116">5</span><span class="sxs-lookup"><span data-stu-id="45884-116">5</span></span></p></td>
<td><p><span data-ttu-id="45884-117">50</span><span class="sxs-lookup"><span data-stu-id="45884-117">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45884-118">6</span><span class="sxs-lookup"><span data-stu-id="45884-118">6</span></span></p></td>
<td><p><span data-ttu-id="45884-119">50</span><span class="sxs-lookup"><span data-stu-id="45884-119">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45884-120">7</span><span class="sxs-lookup"><span data-stu-id="45884-120">7</span></span></p></td>
<td><p><span data-ttu-id="45884-121">50</span><span class="sxs-lookup"><span data-stu-id="45884-121">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45884-122">个</span><span class="sxs-lookup"><span data-stu-id="45884-122">8</span></span></p></td>
<td><p><span data-ttu-id="45884-123">4550</span><span class="sxs-lookup"><span data-stu-id="45884-123">4550</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45884-124">db-9</span><span class="sxs-lookup"><span data-stu-id="45884-124">9</span></span></p></td>
<td><p><span data-ttu-id="45884-125">50</span><span class="sxs-lookup"><span data-stu-id="45884-125">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45884-126">10</span><span class="sxs-lookup"><span data-stu-id="45884-126">10</span></span></p></td>
<td><p><span data-ttu-id="45884-127">50</span><span class="sxs-lookup"><span data-stu-id="45884-127">50</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="45884-128">这些往返时间的平均值是500毫秒 (5000 除以 10)。</span><span class="sxs-lookup"><span data-stu-id="45884-128">The average for those roundtrip times is 500 milliseconds (5000 divided by 10).</span></span> <span data-ttu-id="45884-129">500毫秒是非常大的往返时间;因此, 你可能会认为你遇到了网络拥塞的严重问题。</span><span class="sxs-lookup"><span data-stu-id="45884-129">Five hundred milliseconds is an extremely large roundtrip time; as a result, you might believe that you have a serious problem with network congestion.</span></span> <span data-ttu-id="45884-130">(长往返时间通常是超载网络的结果。)</span><span class="sxs-lookup"><span data-stu-id="45884-130">(Long roundtrip times are typically the result of overloaded networks.)</span></span>

<span data-ttu-id="45884-131">当然，实际上 90% 的呼叫有良好的往返时间；仅仅有一次呼叫不佳歪曲了整体结果。</span><span class="sxs-lookup"><span data-stu-id="45884-131">In reality, of course, 90% of your calls had excellent round trip times; you merely had one bad call that skewed the overall results.</span></span> <span data-ttu-id="45884-132">如果您仅查看平均往返时间, 可能会跳转到一个非常错误的结论。</span><span class="sxs-lookup"><span data-stu-id="45884-132">If you only look at the average roundtrip time you might jump to a very wrong conclusion.</span></span>

<span data-ttu-id="45884-p104">媒体质量指标分布报告可显示指定指标（如往返时间）的图形分布，帮助您避免得出错误结论。这些图形有助于清楚表明有 9 次非常好的呼叫而只有 1 次非常不良的呼叫。无可否认地，您可能仍然想进一步调查那一次呼叫；但是，10 次呼叫中有 9 次非常好，表明没有理由对网络进行任何重大更改，至少此时不应更改。</span><span class="sxs-lookup"><span data-stu-id="45884-p104">The Media Quality Metrics Distribution Report helps you avoid jumping to wrong conclusions by showing you a graphical distribution of a specified metric (such as round trip time). These graphs can help make it clear that you had nine very good calls and one very bad call. Admittedly, you might still want to further investigate that one call; however, the fact that 9 out of the 10 calls were very good suggests that there is no reason to make any drastic changes to your network, at least not at this point in time.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="45884-136">筛选器</span><span class="sxs-lookup"><span data-stu-id="45884-136">Filters</span></span>

<span data-ttu-id="45884-p105">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于媒体质量指标分布报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="45884-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Media Quality Metrics Distribution Report.</span></span>

### <a name="media-quality-metrics-distribution-report-filters"></a><span data-ttu-id="45884-139">媒体质量指标分布报告筛选器</span><span class="sxs-lookup"><span data-stu-id="45884-139">Media Quality Metrics Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45884-140">名称</span><span class="sxs-lookup"><span data-stu-id="45884-140">Name</span></span></th>
<th><span data-ttu-id="45884-141">描述</span><span class="sxs-lookup"><span data-stu-id="45884-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45884-142"><strong>从</strong></span><span class="sxs-lookup"><span data-stu-id="45884-142"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="45884-p106">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="45884-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="45884-145">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="45884-145">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="45884-p107">如果您未输入开始时间，该报告会自动将将某个特定日期的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="45884-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="45884-148">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="45884-148">7/7/2012</span></span></p>
<p><span data-ttu-id="45884-149">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="45884-149">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="45884-150">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="45884-150">7/3/2012</span></span></p>
<p><span data-ttu-id="45884-151">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="45884-151">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45884-152"><strong>到</strong></span><span class="sxs-lookup"><span data-stu-id="45884-152"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="45884-p108">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="45884-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="45884-155">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="45884-155">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="45884-p109">如果您未输入结束时间，该报告会自动将某个特定日期的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="45884-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="45884-158">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="45884-158">7/7/2012</span></span></p>
<p><span data-ttu-id="45884-159">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="45884-159">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="45884-160">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="45884-160">7/3/2012</span></span></p>
<p><span data-ttu-id="45884-161">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="45884-161">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45884-162"><strong>x 轴中的最小值</strong></span><span class="sxs-lookup"><span data-stu-id="45884-162"><strong>Minimum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="45884-163">要在图形 X 轴上显示的最小值。</span><span class="sxs-lookup"><span data-stu-id="45884-163">Lowest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45884-164"><strong>x 轴中的最大值</strong></span><span class="sxs-lookup"><span data-stu-id="45884-164"><strong>Maximum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="45884-165">要在图形 X 轴上显示的最大值。</span><span class="sxs-lookup"><span data-stu-id="45884-165">Highest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45884-166"><strong>访问类型</strong></span><span class="sxs-lookup"><span data-stu-id="45884-166"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="45884-p110">指示客户端在发起呼叫时已登录到内部网络还是外部网络。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="45884-p110">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="45884-169">[所有]</span><span class="sxs-lookup"><span data-stu-id="45884-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="45884-170">内部</span><span class="sxs-lookup"><span data-stu-id="45884-170">Internal</span></span></p></li>
<li><p><span data-ttu-id="45884-171">外部</span><span class="sxs-lookup"><span data-stu-id="45884-171">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45884-172"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="45884-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="45884-p111">指示外部客户端在发起呼叫时是否使用了虚拟专用网 (VPN) 连接。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="45884-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="45884-175">[所有]</span><span class="sxs-lookup"><span data-stu-id="45884-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="45884-176">VPN</span><span class="sxs-lookup"><span data-stu-id="45884-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="45884-177">非 VPN</span><span class="sxs-lookup"><span data-stu-id="45884-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45884-178"><strong>网络类型</strong></span><span class="sxs-lookup"><span data-stu-id="45884-178"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="45884-p112">指示客户端在发起呼叫时已连接到的网络的类型。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="45884-p112">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="45884-181">[所有]</span><span class="sxs-lookup"><span data-stu-id="45884-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="45884-182">有线</span><span class="sxs-lookup"><span data-stu-id="45884-182">Wired</span></span></p></li>
<li><p><span data-ttu-id="45884-183">无线</span><span class="sxs-lookup"><span data-stu-id="45884-183">Wireless</span></span></p></li>
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

