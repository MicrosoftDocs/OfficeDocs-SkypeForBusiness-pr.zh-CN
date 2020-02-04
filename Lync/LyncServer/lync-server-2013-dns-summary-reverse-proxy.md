---
title: Lync Server 2013：DNS 摘要 - 反向代理
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
ms.openlocfilehash: ae4834ce608f6726403e8742a4d506b173309b35
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 摘要 - 反向代理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-03-22_

您在反向代理服务器中配置两个网络适配器，如下所示：

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a>反向代理网络适配器要求

  - **网络适配器1（内部接口）** 示例
    
    已分配172.25.33.40 的内部接口。
    
    未定义默认网关。
    
    确保存在从网络到包含 Lync Server 前端池服务器（例如从172.25.33.0 到192.168.10.0）的反向代理内部接口的路由。

  - **网络适配器2（外部接口）** 示例
    
    至少有一个公共 IP 地址分配给此网络适配器。
    
    网关定义为指向外部外围设备中的路由器或集成防火墙。 （10.45.16.1 在方案示例中）

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
<th>映射到/批注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>分配给外部已发布资源的侦听器</p></td>
<td><p>内部部署中的外部 web 服务。 对于将使用此反向代理的任何 SIP 域，可以为所有池和单个服务器定义和创建其他记录，并且已定义外部 web 服务。</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>webdirext.contoso.com</p></td>
<td><p>分配给外部已发布资源的侦听器</p></td>
<td><p>部署中的控制器或控制器池的外部 web 服务。 你可以定义任意多个控制器，因为不同的控制器可能与其他 SIP 域相关联。</p>
<div>

> [!IMPORTANT]  
> 定义和发布控制器的 DNS 记录既不是前端池，也不是控制器决策。 如果您使用的是董事，则必须定义和发布 Director 和前端池外部 web 服务。 特定流量类型（用于身份验证和其他使用）将首先发送给 Director，前提是它在拓扑中定义。


</div></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>分配给外部已发布资源的侦听器</p></td>
<td><p>外部发布的电话拨入式会议</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>分配给外部已发布资源的侦听器</p></td>
<td><p>外部发布的会议</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>officewebapps01.contoso.com</p></td>
<td><p>已分配 Office Web Apps 服务器侦听器</p></td>
<td><p>Office Web Apps 服务器内部部署或在外围部署，并且已发布外部客户端访问</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>lyncdiscover.contoso.com</p></td>
<td><p>分配给外部已发布资源的侦听器</p></td>
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

