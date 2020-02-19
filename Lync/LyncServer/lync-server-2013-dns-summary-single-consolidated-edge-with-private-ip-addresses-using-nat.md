---
title: DNS 摘要-使用 NAT 的具有专用 IP 地址的单一合并边缘
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: a7e5d792-f397-45e5-af85-20d0f4bf405f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412787(v=OCS.15)
ms:contentKeyID: 48185025
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71395e8107c2a1fcb5bd999bd49ef73ea556fa13
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 摘要-使用 NAT 的专用 IP 地址的单一合并边缘

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

若要避免路由问题，请确认边缘服务器中至少有两个网络适配器，并且默认网关仅在与外部接口相关联的网络适配器上设置。 例如，如在[使用 Lync Server 2013 的专用 IP 地址和 NAT 的单一](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)合并边缘拓扑图中所示，默认网关将指向外部防火墙（10.45.16.1）。

您可以在边缘服务器中配置两个网络适配器，如下所示：

  - **网络适配器 1（内部接口）**
    
    分配有 172.25.33.10 的内部接口。
    
    未定义默认网关。
    
    确保从包含边缘内部接口的网络的路由到包含运行 Lync Server 2013 或 Lync Server 2013 客户端的服务器的任何网络（例如，从172.25.33.0 到192.168.10.0）。

  - **网络适配器 2（外部接口）**
    
    将向此网络适配器分配三个专用 IP 地址，例如，10.45.16.10（针对访问边缘）、10.45.16.20（针对 Web 会议边缘）和 10.45.16.30（针对 AV 边缘）
    
    <div>
    

    > [!NOTE]
    > 虽然可以对所有三个边缘服务接口使用一个 IP 地址，但不建议这样做。虽然这样能节省 IP 地址，但每个服务需要不同的端口号。默认端口号为 443/TCP，这将确保大多数远程防火墙允许通信。针对访问边缘、Web 会议边缘和 AV 边缘分别将端口值更改为 5061/TCP、444/TCP 和 443/TCP（举例而言）可能导致远程用户遇到问题，即，他们所用的防火墙不允许通过 5061/TCP 和 444/TCP 进行通信。此外，使用三个不同的 IP 地址将使故障排除更加轻松，因为这样能筛选 IP 地址。

    
    </div>
    
    访问边缘 IP 地址是默认网关设置为集成路由器的主要 IP 地址 (10.45.16.1)。
    
    Web 会议和 A/V 边缘 IP 地址是次要 IP 地址。

<div>


> [!TIP]
> 配置具有两个网络适配器的边缘服务器是两个选项之一。 另一种方法是将一个网络适配器用于内部端，将三个网络适配器用于边缘服务器的外部端。 此选项的主要优点是，每个边缘服务器服务都有不同的网络适配器，并且在需要故障排除时有可能更简单的数据收集



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-private-ip-addresses-using-nat-example"></a>带有使用 NAT 的专用 IP 地址的单一合并边缘所需的 DNS 记录（示例）

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
<td><p>访问边缘外部接口 (Contoso) 根据需要对包含启用了 Lync 的用户的所有 SIP 域重复</p></td>
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
> 上表中列出的记录以 <EM>.net</EM> 扩展名或 <EM>.com</EM> 扩展名显示，以便在未使用裂脑 DNS 时突出显示需要驻留这些记录的区域。 如果使用裂脑 DNS，则所有记录将位于同一 <EM>.com</EM> 区域中，唯一的区别在于它们是位于内部还是外部的 DNS 区域版本。 有关详细信息，请参阅<A href="lync-server-2013-determine-dns-requirements.md">确定 Lync Server 2013 的 DNS 要求</A>中的 "裂脑 dns"。



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

