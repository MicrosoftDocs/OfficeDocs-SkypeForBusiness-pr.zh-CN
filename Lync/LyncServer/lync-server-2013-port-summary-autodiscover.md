---
title: Lync Server 2013：端口摘要-自动发现
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
ms.openlocfilehash: 945e3ed9d532f27676e250c29ab415646bd967ec
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---autodiscover-in-lync-server-2013"></a>端口摘要-Lync Server 2013 中的自动发现

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-03-05_

Lync Server 2013 自动发现服务在 Director 和前端池服务器上运行，并且当使用和`lyncdiscover.<domain>` `lyncdiscoverinternal.<domain>`主机记录在 DNS 中发布时，客户端可以使用该服务查找 Lync Server 功能。 为使 Lync Mobile 运行的移动设备使用自动发现，你可能需要首先在运行自动发现服务的任何控制器和前端服务器上修改证书主题备用名称列表。 此外，可能还需要修改用于反向代理上的外部 web 服务发布规则的证书上的使用者备用名称列表。

有关是否在反向代理上使用主题备用名称列表的决策取决于你是在端口80还是在端口443上发布自动发现服务：

  - **已在端口 80**   上发布对于移动设备，如果对自动发现服务的初始查询通过端口80进行，则不需要进行证书更改。 这是因为运行 Lync 的移动设备将外部访问端口80上的反向代理，然后在内部将其重定向到端口8080上的 Director 或前端服务器。

  - **在端口 443**   上发布在外部 web 服务发布规则使用的证书上的 "使用者备用名称" `lyncdiscover.<sipdomain>`列表中，必须包含组织内每个 SIP 域的条目。
    
    <div>
    

    > [!IMPORTANT]  
    > 对于部署了移动性的 Lync Server 2010 的全新安装或升级，你可以使用端口80自动发现移动服务，或者将证书重新颁发给适当的主题名称和主题备用名称。 查看控制器和前端服务器上的证书以确认您选择的路径。

    
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
<td><p>任意</p></td>
<td><p>反向代理侦听器</p></td>
<td><p>可选如果用户进入 http://&lt;publishedSiteFQDN&gt;，则重定向到 HTTPS。 如果在组织不希望修改外部 Web 服务发布规则证书的情况下，使用适用于会议的 Office Web Apps 和适用于运行 Lync 的移动设备的自动发现服务，也需要使用此参数。</p></td>
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
<td><p>前端服务器、前端池、导演、控制器池、Office Web Apps for 电话会议</p></td>
<td><p>如果在组织不希望修改外部 web 服务发布规则证书的情况下使用运行 Lync 的移动设备的自动发现服务，则为必需。 发送到反向代理外部接口上的端口80的流量将从反向代理内部接口重定向到端口8080上的池，以便池 Web 服务可以将其与内部 Web 流量区分开。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>内部反向代理接口</p></td>
<td><p>前端服务器、前端池、导演、控制器池、Office Web Apps for 电话会议</p></td>
<td><p>发送到反向代理外部接口上的端口443的流量将从反向代理内部接口重定向到端口4443上的池，以便池 web 服务可以将其与内部 web 流量区分开。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

