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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199918"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a><span data-ttu-id="6d63f-103">管理您的组织的访问边缘配置</span><span class="sxs-lookup"><span data-stu-id="6d63f-103">Manage Access Edge Configuration for your organization</span></span>

<span data-ttu-id="6d63f-104">后部署一个或多个边缘服务器，必须启用外部域或提供程序访问、 远程用户访问和匿名用户通过边缘服务器将用于您的组织支持的会议访问的类型。</span><span class="sxs-lookup"><span data-stu-id="6d63f-104">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="6d63f-105">这些选项包括以下类型的可以通过**访问边缘配置**页上配置的访问：</span><span class="sxs-lookup"><span data-stu-id="6d63f-105">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="6d63f-106">**启用联盟和公共 IM 连接**   启用此项如果您想要支持联盟的伙伴域用户访问。</span><span class="sxs-lookup"><span data-stu-id="6d63f-106">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="6d63f-107">此设置适用于 SIP 联合身份验证配置的全局、 站点或用户范围在**外部访问策略**页上。</span><span class="sxs-lookup"><span data-stu-id="6d63f-107">This setting applies to SIP federation configured for global, site, or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="6d63f-108">对于要应用的联合身份验证设置，您必须两页上配置联盟支持。</span><span class="sxs-lookup"><span data-stu-id="6d63f-108">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="6d63f-109">两个选项存在的可选设置如何发现联盟的伙伴，以及是否存档免责声明 (向联盟联系人的通知与您通信的部署已启用了存档和通信将存档的详细信息） 将发送给联系人：</span><span class="sxs-lookup"><span data-stu-id="6d63f-109">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts:</span></span>
    
      - <span data-ttu-id="6d63f-110">**启用伙伴域发现**   选择此选项允许您可以与联盟的域的自动发现。</span><span class="sxs-lookup"><span data-stu-id="6d63f-110">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="6d63f-111">Skype 业务服务器使用域名系统 (DNS) 记录尝试发现域未列出在允许的域列表中，自动评估传入流量发现联盟伙伴和限制或阻止基于信任该流量级别，通信和管理员设置的量。</span><span class="sxs-lookup"><span data-stu-id="6d63f-111">Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="6d63f-112">如果您未选择此选项，仅对您在允许的域列表包含的域中的用户启用联盟的用户访问。</span><span class="sxs-lookup"><span data-stu-id="6d63f-112">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="6d63f-113">是否选择此选项，您可以指定的单个域阻止或允许，包括限制对特定服务器的联盟域中运行访问边缘服务的访问。</span><span class="sxs-lookup"><span data-stu-id="6d63f-113">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="6d63f-114">有关详细信息，请参阅[支持的允许的外部域的配置](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="6d63f-114">For details, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>
    
      - <span data-ttu-id="6d63f-115">**向联盟伙伴发送存档免责声明**   选择此选项允许向建议他们 communications 详细信息会记录的联盟伙伴发送存档免责声明消息。</span><span class="sxs-lookup"><span data-stu-id="6d63f-115">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="6d63f-116">如果与联盟的伙伴域的外部通信存档时，应启用存档放弃通知以提醒伙伴部署要存档其消息和通信的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6d63f-116">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="6d63f-117">有关存档的详细信息，请参阅[启用或禁用发送存档免责声明向联盟伙伴](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)。</span><span class="sxs-lookup"><span data-stu-id="6d63f-117">For details on archiving, see [Enable or disable sending an Archiving disclaimer to federated partner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

  - <span data-ttu-id="6d63f-118">**启用远程用户访问**   启用此选项，如果您希望您的组织防火墙，如远程办公和用户在旅行，能够连接到 Skype 业务服务器之外的用户。</span><span class="sxs-lookup"><span data-stu-id="6d63f-118">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server.</span></span> <span data-ttu-id="6d63f-119">有关详细信息，请参阅[启用或禁用远程用户访问](enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="6d63f-119">For details, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="6d63f-120">**启用匿名用户访问会议**   启用此选项，如果您希望内部用户可以邀请外部匿名用户加入他们所组织的会议。</span><span class="sxs-lookup"><span data-stu-id="6d63f-120">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="6d63f-121">启用此设置仅适用于会议允许匿名用户。</span><span class="sxs-lookup"><span data-stu-id="6d63f-121">Enabling this setting only allows anonymous users for conferences.</span></span>

> [!NOTE]  
> <span data-ttu-id="6d63f-122">除了启用外部用户访问支持，您还配置策略以控制远程用户访问您的组织中使用任何类型的外部用户访问之前对用户可用。</span><span class="sxs-lookup"><span data-stu-id="6d63f-122">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="6d63f-123">有关创建、 配置和外部用户访问的应用策略的详细信息，请参阅[管理您的组织的外部访问策略](../external-access-policies/manage-external-access-policy-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="6d63f-123">For details about creating, configuring, and applying policies for external user access, see [Manage external access policy for your organization](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span></span>

<span data-ttu-id="6d63f-124">**通过使用 Windows PowerShell cmdlet 查看访问边缘配置信息**</span><span class="sxs-lookup"><span data-stu-id="6d63f-124">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="6d63f-125">使用 Windows PowerShell 和**Get-csaccessedgeconfiguration** cmdlet 可以查看访问边缘配置信息。</span><span class="sxs-lookup"><span data-stu-id="6d63f-125">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="6d63f-126">从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6d63f-126">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="6d63f-127">若要查看有关所有访问边缘配置设置的信息，业务 Server 命令行管理程序 Skype 中键入以下命令，然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="6d63f-127">To view information about all your Access Edge configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
     `Get-CsAccessEdgeConfiguration`
    
    <span data-ttu-id="6d63f-128">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="6d63f-128">That will return information similar to this:</span></span>
    
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

