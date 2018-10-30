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
ms.openlocfilehash: df5fed224484a3c8f8957365f5304095a115b7b1
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839147"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="04666-103">Skype 混合配置的业务</span><span class="sxs-lookup"><span data-stu-id="04666-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="04666-104">若要配置业务混合 Skype，您需要：</span><span class="sxs-lookup"><span data-stu-id="04666-104">To configure Skype for Business hybrid, you need to:</span></span>

- [<span data-ttu-id="04666-105">配置联合身份验证</span><span class="sxs-lookup"><span data-stu-id="04666-105">Configure federation</span></span>](#configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online)
- [<span data-ttu-id="04666-106">配置共享的会话初始协议 (SIP) 地址空间</span><span class="sxs-lookup"><span data-stu-id="04666-106">Configure a shared Session Initiation Protocol (SIP) address space</span></span>](#configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space)
- [<span data-ttu-id="04666-107">如果需要，配置服务器到服务器身份验证</span><span class="sxs-lookup"><span data-stu-id="04666-107">Configure server-to-server authentication if required</span></span>](#configure-server-to-server-authentication-if-required)
  
## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="04666-108">为业务 Online 与 Skype 配置联合身份验证您的本地边缘服务</span><span class="sxs-lookup"><span data-stu-id="04666-108">Configure your on-premises Edge service for federation with Skype for Business Online</span></span>

<span data-ttu-id="04666-109">联合身份验证允许在本地部署与 Office 365 组织中的用户进行通信中的用户。</span><span class="sxs-lookup"><span data-stu-id="04666-109">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="04666-110">若要配置联合身份验证，请为业务 Server 命令行管理程序 Skype 中运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="04666-110">To configure federation, run the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

```
New-CSHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
```

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="04666-111">配置业务 Online 租户中为共享的 SIP 地址空间您 Skype</span><span class="sxs-lookup"><span data-stu-id="04666-111">Configure your Skype for Business Online tenant for a shared SIP address space</span></span>

<span data-ttu-id="04666-112">会话初始协议 (SIP) 地址是网络上每个用户的唯一标识符，类似于电话号码或电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="04666-112">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="04666-113">您尝试移动用户从内部部署到 Skype 业务 online 之前，您需要配置 Office 365 租户共享您的本地部署的共享会话初始协议 (SIP) 地址空间。</span><span class="sxs-lookup"><span data-stu-id="04666-113">Before you try to move users from on-premises to Skype for Business Online, you'll need to configure your Office 365 tenant to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="04666-114">如果未进行此配置，您可能会看到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="04666-114">If this is not configured, you may see the following error message:</span></span>
  
<span data-ttu-id="04666-115">Move-csuser: HostedMigration 容错： Error=(510)，说明 = （此用户的租户不启用了共享的 sip 地址空间。）</span><span class="sxs-lookup"><span data-stu-id="04666-115">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user's tenant is not enabled for shared sip address space.)</span></span>
  
<span data-ttu-id="04666-116">若要配置共享的 SIP 地址空间，业务 online 建立与 Skype 的远程 PowerShell 会话，然后运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="04666-116">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="04666-117">SharedSipAddressSpace 属性需要保持为“True”，直到完成迁移到联机，且本地已没有用户。</span><span class="sxs-lookup"><span data-stu-id="04666-117">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="04666-118">要建立与 Skype 的远程 PowerShell 会话业务 online，首先需要安装用于 Windows PowerShell，可以获取业务 Online 连接器模块的 Skype[此处](https://go.microsoft.com/fwlink/p/?LinkId=391911)。</span><span class="sxs-lookup"><span data-stu-id="04666-118">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get [here](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="04666-119">安装该模块后，您可以使用下列 cmdlet 建立远程会话：</span><span class="sxs-lookup"><span data-stu-id="04666-119">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
```
Import-Module SkypeOnlineConnector
```

```
$cred = Get-Credential
```

```
$CSSession = New-CsOnlineSession -Credential $cred
```

```
Import-PSSession $CSSession -AllowClobber
```

<span data-ttu-id="04666-120">有关如何建立与 Skype 的远程 PowerShell 会话的业务联机状态，以及如何使用业务 Online Connector 模块 Skype 的详细信息，请参阅[Windows PowerShell 将计算机设置](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="04666-120">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="configure-server-to-server-authentication-if-required"></a><span data-ttu-id="04666-121">如果需要，配置服务器到服务器身份验证</span><span class="sxs-lookup"><span data-stu-id="04666-121">Configure server-to-server authentication if required</span></span>

<span data-ttu-id="04666-122">根据您要配置的混合环境的类型，您可能需要配置服务器到服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="04666-122">Depending on the type of hybrid environment you are configuring, you may need to configure server-to-server authentication.</span></span>  <span data-ttu-id="04666-123">有关详细信息，请参阅[Skype 业务服务器中的管理服务器到服务器身份验证](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications)。</span><span class="sxs-lookup"><span data-stu-id="04666-123">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications).</span></span>


## <a name="see-also"></a><span data-ttu-id="04666-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04666-124">See also</span></span>

[<span data-ttu-id="04666-125">新 CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="04666-125">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

