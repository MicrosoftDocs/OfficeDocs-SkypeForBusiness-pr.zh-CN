---
title: 证书摘要-SIP、XMPP 联盟和公共即时消息
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
ms.openlocfilehash: 0fc3b7a1745d045954fb06403dbb3359fb699a29
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730212"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>证书摘要-Lync Server 2013 中的 SIP、XMPP 联盟和公共即时消息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-03-15_

您所需要的用于与 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通信服务器进行联盟的证书通常由您配置、请求和分配给 Edge 服务器的证书满足。

启用和建立与可扩展消息和状态协议（XMPP）合作伙伴的通信的证书要求需要为 XMPP 域添加条目。 作为主题备用名称（SAN）包含在证书上的记录将是可参与 XMPP 通信的域。 如果你想要为整个域启用 XMPP，或者可以选择子域（例如 corp.contoso.com，finance.contoso.com），则域可以是根级别的域（例如 contoso.com），如果要为用户的子集启用 XMPP，也可以选择 "子域" （例如、）。

若要配置公共即时消息连接的证书，请注意，与其他 SIP 联合类型或即使是标准边缘服务器证书没有什么不同，不同之处在于美国 Online （AOL）需要证书或证书（在边缘池的大小写）还包含客户端 EKU。 客户端 EKU 是证书的补充，并且是分配给 Edge 服务器的外部公共证书的一部分。

若要确认你已满足 Edge 服务器部署的正确证书要求，请查看标题为 "**另请参阅**" 的部分中列出的主题。

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
<th>主题名称</th>
<th>主题备用名称（SAN）</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部/访问边缘</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>contoso.com</p>



> [!NOTE]
> 若要支持 contoso.com XMPP 命名空间


<p>sip.fabrikam.com</p>



> [!NOTE]
> 支持 fabrikam.com SIP 命名空间


<p>fabrikam.com</p>



> [!NOTE]
> 若要支持 fabrikam.com XMPP 命名空间

</td>
<td><p>证书必须来自公共 CA，并且必须具有服务器 EKU 和客户端 EKU，前提是要部署与 AOL 的公共 IM 连接。 证书已分配给以下对象的外部边缘服务器接口：</p>
<ul>
<li><p>访问边缘服务</p></li>
<li><p>Web 会议边缘服务</p></li>
<li><p>A/V 边缘服务</p></li>
</ul>



> [!NOTE]
> 从技术上讲，证书未分配给 A/V 边缘。 安全通信和身份验证通过媒体中继身份验证服务（MRAS）进行管理。 MRAS 使用分配给 Edge 服务器内部接口的证书。


<p>请注意，San 会根据拓扑生成器中的定义自动添加到证书。 根据需要为其他 SIP 域和其他需要支持的条目添加 SAN 条目。 主题名称是在 SAN 中复制的，并且必须存在才能正确操作。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的示例 XMPP 配置 –  与 Google Talk 的 XMPP 联盟](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[在 Lync Server 2013 中规划边缘服务器证书](lync-server-2013-plan-for-edge-server-certificates.md)  
[Lync Server 2013 中的证书摘要 - 单一合并边缘（使用 NAT 通过专用 IP 地址进行）](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[Lync Server 2013 中的证书摘要 - 使用公用 IP 地址的单一合并边缘](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[Lync Server 2013 中的证书摘要 - 扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[Lync Server 2013 中的证书摘要 - 扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[Lync Server 2013 中的证书摘要 - 使用硬件负载平衡器的扩展的合并边缘](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

