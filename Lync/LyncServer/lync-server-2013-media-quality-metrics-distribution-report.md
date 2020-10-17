---
title: Lync Server 2013：媒体质量指标分布报告
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
ms.openlocfilehash: c3823f65d5bc565f01b55b08259a4482c97bbd43
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500649"
---
# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a>Lync Server 2013 中的媒体质量指标分布报告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-06-06_

通过媒体质量指标分布报告，可以查看显示 "体验质量" 指标（如抖动或数据包丢失）的分布值的图形。 例如，假设您的用户总共拨打了10个电话呼叫;这10个呼叫报告以下往返时间：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>呼叫号码</th>
<th>往返时间 (毫秒) </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>双面</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>第三章</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>4 </p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>5 </p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>6 </p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>7 </p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>8 </p></td>
<td><p>4550</p></td>
</tr>
<tr class="odd">
<td><p>9 </p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>10  </p></td>
<td><p>50</p></td>
</tr>
</tbody>
</table>


这些往返时间的平均值是500毫秒 (5000 除以 10) 。 500毫秒是往返时间非常长;因此，您可能认为网络拥塞存在严重问题。  (长往返时间通常是超载网络的结果。 ) 

当然，事实上，90% 的呼叫中有很好的往返时间;您只是有一个错误的呼叫，它会将整体结果引起扭曲。 如果您仅查看平均往返时间，可能会跳转到一个非常错误的结论。

媒体质量指标分布报告通过向您显示指定 (指标的图形分布（如往返行程时间) ），帮助您避免跳转到错误的结论。 这些关系图可帮助您清楚您有九个良好的呼叫和一个非常坏的呼叫。 无可否认，您可能仍希望进一步调查一个呼叫;但是，10个呼叫中的9个事实非常良好，这意味着没有理由对网络进行任何重大更改（至少在此时间点）。

<div>

## <a name="filters"></a>筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。 下表列出了可用于媒体质量指标分布报告的筛选器。

### <a name="media-quality-metrics-distribution-report-filters"></a>媒体质量指标分布报告筛选器

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>名称</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>From</strong></p></td>
<td><p>时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>X 轴中的最小值</strong></p></td>
<td><p>要在图的 X 轴上显示的最小值。</p></td>
</tr>
<tr class="even">
<td><p><strong>X 轴中的最大值</strong></p></td>
<td><p>要在图的 X 轴上显示的最大值。</p></td>
</tr>
<tr class="odd">
<td><p><strong>访问类型</strong></p></td>
<td><p>指示客户端在发起呼叫时已登录到内部网络还是外部网络。选择下列选项之一：</p>
<ul>
<li><p>各种</p></li>
<li><p>内部</p></li>
<li><p>外部</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>指示外部客户端在发起呼叫时是否使用了虚拟专用网 (VPN) 连接。选择下列选项之一：</p>
<ul>
<li><p>各种</p></li>
<li><p>VPN</p></li>
<li><p>非 VPN</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>网络类型</strong></p></td>
<td><p>指示客户端在发起呼叫时已连接到的网络的类型。选择下列选项之一：</p>
<ul>
<li><p>各种</p></li>
<li><p>有线</p></li>
<li><p>无线</p></li>
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

