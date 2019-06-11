---
title: 端口摘要-SIP、XMPP 联盟和公共即时消息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - SIP, XMPP federation, and public instant messaging
ms:assetid: ab05bdd6-e9b0-4b1b-9dd9-29ab88e8befe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618373(v=OCS.15)
ms:contentKeyID: 49105660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2edcad9806c5e6c8714f3face301211633a53fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>端口摘要-Lync Server 2013 中的 SIP、XMPP 联盟和公共即时消息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-03-15_

与 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通信服务器的联盟的端口、协议和防火墙要求与已部署的边缘服务器的身份验证要求类似。 客户通过 TLS/SIP/TCP 443 上的访问边缘服务发起通信。 但是, 联盟伙伴将通过 MTLS/SIP/TCP 5061 发起与访问边缘服务的通信。

若要为支持公共即时消息连接所需的端口和协议配置防火墙, 请首先注意 SIP/MTLS/TCP 5061 是双向的, 以确保公共 IM 提供商联系 Lync 客户端的能力, 或将 Lync 的联系人联系公共 IM 联系人。

Windows Live Messenger 可参与 Lync 客户端的音频/视频通信。 此帐户适用于通常在防火墙上支持 Lync 客户端作为外部用户的防火墙端口和协议配置。

<div>


> [!IMPORTANT]
> Lync 比以往更多, 是一种强大的工具, 用于跨组织和全球各地的人员进行连接。 与 Windows Live Messenger 的联盟要求除 Lync 标准客户端访问许可证 (CAL) 之外没有其他用户/设备许可证。 Skype 联盟将添加到此列表, 使 Lync 用户可以通过 IM 和语音与成百上千人联系。<BR>与 Messenger 客户联系人的联盟将于2013年3月15日 (中国大陆除外) 正式结束。 Skype 将成为以前使用 Messenger 的联盟用户的联合身份验证客户端。



</div>

为在 Edge 服务器上部署的可扩展消息和状态协议 (XMPP) 代理定义的端口和协议允许从 XMPP 联盟合作伙伴到边缘服务器的通信, 还允许从边缘服务器到 XMPP 的通信。联盟合作伙伴。 规则还在面向内部的防火墙上定义, 从前端服务器或前端池到边缘服务器或边缘池。

<div>

## <a name="firewall-summary---sip-federation"></a>防火墙摘要-SIP 联盟


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
<td><p>Access/SIP (MTLS)/TCP/5061</p></td>
<td><p>Access Edge 服务公共 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>对于使用 SIP 的联盟和公共 IM 连接</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>防火墙摘要-公共即时消息连接


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
<td><p>Access/SIP (MTLS)/TCP/5061</p></td>
<td><p>公共 IM 连接合作伙伴</p></td>
<td><p>Edge 服务器访问接口</p></td>
<td><p>对于使用 SIP 的联盟和公共 IM 连接。</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP (MTLS)/TCP/5061</p></td>
<td><p>Edge 服务器访问接口</p></td>
<td><p>公共 IM 连接合作伙伴</p></td>
<td><p>对于使用 SIP 的联盟和公共 IM 连接。</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (TLS)/TCP/443</p></td>
<td><p>客户端</p></td>
<td><p>Edge 服务器访问接口</p></td>
<td><p>外部用户访问的客户端到服务器 SIP 通信。</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>Edge 服务器访问接口</p></td>
<td><p>实时 Messenger 客户端</p></td>
<td><p>如果配置了公用 IM 连接, 则用于带有 Windows Live Messenger 的 A/V 会话。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>Edge 服务器访问接口</p></td>
<td><p>实时 Messenger 客户端</p></td>
<td><p>对于具有 Windows Live Messenger 的公共 IM 连接, 则是必需的。</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>实时 Messenger 客户端</p></td>
<td><p>Edge 服务器访问接口</p></td>
<td><p>对于具有 Windows Live Messenger 的公共 IM 连接, 则是必需的。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a>防火墙摘要-可扩展消息和状态协议 (XMPP)


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
<th>源 (IP 地址)</th>
<th>目标 (IP 地址)</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>任意</p></td>
<td><p>Access Edge 服务接口 IP 地址</p></td>
<td><p>适用于 XMPP 的标准服务器到服务器通信端口。 允许与联盟 XMPP 合作伙伴的 Edge 服务器 XMPP 代理通信</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Access Edge 服务接口 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>适用于 XMPP 的标准服务器到服务器通信端口。 允许从 Edge 服务器 XMPP 代理到联合 XMPP 合作伙伴的通信</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>任意</p></td>
<td><p>内部边缘服务器接口 IP</p></td>
<td><p>从前端服务器或前端池中的 XMPP 网关到边缘服务器的内部 XMPP 流量</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)  
[确定 Lync Server 2013 的外部 A/V 防火墙和端口要求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[在 Lync Server 2013 中管理组织的 XMPP 联盟伙伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

