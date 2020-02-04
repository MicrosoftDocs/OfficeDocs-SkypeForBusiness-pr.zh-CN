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
ms.openlocfilehash: d47fb90b7ffb9eb0cb7fcd1631a0f00ca249276a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724602"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-view-details-in-lync-server-2013"></a>QoE 在 Lync Server 2013 中查看详细信息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-03_

视图涵盖从 QoE SQL 数据库返回数据的最常见方案。 推荐用于构建自定义报表的视图，而不是直接访问数据库表;这是因为视图更有可能保持与未来版本的向后兼容性。


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
<td><p>存储有关数据库中每个音频流的信息。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialine-view.md">Lync Server 2013 中的 MediaLine 视图</a></p></td>
<td><p>存储有关数据库中每个媒体行的信息。 一个音频会话通常包含一个音频媒体行。 一个音频和视频（A/V）会话通常包含一个音频媒体线和一个视频媒体行;但是，如果使用了会议设备或使用了库视图，则会话可能包含两个视频媒体线。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-networkconfigurationsettings-view.md">Lync Server 2013 中的 NetworkConfigurationSettings 视图</a></p></td>
<td><p>存储有关网络配置的信息。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-view.md">Lync Server 2013 中的 "会话" 视图</a></p></td>
<td><p>存储有关在数据库中具有记录的会话的信息。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-view.md">Lync Server 2013 中的 UserAgent 视图</a></p></td>
<td><p>存储有关在数据库中具有记录的会话中涉及的用户代理的信息。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostreamdetail-view.md">Lync Server 2013 中的 VideoStreamDetail 视图</a></p></td>
<td><p>存储有关数据库中的每个视频流的信息。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

