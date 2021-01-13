---
title: 管理你的组织的访问边缘配置
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 部署一个或多个边缘服务器后，必须通过组织支持的边缘服务器启用外部域或提供程序访问、远程用户访问和匿名用户访问会议的类型。
ms.openlocfilehash: 63d33a5dd3459aef5f657d8ab5772515a16e7915
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817332"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>管理你的组织的访问边缘配置

部署一个或多个边缘服务器后，必须通过组织支持的边缘服务器启用外部域或提供程序访问、远程用户访问和匿名用户访问会议的类型。

这些选项包括以下访问类型，可通过“访问边缘配置”页面进行配置：

  - **启用联盟和公共 IM 连接**   如果要支持用户访问联盟伙伴域，则启用此功能。 此设置适用于在"外部访问策略"页上为全局、站点或用户范围配置的 SIP **联盟。** 若要应用联盟设置，必须在两个页面上配置联合身份验证支持。
    
    存在两个选项，即如何发现联盟伙伴的可选设置，以及是否将存档免责声明 (通知发送给您通信的联盟联系人，告知您的部署已启用存档，通信详细信息将存档) 将发送给联系人：
    
      - **启用合作伙伴域发现**   选择此选项可启用可以联盟的域的自动发现。 Skype for Business Server 使用域名系统 (DNS) 记录尝试发现未在允许域列表中列出的域，自动评估发现的联盟伙伴的传入流量，并基于信任级别、流量和管理员设置限制或阻止该流量。 如果不选择此选项，则仅对包括在允许域列表上的域中的用户启用联盟用户访问。 无论你是否选择此选项，都可以指定要阻止或允许的单个域，包括限制对在联盟域中运行访问边缘服务的特定服务器的访问。 有关详细信息，请参阅 [配置对允许的外部域的支持](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。
    
      - **向联盟伙伴发送存档免责声明**   选择此选项后，即可向联盟伙伴发送存档免责声明消息，告知他们记录通信详细信息。 如果存档与联盟伙伴域的外部通信，应启用存档免责声明通知，以警告合作伙伴您的部署正在存档其邮件和通信详细信息。 有关存档的详细信息，请参阅"启用[或禁用向联盟伙伴发送存档免责声明"。](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - **启用远程用户访问**   如果希望组织中位于防火墙之外的用户（如远程办公者和出差的用户）能够连接到 Skype for Business Server，请启用此选项。 有关详细信息，请参阅 [启用或禁用远程用户访问](enable-or-disable-remote-user-access.md)。

  - **允许匿名用户访问会议**   如果希望内部用户邀请外部匿名用户参加他们组织的会议，请启用此选项。 启用此设置仅允许匿名用户参加会议。

> [!NOTE]  
> 除了启用外部用户访问支持，您还可以配置策略，在用户不能使用任何外部用户访问类型时，控制组织内远程用户访问的使用。 有关为外部用户访问创建、配置和应用策略的详细信息，请参阅"管理[组织的外部访问策略"。](../external-access-policies/manage-external-access-policy-for-your-organization.md)

**使用 cmdlet 查看访问边缘Windows PowerShell信息**

  - 可通过使用 Windows PowerShell **和 Get-CsAccessEdgeConfiguration** cmdlet 查看访问边缘配置信息。 此 cmdlet 可以从 Skype for Business Server 命令行管理程序运行，也可以从远程会话Windows PowerShell。 
    
    若要查看有关所有访问边缘配置设置的信息，请在 Skype for Business Server 命令行管理程序 中键入以下命令，然后按 Enter：
    
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

