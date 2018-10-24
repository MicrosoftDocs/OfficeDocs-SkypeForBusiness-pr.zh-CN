---
title: Lync Server 2013：端口摘要 - 已进行 DNS 和 HLB 负载平衡
TOCTitle: 端口摘要 - 已进行 DNS 和 HLB 负载平衡
ms:assetid: b07c37e4-820e-46ee-a678-1da95d1b87af
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205179(v=OCS.15)
ms:contentKeyID: 49313941
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的端口摘要 - 已进行 DNS 和 HLB 负载平衡

 

_**上一次修改主题：** 2015-03-09_

单个 控制器的防火墙端口要求包含用来从反向代理的内部接口或面向内部的网络与 控制器建立通信的端口。默认情况下， Microsoft Lync Server 2013 需要端口 HTTP/TCP 8080 和 HTTPS/TCP 4443 从反向代理打开到 控制器以及 前端池和 前端服务器。此外，必须存在从 边缘服务器内部接口到 控制器以及到 前端池和 前端服务器的会话初始协议 (SIP) 通信。SIP 协议使用从 边缘服务器到 前端池和 前端服务器的 SIP/MTLS/TCP 5061。同时必须创建可允许从 控制器、 前端池和 前端服务器到 边缘服务器内部接口的 SIP/MTLS/TCP 5061 通信的规则。

### 用于防火墙定义的单个 控制器端口和协议

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
<td><p>HTTP/TCP 8080</p></td>
<td><p>反向代理内部接口</p></td>
<td><p>控制器硬件负载平衡器 VIP</p></td>
<td><p>通信最初是由反向代理的外部端进行接收，系统会将其发送到 控制器 HLB VIP 和 前端服务器 Web 服务上。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>反向代理内部接口</p></td>
<td><p>控制器硬件负载平衡器 VIP</p></td>
<td><p>通信最初是由反向代理的外部端进行接收，系统会将其发送到 控制器 HLB VIP 和 前端服务器 Web 服务上。</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>控制器</p></td>
<td><p>前端池 或 前端服务器</p></td>
<td><p>控制器 HLB VIP 与一个 前端服务器或多个 前端服务器之间的服务器间通信。</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>内部客户端</p></td>
<td><p>控制器硬件负载平衡器 VIP</p></td>
<td><p>控制器会将 Web 服务提供给内部以及外部客户端。</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>内部客户端</p></td>
<td><p>控制器硬件负载平衡器 VIP</p></td>
<td><p>控制器会将 Web 服务提供给内部以及外部客户端。</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>控制器</p></td>
<td><p>从边缘服务器到 控制器以及 前端服务器的 SIP 通信。</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>任意</p></td>
<td><p>控制器</p></td>
<td><p>集中日志记录服务控制器 (ClsController.exe) 或代理 (ClsAgent.exe) 命令和日志集合</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>任意</p></td>
<td><p>控制器</p></td>
<td><p>集中日志记录服务控制器 (ClsController.exe) 或代理 (ClsAgent.exe) 命令和日志集合</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>任意</p></td>
<td><p>控制器</p></td>
<td><p>集中日志记录服务控制器 (ClsController.exe) 或代理 (ClsAgent.exe) 命令和日志集合</p></td>
</tr>
</tbody>
</table>

