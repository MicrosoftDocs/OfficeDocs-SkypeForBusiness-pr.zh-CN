---
title: Lync Server 2013： DNS 摘要-扩展的合并边缘（使用公用 IP 地址进行 DNS 负载平衡）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: dc8f096a-a0a4-4f71-8930-88ff8fc089d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205319(v=OCS.15)
ms:contentKeyID: 48185594
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eaa466792de1adcd3d048c946c7b36803fbaab63
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501299"
---
# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 摘要-扩展的合并边缘（使用公用 IP 地址进行 DNS 负载平衡）

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2017-03-09_

与证书和端口相比，远程访问 Lync Server 2013 的 DNS 记录要求相当简单。 此外，许多记录是可选的，具体取决于如何配置运行 Lync 2013 的客户端以及是否启用联盟。

有关 Lync 2013 DNS 要求的详细信息，请参阅 [确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)。

有关如何配置 Lync 2013 客户端的自动配置的详细信息，请参阅 [确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)中的 "自动配置，而不拆分大脑 dns" 部分。

下表包含 DNS 记录的摘要，支持单个合并边缘拓扑图中显示的单个合并边缘拓扑时需要这些 DNS 记录。 请注意，只有在自动配置 Lync 2013 客户端时，才需要某些 DNS 记录。 如果您计划使用组策略对象 (Gpo) 来配置 Lync 客户端，则不需要关联的记录。

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>重要说明：边缘服务器网络适配器要求

若要避免路由问题，请确认边缘服务器中至少有两个网络适配器，并且默认网关仅在与外部接口相关联的网络适配器上设置。 例如，如扩展合并边缘的扩展合并边缘方案中所示 [，在 Lync Server 2013 中使用公用 IP 地址进行 DNS 负载平衡](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md) ，默认网关将指向外部防火墙。

您可以在每台边缘服务器中配置两个网络适配器，如下所示：

  - **网络适配器 1 - 节点 1（内部接口）**
    
    分配有 172.25.33.10 的内部接口。
    
    未定义默认网关。
    
    确保从包含边缘内部接口的网络的路由到包含运行 Lync Server 2013 或 Lync Server 2013 客户端的服务器的任何网络 (例如，从172.25.33.0 到 192.168.10.0) 。

  - **网络适配器 1 - 节点 2（内部接口）**
    
    分配有 172.25.33.11 的内部接口。
    
    未定义默认网关。
    
    确保从包含边缘内部接口的网络的路由到包含运行 Lync Server 2013 或 Lync Server 2013 客户端的服务器的任何网络 (例如，从172.25.33.0 到 192.168.10.0) 。

  - **网络适配器 2 - 节点 1（外部接口）**
    
    向此网络适配器分配了三个专用 IP 地址，例如 131.107.155.10 for Access Edge service、131.107.155.20 for Web 会议边缘服务、131.107.155.30 for A/V Edge 服务。
    
    访问边缘服务公用 IP 地址是主要的，默认网关设置为公用路由器 (131.107.155.1) 。
    
    Web 会议边缘服务和 A/V 边缘服务专用 IP 地址是 Windows Server 中**本地连接属性**的**internet 协议版本 4 (tcp/IPv4) **和**INTERNET 协议版本 6 (tcp/IPv6) **属性的 "**高级**" 部分中的其他 IP 地址。
    
    <div>
    

    > [!NOTE]  
    > 可以为所有三个边缘服务接口使用一个 IP 地址，但不建议这样做。 尽管这样可以节省 IP 地址，但需要为每个服务使用不同端口号。 默认端口号为 443/TCP，它可确保大多数远程防火墙将允许流量通过。 将端口值更改为 (例如，访问边缘服务的) 5061/TCP、A/V 边缘服务的 444/tcp （A/V 边缘服务的 444/tcp）可能会导致远程用户出现问题，在该用户背后的防火墙不允许通过 5061/TCP 和 444/TCP 的流量。 另外，由于能够筛选 IP 地址，因此使用三个不同的 IP 地址更便于排除故障。

    
    </div>

  - **网络适配器 2 - 节点 2（外部接口）**
    
    向此网络适配器分配了三个专用 IP 地址，例如 131.107.155.11 for Access Edge service、131.107.155.21 for Web 会议边缘服务、131.107.155.31 for A/V Edge 服务。
    
    访问边缘服务公用 IP 地址是主要的，默认网关设置为公用路由器 (131.107.155.1) 。
    
    Web 会议边缘服务和 A/V 边缘服务专用 IP 地址是 Windows Server 中**本地连接属性**的**internet 协议版本 4 (tcp/IPv4) **和**INTERNET 协议版本 6 (tcp/IPv6) **属性的 "**高级**" 部分中的其他 IP 地址。

<div>


> [!TIP]  
> 配置具有两个网络适配器的边缘服务器是两个选项之一。 另一种方法是将一个网络适配器用于内部端，将三个网络适配器用于边缘服务器的外部端。 此选项的主要优点是，每个边缘服务器服务都有不同的网络适配器，并且在需要故障排除时有可能更简单的数据收集



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-example"></a>扩展的合并边缘所需的 DNS 记录，使用公用 IP 地址的 DNS 负载平衡 (示例) 

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
<td><p>131.107.155.10 和 131.107.155.11</p></td>
<td><p>访问边缘服务外部接口 (Contoso) 对于启用了 Lync 的用户的所有 SIP 域，请根据需要重复此步骤</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20 和 131.107.155.21</p></td>
<td><p>Web 会议边缘服务外部接口</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30 和 131.107.155.31</p></td>
<td><p>A/V 边缘服务外部接口</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/SRV/443</p></td>
<td><p>_sip _sip._tls .com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>访问边缘服务外部接口。 将 Lync 2013 和 Lync 2010 客户端的自动配置用于外部工作是必需的。 根据需要为启用 Lync 的用户的所有 SIP 域重复使用。</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls _sipfederationtls._tcp .com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>访问边缘服务外部接口需要联合合作伙伴（称为 "允许的 SIP 域"）的自动 DNS 发现，在以前的版本中称为 "增强联盟" () 。 根据需要为启用 Lync 的用户的所有 SIP 域重复使用</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10 和 172.25.33.11</p></td>
<td><p>合并边缘内部接口</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a>联盟需要的记录


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
<td><p>_sipfederationtls _sipfederationtls._tcp .com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>SIP 访问边缘服务外部接口，将联合身份验证自动 DNS 发现到其他潜在联合合作伙伴，并将其称为 "允许的 SIP 域" (在以前版本中称为 "增强联盟") 。</p>
<div>

> [!IMPORTANT]  
> 对于启用了 Lync 的用户和使用推送通知服务或 Apple 推送通知服务的 Microsoft Lync 移动客户端的所有 SIP 域，请按需重复执行此操作。


</div></td>
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
<th>映射位置/注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/SRV/5269</p></td>
<td><p>_xmpp server._tcp .com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>访问边缘服务或边缘池上的 XMPP 代理外部接口。对于所有内部 SIP 域，请根据需要对启用了 XMPP 联系人的用户通过外部策略、用户所在的网站策略或应用到启用 Lync 的用户的用户策略的配置来使用。 还必须在 XMPP 联盟伙伴策略中配置允许的 XMPP 域。 有关其他详细信息，请参阅 <strong>另请参阅</strong> 主题中的主题</p></td>
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

