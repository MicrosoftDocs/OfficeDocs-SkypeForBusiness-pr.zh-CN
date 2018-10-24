---
title: Lync Server 2013：端口摘要 - 使用硬件负载平衡器的扩展的合并边缘
TOCTitle: 端口摘要 - 使用硬件负载平衡器的扩展的合并边缘
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398739(v=OCS.15)
ms:contentKeyID: 49313589
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的端口摘要 - 使用硬件负载平衡器的扩展的合并边缘

 

_**上一次修改主题：** 2015-04-27_

此方案体系结构中描述的 Lync Server 2013 边缘服务器功能非常类似于 Lync Server 2010 中实现的内容。最值得注意的是端口 **5269 over TCP**（可扩展消息传递和状态协议 (XMPP) 的入口）。Lync Server 2013 也可选择在边缘服务器或边缘池上以及前端服务器或前端池上的 XMPP 网关服务器上部署 XMPP 代理。

除了 IPv4 之外， 边缘服务器现在支持 IPv6。为了清楚起见，本方案中仅使用 IPv4。

**使用硬件负载平衡的扩展合并边缘**

![边缘服务器外围网络端口和协议](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "边缘服务器外围网络端口和协议")

## 端口和协议详细信息

建议仅打开支持为其提供外部访问的功能所需的端口。

要对任何边缘服务进行远程访问，必须允许 SIP 流量进行双向流动，如入站/出站边缘流量图中所示。换言之，即时消息 (IM)、状态、Web 会议、音频/视频 (A/V) 和联盟中会涉及在 访问边缘服务中接收和发送 SIP 消息。

### 扩展的合并边缘（硬件负载已平衡）的防火墙摘要：外部接口 – 节点 1 和节点 2（示例）

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
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>访问/HTTP/TCP/80</p></td>
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
<td><p>A/V/RTP/TCP/50,000-59,999</p></td>
<td><p>边缘服务器A/V 边缘服务 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>仅当与运行 Office Communications Server 2007、Office Communications Server 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作伙伴进行联盟时必需。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50,000-59,999</p></td>
<td><p>边缘服务器A/V 边缘服务公用 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>仅当与运行 Office Communications Server 2007 的合作伙伴联盟时必需。</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50,000-59,999</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器A/V 边缘服务公用 IP 地址</p></td>
<td><p>仅当与运行 Office Communications Server 2007 的合作伙伴联盟时必需</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50,000-59,999</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器A/V 边缘服务公用 IP 地址</p></td>
<td><p>仅当与运行 Office Communications Server 2007 的合作伙伴联盟时必需</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>边缘服务器A/V 边缘服务公用 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>3478 出站用于确定 Lync Server 与其进行通信的边缘服务器的版本，还用于从边缘服务器到边缘服务器的媒体流量。与 Lync Server 2010、Windows Live Messenger 和 Office Communications Server 2007 R2 联盟时必需，当公司中部署了多个边缘池时也是必需的。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器A/V 边缘服务公用 IP 地址</p></td>
<td><p>通过 UDP/3478 进行的候选项 STUN/TURN 协商</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN,MSTURN/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器A/V 边缘服务公用 IP 地址</p></td>
<td><p>通过 TCP/443 进行的候选项 STUN/TURN 协商</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN,MSTURN/TCP/443</p></td>
<td><p>边缘服务器A/V 边缘服务公用 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>通过 TCP/443 进行的候选项 STUN/TURN 协商</p></td>
</tr>
</tbody>
</table>


### 扩展的合并边缘（硬件负载已平衡）的防火墙摘要：内部接口节点 1 和节点 2

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
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>任意（可定义为运行 XMPP 网关服务的 前端服务器地址或 前端池虚拟 IP 地址）</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>来自 前端服务器或 前端池上运行的 XMPP 网关服务的出站 XMPP 流量</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>任意（可定义为 前端服务器服务器 IP 或承载 中央管理存储的池）</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>将 中央管理存储中的更改复制到 边缘服务器</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>任意（可定义为 控制器 IP、 前端服务器 IP 或池虚拟 IP）</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>内部部署到内部 边缘服务器接口的 Web 会议流量</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>任意（可定义为 控制器 IP、 前端服务器 IP 或池虚拟 IP）</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>用于内外部用户、Survivable Branch Appliance 或 Survivable Branch Server 间的 A/V 媒体传输的首选路径</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>任意（可定义为 控制器 IP、 前端服务器 IP 或池虚拟 IP）</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>用于内外部用户、Survivable Branch Appliance 或 Survivable Branch Server 间的 A/V 媒体传输的回退路径，如果无法建立 UDP 通信，则将 TCP 用于文件传输和桌面共享</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50001</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>集中日志记录服务控制器，使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行 (ClsController.exe) 或代理 (ClsAgent.exe) 命令和日志集合</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50002</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>集中日志记录服务控制器，使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行 (ClsController.exe) 或代理 (ClsAgent.exe) 命令和日志集合</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50003</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>集中日志记录服务控制器，使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行 (ClsController.exe) 或代理 (ClsAgent.exe) 命令和日志集合</p></td>
</tr>
</tbody>
</table>


当部署硬件负载平衡器以便为 Lync Server 提供可用性和负载平衡时，该工具具有特定要求。这些要求在下面的图和表中定义。第三方供应商可能对此处定义的要求使用不同的术语。若要将 Lync Server 的要求映射到您的硬件负载平衡器供应商提供的功能和配置选项，则这些要求是必需的。

