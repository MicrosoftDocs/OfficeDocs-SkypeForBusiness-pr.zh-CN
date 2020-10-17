---
title: Lync Server 2013：响应组的容量规划
description: Lync Server 2013：响应组的容量规划。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48184951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78c543f558f67deaaeb781b308aa5f68d39cd785
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544428"
---
# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a>Lync Server 2013 中的响应组的容量规划

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-29_

<div id="sectionSection0" class="section">

下表介绍了可以用作容量规划要求基础的响应组用户模型。

<div>


> [!NOTE]  
> 下表中的数值假定所有响应组音频文件使用的是 16 kHz、单声道、16 位的 Wave (.wav) 文件。如果使用其他文件格式（如 Windows Media 音频 (.wma)），则数值可能会有所不同。



</div>

<div>


> [!IMPORTANT]  
> 请记住，对于灾难恢复容量规划，一对池中的每一个池都应能处理这两个池中的所有响应组的工作负荷。



</div>

### <a name="response-group-user-model"></a>响应组用户模型

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>跃点数</th>
<th>每个 Enterprise Edition 池 (与8台前端服务器) </th>
<th>每台 Standard Edition Server</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>每秒传入的呼叫数</p></td>
<td><p>16 </p></td>
<td><p>双面</p></td>
</tr>
<tr class="even">
<td><p>连接到 IVR 或 MoH 的并发呼叫数</p></td>
<td><p>480</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>并发的匿名会话数（无 IM）</p></td>
<td><p>224</p></td>
<td><p>28</p></td>
</tr>
<tr class="even">
<td><p>并发的匿名会话数（具有 IM）</p></td>
<td><p>64</p></td>
<td><p>8 </p></td>
</tr>
<tr class="odd">
<td><p>活动代理数（正式和非正式）</p></td>
<td><p>1200</p></td>
<td><p>1200</p></td>
</tr>
<tr class="even">
<td><p>智能寻线数</p></td>
<td><p>400</p></td>
<td><p>400</p></td>
</tr>
<tr class="odd">
<td><p>IVR 组数（使用语音识别）</p></td>
<td><p>200</p></td>
<td><p>200</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

