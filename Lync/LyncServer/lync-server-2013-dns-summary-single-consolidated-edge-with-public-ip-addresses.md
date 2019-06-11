---
title: DNS 摘要 - 使用公用 IP 地址的单一合并边缘
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Single consolidated edge with public IP addresses
ms:assetid: 7b83eae4-aa1a-4cc6-8077-42176d56cab5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205025(v=OCS.15)
ms:contentKeyID: 48184601
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50aae14309e55919eb3f65560cd7cd0e7f1b1283
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a>Lync Server 2013 中的证书摘要 - 使用公用 IP 地址的单一合并边缘

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2017-03-09_

与证书和端口的远程2013访问的 DNS 记录要求相当直接。 此外, 许多记录是可选的, 具体取决于您配置运行 Lync 2013 的客户端的方式以及是否启用联盟。

有关 Lync 2013 DNS 要求的详细信息, 请参阅[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)。

有关运行 Lync 2013 的客户端的自动配置的详细信息 (如果未配置分裂大脑 DNS), 请参阅[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)中的 "没有分裂的 dns 所需的自动配置"。

下表列出了支持单个统一边缘拓扑图中所示的单个统一边缘拓扑所需的 DNS 记录的摘要。 请注意, 只有在自动配置 Lync 2013 和 Lync 2010 客户端时, 才需要某些 DNS 记录。 如果你计划使用组策略对象 (Gpo) 配置 Lync 客户端, 则不需要关联的自动配置记录。

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>重要提示: Edge 服务器网络适配器要求

为避免路由问题, 请验证边缘服务器中是否至少有两个网络适配器, 并且是否仅在与外部接口关联的网络适配器上设置默认网关。 例如, 如在[Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)中具有公共 ip 地址的单个统一边缘拓扑图中显示的单个统一边缘拓扑中, 默认网关将指向 Internet 外围的外部路由器或可提供公共 IP 地址的防火墙。 Edge 服务器接口的网络关系是路由关系, 而不是 NAT 关系。

你可以在 Edge 服务器中配置两个网络适配器, 如下所示:

  - **网络适配器 1 (内部接口)**
    
    已分配172.25.33.10 的内部接口。
    
    未定义默认网关。
    
    请确保从网络中有一个路由, 该网络包含指向运行 Lync Server 2013 或 Lync Server 2013 客户端 (例如从172.25.33.0 到 192.168.10.0) 的服务器的任何网络的边缘内部接口。

  - **网络适配器 2 (外部接口)**
    
    将三个公共 IP 地址分配给此网络适配器, 例如131.107.155.10 用于访问边缘, 131.107.155.20 用于 Web 会议边缘, 131.107.155.30 AV 边缘。
    
    <div>
    

    > [!NOTE]
    > 虽然不推荐使用所有三个边缘服务接口的单个 IP 地址, 但也有可能。 虽然这会保存 IP 地址, 但它需要每个服务的不同端口号。 默认端口号为 443/TCP, 这可确保大多数远程防火墙都允许流量。 将端口值更改为 (例如) 访问边缘的 5061/tcp, 对于 Web 会议边缘的 444/tcp 和 AV 边缘的 443/TCP 可能会导致远程用户出现问题, 在这种情况下, 其背后的防火墙不允许通过 5061/TCP 和 444/TCP 的流量。 此外, 由于能够筛选 IP 地址, 三个不同的 IP 地址使疑难解答变得更轻松。

    
    </div>
    
    访问边缘公共 IP 地址是主要的, 将默认网关设置为公共路由器 (131.107.155.1)。
    
    Web 会议和 A/V 边缘公共 IP 地址是**Internet 协议版本 4 (tcp/IPv4)** 和**internet 协议版本 6 (tcp/IPv6)** 在本地区域的属性的 "**高级**" 部分中的附加 ip 地址**** Windows Server 中的连接属性。

<div>


> [!TIP]
> 配置具有两个网络适配器的 Edge 服务器是两个选项之一。 另一种选择是将一个网络适配器用于内部端, 将三个网络适配器用于边缘服务器的外部端。 此选项的主要优点是每个边缘服务器服务有一个不同的网络适配器, 并且在需要故障排除时有可能更简洁的数据收集



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-public-ip-addresses-example"></a>具有公共 IP 地址的单个统一边缘所需的 DNS 记录 (示例)

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
<td><p>允许启用 Lync 的用户的所有 SIP 域的访问边缘外部接口 (Contoso) 都有必要重复</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>网络会议边缘外部界面</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
<td><p>A/V 边缘外部接口</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/SRV/443</p></td>
<td><p>_sip._tls.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>访问边缘外部接口。 需要将 Lync 2013 和 Lync 2010 客户端的自动配置用于外部工作。 根据需要对启用了 Lync 的用户的所有 SIP 域重复此操作。</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>SIP 访问边缘外部接口, 用于自动 DNS 发现称为 "允许的 SIP 域" 的联盟伙伴 (在以前的版本中称为 "增强联盟")。根据需要对启用了 Lync 的用户的所有 SIP 域重复此操作</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>统一边缘内部接口</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> 使用<EM>.net</EM>扩展或<EM>.com</EM>扩展名显示上表中列出的记录, 以突出显示要在不使用分裂的 DNS 时需要驻留的区域。 如果使用的是分裂大脑 DNS, 则所有记录将位于同一区域中, 唯一的区别是它们是否位于内部或外部版本中。 有关详细信息, 请参阅<A href="lync-server-2013-determine-dns-requirements.md">确定 Lync Server 2013 的 DNS 要求</A>中的 "分裂大脑 dns"。



</div>

</div>

<div>

## <a name="records-required-for-federation"></a>联盟所需的记录


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
<th>IP 地址/FQDN 主机记录</th>
<th>映射到/批注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>SIP 访问边缘外部接口, 将联合身份验证自动 DNS 发现到其他潜在的联合合作伙伴, 并称为 "允许的 SIP 域" (在以前的版本中称为增强联盟)。根据需要对启用了 Lync 的用户的所有 SIP 域重复此操作</p>



> [!IMPORTANT]
> 移动和推送通知交换所需要此 SRV 记录

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a>可扩展消息和状态协议的 DNS 摘要


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
<th>IP 地址/FQDN 主机记录</th>
<th>映射到/批注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/SRV/5269</p></td>
<td><p>_xmpp-server._tcp.contoso.com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>"访问边缘服务" 或 "边缘池" 上的 XMPP 代理外部接口。对于启用了 Lync 的用户, 通过全局策略、用户所在的网站策略或应用了用户策略的用户策略, 可对所有内部 SIP 域进行必要的操作, 并允许使用启用了 Lync 的用户使用 XMPP 联系人。启用 Lync 的用户。 还必须在 XMPP 联盟合作伙伴策略中配置允许的 XMPP 域。 有关其他详细信息, 请参阅<strong>另请参阅</strong>中的主题</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>xmpp.contoso.com (例如)</p></td>
<td><p>边缘服务器上的访问边缘服务的 IP 地址或托管 XMPP 代理的边缘池的 IP 地址</p></td>
<td><p>指向托管 XMPP 代理服务的访问边缘服务或边缘池。 通常, 你创建的 SRV 记录将指向此主机 (A 或 AAAA) 记录</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

