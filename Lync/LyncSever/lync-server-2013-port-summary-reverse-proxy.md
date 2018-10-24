---
title: Lync Server 2013：端口摘要 - 反向代理
TOCTitle: 端口摘要 - 反向代理
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204932(v=OCS.15)
ms:contentKeyID: 49312932
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的端口摘要 - 反向代理

 

_**上一次修改主题：** 2015-03-09_

反向代理对于防火墙和端口/协议具有最低要求。

  - 外部防火墙要求是 HTTPS/TCP/443 和可选的 HTTP/TCP/80。HTTPS 用于通过反向代理的 SSL 和 TLS 安全通信。在修改证书可能证明很难或成本不合理时，如果您选择允许访问自动发现服务，则使用 HTTP。

  - 客户端预期通过 HTTPS 与 Office Web Apps Server 联系。 Office Web Apps Server 预期通过 HTTPS/TCP/443 的来自内部客户端的通信。推荐的配置是允许从反向代理到 Office Web Apps Server 的 HTTPS/TCP/443。

  - 端口 8080 用于将流量从反向代理内部接口路由到 前端服务器、 前端池虚拟 IP (VIP) 或可选的 控制器或 控制器池 VIP。在对外部 Web 服务发布规则证书的修改不恰当时（例如，如果您有大量 SIP 域），运行 Lync 的移动设备定位自动发现服务需要端口 TCP 8080。如果选择使用必需的 SAN 项获取新证书，则端口 TCP 8080 是不需要的并且是可选的。

  - 端口 4443 用于从反向代理内部接口路由到 前端服务器、 前端池虚拟 IP (VIP) 或可选的 控制器或 控制器池 VIP 的流量
    
    ![反向代理和外部 Web 服务](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "反向代理和外部 Web 服务")  
    
    > [!CAUTION]
    > 不要将来自内部部署的反向代理的 4443 over TCP 与来自 Standard Edition 服务器或保存 中央管理存储角色的 前端池的端口 4443 over TCP 流量混淆。


## 端口和协议详细信息

### 反向代理服务器的防火墙详细信息：外部接口

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
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/80</p></td>
<td><p>任意</p></td>
<td><p>反向代理侦听器</p></td>
<td><p>（可选）如果用户输入 http://<em>&lt;publishedSiteFQDN&gt;</em>，则重定向到 HTTPS。</p>
<p>在组织不需要修改外部 Web 服务发布规则证书的情况下对运行 Lync 的移动设备使用用于会议的 Office Web Apps 和自动发现服务时也是必需的。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>反向代理侦听器</p></td>
<td><p>通讯簿下载、通讯簿 Web 查询服务、自动发现、客户端更新、会议内容、设备更新、组扩展、会议用 Office Web Apps 和电话拨入式会议。</p></td>
</tr>
</tbody>
</table>


### 反向代理服务器的防火墙详细信息：内部接口

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
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/8080</p></td>
<td><p>内部反向代理接口</p></td>
<td><p>前端服务器、 前端池、 控制器、 控制器池</p></td>
<td><p>在组织不需要修改外部 Web 服务发布规则证书时对运行 Lync 的移动设备使用自动发现服务时是必需的。</p>
<p>发送到反向代理外部接口上的端口 80 的流量将从反向代理内部接口重定向到端口 8080 上的池，以便池 Web 服务可将其与内部 Web 流量区分开来。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>内部反向代理接口</p></td>
<td><p>前端服务器、 前端池、 控制器、 控制器池</p></td>
<td><p>发送到反向代理外部接口上的端口 443 的流量将从反向代理内部接口重定向到端口 4443 上的池，以便池 Web 服务可将其与内部 Web 流量区分开来。</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP/443</p></td>
<td><p>内部反向代理接口</p></td>
<td><p>用于会议的 Office Web Apps</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

