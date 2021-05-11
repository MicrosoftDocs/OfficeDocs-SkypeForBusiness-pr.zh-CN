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
description: 摘要：了解如何配置本地部署和本地部署之间的Teams。
ms.openlocfilehash: 2c6fda43b939a616071009be2b8d28e636036101
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305966"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="a84b7-103">配置 Skype for Business 混合环境</span><span class="sxs-lookup"><span data-stu-id="a84b7-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="a84b7-104">若要配置 Skype for Business 混合，需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a84b7-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="a84b7-105">[将本地边缘服务配置为与](#configure-your-on-premises-edge-service-to-federate-with-teams)Teams 联合。</span><span class="sxs-lookup"><span data-stu-id="a84b7-105">[Configure your on-premises Edge service to federate with Teams](#configure-your-on-premises-edge-service-to-federate-with-teams).</span></span>
- <span data-ttu-id="a84b7-106">[将本地环境配置为信任Teams并启用共享 SIP 地址空间](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams)。</span><span class="sxs-lookup"><span data-stu-id="a84b7-106">[Configure your on-premises environment to trust Teams and enable shared SIP address space](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams).</span></span>
- <span data-ttu-id="a84b7-107">[在组织中启用共享 SIP 地址Teams空间](#enable-shared-sip-address-space-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="a84b7-107">[Enable shared SIP address space in your Teams organization](#enable-shared-sip-address-space-in-your-organization).</span></span>

<span data-ttu-id="a84b7-108">如果你有本地Exchange，你可能想要在本地和联机环境Exchange OAuth Skype for Business OAuth。</span><span class="sxs-lookup"><span data-stu-id="a84b7-108">If you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="a84b7-109">有关详细信息，请参阅在 Skype for Business Server 中管理服务器到服务器身份验证[Skype for Business Exchange。](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) [](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md)</span><span class="sxs-lookup"><span data-stu-id="a84b7-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) and [Plan to integrate Skype for Business and Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-teams"></a><span data-ttu-id="a84b7-110">配置内部部署边缘服务以与 Teams</span><span class="sxs-lookup"><span data-stu-id="a84b7-110">Configure your on-premises Edge service to federate with Teams</span></span>

<span data-ttu-id="a84b7-111">联合身份验证允许本地部署中的用户与Teams Skype for Business Online 用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="a84b7-111">Federation allows users in your on-premises deployment to communicate with Teams and Skype for Business Online  users in your organization.</span></span> <span data-ttu-id="a84b7-112">若要配置联盟，请运行命令行管理程序Skype for Business Server cmdlet：</span><span class="sxs-lookup"><span data-stu-id="a84b7-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

<span data-ttu-id="a84b7-113">如果"-EnablePartnerDiscovery"值设置为 $True，Skype for Business Server 将使用 DNS 记录尝试和发现 AllowedDomains 列表中未列出的合作伙伴域。</span><span class="sxs-lookup"><span data-stu-id="a84b7-113">If '-EnablePartnerDiscovery' value is set to $True, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="a84b7-114">如果该值设置为 $False ，Skype for Business Server将仅与 AllowedDomains 列表中的域联盟。</span><span class="sxs-lookup"><span data-stu-id="a84b7-114">If the value is set to $False , Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="a84b7-115">如果使用 DNS 服务路由，则需要此参数。</span><span class="sxs-lookup"><span data-stu-id="a84b7-115">This parameter is required if you use DNS service routing.</span></span>

> [!NOTE]
> <span data-ttu-id="a84b7-116">有关在内部部署 Skype for Business 部署的用户和 Microsoft 365 组织的用户之间启用联盟的更多详细信息，请参阅在 Skype for Business Server 中为 Microsoft 365 客户配置[联合Skype for Business Server。](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md)</span><span class="sxs-lookup"><span data-stu-id="a84b7-116">For more details about enabling federation between users of your on-premises Skype for Business deployment and users of a Microsoft 365 organization, see [Configuring federation support for a Microsoft 365 customer in Skype for Business Server](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md).</span></span>


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams"></a><span data-ttu-id="a84b7-117">配置本地环境以启用与用户共享的 SIP 地址Teams</span><span class="sxs-lookup"><span data-stu-id="a84b7-117">Configure your on-premises environment to enable shared SIP address space with Teams</span></span>

<span data-ttu-id="a84b7-118">还必须将本地环境配置为信任Teams并启用共享 SIP 地址空间。</span><span class="sxs-lookup"><span data-stu-id="a84b7-118">You must also configure your on-premises environment to trust Teams and enable shared SIP address space.</span></span> <span data-ttu-id="a84b7-119">此配置Teams可以托管与本地环境相同的 SIP 域集的用户帐户，并且可以在本地和联机托管的用户之间路由消息。</span><span class="sxs-lookup"><span data-stu-id="a84b7-119">This configuration means Teams can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span> <span data-ttu-id="a84b7-120">使用 ProxyFqdn=sipfed.online.lync.com 配置宿主提供商，如下所述。</span><span class="sxs-lookup"><span data-stu-id="a84b7-120">You configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="a84b7-121">首先，检查您是否已有具有 ProxyFqdn=sipfed.online.lync.com 的宿主提供商。</span><span class="sxs-lookup"><span data-stu-id="a84b7-121">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="a84b7-122">如果存在，则使用命令行管理程序中的以下命令将其删除Skype for Business Server命令行管理程序：</span><span class="sxs-lookup"><span data-stu-id="a84b7-122">If one exists, then remove it by using the following command in the Skype for Business Server Management Shell:</span></span>

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="a84b7-123">然后，使用 cmdlet 创建新的托管New-CsHostingProvider，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a84b7-123">Then create a new hosting provider by using the New-CsHostingProvider cmdlet as follows:</span></span> 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a><span data-ttu-id="a84b7-124">在组织中启用共享 SIP 地址空间</span><span class="sxs-lookup"><span data-stu-id="a84b7-124">Enable shared SIP address space in your organization</span></span>
  
<span data-ttu-id="a84b7-125">除了在内部部署中做出更改之外，还需要在 Teams 组织中进行相应的更改，以启用本地部署的共享 SIP 地址空间。</span><span class="sxs-lookup"><span data-stu-id="a84b7-125">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Teams organization to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="a84b7-126">若要在组织中启用共享 SIP 地址空间，请与 Teams 建立远程 PowerShell 会话，然后运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="a84b7-126">To enable shared SIP address space in your organization, establish a remote PowerShell session with Teams, and then run the following cmdlet:</span></span>
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="a84b7-127">SharedSipAddressSpace 属性需要保持"True"，直到最终移动到联机，并且没有用户保持本地。</span><span class="sxs-lookup"><span data-stu-id="a84b7-127">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="a84b7-128">若要与 Teams (或 Skype for Business Online) 建立远程 PowerShell 会话，首先需要安装 Teams [PowerShell 模块](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="a84b7-128">To establish a remote PowerShell session with Teams (or Skype for Business Online), you first need to install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span> <span data-ttu-id="a84b7-129">The Teams PowerShell module replaces the Skype for Busines Online Connector module， which has been retired.</span><span class="sxs-lookup"><span data-stu-id="a84b7-129">The Teams PowerShell module replaces the Skype for Busines Online Connector module, which has been retired.</span></span>
  
<span data-ttu-id="a84b7-130">安装模块后，可以使用以下 cmdlet 建立远程会话：</span><span class="sxs-lookup"><span data-stu-id="a84b7-130">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

<span data-ttu-id="a84b7-131">若要详细了解如何使用 Teams 建立远程 PowerShell 会话，以及如何使用 Teams PowerShell 模块，请参阅为 Windows PowerShell 设置[计算机](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="a84b7-131">For more information about how to establish a remote PowerShell session with Teams, and how to use the Teams PowerShell module, see [Set up your computer for Windows PowerShell](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="a84b7-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a84b7-132">See also</span></span>

[<span data-ttu-id="a84b7-133">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="a84b7-133">New-CsHostingProvider</span></span>](/powershell/module/skype/new-cshostingprovider?view=skype-ps)
