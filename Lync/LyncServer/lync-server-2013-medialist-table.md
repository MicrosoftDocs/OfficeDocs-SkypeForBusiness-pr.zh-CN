---
title: Lync Server 2013： MediaList 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaList table
ms:assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398279(v=OCS.15)
ms:contentKeyID: 48183579
ms.date: 07/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a22ef9b9e0ef429fcac96a7f7d5c87093f79a02
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505719"
---
# <a name="medialist-table-in-lync-server-2013"></a>Lync Server 2013 中的 MediaList 表

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-07-12_

MediaList 表是一个静态表，用于存储各种媒体类型的列表。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>数据类型</th>
<th>键/索引</th>
<th>详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>MediaId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主</p></td>
<td><p>值：1-7</p></td>
</tr>
<tr class="even">
<td><p><strong>Media</strong></p></td>
<td><p>nvarchar (256) </p></td>
<td></td>
<td><p>MediaID 和媒体值的静态映射：</p>
<ul>
<li><p>1– IM</p></li>
<li><p>2 – 文件传输</p></li>
<li><p>3 – 远程协助</p></li>
<li><p>4 – 应用程序共享</p></li>
<li><p>5–音频</p></li>
<li><p>6–视频</p></li>
<li><p>7 – 应用程序邀请</p></li>
</ul></td>
</tr>
</tbody>
</table>


如果您尝试为 SessionDetailsView 中的值确定 LcsCDR 类型，则需要使用以下联接代码段：

    LEFT JOIN on Media.MediaId = MediaList.MediaId

</div>

<span> </span>

</div>

</div>

</div>

