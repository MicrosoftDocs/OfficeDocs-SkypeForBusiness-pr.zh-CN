---
title: Lync Server 2013：监视组聊天
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
ms.openlocfilehash: cb82eedd9d9578aeb4120136c1896267cde35392
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051134"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a>在 Lync Server 2013 中监视组聊天

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-08-04_

强烈建议运行 Microsoft 下载中心提供的最新[累积服务器更新安装程序](http://support.microsoft.com/kb/968802)，以提高性能。

如果你正在运行最新的累积更新，请使用以下压力测试表来了解你的组聊天服务器是否以最佳运行状况运行的指标。

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
<td><p>组聊天池中的三组聊天服务器，每个服务器具有 8 GB 内存和8个处理器。</p></td>
</tr>
<tr class="even">
<td><p>企业版中的两个 Lync Server 2013 前端。</p></td>
</tr>
<tr class="odd">
<td><p>在三个组聊天服务器上为60000个并发用户。</p></td>
</tr>
<tr class="even">
<td><p>25000通道由组聊天池承载。</p></td>
</tr>
<tr class="odd">
<td><p>频道大小：</p>
<ul>
<li><p>小频道大小：30</p></li>
<li><p>中等频道大小：150</p></li>
<li><p>大型频道大小：2500</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>频道计数：</p>
<ul>
<li><p>数字小通道：24000</p></li>
<li><p>数字中等通道800</p></li>
<li><p>大型频道数24</p></li>
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
<td><p>用户加入的通道数：</p>
<ul>
<li><p>小：12</p></li>
<li><p>中：2</p></li>
<li><p>大型：1</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>联接率：</p>
<ul>
<li><p>每台服务器总共10次，每个服务器 3.33/秒</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>注销率：</p>
<ul>
<li><p>每台服务器总共10次，每个服务器 3.33/秒</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>聊天速度：</p>
<ul>
<li><p>每个服务器总共20个，每秒 6.66/秒</p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> 使用不同的硬件规范或用户配置文件时，以下性能计数器数可能会有所不同。



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
<th>阙</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Process （ChannelService）-&gt;处理器时间百分比</p></td>
<td><p>最小值：0</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

