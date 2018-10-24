---
title: TraceRoute 表
TOCTitle: TraceRoute 表
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205205(v=OCS.15)
ms:contentKeyID: 49314039
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# TraceRoute 表

 

_**上一次修改主题：** 2015-03-09_

TraceRoute 表包含来自呼叫的路由信息。此表是在 Microsoft Lync Server 2013 中引入的。


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
<td><p>代表呼叫中所使用的视频线的类型。允许的值包括：</p>
<ul>
<li><p>0 – 音频</p></li>
<li><p>1 – 视频</p></li>
<li><p>2 – 全景视频</p></li>
<li><p>3 – 应用程序/桌面共享</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>bit</p></td>
<td><p>主</p></td>
<td><p>发起呼叫的终结点。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hop</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>网络跃点/</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddressKey</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>IP 地址的唯一标识符。IP 地址信息存储在 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表</a>中。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RTT</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>来回行程的时间。来回行程的时间会测量语音数据包到达其目标，然后将其所收到的通知发送回来所需的时间量。</p></td>
</tr>
</tbody>
</table>

