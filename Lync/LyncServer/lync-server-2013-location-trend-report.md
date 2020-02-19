---
title: Lync Server 2013：位置趋势报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Trend Report
ms:assetid: 61e2db3c-9f10-4411-8e7e-c6950faf8533
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204941(v=OCS.15)
ms:contentKeyID: 48184280
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce5ee9e9158532c2ac430c8a41426765d6b01d56
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="location-trend-report-in-lync-server-2013"></a><span data-ttu-id="e98b5-102">Lync Server 2013 中的位置趋势报告</span><span class="sxs-lookup"><span data-stu-id="e98b5-102">Location Trend Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e98b5-103">_**上次修改的主题：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="e98b5-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="e98b5-104">位置趋势报告提供网络位置的呼叫质量趋势信息。</span><span class="sxs-lookup"><span data-stu-id="e98b5-104">The Location Trend Report provides call quality trend information for network locations.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="e98b5-105">筛选器</span><span class="sxs-lookup"><span data-stu-id="e98b5-105">Filters</span></span>

<span data-ttu-id="e98b5-p101">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，位置趋势报告使您能够按访问类型（即内部访问与外部访问）或有线/无线网络连接等条件来筛选返回的数据。您还可以选择数据的分组方式。在此示例中，将按小时、日或周对呼叫进行分组。</span><span class="sxs-lookup"><span data-stu-id="e98b5-p101">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Location Trend Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, or week.</span></span>

<span data-ttu-id="e98b5-110">下表列出了可用于位置趋势报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="e98b5-110">The following table lists the filters that you can use with the Location Trend Report.</span></span>

### <a name="location-trend-report-filters"></a><span data-ttu-id="e98b5-111">位置趋势报告筛选器</span><span class="sxs-lookup"><span data-stu-id="e98b5-111">Location Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e98b5-112">名称</span><span class="sxs-lookup"><span data-stu-id="e98b5-112">Name</span></span></th>
<th><span data-ttu-id="e98b5-113">说明</span><span class="sxs-lookup"><span data-stu-id="e98b5-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e98b5-114"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="e98b5-114"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="e98b5-p102">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e98b5-p102">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="e98b5-117">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e98b5-117">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e98b5-p103">如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="e98b5-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e98b5-120">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e98b5-120">7/7/2012</span></span></p>
<p><span data-ttu-id="e98b5-121">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="e98b5-121">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e98b5-122">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e98b5-122">7/3/2012</span></span></p>
<p><span data-ttu-id="e98b5-123">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="e98b5-123">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e98b5-124"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="e98b5-124"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="e98b5-p104">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e98b5-p104">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="e98b5-127">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e98b5-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e98b5-p105">如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="e98b5-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e98b5-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e98b5-130">7/7/2012</span></span></p>
<p><span data-ttu-id="e98b5-131">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="e98b5-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e98b5-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e98b5-132">7/3/2012</span></span></p>
<p><span data-ttu-id="e98b5-133">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="e98b5-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e98b5-134"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="e98b5-134"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="e98b5-p106">时间间隔。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="e98b5-p106">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e98b5-137">每小时（最多可显示 25 个小时）</span><span class="sxs-lookup"><span data-stu-id="e98b5-137">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e98b5-138">每天（最多可显示 31 天）</span><span class="sxs-lookup"><span data-stu-id="e98b5-138">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e98b5-139">每周（最多可显示 12 周）</span><span class="sxs-lookup"><span data-stu-id="e98b5-139">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="e98b5-p107">如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。例如，如果选择的开始日期为 8/1/2011、结束日期为 9/28/2011、间隔为“每天”，则显示从 8/1/2011 12:00 AM 到 9/1/2011 12:00 AM 这些天的数据（即总共 31 天的数据）。</span><span class="sxs-lookup"><span data-stu-id="e98b5-p107">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 1/1/2011 and an end date of 2/28/2011, data is displayed for the days 8/1/2011 12:00 AM to 9/1/2011 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e98b5-142"><strong>访问类型</strong></span><span class="sxs-lookup"><span data-stu-id="e98b5-142"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="e98b5-p108">指示客户端在发起呼叫时已登录到内部网络还是外部网络。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="e98b5-p108">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e98b5-145">各种</span><span class="sxs-lookup"><span data-stu-id="e98b5-145">[All]</span></span></p></li>
<li><p><span data-ttu-id="e98b5-146">内部</span><span class="sxs-lookup"><span data-stu-id="e98b5-146">Internal</span></span></p></li>
<li><p><span data-ttu-id="e98b5-147">外部</span><span class="sxs-lookup"><span data-stu-id="e98b5-147">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e98b5-148"><strong>网络类型</strong></span><span class="sxs-lookup"><span data-stu-id="e98b5-148"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="e98b5-p109">指示客户端在发起呼叫时已连接到的网络的类型。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="e98b5-p109">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e98b5-151">各种</span><span class="sxs-lookup"><span data-stu-id="e98b5-151">[All]</span></span></p></li>
<li><p><span data-ttu-id="e98b5-152">有线</span><span class="sxs-lookup"><span data-stu-id="e98b5-152">Wired</span></span></p></li>
<li><p><span data-ttu-id="e98b5-153">无线</span><span class="sxs-lookup"><span data-stu-id="e98b5-153">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e98b5-154"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="e98b5-154"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="e98b5-p110">指示外部客户端在发起呼叫时是否使用了虚拟专用网 (VPN) 连接。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="e98b5-p110">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e98b5-157">各种</span><span class="sxs-lookup"><span data-stu-id="e98b5-157">[All]</span></span></p></li>
<li><p><span data-ttu-id="e98b5-158">VPN</span><span class="sxs-lookup"><span data-stu-id="e98b5-158">VPN</span></span></p></li>
<li><p><span data-ttu-id="e98b5-159">非 VPN</span><span class="sxs-lookup"><span data-stu-id="e98b5-159">Non-VPN</span></span></p></li>
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

