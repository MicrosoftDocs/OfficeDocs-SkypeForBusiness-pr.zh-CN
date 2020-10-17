---
title: Lync Server 2013： P2P 摘要子报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: P2P Summary Subreport
ms:assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205416(v=OCS.15)
ms:contentKeyID: 48185950
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee8b2b914779cf8fde4f1e3a58d827dd355d28e7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515989"
---
# <a name="p2p-summary-subreport-in-lync-server-2013"></a>Lync Server 2013 中的 P2P 摘要子报告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-21_

P2P 摘要子报表对失败点对点通信会话提供一个总体视图。

<div>

## <a name="filters"></a>筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于 P2P 摘要子报表的筛选器。

### <a name="p2p-summary-subreport-filters"></a>P2P 摘要子报表筛选器

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
<td><p>时间范围的开始日期和时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>时间范围的结束日期和时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>注册器池或边缘服务器的完全限定域名 (FQDN)。可以选择单个池，也可以单击“[所有]”<strong></strong>查看所有池的数据。系统根据数据库中的记录自动为您填充该下拉列表。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指标

下表列出了 P2P 摘要子报表中提供的信息。

### <a name="p2p-summary-subreport-metrics"></a>P2P 摘要子报告指标

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名称</th>
<th>是否可按此项排序？</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>会话总数</strong></p></td>
<td><p>否</p></td>
<td><p>会话的总数，包括成功的会话、失败的会话（预期失败和意外失败）及未归类的会话。</p></td>
</tr>
<tr class="even">
<td><p><strong>故障率</strong></p></td>
<td><p>否</p></td>
<td><p>失败的点对点会话百分比。</p></td>
</tr>
<tr class="odd">
<td><p><strong>按形式列出的会话</strong></p></td>
<td><p>否</p></td>
<td><p>按形式分组的会话总数（例如，即时消息）。</p></td>
</tr>
<tr class="even">
<td><p><strong>按形式列出的故障率</strong></p></td>
<td><p>否</p></td>
<td><p>按形式分组的失败会话总数（例如，即时消息）。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

