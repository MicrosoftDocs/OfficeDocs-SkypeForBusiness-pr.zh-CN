---
title: Lync Server 2013：端口摘要 - 单一控制器
TOCTitle: 端口摘要 - 单一控制器
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204648(v=OCS.15)
ms:contentKeyID: 49311905
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的端口摘要 - 单一控制器

 

_**上一次修改主题：** 2015-03-09_

单个 控制器的防火墙端口要求由用来从反向代理的内部接口或面向内部的网络与控制器建立通信的端口组成。默认情况下， Microsoft Lync Server 2013 期待从反向代理到 控制器以及 前端池和 前端服务器打开 HTTP/TCP 8080 和 HTTPS/TCP 4443 端口。此外，还必须有从 边缘服务器内部接口到 控制器再到 前端池和 前端服务器的会话初始协议 (SIP) 通信。SIP 协议从 边缘服务器到 前端池和 前端服务器使用 SIP/MTLS/TCP 5061。还必须创建允许从 控制器、 前端池和 前端服务器到 边缘服务器内部接口的 SIP/MTLS/TCP 5061 通信的规则。

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
<td><p>控制器</p></td>
<td><p>最初由反向代理的外侧接收通信，然后，通信转发到 控制器和 前端服务器 Web 服务</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>反向代理内部接口</p></td>
<td><p>控制器</p></td>
<td><p>最初由反向代理的外侧接收通信，然后，通信转发到 控制器和 前端服务器 Web 服务</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>控制器</p></td>
<td><p>前端服务器或前端池</p></td>
<td><p>控制器和 前端服务器的服务器间通信</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>内部客户端</p></td>
<td><p>控制器 Web 服务</p></td>
<td><p>控制器向内部和外部客户端提供 Web 服务。</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>内部客户端</p></td>
<td><p>控制器 Web 服务</p></td>
<td><p>控制器向内部和外部客户端提供 Web 服务。</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>控制器</p></td>
<td><p>从边缘服务器到 控制器和 前端服务器的 SIP 通信。</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>集中日志记录服务控制器 (ClsController.exe) 或代理 (ClasAgent.exe) 命令和日志集</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>集中日志记录服务控制器 (ClsController.exe) 或代理 (ClasAgent.exe) 命令和日志集</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>集中日志记录服务控制器 (ClsController.exe) 或代理 (ClasAgent.exe) 命令和日志集</p></td>
</tr>
</tbody>
</table>

