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
localization_priority: Normal
description: 部署一个或多个边缘服务器后, 必须通过你的组织支持的边缘服务器启用外部域或提供者访问、远程用户访问和匿名用户访问的类型。
ms.openlocfilehash: b79560d2cb0e570ab2b4fcf061a5b91c6a74a8bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280192"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a><span data-ttu-id="41b30-103">管理您的组织的访问边缘配置</span><span class="sxs-lookup"><span data-stu-id="41b30-103">Manage Access Edge Configuration for your organization</span></span>

<span data-ttu-id="41b30-104">部署一个或多个边缘服务器后, 必须通过你的组织支持的边缘服务器启用外部域或提供者访问、远程用户访问和匿名用户访问的类型。</span><span class="sxs-lookup"><span data-stu-id="41b30-104">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="41b30-105">这些选项包括以下可通过 "**访问边缘配置**" 页面配置的访问类型:</span><span class="sxs-lookup"><span data-stu-id="41b30-105">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="41b30-106">**启用联盟和公共 IM 连接**   如果你想要支持用户对联盟伙伴域的访问, 请启用此连接。</span><span class="sxs-lookup"><span data-stu-id="41b30-106">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="41b30-107">此设置适用于针对**外部访问策略**页面上的全局、网站或用户作用域配置的 SIP 联合。</span><span class="sxs-lookup"><span data-stu-id="41b30-107">This setting applies to SIP federation configured for global, site, or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="41b30-108">若要应用联盟设置, 必须在两个页面上配置联合身份验证支持。</span><span class="sxs-lookup"><span data-stu-id="41b30-108">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="41b30-109">存在两个选项, 这两个选项是有关如何发现联合合作伙伴的可选设置, 以及是否存档免责声明 (通知你与你的部署已启用存档的联合联系人), 并且通信将存档的详细信息) 将发送给联系人:</span><span class="sxs-lookup"><span data-stu-id="41b30-109">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts:</span></span>
    
      - <span data-ttu-id="41b30-110">**启用合作伙伴域发现**   选择此选项可自动发现你可以与其进行联盟的域。</span><span class="sxs-lookup"><span data-stu-id="41b30-110">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="41b30-111">Skype for Business 服务器使用域名系统 (DNS) 记录来尝试发现未在 "允许的域" 列表中列出的域, 自动评估已发现的联盟伙伴的传入通信, 并基于信任限制或阻止该流量级别、流量数量和管理员设置。</span><span class="sxs-lookup"><span data-stu-id="41b30-111">Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="41b30-112">如果不选择此选项, 则仅对在 "允许的域" 列表中包含的域中的用户启用 "联盟用户访问"。</span><span class="sxs-lookup"><span data-stu-id="41b30-112">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="41b30-113">无论是否选择此选项, 您都可以指定要阻止或允许的单个域, 包括限制对运行联盟域中的访问边缘服务的特定服务器的访问。</span><span class="sxs-lookup"><span data-stu-id="41b30-113">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="41b30-114">有关详细信息, 请参阅[配置对允许的外部域的支持](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="41b30-114">For details, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>
    
      - <span data-ttu-id="41b30-115">**将存档免责声明发送给联盟合作伙伴**   选择此选项可将存档免责声明消息发送给联合合作伙伴, 建议记录通信详细信息。</span><span class="sxs-lookup"><span data-stu-id="41b30-115">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="41b30-116">如果您将外部通信与联盟伙伴域进行了存档, 则应启用存档免责声明通知, 以警告合作伙伴其邮件和通信详细信息已被你的部署存档。</span><span class="sxs-lookup"><span data-stu-id="41b30-116">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="41b30-117">有关存档的详细信息, 请参阅[启用或禁用向联盟伙伴发送存档免责声明](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)。</span><span class="sxs-lookup"><span data-stu-id="41b30-117">For details on archiving, see [Enable or disable sending an Archiving disclaimer to federated partner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

  - <span data-ttu-id="41b30-118">**启用远程用户访问**   如果你希望你的组织外部的用户 (如出差的远程办公和用户) 能够连接到 Skype for business 服务器, 请启用此选项。</span><span class="sxs-lookup"><span data-stu-id="41b30-118">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server.</span></span> <span data-ttu-id="41b30-119">有关详细信息, 请参阅[启用或禁用远程用户访问](enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="41b30-119">For details, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="41b30-120">**允许匿名用户访问会议**   如果希望内部用户邀请外部匿名用户加入他们组织的会议, 请启用此选项。</span><span class="sxs-lookup"><span data-stu-id="41b30-120">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="41b30-121">启用此设置仅允许匿名用户进行会议。</span><span class="sxs-lookup"><span data-stu-id="41b30-121">Enabling this setting only allows anonymous users for conferences.</span></span>

> [!NOTE]  
> <span data-ttu-id="41b30-122">除了启用外部用户访问支持外, 你还可以配置策略来控制在你的组织中使用远程用户访问, 然后再向用户提供任何类型的外部用户访问权限。</span><span class="sxs-lookup"><span data-stu-id="41b30-122">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="41b30-123">有关创建、配置和应用外部用户访问策略的详细信息, 请参阅[管理组织的外部访问策略](../external-access-policies/manage-external-access-policy-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="41b30-123">For details about creating, configuring, and applying policies for external user access, see [Manage external access policy for your organization](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span></span>

<span data-ttu-id="41b30-124">**使用 Windows PowerShell cmdlet 查看访问边缘配置信息**</span><span class="sxs-lookup"><span data-stu-id="41b30-124">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="41b30-125">可以使用 Windows PowerShell 和**CsAccessEdgeConfiguration** cmdlet 查看访问边缘配置信息。</span><span class="sxs-lookup"><span data-stu-id="41b30-125">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="41b30-126">此 cmdlet 既可以从 Skype for Business 服务器管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="41b30-126">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="41b30-127">若要查看有关所有访问边缘配置设置的信息, 请在 Skype for Business Server 命令行管理器中键入以下命令, 然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="41b30-127">To view information about all your Access Edge configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
     `Get-CsAccessEdgeConfiguration`
    
    <span data-ttu-id="41b30-128">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="41b30-128">That will return information similar to this:</span></span>
    
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

