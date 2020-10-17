---
title: 证书摘要-SIP、XMPP 联合身份验证和公共即时消息
description: 证书摘要-SIP、XMPP 联盟和公共即时消息。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49105659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 565d3b935d304aa09588688bd8d71948b1b3ec3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572138"
---
# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Lync Server 2013 中的证书摘要-SIP、XMPP 联合身份验证和公共即时消息

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-03-15_

您需要用于与 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通信服务器进行联盟的证书通常由您配置的证书满足，请求并分配给您的边缘服务器。

启用和建立与可扩展邮件和状态协议 (XMPP) 合作伙伴的通信的证书要求需要添加 XMPP 域的条目。 作为使用者替代名称 (SAN) 包含在证书上的记录将成为可以参与 XMPP 通信的域。 如果要针对整个域启用 XMPP，则该域可以是根级别域（例如，contoso.com），或者如果要针对用户的子集启用 XMPP，该域也可以是选定的子域（例如，corp.contoso.com、finance.contoso.com）。

若要为公用即时消息连接配置证书，请注意，与其他 SIP 联合类型或甚至标准边缘服务器证书没有什么不同，只是在边缘池 (AOL) 需要证书或证书 (在边缘池) 也包含客户端 EKU 的情况下。 客户端 EKU 是对证书的补充，并且是分配给边缘服务器的外部公用证书的一部分。

若要确认您已满足边缘服务器部署的正确证书要求，请查看标题为 " **另请参阅**" 的部分中列出的主题。

<div>



<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>组件</th>
<th>使用者名称</th>
<th>使用者替代名称 (SAN)</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>访问/边缘外部</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>contoso.com</p>



> [!NOTE]
> 支持 contoso.com XMPP 命名空间


<p>sip.fabrikam.com</p>



> [!NOTE]
> 支持 fabrikam.com SIP 命名空间


<p>fabrikam.com</p>



> [!NOTE]
> 支持 fabrikam.com XMPP 命名空间

</td>
<td><p>证书必须来自公共 CA，并且必须具有服务器 EKU 和客户端 EKU （如果要部署具有 AOL 的公共 IM 连接）。 将证书分配给外部边缘服务器接口：</p>
<ul>
<li><p>Access Edge service － 访问边缘服务</p></li>
<li><p>Web 会议边缘服务</p></li>
<li><p>A/V 边缘服务</p></li>
</ul>



> [!NOTE]
> 从技术上讲，证书未分配给 A/V 边缘。 通过媒体中继身份验证服务 (/MRAS) 来管理安全通信和身份验证。 /MRAS 使用分配给边缘服务器内部接口的证书。


<p>请注意，根据拓扑生成器中的定义，SAN 将自动添加到证书中。根据需要为其他 SIP 域和其他需要支持的条目添加 SAN 条目。将在 SAN 中复制使用者名称，并且该名称必须在正确的操作中显示。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的示例 XMPP 配置–与 Google 对话的 XMPP 联盟](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[在 Lync Server 2013 中规划边缘服务器证书](lync-server-2013-plan-for-edge-server-certificates.md)  
[Lync Server 2013 中的证书摘要-使用 NAT 的专用 IP 地址的单一合并边缘](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[Lync Server 2013 中的证书摘要-使用公用 IP 地址的单一合并边缘](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[Lync Server 2013 中的证书摘要-扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[Lync Server 2013 中的证书摘要-扩展的合并边缘（使用公用 IP 地址进行 DNS 负载平衡）](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[Lync Server 2013 中的证书摘要-使用硬件负载平衡器的扩展的合并边缘](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

