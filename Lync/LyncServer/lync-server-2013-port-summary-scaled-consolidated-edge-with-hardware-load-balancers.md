---
title: 端口摘要 - 使用硬件负载平衡器的扩展的合并边缘
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48184841
ms.date: 04/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6260a4ad7f2717e0b4eb2446fc5b17671c3e45a5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725032"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Lync Server 2013 中的端口摘要 - 使用硬件负载平衡器的扩展的合并边缘

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2015-04-27_

此方案体系结构中所述的 Lync Server 2013、Edge 服务器功能非常类似于 Lync Server 2010 中实现的功能。 最显著的相加是针对可扩展消息和状态协议（XMPP）的 TCP 条目的端口**5269** 。 Lync Server 2013 （可选）在 Edge 服务器或边缘池以及前端服务器或前端池中的 XMPP 网关服务器上部署 XMPP 代理。

除了 IPv4，Edge 服务器现在还支持 IPv6。 为了清楚起见，方案中仅使用了 IPv4。

**使用硬件负载平衡缩放的合并边缘**

![边缘服务器外围网络端口和协议](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "边缘服务器外围网络端口和协议")

<div>

## <a name="port-and-protocol-details"></a>端口和协议详细信息

建议你仅打开支持你为其提供外部访问的功能所需的端口。

若要使远程访问适用于任何 edge 服务，必须确保 SIP 流量可以双向排列，如入站/出站边缘流量图中所示。 另一种方法是，在即时消息（IM）、状态、web 会议、音频/视频（A/V）和联合身份验证中涉及到和发送来自访问边缘服务的 SIP 消息。

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a>用于缩放后的合并边缘的防火墙摘要，硬件负载平衡：外部接口-节点1和节点2（示例）

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>角色/协议/TCP 或 UDP/端口</th>
<th>源 IP 地址</th>
<th>目标 IP 地址</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Access/HTTP/TCP/80</p></td>
<td><p>边缘服务器访问边缘服务公共 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>证书吊销/CRL 检查和检索</p></td>
</tr>
<tr class="even">
<td><p>Access/DNS/TCP/53</p></td>
<td><p>边缘服务器访问边缘服务公共 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>通过 TCP 进行 DNS 查询</p></td>
</tr>
<tr class="odd">
<td><p>Access/DNS/UDP/53</p></td>
<td><p>边缘服务器访问边缘服务公共 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>通过 UDP 进行 DNS 查询</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>Edge 服务器 A/V 边缘服务 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>与运行 Office 通信服务器2007、Office 通信服务器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作伙伴进行联盟所必需。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>Edge 服务器 A/V 边缘服务公共 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>仅适用于运行 Office 通信服务器2007的合作伙伴的联盟所必需。</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>任意</p></td>
<td><p>Edge 服务器 A/V 边缘服务公共 IP 地址</p></td>
<td><p>仅适用于运行 Office 通信服务器2007的合作伙伴的联盟所需</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>任意</p></td>
<td><p>Edge 服务器 A/V 边缘服务公共 IP 地址</p></td>
<td><p>仅适用于运行 Office 通信服务器2007的合作伙伴的联盟所需</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>Edge 服务器 A/V 边缘服务公共 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>3478出站用于确定 Lync Server 与之通信的边缘服务器的版本以及边缘服务器到边缘服务器上的媒体流量。 对于具有 Lync Server 2010、Windows Live Messenger 和 Office 通信服务器 2007 R2 的联盟，以及在公司内部部署了多个边缘池的情况下，也是必需的。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>任意</p></td>
<td><p>Edge 服务器 A/V 边缘服务公共 IP 地址</p></td>
<td><p>通过 UDP/3478 对候选人的 STUN 进行协商/启用</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>Edge 服务器 A/V 边缘服务公共 IP 地址</p></td>
<td><p>在 TCP/443 上 STUN/打开候选人的协商</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/TCP/443</p></td>
<td><p>Edge 服务器 A/V 边缘服务公共 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>在 TCP/443 上 STUN/打开候选人的协商</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a>用于缩放后的合并边缘的防火墙摘要，硬件负载平衡：内部接口节点1和节点2

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>角色/协议/TCP 或 UDP/端口</th>
<th>源 IP 地址</th>
<th>目标 IP 地址</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>任何（可以定义为前端服务器地址，或运行 XMPP 网关服务的前端池虚拟 IP 地址）</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>来自前端服务器或前端池运行的 XMPP 网关服务的出站 XMPP 流量</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>任何（可以定义为拥有中央管理存储的前端服务器服务器 IP 或池）</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>将中央管理存储中的更改复制到边缘服务器</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>任何（可以定义为 Director IP、前端服务器 IP 或池虚拟 IP）</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>从内部部署到内部边缘服务器接口的网络会议流量</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>任何（可以定义为 Director IP、前端服务器 IP 或池虚拟 IP）</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>内部和外部用户之间的/V 媒体传输的首选路径，Survivable 分支装置或 Survivable 分支服务器</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>任何（可以定义为 Director IP、前端服务器 IP 或池虚拟 IP）</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>内部和外部用户、Survivable 分支装置或 Survivable 分支服务器之间的 A/V 媒体传输的回退路径如果无法建立 UDP 通信，则使用 TCP 进行文件传输和桌面共享</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50001</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>使用 Lync Server Management Shell 和集中式日志记录服务 cmdlet、ClsController 命令行（ClsController）或代理（ClsAgent）命令和日志收集的集中式日志服务控制器</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50002</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>使用 Lync Server Management Shell 和集中式日志记录服务 cmdlet、ClsController 命令行（ClsController）或代理（ClsAgent）命令和日志收集的集中式日志服务控制器</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50003</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>使用 Lync Server Management Shell 和集中式日志记录服务 cmdlet、ClsController 命令行（ClsController）或代理（ClsAgent）命令和日志收集的集中式日志服务控制器</p></td>
</tr>
</tbody>
</table>


