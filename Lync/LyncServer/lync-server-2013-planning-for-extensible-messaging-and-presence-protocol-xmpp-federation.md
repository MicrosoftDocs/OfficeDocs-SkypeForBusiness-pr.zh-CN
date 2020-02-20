---
title: 规划可扩展消息传递和状态协议（XMPP）联盟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for extensible messaging and presence protocol (XMPP) federation
ms:assetid: 952b33e2-1f58-4831-9a39-1dfec2a316ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205107(v=OCS.15)
ms:contentKeyID: 48184892
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8421c8fc7568aae9c7e7cedc0cad9ea0c503140
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>在 Lync Server 2013 中规划可扩展消息和状态协议（XMPP）联盟

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-22_

早期版本的 Lync Server 和 Office 通信服务器提供了可扩展消息和状态协议（XMPP）网关，可将其作为单独的服务器角色进行部署，以允许与 XMPP 部署进行联盟。 在 Microsoft Lync Server 2013 中，可以将 XMPP 功能部署为功能。 XMPP 功能安装在两个部分中：在边缘服务器上运行的 XMPP 代理，以及在前端服务器上运行的 XMPP 网关。

在[Lync Server 2013 中部署外部用户访问权限](lync-server-2013-deploying-external-user-access.md)中介绍了 XMPP 的部署和配置。通过在防火墙上定义端口和协议规则、配置证书以及添加 DNS 记录，在您计划支持组织中的 XMPP。 本节中的以下主题汇总了为您的部署成功规划 XMPP 联合所需的信息。

<div>


> [!IMPORTANT]
> Microsoft 对 Lync Server 2013 的 XMPP 功能进行了测试，并支持 Microsoft 实现与 Google 谈话的即时消息联盟。 对于任何其他 XMPP 系统，请联系第三方供应商以验证它们是否支持与 Lync Server 2013 联合，以及任何部署或疑难解答建议。



</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [Lync Server 2013 中的证书摘要-可扩展消息传递和状态协议（XMPP）联盟](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [Lync Server 2013 中的端口摘要-可扩展消息传递和状态协议（XMPP）联盟](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [Lync Server 2013 中的 DNS 摘要-可扩展消息传递和状态协议（XMPP）联盟](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中设置 XMPP 联盟](lync-server-2013-setting-up-xmpp-federation.md)  
[在 Lync Server 2013 中配置策略以控制 XMPP 联盟用户访问](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  


[在 Lync Server 2013 中管理 XMPP 联盟伙伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Set-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))  
[CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))  
[CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