在配置硬件负载平衡器时，请考虑以下要求：

  - 可在硬件负载平衡器 (HLB) 上为 访问边缘服务和 Web 会议边缘服务配置源网络地址转换 (SNAT)

  - 无法在 A/V 边缘服务上配置 SNAT - A/V 边缘服务必须使用真实的服务器地址（而不是 HLB 虚拟 IP (VIP)）进行响应，以便让 UDP 对 NAT 的简单穿越 (STUN)/使用中继 NAT (TURN)/联盟 TURN (FTURN) 的穿越正常运行

  - 公用 IP 地址在每个服务器接口上以及 HLB 的 VIP 上使用，您的公用 IP 地址要求是 N+1，其中，存在针对每个真实服务器接口的公用 IP 地址和针对每个 HLB VIP 的公用 IP 地址。当池中有 2 个边缘服务器时，这将生成 9 个公用 IP 地址，其中 3 个用于 HLB VIP，剩下的IP地址中，一个 IP 地址用于一个边缘服务器接口（服务器共有 6 个）

  - 对于 访问边缘服务和 Web 会议边缘服务，（并在 HLB 上使用 NAT）客户端会联系 VIP，VIP 将客户端中的源 IP 地址更改为其自己的 IP 地址。服务器接口会将返回地址寻址到 VIP，VIP 会更改服务器接口 IP 地址中的源地址并将数据包发送到客户端

  - 对于 A/V 边缘服务，VIP 不能更改源 IP 地址，真实服务器地址将直接返回到客户端 - 您无法在 HLB 上为 AV 流量配置 NAT

  - 对于 AV，外部防火墙将为所有数据包保留真实服务器公用 IP 地址

  - 客户端与 A/V 边缘服务的通信建立后，该通信将指向真实服务器，而不是 HLB

  - 必须路由内部边缘到内部服务器和客户端，且必须为所有承载服务器或客户端的内部网络设置持久路由

  - HLB 访问边缘服务 VIP 将充当每个边缘服务器接口的默认网关

![边缘服务器端口和协议详细信息](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "边缘服务器端口和协议详细信息")

### 扩展的合并边缘（硬件负载已平衡）所需的外部端口设置：外部接口虚拟 IP

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
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>任意</p></td>
<td><p>XMPP 代理服务（与访问边缘服务共享 IP 地址）</p></td>
<td><p>XMPP 代理服务接受来自在 XMPP 联盟中定义的 XMPP 联系人的流量</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>XMPP 代理服务（与访问边缘服务共享 IP 地址）</p></td>
<td><p>任意</p></td>
<td><p>XMPP 代理服务将流量发送到定义的 XMPP 联盟中的 XMPP 联系人</p></td>
</tr>
<tr class="odd">
<td><p>访问/SIP(TLS)/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>访问边缘服务公共 VIP 地址</p></td>
<td><p>外部用户访问的客户端到服务器的 SIP 通信</p></td>
</tr>
<tr class="even">
<td><p>访问/SIP(MTLS)/TCP/5061</p></td>
<td><p>任意</p></td>
<td><p>访问边缘服务公共 VIP 地址</p></td>
<td><p>SIP 信号，使用 SIP 的联盟和公共 IM 连接</p></td>
</tr>
<tr class="odd">
<td><p>访问/SIP(MTLS)/TCP/5061</p></td>
<td><p>访问边缘服务公共 VIP 地址</p></td>
<td><p>联盟伙伴</p></td>
<td><p>SIP 信号，使用 SIP 的联盟和公共 IM 连接</p></td>
</tr>
<tr class="even">
<td><p>Web 会议/PSOM(TLS)TCP/443</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器  Web 会议边缘服务公共 VIP 地址</p></td>
<td><p>Web 会议媒体</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器  A/V 边缘服务 公共 VIP 地址</p></td>
<td><p>通过 UDP/3478 进行的候选项 STUN/TURN 协商</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN,MSTURN/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器  A/V 边缘服务 公共 VIP 地址</p></td>
<td><p>通过 TCP/443 进行的候选项 STUN/TURN 协商</p></td>
</tr>
</tbody>
</table>


### 扩展的合并边缘（硬件负载已平衡）的防火墙摘要：内部接口虚拟 IP

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
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>访问/SIP(MTLS)/TCP/5061</p></td>
<td><p>任意（可定义为 控制器、 控制器池虚拟 IP 地址、 前端服务器或 前端池虚拟 IP 地址）</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>发往内部边缘 VIP 的出站 SIP 流量（来自 控制器、 控制器池虚拟 IP 地址、 前端服务器或 前端池虚拟 IP 地址）</p></td>
</tr>
<tr class="even">
<td><p>访问/SIP(MTLS)/TCP/5061</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>任意（可定义为 控制器、 控制器池虚拟 IP 地址、 前端服务器或 前端池虚拟 IP 地址）</p></td>
<td><p>来自 边缘服务器内部接口的入站 SIP 流量（发往 控制器、 控制器池虚拟 IP 地址、 前端服务器或 前端池虚拟 IP 地址）</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>任意（可定义为前端服务器 IP 地址或前端池 IP 地址，或任何使用此边缘服务器的 Survivable Branch Appliance 或 Survivable Branch Server）</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>来自前端服务器或前端池 IP 地址或任何使用此边缘服务器的 Survivable Branch Appliance 或 Survivable Branch Server 的 A/V 用户的身份验证（A/V 身份验证服务）</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>用于内外部用户间的 A/V 媒体传输的首选路径</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>用于内外部间的 A/V 媒体传输的回退路径，如果无法建立 UDP 通信，则将 TCP 用于文件传输和桌面共享</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>任意</p></td>
<td><p>用于内外部间的 A/V 媒体传输的回退路径，如果无法建立 UDP 通信，则将 TCP 用于文件传输和桌面共享</p></td>
</tr>
</tbody>
</table>

