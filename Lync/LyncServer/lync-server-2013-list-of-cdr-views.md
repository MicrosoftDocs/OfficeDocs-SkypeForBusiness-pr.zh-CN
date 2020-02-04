---
title: Lync Server 2013： CDR 视图列表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR views
ms:assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688009(v=OCS.15)
ms:contentKeyID: 49733598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fe2620175c2a706bfb2c48fe7fb380d5fae4c09
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-views-in-lync-server-2013"></a>Lync Server 2013 中的 CDR 视图列表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-01_

视图提供了一种简单的方法来访问有关用于从 CDR 数据库返回数据的最常见方案的信息。 建议使用视图生成自定义报表，而不是使用实际的 CDR 数据库表;这是因为数据库视图更有可能保持与 Lync Server 未来版本的向后兼容性。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>视图名称</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-clientversions-view.md">Lync Server 2013 中的 ClientVersions 视图</a></p></td>
<td><p>返回有关在通信会话中使用的客户端软件/设备的信息。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencemessagecount-view.md">Lync Server 2013 中的 ConferenceMessageCount 视图</a></p></td>
<td><p>返回有关会议中用户发送的邮件数的信息。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-view.md">Lync Server 2013 中的 "会议" 视图</a></p></td>
<td><p>返回会议信息，包括 "开始时间"、"结束时间" 和 "会议组织者"。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-view.md">Lync Server 2013 中的 ConferenceSessionDetails 视图</a></p></td>
<td><p>返回所有会议会话的会话详细信息，包括开始和结束时间、用户 Id、响应代码和诊断 Id。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferenceuris-view.md">Lync Server 2013 中的 ConferenceUris 视图</a></p></td>
<td><p>返回有关会议中使用的会议 Uri 的信息</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errorreport-view.md">Lync Server 2013 中的 ErrorReport 视图</a></p></td>
<td><p>返回有关会话期间发生的错误的信息。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-filetransfers-view.md">Lync Server 2013 中的 FileTransfers 视图</a></p></td>
<td><p>返回有关文件传输会话的信息，包括文件名以及是否接受、拒绝或取消传输。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-focusjoinsandleaves-view.md">Lync Server 2013 中的 FocusJoinsAndLeaves 视图</a></p></td>
<td><p>返回有关会议加入和退出活动的信息。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mcujoinsandleaves-view.md">Lync Server 2013 中的 McuJoinsAndLeaves 视图</a></p></td>
<td><p>返回有关会议加入和退出活动的组合信息（每个会议联接与相应的会议休假配对）。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-view.md">Lync Server 2013 中的 Mcus 视图</a></p></td>
<td><p>返回有关会议服务器的信息。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-view.md">Lync Server 2013 中的 "媒体" 视图</a></p></td>
<td><p>返回有关对等通信会话中使用的媒体类型的信息。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-view.md">Lync Server 2013 中的 ProgressReport 视图</a></p></td>
<td><p>返回有关已完成会话的信息。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-registration-view.md">Lync Server 2013 中的注册视图</a></p></td>
<td><p>返回有关 Lync Server 注册的信息。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 中的 SessionDetails 视图</a></p></td>
<td><p>返回有关对等会话的信息，包括 VoIP-VoIP 电话呼叫、两方 IM 会话或其他对等通信会话。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-user-view.md">Lync Server 2013 中的用户视图</a></p></td>
<td><p>返回有关参与通信会话的用户的信息。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-voipdetails-view.md">Lync Server 2013 中的 VoIPDetails 视图</a></p></td>
<td><p>返回至少涉及一个 VoIP （通过 IO 的语音）用户的对等会话的信息。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

