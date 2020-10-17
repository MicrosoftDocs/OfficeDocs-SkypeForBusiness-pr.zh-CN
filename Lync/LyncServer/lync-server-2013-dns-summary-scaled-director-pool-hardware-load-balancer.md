---
title: Lync Server 2013： DNS 摘要-扩展的控制器池、硬件负载平衡器
description: Lync Server 2013： DNS 摘要-扩展的控制器池、硬件负载平衡器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled Director pool, hardware load balancer
ms:assetid: 08ba48e6-bfa1-4ab0-bc89-d58ddb9c20af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204655(v=OCS.15)
ms:contentKeyID: 48183340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7198e6a97feed8ce70cb16753ad1f21d58ef246c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555878"
---
# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 摘要-扩展的控制器池、硬件负载平衡器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-20_

下表列出了支持硬件负载平衡控制器所需的 DNS 记录的摘要。 Director 的角色需要类似的 DNS 记录作为前端服务器。 所需的记录数反映在控制器证书所需的主题替代名称中。 与前端服务器不同，控制器池不承载用户帐户或承载移动服务。

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a>使用硬件负载平衡器和 DNS 负载平衡的控制器池所需的 DNS 记录

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>位置/类型/端口</th>
<th>FQDN/DNS 记录</th>
<th>IP 地址/FQDN</th>
<th>映射位置/注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部 DNS/A</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>控制器</p></td>
<td><p>用于复制和服务器到服务器通信的控制器主机记录</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>控制器池 HLB VIP</p></td>
<td><p>DNS 负载平衡控制器池的主机记录</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>控制器池 HLB VIP</p></td>
<td><p>来自边缘服务器的内部接口的入站会话初始协议 (SIP) </p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>控制器池 HLB VIP</p></td>
<td><p>反向代理发布的经过硬件负载平衡的 dialin Web 服务</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>控制器池 HLB VIP</p></td>
<td><p>反向代理发布的经过硬件负载平衡的 meet Web 服务</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>控制器池 HLB VIP</p></td>
<td><p>由反向代理发布和定义，经过硬件负载平衡的用于控制器池的 Web Ticket 外部 Web 服务</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

