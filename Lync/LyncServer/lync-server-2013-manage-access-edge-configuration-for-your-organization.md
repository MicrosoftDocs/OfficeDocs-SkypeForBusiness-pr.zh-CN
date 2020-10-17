---
title: Lync Server 2013：管理您的组织的访问边缘配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Access Edge Configuration for your organization
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c62e5b03057f09d7489a413456e432e8e08799b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534543"
---
# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a>在 Lync Server 2013 中管理您的组织的访问边缘配置

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

这是初步文档，可能会发生变更。 空白主题作为占位符包含在内。

部署一个或多个边缘服务器后，必须通过将受组织支持的边缘服务器启用外部域或提供者访问的类型、远程用户访问和匿名用户访问会议。

这些选项包括以下访问类型，可通过“访问边缘配置”**** 页面进行配置：

  - **启用联盟和公共 IM 连接**    如果要支持用户对联盟伙伴域的访问权限，请启用此。 此设置适用于为 **外部访问策略** 页上的全局、站点或用户作用域配置的 SIP 联合身份验证和 XMPP 联合身份验证。 对于要应用的联盟设置，必须在这两个页面上配置联合支持。
    
    有两个可选选项可用来设置如何发现联盟合作伙伴，以及是否向联系人发送存档免责声明（通知与您通信的联盟联系人，您的部署已启用存档，通信详细信息将会存档）
    
      - **启用合作伙伴域发现**    选择此选项将启用可与之联合的域的自动发现。 Lync Server 2013 使用域名系统 (DNS) 记录来尝试发现未在 "允许的域" 列表中列出的域，并自动评估已发现的联盟伙伴的传入流量，并根据信任级别、流量量和管理员设置来限制或阻止该流量。 如果未选择此选项，则仅对您在允许的域列表中包含的域中的用户启用联合用户访问权限。 无论您是否选择此选项，您都可以指定要阻止或允许的单个域，包括限制对在联合域中运行访问边缘服务的特定服务器的访问。 有关详细信息，请参阅 [在 Lync Server 2013 中配置对允许的外部域的支持](lync-server-2013-configure-support-for-allowed-external-domains.md)。
    
      - 向**联盟伙伴**     发送存档免责声明如果选择此选项，则会向联合合作伙伴发送存档免责声明消息，建议将通信详细信息记录下来。 如果您存档与联盟伙伴域的外部通信，则应启用存档免责声明通知，以警告合作伙伴其邮件和通信详细信息正在由您的部署存档。 有关存档的详细信息，请参阅 [在 Lync Server 2013 中定义存档要求](lync-server-2013-defining-your-requirements-for-archiving.md)。

  - **启用远程用户访问**    如果您希望组织中的用户（如正在旅行的远程办公和用户）能够连接到 Lync Server，请启用此选项。 有关详细信息，请参阅 [在 Lync Server 2013 中启用或禁用远程用户访问](lync-server-2013-enable-or-disable-remote-user-access.md)。

  - **允许匿名用户访问会议**    如果希望内部用户邀请外部匿名用户加入他们组织的会议，请启用此选项。 如果启用此设置，则仅允许匿名用户参加会议。 若要配置会议体验和选项，以定义您的用户如何以及用户如何使用会议以及如何包含匿名用户，请参阅 [创建或修改会议用户体验中的网站或用户](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) 和 [会议策略设置引用的 Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)的详细信息。

<div>


> [!NOTE]  
> 除了启用外部用户访问支持，您还可以配置策略，在用户不能使用任何外部用户访问类型时，控制组织内远程用户访问的使用。 有关创建、配置和应用外部用户访问策略的详细信息，请参阅 <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">在 Lync Server 2013 中管理外部访问策略</A>。



</div>

**使用 Windows PowerShell cmdlet 查看访问边缘配置信息**

  - 可以使用 Windows PowerShell 和 **set-csaccessedgeconfiguration** cmdlet 查看访问边缘配置信息。 此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。
    
    若要查看有关所有访问边缘配置设置的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：
    
        Get-CsAccessEdgeConfiguration
    
    这将返回与以下类似的信息：
    
        Identity                               : Global
        AllowAnonymousUsers                    : False
        AllowFederatedUsers                    : False
        AllowOutsideUsers                      : True
        BeClearingHouse                        : False
        EnablePartnerDiscovery                 : False
        EnableArchivingDisclaimer              : False
        EnableUserReplicator                   : True
        KeepCrlsUpToDateForPeers               : True
        MarkSourceVerifiableOnOutgoingMessages : True
        OutgoingTlsCountForFederatedPartners   : 4
        DiscoveredPartnerStandardRate          : 20
        EnableDiscoveredPartnerContactsLimit   : True
        MaxContactsPerDiscoveredPartner        : 1000
        DiscoveredPartnerReportPeriodMinutes   : 60
        MaxAcceptedCertificatesStored          : 1000
        MaxRejectedCertificatesStored          : 500
        CertificatesDeletedPercentage          : 20
        RoutingMethod                          : UseDnsSrvRouting

<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [在 Lync Server 2013 中启用或禁用联盟伙伴发现](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [在 Lync Server 2013 中启用或禁用向联盟伙伴发送存档免责声明](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [在 Lync Server 2013 中启用或禁用远程用户访问](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [在 Lync Server 2013 中启用或禁用匿名用户访问](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [在 Lync Server 2013 中分配会议策略以支持匿名用户](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

