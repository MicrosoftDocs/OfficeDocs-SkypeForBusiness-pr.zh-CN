---
title: Lync Server 2013：内部服务器的端口和协议
TOCTitle: 内部服务器的端口和协议
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398833(v=OCS.15)
ms:contentKeyID: 49314241
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的内部服务器的端口和协议

 

_**上一次修改主题：** 2016-04-06_

本节汇总了 Lync Server 部署中服务器、负载平衡器和客户端使用的端口和协议。

> [!IMPORTANT]
> 一对一通信中涉及的 Lync 和 Communicator 客户端通常称为对等客户端。从技术上来说，两个客户端在一对一对话中使用即时消息多点控制单元 (IMMCU) 进行通信。IMMCU 是 前端服务器 的一个组件。将 IMMCU 放在所需的通信工作流中允许进行呼叫详细信息记录和 前端服务器 启用的其他功能。通信从客户端上的动态源端口发送到 前端服务器 端口 TLS/TCP/5061（假设使用推荐的传输层安全性）。根据设计，只有当 Lync Server 和 IMMCU 处于活动状态且可用时，才可能实现对等通信（以及多方 IM）。


## 端口和协议详细信息

> [!NOTE]  
> Windows 防火墙必须在启动服务器的 Lync Server 服务之前就已运行，因为启动相应服务时 Lync Server 要在防火墙中打开所需端口。



