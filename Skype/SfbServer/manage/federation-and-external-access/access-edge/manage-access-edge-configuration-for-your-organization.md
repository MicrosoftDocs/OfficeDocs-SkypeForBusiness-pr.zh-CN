---
title: 管理你的组织的访问边缘配置
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 部署一个或多个边缘服务器后，必须通过组织支持的 Edge Server 启用外部域或提供程序访问、远程用户访问和匿名用户对会议的访问。
ms.openlocfilehash: 228d3c2975d403422795244dafebc0138e385d89
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674594"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>管理你的组织的访问边缘配置

部署一个或多个边缘服务器后，必须通过组织支持的 Edge Server 启用外部域或提供程序访问、远程用户访问和匿名用户对会议的访问。

这些选项包括以下访问类型，可通过“访问边缘配置”页面进行配置：

  - **启用联合身份验证和公共 IM 连接**   如果想要支持用户访问联合合作伙伴域，请启用此功能。 此设置适用于为 **外部访问** 策略页上的全局、站点或用户范围配置的 SIP 联合身份验证。 若要应用联合身份验证设置，必须在这两个页面上配置联合身份验证支持。
    
    存在两个选项，这些选项是有关如何发现联合伙伴的可选设置，以及是否将免责声明存档 (通知到你与之通信的联合联系人，并且部署已启用存档，并且通信详细信息将存档) 将发送给联系人：
    
      - **启用合作伙伴域发现**   选择此选项可自动发现可以联合使用的域。 Skype for Business Server使用域名系统 (DNS) 记录来尝试发现允许的域列表中未列出的域，自动评估来自发现的联合伙伴的传入流量，并根据信任级别、流量量和管理员设置限制或阻止该流量。 如果未选择此选项，则仅对允许域列表中包含的域中的用户启用联合用户访问权限。 无论是否选择此选项，都可以指定要阻止或允许的单个域，包括限制对在联合域中运行 Access Edge 服务的特定服务器的访问。 有关详细信息，请参阅 [配置对允许的外部域的支持](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。
    
      - **向联合合作伙伴发送存档免责声明**   选择此选项可向联合合作伙伴发送存档免责声明消息，告知他们通信详细信息已记录。 如果存档与联合合作伙伴域的外部通信，则应启用存档免责声明通知，以警告合作伙伴其消息和通信详细信息正在由部署存档。 有关存档的详细信息，请参阅 [启用或禁用向联合合作伙伴发送存档免责声明](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)。

  - **启用远程用户访问**  如果希望组织中防火墙外部的用户（例如远程通勤者和正在旅行的用户）能够连接到Skype for Business Server，请启用此选项。 有关详细信息，请参阅[“启用”或“禁用远程用户访问”。](enable-or-disable-remote-user-access.md)

  - **允许匿名用户访问会议**   如果希望内部用户邀请外部匿名用户参加他们组织的会议，请启用此选项。 启用此设置仅允许匿名用户参加会议。

> [!NOTE]  
> 除了启用外部用户访问支持，您还可以配置策略，在用户不能使用任何外部用户访问类型时，控制组织内远程用户访问的使用。 有关为外部用户访问创建、配置和应用策略的详细信息，请参阅 [管理组织的外部访问策略](../external-access-policies/manage-external-access-policy-for-your-organization.md)。

**使用 Windows PowerShell cmdlet 查看 Access Edge 配置信息**

  - 可以使用 Windows PowerShell 和 **Get-CsAccessEdgeConfiguration** cmdlet 查看 Access Edge 配置信息。 此 cmdlet 可以从 Skype for Business Server Management Shell 运行，也可以从远程Windows PowerShell会话运行。 
    
    若要查看有关所有 Access Edge 配置设置的信息，请在 Skype for Business Server Management Shell 中键入以下命令，然后按 Enter：
    
     `Get-CsAccessEdgeConfiguration`
    
    这将返回与以下类似的信息：
    
    标识：全局<br/>
    AllowAnonymousUsers： False<br/>
    AllowFederatedUsers： False<br/>
    AllowOutsideUsers： True<br/>
    BeClearingHouse： False<br/>
    EnablePartnerDiscovery： False<br/>
    EnableArchivingDisclaimer： False<br/>
    EnableUserReplicator： True<br/>
    KeepCrlsUpToDateForPeers： True<br/>
    MarkSourceVerifiableOnOutgoingMessages ： True<br/>
    OutgoingTlsCountForFederatedPartners ： 4<br/>
    DiscoveredPartnerStandardRate ： 20<br/>
    EnableDiscoveredPartnerContactsLimit： True<br/>
    MaxContactsPerDiscoveredPartner： 1000<br/>
    DiscoveredPartnerReportPeriodMinutes： 60<br/>
    MaxAcceptedCertificatesStored： 1000<br/>
    MaxRejectedCertificatesStored： 500<br/>
    CertificatesDeletedPercentage： 20<br/>
    RoutingMethod： UseDnsSrvRouting<br/>

