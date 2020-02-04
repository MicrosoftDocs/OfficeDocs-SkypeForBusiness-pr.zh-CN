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
ms.openlocfilehash: 691b7576d59511428400d14a3ff21109525dc5a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="traceroute-table-in-lync-server-2013"></a>Lync Server 2013 中的 TraceRoute 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-02-21_

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
<th><strong>详细信息</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主、外部</p></td>
<td><p>通话开始的日期和时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主、外部</p></td>
<td><p>用于区分可能在同一日期和同一时间开始的多个通话的唯一标识符。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主、外部</p></td>
<td><p>表示通话中使用的视频线路类型。 允许的值包括：</p>
<ul>
<li><p>0-音频</p></li>
<li><p>1-视频</p></li>
<li><p>2-全景视频</p></li>
<li><p>3-应用程序/桌面共享</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>bit</p></td>
<td><p>Primary</p></td>
<td><p>发出呼叫的终结点。</p></td>
</tr>
<tr class="odd">
<td><p><strong>跳</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>网络跃点/</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddressKey</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>IP 地址的唯一标识符。 IP 地址信息存储在<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 的 "IPAddress" 表中</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RTT</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>往返时间。 往返时间测量语音数据包到达其目标所需的时间量，然后发送发送回收到通知的时间。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

