---
title: 配置 Skype for Business 混合
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 摘要：了解如何配置本地部署和 Skype for Business Online 之间的互操作性。
ms.openlocfilehash: e2af514ef1a10d652abae7bdd39a923dc52e1c4a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118941"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="94632-103">配置 Skype for Business 混合环境</span><span class="sxs-lookup"><span data-stu-id="94632-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="94632-104">若要配置 Skype for Business 混合，需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="94632-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="94632-105">[将本地边缘服务配置为与 Microsoft 365 或 Office 365 联合](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365)。</span><span class="sxs-lookup"><span data-stu-id="94632-105">[Configure your on-premises Edge service to federate with Microsoft 365 or Office 365](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365).</span></span>
- <span data-ttu-id="94632-106">[将本地环境配置为信任 Microsoft 365 或 Office 365 并启用共享 SIP 地址空间](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365)。</span><span class="sxs-lookup"><span data-stu-id="94632-106">[Configure your on-premises environment to trust Microsoft 365 or Office 365 and enable shared SIP address space](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365).</span></span>
- <span data-ttu-id="94632-107">[在 Microsoft 365 或 Office 365 组织中启用共享 SIP](#enable-shared-sip-address-space-in-your-organization)地址空间。</span><span class="sxs-lookup"><span data-stu-id="94632-107">[Enable shared SIP address space in your Microsoft 365 or Office 365 organization](#enable-shared-sip-address-space-in-your-organization).</span></span>

<span data-ttu-id="94632-108">请注意，如果你有本地 Exchange，你可能想要在本地 Exchange 和 Skype for Business Online 环境之间配置 OAuth。</span><span class="sxs-lookup"><span data-stu-id="94632-108">Note that if you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="94632-109">有关详细信息，请参阅在[Skype for Business Server](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md)中管理服务器到服务器身份验证和[计划集成 Skype for Business 和 Exchange。](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)</span><span class="sxs-lookup"><span data-stu-id="94632-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) and [Plan to integrate Skype for Business and Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365"></a><span data-ttu-id="94632-110">配置本地边缘服务以与 Microsoft 365 或 Office 365 联盟</span><span class="sxs-lookup"><span data-stu-id="94632-110">Configure your on-premises Edge service to federate with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="94632-111">联合身份验证允许本地部署中的用户与贵组织的 Microsoft 365 或 Office 365 用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="94632-111">Federation allows users in your on-premises deployment to communicate with Microsoft 365 or Office 365 users in your organization.</span></span> <span data-ttu-id="94632-112">若要配置联盟，请运行 Skype for Business Server 命令行管理程序中的以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="94632-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

<span data-ttu-id="94632-113">如果"-EnablePartnerDiscovery"值设置为 $True，Skype for Business Server 将使用 DNS 记录来尝试和发现未列在 AllowedDomains 列表中的合作伙伴域。</span><span class="sxs-lookup"><span data-stu-id="94632-113">If '-EnablePartnerDiscovery' value is set to $True, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="94632-114">如果该值设置为 $False ，Skype for Business Server 将仅与 AllowedDomains 列表中的域联盟。</span><span class="sxs-lookup"><span data-stu-id="94632-114">If the value is set to $False , Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="94632-115">如果使用 DNS 服务路由，则需要此参数。</span><span class="sxs-lookup"><span data-stu-id="94632-115">This parameter is required if you use DNS service routing.</span></span>

> [!NOTE]
> <span data-ttu-id="94632-116">有关在本地 Skype for Business 部署的用户和 Skype for Business Online 组织的用户之间启用联盟的更多详细信息，请参阅在 Skype for Business Server 中为 [Skype for Business Online](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md)客户配置联盟支持。</span><span class="sxs-lookup"><span data-stu-id="94632-116">For more details about enabling federation between users of your on-premises Skype for Business deployment and users of a Skype for Business Online organization, see [Configuring federation support for a Skype for Business Online customer in Skype for Business Server](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md).</span></span>


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365"></a><span data-ttu-id="94632-117">配置本地环境以启用 Microsoft 365 或 Office 365 的共享 SIP 地址空间</span><span class="sxs-lookup"><span data-stu-id="94632-117">Configure your on-premises environment to enable shared SIP address space with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="94632-118">还必须将本地环境配置为信任 Microsoft 365 或 Office 365 并启用共享 SIP 地址空间。</span><span class="sxs-lookup"><span data-stu-id="94632-118">You must also configure your on-premises environment to trust Microsoft 365 or Office 365 and enable shared SIP address space.</span></span> <span data-ttu-id="94632-119">这意味着 Microsoft 365 或 Office 365 可能会托管与本地环境相同的 SIP 域集的用户帐户，并且可以在本地和联机托管的用户之间路由消息。</span><span class="sxs-lookup"><span data-stu-id="94632-119">This means Microsoft 365 or Office 365 can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span>  <span data-ttu-id="94632-120">为此，您可以使用 ProxyFqdn=sipfed.online.lync.com 配置宿主提供商，如下所述。</span><span class="sxs-lookup"><span data-stu-id="94632-120">You do this by configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="94632-121">首先，检查您是否已有具有 ProxyFqdn=sipfed.online.lync.com 的宿主提供商。</span><span class="sxs-lookup"><span data-stu-id="94632-121">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="94632-122">如果存在，则使用下列命令将其删除：</span><span class="sxs-lookup"><span data-stu-id="94632-122">If one exists, then remove it by using the following command:</span></span>

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="94632-123">然后，创建新的宿主提供商，New-CsHostingProvider cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="94632-123">Then create a new hosting provider, use the New-CsHostingProvider cmdlet as follows:</span></span> 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a><span data-ttu-id="94632-124">在组织中启用共享 SIP 地址空间</span><span class="sxs-lookup"><span data-stu-id="94632-124">Enable shared SIP address space in your organization</span></span>
  
<span data-ttu-id="94632-125">除了在本地部署中做出更改之外，还需要在 Microsoft 365 或 Office 365 组织中进行相应的更改，以启用本地部署的共享 SIP 地址空间。</span><span class="sxs-lookup"><span data-stu-id="94632-125">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Microsoft 365 or Office 365 organization to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="94632-126">若要在组织中启用共享 SIP 地址空间，请与 Skype for Business Online 建立远程 PowerShell 会话，然后运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="94632-126">To enable shared SIP address space in your organization, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="94632-127">SharedSipAddressSpace 属性需要保持"True"，直到最终移动到联机，并且没有用户保持本地。</span><span class="sxs-lookup"><span data-stu-id="94632-127">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="94632-128">若要与 Teams 或 Skype for Business Online 建立远程 PowerShell 会话，首先需要安装 [Teams PowerShell 模块](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="94632-128">To establish a remote PowerShell session with Teams or Skype for Business Online, you first need to install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
  
<span data-ttu-id="94632-129">安装模块后，可以使用以下 cmdlet 建立远程会话：</span><span class="sxs-lookup"><span data-stu-id="94632-129">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

<span data-ttu-id="94632-130">若要详细了解如何与 Skype for Business Online 建立远程 PowerShell 会话，以及如何使用 Skype for Business Online 连接器模块，请参阅为计算机设置[Windows PowerShell。](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="94632-130">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="94632-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94632-131">See also</span></span>

[<span data-ttu-id="94632-132">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="94632-132">New-CsHostingProvider</span></span>](/powershell/module/skype/new-cshostingprovider?view=skype-ps)