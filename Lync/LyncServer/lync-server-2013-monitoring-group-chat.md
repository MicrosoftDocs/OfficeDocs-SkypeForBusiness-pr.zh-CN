---
title: Lync Server 2013：监视群组聊天
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720924(v=OCS.15)
ms:contentKeyID: 63969648
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa350924503f430ec0494cc5e1eb17f7878084a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a>在 Lync Server 2013 中监视群组聊天

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-08-04_

强烈建议运行 Microsoft 下载中心提供的最新[累积服务器更新安装程序](http://support.microsoft.com/kb/968802)，以提高性能。

假设你正在运行最新的累积更新，请使用以下压力测试表来了解你的群组聊天服务器是否在最佳运行状况下运行。

### <a name="test-environment-and-user-model"></a>测试环境和用户模型

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>群组聊天池中的三个群组聊天服务器，每个服务器都有 8 GB 内存和8个处理器。</p></td>
</tr>
<tr class="even">
<td><p>企业版中的两个 Lync Server 2013 前端。</p></td>
</tr>
<tr class="odd">
<td><p>60000多个群组聊天服务器上的并行用户。</p></td>
</tr>
<tr class="even">
<td><p>25000通道由群组聊天池托管。</p></td>
</tr>
<tr class="odd">
<td><p>频道大小：</p>
<ul>
<li><p>小频道大小：30</p></li>
<li><p>中等频道大小：150</p></li>
<li><p>大频道大小：2500</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>频道计数：</p>
<ul>
<li><p>数字小型频道：24000</p></li>
<li><p>数字中等通道800</p></li>
<li><p>大量频道24</p></li>
<li><p>通道24824总数</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>邀请频道：</p>
<ul>
<li><p>频道的一半邀请频道</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>用户加入的频道数：</p>
<ul>
<li><p>小：12</p></li>
<li><p>中等：2</p></li>
<li><p>大：1</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>联接费率：</p>
<ul>
<li><p>每台服务器10个总/秒、3.33/秒</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>注销费率：</p>
<ul>
<li><p>每台服务器10个总/秒、3.33/秒</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>聊天费率：</p>
<ul>
<li><p>每个服务器20总/秒、每个服务器 6.66/秒</p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> 当使用不同的硬件规范或用户配置文件时，以下性能计数器数值可能会有所不同。



</div>

### <a name="performance-counter-to-be-monitored"></a>要监视的性能计数器

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>性能计数器</th>
<th>01b</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Process （ChannelService）-&gt;处理器时间百分比</p></td>
<td><p>分钟：0</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

