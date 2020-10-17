---
title: DNS 摘要-可扩展消息传递和状态协议 (XMPP) 联盟
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
ms.openlocfilehash: 7ac2e44382aa75b61ae4e2966b5ef87fd977e798
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532129"
---
# <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 摘要-可扩展消息和状态协议 (XMPP) 联盟

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-04-08_

若要在部署中配置可扩展消息和状态协议 (XMPP) ，请创建两个域名系统 (DNS) 中的记录，该外部 DNS 服务器会将这些记录解析为您的边缘服务器或边缘池的访问边缘服务。

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a>可扩展消息传递和状态协议的 DNS 摘要


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
<th>映射位置/注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/SRV/5269</p></td>
<td><p>_xmpp server._tcp .com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>访问边缘服务或边缘池上的 XMPP 代理外部接口。对于所有内部 SIP 域，请根据需要对启用了 XMPP 联系人的用户通过外部策略、用户所在的网站策略或应用到启用 Lync 的用户的用户策略的配置来使用。 还必须在 XMPP 联盟伙伴策略中配置允许的 XMPP 域。 有关其他详细信息，请参阅 <strong>另请参阅</strong> 主题中的主题</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>xmpp.contoso.com（举例）</p></td>
<td><p>边缘服务器或边缘池托管 XMPP 代理上的访问边缘服务的 IP 地址</p></td>
<td><p>指向承载 XMPP 代理服务的访问边缘服务或边缘池。 一般而言，您创建的 SRV 记录将指向此主机（A 或 AAAA）记录</p></td>
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

