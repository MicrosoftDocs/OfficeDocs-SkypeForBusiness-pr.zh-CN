---
title: Lync Server 2013：端口摘要 - 扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: f7cbd0f1-841d-4116-8d17-e9d991daa4a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205394(v=OCS.15)
ms:contentKeyID: 48185865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2095df7ebd68265d135a8b174ce2d1d3ae76ca5d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a>Lync Server 2013 中的端口摘要 - 扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-04-03_

此方案体系结构中所述的 Lync Server 2013、Edge 服务器功能非常类似于 Lync Server 2010 中实现的功能。 最显著的相加是针对可扩展消息和状态协议 (XMPP) 的 TCP 条目的端口**5269** 。 Lync Server 2013 (可选) 在 Edge 服务器或边缘池以及前端服务器或前端池中的 XMPP 网关服务器上部署 XMPP 代理。

除了 IPv4, Edge 服务器现在还支持 IPv6。 为了清楚起见, 方案中仅使用了 IPv4。

**用于缩放合并边缘的企业外围网络, 具有公共 IP 地址的 DNS 负载平衡**

![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")

<div>

## <a name="port-and-protocol-details"></a>端口和协议详细信息

建议你仅打开支持你为其提供外部访问的功能所需的端口。

若要使远程访问适用于任何 edge 服务, 必须确保 SIP 流量可以双向排列, 如入站/出站边缘流量图中所示。 另一种方法是, 在即时消息 (IM)、状态、web 会议、音频/视频 (A/V) 和联合身份验证中涉及到和发送来自访问边缘服务的 SIP 消息。

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-external-interface--node-1-and-node-2-example"></a>用于缩放后的合并边缘的防火墙摘要、具有公共 IP 地址的 DNS 负载平衡: 外部接口-节点1和节点 2 (示例)

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
<td><p>XMPP 代理服务 (使用 Access Edge 服务共享 IP 地址)</p></td>
<td><p>XMPP 代理服务接受来自定义的 XMPP 联合的 XMPP 联系人的流量</p></td>
</tr>
<tr class="even">
<td><p>Access/HTTP/TCP/80</p></td>
<td><p>边缘服务器访问边缘服务公共 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>证书吊销/CRL 检查和检索</p></td>
</tr>
<tr class="odd">
<td><p>Access/DNS/TCP/53</p></td>
<td><p>边缘服务器访问边缘服务公共 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>通过 TCP 进行 DNS 查询</p></td>
</tr>
<tr class="even">
<td><p>Access/DNS/UDP/53</p></td>
<td><p>边缘服务器访问边缘服务公共 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>通过 UDP 进行 DNS 查询</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (TLS)/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器访问边缘服务公共 IP 地址</p></td>
<td><p>用于外部用户访问的客户端到服务器 SIP 流量</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP (MTLS)/TCP/5061</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器访问边缘服务公共 IP 地址</p></td>
<td><p>对于使用 SIP 的联盟和公共 IM 连接</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (MTLS)/TCP/5061</p></td>
<td><p>边缘服务器访问边缘服务公共 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>对于使用 SIP 的联盟和公共 IM 连接</p></td>
</tr>
<tr class="even">
<td><p>网络会议/PSOM (TLS) TCP/443</p></td>
<td><p>任意</p></td>
<td><p>Edge 服务器 Web 会议边缘服务公共 IP 地址</p></td>
<td><p>网络会议媒体</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>Edge 服务器 A/V 边缘服务公共 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>与运行 Office 通信服务器2007、Office 通信服务器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作伙伴进行联盟所必需。</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>Edge 服务器 A/V 边缘服务公共 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>仅适用于运行 Office 通信服务器2007的合作伙伴的联盟所必需。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>任意</p></td>
<td><p>Edge 服务器 A/V 边缘服务公共 IP 地址</p></td>
<td><p>仅适用于运行 Office 通信服务器2007的合作伙伴的联盟所需</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>任意</p></td>
<td><p>Edge 服务器 A/V 边缘服务公共 IP 地址</p></td>
<td><p>仅适用于运行 Office 通信服务器2007的合作伙伴的联盟所需</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>Edge 服务器 A/V 边缘服务公共 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>3478出站用于确定 Lync Server 与之通信的边缘服务器的版本以及边缘服务器到边缘服务器上的媒体流量。 对于具有 Lync Server 2010、Windows Live Messenger 和 Office 通信服务器 2007 R2 的联盟, 以及在公司内部部署了多个边缘池的情况下, 也是必需的。</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>任意</p></td>
<td><p>Edge 服务器 A/V 边缘服务公共 IP 地址</p></td>
<td><p>通过 UDP/3478 对候选人的 STUN 进行协商/启用</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>Edge 服务器 A/V 边缘服务公共 IP 地址</p></td>
<td><p>在 TCP/443 上 STUN/打开候选人的协商</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/TCP/443</p></td>
<td><p>Edge 服务器 A/V 边缘服务</p></td>
<td><p>任意</p></td>
<td><p>在 TCP/443 上 STUN/打开候选人的协商</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-internal-interface--node-1-and-node-2-example"></a>用于缩放后的合并边缘的防火墙摘要、具有公共 IP 地址的 DNS 负载平衡: 内部接口-节点1和节点 2 (示例)

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
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>任何 (可以定义为前端服务器地址, 或运行 XMPP 网关服务的前端池 IP 地址)</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>来自前端服务器或前端池运行的 XMPP 网关服务的出站 XMPP 流量</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>任何 (可以定义为 Director、Director pool IP 地址、前端服务器或前端池 IP 地址)</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>出站 SIP 流量 (从控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址) 到边缘服务器内部接口</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>任何 (可以定义为 Director、Director pool IP 地址、前端服务器或前端池 IP 地址)</p></td>
<td><p>来自边缘服务器内部接口的入站 SIP 流量 (到控制器、控制器池 IP 地址、前端服务器或前端池 IP 地址)</p></td>
</tr>
<tr class="even">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>任何 (可以定义为前端服务器 IP 地址, 或前端池中的每个前端服务器 IP 地址)</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>从前端服务器或每台前端服务器 (如果在池中) 到边缘服务器内部接口的 Web 会议流量</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>任何 (可以定义为前端服务器 IP 地址或前端池 IP 地址, 或使用此 Edge 服务器的任何 Survivable 分支装置或 Survivable 分支服务器)</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>使用此 Edge 服务器从前端服务器或前端池 IP 地址或任何 Survivable 分支装置或 Survivable 分支服务器身份验证 A/V 用户 (A/V 身份验证服务) 的身份验证</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>内部和外部用户之间的/V 媒体传输的首选路径, Survivable 分支装置或 Survivable 分支服务器</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>内部和外部用户、Survivable 分支装置或 Survivable 分支服务器之间的 A/V 媒体传输的回退路径如果无法建立 UDP 通信, 则使用 TCP 进行文件传输和桌面共享</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>任何 (可以定义为前端服务器 IP 地址或拥有中央管理存储的池)</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>将中央管理存储中的更改复制到边缘服务器</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>使用 Lync Server Management Shell 和集中式日志记录服务 cmdlet、ClsController 命令行 (ClsController) 或代理 (ClsAgent) 命令和日志收集的集中式日志服务控制器</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>使用 Lync Server Management Shell 和集中式日志记录服务 cmdlet、ClsController 命令行 (ClsController) 或代理 (ClsAgent) 命令和日志收集的集中式日志服务控制器</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>使用 Lync Server Management Shell 和集中式日志记录服务 cmdlet、ClsController 命令行 (ClsController) 或代理 (ClsAgent) 命令和日志收集的集中式日志服务控制器</p></td>
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
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Access/SIP (MTLS)/TCP/5061</p></td>
<td><p>Access Edge 服务公共 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>对于使用 SIP 的联盟和公共 IM 连接</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>防火墙摘要-公共即时消息连接


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
<td><p>Access/SIP (MTLS)/TCP/5061</p></td>
<td><p>公共 IM 连接合作伙伴</p></td>
<td><p>Edge 服务器访问边缘服务</p></td>
<td><p>对于使用 SIP 的联盟和公共 IM 连接</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP (MTLS)/TCP/5061</p></td>
<td><p>Edge 服务器访问边缘服务</p></td>
<td><p>公共 IM 连接合作伙伴</p></td>
<td><p>对于使用 SIP 的联盟和公共 IM 连接</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (TLS)/TCP/443</p></td>
<td><p>客户端</p></td>
<td><p>Edge 服务器访问边缘服务</p></td>
<td><p>用于外部用户访问的客户端到服务器 SIP 流量</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>Edge 服务器 A/V 边缘服务</p></td>
<td><p>实时 Messenger 客户端</p></td>
<td><p>如果配置了公用 IM 连接, 则用于带有 Windows Live Messenger 的 A/V 会话。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>Edge 服务器 A/V 边缘服务</p></td>
<td><p>实时 Messenger 客户端</p></td>
<td><p>与 Windows Live Messenger 的公共即时消息连接所必需</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>实时 Messenger 客户端</p></td>
<td><p>Edge 服务器 A/V 边缘服务</p></td>
<td><p>与 Windows Live Messenger 的公共即时消息连接所必需</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a>可扩展消息和状态协议的防火墙摘要


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
<th>源 (IP 地址)</th>
<th>目标 (IP 地址)</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>任意</p></td>
<td><p>Edge 服务器访问边缘服务接口 IP 地址</p></td>
<td><p>适用于 XMPP 的标准服务器到服务器通信端口。 允许与联盟 XMPP 合作伙伴的 Edge 服务器 XMPP 代理通信</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Edge 服务器访问边缘服务接口 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>适用于 XMPP 的标准服务器到服务器通信端口。 允许从 Edge 服务器 XMPP 代理到联合 XMPP 合作伙伴的通信</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>任意</p></td>
<td><p>每个内部边缘服务器接口 IP</p></td>
<td><p>从前端服务器或前端池中的 XMPP 网关到边缘服务器内部 IP 地址或每个边缘池成员的内部 IP 地址的内部 XMPP 流量</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

