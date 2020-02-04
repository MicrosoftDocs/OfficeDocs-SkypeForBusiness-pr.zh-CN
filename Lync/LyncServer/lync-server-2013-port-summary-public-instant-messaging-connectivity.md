---
title: Lync Server 2013：端口摘要-公共即时消息连接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Public instant messaging connectivity
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49105663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16430849221631d9b540f5ee51b0a07758a38b05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725052"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a>端口摘要-Lync Server 2013 中的公共即时消息连接

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-16_

若要为支持公共即时消息连接所需的端口和协议配置防火墙，请首先注意 SIP/MTLS/TCP 5061 是双向的，以确保公共 IM 提供商联系 Lync 客户端的能力或 Lync 联系公共 IM 联系人。

Windows Live Messenger 可参与 Lync 客户端的音频/视频通信。 此帐户适用于通常在防火墙上支持 Lync 客户端作为外部用户的防火墙端口和协议配置。

<div>


> [!IMPORTANT]  
> Lync 比以往更多，是一种强大的工具，用于跨组织和全球各地的人员进行连接。 与 Windows Live Messenger 的联盟要求除 Lync 标准客户端访问许可证（CAL）之外没有其他用户/设备许可证。 Skype 联盟将添加到此列表，使 Lync 用户可以通过 IM 和语音与成百上千人联系。<BR>与 Messenger 客户联系人的联盟将于2013年3月15日（中国大陆除外）正式结束。 Skype 将成为以前使用 Messenger 的联盟用户的联合身份验证客户端。



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
<td><p>Access/SIP （MTLS）/TCP/5061</p></td>
<td><p>公共 IM 连接合作伙伴</p></td>
<td><p>Edge 服务器访问接口</p></td>
<td><p>对于使用 SIP 的联盟和公共 IM 连接。</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP （MTLS）/TCP/5061</p></td>
<td><p>Edge 服务器访问接口</p></td>
<td><p>公共 IM 连接合作伙伴</p></td>
<td><p>对于使用 SIP 的联盟和公共 IM 连接。</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP （TLS）/TCP/443</p></td>
<td><p>客户端</p></td>
<td><p>Edge 服务器访问接口</p></td>
<td><p>外部用户访问的客户端到服务器 SIP 通信。</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>Edge 服务器访问接口</p></td>
<td><p>实时 Messenger 客户端</p></td>
<td><p>如果配置了公用 IM 连接，则用于带有 Windows Live Messenger 的 A/V 会话。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>Edge 服务器访问接口</p></td>
<td><p>实时 Messenger 客户端</p></td>
<td><p>对于具有 Windows Live Messenger 的公共 IM 连接，则是必需的。</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>实时 Messenger 客户端</p></td>
<td><p>Edge 服务器访问接口</p></td>
<td><p>对于具有 Windows Live Messenger 的公共 IM 连接，则是必需的。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)  
[确定 Lync Server 2013 的外部 A/V 防火墙和端口要求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

