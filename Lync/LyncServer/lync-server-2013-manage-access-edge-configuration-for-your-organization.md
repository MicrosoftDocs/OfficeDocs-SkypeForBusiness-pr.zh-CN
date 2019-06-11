---
title: Lync Server 2013：管理您的组织的访问边缘配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage Access Edge Configuration for your organization
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05d2bcca7836bd451b2535fb02c350facd7fc1bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a>在 Lync Server 2013 中管理您的组织的访问边缘配置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

本文档是预备文档，可能随时更改。 空白主题均以占位符的形式包含在内。

部署一个或多个边缘服务器后, 必须通过你的组织支持的边缘服务器启用外部域或提供者访问、远程用户访问和匿名用户访问的类型。

这些选项包括以下可通过 "**访问边缘配置**" 页面配置的访问类型:

  - **启用联盟和公共 IM 连接**   如果你想要支持用户对联盟伙伴域的访问, 请启用此连接。 此设置适用于针对**外部访问策略**页面上的全局、网站或用户作用域配置的 SIP 联合身份验证和 XMPP 联合身份验证。 若要应用联盟设置, 必须在两个页面上配置联合身份验证支持。
    
    存在两个选项, 这两个选项是有关如何发现联合合作伙伴的可选设置, 以及是否存档免责声明 (通知你与你的部署已启用存档的联合联系人), 并且通信将存档的详细信息) 将发送给联系人
    
      - **启用合作伙伴域发现**   选择此选项可自动发现你可以与其进行联盟的域。 Lync Server 2013 使用域名系统 (DNS) 记录来尝试发现未在 "允许的域" 列表中列出的域、自动评估已发现的联盟伙伴的传入流量并基于信任级别限制或阻止该流量。通讯量和管理员设置。 如果不选择此选项, 则仅对在 "允许的域" 列表中包含的域中的用户启用 "联盟用户访问"。 无论是否选择此选项, 您都可以指定要阻止或允许的单个域, 包括限制对运行联盟域中的访问边缘服务的特定服务器的访问。 有关详细信息, 请参阅[在 Lync Server 2013 中配置对允许的外部域的支持](lync-server-2013-configure-support-for-allowed-external-domains.md)。
    
      - **将存档免责声明发送给联盟合作伙伴**   选择此选项可将存档免责声明消息发送给联合合作伙伴, 建议记录通信详细信息。 如果您将外部通信与联盟伙伴域进行了存档, 则应启用存档免责声明通知, 以警告合作伙伴其邮件和通信详细信息已被你的部署存档。 有关存档的详细信息, 请参阅[在 Lync Server 2013 中定义存档要求](lync-server-2013-defining-your-requirements-for-archiving.md)。

  - **启用远程用户访问**   如果你希望你的组织中的用户 (如正在旅行的远程办公和用户) 能够连接到 Lync 服务器, 请启用此选项。 有关详细信息, 请参阅[在 Lync Server 2013 中启用或禁用远程用户访问](lync-server-2013-enable-or-disable-remote-user-access.md)。

  - **允许匿名用户访问会议**   如果希望内部用户邀请外部匿名用户加入他们组织的会议, 请启用此选项。 启用此设置仅允许匿名用户进行会议。 若要配置会议体验和选项以定义用户如何使用会议以及如何包含匿名用户, 请参阅为[网站或用户](https://technet.microsoft.com/en-us/library/gg429715\(v=ocs.15\))[创建或修改会议用户体验中的详细信息。Lync Server 2013 的会议策略设置参考](lync-server-2013-conferencing-policy-settings-reference.md)。

<div>


> [!NOTE]  
> 除了启用外部用户访问支持外, 你还可以配置策略来控制在你的组织中使用远程用户访问, 然后再向用户提供任何类型的外部用户访问权限。 有关创建、配置和应用外部用户访问策略的详细信息, 请参阅<A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">在 Lync Server 2013 中管理外部访问策略</A>。



</div>

**使用 Windows PowerShell cmdlet 查看访问边缘配置信息**

  - 可以使用 Windows PowerShell 和**CsAccessEdgeConfiguration** cmdlet 查看访问边缘配置信息。 此 cmdlet 既可以从 Lync Server 2013 管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。
    
    若要查看有关所有访问边缘配置设置的信息, 请在 Lync Server 命令行管理程序中键入以下命令, 然后按 ENTER:
    
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

## <a name="in-this-section"></a>本节内容

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