硬件负载平衡器在部署以提供 Lync 服务器的可用性和负载平衡时有特定的要求。 这些要求在下图和表中定义。 第三方供应商可能对此处定义的要求使用不同的术语。 需要将 Lync Server 的要求映射到硬件负载平衡器供应商提供的功能和配置选项。

配置硬件负载平衡器时，请考虑以下要求：

  - 可在硬件负载平衡器（HLB）上为 Access Edge 服务和 Web 会议边缘服务配置源网络地址转换（SNAT）

  - 不能在 A/V 边缘服务上配置 SNAT-A/V 边缘服务必须用真实的服务器地址（而不是 HLB 虚拟 IP （VIP））响应，以便使用中继 NAT （STUN）/traversal 简单遍历 NAT over NAT （），/federation 转动（FTURN）才能正常工作
    
      - 如果客户端向 HLB 发送请求，则该响应必须从 HLB VIP 返回
    
      - 如果客户端向边缘发送请求，则响应必须从边缘 IP 返回

  - 公共 IP 地址在每个服务器接口和 HLB 的 Vip 上使用，并且您的公共 IP 地址要求是 N + 1，其中包含每个真实服务器接口的公共 IP 地址，以及每个 HLB VIP 的一个公共 IP 地址。 如果池中有2台边缘服务器，这将产生9个公共 IP 地址，其中3用于 HLB Vip，另一个用于每个边缘服务器接口（共6台服务器）

  - 对于 Access Edge 服务和 Web 会议边缘服务（并在 HLB 上使用 NAT），该 VIP 会将源 IP 地址从客户端更改为其自己的 IP 地址。 服务器接口将寄信人地址寻址到 VIP，VIP 从服务器接口 IP 地址更改源地址，并将该数据包发送到客户端

  - 对于 A/V 边缘服务，VIP 不得更改源 IP 地址，而真正的服务器地址将直接返回到客户端-你无法在 HLB 上配置用于 AV 流量的 NAT
    
      - 如果客户端向 HLB VIP 发送请求，则响应必须从 HLB VIP 返回
    
      - 如果客户端向边缘 IP 发送请求，则响应必须从边缘 IP 返回

  - 对于 AV，外部防火墙将保留所有数据包的真实服务器公共 IP 地址

  - 客户端到 A/V 边缘服务通信一经建立，就是真正的服务器，而不是 HLB

  - 内部边缘到内部服务器和客户端必须路由，并且为托管服务器或客户端的所有内部网络设置持久路由

  - HLB Access Edge 服务 VIP 将用作每个 Edge 服务器接口的默认网关

<div>


> [!NOTE]
> 有关 NAT 规划和功能的详细信息，请参阅<A href="lync-server-2013-hardware-load-balancer-requirements.md">Lync Server 2013 的硬件负载平衡器要求</A>。



