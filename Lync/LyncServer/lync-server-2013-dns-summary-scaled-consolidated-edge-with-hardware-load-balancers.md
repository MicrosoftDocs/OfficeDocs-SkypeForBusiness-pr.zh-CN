---
title: DNS 摘要-使用硬件负载平衡器的扩展的合并边缘
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 8453297c-da1d-4b9e-a37e-6721458c6feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398670(v=OCS.15)
ms:contentKeyID: 48184700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95ab0c9b68d21af782570c850642ce7e83b996d8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036874"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 摘要-使用硬件负载平衡器的扩展的合并边缘

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-01-27_

与证书和端口相比，远程访问 Lync Server 2013 的 DNS 记录要求相当简单。 此外，许多记录是可选的，具体取决于如何配置运行 Lync 2013 的客户端以及是否启用联盟。

有关 Lync 2013 DNS 要求的详细信息，请参阅[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)。

有关如何配置 Lync 2013 客户端的自动配置的详细信息，请参阅[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)中的 "自动配置，而不拆分大脑 dns" 部分。

下表包含支持“扩展的合并边缘拓扑（硬件负载已平衡）”图所需的 DNS 记录的摘要。 请注意，只有 Lync 客户端的自动配置需要某些 DNS 记录。 如果您计划使用组策略对象（Gpo）来配置 Lync 客户端，则不需要关联的记录。

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>重要说明：边缘服务器网络适配器要求

若要避免路由问题，请确认边缘服务器中至少有两个网络适配器，并且默认网关仅在与外部接口相关联的网络适配器上设置。 例如，如在 Lync Server 2013 中的扩展的合并边缘方案中，在[使用硬件负载平衡](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)器的扩展合并边缘方案中，默认网关将指向外部防火墙。

您可以在每个边缘服务器中配置两个网络适配器，如下所示：

  - **网络适配器 1（内部接口）**
    
    分配有 172.25.33.10 的内部接口。
    
    无默认网关。
    
    确保从网络中有一个路由，该网络包含向包含 Lync Server 客户端或运行 Lync Server 的服务器的任何网络（例如，从172.25.33.0 到192.168.10.0）的边缘服务器内部接口。

  - **网络适配器 2（外部接口）**
    
    向此网络适配器分配三个公共 IP 地址，例如 131.107.155.10 for Access Edge service、131.107.155.20 for Web 会议边缘服务、131.107.155.30 for A/V Edge 服务。
    
    <div>
    

    > [!NOTE]
    > 分配给边缘服务器的实际外部网络接口的 IP 地址可能取决于所选的硬件负载平衡器。 请参阅您的硬件负载平衡器的文档以了解实际 IP 地址要求。<BR>可以为所有三个边缘服务接口使用一个 IP 地址，但不建议这样做。 尽管这样可以节省 IP 地址，但需要为每个服务使用不同端口号。 默认端口号为 443/TCP，它可确保大多数远程防火墙将允许流量通过。 如果将端口值更改为（例如）访问边缘服务的 5061/TCP，则 Web 会议边缘服务的 444/tcp 和 A/V 边缘服务的 443/TCP 可能会导致远程用户出现问题，在该用户背后的防火墙不允许通过 5061/TCP 和 444/TCP 的流量。 另外，由于能够筛选 IP 地址，因此使用三个不同的 IP 地址更便于排除故障。

    
    </div>
    
    访问边缘服务 IP 地址主要是将默认网关设置为面向 Internet 的路由器（131.107.155.1）。
    
    Web 会议边缘服务和 A/V 边缘服务 IP 地址（第二个）。

<div>


> [!TIP]
> 配置具有两个网络适配器的边缘服务器是两个选项之一。 另一种方法是将一个网络适配器用于内部端，将三个网络适配器用于边缘服务器的外部端。 此选项的主要优点是，每个边缘服务器服务都有不同的网络适配器，并且在需要故障排除时有可能更简单的数据收集



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a>扩展的合并边缘（硬件负载已平衡）所需的 DNS 记录（示例）

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
<td><p>外部 DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>131.107.155.10</p></td>
<td><p>访问边缘服务外部接口（Contoso）。 根据需要为启用 Lync 的用户的所有 SIP 域重复使用</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>Web 会议边缘服务外部接口</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
<td><p>A/V 边缘服务外部接口</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/SRV/443</p></td>
<td><p>_sip _tls .com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>访问边缘服务外部接口。 将 Lync 2013 和 Lync 2010 客户端的自动配置用于外部工作是必需的。 根据需要为启用 Lync 的用户的所有 SIP 域重复使用。</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls _tcp .com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>SIP 访问边缘服务联合合作伙伴（称为 "允许的 SIP 域"）的自动 DNS 发现所需的外部接口（在以前的版本中称为 "增强联盟"）。 对于启用了 Lync 的用户和使用推送通知服务或 Apple 推送通知服务的 Microsoft Lync 移动客户端的所有 SIP 域，请按需重复执行此操作。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>合并边缘内部接口</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

