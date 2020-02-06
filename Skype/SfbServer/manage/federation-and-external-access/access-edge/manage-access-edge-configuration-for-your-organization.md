---
title: 管理您的组织的访问边缘配置
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 部署一个或多个边缘服务器后，必须通过你的组织支持的边缘服务器启用外部域或提供者访问、远程用户访问和匿名用户访问的类型。
ms.openlocfilehash: 7308d6914f3f6d79cd217a31c0246c6f2d189516
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818343"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>管理您的组织的访问边缘配置

部署一个或多个边缘服务器后，必须通过你的组织支持的边缘服务器启用外部域或提供者访问、远程用户访问和匿名用户访问的类型。

这些选项包括以下可通过 "**访问边缘配置**" 页面配置的访问类型：

  - **启用联盟和公共 IM 连接**   如果你想要支持用户对联盟伙伴域的访问，请启用此连接。 此设置适用于针对**外部访问策略**页面上的全局、网站或用户作用域配置的 SIP 联合。 若要应用联盟设置，必须在两个页面上配置联合身份验证支持。
    
    存在两个选项，这两个选项是有关如何发现联合合作伙伴的可选设置，以及是否存档免责声明（通知你与你的部署已启用存档的联合联系人），并且通信将存档的详细信息）将发送给联系人：
    
      - **启用合作伙伴域发现**   选择此选项可自动发现你可以与其进行联盟的域。 Skype for Business 服务器使用域名系统（DNS）记录来尝试发现未在 "允许的域" 列表中列出的域，自动评估已发现的联盟伙伴的传入通信，并基于信任限制或阻止该流量级别、流量数量和管理员设置。 如果不选择此选项，则仅对在 "允许的域" 列表中包含的域中的用户启用 "联盟用户访问"。 无论是否选择此选项，您都可以指定要阻止或允许的单个域，包括限制对运行联盟域中的访问边缘服务的特定服务器的访问。 有关详细信息，请参阅[配置对允许的外部域的支持](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。
    
      - **将存档免责声明发送给联盟合作伙伴**   选择此选项可将存档免责声明消息发送给联合合作伙伴，建议记录通信详细信息。 如果您将外部通信与联盟伙伴域进行了存档，则应启用存档免责声明通知，以警告合作伙伴其邮件和通信详细信息已被你的部署存档。 有关存档的详细信息，请参阅[启用或禁用向联盟伙伴发送存档免责声明](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)。

  - **启用远程用户访问**   如果你希望你的组织外部的用户（如出差的远程办公和用户）能够连接到 Skype for business 服务器，请启用此选项。 有关详细信息，请参阅[启用或禁用远程用户访问](enable-or-disable-remote-user-access.md)。

  - **允许匿名用户访问会议**   如果希望内部用户邀请外部匿名用户加入他们组织的会议，请启用此选项。 启用此设置仅允许匿名用户进行会议。

> [!NOTE]  
> 除了启用外部用户访问支持外，你还可以配置策略来控制在你的组织中使用远程用户访问，然后再向用户提供任何类型的外部用户访问权限。 有关创建、配置和应用外部用户访问策略的详细信息，请参阅[管理组织的外部访问策略](../external-access-policies/manage-external-access-policy-for-your-organization.md)。

**使用 Windows PowerShell cmdlet 查看访问边缘配置信息**

  - 可以使用 Windows PowerShell 和**CsAccessEdgeConfiguration** cmdlet 查看访问边缘配置信息。 此 cmdlet 既可以从 Skype for Business 服务器管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。 
    
    若要查看有关所有访问边缘配置设置的信息，请在 Skype for Business Server 命令行管理器中键入以下命令，然后按 ENTER：
    
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

