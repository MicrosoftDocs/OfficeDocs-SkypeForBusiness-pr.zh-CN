---
title: 配置 Skype 会议直播本地部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 摘要：了解为本地 Skype for business Server 混合部署配置 Skype 会议直播时需要执行的步骤。
ms.openlocfilehash: 8bdbb163f5ef867711ce109bc923ba0ec8401ffa
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790940"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="baa1d-103">Configure your on-premises deployment for Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="baa1d-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="baa1d-104">**摘要：** 了解为本地 Skype for business 服务器混合部署配置 Skype 会议直播时需要执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="baa1d-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="baa1d-105">Skype 会议直播是 Office 365 中的一种在线服务。</span><span class="sxs-lookup"><span data-stu-id="baa1d-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="baa1d-106">如果您运行的是本地 Skype for business 服务器，并且想要在您的环境中使用 Skype 会议直播，则需要按照本主题中的配置步骤操作。</span><span class="sxs-lookup"><span data-stu-id="baa1d-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="baa1d-107">开始之前，需要为与 Skype for Business Online 的混合配置你的环境。</span><span class="sxs-lookup"><span data-stu-id="baa1d-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="baa1d-108">有关详细信息，请参阅[Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)和[Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="baa1d-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="baa1d-109">为 Skype 会议直播配置混合环境</span><span class="sxs-lookup"><span data-stu-id="baa1d-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="baa1d-110">您需要执行以下操作来为您的 Skype 会议直播准备环境：</span><span class="sxs-lookup"><span data-stu-id="baa1d-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="baa1d-111">配置与 Skype for Business Online 资源的联盟</span><span class="sxs-lookup"><span data-stu-id="baa1d-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="baa1d-112">配置 SIP 联盟域</span><span class="sxs-lookup"><span data-stu-id="baa1d-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="baa1d-113">配置与 Skype for Business Online 资源的联盟</span><span class="sxs-lookup"><span data-stu-id="baa1d-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="baa1d-114">若要启用与 Skype for Business Online 资源的联盟，你需要为 SIP 联合提供商配置外部访问权限。</span><span class="sxs-lookup"><span data-stu-id="baa1d-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="baa1d-115">要使用 Skype for Business 服务器控制面板执行此操作，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="baa1d-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="baa1d-116">启动 Skype for Business 服务器控制面板，然后在左侧选择 "**外部访问**"。</span><span class="sxs-lookup"><span data-stu-id="baa1d-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="baa1d-117">选择“SIP 联盟提供程序”\*\*\*\*，再单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="baa1d-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="baa1d-118">使用以下设置配置新的提供程序：</span><span class="sxs-lookup"><span data-stu-id="baa1d-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="baa1d-119">**启用与此提供商的通信：**</span><span class="sxs-lookup"><span data-stu-id="baa1d-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="baa1d-120">选中</span><span class="sxs-lookup"><span data-stu-id="baa1d-120">Selected</span></span>  <br/> |
|<span data-ttu-id="baa1d-121">**提供程序名称:**</span><span class="sxs-lookup"><span data-stu-id="baa1d-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="baa1d-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="baa1d-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="baa1d-123">**访问边缘服务(FQDN):**</span><span class="sxs-lookup"><span data-stu-id="baa1d-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="baa1d-124">sipfed.resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="baa1d-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="baa1d-125">**默认验证级别:**</span><span class="sxs-lookup"><span data-stu-id="baa1d-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="baa1d-126">允许用户与使用此提供程序的每个人通信。</span><span class="sxs-lookup"><span data-stu-id="baa1d-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="baa1d-127">您也可以通过在 Skype for business Server Management Shell 中运行以下 cmdlet 来启用与 Skype for Business Online 资源的联盟：</span><span class="sxs-lookup"><span data-stu-id="baa1d-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="baa1d-128">配置 SIP 联盟域</span><span class="sxs-lookup"><span data-stu-id="baa1d-128">Configure SIP federated domains</span></span>

<span data-ttu-id="baa1d-129">接下来，你需要将 SIP 联盟域添加到 "允许的域" 列表。</span><span class="sxs-lookup"><span data-stu-id="baa1d-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="baa1d-130">对列出的每个域重复这些步骤，创建 4 个新的 SIP 联盟域。</span><span class="sxs-lookup"><span data-stu-id="baa1d-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="baa1d-131">这些域包括用于 Skype for Business Online 中的区域数据中心。</span><span class="sxs-lookup"><span data-stu-id="baa1d-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="baa1d-132">启动 Skype for Business 服务器控制面板，然后在左侧选择 "**外部访问**"。</span><span class="sxs-lookup"><span data-stu-id="baa1d-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="baa1d-133">选择“SIP 联盟域”\*\*\*\*，再单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="baa1d-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="baa1d-134">对于“域名(或 FQDN):”\*\*\*\*，输入域，为以下每个域重复此过程：</span><span class="sxs-lookup"><span data-stu-id="baa1d-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
   - <span data-ttu-id="baa1d-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="baa1d-135">noammeetings.lync.com</span></span>
    
   - <span data-ttu-id="baa1d-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="baa1d-136">emeameetings.lync.com</span></span>
    
   - <span data-ttu-id="baa1d-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="baa1d-137">apacmeetings.lync.com</span></span>
    
   - <span data-ttu-id="baa1d-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="baa1d-138">resources.lync.com</span></span>
    
<span data-ttu-id="baa1d-139">你还可以通过在 Skype for Business Server Management Shell 中运行以下 cmdlet 来配置 SIP 联盟域的外部访问：</span><span class="sxs-lookup"><span data-stu-id="baa1d-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="baa1d-140">完成这些配置步骤后，您可以开始在部署中使用 Skype 会议直播。</span><span class="sxs-lookup"><span data-stu-id="baa1d-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="baa1d-141">有关 Skype 会议直播的详细信息，请参阅[什么是 Skype 会议直播？](https://go.microsoft.com/fwlink/?LinkId=617071) [Skype 会议直播管理员指南](https://go.microsoft.com/fwlink/?LinkId=617075)。</span><span class="sxs-lookup"><span data-stu-id="baa1d-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  

