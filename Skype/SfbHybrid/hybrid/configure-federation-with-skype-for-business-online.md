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
description: 摘要：了解如何在本地部署和 Skype for business Online 之间配置互操作性。
ms.openlocfilehash: 0df507fcc47157a9290018a199e1362cb203048b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221446"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="b7ce8-103">配置 Skype for Business 混合</span><span class="sxs-lookup"><span data-stu-id="b7ce8-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="b7ce8-104">若要配置 Skype for Business 混合，需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b7ce8-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="b7ce8-105">[将本地边缘服务配置为与 Microsoft 365 或 Office 365 联合](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365)。</span><span class="sxs-lookup"><span data-stu-id="b7ce8-105">[Configure your on-premises Edge service to federate with Microsoft 365 or Office 365](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365).</span></span>
- <span data-ttu-id="b7ce8-106">[将本地环境配置为信任 Microsoft 365 或 Office 365 并启用共享 SIP 地址空间](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365)。</span><span class="sxs-lookup"><span data-stu-id="b7ce8-106">[Configure your on-premises environment to trust Microsoft 365 or Office 365 and enable shared SIP address space](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365).</span></span>
- <span data-ttu-id="b7ce8-107">[在 Microsoft 365 或 Office 365 组织中启用共享 SIP 地址空间](#enable-shared-sip-address-space-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="b7ce8-107">[Enable shared SIP address space in your Microsoft 365 or Office 365 organization](#enable-shared-sip-address-space-in-your-organization).</span></span>

<span data-ttu-id="b7ce8-108">请注意，如果您有本地 Exchange，则可能需要在 Exchange 内部部署和 Skype for business Online 环境之间配置 OAuth。</span><span class="sxs-lookup"><span data-stu-id="b7ce8-108">Note that if you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="b7ce8-109">有关详细信息，请参阅[在 skype For Business server 中管理服务器到服务器身份验证](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications)和[计划集成 Skype For business 和 Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support)。</span><span class="sxs-lookup"><span data-stu-id="b7ce8-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) and [Plan to integrate Skype for Business and Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365"></a><span data-ttu-id="b7ce8-110">将本地边缘服务配置为与 Microsoft 365 或 Office 365 联合</span><span class="sxs-lookup"><span data-stu-id="b7ce8-110">Configure your on-premises Edge service to federate with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="b7ce8-111">联合身份验证允许本地部署中的用户与组织中的 Microsoft 365 或 Office 365 用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="b7ce8-111">Federation allows users in your on-premises deployment to communicate with Microsoft 365 or Office 365 users in your organization.</span></span> <span data-ttu-id="b7ce8-112">若要配置联合，请在 Skype for Business Server 命令行管理程序中运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b7ce8-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

<span data-ttu-id="b7ce8-113">如果 "-EnablePartnerDiscovery" 值设置为 $True，则 Skype for Business Server 将使用 DNS 记录尝试并发现未在 AllowedDomains 列表中列出的合作伙伴域。</span><span class="sxs-lookup"><span data-stu-id="b7ce8-113">If '-EnablePartnerDiscovery' value is set to $True, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="b7ce8-114">如果将此值设置为 $False，Skype for Business Server 将仅与在 AllowedDomains 列表中找到的域联盟。</span><span class="sxs-lookup"><span data-stu-id="b7ce8-114">If the value is set to $False , Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="b7ce8-115">如果使用 DNS 服务路由，则需要此参数。</span><span class="sxs-lookup"><span data-stu-id="b7ce8-115">This parameter is required if you use DNS service routing.</span></span>

> [!NOTE]
> <span data-ttu-id="b7ce8-116">有关在本地 Skype for Business 部署的用户和 Skype for business Online 组织的用户之间启用联盟的详细信息，请参阅[在 skype for Business Server 中为 skype for Business online 客户配置联合支持](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support)。</span><span class="sxs-lookup"><span data-stu-id="b7ce8-116">For more details about enabling federation between users of your on-premises Skype for Business deployment and users of a Skype for Business Online organization, see [Configuring federation support for a Skype for Business Online customer in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support).</span></span>


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365"></a><span data-ttu-id="b7ce8-117">将本地环境配置为使用 Microsoft 365 或 Office 365 启用共享 SIP 地址空间</span><span class="sxs-lookup"><span data-stu-id="b7ce8-117">Configure your on-premises environment to enable shared SIP address space with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="b7ce8-118">您还必须将本地环境配置为信任 Microsoft 365 或 Office 365 并启用共享 SIP 地址空间。</span><span class="sxs-lookup"><span data-stu-id="b7ce8-118">You must also configure your on-premises environment to trust Microsoft 365 or Office 365 and enable shared SIP address space.</span></span> <span data-ttu-id="b7ce8-119">这意味着 Microsoft 365 或 Office 365 可能会为与本地环境相同的一组 SIP 域承载用户帐户，并且可以在本地托管的用户和联机用户之间路由邮件。</span><span class="sxs-lookup"><span data-stu-id="b7ce8-119">This means Microsoft 365 or Office 365 can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span>  <span data-ttu-id="b7ce8-120">为此，请配置具有 ProxyFqdn = sipfed.online.lync.com> 的托管提供程序，如下所述。</span><span class="sxs-lookup"><span data-stu-id="b7ce8-120">You do this by configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="b7ce8-121">首先，检查是否已有具有 ProxyFqdn = sipfed.online.lync.com> 的托管提供程序。</span><span class="sxs-lookup"><span data-stu-id="b7ce8-121">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="b7ce8-122">如果有，则使用以下命令将其删除：</span><span class="sxs-lookup"><span data-stu-id="b7ce8-122">If one exists, then remove it by using the following command:</span></span>

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="b7ce8-123">然后，创建新的承载提供程序，使用 CsHostingProvider cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b7ce8-123">Then create a new hosting provider, use the New-CsHostingProvider cmdlet as follows:</span></span> 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a><span data-ttu-id="b7ce8-124">在组织中启用共享 SIP 地址空间</span><span class="sxs-lookup"><span data-stu-id="b7ce8-124">Enable shared SIP address space in your organization</span></span>
  
<span data-ttu-id="b7ce8-125">除了您在本地部署中所做的更改外，还需要在 Microsoft 365 或 Office 365 组织中进行相应的更改，以便在本地部署中启用共享 SIP 地址空间。</span><span class="sxs-lookup"><span data-stu-id="b7ce8-125">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Microsoft 365 or Office 365 organization to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="b7ce8-126">若要在组织中启用共享 SIP 地址空间，请建立与 Skype for Business Online 的远程 PowerShell 会话，然后运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b7ce8-126">To enable shared SIP address space in your organization, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="b7ce8-127">SharedSipAddressSpace 属性必须保持为 "True"，直到将联机状态移动到联机状态，并且没有用户保留在本地。</span><span class="sxs-lookup"><span data-stu-id="b7ce8-127">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="b7ce8-128">若要与团队或 Skype for business Online 建立远程 PowerShell 会话，首先需要安装可在[此处](https://go.microsoft.com/fwlink/p/?LinkId=391911)获取的适用于 Windows PowerShell 的 Skype For business Online 连接器模块。</span><span class="sxs-lookup"><span data-stu-id="b7ce8-128">To establish a remote PowerShell session with Teams or Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get [here](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="b7ce8-129">安装该模块后，可以使用以下 cmdlet 建立远程会话：</span><span class="sxs-lookup"><span data-stu-id="b7ce8-129">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
```PowerShell
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

<span data-ttu-id="b7ce8-130">有关如何建立与 Skype for business Online 的远程 PowerShell 会话以及如何使用 Skype for Business Online 连接器模块的详细信息，请参阅[设置 Windows PowerShell 的计算机](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b7ce8-130">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="b7ce8-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b7ce8-131">See also</span></span>

[<span data-ttu-id="b7ce8-132">新 CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="b7ce8-132">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)
