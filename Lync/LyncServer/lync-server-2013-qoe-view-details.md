---
title: Lync Server 2013： QoE 查看详细信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE view details
ms:assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688081(v=OCS.15)
ms:contentKeyID: 49733677
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5195067fcd02db0be6dd1838af44f5ed51ddb6a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-view-details-in-lync-server-2013"></a>Lync Server 2013 中的 QoE 查看详细信息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-03_

视图涉及有关从 QoE SQL 数据库返回数据的最常见方案。 建议将视图用于生成自定义报告而不是直接访问数据库表；这是因为视图很有可能保留与将来版本的向后兼容性。


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
<td><p><a href="lync-server-2013-audiostreamdetail-view.md">Lync Server 2013 中的 AudioStreamDetail 视图</a></p></td>
<td><p>存储数据库中每个音频流的相关信息。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialine-view.md">Lync Server 2013 中的 MediaLine 视图</a></p></td>
<td><p>存储有关数据库中每个媒体行的信息。 一个音频会话通常包含一个音频媒体行。 一个音频与视频 (A/V) 会话通常包含一个音频媒体行和一个视频媒体行；但是，如果使用了会议设备或库视图，则会话可能包含两个视频媒体行。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-networkconfigurationsettings-view.md">Lync Server 2013 中的 NetworkConfigurationSettings 视图</a></p></td>
<td><p>存储有关网络配置的信息。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-view.md">Lync Server 2013 中的会话视图</a></p></td>
<td><p>存储有关数据库中包含记录的会话的信息。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-view.md">Lync Server 2013 中的 UserAgent 视图</a></p></td>
<td><p>存储有关数据库中包含记录的会话中涉及的用户代理的信息。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostreamdetail-view.md">Lync Server 2013 中的 VideoStreamDetail 视图</a></p></td>
<td><p>存储有关数据库中每个视频流的信息。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

