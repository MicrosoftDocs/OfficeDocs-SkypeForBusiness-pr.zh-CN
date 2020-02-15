---
title: Lync Server 2013： DNS 摘要-反向代理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fde945b4bd08020a072f36be073169454e423279
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 摘要-反向代理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-03-22_

可以在反向代理中配置两个网络适配器，如下所示：

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a>反向代理网络适配器要求

  - **网络适配器 1（内部接口）** 示例
    
    分配有 172.25.33.40 的内部接口。
    
    未定义默认网关。
    
    确保从包含反向代理内部接口的网络到包含 Lync Server 前端池服务器的任何网络的路由（例如，从172.25.33.0 到192.168.10.0）。

  - **网络适配器 2（外部接口）** 示例
    
    至少为此网络适配器分配了一个公用 IP 地址。
    
    定义网关以指向外围中的路由器或集成防火墙。（在方案示例中为 10.45.16.1）

### <a name="dns-records-required-for-reverse-proxy"></a>反向代理所需的 DNS 记录

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
<th>FQDN</th>
<th>IP 地址</th>
<th>映射位置/注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>为外部发布的资源分配的侦听器</p></td>
<td><p>来自内部部署的外部 Web 服务。可以为将使用此反向代理且已定义外部 Web 服务的任何 SIP 域的所有池和各个服务器定义和创建附加记录。</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>webdirext.contoso.com</p></td>
<td><p>为外部发布的资源分配的侦听器</p></td>
<td><p>部署中的控制器或控制器池的外部 web 服务。 您可以定义任意多个控制器，因为有不同的控制器，这些控制器可能与其他 SIP 域相关联。</p>
<div>

> [!IMPORTANT]  
> 定义和发布控制器的 DNS 记录不是前端池或控制器决策。 如果您使用的是控制器，则必须定义并发布 Director 和前端池外部 web 服务。 如果在拓扑中定义了特定的流量类型（用于身份验证和其他使用），则会先将其发送给控制器。


</div></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>为外部发布的资源分配的侦听器</p></td>
<td><p>在外部发布的电话拨入式会议</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>为外部发布的资源分配的侦听器</p></td>
<td><p>在外部发布的会议</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>officewebapps01.contoso.com</p></td>
<td><p>为 Office Web Apps Server 分配的侦听器</p></td>
<td><p>Office Web Apps Server 在内部部署或在外围部署，并已发布用于外部客户端访问</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>lyncdiscover.contoso.com</p></td>
<td><p>为外部发布的资源分配的侦听器</p></td>
<td><p>Lync 发现外部发布的自动发现的外部记录，包括移动性、Microsoft Lync Web App 和计划程序 Web 应用</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

