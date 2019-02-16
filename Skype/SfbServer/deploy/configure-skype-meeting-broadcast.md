---
title: 配置 Skype 会议直播本地部署
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 摘要： 了解您需要为您的本地 Skype Business Server 混合部署配置 Skype 会议广播执行的步骤。
ms.openlocfilehash: 09b99cab45b8832be34a3219a222324d199c5195
ms.sourcegitcommit: 4967c9b1010a444475dcfbdb6dd3c058494449d9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2019
ms.locfileid: "30069467"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="2fc87-103">Configure your on-premises deployment for Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="2fc87-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="2fc87-104">**摘要：** 了解您需要为您的本地 Skype Business Server 混合部署配置 Skype 会议广播执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="2fc87-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="2fc87-105">Skype 会议广播是为 Office 365 的一部分的联机服务。</span><span class="sxs-lookup"><span data-stu-id="2fc87-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="2fc87-106">如果您的业务 Server 内部部署运行 Skype，并想要在您的环境中使用 Skype 会议广播，您需要按照本主题中的配置步骤。</span><span class="sxs-lookup"><span data-stu-id="2fc87-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="2fc87-107">在开始之前，您的环境需要用来配置混合 Skype 业务 online。</span><span class="sxs-lookup"><span data-stu-id="2fc87-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="2fc87-108">有关详细信息，请参阅[Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)和[Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="2fc87-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="2fc87-109">为会议广播 Skype 配置混合环境</span><span class="sxs-lookup"><span data-stu-id="2fc87-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="2fc87-110">您需要执行以下操作来为 Skype 会议广播准备环境：</span><span class="sxs-lookup"><span data-stu-id="2fc87-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="2fc87-111">配置联合身份验证与 Skype 的业务联机资源</span><span class="sxs-lookup"><span data-stu-id="2fc87-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="2fc87-112">配置 SIP 联盟域</span><span class="sxs-lookup"><span data-stu-id="2fc87-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="2fc87-113">配置联合身份验证与 Skype 的业务联机资源</span><span class="sxs-lookup"><span data-stu-id="2fc87-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="2fc87-114">若要启用的业务联机资源与 Skype 联合身份验证，您需要配置外部访问的 SIP 联盟提供程序。</span><span class="sxs-lookup"><span data-stu-id="2fc87-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="2fc87-115">若要执行此使用适用于业务 Server Control Panel Skype 执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="2fc87-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="2fc87-116">为业务 Server Control Panel 启动 Skype 并选择左侧的**外部访问**。</span><span class="sxs-lookup"><span data-stu-id="2fc87-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="2fc87-117">选择“SIP 联盟提供程序”\*\*\*\*，再单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2fc87-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="2fc87-118">使用以下设置配置新的提供程序：</span><span class="sxs-lookup"><span data-stu-id="2fc87-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="2fc87-119">**启用与此提供程序通信：**</span><span class="sxs-lookup"><span data-stu-id="2fc87-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="2fc87-120">选中</span><span class="sxs-lookup"><span data-stu-id="2fc87-120">Selected</span></span>  <br/> |
|<span data-ttu-id="2fc87-121">**提供程序名称:**</span><span class="sxs-lookup"><span data-stu-id="2fc87-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="2fc87-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="2fc87-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="2fc87-123">**访问边缘服务(FQDN):**</span><span class="sxs-lookup"><span data-stu-id="2fc87-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="2fc87-124">sipfed.resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="2fc87-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="2fc87-125">**默认验证级别:**</span><span class="sxs-lookup"><span data-stu-id="2fc87-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="2fc87-126">允许用户与使用此提供程序的每个人通信。</span><span class="sxs-lookup"><span data-stu-id="2fc87-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="2fc87-127">您还可以通过运行以下 cmdlet 中 Skype 业务 Server 命令行管理程序启用业务联机资源与 Skype 联合身份的验证：</span><span class="sxs-lookup"><span data-stu-id="2fc87-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="2fc87-128">配置 SIP 联盟域</span><span class="sxs-lookup"><span data-stu-id="2fc87-128">Configure SIP federated domains</span></span>

<span data-ttu-id="2fc87-129">接下来，您需要将 SIP 联盟域添加到允许的域列表。</span><span class="sxs-lookup"><span data-stu-id="2fc87-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="2fc87-130">对列出的每个域重复这些步骤，创建 4 个新的 SIP 联盟域。</span><span class="sxs-lookup"><span data-stu-id="2fc87-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="2fc87-131">包含这些域是的区域数据中心中使用的 Skype 业务联机。</span><span class="sxs-lookup"><span data-stu-id="2fc87-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="2fc87-132">为业务 Server Control Panel 启动 Skype 并选择左侧的**外部访问**。</span><span class="sxs-lookup"><span data-stu-id="2fc87-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="2fc87-133">选择“SIP 联盟域”\*\*\*\*，再单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2fc87-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="2fc87-134">对于“域名(或 FQDN):”\*\*\*\*，输入域，为以下每个域重复此过程：</span><span class="sxs-lookup"><span data-stu-id="2fc87-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
   - <span data-ttu-id="2fc87-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="2fc87-135">noammeetings.lync.com</span></span>
    
   - <span data-ttu-id="2fc87-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="2fc87-136">emeameetings.lync.com</span></span>
    
   - <span data-ttu-id="2fc87-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="2fc87-137">apacmeetings.lync.com</span></span>
    
   - <span data-ttu-id="2fc87-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="2fc87-138">resources.lync.com</span></span>
    
<span data-ttu-id="2fc87-139">您还可以通过运行以下 cmdlet 中的 Skype 业务 Server 命令行管理程序配置 SIP 联盟域的外部访问：</span><span class="sxs-lookup"><span data-stu-id="2fc87-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="2fc87-140">已完成这些配置步骤之后，您可以开始部署中使用 Skype 会议广播。</span><span class="sxs-lookup"><span data-stu-id="2fc87-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="2fc87-141">有关 Skype 会议广播的详细信息，请参阅[Skype 会议广播是什么？](https://go.microsoft.com/fwlink/?LinkId=617071)和[Skype 会议广播管理指南](https://go.microsoft.com/fwlink/?LinkId=617075)。</span><span class="sxs-lookup"><span data-stu-id="2fc87-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  