</div>

![边缘服务器端口和协议详细信息](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "边缘服务器端口和协议详细信息")

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a>缩放后的合并边缘所需的外部端口设置，硬件负载平衡：外部接口虚拟 IPs

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>角色/协议/TCP 或 UDP/端口</th>
<th>源 IP 地址</th>
<th>目标 IP 地址</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>任意</p></td>
<td><p>XMPP 代理服务（使用 Access Edge 服务共享 IP 地址）</p></td>
<td><p>XMPP 代理服务接受来自定义的 XMPP 联合的 XMPP 联系人的流量</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>XMPP 代理服务（使用 Access Edge 服务共享 IP 地址）</p></td>
<td><p>任意</p></td>
<td><p>XMPP 代理服务将流量发送到定义的 XMPP 联合体中的 XMPP 联系人</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP （TLS）/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>Access Edge 服务公共 VIP 地址</p></td>
<td><p>用于外部用户访问的客户端到服务器 SIP 流量</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP （MTLS）/TCP/5061</p></td>
<td><p>任意</p></td>
<td><p>Access Edge 服务公共 VIP 地址</p></td>
<td><p>使用 SIP 的 SIP 信号、联盟和公共 IM 连接</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP （MTLS）/TCP/5061</p></td>
<td><p>Access Edge 服务公共 VIP 地址</p></td>
<td><p>联盟伙伴</p></td>
<td><p>使用 SIP 的 SIP 信号、联盟和公共 IM 连接</p></td>
</tr>
<tr class="even">
<td><p>Web 会议/PSOM （TLS）/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>Edge 服务器 Web 会议 Edge 服务公共 VIP 地址</p></td>
<td><p>网络会议媒体</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>任意</p></td>
<td><p>Edge 服务器 A/V 边缘服务公共 VIP 地址</p></td>
<td><p>通过 UDP/3478 对候选人的 STUN 进行协商/启用</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>Edge 服务器 A/V 边缘服务公共 VIP 地址</p></td>
<td><p>在 TCP/443 上 STUN/打开候选人的协商</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a>用于缩放后的合并边缘的防火墙摘要，硬件负载平衡：内部接口虚拟 IPs

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>角色/协议/TCP 或 UDP/端口</th>
<th>源 IP 地址</th>
<th>目标 IP 地址</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Access/SIP （MTLS）/TCP/5061</p></td>
<td><p>任何（可以定义为 Director、Director pool 虚拟 IP 地址、前端服务器或前端池虚拟 IP 地址）</p></td>
<td><p>Edge 服务器内部 VIP 接口</p></td>
<td><p>出站 SIP 流量（从控制器、控制器池虚拟 IP 地址、前端服务器或前端池虚拟 IP 地址）到内部边缘 VIP</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP （MTLS）/TCP/5061</p></td>
<td><p>Edge 服务器内部 VIP 接口</p></td>
<td><p>任何（可以定义为 Director、Director pool 虚拟 IP 地址、前端服务器或前端池虚拟 IP 地址）</p></td>
<td><p>来自边缘服务器内部接口的入站 SIP 流量（到控制器、控制器池虚拟 IP 地址、前端服务器或前端池虚拟 IP 地址）</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>任何（可以定义为前端服务器 IP 地址或前端池 IP 地址，或使用此 Edge 服务器的任何 Survivable 分支装置或 Survivable 分支服务器）</p></td>
<td><p>Edge 服务器内部 VIP 接口</p></td>
<td><p>使用此 Edge 服务器从前端服务器或前端池 IP 地址或任何 Survivable 分支装置或 Survivable 分支服务器身份验证 A/V 用户（A/V 身份验证服务）的身份验证</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>任意</p></td>
<td><p>Edge 服务器内部 VIP 接口</p></td>
<td><p>内部和外部用户之间的 A/V 媒体传输的首选路径</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>Edge 服务器内部 VIP 接口</p></td>
<td><p>内部和外部用户之间的 A/V 媒体传输的回退路径如果无法建立 UDP 通信，则使用 TCP 进行文件传输和桌面共享</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Edge 服务器内部 VIP 接口</p></td>
<td><p>任意</p></td>
<td><p>内部和外部用户之间的 A/V 媒体传输的回退路径如果无法建立 UDP 通信，则使用 TCP 进行文件传输和桌面共享</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

