---
title: 配置与 Skype for Business Online 联盟
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/12/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
description: 摘要： 了解如何为业务 Online 配置内部部署和 Skype 之间的互操作性。
ms.openlocfilehash: 403cabdd808cd197ece2289564b14fea62a5c72a
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="configure-federation-with-skype-for-business-online"></a><span data-ttu-id="a419b-103">配置与 Skype for Business Online 联盟</span><span class="sxs-lookup"><span data-stu-id="a419b-103">Configure federation with Skype for Business Online</span></span>
 
<span data-ttu-id="a419b-104">**摘要：**了解如何为业务 Online 配置内部部署和 Skype 之间的互操作性。</span><span class="sxs-lookup"><span data-stu-id="a419b-104">**Summary:** Learn how to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>
  
<span data-ttu-id="a419b-105">按照本节业务 online 配置内部部署和 Skype 之间的互操作性中的步骤。</span><span class="sxs-lookup"><span data-stu-id="a419b-105">Follow the steps in this section to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>
  
## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="a419b-106">为业务 Online 与 Skype 配置联合身份验证您的本地边缘服务</span><span class="sxs-lookup"><span data-stu-id="a419b-106">Configure your on-premises Edge service for federation with Skype for Business Online</span></span>

<span data-ttu-id="a419b-107">联合身份验证允许在本地部署与 Office 365 组织中的用户进行通信中的用户。</span><span class="sxs-lookup"><span data-stu-id="a419b-107">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="a419b-108">若要配置联合身份验证，请为业务 Server 命令行管理程序 Skype 中运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a419b-108">To configure federation, run the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

```
New-CSHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
```

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="a419b-109">配置业务 Online 租户中为共享的 SIP 地址空间您 Skype</span><span class="sxs-lookup"><span data-stu-id="a419b-109">Configure your Skype for Business Online tenant for a shared SIP address space</span></span>

<span data-ttu-id="a419b-110">会话初始协议 (SIP) 地址是网络上每个用户的唯一标识符，类似于电话号码或电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a419b-110">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="a419b-111">您尝试移动用户从内部部署到 Skype 业务 online 之前，您需要配置 Office 365 租户共享您的本地部署的共享会话初始协议 (SIP) 地址空间。</span><span class="sxs-lookup"><span data-stu-id="a419b-111">Before you try to move users from on-premises to Skype for Business Online, you'll need to configure your Office 365 tenant to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="a419b-112">如果未进行此配置，您可能会看到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="a419b-112">If this is not configured, you may see the following error message:</span></span>
  
<span data-ttu-id="a419b-113">Move-csuser: HostedMigration 容错： Error=(510)，说明 = （此用户的租户不启用了共享的 sip 地址空间。）</span><span class="sxs-lookup"><span data-stu-id="a419b-113">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user's tenant is not enabled for shared sip address space.)</span></span>
  
<span data-ttu-id="a419b-114">若要配置共享的 SIP 地址空间，业务 online 建立与 Skype 的远程 PowerShell 会话，然后运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a419b-114">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="a419b-115">SharedSipAddressSpace 属性需要保持为“True”，直到完成迁移到联机，且本地已没有用户。</span><span class="sxs-lookup"><span data-stu-id="a419b-115">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="a419b-116">要建立与 Skype 的远程 PowerShell 会话业务 online，首先需要安装用于 Windows PowerShell，您可以在此处获取业务 Online 连接器模块的 Skype: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911)。</span><span class="sxs-lookup"><span data-stu-id="a419b-116">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="a419b-117">安装该模块后，您可以使用下列 cmdlet 建立远程会话：</span><span class="sxs-lookup"><span data-stu-id="a419b-117">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
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

<span data-ttu-id="a419b-118">有关如何为业务联机建立与 Skype 的远程 PowerShell 会话的详细信息，请参阅[连接到 Lync Online 通过使用 Windows PowerShell](http://technet.microsoft.com/library/6167dad9-9628-4fdb-bed1-bdb3f7108e64.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a419b-118">For more information about how to establish a remote PowerShell session with Skype for Business Online, see [Connecting to Lync Online By Using Windows PowerShell](http://technet.microsoft.com/library/6167dad9-9628-4fdb-bed1-bdb3f7108e64.aspx).</span></span>
  
<span data-ttu-id="a419b-119">有关使用的业务 Online 连接器 PowerShell 模块 Skype 的详细信息，请参阅[使用 Windows PowerShell 管理 Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a419b-119">For more information about using the Skype for Business Online connector PowerShell module, see [Using Windows PowerShell to Manage Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a419b-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a419b-120">See also</span></span>

#### 

[<span data-ttu-id="a419b-121">新 CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="a419b-121">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

