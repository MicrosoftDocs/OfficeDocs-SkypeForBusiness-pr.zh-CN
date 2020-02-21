---
title: Lync Server 2013：移动性的 DNS 要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for mobility
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48185624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85ceddef859ebc24168c12fdf0721448c6d2b658
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208871"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a>具有 Lync Server 2013 的移动性的 DNS 要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-13_

在部署 Lync Server 2013 移动功能时，可以使用 Microsoft Lync Server 2013 自动发现服务中提供的新 Url，也可以使用现有的 Web 服务 Url。 如果您使用现有的 Url，则用户需要在其移动设备设置中手动输入 Url。 此选项通常用于故障排除。 使用新 Url 时，移动客户端可以自动发现 Lync Server 2013 资源。 当您支持自动发现时，您需要添加新的域名系统（DNS）记录。 本节介绍了自动发现所需的 DNS 记录。

若要支持自动发现，您需要为每个 SIP 域创建以下 DNS 记录：

  - 支持从组织网络内部进行连接的移动用户的内部 DNS 记录

  - 支持从 Internet 进行连接的移动用户的外部或公共 DNS 记录

应无法从网络外部对内部自动发现 URL 进行寻址。 应无法从网络内部对外部自动发现 URL 进行寻址。 但是，如果您无法满足外部 URL 的此要求，则移动客户端功能不应受到影响。

DNS 记录可以是 CNAME 记录或 A（主机）记录。

**内部 DNS 记录**

您需要创建以下内部 DNS 记录之一：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>记录类型</th>
<th>主机名或 SRV 定义</th>
<th>解析为</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscoverinternal..&lt;sipdomain&gt;</p></td>
<td><p>如果你拥有控制器池的内部 Web 服务完全限定域名（FQDN）（如果有），或者对于你的前端池，如果你没有控制器，则为该域名（FQDN）。</p></td>
</tr>
<tr class="even">
<td><p>A（主机）</p></td>
<td><p>lyncdiscoverinternal..&lt;sipdomain&gt;</p></td>
<td><p>如果你拥有控制器池的内部 Web 服务 IP 地址（虚拟 IP （VIP）地址）（如果你有一个或多个前端池）（如果你没有控制器），则为该地址（VIP）地址）。</p></td>
</tr>
</tbody>
</table>


**外部 DNS 记录**

您需要创建下列外部 DNS 记录之一：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>记录类型</th>
<th>主机名</th>
<th>解析为</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>如果你拥有控制器池的外部 Web 服务 FQDN （如果有），或者如果你没有控制器，则为你的前端池</p></td>
</tr>
<tr class="even">
<td><p>A（主机）</p></td>
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>反向代理的外部或公共 IP 地址（如果使用负载平衡器，则为 VIP 地址）</p></td>
</tr>
<tr class="odd">
<td><p>SRV</p></td>
<td><p>_sipfederationtls _tcp。 &lt;sipdomain&gt;</p>
<p>解析为访问边缘服务的主机（A 或 AAAA）记录</p></td>
<td><p>若要支持推送通知服务和 Apple 推送通知服务，请为拥有 Microsoft Lync 移动客户端的每个 SIP 域创建一个 SRV 记录。</p>
<div>

> [!IMPORTANT]  
> 此要求仅适用于基于 Apple 或 Microsoft 的移动设备上的 Microsoft Lync 移动客户端。 Andriod 和 Nokia Symbian 设备不使用推送通知。


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Lyncdiscover. 也称为自动发现，流量通过反向代理。 SRV 记录指向通过访问边缘服务解析的记录。



</div>

</div>

<span> </span>

</div>

</div>

</div>

