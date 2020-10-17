---
title: 端口摘要-使用 NAT 的具有专用 IP 地址的单一合并边缘
description: 端口摘要-使用 NAT 的具有专用 IP 地址的单一合并边缘。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: 3c1a389f-5f42-4719-a05b-e0b84aa3eb9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425891(v=OCS.15)
ms:contentKeyID: 48183877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3fc182b9fbbd24d589feb7f73e3c0086fa23152
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564558"
---
# <a name="port-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>Lync Server 2013 中的端口摘要-使用 NAT 的具有专用 IP 地址的单一合并边缘

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-04-03_

此方案体系结构中所述的 Lync Server 2013、Edge 服务器功能与 Lync Server 2010 中实施的功能非常相似。 最引人注目的是为可扩展消息传递和状态协议 (XMPP) 新增了端口 **5269 over TCP** 条目。 Lync Server 2013 （可选）在边缘服务器或边缘池以及前端服务器或前端池上的 XMPP 网关服务器上部署 XMPP 代理。

除 IPv4 外，边缘服务器现在还支持 IPv6。 为了清楚起见，本方案中仅使用 IPv4。

**具有使用 NAT 的专用 IP 寻址的单个合并边缘服务器的网络外围**

![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")

<div>

## <a name="port-and-protocol-details"></a>端口和协议详细信息

我们建议您仅打开支持为其提供外部访问权限的功能所需的端口。

要对任何边缘服务进行远程访问，必须允许 SIP 流量进行双向流动，如入站/出站边缘流量图中所示。 另一种方法，在即时消息 (IM) 、状态、web 会议、音频/视频 (A/V) 和联合身份验证中，与来自访问边缘服务的 SIP 消息涉及。

### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-external-interface"></a>具有使用 NAT 的专用 IP 地址的单一合并边缘的防火墙摘要：外部接口

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
<th>注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>任何</p></td>
<td><p>XMPP 代理服务 (与访问边缘服务共享 IP 地址) </p></td>
<td><p>XMPP 代理服务可接受来自所定义的 XMPP 联盟中 XMPP 联系人的流量</p></td>
</tr>
<tr class="even">
<td><p>Access/HTTP/TCP/80</p></td>
<td><p>边缘服务器访问边缘服务</p></td>
<td><p>任何</p></td>
<td><p>证书吊销/CRL 检查和检索</p></td>
</tr>
<tr class="odd">
<td><p>访问/DNS/TCP/53</p></td>
<td><p>边缘服务器访问边缘服务</p></td>
<td><p>任何</p></td>
<td><p>通过 TCP 的 DNS 查询</p></td>
</tr>
<tr class="even">
<td><p>访问/DNS/UDP/53</p></td>
<td><p>边缘服务器访问边缘服务</p></td>
<td><p>任何</p></td>
<td><p>通过 UDP 的 DNS 查询</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (TLS) /TCP/443</p></td>
<td><p>任何</p></td>
<td><p>边缘服务器访问边缘服务</p></td>
<td><p>外部用户访问的客户端到服务器 SIP 流量</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP (MTLS) /TCP/5061</p></td>
<td><p>任何</p></td>
<td><p>边缘服务器访问边缘服务</p></td>
<td><p>对于使用 SIP 的联盟和公共 IM 连接</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (MTLS) /TCP/5061</p></td>
<td><p>边缘服务器访问边缘服务</p></td>
<td><p>任何</p></td>
<td><p>对于使用 SIP 的联盟和公共 IM 连接</p></td>
</tr>
<tr class="even">
<td><p>Web 会议/PSOM (TLS) /TCP/443</p></td>
<td><p>任何</p></td>
<td><p>边缘服务器 Web 会议边缘服务</p></td>
<td><p>Web 会议媒体</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>边缘服务器 A/V 边缘服务</p></td>
<td><p>任何</p></td>
<td><p>与运行 Office 通信服务器2007、Office 通信服务器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作伙伴进行联盟的必要条件。</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>边缘服务器 A/V 边缘服务</p></td>
<td><p>任何</p></td>
<td><p>仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>任何</p></td>
<td><p>边缘服务器 A/V 边缘服务</p></td>
<td><p>仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>任何</p></td>
<td><p>边缘服务器 A/V 边缘服务</p></td>
<td><p>仅对运行 Office 通信服务器2007的合作伙伴的联盟是必需的</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>边缘服务器 A/V 边缘服务</p></td>
<td><p>任何</p></td>
<td><p>3478出站用于确定 Lync Server 与之通信的边缘服务器的版本以及边缘服务器到边缘服务器上的媒体流量。 对于具有 Lync Server 2010、Windows Live Messenger 和 Office 通信服务器 2007 R2 的联盟，以及在公司中部署了多个边缘池的情况下是必需的。</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>任何</p></td>
<td><p>边缘服务器 A/V 边缘服务</p></td>
<td><p>通过 UDP/3478 进行的候选项 STUN/TURN 协商</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/TCP/443</p></td>
<td><p>任何</p></td>
<td><p>边缘服务器 A/V 边缘服务</p></td>
<td><p>通过 TCP/443 进行的候选项 STUN/TURN 协商</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/TCP/443</p></td>
<td><p>边缘服务器 A/V 边缘服务</p></td>
<td><p>任何</p></td>
<td><p>通过 TCP/443 进行的候选项 STUN/TURN 协商</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-internal-interface"></a>具有使用 NAT 的专用 IP 地址的单一合并边缘的防火墙摘要： Internal 接口

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>协议/TCP 或 UDP/端口</th>
<th>源 IP 地址</th>
<th>目标 IP 地址</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>可以将任何 (定义为 Standard Edition server IP、Standard Edition server IP 地址或运行 XMPP 网关服务的池 IP 地址) </p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>来自前端服务器或前端池上运行的 XMPP 网关服务的出站 XMPP 流量</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>可以将任何 (定义为控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址) </p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>从控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址) 到边缘服务器内部接口的出站 SIP 流量 (</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>可以将任何 (定义为控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址) </p></td>
<td><p>入站 SIP 流量 (到控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址) 从边缘服务器内部接口</p></td>
</tr>
<tr class="even">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>可以将任何 (定义为前端服务器 IP 地址，或在前端池中的每个前端服务器 IP 地址) </p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>从前端服务器或每台前端服务器（如果在池中）到边缘服务器内部接口的 Web 会议流量</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>可以将任何 (定义为前端服务器 IP 地址或前端池 IP 地址，或使用此边缘服务器的任何 Survivable 分支机构或 Survivable 分支服务器) </p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>A/V 身份验证服务 (A/v 身份验证服务) 从前端服务器或前端池 IP 地址或使用此边缘服务器的任何 Survivable 分支装置或 Survivable 分支服务器进行身份验证</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>任何</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>内部和外部用户之间的 A/V 媒体传输的首选路径，Survivable Branch 设备或 Survivable Branch Server</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>任何</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>内部和外部用户之间的 A/V 媒体传输的回退路径，Survivable 分支装置或 Survivable 分支服务器如果无法建立 UDP 通信，则使用 TCP 进行文件传输和桌面共享</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>可以将任何 (定义为前端服务器 IP 地址或包含中央管理存储的池) </p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>将中央管理存储中的更改复制到边缘服务器</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>任何</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行 ( # A0) 或代理 ( # A1) 命令和日志集合的集中日志记录服务控制器</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>任何</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行 ( # A0) 或代理 ( # A1) 命令和日志集合的集中日志记录服务控制器</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>任何</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行 ( # A0) 或代理 ( # A1) 命令和日志集合的集中日志记录服务控制器</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a>联盟的防火墙摘要


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
<th>注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Access/SIP (MTLS) /TCP/5061</p></td>
<td><p>访问边缘服务公用 IP 地址</p></td>
<td><p>任何</p></td>
<td><p>对于使用 SIP 的联盟和公共 IM 连接</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>防火墙摘要 – 公共即时消息连接


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
<th>注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Access/SIP (MTLS) /TCP/5061</p></td>
<td><p>公共 IM 连接合作伙伴</p></td>
<td><p>边缘服务器访问边缘服务</p></td>
<td><p>对于使用 SIP 的联盟和公共 IM 连接</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP (MTLS) /TCP/5061</p></td>
<td><p>边缘服务器访问边缘服务</p></td>
<td><p>公共 IM 连接合作伙伴</p></td>
<td><p>对于使用 SIP 的联盟和公共 IM 连接</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (TLS) /TCP/443</p></td>
<td><p>客户端</p></td>
<td><p>边缘服务器访问边缘服务</p></td>
<td><p>外部用户访问的客户端到服务器 SIP 流量</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>边缘服务器 A/V 边缘服务</p></td>
<td><p>Live Messenger 客户端</p></td>
<td><p>用于与 Windows Live Messenger 的 A/V 会话，前提是配置了公共 IM 连接。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>边缘服务器 A/V 边缘服务</p></td>
<td><p>Live Messenger 客户端</p></td>
<td><p>需要与 Windows Live Messenger 的公共 IM 连接</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>Live Messenger 客户端</p></td>
<td><p>边缘服务器 A/V 边缘服务</p></td>
<td><p>需要与 Windows Live Messenger 的公共 IM 连接</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a>可扩展消息传递和状态协议的防火墙摘要


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>协议/TCP 或 UDP/端口</th>
<th>源（IP 地址）</th>
<th>目标（IP 地址）</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>任何</p></td>
<td><p>边缘服务器访问边缘服务接口 IP 地址</p></td>
<td><p>用于 XMPP 的标准服务器到服务器通信端口。 允许与来自联合 XMPP 合作伙伴的边缘服务器 XMPP 代理的通信</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>边缘服务器访问边缘服务接口 IP 地址</p></td>
<td><p>任何</p></td>
<td><p>用于 XMPP 的标准服务器到服务器通信端口。 允许从边缘服务器 XMPP 代理到联合 XMPP 合作伙伴的通信</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>任何</p></td>
<td><p>每个内部边缘服务器接口 IP</p></td>
<td><p>从前端服务器或前端池上的 XMPP 网关到边缘服务器内部 IP 地址或每个边缘池成员的内部 IP 地址的内部 XMPP 流量</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

