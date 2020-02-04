---
title: DNS 摘要-可扩展消息传递和状态协议（XMPP）联合身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 0f720a2a-8ab5-43cc-882a-ab595ed3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618368(v=OCS.15)
ms:contentKeyID: 49105655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 941996ea1167cf9baeee05567a00c71ea5ed4baa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 摘要-可扩展消息和状态协议（XMPP）联合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-04-08_

若要为你的部署配置可扩展消息和状态协议（XMPP），请在外部 DNS 服务器中创建两个域名系统（DNS）记录，该服务器会将记录解析为 Edge 服务器或边缘池的访问边缘服务。

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a>可扩展消息和状态协议的 DNS 摘要


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>位置/类型/端口</th>
<th>FQDN</th>
<th>IP 地址/FQDN 主机记录</th>
<th>映射到/批注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/SRV/5269</p></td>
<td><p>_xmpp-server._tcp.contoso.com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>"访问边缘服务" 或 "边缘池" 上的 XMPP 代理外部接口。对于启用了 Lync 的用户，通过全局策略、用户所在的网站策略或应用了用户策略的用户策略，可对所有内部 SIP 域进行必要的操作，并允许使用启用了 Lync 的用户使用 XMPP 联系人。启用 Lync 的用户。 还必须在 XMPP 联盟合作伙伴策略中配置允许的 XMPP 域。 有关其他详细信息，请参阅<strong>另请参阅</strong>中的主题</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>xmpp.contoso.com （例如）</p></td>
<td><p>边缘服务器上的访问边缘服务的 IP 地址或托管 XMPP 代理的边缘池的 IP 地址</p></td>
<td><p>指向托管 XMPP 代理服务的访问边缘服务或边缘池。 通常，你创建的 SRV 记录将指向此主机（A 或 AAAA）记录</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中设置 XMPP 联盟](lync-server-2013-setting-up-xmpp-federation.md)  


[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

