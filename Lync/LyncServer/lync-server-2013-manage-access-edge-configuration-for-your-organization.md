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

# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a><span data-ttu-id="8306e-102">在 Lync Server 2013 中管理您的组织的访问边缘配置</span><span class="sxs-lookup"><span data-stu-id="8306e-102">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8306e-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8306e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8306e-104">本文档是预备文档，可能随时更改。</span><span class="sxs-lookup"><span data-stu-id="8306e-104">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="8306e-105">空白主题均以占位符的形式包含在内。</span><span class="sxs-lookup"><span data-stu-id="8306e-105">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="8306e-106">部署一个或多个边缘服务器后, 必须通过你的组织支持的边缘服务器启用外部域或提供者访问、远程用户访问和匿名用户访问的类型。</span><span class="sxs-lookup"><span data-stu-id="8306e-106">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="8306e-107">这些选项包括以下可通过 "**访问边缘配置**" 页面配置的访问类型:</span><span class="sxs-lookup"><span data-stu-id="8306e-107">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="8306e-108">**启用联盟和公共 IM 连接**   如果你想要支持用户对联盟伙伴域的访问, 请启用此连接。</span><span class="sxs-lookup"><span data-stu-id="8306e-108">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="8306e-109">此设置适用于针对**外部访问策略**页面上的全局、网站或用户作用域配置的 SIP 联合身份验证和 XMPP 联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="8306e-109">This setting applies to both SIP federation and XMPP federation that are configured for global, site or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="8306e-110">若要应用联盟设置, 必须在两个页面上配置联合身份验证支持。</span><span class="sxs-lookup"><span data-stu-id="8306e-110">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="8306e-111">存在两个选项, 这两个选项是有关如何发现联合合作伙伴的可选设置, 以及是否存档免责声明 (通知你与你的部署已启用存档的联合联系人), 并且通信将存档的详细信息) 将发送给联系人</span><span class="sxs-lookup"><span data-stu-id="8306e-111">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts</span></span>
    
      - <span data-ttu-id="8306e-112">**启用合作伙伴域发现**   选择此选项可自动发现你可以与其进行联盟的域。</span><span class="sxs-lookup"><span data-stu-id="8306e-112">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="8306e-113">Lync Server 2013 使用域名系统 (DNS) 记录来尝试发现未在 "允许的域" 列表中列出的域、自动评估已发现的联盟伙伴的传入流量并基于信任级别限制或阻止该流量。通讯量和管理员设置。</span><span class="sxs-lookup"><span data-stu-id="8306e-113">Lync Server 2013 uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="8306e-114">如果不选择此选项, 则仅对在 "允许的域" 列表中包含的域中的用户启用 "联盟用户访问"。</span><span class="sxs-lookup"><span data-stu-id="8306e-114">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="8306e-115">无论是否选择此选项, 您都可以指定要阻止或允许的单个域, 包括限制对运行联盟域中的访问边缘服务的特定服务器的访问。</span><span class="sxs-lookup"><span data-stu-id="8306e-115">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="8306e-116">有关详细信息, 请参阅[在 Lync Server 2013 中配置对允许的外部域的支持](lync-server-2013-configure-support-for-allowed-external-domains.md)。</span><span class="sxs-lookup"><span data-stu-id="8306e-116">For details, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>
    
      - <span data-ttu-id="8306e-117">**将存档免责声明发送给联盟合作伙伴**   选择此选项可将存档免责声明消息发送给联合合作伙伴, 建议记录通信详细信息。</span><span class="sxs-lookup"><span data-stu-id="8306e-117">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="8306e-118">如果您将外部通信与联盟伙伴域进行了存档, 则应启用存档免责声明通知, 以警告合作伙伴其邮件和通信详细信息已被你的部署存档。</span><span class="sxs-lookup"><span data-stu-id="8306e-118">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="8306e-119">有关存档的详细信息, 请参阅[在 Lync Server 2013 中定义存档要求](lync-server-2013-defining-your-requirements-for-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="8306e-119">For details on archiving, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).</span></span>

  - <span data-ttu-id="8306e-120">**启用远程用户访问**   如果你希望你的组织中的用户 (如正在旅行的远程办公和用户) 能够连接到 Lync 服务器, 请启用此选项。</span><span class="sxs-lookup"><span data-stu-id="8306e-120">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server.</span></span> <span data-ttu-id="8306e-121">有关详细信息, 请参阅[在 Lync Server 2013 中启用或禁用远程用户访问](lync-server-2013-enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="8306e-121">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="8306e-122">**允许匿名用户访问会议**   如果希望内部用户邀请外部匿名用户加入他们组织的会议, 请启用此选项。</span><span class="sxs-lookup"><span data-stu-id="8306e-122">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="8306e-123">启用此设置仅允许匿名用户进行会议。</span><span class="sxs-lookup"><span data-stu-id="8306e-123">Enabling this setting only allows anonymous users for conferences.</span></span> <span data-ttu-id="8306e-124">若要配置会议体验和选项以定义用户如何使用会议以及如何包含匿名用户, 请参阅为[网站或用户](https://technet.microsoft.com/en-us/library/gg429715\(v=ocs.15\))[创建或修改会议用户体验中的详细信息。Lync Server 2013 的会议策略设置参考](lync-server-2013-conferencing-policy-settings-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="8306e-124">To configure the conferencing experience and options that will define how and what your users can do with conferences and for the inclusion of anonymous users, see details at [Create or Modify Conferencing User Experience for a Site or Users](https://technet.microsoft.com/en-us/library/gg429715\(v=ocs.15\)) and [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8306e-125">除了启用外部用户访问支持外, 你还可以配置策略来控制在你的组织中使用远程用户访问, 然后再向用户提供任何类型的外部用户访问权限。</span><span class="sxs-lookup"><span data-stu-id="8306e-125">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="8306e-126">有关创建、配置和应用外部用户访问策略的详细信息, 请参阅<A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">在 Lync Server 2013 中管理外部访问策略</A>。</span><span class="sxs-lookup"><span data-stu-id="8306e-126">For details about creating, configuring, and applying policies for external user access, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="8306e-127">**使用 Windows PowerShell cmdlet 查看访问边缘配置信息**</span><span class="sxs-lookup"><span data-stu-id="8306e-127">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="8306e-128">可以使用 Windows PowerShell 和**CsAccessEdgeConfiguration** cmdlet 查看访问边缘配置信息。</span><span class="sxs-lookup"><span data-stu-id="8306e-128">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="8306e-129">此 cmdlet 既可以从 Lync Server 2013 管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="8306e-129">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8306e-130">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="8306e-130">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="8306e-131">若要查看有关所有访问边缘配置设置的信息, 请在 Lync Server 命令行管理程序中键入以下命令, 然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="8306e-131">To view information about all your Access Edge configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsAccessEdgeConfiguration
    
    <span data-ttu-id="8306e-132">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="8306e-132">That will return information similar to this:</span></span>
    
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

## <a name="in-this-section"></a><span data-ttu-id="8306e-133">本节内容</span><span class="sxs-lookup"><span data-stu-id="8306e-133">In This Section</span></span>

  - [<span data-ttu-id="8306e-134">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="8306e-134">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [<span data-ttu-id="8306e-135">在 Lync Server 2013 中启用或禁用联盟伙伴发现</span><span class="sxs-lookup"><span data-stu-id="8306e-135">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [<span data-ttu-id="8306e-136">在 Lync Server 2013 中启用或禁用向联盟伙伴发送存档免责声明</span><span class="sxs-lookup"><span data-stu-id="8306e-136">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="8306e-137">在 Lync Server 2013 中启用或禁用远程用户访问</span><span class="sxs-lookup"><span data-stu-id="8306e-137">Enable or disable remote user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [<span data-ttu-id="8306e-138">在 Lync Server 2013 中启用或禁用匿名用户访问</span><span class="sxs-lookup"><span data-stu-id="8306e-138">Enable or disable anonymous user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [<span data-ttu-id="8306e-139">在 Lync Server 2013 中分配会议策略以支持匿名用户</span><span class="sxs-lookup"><span data-stu-id="8306e-139">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

