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
# <a name="manage-access-edge-configuration-for-your-organization"></a><span data-ttu-id="ac39d-103">管理你的组织的访问边缘配置</span><span class="sxs-lookup"><span data-stu-id="ac39d-103">Manage Access Edge Configuration for your organization</span></span>

<span data-ttu-id="ac39d-104">部署一个或多个边缘服务器后，必须通过组织支持的边缘服务器启用外部域或提供程序访问、远程用户访问和匿名用户访问会议的类型。</span><span class="sxs-lookup"><span data-stu-id="ac39d-104">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="ac39d-105">这些选项包括以下访问类型，可通过“访问边缘配置”页面进行配置：</span><span class="sxs-lookup"><span data-stu-id="ac39d-105">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="ac39d-106">**启用联盟和公共 IM 连接**   如果要支持用户访问联盟伙伴域，则启用此功能。</span><span class="sxs-lookup"><span data-stu-id="ac39d-106">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="ac39d-107">此设置适用于在"外部访问策略"页上为全局、站点或用户范围配置的 SIP **联盟。**</span><span class="sxs-lookup"><span data-stu-id="ac39d-107">This setting applies to SIP federation configured for global, site, or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="ac39d-108">若要应用联盟设置，必须在两个页面上配置联合身份验证支持。</span><span class="sxs-lookup"><span data-stu-id="ac39d-108">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="ac39d-109">存在两个选项，即如何发现联盟伙伴的可选设置，以及是否将存档免责声明 (通知发送给您通信的联盟联系人，告知您的部署已启用存档，通信详细信息将存档) 将发送给联系人：</span><span class="sxs-lookup"><span data-stu-id="ac39d-109">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts:</span></span>
    
      - <span data-ttu-id="ac39d-110">**启用合作伙伴域发现**   选择此选项可启用可以联盟的域的自动发现。</span><span class="sxs-lookup"><span data-stu-id="ac39d-110">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="ac39d-111">Skype for Business Server 使用域名系统 (DNS) 记录尝试发现未在允许域列表中列出的域，自动评估发现的联盟伙伴的传入流量，并基于信任级别、流量和管理员设置限制或阻止该流量。</span><span class="sxs-lookup"><span data-stu-id="ac39d-111">Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="ac39d-112">如果不选择此选项，则仅对包括在允许域列表上的域中的用户启用联盟用户访问。</span><span class="sxs-lookup"><span data-stu-id="ac39d-112">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="ac39d-113">无论你是否选择此选项，都可以指定要阻止或允许的单个域，包括限制对在联盟域中运行访问边缘服务的特定服务器的访问。</span><span class="sxs-lookup"><span data-stu-id="ac39d-113">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="ac39d-114">有关详细信息，请参阅 [配置对允许的外部域的支持](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="ac39d-114">For details, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>
    
      - <span data-ttu-id="ac39d-115">**向联盟伙伴发送存档免责声明**   选择此选项后，即可向联盟伙伴发送存档免责声明消息，告知他们记录通信详细信息。</span><span class="sxs-lookup"><span data-stu-id="ac39d-115">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="ac39d-116">如果存档与联盟伙伴域的外部通信，应启用存档免责声明通知，以警告合作伙伴您的部署正在存档其邮件和通信详细信息。</span><span class="sxs-lookup"><span data-stu-id="ac39d-116">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="ac39d-117">有关存档的详细信息，请参阅"启用[或禁用向联盟伙伴发送存档免责声明"。](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)</span><span class="sxs-lookup"><span data-stu-id="ac39d-117">For details on archiving, see [Enable or disable sending an Archiving disclaimer to federated partner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

  - <span data-ttu-id="ac39d-118">**启用远程用户访问**   如果希望组织中位于防火墙之外的用户（如远程办公者和出差的用户）能够连接到 Skype for Business Server，请启用此选项。</span><span class="sxs-lookup"><span data-stu-id="ac39d-118">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server.</span></span> <span data-ttu-id="ac39d-119">有关详细信息，请参阅 [启用或禁用远程用户访问](enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="ac39d-119">For details, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="ac39d-120">**允许匿名用户访问会议**   如果希望内部用户邀请外部匿名用户参加他们组织的会议，请启用此选项。</span><span class="sxs-lookup"><span data-stu-id="ac39d-120">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="ac39d-121">启用此设置仅允许匿名用户参加会议。</span><span class="sxs-lookup"><span data-stu-id="ac39d-121">Enabling this setting only allows anonymous users for conferences.</span></span>

> [!NOTE]  
> <span data-ttu-id="ac39d-122">除了启用外部用户访问支持，您还可以配置策略，在用户不能使用任何外部用户访问类型时，控制组织内远程用户访问的使用。</span><span class="sxs-lookup"><span data-stu-id="ac39d-122">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="ac39d-123">有关为外部用户访问创建、配置和应用策略的详细信息，请参阅"管理[组织的外部访问策略"。](../external-access-policies/manage-external-access-policy-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="ac39d-123">For details about creating, configuring, and applying policies for external user access, see [Manage external access policy for your organization](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span></span>

<span data-ttu-id="ac39d-124">**使用 cmdlet 查看访问边缘Windows PowerShell信息**</span><span class="sxs-lookup"><span data-stu-id="ac39d-124">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="ac39d-125">可通过使用 Windows PowerShell **和 Get-CsAccessEdgeConfiguration** cmdlet 查看访问边缘配置信息。</span><span class="sxs-lookup"><span data-stu-id="ac39d-125">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="ac39d-126">此 cmdlet 可以从 Skype for Business Server 命令行管理程序运行，也可以从远程会话Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="ac39d-126">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="ac39d-127">若要查看有关所有访问边缘配置设置的信息，请在 Skype for Business Server 命令行管理程序 中键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="ac39d-127">To view information about all your Access Edge configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
     `Get-CsAccessEdgeConfiguration`
    
    <span data-ttu-id="ac39d-128">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="ac39d-128">That will return information similar to this:</span></span>
    
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

