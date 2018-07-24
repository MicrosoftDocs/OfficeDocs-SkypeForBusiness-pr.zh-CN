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
ms.openlocfilehash: 55b7c5c1e97c2e059ead73384ae2914b07d47c4b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21004691"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="19bcc-103">配置 Skype 会议直播本地部署</span><span class="sxs-lookup"><span data-stu-id="19bcc-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="19bcc-104">**摘要：** 了解您需要为您的本地 Skype Business Server 混合部署配置 Skype 会议广播执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="19bcc-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="19bcc-105">Skype 会议广播是为 Office 365 的一部分的联机服务。</span><span class="sxs-lookup"><span data-stu-id="19bcc-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="19bcc-106">如果您的业务 Server 内部部署运行 Skype，并想要在您的环境中使用 Skype 会议广播，您需要按照本主题中的配置步骤。</span><span class="sxs-lookup"><span data-stu-id="19bcc-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="19bcc-107">在开始之前，您的环境需要用来配置混合 Skype 业务 online。</span><span class="sxs-lookup"><span data-stu-id="19bcc-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="19bcc-108">有关详细信息，请参阅[规划 Skype 业务服务器和 Skype 业务 online 之间的混合连接性](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)和[部署业务服务器和 Skype 业务 online Skype 之间的混合连接性](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="19bcc-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="19bcc-109">为会议广播 Skype 配置混合环境</span><span class="sxs-lookup"><span data-stu-id="19bcc-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="19bcc-110">您需要执行以下操作来为 Skype 会议广播准备环境：</span><span class="sxs-lookup"><span data-stu-id="19bcc-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="19bcc-111">配置联合身份验证与 Skype 的业务联机资源</span><span class="sxs-lookup"><span data-stu-id="19bcc-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="19bcc-112">配置 SIP 联盟域</span><span class="sxs-lookup"><span data-stu-id="19bcc-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="19bcc-113">配置联合身份验证与 Skype 的业务联机资源</span><span class="sxs-lookup"><span data-stu-id="19bcc-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="19bcc-114">若要启用的业务联机资源与 Skype 联合身份验证，您需要配置外部访问的 SIP 联盟提供程序。</span><span class="sxs-lookup"><span data-stu-id="19bcc-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="19bcc-115">若要执行此使用适用于业务 Server Control Panel Skype 执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="19bcc-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="19bcc-116">为业务 Server Control Panel 启动 Skype 并选择左侧的**外部访问**。</span><span class="sxs-lookup"><span data-stu-id="19bcc-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="19bcc-117">选择“SIP 联盟提供程序”****，再单击“新建”****。</span><span class="sxs-lookup"><span data-stu-id="19bcc-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="19bcc-118">使用以下设置配置新的提供程序：</span><span class="sxs-lookup"><span data-stu-id="19bcc-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="19bcc-119">**启用与此提供程序通信：**</span><span class="sxs-lookup"><span data-stu-id="19bcc-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="19bcc-120">选中</span><span class="sxs-lookup"><span data-stu-id="19bcc-120">Selected</span></span>  <br/> |
|<span data-ttu-id="19bcc-121">**提供程序名称:**</span><span class="sxs-lookup"><span data-stu-id="19bcc-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="19bcc-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="19bcc-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="19bcc-123">**访问边缘服务(FQDN):**</span><span class="sxs-lookup"><span data-stu-id="19bcc-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="19bcc-124">sipfed.resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="19bcc-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="19bcc-125">**默认验证级别:**</span><span class="sxs-lookup"><span data-stu-id="19bcc-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="19bcc-126">允许用户与使用此提供程序的每个人通信。</span><span class="sxs-lookup"><span data-stu-id="19bcc-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="19bcc-127">您还可以通过运行以下 cmdlet 中 Skype 业务 Server 命令行管理程序启用业务联机资源与 Skype 联合身份的验证：</span><span class="sxs-lookup"><span data-stu-id="19bcc-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="19bcc-128">配置 SIP 联盟域</span><span class="sxs-lookup"><span data-stu-id="19bcc-128">Configure SIP federated domains</span></span>

<span data-ttu-id="19bcc-129">接下来，您需要将 SIP 联盟域添加到允许的域列表。</span><span class="sxs-lookup"><span data-stu-id="19bcc-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="19bcc-130">对列出的每个域重复这些步骤，创建 4 个新的 SIP 联盟域。</span><span class="sxs-lookup"><span data-stu-id="19bcc-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="19bcc-131">包含这些域是的区域数据中心中使用的 Skype 业务联机。</span><span class="sxs-lookup"><span data-stu-id="19bcc-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="19bcc-132">为业务 Server Control Panel 启动 Skype 并选择左侧的**外部访问**。</span><span class="sxs-lookup"><span data-stu-id="19bcc-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="19bcc-133">选择“SIP 联盟域”****，再单击“新建”****。</span><span class="sxs-lookup"><span data-stu-id="19bcc-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="19bcc-134">对于“域名(或 FQDN):”****，输入域，为以下每个域重复此过程：</span><span class="sxs-lookup"><span data-stu-id="19bcc-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
  - <span data-ttu-id="19bcc-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="19bcc-135">noammeetings.lync.com</span></span>
    
  - <span data-ttu-id="19bcc-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="19bcc-136">emeameetings.lync.com</span></span>
    
  - <span data-ttu-id="19bcc-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="19bcc-137">apacmeetings.lync.com</span></span>
    
  - <span data-ttu-id="19bcc-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="19bcc-138">resources.lync.com</span></span>
    
<span data-ttu-id="19bcc-139">您还可以通过运行以下 cmdlet 中的 Skype 业务 Server 命令行管理程序配置 SIP 联盟域的外部访问：</span><span class="sxs-lookup"><span data-stu-id="19bcc-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="19bcc-140">已完成这些配置步骤之后，您可以开始部署中使用 Skype 会议广播。</span><span class="sxs-lookup"><span data-stu-id="19bcc-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="19bcc-141">有关 Skype 会议广播的详细信息，请参阅[Skype 会议广播是什么？](https://go.microsoft.com/fwlink/?LinkId=617071)和[Skype 会议广播管理指南](https://go.microsoft.com/fwlink/?LinkId=617075)。</span><span class="sxs-lookup"><span data-stu-id="19bcc-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  

