---
title: Lync Server 2013：端口摘要 - 扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）
TOCTitle: 端口摘要 - 扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）
ms:assetid: f7cbd0f1-841d-4116-8d17-e9d991daa4a8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205394(v=OCS.15)
ms:contentKeyID: 49314781
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的端口摘要 - 扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）

 

_**上一次修改主题：** 2015-03-09_

此方案体系结构中描述的 Lync Server 2013 边缘服务器功能非常类似于 Lync Server 2010 中实现的内容。最值得注意的是端口 **5269 over TCP**（可扩展消息传递和状态协议 (XMPP) 的入口）。Lync Server 2013 也可选择在边缘服务器或边缘池上以及前端服务器或前端池上的 XMPP 网关服务器上部署 XMPP 代理。

除了 IPv4 之外， 边缘服务器现在支持 IPv6。为了清楚起见，本方案中仅使用 IPv4。

**使用公用 IP 地址的扩展的合并边缘（DNS 负载平衡）的企业外围网络**

![扩展合并边缘](images/Gg412756.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "扩展合并边缘")

## 端口和协议详细信息

建议仅打开支持为其提供外部访问的功能所需的端口。

要对任何边缘服务进行远程访问，必须允许 SIP 流量进行双向流动，如入站/出站边缘流量图中所示。换言之，即时消息 (IM)、状态、Web 会议、音频/视频 (A/V) 和联盟中会涉及在访问边缘服务中接收和发送 SIP 消息。

### 使用公用 IP 地址的扩展的合并边缘（DNS 负载平衡）的防火墙摘要：外部接口 – 节点 1 和节点 2（示例）

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
<td><p>访问/HTTP/TCP/80</p></td>
<td><p>边缘服务器访问边缘服务公用 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>证书吊销/CRL 检查和检索</p></td>
</tr>
<tr class="odd">
<td><p>访问/DNS/TCP/53</p></td>
<td><p>边缘服务器访问边缘服务公用 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>通过 TCP 的 DNS 查询</p></td>
</tr>
<tr class="even">
<td><p>访问/DNS/UDP/53</p></td>
<td><p>边缘服务器访问边缘服务公用 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>通过 UDP 的 DNS 查询</p></td>
</tr>
<tr class="odd">
<td><p>访问/SIP(TLS)/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器访问边缘服务公用 IP 地址</p></td>
<td><p>外部用户访问的客户端到服务器的 SIP 通信</p></td>
</tr>
<tr class="even">
<td><p>访问/SIP(MTLS)/TCP/5061</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器访问边缘服务公用 IP 地址</p></td>
<td><p>对于使用 SIP 的联盟和公共 IM 连接</p></td>
</tr>
<tr class="odd">
<td><p>访问/SIP(MTLS)/TCP/5061</p></td>
<td><p>边缘服务器访问边缘服务公用 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>对于使用 SIP 的联盟和公共 IM 连接</p></td>
</tr>
<tr class="even">
<td><p>Web 会议/PSOM(TLS)TCP/443</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器Web 会议边缘服务公用 IP 地址</p></td>
<td><p>Web 会议媒体</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50,000-59,999</p></td>
<td><p>边缘服务器A/V 边缘服务公用 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>仅当与运行 Office Communications Server 2007、Office Communications Server 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作伙伴进行联盟时必需。</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50,000-59,999</p></td>
<td><p>边缘服务器A/V 边缘服务公用 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>仅当与运行 Office Communications Server 2007 的合作伙伴联盟时必需。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50,000-59,999</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器A/V 边缘服务公用 IP 地址</p></td>
<td><p>仅当与运行 Office Communications Server 2007 的合作伙伴联盟时必需</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50,000-59,999</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器A/V 边缘服务公用 IP 地址</p></td>
<td><p>仅当与运行 Office Communications Server 2007 的合作伙伴联盟时必需</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>边缘服务器A/V 边缘服务公用 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>3478 出站用于确定 Lync Server 与其进行通信的边缘服务器的版本，还用于从边缘服务器到边缘服务器的媒体流量。与 Lync Server 2010、Windows Live Messenger 和 Office Communications Server 2007 R2 联盟时必需，当公司中部署了多个边缘池时也是必需的。</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器A/V 边缘服务公用 IP 地址</p></td>
<td><p>通过 UDP/3478 进行的候选项 STUN/TURN 协商</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN,MSTURN/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器A/V 边缘服务公用 IP 地址</p></td>
<td><p>通过 TCP/443 进行的候选项 STUN/TURN 协商</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN,MSTURN/TCP/443</p></td>
<td><p>边缘服务器 A/V 边缘服务</p></td>
<td><p>任意</p></td>
<td><p>通过 TCP/443 进行的候选项 STUN/TURN 协商</p></td>
</tr>
</tbody>
</table>


