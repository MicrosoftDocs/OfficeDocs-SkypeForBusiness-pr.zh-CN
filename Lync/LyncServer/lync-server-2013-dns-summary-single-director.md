---
title: Lync Server 2013：DNS 摘要 - 单一控制器
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
ms.openlocfilehash: 71fb3052de36a92afb4ed9076820f7fcb2b54997
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-director-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 摘要 - 单一控制器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-20_

下表包含支持单个控制器所需的 DNS 记录的摘要。 Director 的角色需要类似的 DNS 记录作为前端服务器。 所需的记录数反映在 Director 证书所需的主题备用名称中。 与前端服务器不同，控制器不会托管用户帐户或托管移动服务。

### <a name="dns-records-required-for-the-director"></a>Director 所需的 DNS 记录

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
<th>映射到/批注</th>
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
<td><p>来自边缘服务器的内部边缘接口的入站会话初始协议（SIP）</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>控制器</p></td>
<td><p>从反向代理已发布的拨入 web 服务</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>控制器</p></td>
<td><p>已发布通过反向代理的 web 服务</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>控制器</p></td>
<td><p>由 "反向代理 Web 票" 发布和定义的由 Director 的外部 web 服务</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

