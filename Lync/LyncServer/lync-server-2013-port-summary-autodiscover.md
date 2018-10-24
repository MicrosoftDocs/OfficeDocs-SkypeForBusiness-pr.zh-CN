---
title: Lync Server 2013 中的端口摘要 - 自动发现
TOCTitle: Lync Server 2013 中的端口摘要 - 自动发现
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ945642(v=OCS.15)
ms:contentKeyID: 52061058
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的端口摘要 - 自动发现

 

_**上一次修改主题：** 2016-04-06_

Lync Server 2013 自动发现服务运行于控制器和前端池服务器上，当使用 `lyncdiscover.<domain>` 和 `lyncdiscoverinternal.<domain>` 主机记录在 DNS 中发布时，可供客户端用来定位 Lync Server 功能。为便于运行 Lync Mobile 的移动设备使用自动发现，可能需要先在所有运行自动发现服务的控制器和前端服务器上修改证书使用者替代名称列表。此外，可能还需要修改证书上的供反向代理上的外部 Web 服务发布规则使用的使用者替代名称列表。

有关是否在反向代理上利用使用者替代名称列表的决定基于您是在端口 80 还是端口 443 上发布自动发现服务：

  - **在端口 80 上发布**   对于移动设备，如果对自动发现服务的初始查询发生在端口 80 上，则无需更改证书。这是因为运行 Lync 的移动设备将在外部端口 80 上访问反向代理，然后在内部端口 8080 上重定向至控制器或前端服务器。

  - **在端口 443 上发布**   外部 Web 服务发布规则使用的证书上的使用者替代名称列表必须为您组织中的每个 SIP 域包含一个 `lyncdiscover.<sipdomain>` 条目。
    
    > [!IMPORTANT]
    > 对于从已部署了 Mobility 的 Lync Server 2010 进行的新安装或升级，您或者已将端口 80 用于 Mobility Service 的自动发现，或者已重新颁发已具有适当使用者名称和使用者替代名称的证书。检查您的控制器和前端服务器上的证书来确认您选择了哪条路径。


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
<td><p>（可选）如果用户输入 http://<em>&lt;publishedSiteFQDN&gt;</em>，则重定向到 HTTPS。在组织不打算修改外部 Web 服务发布规则证书的情况下，如果将 Office Web Apps 用于会议，将自动发现服务用于运行 Lync 的移动设备，则此选项也是必需的。</p></td>
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
<td><p>前端服务器、前端池、控制器、控制器池、会议用 Office Web Apps</p></td>
<td><p>在组织不打算修改外部 Web 服务发布规则证书的情况下，如果将自动发现服务用于运行 Lync 的移动设备，则此选项是必需的。发送到反向代理外部接口上的端口 80 的流量将从反向代理内部接口重定向到端口 8080 上的池，以便池 Web 服务可将其与内部 Web 流量区分开来。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>内部反向代理接口</p></td>
<td><p>前端服务器、前端池、控制器、控制器池、会议用 Office Web Apps</p></td>
<td><p>发送到反向代理外部接口上的端口 443 的流量将从反向代理内部接口重定向到端口 4443 上的池，以便池 Web 服务可将其与内部 Web 流量区分开来。</p></td>
</tr>
</tbody>
</table>

