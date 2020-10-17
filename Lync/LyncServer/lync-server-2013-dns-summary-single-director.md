---
title: Lync Server 2013： DNS 摘要-单一控制器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single Director
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205021(v=OCS.15)
ms:contentKeyID: 48184568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1eaaebf1fb695bc1ee6ea1b86f980a666cf0a70
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515529"
---
# <a name="dns-summary---single-director-in-lync-server-2013"></a>DNS 摘要-Lync Server 2013 中的单个控制器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-20_

下表列出了支持单个控制器所需的 DNS 记录的摘要。 Director 的角色需要类似的 DNS 记录作为前端服务器。 所需的记录数反映在控制器证书所需的主题替代名称中。 与前端服务器不同，控制器不承载用户帐户或承载移动服务。

### <a name="dns-records-required-for-the-director"></a>控制器所需的 DNS 记录

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
<td><p>用于复制和服务器到服务器的控制器主机记录</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>控制器</p></td>
<td><p>来自边缘服务器的内部边缘接口 (SIP) 的入站会话初始协议</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>控制器</p></td>
<td><p>反向代理中的已发布电话拨入式 Web 服务</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>控制器</p></td>
<td><p>反向代理中的已发布的会议 Web 服务</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>控制器</p></td>
<td><p>由 Director 的反向代理 Web 票证外部 web 服务发布和定义</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

