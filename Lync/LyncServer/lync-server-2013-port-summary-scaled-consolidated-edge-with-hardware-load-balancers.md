---
title: 端口摘要-使用硬件负载平衡器的扩展的合并边缘
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
ms.openlocfilehash: 78196bab17af69d83bbeacf636b4b2ba4e972121
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Lync Server 2013 中的端口摘要-使用硬件负载平衡器的扩展的合并边缘

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2015-04-27_

此方案体系结构中所述的 Lync Server 2013、Edge 服务器功能与 Lync Server 2010 中实施的功能非常相似。 最引人注目的是为可扩展消息传递和状态协议 (XMPP) 新增了端口 **5269 over TCP** 条目。 Lync Server 2013 （可选）在边缘服务器或边缘池以及前端服务器或前端池上的 XMPP 网关服务器上部署 XMPP 代理。

除 IPv4 外，边缘服务器现在还支持 IPv6。 为了清楚起见，本方案中仅使用 IPv4。

**使用硬件负载平衡的扩展的合并边缘**

![边缘服务器外围网络端口和协议](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "边缘服务器外围网络端口和协议")

<div>

## <a name="port-and-protocol-details"></a>端口和协议详细信息

建议仅打开支持为其提供外部访问的功能所需的端口。

要对任何边缘服务进行远程访问，必须允许 SIP 流量进行双向流动，如入站/出站边缘流量图中所示。换言之，即时消息 (IM)、状态、Web 会议、音频/视频 (A/V) 和联盟中会涉及在访问边缘服务中接收和发送 SIP 消息。

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a>扩展的合并边缘（硬件负载平衡）的防火墙摘要：外部接口–节点1和节点2（示例）

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
<td><p>边缘服务器访问边缘服务公用 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>证书吊销/CRL 检查和检索</p></td>
</tr>
<tr class="even">
<td><p>访问/DNS/TCP/53</p></td>
<td><p>边缘服务器访问边缘服务公用 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>通过 TCP 的 DNS 查询</p></td>
</tr>
<tr class="odd">
<td><p>访问/DNS/UDP/53</p></td>
<td><p>边缘服务器访问边缘服务公用 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>通过 UDP 的 DNS 查询</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>边缘服务器 A/V 边缘服务 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>与运行 Office 通信服务器2007、Office 通信服务器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作伙伴进行联盟的必要条件。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>边缘服务器 A/V 边缘服务公共 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的。</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器 A/V 边缘服务公共 IP 地址</p></td>
<td><p>仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器 A/V 边缘服务公共 IP 地址</p></td>
<td><p>仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>边缘服务器 A/V 边缘服务公共 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>3478出站用于确定 Lync Server 与之通信的边缘服务器的版本以及边缘服务器到边缘服务器上的媒体流量。 对于具有 Lync Server 2010、Windows Live Messenger 和 Office 通信服务器 2007 R2 的联盟，以及在公司中部署了多个边缘池的情况下是必需的。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器 A/V 边缘服务公共 IP 地址</p></td>
<td><p>通过 UDP/3478 进行的候选项 STUN/TURN 协商</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器 A/V 边缘服务公共 IP 地址</p></td>
<td><p>通过 TCP/443 进行的候选项 STUN/TURN 协商</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/TCP/443</p></td>
<td><p>边缘服务器 A/V 边缘服务公共 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>通过 TCP/443 进行的候选项 STUN/TURN 协商</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a>扩展的合并边缘（硬件负载平衡）的防火墙摘要：内部接口节点1和节点2

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
<td><p>Any （可定义为前端服务器地址，或运行 XMPP 网关服务的前端池虚拟 IP 地址）</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>来自前端服务器或前端池上运行的 XMPP 网关服务的出站 XMPP 流量</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Any （可定义为保留中央管理存储的前端服务器服务器 IP 或池）</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>将中央管理存储中的更改复制到边缘服务器</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Any （可定义为控制器 IP、前端服务器 IP 或池虚拟 IP）</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>内部部署到内部边缘服务器接口的 Web 会议流量</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Any （可定义为控制器 IP、前端服务器 IP 或池虚拟 IP）</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>内部和外部用户之间的 A/V 媒体传输的首选路径，Survivable Branch 设备或 Survivable Branch Server</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Any （可定义为控制器 IP、前端服务器 IP 或池虚拟 IP）</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>内部和外部用户之间的 A/V 媒体传输的回退路径，Survivable 分支装置或 Survivable 分支服务器如果无法建立 UDP 通信，则使用 TCP 进行文件传输和桌面共享</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50001</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行（ClsController）或代理（ClsAgent）命令和日志集合的集中日志记录服务控制器</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50002</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行（ClsController）或代理（ClsAgent）命令和日志集合的集中日志记录服务控制器</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50003</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行（ClsController）或代理（ClsAgent）命令和日志集合的集中日志记录服务控制器</p></td>
</tr>
</tbody>
</table>


在部署时，硬件负载平衡器有特定的要求，以提供 Lync Server 的可用性和负载平衡。 这些要求是在下图和表中定义的。 第三方供应商可能会对此处定义的要求使用不同的术语。 需要将 Lync Server 的要求映射到由硬件负载平衡器供应商提供的功能和配置选项。

