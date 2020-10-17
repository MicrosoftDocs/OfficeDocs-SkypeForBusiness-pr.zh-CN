---
title: Lync Server 2013：端口摘要-自动发现
description: Lync Server 2013：端口摘要-自动发现。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Autodiscover
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945642(v=OCS.15)
ms:contentKeyID: 51541497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20a5ef54d4ad8419fd6e73909f97764bf1290c22
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543138"
---
# <a name="port-summary---autodiscover-in-lync-server-2013"></a>Lync Server 2013 中的端口摘要-自动发现

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-03-05_

Lync Server 2013 自动发现服务在控制器和前端池服务器上运行，并且在使用和主机记录在 DNS 中发布时， `lyncdiscover.<domain>` `lyncdiscoverinternal.<domain>` 客户端可以使用它们查找 Lync Server 功能。 为了使 Lync Mobile 运行的移动设备使用自动发现，您可能需要首先在运行自动发现服务的任何控制器和前端服务器上修改证书主题备用名称列表。 此外，可能还必须修改证书上的供反向代理上的外部 Web 服务发布规则使用的使用者替代名称列表。

有关是否在反向代理上使用主题备用名称列表的决策取决于您是在端口80上还是在端口443上发布自动发现服务：

  - **已在端口 80**     上发布对于移动设备，如果对自动发现服务的初始查询在端口80上发生，则不需要进行证书更改。 这是因为运行 Lync 的移动设备将在外部端口80上访问反向代理，然后在内部将其重定向到端口8080上的控制器或前端服务器。

  - **已在端口 443**     上发布外部 web 服务发布规则所使用的证书上的 "主题备用名称" 列表必须包含 `lyncdiscover.<sipdomain>` 组织内每个 SIP 域的条目。
    
    <div>
    

    > [!IMPORTANT]  
    > 对于部署了移动性的 Lync Server 2010 的全新安装或升级，您可以使用端口80自动发现移动服务，或者就地重新颁发具有正确主题名称和使用者备用名称的证书。 查看控制器和前端服务器上的证书，确认选择了哪个路径。

    
    </div>

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
<td><p>任何</p></td>
<td><p>反向代理侦听器</p></td>
<td><p> (可选) 重定向到 HTTPS （如果用户进入 http:// &lt; publishedSiteFQDN &gt; 。 如果在组织不想修改外部 Web 服务发布规则证书的情况下，使用 Office Web Apps for 会议和运行 Lync 的移动设备的自动发现服务，也需要使用此属性。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/443</p></td>
<td><p>任何</p></td>
<td><p>反向代理侦听器</p></td>
<td><p>通讯簿下载、通讯簿 Web 查询服务、自动发现、客户端更新、会议内容、设备更新、组扩展、Office Web Apps for 会议、电话拨入式会议和会议。</p></td>
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
<td><p>前端服务器、前端池、控制器、控制器池、适用于会议的 Office Web Apps</p></td>
<td><p>如果组织不想修改外部 web 服务发布规则证书的情况下，使用运行 Lync 的移动设备的自动发现服务，则为必需。 发送到反向代理外部接口上的端口 80 的流量将从反向代理内部接口重定向到端口 8080 上的池，以便池 Web 服务可将其与内部 Web 流量区分开来。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>内部反向代理接口</p></td>
<td><p>前端服务器、前端池、控制器、控制器池、适用于会议的 Office Web Apps</p></td>
<td><p>发送到反向代理外部接口上的端口 443 的流量将从反向代理内部接口重定向到端口 4443 上的池，以便池 Web 服务可将其与内部 Web 流量区分开来。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