### 使用公用 IP 地址的扩展的合并边缘（DNS 负载平衡）的防火墙摘要：外部接口 – 节点 1 和节点 2（示例）

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
<td><p>任意（可定义为运行 XMPP 网关服务的 前端服务器地址，或 前端池 IP 地址）</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>来自 前端服务器或 前端池上运行的 XMPP 网关服务的出站 XMPP 流量</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>任意（可以定义为 控制器、 控制器池 IP 地址、 前端服务器或 前端池 IP 地址）</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>流向 边缘服务器内部接口的出站 SIP 流量（来自 控制器、 控制器池 IP 地址、 前端服务器或 前端池 IP 地址）</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>任意（可以定义为 控制器、 控制器池 IP 地址、 前端服务器或 前端池 IP 地址）</p></td>
<td><p>来自 边缘服务器内部接口的入站 SIP 流量（流向 控制器、 控制器池 IP 地址、 前端服务器或 前端池 IP 地址）</p></td>
</tr>
<tr class="even">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>任意（可以定义为 前端服务器 IP 地址，或 前端池中的每个 前端服务器 IP 地址）</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>从 前端服务器或每个 前端服务器（如果位于池内）到 边缘服务器内部接口的 Web 会议流量</p></td>
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
<td><p>用于内外部用户、Survivable Branch Appliance 或 Survivable Branch Server 间的 A/V 媒体传输的首选路径</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>用于内外部用户、Survivable Branch Appliance 或 Survivable Branch Server 间的 A/V 媒体传输的回退路径，如果无法建立 UDP 通信，则将 TCP 用于文件传输和桌面共享</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>任意（可定义为 前端服务器 IP 地址，或承载 中央管理存储的池）</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>将 中央管理存储中的更改复制到 边缘服务器</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>集中日志记录服务控制器，使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行 (ClsController.exe) 或代理 (ClsAgent.exe) 命令和日志集合</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>集中日志记录服务控制器，使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行 (ClsController.exe) 或代理 (ClsAgent.exe) 命令和日志集合</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>集中日志记录服务控制器，使用 Lync Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行 (ClsController.exe) 或代理 (ClsAgent.exe) 命令和日志集合</p></td>
</tr>
</tbody>
</table>


## 联盟的防火墙摘要


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
<td><p>访问边缘服务公用 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>对于使用 SIP 的联盟和公共 IM 连接</p></td>
</tr>
</tbody>
</table>


## 防火墙摘要 – 公共即时消息连接


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
<td><p>公共 IM 连接合作伙伴</p></td>
<td><p>边缘服务器访问边缘服务 </p></td>
<td><p>对于使用 SIP 的联盟和公共 IM 连接</p></td>
</tr>
<tr class="even">
<td><p>访问/SIP(MTLS)/TCP/5061</p></td>
<td><p>边缘服务器访问边缘服务 </p></td>
<td><p>公共 IM 连接合作伙伴</p></td>
<td><p>对于使用 SIP 的联盟和公共 IM 连接</p></td>
</tr>
<tr class="odd">
<td><p>访问/SIP(TLS)/TCP/443</p></td>
<td><p>客户端</p></td>
<td><p>边缘服务器访问边缘服务 </p></td>
<td><p>外部用户访问的客户端到服务器的 SIP 通信</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50,000-59,999</p></td>
<td><p>边缘服务器 A/V 边缘服务</p></td>
<td><p>Live Messenger 客户端</p></td>
<td><p>用于与 Windows Live Messenger 的 A/V 会话，前提是配置了公共 IM 连接。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>边缘服务器 A/V 边缘服务</p></td>
<td><p>Live Messenger 客户端</p></td>
<td><p>需要与 Windows Live Messenger 的公共 IM 连接</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>Live Messenger 客户端</p></td>
<td><p>边缘服务器 A/V 边缘服务</p></td>
<td><p>需要与 Windows Live Messenger 的公共 IM 连接</p></td>
</tr>
</tbody>
</table>


## 可扩展消息传递和状态协议的防火墙摘要


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
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器 访问边缘服务 接口 IP 地址</p></td>
<td><p>用于 XMPP 的标准服务器到服务器通信端口。允许联盟 XMPP 伙伴至边缘服务器 XMPP 代理的通信</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>边缘服务器 访问边缘服务 接口 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>用于 XMPP 的标准服务器到服务器通信端口。允许联盟 XMPP 伙伴至边缘服务器 XMPP 代理的通信</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>任意</p></td>
<td><p>每个内部 边缘服务器接口 IP</p></td>
<td><p>从 前端服务器或 前端池上的 XMPP 网关至 边缘服务器内部 IP 地址或每个 边缘池成员的内部 IP 地址的内部 XMPP 流量</p></td>
</tr>
</tbody>
</table>

