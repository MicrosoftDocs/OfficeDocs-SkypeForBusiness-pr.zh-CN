---
title: Lync Server 2013：管理您的组织的访问边缘配置
TOCTitle: 管理您的组织的访问边缘配置
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ552443(v=OCS.15)
ms:contentKeyID: 49311802
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中管理您的组织的访问边缘配置

 

_**上一次修改主题：** 2012-11-01_

本文档是预备文档，可能随时更改。空白主题均以占位符的形式包含在内。

部署一个或多个 边缘服务器后，必须通过您的组织将支持的 边缘服务器启用对会议的以下访问类型：外部域或提供商访问、远程用户访问和匿名用户访问。

这些选项包括以下访问类型，可通过“访问边缘配置”页面进行配置：

  - **启用联盟和公共 IM 连接**    如果您要支持用户对联盟伙伴域的访问，则启用此选项。此设置适用于在“外部访问策略”页上为全局、站点或用户范围配置的 SIP 联盟和 XMPP 联盟。要应用联盟设置，必须同时在两个页面上配置联盟支持。
    
    有两个可选选项可用来设置如何发现联盟合作伙伴，以及是否向联系人发送存档免责声明（通知与您通信的联盟联系人，您的部署已启用存档，通信详细信息将会存档）
    
      - **启用合作伙伴域发现**    选择此选项可以自动发现您可以与之联盟的域。 Lync Server 2013 使用域名系统 (DNS) 记录来尝试发现不在允许的域列表中的域，从而自动评估来自已发现的联盟合作伙伴的传入通信，以及基于信任级别、通信量和管理员设置限制或阻止通信。如果不选择此选项，将只对允许的域列表上包含的域中的用户启用联盟用户访问。不论是否选择此选项，都可以指定是阻止还是允许个别域，包括限制访问联盟域中运行访问边缘服务的特定服务器。有关详细信息，请参阅 [在 Lync Server 2013 中配置对允许的外部域的支持](lync-server-2013-configure-support-for-allowed-external-domains.md).
    
      - **向联盟合作伙伴发送存档免责声明**    选择此选项将允许向联盟合作伙伴发送存档免责声明消息，以告知他们通信详细信息将被记录。如果存档与联盟合作伙伴域的外部通信，则应启用存档免责声明通知，以提醒合作伙伴其消息和通信详细信息将被您的部署存档。有关存档的详细信息，请参阅 [在 Lync Server 2013 中定义组织的存档要求](lync-server-2013-defining-your-requirements-for-archiving.md)。

  - **启用远程用户访问**    如果希望您的组织中位于防火墙之外的用户（如远程办公人员和在出差的用户）能够连接到 Lync Server，请启用此选项。有关详细信息，请参阅 [在 Lync Server 2013 中启用或禁用远程用户访问](lync-server-2013-enable-or-disable-remote-user-access.md)。

  - **允许匿名用户访问会议**    如果您希望内部用户邀请外部匿名用户访问他们组织的会议，则启用此选项。启用此设置只允许匿名用户访问会议。要配置会议体验和定义您的用户如何配置和如何利用会议的选项，以及如何加入匿名用户等，请参阅 [创建或修改站点或用户组的会议用户体验](https://technet.microsoft.com/zh-cn/library/gg429715\(v=ocs.15\))和 [在 Lync Server 2013 中会议策略设置参考](lync-server-2013-conferencing-policy-settings-reference.md)中的详细信息。

> [!NOTE]  
> 除了启用外部用户访问支持，您还可以配置策略，在用户不能使用任何外部用户访问类型时，控制组织内远程用户访问的使用。有关为外部用户访问创建、配置和应用策略的详细信息，请参阅 <a href="lync-server-2013-manage-external-access-policy-for-your-organization.md">在 Lync Server 2013 中管理组织的外部访问策略</a>。



**使用 Windows PowerShell Cmdlet 查看访问边缘配置信息**

  - 可以使用 Windows PowerShell 和 **Get-CsAccessEdgeConfiguration** cmdlet 查看访问边缘配置信息。可从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。
    
    要查看有关您的所有访问边缘配置设置的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 Enter：
    
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

## 本部分内容

  - [在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [在 Lync Server 2013 中启用或禁用联盟伙伴发现](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [在 Lync Server 2013 中启用或禁用向联盟伙伴发送存档免责声明](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [在 Lync Server 2013 中启用或禁用远程用户访问](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [在 Lync Server 2013 中启用或禁用匿名用户访问](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [在 Lync Server 2013 中分配会议策略以支持匿名用户](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

