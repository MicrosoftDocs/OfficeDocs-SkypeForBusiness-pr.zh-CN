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
ms.openlocfilehash: df3896704565a617ae4f50cfcc9afee29f5f098e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513769"
---
# <a name="location-trend-report-in-lync-server-2013"></a>Lync Server 2013 中的位置趋势报告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-06-06_

位置趋势报告提供网络位置的呼叫质量趋势信息。

<div>

## <a name="filters"></a>筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，位置趋势报告使您能够按访问类型（即内部访问与外部访问）或有线/无线网络连接等条件来筛选返回的数据。您还可以选择数据的分组方式。在此示例中，将按小时、日或周对呼叫进行分组。

下表列出了可用于位置趋势报告的筛选器。

### <a name="location-trend-report-filters"></a>位置趋势报告筛选器

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
<td><p><strong>Interval</strong></p></td>
<td><p>时间间隔。选择下列选项之一：</p>
<ul>
<li><p>每小时（最多可显示 25 个小时）</p></li>
<li><p>每天（最多可显示 31 天）</p></li>
<li><p>每周（最多可显示 12 周）</p></li>
</ul>
<p>如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。例如，如果选择的开始日期为 8/1/2011、结束日期为 9/28/2011、间隔为“每天”，则显示从 8/1/2011 12:00 AM 到 9/1/2011 12:00 AM 这些天的数据（即总共 31 天的数据）。</p></td>
</tr>
<tr class="even">
<td><p><strong>访问类型</strong></p></td>
<td><p>指示客户端在发起呼叫时已登录到内部网络还是外部网络。选择下列选项之一：</p>
<ul>
<li><p>各种</p></li>
<li><p>内部</p></li>
<li><p>外部</p></li>
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
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>指示外部客户端在发起呼叫时是否使用了虚拟专用网 (VPN) 连接。选择下列选项之一：</p>
<ul>
<li><p>各种</p></li>
<li><p>VPN</p></li>
<li><p>非 VPN</p></li>
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

