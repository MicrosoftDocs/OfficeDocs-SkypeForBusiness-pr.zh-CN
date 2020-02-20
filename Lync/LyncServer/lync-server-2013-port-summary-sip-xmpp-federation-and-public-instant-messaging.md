---
title: 端口摘要-SIP、XMPP 联合身份验证和公共即时消息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - SIP, XMPP federation, and public instant messaging
ms:assetid: ab05bdd6-e9b0-4b1b-9dd9-29ab88e8befe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618373(v=OCS.15)
ms:contentKeyID: 49105660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7135624695d1e4be6337f723bc69c47ff6fc706d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Lync Server 2013 中的端口摘要-SIP、XMPP 联合身份验证和公共即时消息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-03-15_

与 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通信服务器的联合身份验证的端口、协议和防火墙要求与部署的边缘服务器类似。 客户端通过 TLS/SIP/TCP 443 启动与访问边缘服务的通信。 但是，联盟伙伴将启动与 MTLS/SIP/TCP 5061 的访问边缘服务的通信。

若要将防火墙配置为支持公用即时消息连接所需的端口和协议，请首先注意 SIP/MTLS/TCP 5061 是双向的，以确保公共 IM 提供商中的联系人能够联系 Lync 客户端，或与 Lync 联系以联系公共 IM 联系人。

Windows Live Messenger 可以参与与 Lync 客户端的音频/视频通信。 此帐户适用于通常在防火墙上支持作为外部用户的 Lync 客户端的防火墙端口和协议配置。

<div>


> [!IMPORTANT]
> Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。 与 Windows Live Messenger 的联盟不需要其他用户/设备许可证，而不能超过 Lync Standard Client Access 许可证（CAL）。 Skype 联合身份验证将添加到此列表中，使 Lync 用户可以使用即时消息和语音访问成百上千人。<BR>与 Messenger 客户联系人的联盟将于2013年3月15日正式结束（中国大陆除外）。 Skype 将成为以前使用 Messenger 的联盟用户的联合身份验证客户端。



</div>

为在边缘服务器上部署的可扩展消息和状态协议（XMPP）代理定义的端口和协议允许从 XMPP 联合合作伙伴到边缘服务器的通信，还允许从边缘服务器到 XMPP 的通信。联盟伙伴。 在面向内部的防火墙上定义的规则也是从前端服务器或前端池到边缘服务器或边缘池。

<div>

## <a name="firewall-summary---sip-federation"></a>防火墙摘要-SIP 联合


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
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Access/SIP （MTLS）/TCP/5061</p></td>
<td><p>访问边缘服务公用 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>对于使用 SIP 的联盟和公共 IM 连接</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>防火墙摘要 – 公共即时消息连接


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
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Access/SIP （MTLS）/TCP/5061</p></td>
<td><p>公共 IM 连接合作伙伴</p></td>
<td><p>边缘服务器访问接口</p></td>
<td><p>用于使用 SIP 的联盟和公共 IM 连接。</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP （MTLS）/TCP/5061</p></td>
<td><p>边缘服务器访问接口</p></td>
<td><p>公共 IM 连接合作伙伴</p></td>
<td><p>用于使用 SIP 的联盟和公共 IM 连接。</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP （TLS）/TCP/443</p></td>
<td><p>客户端</p></td>
<td><p>边缘服务器访问接口</p></td>
<td><p>用于外部用户访问的客户端到服务器 SIP 流量。</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>边缘服务器访问接口</p></td>
<td><p>Live Messenger 客户端</p></td>
<td><p>用于与 Windows Live Messenger 的 A/V 会话，前提是配置了公共 IM 连接。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>边缘服务器访问接口</p></td>
<td><p>Live Messenger 客户端</p></td>
<td><p>对于使用 Windows Live Messenger 的公共 IM 连接是必需的。</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>Live Messenger 客户端</p></td>
<td><p>边缘服务器访问接口</p></td>
<td><p>对于使用 Windows Live Messenger 的公共 IM 连接是必需的。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a>防火墙摘要-可扩展消息传递和状态协议（XMPP）


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
<th>注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>任意</p></td>
<td><p>访问边缘服务接口 IP 地址</p></td>
<td><p>用于 XMPP 的标准服务器到服务器通信端口。 允许与来自联合 XMPP 合作伙伴的边缘服务器 XMPP 代理的通信</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>访问边缘服务接口 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>用于 XMPP 的标准服务器到服务器通信端口。 允许从边缘服务器 XMPP 代理到联合 XMPP 合作伙伴的通信</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>任意</p></td>
<td><p>内部边缘服务器接口 IP</p></td>
<td><p>从前端服务器或前端池上的 XMPP 网关到边缘服务器的内部 XMPP 流量</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)  
[确定 Lync Server 2013 的外部 A/V 防火墙和端口要求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[在 Lync Server 2013 中管理 XMPP 联盟伙伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