配置硬件负载平衡器时，请考虑以下要求：

  - 可以在硬件负载平衡器（HLB）上为访问边缘服务和 Web 会议边缘服务配置源网络地址转换（SNAT）

  - 无法在 A/V 边缘服务上配置 SNAT – A/V 边缘服务必须使用实际的服务器地址（而不是 HLB 虚拟 IP （VIP））进行响应，以便使用中继 NAT （STUN）/traversal 简单遍历 UDP over NAT （）使用中继 NAT （关闭）/federation 轮流（FTURN）才能正常工作
    
      - 如果客户端向 HLB 发送请求，则响应必须从 HLB VIP 返回
    
      - 如果客户端向边缘发送请求，响应必须从边缘 IP 返回

  - 公用 IP 地址在每个服务器接口和 HLB 的 Vip 上使用，并且公共 IP 地址要求为 N + 1，其中包含每个实际服务器接口的公用 IP 地址和每个 HLB VIP 对应一个公用 IP 地址。 在池中有2台边缘服务器的情况下，这会生成9个公用 IP 地址，其中3用于 HLB Vip，另一个用于每个边缘服务器接口（共6台服务器）

  - 对于访问边缘服务和 Web 会议边缘服务（并使用 HLB 上的 NAT），客户端将联系 VIP，VIP 会将源 IP 地址从客户端更改为自己的 IP 地址。 服务器接口将返回地址和 VIP 寻址，VIP 将从服务器接口 IP 地址更改源地址，并将数据包发送到客户端

  - 对于 A/V 边缘服务，VIP 不得更改源 IP 地址，且实际服务器地址直接返回到客户端–您无法在 HLB 上为 AV 流量配置 NAT
    
      - 如果客户端向 HLB VIP 发送请求，则响应必须从 HLB VIP 返回
    
      - 如果客户端向边缘 IP 发送请求，则响应必须从边缘 IP 返回

  - 对于 AV，外部防火墙将保留所有数据包的真实服务器公用 IP 地址

  - 一旦建立，客户端到 A/V 边缘服务通信就是真正的服务器，而不是 HLB

  - 内部边缘到内部服务器和客户端必须路由，且为承载服务器或客户端的所有内部网络设置持久路由

  - HLB Access Edge service VIP 将充当每个边缘服务器接口的默认网关

<div>


> [!NOTE]
> 有关 NAT 规划和功能的详细信息，请参阅<A href="lync-server-2013-hardware-load-balancer-requirements.md">Lync Server 2013 的硬件负载平衡器要求</A>。



</div>

![边缘服务器端口和协议详细信息](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "边缘服务器端口和协议详细信息")

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a>扩展的合并边缘（硬件负载平衡）所需的外部端口设置：外部接口虚拟 Ip

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
<td><p>XMPP 代理服务（与访问边缘服务共享 IP 地址）</p></td>
<td><p>XMPP 代理服务可接受来自所定义的 XMPP 联盟中 XMPP 联系人的流量</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>XMPP 代理服务（与访问边缘服务共享 IP 地址）</p></td>
<td><p>任意</p></td>
<td><p>XMPP 代理服务向定义的 XMPP 联合中的 XMPP 联系人发送流量</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP （TLS）/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>访问边缘服务公用 VIP 地址</p></td>
<td><p>外部用户访问的客户端到服务器 SIP 流量</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP （MTLS）/TCP/5061</p></td>
<td><p>任意</p></td>
<td><p>访问边缘服务公用 VIP 地址</p></td>
<td><p>SIP 信号、联合和公共 IM 连接使用 SIP</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP （MTLS）/TCP/5061</p></td>
<td><p>访问边缘服务公用 VIP 地址</p></td>
<td><p>联盟伙伴</p></td>
<td><p>SIP 信号、联合和公共 IM 连接使用 SIP</p></td>
</tr>
<tr class="even">
<td><p>Web 会议/PSOM （TLS）/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器 Web 会议边缘服务公用 VIP 地址</p></td>
<td><p>Web 会议媒体</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器 A/V 边缘服务公共 VIP 地址</p></td>
<td><p>通过 UDP/3478 进行的候选项 STUN/TURN 协商</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器 A/V 边缘服务公共 VIP 地址</p></td>
<td><p>通过 TCP/443 进行的候选项 STUN/TURN 协商</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a>扩展的合并边缘（硬件负载平衡）的防火墙摘要：内部接口虚拟 Ip

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
<td><p>Any （可定义为控制器、控制器池虚拟 IP 地址、前端服务器或前端池虚拟 IP 地址）</p></td>
<td><p>边缘服务器内部 VIP 接口</p></td>
<td><p>出站 SIP 流量（从控制器、控制器池虚拟 IP 地址、前端服务器或前端池虚拟 IP 地址）到内部边缘 VIP</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP （MTLS）/TCP/5061</p></td>
<td><p>边缘服务器内部 VIP 接口</p></td>
<td><p>Any （可定义为控制器、控制器池虚拟 IP 地址、前端服务器或前端池虚拟 IP 地址）</p></td>
<td><p>来自边缘服务器内部接口的入站 SIP 流量（到控制器、控制器池虚拟 IP 地址、前端服务器或前端池虚拟 IP 地址）</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Any （可定义为前端服务器 IP 地址或前端池 IP 地址，或使用此边缘服务器的任何 Survivable 分支机构或 Survivable 分支服务器）</p></td>
<td><p>边缘服务器内部 VIP 接口</p></td>
<td><p>使用此边缘服务器从前端服务器或前端池 IP 地址或任何 Survivable 分支机构或 Survivable 分支服务器对 A/V 用户（A/V 身份验证服务）进行身份验证</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器内部 VIP 接口</p></td>
<td><p>用于内外部用户间的 A/V 媒体传输的首选路径</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器内部 VIP 接口</p></td>
<td><p>用于内外部间的 A/V 媒体传输的回退路径，如果无法建立 UDP 通信，则将 TCP 用于文件传输和桌面共享</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>边缘服务器内部 VIP 接口</p></td>
<td><p>任意</p></td>
<td><p>用于内外部间的 A/V 媒体传输的回退路径，如果无法建立 UDP 通信，则将 TCP 用于文件传输和桌面共享</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