有关边缘组件的防火墙配置的详细信息，请参阅[确定 Lync Server 2013 的外部 A/V 防火墙和端口要求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。

下表依据每个内部服务器角色列出了需要打开的端口。

### 所需服务器端口（根据服务器角色）

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>服务器角色</th>
<th>服务名称</th>
<th>端口</th>
<th>协议</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>所有服务器</p></td>
<td><p>SQL 浏览器</p></td>
<td><p>1434</p></td>
<td><p>UDP</p></td>
<td><p>SQL 浏览器用于中央管理存储数据库的本地副本。</p></td>
</tr>
<tr class="even">
<td><p>前端服务器</p></td>
<td><p>Lync Server 前端服务</p></td>
<td><p>5060</p></td>
<td><p>TCP</p></td>
<td><p>（可选）Standard Edition Server 和前端服务器用于静态路由到受信任服务，例如，远程呼叫控制服务器。</p></td>
</tr>
<tr class="odd">
<td><p>前端服务器</p></td>
<td><p>Lync Server 前端服务</p></td>
<td><p>5061</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Standard Edition Server 和前端池用于在服务器 (MTLS) 之间进行所有的内部 SIP 通信、在服务器和客户端 (TLS) 之间进行 SIP 通信，以及在前端服务器和中介服务器 (MTLS) 之间进行 SIP 通信。还用于与监控服务器进行通信。</p></td>
</tr>
<tr class="even">
<td><p>前端服务器</p></td>
<td><p>Lync Server 前端服务</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p>
<p>TCP</p></td>
<td><p>用于会议状态中心（管理会议状态的 Lync Server 组件）与单个服务器之间的 HTTPS 通信。</p>
<p>此端口也用于 Survivable Branch Appliance 与前端服务器之间的 TCP 通信。</p></td>
</tr>
<tr class="odd">
<td><p>前端服务器</p></td>
<td><p>Lync Server 前端服务</p></td>
<td><p>135</p></td>
<td><p>DCOM 和远程过程调用 (RPC)</p></td>
<td><p>用于基于 DCOM 的操作，例如，移动用户、用户复制程序同步和通讯簿同步。</p></td>
</tr>
<tr class="even">
<td><p>前端服务器</p></td>
<td><p>Lync Server IM 会议服务</p></td>
<td><p>5062</p></td>
<td><p>TCP</p></td>
<td><p>用于即时消息 (IM) 会议的传入 SIP 请求。</p></td>
</tr>
<tr class="odd">
<td><p>前端服务器</p></td>
<td><p>Lync Server Web 会议服务</p></td>
<td><p>8057</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>用于侦听来自客户端的持续性共享对象模型 (PSOM) 连接。</p></td>
</tr>
<tr class="even">
<td><p>前端服务器</p></td>
<td><p>Lync Server Web 会议兼容性服务</p></td>
<td><p>8058</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>用于侦听来自 Live Meeting 客户端和早期版本 Lync Server 的持续性共享对象模型 (PSOM) 连接。</p></td>
</tr>
<tr class="odd">
<td><p>前端服务器</p></td>
<td><p>Lync Server 音频/视频会议服务</p></td>
<td><p>5063</p></td>
<td><p>TCP</p></td>
<td><p>用于音频/视频 (A/V) 会议的传入 SIP 请求。</p></td>
</tr>
<tr class="even">
<td><p>前端服务器</p></td>
<td><p>Lync Server 音频/视频会议服务</p></td>
<td><p>57501 -65535</p></td>
<td><p>TCP/UDP</p></td>
<td><p>用于视频会议的媒体端口范围。</p></td>
</tr>
<tr class="odd">
<td><p>前端服务器</p></td>
<td><p>Lync Server Web 兼容性服务</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
<td><p>用于未使用 HTTPS 时从前端服务器到 Web 场 FQDN（IIS Web 组件使用的 URL）的通信。</p></td>
</tr>
<tr class="even">
<td><p>前端服务器</p></td>
<td><p>Lync Server Web 兼容性服务</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p>用于从前端服务器到 Web 场 FQDN（IIS Web 组件使用的 URL）的通信。</p></td>
</tr>
<tr class="odd">
<td><p>前端服务器</p></td>
<td><p>Lync Server Web 兼容性服务</p></td>
<td><p>8080</p></td>
<td><p>TCP 和 HTTP</p></td>
<td><p>用于 Web 组件供外部访问。</p></td>
</tr>
<tr class="even">
<td><p>前端服务器</p></td>
<td><p>Web 服务器组件</p></td>
<td><p>4443</p></td>
<td><p>HTTPS</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>前端服务器</p></td>
<td><p>Web 服务器组件</p></td>
<td><p>8060</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>前端服务器</p></td>
<td><p>Web 服务器组件</p></td>
<td><p>8061</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>前端服务器</p></td>
<td><p>Mobility Service 组件</p></td>
<td><p>5086</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Mobility Service 内部过程所使用的 SIP 端口。</p></td>
</tr>
<tr class="even">
<td><p>前端服务器</p></td>
<td><p>Mobility Service 组件</p></td>
<td><p>5087</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Mobility Service 内部过程所使用的 SIP 端口。</p></td>
</tr>
<tr class="odd">
<td><p>前端服务器</p></td>
<td><p>Mobility Service 组件</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>前端服务器</p></td>
<td><p>Lync Server 会议助理服务（电话拨入式会议）</p></td>
<td><p>5064</p></td>
<td><p>TCP</p></td>
<td><p>用于电话拨入式会议的传入 SIP 请求。</p></td>
</tr>
<tr class="odd">
<td><p>前端服务器</p></td>
<td><p>Lync Server 会议助理服务（电话拨入式会议）</p></td>
<td><p>5072</p></td>
<td><p>TCP</p></td>
<td><p>用于 助理（电话拨入式会议）的传入 SIP 请求。</p></td>
</tr>
<tr class="even">
<td><p>也运行并置中介服务器的前端服务器</p></td>
<td><p>Lync Server 中介服务</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
<td><p>中介服务器用于从前端服务器到中介服务器的传入请求。</p></td>
</tr>
<tr class="odd">
<td><p>也运行并置中介服务器的前端服务器</p></td>
<td><p>Lync Server 中介服务</p></td>
<td><p>5067</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>用于从 PSTN 网关到中介服务器的传入 SIP 请求。</p></td>
</tr>
<tr class="even">
<td><p>也运行并置中介服务器的前端服务器</p></td>
<td><p>Lync Server 中介服务</p></td>
<td><p>5068</p></td>
<td><p>TCP</p></td>
<td><p>用于从 PSTN 网关到中介服务器的传入 SIP 请求。</p></td>
</tr>
<tr class="odd">
<td><p>也运行并置中介服务器的前端服务器</p>
<p></p></td>
<td><p>Lync Server 中介服务</p>
<p></p></td>
<td><p>5081</p></td>
<td><p>TCP</p></td>
<td><p>用于从中介服务器到 PSTN 网关的传出 SIP 请求。</p></td>
</tr>
<tr class="even">
<td><p>也运行并置中介服务器的前端服务器</p>
<p></p></td>
<td><p>Lync Server 中介服务</p>
<p></p></td>
<td><p>5082</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>用于从中介服务器到 PSTN 网关的传出 SIP 请求。</p></td>
</tr>
<tr class="odd">
<td><p>前端服务器</p></td>
<td><p>Lync Server 应用程序共享服务</p></td>
<td><p>5065</p></td>
<td><p>TCP</p></td>
<td><p>用于应用程序共享的传入 SIP 侦听请求。</p></td>
</tr>
<tr class="even">
<td><p>前端服务器</p></td>
<td><p>Lync Server 应用程序共享服务</p></td>
<td><p>49152 -65535</p></td>
<td><p>TCP</p></td>
<td><p>用于应用程序共享的媒体端口范围。</p></td>
</tr>
<tr class="odd">
<td><p>前端服务器</p></td>
<td><p>Lync Server 会议通知服务</p></td>
<td><p>5073</p></td>
<td><p>TCP</p></td>
<td><p>用于 Lync Server 会议通知服务（即，电话拨入式会议）的传入 SIP 请求。</p></td>
</tr>
<tr class="even">
<td><p>前端服务器</p></td>
<td><p>Lync Server 呼叫寄存服务</p></td>
<td><p>5075</p></td>
<td><p>TCP</p></td>
<td><p>用于呼叫寄存应用程序的传入 SIP 请求。</p></td>
</tr>
<tr class="odd">
<td><p>前端服务器</p></td>
<td><p>Lync Server 音频测试服务</p></td>
<td><p>5076</p></td>
<td><p>TCP</p></td>
<td><p>用于音频测试服务的传入 SIP 请求。</p></td>
</tr>
<tr class="even">
<td><p>前端服务器</p></td>
<td><p>不适用</p></td>
<td><p>5066</p></td>
<td><p>TCP</p></td>
<td><p>用于出站增强型 9-1-1 (E9-1-1) 网关。</p></td>
</tr>
<tr class="odd">
<td><p>前端服务器</p></td>
<td><p>Lync Server 响应组服务</p></td>
<td><p>5071</p></td>
<td><p>TCP</p></td>
<td><p>用于响应组应用程序的传入 SIP 请求。</p></td>
</tr>
<tr class="even">
<td><p>前端服务器</p></td>
<td><p>Lync Server 响应组服务</p></td>
<td><p>8404</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>用于响应组应用程序的传入 SIP 请求。</p></td>
</tr>
<tr class="odd">
<td><p>前端服务器</p></td>
<td><p>Lync Server 带宽策略服务</p></td>
<td><p>5080</p></td>
<td><p>TCP</p></td>
<td><p>用于通过带宽策略服务对 A/V 边缘 TURN 流量进行呼叫允许控制。</p></td>
</tr>
<tr class="even">
<td><p>前端服务器</p></td>
<td><p>Lync Server 带宽策略服务</p></td>
<td><p>448</p></td>
<td><p>TCP</p></td>
<td><p>用于通过 Lync Server 带宽策略服务进行呼叫允许控制。</p></td>
</tr>
<tr class="odd">
<td><p>中央管理存储所在的前端服务器</p></td>
<td><p>Lync Server 主复制程序代理服务</p></td>
<td><p>445</p></td>
<td><p>TCP</p></td>
<td><p>用于将中央管理存储中的配置数据推送到运行 Lync Server 的服务器。</p></td>
</tr>
<tr class="even">
<td><p>所有服务器</p></td>
<td><p>SQL 浏览器</p></td>
<td><p>1434</p></td>
<td><p>UDP</p></td>
<td><p>本地 SQL Server 实例中的中央管理存储数据的本地副本的 SQL 浏览器。</p></td>
</tr>
<tr class="odd">
<td><p>所有内部服务器</p></td>
<td><p>各种</p></td>
<td><p>49152 -57500</p></td>
<td><p>TCP/UDP</p></td>
<td><p>用于所有内部服务器上的音频会议的媒体端口范围。由终止音频的所有服务器使用：前端服务器（用于 Lync Server 会议助理服务、Lync Server 会议通知服务和 Lync Server 音频/视频会议服务）和中介服务器。</p></td>
</tr>
<tr class="even">
<td><p>Office Web Apps Servers</p></td>
<td><p></p></td>
<td><p>443</p></td>
<td><p></p></td>
<td><p>由 Lync Server 2013 使用以连接到 Office Web Apps Server。</p></td>
</tr>
<tr class="odd">
<td><p>控制器</p></td>
<td><p>Lync Server 前端服务</p></td>
<td><p>5060</p></td>
<td><p>TCP</p></td>
<td><p>（可选）用于静态路由到受信任服务，例如，远程呼叫控制服务器。</p></td>
</tr>
<tr class="even">
<td><p>控制器</p></td>
<td><p>Lync Server 前端服务器</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p>
<p>TCP</p></td>
<td><p>前端与控制器之间的服务器间通信。此外，客户端证书将发布（到前端服务器）或验证是否已发布客户端证书。</p></td>
</tr>
<tr class="odd">
<td><p>控制器</p></td>
<td><p>Lync Server Web 兼容性服务</p></td>
<td><p>80</p></td>
<td><p>TCP</p></td>
<td><p>用于从控制器到 Web 场 FQDN（IIS Web 组件使用的 URL）的初始通信。在常规操作中，将使用端口 443 和协议类型 TCP 切换到 HTTPS 通信。</p></td>
</tr>
<tr class="even">
<td><p>控制器</p></td>
<td><p>Lync Server Web 兼容性服务</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p>用于从控制器到 Web 场 FQDN（IIS Web 组件使用的 URL）之间的通信。</p></td>
</tr>
<tr class="odd">
<td><p>控制器</p></td>
<td><p>Lync Server 前端服务</p></td>
<td><p>5061</p></td>
<td><p>TCP</p></td>
<td><p>用于服务器之间的内部通信和客户端连接。</p></td>
</tr>
<tr class="even">
<td><p>中介服务器</p></td>
<td><p>Lync Server 中介服务</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
<td><p>中介服务器用于来自前端服务器的传入请求。</p></td>
</tr>
<tr class="odd">
<td><p>中介服务器</p></td>
<td><p>Lync Server 中介服务</p></td>
<td><p>5067</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>用于来自 PSTN 网关的传入 SIP 请求。</p></td>
</tr>
<tr class="even">
<td><p>中介服务器</p></td>
<td><p>Lync Server 中介服务</p></td>
<td><p>5068</p></td>
<td><p>TCP</p></td>
<td><p>用于来自 PSTN 网关的传入 SIP 请求。</p></td>
</tr>
<tr class="odd">
<td><p>中介服务器</p></td>
<td><p>Lync Server 中介服务</p></td>
<td><p>5070</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>用于来自前端服务器的 SIP 请求。</p></td>
</tr>
<tr class="even">
<td><p>持久聊天前端服务器</p></td>
<td><p>持久聊天 SIP</p></td>
<td><p>5041</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>持久聊天前端服务器</p></td>
<td><p>持久聊天 Windows Communication Foundation (WCF)</p></td>
<td><p>881</p></td>
<td><p>TCP (TLS) 和 TCP (MTLS)</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>持久聊天前端服务器</p></td>
<td><p>持久聊天文件传输服务</p></td>
<td><p>443</p></td>
<td><p>TCP (TLS)</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> 某些远程呼叫控制方案需要前端服务器或控制器与 PBX 之间的 TCP 连接。虽然 Lync Server 不再使用 TCP 端口 5060，但是在远程呼叫控制部署期间会创建受信任的服务器配置，这样会将 RCC Line Server FQDN 与前端服务器或控制器用来连接到 PBX 系统的 TCP 端口关联。有关详细信息，请参阅 Lync Server 命令行管理程序文档中的 <strong>CsTrustedApplicationComputer</strong> cmdlet。



对于仅使用硬件负载平衡（不是 DNS 负载平衡）的池，下表显示了需要打开硬件负载平衡器的端口。

### 仅使用硬件负载平衡时的硬件负载平衡器端口

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>负载平衡器</th>
<th>端口</th>
<th>协议</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>前端服务器负载平衡器</p></td>
<td><p>5061</p></td>
<td><p>TCP (TLS)</p></td>
</tr>
<tr class="even">
<td><p>前端服务器负载平衡器</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>前端服务器负载平衡器</p></td>
<td><p>135</p></td>
<td><p>DCOM 和远程过程调用 (RPC)</p></td>
</tr>
<tr class="even">
<td><p>前端服务器负载平衡器</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
</tr>
<tr class="odd">
<td><p>前端服务器负载平衡器</p></td>
<td><p>8080</p></td>
<td><p>TCP - 从前端服务器中进行的客户端和设备根证书检索 – NTLM 授权的客户端和设备</p></td>
</tr>
<tr class="even">
<td><p>前端服务器负载平衡器</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>前端服务器负载平衡器</p></td>
<td><p>4443</p></td>
<td><p>HTTPS（来自反向代理）</p></td>
</tr>
<tr class="even">
<td><p>前端服务器负载平衡器</p></td>
<td><p>5072</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>前端服务器负载平衡器</p>
<p></p></td>
<td><p>5073</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>前端服务器负载平衡器</p>
<p></p></td>
<td><p>5075</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>前端服务器负载平衡器</p>
<p></p></td>
<td><p>5076</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>前端服务器负载平衡器</p>
<p></p></td>
<td><p>5071</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>前端服务器负载平衡器</p>
<p></p></td>
<td><p>5080</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>前端服务器负载平衡器</p>
<p></p></td>
<td><p>448</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>中介服务器负载平衡器</p>
<p></p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>前端服务器负载平衡器（如果池也运行中介服务器）</p>
<p></p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>控制器负载平衡器</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>控制器负载平衡器</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>控制器负载平衡器</p>
<p></p></td>
<td><p>5061</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>控制器负载平衡器</p></td>
<td><p>4443</p></td>
<td><p>HTTPS（来自反向代理）</p></td>
</tr>
</tbody>
</table>


使用 DNS 负载平衡的前端池和控制器池还必须部署硬件负载平衡器。下表显示了需要在这些硬件负载平衡器上打开的端口。

### 使用 DNS 负载平衡时的硬件负载平衡器端口

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>负载平衡器</th>
<th>端口</th>
<th>协议</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>前端服务器负载平衡器</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
</tr>
<tr class="even">
<td><p>前端服务器负载平衡器</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>前端服务器负载平衡器</p></td>
<td><p>8080</p></td>
<td><p>TCP - 从前端服务器中进行的客户端和设备根证书检索 – NTLM 授权的客户端和设备</p></td>
</tr>
<tr class="even">
<td><p>前端服务器负载平衡器</p></td>
<td><p>4443</p></td>
<td><p>HTTPS（来自反向代理）</p></td>
</tr>
<tr class="odd">
<td><p>控制器负载平衡器</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p>控制器负载平衡器</p></td>
<td><p>4443</p></td>
<td><p>HTTPS（来自反向代理）</p></td>
</tr>
</tbody>
</table>


### 所需客户端端口

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>组件</th>
<th>端口</th>
<th>协议</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>客户端</p></td>
<td><p>67/68</p></td>
<td><p>DHCP</p></td>
<td><p>Lync Server 用来查找注册器 FQDN（也就是说，如果 DNS SRV 发生故障，且未配置手动设置）。</p></td>
</tr>
<tr class="even">
<td><p>客户端</p>
<p></p></td>
<td><p>443</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>用于外部用户访问的客户端到服务器 SIP 通信。</p></td>
</tr>
<tr class="odd">
<td><p>客户端</p></td>
<td><p>443</p></td>
<td><p>TCP (PSOM/TLS)</p></td>
<td><p>用于外部用户访问 Web 会议会话。</p></td>
</tr>
<tr class="even">
<td><p>客户端</p></td>
<td><p>443</p></td>
<td><p>TCP (STUN/MSTURN)</p></td>
<td><p>用于外部用户访问 A/V 会话和媒体 (TCP)。</p></td>
</tr>
<tr class="odd">
<td><p>客户端</p></td>
<td><p>3478</p></td>
<td><p>UDP (STUN/MSTURN)</p></td>
<td><p>用于外部用户访问 A/V 会话和媒体 (UDP)。</p></td>
</tr>
<tr class="even">
<td><p>客户端</p></td>
<td><p>5061</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>用于外部用户访问的客户端到服务器 SIP 通信。</p></td>
</tr>
<tr class="odd">
<td><p>客户端</p></td>
<td><p>6891 -6901</p></td>
<td><p>TCP</p></td>
<td><p>用于在 Lync 客户端和以前的客户端（Microsoft Office Communications Server 2007 R2、Microsoft Office Communications Server 2007 和 Live Communications Server 2005 的客户端）之间进行文件传输。</p></td>
</tr>
<tr class="even">
<td><p>客户端</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP/UDP</p></td>
<td><p>音频端口范围（最少需要 20 个端口）。</p></td>
</tr>
<tr class="odd">
<td><p>客户端</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP/UDP</p>
<p></p></td>
<td><p>视频端口范围（最少需要 20 个端口）。</p></td>
</tr>
<tr class="even">
<td><p>客户端</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP</p></td>
<td><p>对等文件传输（对于会议文件传输，客户端使用 PSOM）。</p></td>
</tr>
<tr class="odd">
<td><p>客户端</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP</p></td>
<td><p>应用程序共享。</p></td>
</tr>
<tr class="even">
<td><p>Aastra 6721ip 公用区域电话</p>
<p>Aastra 6725ip 桌面电话</p>
<p>HP 4110 IP Phone（公用区域电话）</p>
<p>HP 4120 IP Phone（桌面电话）</p>
<p>Polycom CX500 IP 公用区域电话</p>
<p>Polycom CX600 IP 桌面电话</p>
<p>Polycom CX700 IP 桌面电话</p>
<p>Polycom CX3000 IP 会议电话</p></td>
<td><p>67/68</p></td>
<td><p>DHCP</p></td>
<td><p>列出的设备用来查找 Lync Server 证书、设置 FQDN 和注册器 FQDN。</p></td>
</tr>
</tbody>
</table>


**\***若要为这些媒体类型配置特定端口，请使用 CsConferencingConfiguration cmdlet（ClientMediaPortRangeEnabled、ClientMediaPort 和 ClientMediaPortRange parameters）。

> [!NOTE]  
> Lync 客户端的设置程序会自动在客户端计算机上创建所需的操作系统防火墙例外。



> [!NOTE]  
> 在客户端必须遍历组织的防火墙的任何方案中，都需要用于外部用户访问的端口（例如，由其他组织承载的任何外部通信或会议）。


