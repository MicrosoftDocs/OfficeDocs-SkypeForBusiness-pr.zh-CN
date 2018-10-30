---
title: Lync Server 2013：端口摘要 - 扩展的控制器池、硬件负载平衡器
TOCTitle: 端口摘要 - 扩展的控制器池、硬件负载平衡器
ms:assetid: 6ae2f4ac-5b64-4e45-8253-133308f5812d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204983(v=OCS.15)
ms:contentKeyID: 49313146
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的端口摘要 - 扩展的控制器池、硬件负载平衡器

 

_**上一次修改主题：** 2015-03-09_

控制器池的防火墙端口要求包含用于从 边缘服务器的内部接口或反向代理的面向内部的接口建立与 控制器的通信的接口。默认情况下， Microsoft Lync Server 2013 期望在反向代理与 控制器以及 前端池和 前端服务器之间打开端口 HTTP/TCP 8080 和 HTTPS/TCP 4443。此外，必须在 边缘服务器内部接口与 控制器以及 前端池和 前端服务器之间建立会话初始协议 (SIP) 通信。此 SIP 协议在 边缘服务器与 前端池和 前端服务器之间使用 SIP/MTLS/TCP 5061。还必须创建允许在 控制器、 前端池和 前端服务器与 边缘服务器内部接口之间进行 SIP/MTLS/TCP 5061 通信的规则。

### 用于防火墙定义的控制器端口和协议

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
<td><p>最初由反向代理的外部端接收，通信将发送到 控制器 HLB VIP 和 前端服务器 Web 服务</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>反向代理内部接口</p></td>
<td><p>控制器硬件负载平衡器 VIP</p></td>
<td><p>最初由反向代理的外部端接收，通信将发送到 控制器 HLB VIP 和 前端服务器 Web 服务</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>控制器</p></td>
<td><p>前端服务器或 前端池</p></td>
<td><p>控制器 HLB VIP 和 前端服务器之间的服务器间通信</p></td>
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
<td><p>控制器硬件负载平衡器 VIP</p></td>
<td><p>边缘服务器与 控制器和 前端服务器之间的 SIP 通信。</p></td>
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

