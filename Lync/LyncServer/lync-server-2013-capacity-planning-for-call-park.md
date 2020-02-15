---
title: Lync Server 2013：呼叫寄存的容量规划
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Call Park
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416493(v=OCS.15)
ms:contentKeyID: 48184529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1192ef9b5b30c722a4f62973cf4992da3ca7300
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a>Lync Server 2013 中呼叫寄存的容量规划

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-13_

<div id="sectionSection0" class="section">

下表介绍了可以用作容量规划要求基础的呼叫寄存用户模型。

<div>


> [!IMPORTANT]  
> 请记住，对于灾难恢复容量规划，配对池的每个池都应该能够处理两个池中的呼叫寄存服务的工作负荷。



</div>

### <a name="call-park-user-model"></a>呼叫寄存用户模型

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>多重</th>
<th>每个前端池（包含8台前端服务器）</th>
<th>每台 Standard Edition Server</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>寄存速率</p></td>
<td><p>每分钟 8 个</p></td>
<td><p>每分钟 1 个</p></td>
</tr>
<tr class="even">
<td><p>取回寄存呼叫的速率</p></td>
<td><p>每分钟 8 个</p></td>
<td><p>每分钟 1 个</p></td>
</tr>
<tr class="odd">
<td><p>平均寄存持续时间</p></td>
<td><p>60 秒。</p></td>
<td><p>60 秒</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

