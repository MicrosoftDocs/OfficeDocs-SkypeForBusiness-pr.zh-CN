---
title: DNS 摘要-SIP、XMPP 联合身份验证和公共即时消息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49105656
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8c7b36448f2aa8eb895aebeeaddc6187c1831ca
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501189"
---
# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 摘要-SIP、XMPP 联合身份验证和公共即时消息

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2017-03-09_

域名系统 (DNS) 在使用 Office 通信服务器或 Lync Server 合作伙伴定义联合身份验证时所需的记录取决于允许其他视角合作伙伴自动 DNS 发现您的域的决定。 如果发布 \_ sipfederationtls。 \_rdp-tcp. *\<SIP domain name\>* SRV 记录，任何其他 SIP 联盟域都将能够 "发现" 你的联盟。 您可以通过使用 Lync Server 控制面板中的 "允许域和阻止域" 设置，或者通过使用 Lync Server 命令行管理程序和 **Get**、 **Set**、 **New**、 **CsAllowedDomain** 和 **-CsBlockedDomain** PowerShell cmdlet 来控制哪些联盟域可以与您通信。 有关如何配置这些设置以及如何使用 PowerShell cmdlet 的其他信息，请参阅本主题结尾的**相关主题**。

DNS 记录摘要表描述开放或可发现联盟所需要的条目。 如果您不想实现联合发现，则可以决定不配置 \_ sipfederationtls。 \_rdp-tcp. *\<SIP domain name\>* 记录.

<div>


> [!IMPORTANT]
> 在某些特定情况下，您必须具有 _sipfederationtls._tcp. <EM> &lt; SIP 域名 &gt; </EM> SRV 记录，但不希望具有可检测到的联合身份验证。 其中一种情况是，您已经为用户部署了移动性。 移动推送通知 clearinghouse (PNCH) 是一种特殊类型的联盟，用于 Apple iPhone 或 iPad 上使用 lync 2010 移动客户端或使用 lync 2010 移动客户端或 Windows Phone 的 Microsoft Lync Mobile 客户端或 Lync 2013 移动客户端。 如果同时部署了移动性和 PNCH，则需要使用 _sipfederationtls._tcp. <EM> &lt; SIP 域名 &gt; </EM> SRV 记录在移动性和推送通知的情况下使用。 若要缓解此问题并控制可发现性，请清除设置“启用合作伙伴域发现”<STRONG></STRONG>以关闭发现功能。



</div>

若要在部署中配置可扩展消息和状态协议 (XMPP) ，请创建两个域名系统 (DNS) 中的记录，该外部 DNS 服务器会将这些记录解析为您的边缘服务器或边缘池的访问边缘服务。

为公共即时消息连接配置域名系统 (DNS) 时，将会发现支持外部用户的配置将支持公用 IM 连接。 如果已配置了边缘服务器或边缘池，则应具有支持公用 IM 连接所必需的 DNS 记录。

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a>DNS 摘要-SIP 联盟，包括公共即时消息连接


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
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls _sipfederationtls._tcp .com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>访问边缘服务外部接口需要向其他潜在联合合作伙伴的联合进行自动 DNS 发现，并且称为 "允许的 SIP 域" (在以前版本中称为 "增强联盟") 。根据需要对启用了 Lync 的用户的所有 SIP 域重复此操作</p>



> [!IMPORTANT]
> 移动性和推送通知交换所需要此 SRV 记录。 在有多个 SIP 域的情况下，为将拥有 Lync 移动客户端的每个域创建并发布一个 SRV 记录。 如果部署支持的每个 SIP 域没有明确的 SRV 记录，则推送通知服务和 Apple 推送通知服务可能无法按预期运行。

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a>DNS 摘要-可扩展消息传递和状态协议 (XMPP) 


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
[在 Lync Server 2013 中配置推送通知](lync-server-2013-configuring-for-push-notifications.md)  
[在 Lync Server 2013 中启用或禁用联盟伙伴发现](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)  
[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)  


[在 Lync Server 2013 中管理组织的 SIP 联盟域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

