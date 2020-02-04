---
title: Lync Server 2013：端口摘要 - 反向代理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Reverse proxy
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204932(v=OCS.15)
ms:contentKeyID: 48184251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2944cde932413f00b5a4dcb75cd4a37bd5b3a3a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a>Lync Server 2013 中的端口摘要 - 反向代理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-15_

反向代理对防火墙和端口/协议具有最低要求。

  - 外部防火墙要求是 HTTPS/TCP/443 以及可选的 HTTP/TCP/80。 HTTPS 用于通过反向代理进行 SSL 和 TLS 安全通信。 如果你选择允许在修改证书时访问自动发现服务的操作可能很难或不会导致成本调整，则使用 HTTP。

  - 客户端希望在 HTTPS 上联系 Office Web Apps 服务器。 Office Web Apps 服务器需要来自 HTTPS/TCP/443 的内部客户端的通信。 建议的配置是允许从反向代理到 Office Web Apps 服务器的 HTTPS/TCP/443。

  - 端口8080用于将流量从反向代理内部接口路由到前端服务器、前端池虚拟 IP （VIP）或可选控制器或控制器池 VIP。 在需要修改外部 web 服务发布规则证书的情况下（例如，如果你有大量 SIP 域），运行 Lync 的移动设备需要端口 TCP 8080 以找到自动发现服务。 如果你选择用所需的 SAN 条目获取新的证书，则不需要端口 TCP 8080，并且是可选的。

  - 端口4443用于从反向代理内部接口到前端服务器、前端池虚拟 IP （VIP）或可选控制器或控制器池 VIP 的流量
    
    ![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")  
    
    <div>
    

    > [!WARNING]  
    > 不要将4443中的与来自管理中央管理存储角色的标准版服务器或前端池的 TCP 流量的端口4443的内部部署相混淆。

    
    </div>

<div>

## <a name="port-and-protocol-details"></a>端口和协议详细信息

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a>反向代理服务器的防火墙详细信息：外部接口

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
<th>注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/80</p></td>
<td><p>任意</p></td>
<td><p>反向代理侦听器</p></td>
<td><p>可选如果用户进入 http://&lt;publishedSiteFQDN&gt;，则重定向到 HTTPS。</p>
<p>如果在组织不希望修改外部 Web 服务发布规则证书的情况下，使用适用于会议的 Office Web Apps 和适用于运行 Lync 的移动设备的自动发现服务，也需要使用此参数。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>反向代理侦听器</p></td>
<td><p>通讯簿下载，通讯簿 Web 查询服务，自动发现，客户端更新，会议内容，设备更新，组扩展，适用于会议的 Office Web Apps，电话拨入式会议和会议。</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a>反向代理服务器的防火墙详细信息：内部接口

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
<th>注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/8080</p></td>
<td><p>内部反向代理接口</p></td>
<td><p>前端服务器、前端池、导演、控制器池</p></td>
<td><p>如果在组织不希望修改外部 web 服务发布规则证书的情况下使用运行 Lync 的移动设备的自动发现服务，则为必需。</p>
<p>发送到反向代理外部接口上的端口80的流量将从反向代理内部接口重定向到端口8080上的池，以便池 Web 服务可以将其与内部 Web 流量区分开。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>内部反向代理接口</p></td>
<td><p>前端服务器、前端池、导演、控制器池</p></td>
<td><p>发送到反向代理外部接口上的端口443的流量将从反向代理内部接口重定向到端口4443上的池，以便池 web 服务可以将其与内部 web 流量区分开。</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP/443</p></td>
<td><p>内部反向代理接口</p></td>
<td><p>适用于会议的 Office Web Apps</p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

