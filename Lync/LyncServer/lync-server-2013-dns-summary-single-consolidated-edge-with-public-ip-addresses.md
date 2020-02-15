---
title: DNS 摘要-使用公用 IP 地址的单一合并边缘
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single consolidated edge with public IP addresses
ms:assetid: 7b83eae4-aa1a-4cc6-8077-42176d56cab5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205025(v=OCS.15)
ms:contentKeyID: 48184601
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d78bcb5733b2630ad69ebc7686885625ce6ed13
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 摘要-使用公用 IP 地址的单一合并边缘

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2017-03-09_

与证书和端口相比，远程访问 Lync Server 2013 的 DNS 记录要求相当简单。 此外，许多记录是可选的，具体取决于如何配置运行 Lync 2013 的客户端以及是否启用联盟。

有关 Lync 2013 DNS 要求的详细信息，请参阅[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)。

若要详细了解如何自动配置运行 Lync 2013 的客户端，请参阅[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)中的 "自动配置而不拆分大脑 dns"。

下表包含 DNS 记录的摘要，支持单个合并边缘拓扑图中显示的单个合并边缘拓扑时需要这些 DNS 记录。 请注意，只有在自动配置 Lync 2013 和 Lync 2010 客户端时，才需要某些 DNS 记录。 如果您计划使用组策略对象（Gpo）来配置 Lync 客户端，则不需要关联的自动配置记录。

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>重要说明：边缘服务器网络适配器要求

若要避免路由问题，请确认边缘服务器中至少有两个网络适配器，并且默认网关仅在与外部接口相关联的网络适配器上设置。 例如，如在具有公共 IP 地址的单一合并边缘拓扑中，在[Lync Server 2013 中使用公用 ip 地址](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)的单一合并边缘拓扑图中所示，默认网关将指向 Internet 外围的外部路由器或可提供公用 ip 地址的防火墙。 边缘服务器接口的网络关系是路由关系，而不是 NAT 关系。

您可以在边缘服务器中配置两个网络适配器，如下所示：

  - **网络适配器 1（内部接口）**
    
    分配有 172.25.33.10 的内部接口。
    
    未定义默认网关。
    
    确保从包含边缘内部接口的网络的路由到包含运行 Lync Server 2013 或 Lync Server 2013 客户端的服务器的任何网络（例如，从172.25.33.0 到192.168.10.0）。

  - **网络适配器 2（外部接口）**
    
    三个公共 IP 地址将分配到此网络适配器，例如为访问边缘分配 131.107.155.10，为 Web 会议边缘分配 131.107.155.20，为 AV 边缘分配 131.107.155.30。
    
    <div>
    

    > [!NOTE]
    > 可以为所有三个边缘服务接口使用一个 IP 地址，但不建议这样做。尽管这样可以节省 IP 地址，但需要为每个服务使用不同端口号。默认端口号为 443/TCP，它可确保大多数远程防火墙将允许流量通过。对于远程用户（支持这些用户的防火墙不允许 5061/TCP 和 444/TCP 上的流量通过），为访问边缘将端口值更改为（比如）5061/TCP、为 Web 会议边缘将端口值更改为 444/TCP 以及为 AV 边缘将端口值更改为 443/TCP 可能导致问题。另外，由于能够筛选 IP 地址，因此使用三个不同的 IP 地址更便于排除故障。

    
    </div>
    
    访问边缘公共 IP 地址是默认网关设置为公共路由器的主要 IP 地址 (131.107.155.1)。
    
    Web 会议和 A/V 边缘公共 IP 地址是 Windows Server 中**本地区域连接属性**的 **Internet 协议版本 4 (TCP/IPv4)** 和 **Internet 协议版本 6 (TCP/IPv6)** 属性的**高级** 部分中的其他 IP 地址。

<div>


> [!TIP]
> 配置具有两个网络适配器的边缘服务器是两个选项之一。 另一种方法是将一个网络适配器用于内部端，将三个网络适配器用于边缘服务器的外部端。 此选项的主要优点是，每个边缘服务器服务都有不同的网络适配器，并且在需要故障排除时有可能更简单的数据收集



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-public-ip-addresses-example"></a>单个合并边缘所需的 DNS 记录和公共 IP 地址（示例）

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
<td><p>访问边缘外部接口 (Contoso) 根据需要为启用 Lync 的用户的所有 SIP 域重复使用</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>Web 会议边缘外部接口</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
<td><p>A/V 边缘外部接口</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/SRV/443</p></td>
<td><p>_sip _tls .com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>访问边缘外部接口。 将 Lync 2013 和 Lync 2010 客户端的自动配置用于外部工作是必需的。 根据需要为启用 Lync 的用户的所有 SIP 域重复使用。</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls _tcp .com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>SIP 访问边缘外部接口用于实现称为“允许的 SIP 域”的联盟伙伴（在以前版本中称为增强联盟）的自动 DNS 发现。根据需要为启用 Lync 的用户的所有 SIP 域重复使用</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>合并边缘内部接口</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> 上表中列出的记录以 <EM>.net</EM> 扩展名或 <EM>.com</EM> 扩展名显示，以便在未使用裂脑 DNS 时突出显示需要驻留这些记录的区域。 如果使用裂脑 DNS，则所有记录将位于同一区域中，唯一的区别在于它们是位于内部版本还是外部版本。 有关详细信息，请参阅<A href="lync-server-2013-determine-dns-requirements.md">确定 Lync Server 2013 的 DNS 要求</A>中的 "裂脑 dns"。



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
<th>映射位置/注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls _tcp .com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>用于实现与其他潜在联盟伙伴的联盟的自动 DNS 发现的 SIP 访问边缘外部接口，称为“允许的 SIP 域”（在以前版本中称为增强联盟）。必要时对带有启用了 Lync 的用户的所有 SIP 域重复</p>



> [!IMPORTANT]
> 移动性和推送通知交换所需要此 SRV 记录

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a>可扩展消息传递和状态协议的 DNS 摘要


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
<th>映射目标/注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/SRV/5269</p></td>
<td><p>_xmpp-_tcp .com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>访问边缘服务或边缘池上的 XMPP 代理外部接口。根据需要对启用了 Lync 的用户使用通过全局策略、用户所在的网站策略或应用于 XMPP 联系人的外部访问策略的配置，对所有内部 SIP 域重复此操作。启用了 Lync 的用户。 还必须在 XMPP 联盟伙伴策略中配置允许的 XMPP 域。 有关其他详细信息，请参阅<strong>另请参阅</strong>主题中的主题</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>xmpp.contoso.com（举例）</p></td>
<td><p>边缘服务器或边缘池托管 XMPP 代理上的访问边缘服务的 IP 地址</p></td>
<td><p>指向承载 XMPP 代理服务的访问边缘服务或边缘池。 一般而言，您创建的 SRV 记录将指向此主机（A 或 AAAA）记录</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

