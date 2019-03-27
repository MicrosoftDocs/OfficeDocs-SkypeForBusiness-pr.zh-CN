---
title: 管理您的组织的访问边缘配置
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 后部署一个或多个边缘服务器，必须启用外部域或提供程序访问、 远程用户访问和匿名用户通过边缘服务器将用于您的组织支持的会议访问的类型。
ms.openlocfilehash: 8428815a0f3d89124d1b5e681b79924171916f6d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896915"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>管理您的组织的访问边缘配置

后部署一个或多个边缘服务器，必须启用外部域或提供程序访问、 远程用户访问和匿名用户通过边缘服务器将用于您的组织支持的会议访问的类型。

这些选项包括以下类型的可以通过**访问边缘配置**页上配置的访问：

  - **启用联盟和公共 IM 连接**   启用此项如果您想要支持联盟的伙伴域用户访问。 此设置适用于 SIP 联合身份验证配置的全局、 站点或用户范围在**外部访问策略**页上。 对于要应用的联合身份验证设置，您必须两页上配置联盟支持。
    
    两个选项存在的可选设置如何发现联盟的伙伴，以及是否存档免责声明 (向联盟联系人的通知与您通信的部署已启用了存档和通信将存档的详细信息） 将发送给联系人：
    
      - **启用伙伴域发现**   选择此选项允许您可以与联盟的域的自动发现。 Skype 业务服务器使用域名系统 (DNS) 记录尝试发现域未列出在允许的域列表中，自动评估传入流量发现联盟伙伴和限制或阻止基于信任该流量级别，通信和管理员设置的量。 如果您未选择此选项，仅对您在允许的域列表包含的域中的用户启用联盟的用户访问。 是否选择此选项，您可以指定的单个域阻止或允许，包括限制对特定服务器的联盟域中运行访问边缘服务的访问。 有关详细信息，请参阅[支持的允许的外部域的配置](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。
    
      - **向联盟伙伴发送存档免责声明**   选择此选项允许向建议他们 communications 详细信息会记录的联盟伙伴发送存档免责声明消息。 如果与联盟的伙伴域的外部通信存档时，应启用存档放弃通知以提醒伙伴部署要存档其消息和通信的详细信息。 有关存档的详细信息，请参阅[启用或禁用发送存档免责声明向联盟伙伴](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)。

  - **启用远程用户访问**   启用此选项，如果您希望您的组织防火墙，如远程办公和用户在旅行，能够连接到 Skype 业务服务器之外的用户。 有关详细信息，请参阅[启用或禁用远程用户访问](enable-or-disable-remote-user-access.md)。

  - **启用匿名用户访问会议**   启用此选项，如果您希望内部用户可以邀请外部匿名用户加入他们所组织的会议。 启用此设置仅适用于会议允许匿名用户。

> [!NOTE]  
> 除了启用外部用户访问支持，您还配置策略以控制远程用户访问您的组织中使用任何类型的外部用户访问之前对用户可用。 有关创建、 配置和外部用户访问的应用策略的详细信息，请参阅[管理您的组织的外部访问策略](../external-access-policies/manage-external-access-policy-for-your-organization.md)。

**通过使用 Windows PowerShell cmdlet 查看访问边缘配置信息**

  - 使用 Windows PowerShell 和**Get-csaccessedgeconfiguration** cmdlet 可以查看访问边缘配置信息。 从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。 
    
    若要查看有关所有访问边缘配置设置的信息，业务 Server 命令行管理程序 Skype 中键入以下命令，然后按 ENTER:
    
     `Get-CsAccessEdgeConfiguration`
    
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

