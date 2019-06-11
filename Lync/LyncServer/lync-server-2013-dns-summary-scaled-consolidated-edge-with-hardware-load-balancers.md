---
title: DNS 摘要 - 使用硬件负载平衡器的扩展的合并边缘
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 8453297c-da1d-4b9e-a37e-6721458c6feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398670(v=OCS.15)
ms:contentKeyID: 48184700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d411b004edde96314e3c06d7f28a9f9d294688ad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 摘要 - 使用硬件负载平衡器的扩展的合并边缘

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-01-27_

与证书和端口的远程2013访问的 DNS 记录要求相当直接。 此外, 许多记录是可选的, 具体取决于您配置运行 Lync 2013 的客户端的方式以及是否启用联盟。

有关 Lync 2013 DNS 要求的详细信息, 请参阅[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)。

有关配置 Lync 2013 客户端的自动配置的详细信息, 请参阅[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)时, 请参阅 "没有拆分大脑 Dns 的自动配置" 部分。

下表包含支持缩放的合并边缘拓扑 (硬件负载平衡) 所需的 DNS 记录的摘要。 请注意, 仅对于 Lync 客户端的自动配置, 某些 DNS 记录是必需的。 如果你计划使用组策略对象 (Gpo) 配置 Lync 客户端, 则不需要关联的记录。

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>重要提示: Edge 服务器网络适配器要求

为避免路由问题, 请验证边缘服务器中是否至少有两个网络适配器, 并且是否仅在与外部接口关联的网络适配器上设置默认网关。 例如, 如在[Lync Server 2013 中缩放](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)后的合并边缘方案图中显示的硬件负载平衡器, 默认网关将指向外部防火墙。

可以在每个边缘服务器中配置两个网络适配器, 如下所示:

  - **网络适配器 1 (内部接口)**
    
    已分配172.25.33.10 的内部接口。
    
    无默认网关。
    
    确保有一条来自网络的路由, 该网络包含与包含 Lync Server 客户端或运行 Lync Server 的服务器 (例如从172.25.33.0 到 192.168.10.0) 的任何网络的边缘服务器内部接口。

  - **网络适配器 2 (外部接口)**
    
    将三个公共 IP 地址分配给此网络适配器, 例如131.107.155.10 用于访问边缘服务, 131.107.155.20 用于 Web 会议 Edge 服务, 131.107.155.30 用于 A/V 边缘服务。
    
    <div>
    

    > [!NOTE]
    > 分配给边缘服务器的实际外部网络接口的 IP 地址可能取决于你选择的硬件负载平衡器。 请参阅硬件负载平衡器的文档以了解实际 IP 地址要求。<BR>虽然不推荐使用所有三个边缘服务接口的单个 IP 地址, 但也有可能。 虽然这会保存 IP 地址, 但它需要每个服务的不同端口号。 默认端口号为 443/TCP, 这可确保大多数远程防火墙都允许流量。 将端口值更改为 (例如) 访问边缘服务的 5061/tcp 对于 "A/V 边缘" 服务的 "5061/tcp", 对于 A/V 边缘服务的 443/TCP, 可能会导致远程用户出现问题, 在这种情况下, 其背后的防火墙不允许通信5061/TCP 和 444/TCP。 此外, 由于能够筛选 IP 地址, 三个不同的 IP 地址使疑难解答变得更轻松。

    
    </div>
    
    Access Edge 服务 IP 地址是主要的, 默认网关设置为面向 Internet 的路由器 (131.107.155.1)。
    
    Web 会议边缘服务和 A/V 边缘服务 IP 地址是第二。

<div>


> [!TIP]
> 配置具有两个网络适配器的 Edge 服务器是两个选项之一。 另一种选择是将一个网络适配器用于内部端, 将三个网络适配器用于边缘服务器的外部端。 此选项的主要优点是每个边缘服务器服务有一个不同的网络适配器, 并且在需要故障排除时有可能更简洁的数据收集



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a>缩放后的合并边缘所需的 DNS 记录, 硬件负载平衡 (示例)

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
<td><p>外部 DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>131.107.155.10</p></td>
<td><p>Access Edge 服务外部接口 (Contoso)。 根据需要对启用了 Lync 的用户的所有 SIP 域重复此操作</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>网络会议边缘服务外部接口</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
<td><p>A/V 边缘服务外部接口</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/SRV/443</p></td>
<td><p>_sip._tls.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Access Edge 服务外部接口。 需要将 Lync 2013 和 Lync 2010 客户端的自动配置用于外部工作。 根据需要对启用了 Lync 的用户的所有 SIP 域重复此操作。</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>SIP Access Edge 服务用于自动 DNS 发现联盟合作伙伴 (称为 "允许的 SIP 域" (在以前的版本中称为增强联盟) 的外部接口。 对于启用了 Lync 的用户和使用推送通知服务或 Apple 推送通知服务的 Microsoft Lync 移动客户端, 请根据需要重复执行所有 SIP 域。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>统一边缘内部接口</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

