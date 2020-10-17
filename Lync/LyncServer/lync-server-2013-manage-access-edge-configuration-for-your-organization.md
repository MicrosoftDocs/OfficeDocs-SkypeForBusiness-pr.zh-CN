---
title: Lync Server 2013：管理您的组织的访问边缘配置
description: Lync Server 2013：管理您的组织的访问边缘配置。
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
ms.openlocfilehash: 2161385f9c03f025bcf6f5e599b7e0276f6d592c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550638"
---
# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a><span data-ttu-id="e4a42-103">在 Lync Server 2013 中管理您的组织的访问边缘配置</span><span class="sxs-lookup"><span data-stu-id="e4a42-103">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4a42-104">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e4a42-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e4a42-105">这是初步文档，可能会发生变更。</span><span class="sxs-lookup"><span data-stu-id="e4a42-105">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="e4a42-106">空白主题作为占位符包含在内。</span><span class="sxs-lookup"><span data-stu-id="e4a42-106">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="e4a42-107">部署一个或多个边缘服务器后，必须通过将受组织支持的边缘服务器启用外部域或提供者访问的类型、远程用户访问和匿名用户访问会议。</span><span class="sxs-lookup"><span data-stu-id="e4a42-107">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="e4a42-108">这些选项包括以下访问类型，可通过“访问边缘配置”\*\*\*\* 页面进行配置：</span><span class="sxs-lookup"><span data-stu-id="e4a42-108">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="e4a42-109">**启用联盟和公共 IM 连接**    如果要支持用户对联盟伙伴域的访问权限，请启用此。</span><span class="sxs-lookup"><span data-stu-id="e4a42-109">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="e4a42-110">此设置适用于为 **外部访问策略** 页上的全局、站点或用户作用域配置的 SIP 联合身份验证和 XMPP 联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="e4a42-110">This setting applies to both SIP federation and XMPP federation that are configured for global, site or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="e4a42-111">对于要应用的联盟设置，必须在这两个页面上配置联合支持。</span><span class="sxs-lookup"><span data-stu-id="e4a42-111">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="e4a42-112">有两个可选选项可用来设置如何发现联盟合作伙伴，以及是否向联系人发送存档免责声明（通知与您通信的联盟联系人，您的部署已启用存档，通信详细信息将会存档）</span><span class="sxs-lookup"><span data-stu-id="e4a42-112">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts</span></span>
    
      - <span data-ttu-id="e4a42-113">**启用合作伙伴域发现**    选择此选项将启用可与之联合的域的自动发现。</span><span class="sxs-lookup"><span data-stu-id="e4a42-113">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="e4a42-114">Lync Server 2013 使用域名系统 (DNS) 记录来尝试发现未在 "允许的域" 列表中列出的域，并自动评估已发现的联盟伙伴的传入流量，并根据信任级别、流量量和管理员设置来限制或阻止该流量。</span><span class="sxs-lookup"><span data-stu-id="e4a42-114">Lync Server 2013 uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="e4a42-115">如果未选择此选项，则仅对您在允许的域列表中包含的域中的用户启用联合用户访问权限。</span><span class="sxs-lookup"><span data-stu-id="e4a42-115">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="e4a42-116">无论您是否选择此选项，您都可以指定要阻止或允许的单个域，包括限制对在联合域中运行访问边缘服务的特定服务器的访问。</span><span class="sxs-lookup"><span data-stu-id="e4a42-116">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="e4a42-117">有关详细信息，请参阅 [在 Lync Server 2013 中配置对允许的外部域的支持](lync-server-2013-configure-support-for-allowed-external-domains.md)。</span><span class="sxs-lookup"><span data-stu-id="e4a42-117">For details, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>
    
      - <span data-ttu-id="e4a42-118">向**联盟伙伴**     发送存档免责声明如果选择此选项，则会向联合合作伙伴发送存档免责声明消息，建议将通信详细信息记录下来。</span><span class="sxs-lookup"><span data-stu-id="e4a42-118">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="e4a42-119">如果您存档与联盟伙伴域的外部通信，则应启用存档免责声明通知，以警告合作伙伴其邮件和通信详细信息正在由您的部署存档。</span><span class="sxs-lookup"><span data-stu-id="e4a42-119">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="e4a42-120">有关存档的详细信息，请参阅 [在 Lync Server 2013 中定义存档要求](lync-server-2013-defining-your-requirements-for-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="e4a42-120">For details on archiving, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).</span></span>

  - <span data-ttu-id="e4a42-121">**启用远程用户访问**    如果您希望组织中的用户（如正在旅行的远程办公和用户）能够连接到 Lync Server，请启用此选项。</span><span class="sxs-lookup"><span data-stu-id="e4a42-121">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server.</span></span> <span data-ttu-id="e4a42-122">有关详细信息，请参阅 [在 Lync Server 2013 中启用或禁用远程用户访问](lync-server-2013-enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="e4a42-122">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="e4a42-123">**允许匿名用户访问会议**    如果希望内部用户邀请外部匿名用户加入他们组织的会议，请启用此选项。</span><span class="sxs-lookup"><span data-stu-id="e4a42-123">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="e4a42-124">如果启用此设置，则仅允许匿名用户参加会议。</span><span class="sxs-lookup"><span data-stu-id="e4a42-124">Enabling this setting only allows anonymous users for conferences.</span></span> <span data-ttu-id="e4a42-125">若要配置会议体验和选项，以定义您的用户如何以及用户如何使用会议以及如何包含匿名用户，请参阅 [创建或修改会议用户体验中的网站或用户](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) 和 [会议策略设置引用的 Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e4a42-125">To configure the conferencing experience and options that will define how and what your users can do with conferences and for the inclusion of anonymous users, see details at [Create or Modify Conferencing User Experience for a Site or Users](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) and [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e4a42-126">除了启用外部用户访问支持，您还可以配置策略，在用户不能使用任何外部用户访问类型时，控制组织内远程用户访问的使用。</span><span class="sxs-lookup"><span data-stu-id="e4a42-126">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="e4a42-127">有关创建、配置和应用外部用户访问策略的详细信息，请参阅 <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">在 Lync Server 2013 中管理外部访问策略</A>。</span><span class="sxs-lookup"><span data-stu-id="e4a42-127">For details about creating, configuring, and applying policies for external user access, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="e4a42-128">**使用 Windows PowerShell cmdlet 查看访问边缘配置信息**</span><span class="sxs-lookup"><span data-stu-id="e4a42-128">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="e4a42-129">可以使用 Windows PowerShell 和 **set-csaccessedgeconfiguration** cmdlet 查看访问边缘配置信息。</span><span class="sxs-lookup"><span data-stu-id="e4a42-129">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="e4a42-130">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="e4a42-130">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e4a42-131">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="e4a42-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="e4a42-132">若要查看有关所有访问边缘配置设置的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="e4a42-132">To view information about all your Access Edge configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsAccessEdgeConfiguration
    
    <span data-ttu-id="e4a42-133">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="e4a42-133">That will return information similar to this:</span></span>
    
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

## <a name="in-this-section"></a><span data-ttu-id="e4a42-134">本部分内容</span><span class="sxs-lookup"><span data-stu-id="e4a42-134">In This Section</span></span>

  - [<span data-ttu-id="e4a42-135">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="e4a42-135">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [<span data-ttu-id="e4a42-136">在 Lync Server 2013 中启用或禁用联盟伙伴发现</span><span class="sxs-lookup"><span data-stu-id="e4a42-136">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [<span data-ttu-id="e4a42-137">在 Lync Server 2013 中启用或禁用向联盟伙伴发送存档免责声明</span><span class="sxs-lookup"><span data-stu-id="e4a42-137">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="e4a42-138">在 Lync Server 2013 中启用或禁用远程用户访问</span><span class="sxs-lookup"><span data-stu-id="e4a42-138">Enable or disable remote user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [<span data-ttu-id="e4a42-139">在 Lync Server 2013 中启用或禁用匿名用户访问</span><span class="sxs-lookup"><span data-stu-id="e4a42-139">Enable or disable anonymous user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [<span data-ttu-id="e4a42-140">在 Lync Server 2013 中分配会议策略以支持匿名用户</span><span class="sxs-lookup"><span data-stu-id="e4a42-140">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

