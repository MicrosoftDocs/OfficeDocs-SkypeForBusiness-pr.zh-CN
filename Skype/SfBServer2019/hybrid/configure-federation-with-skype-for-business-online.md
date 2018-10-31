---
title: Skype 混合配置的业务
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 摘要： 了解如何为业务 Online 配置内部部署和 Skype 之间的互操作性。
ms.openlocfilehash: db03636d412caa72a3b7a38d0c1d691c83d96a5b
ms.sourcegitcommit: a54864c3fcd1b8d240d0f7f2ccf68f8cba566e47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2018
ms.locfileid: "25849346"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="57d6f-103">Skype 混合配置的业务</span><span class="sxs-lookup"><span data-stu-id="57d6f-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="57d6f-104">若要配置业务混合 Skype，您需要：</span><span class="sxs-lookup"><span data-stu-id="57d6f-104">To configure Skype for Business hybrid, you need to:</span></span>

- [<span data-ttu-id="57d6f-105">配置内部部署环境与 Office 365 联盟。</span><span class="sxs-lookup"><span data-stu-id="57d6f-105">Configure your on-premises environment to federate with Office 365.</span></span>](#configure-your-on-premises-edge-service-to-federate-with-Office-365)
- [<span data-ttu-id="57d6f-106">配置为信任 Office 365 的本地环境并启用共享的 SIP 地址空间，与 Office 365。</span><span class="sxs-lookup"><span data-stu-id="57d6f-106">Configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365.</span></span>](#configure-your-on-premises-environment-to-share-your-SIP-address-space-with-Office-365)
- [<span data-ttu-id="57d6f-107">启用 Office 365 租户中的共享的 SIP 地址空间。</span><span class="sxs-lookup"><span data-stu-id="57d6f-107">Enable shared SIP address space in your Office 365 tenant.</span></span>](#configure-server-to-server-authentication-if-required)

> [!NOTE]
> <span data-ttu-id="57d6f-108">如果您有 Exchange 内部部署，您可能希望为业务 Online 环境 Exchange 内部部署和 Skype 之间配置 OAuth。</span><span class="sxs-lookup"><span data-stu-id="57d6f-108">If you have Exchange on-premises, then you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="57d6f-109">有关详细信息，请参阅[Skype 业务服务器中的管理服务器到服务器身份验证](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications)和[计划集成业务和 Exchange Skype](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support)。</span><span class="sxs-lookup"><span data-stu-id="57d6f-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) and [Plan to integrate Skype for Business and Exchange](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365"></a><span data-ttu-id="57d6f-110">配置内部部署边缘服务与 Office 365 联盟</span><span class="sxs-lookup"><span data-stu-id="57d6f-110">Configure your on-premises Edge service to federate with Office 365</span></span>

<span data-ttu-id="57d6f-111">联合身份验证允许在本地部署与 Office 365 组织中的用户进行通信中的用户。</span><span class="sxs-lookup"><span data-stu-id="57d6f-111">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="57d6f-112">若要配置联合身份验证，请为业务 Server 命令行管理程序 Skype 中运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="57d6f-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```



## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a><span data-ttu-id="57d6f-113">配置内部部署环境以便与 Office 365 的共享的 SIP 地址空间</span><span class="sxs-lookup"><span data-stu-id="57d6f-113">Configure your on-premises environment to enable shared SIP address space with Office 365</span></span>

<span data-ttu-id="57d6f-114">您还必须配置为信任 Office 365 的本地环境，并启用共享的 SIP 地址空间，与 Office 365。</span><span class="sxs-lookup"><span data-stu-id="57d6f-114">You must also configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365.</span></span> <span data-ttu-id="57d6f-115">这意味着 Office 365 可能会承载作为您的本地环境，一组相同的 SIP 域的用户帐户和消息可以是承载在本地用户之间的路由和联机。</span><span class="sxs-lookup"><span data-stu-id="57d6f-115">This means Office 365 can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span>  <span data-ttu-id="57d6f-116">通过使用 ProxyFqdn=sipfed.online.lync.com 如下所述配置宿主提供程序执行此操作。</span><span class="sxs-lookup"><span data-stu-id="57d6f-116">You do this by configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="57d6f-117">首先，检查您是否已具有 ProxyFqdn=sipfed.online.lync.com 的宿主提供程序。</span><span class="sxs-lookup"><span data-stu-id="57d6f-117">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="57d6f-118">如果存在，然后将其删除通过使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="57d6f-118">If one exists, then remove it by using the following command:</span></span>

```
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="57d6f-119">然后创建一个新的宿主提供程序，使用 New-cshostingprovider cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="57d6f-119">Then create a new hosting provider, use the New-CsHostingProvider cmdlet as follows:</span></span> 

```
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-tenant"></a><span data-ttu-id="57d6f-120">启用 Office 365 租户中的共享的 SIP 地址空间</span><span class="sxs-lookup"><span data-stu-id="57d6f-120">Enable shared SIP address space in your Office 365 tenant</span></span>
  
<span data-ttu-id="57d6f-121">除了在本地部署中所做的更改，您将需要对已启用共享的 SIP 地址空间的本地部署 Office 365 租户中进行相应的更改。</span><span class="sxs-lookup"><span data-stu-id="57d6f-121">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Office 365 tenant to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="57d6f-122">若要启用 Office 365 租户中的共享的 SIP 地址空间，业务 online 建立与 Skype 的远程 PowerShell 会话，然后运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="57d6f-122">To enable shared SIP address space in your Office 365 tenant, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="57d6f-123">SharedSipAddressSpace 属性需要保持为“True”，直到完成迁移到联机，且本地已没有用户。</span><span class="sxs-lookup"><span data-stu-id="57d6f-123">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="57d6f-124">要建立与团队或 Skype 的远程 PowerShell 会话业务 online，首先需要安装用于 Windows PowerShell，可以获取业务 Online 连接器模块的 Skype[此处](https://go.microsoft.com/fwlink/p/?LinkId=391911)。</span><span class="sxs-lookup"><span data-stu-id="57d6f-124">To establish a remote PowerShell session with Teams or Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get [here](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="57d6f-125">安装该模块后，您可以使用下列 cmdlet 建立远程会话：</span><span class="sxs-lookup"><span data-stu-id="57d6f-125">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
```
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

<span data-ttu-id="57d6f-126">有关如何建立与 Skype 的远程 PowerShell 会话的业务联机状态，以及如何使用业务 Online Connector 模块 Skype 的详细信息，请参阅[Windows PowerShell 将计算机设置](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="57d6f-126">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="57d6f-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57d6f-127">See also</span></span>

[<span data-ttu-id="57d6f-128">新 CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="57d6f-128">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

