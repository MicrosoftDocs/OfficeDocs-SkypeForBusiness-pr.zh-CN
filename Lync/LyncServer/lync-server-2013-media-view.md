---
title: Lync Server 2013：媒体视图
description: Lync Server 2013：媒体视图。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media view
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49733570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74643986b12a30b1055a46a37febf90eeb70c514
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558008"
---
# <a name="media-view-in-lync-server-2013"></a>Lync Server 2013 中的媒体视图

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-01_

“媒体”视图存储有关在对等会话中使用的一种媒体类型的信息。 如果使用多个媒体类型，则一个会话由表中的多条记录表示。 此视图是在 Microsoft Lync Server 2013 中引入的。

<div>


> [!NOTE]  
> “媒体”视图不应用来计算会话的媒体持续时间。此视图包含会话中的媒体交换信号详情。媒体交换通过 INVITE 请求实现，StartTime 指示发出 INVITE 的时间。邀请时间不一定表示媒体的启动时间，因为仅在会话被接受后，媒体才启动。



</div>

媒体视图中包含 SessionDetails 视图中的所有列（在 [Lync Server 2013](lync-server-2013-sessiondetails-view.md) 中）以及下面列出的列。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>数据类型</th>
<th>详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Media</strong></p></td>
<td><p>nvarchar (256) </p></td>
<td><p>媒体类型。 有关详细信息，请参阅 <a href="lync-server-2013-medialist-table.md">Lync Server 2013 中的 MediaList 表</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>MediaStartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>发出媒体请求的时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>会话的结束时间。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

