---
title: DNS 摘要-SIP、XMPP 联盟和公共即时消息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49105656
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c22b38fdb9e936df8b3fd148022acdbd857cdcfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>DNS 摘要-Lync Server 2013 中的 SIP、XMPP 联盟和公共即时消息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2017-03-09_

定义与 Office 通信服务器或 Lync Server 合作伙伴联盟所需的域名系统 (DNS) 记录由你决定允许其他视角合作伙伴自动 DNS 发现你的域。 如果发布\_sipfederationtls。\_tcp。 * \<SIP 域名\> *SRV 记录, 任何其他 SIP 联盟域都将能够 "发现" 您的联盟。 你可以通过使用 Lync Server 控制面板中的 "允许域和阻止域" 设置来控制哪些联盟域可以与你进行通信, 或者通过使用 Lync Server 命令行**管理程序设置允许或阻止的域配置获取**、**设置**、**新建**、**删除 CsAllowedDomain**和 **-CsBlockedDomain** PowerShell cmdlet。 有关如何配置这些设置以及如何使用 PowerShell cmdlet 的其他信息, 请参阅本主题末尾的**相关主题**。

"DNS 记录" 摘要表描述了开放的或可发现的联盟的必需条目。 如果您不想实现联合发现, 则可以决定不配置\_sipfederationtls。\_tcp。 *SIP 域名\> \<*

<div>


> [!IMPORTANT]
> 在某些特定情况下, 您必须拥有 _sipfederationtls _tcp。 <EM> &lt;SIP 域名&gt; </EM>SRV 记录, 但不希望具有可发现的联合。 其中一个实例是为用户部署移动性的位置。 移动推送通知 clearinghouse (PNCH) 是一种特殊类型的联盟, 用于 Apple iPhone 或 iPad 上使用 lync 2010 移动客户端或使用 lync 2013 2010 移动客户端或 Windows Phone 的 Microsoft Lync 移动客户端。 _Sipfederationtls。 _tcp。 <EM> &lt;SIP 域名&gt; </EM>SRV 记录在移动性和推送通知的情况下使用。 若要缓解此问题并控制你的发现, 请清除 "<STRONG>启用合作伙伴域发现</STRONG>" 设置以关闭发现。



</div>

若要为你的部署配置可扩展消息和状态协议 (XMPP), 请在外部 DNS 服务器中创建两个域名系统 (DNS) 记录, 该服务器会将记录解析为 Edge 服务器或边缘池的访问边缘服务。

为公共即时消息连接配置域名系统 (DNS) 时, 你将发现支持外部用户的配置将支持公用 IM 连接。 如果你已配置了 Edge 服务器或边缘池, 则应具有支持公用 IM 连接所必需的 DNS 记录。

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a>DNS 摘要-SIP 联盟, 包括公共即时消息连接


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
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Access Edge 服务外部接口, 需要将联合身份验证自动 DNS 发现到其他潜在的联合合作伙伴, 并称为 "允许的 SIP 域" (在以前版本中称为增强联盟)。根据需要对启用了 Lync 的用户的所有 SIP 域重复此操作</p>



> [!IMPORTANT]
> 移动和推送通知交换所需要此 SRV 记录。 在有多个 SIP 域的情况下, 为将具有 Lync 移动客户端的每个域创建和发布 SRV 记录。 如果部署支持的每个 SIP 域没有明确的 SRV 记录, 则推送通知服务和 Apple 推送通知服务可能不会按预期运行。

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a>DNS 摘要-可扩展消息和状态协议 (XMPP)


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
<td><p>"访问边缘服务" 或 "边缘池" 上的 XMPP 代理外部接口。对于启用了 Lync 的用户, 通过全局策略、用户所在的网站策略或应用了用户策略的用户策略, 可对所有内部 SIP 域进行必要的操作, 并允许使用启用了 Lync 的用户使用 XMPP 联系人。启用 Lync 的用户。 还必须在 XMPP 联盟合作伙伴策略中配置允许的 XMPP 域。 有关其他详细信息, 请参阅<strong>另请参阅</strong>中的主题</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>xmpp.contoso.com (例如)</p></td>
<td><p>边缘服务器上的访问边缘服务的 IP 地址或托管 XMPP 代理的边缘池的 IP 地址</p></td>
<td><p>指向托管 XMPP 代理服务的访问边缘服务或边缘池。 通常, 你创建的 SRV 记录将指向此主机 (A 或 AAAA) 记录</p></td>
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

