---
title: Lync Server 2013： TraceRoute 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: TraceRoute table
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205205(v=OCS.15)
ms:contentKeyID: 48185242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bc4a6d990c91f87022b041d9478b6dde5a71bb5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="traceroute-table-in-lync-server-2013"></a>Lync Server 2013 中的 TraceRoute 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-02-21_

TraceRoute 表包含来自呼叫的路由信息。 此表是在 Microsoft Lync Server 2013 中引入的。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>列</strong></th>
<th><strong>数据类型</strong></th>
<th><strong>键/索引</strong></th>
<th><strong>Details</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主、外</p></td>
<td><p>呼叫开始的日期和时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主、外</p></td>
<td><p>用来区分可能在相同日期和相同时间开始的多个呼叫的唯一标识符。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主、外</p></td>
<td><p>表示在呼叫中使用的视频行的类型。允许的值包括：</p>
<ul>
<li><p>0–音频</p></li>
<li><p>1–视频</p></li>
<li><p>2 – 全景视频</p></li>
<li><p>3–应用程序/桌面共享</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>位</p></td>
<td><p>主</p></td>
<td><p>发起呼叫的终结点。</p></td>
</tr>
<tr class="odd">
<td><p><strong>跃点</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>网络跃点/</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddressKey</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>IP 地址的唯一标识符。 IP 地址信息存储在<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 的 IPAddress 表中</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RTT</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>来回行程的时间。来回行程的时间会测量语音数据包到达其目标，然后将其所收到的通知发送回来所需的时间量。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

