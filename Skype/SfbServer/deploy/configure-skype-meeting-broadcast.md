---
title: 配置 Skype 会议直播本地部署
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
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
description: 摘要： 了解您需要执行配置 Skype 会议广播业务服务器混合部署您的内部部署 Skype 的步骤。
ms.openlocfilehash: e788a263223ea3fa0f4ce9ed844fb5b4eb0ae898
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="e9a36-103">配置 Skype 会议直播本地部署</span><span class="sxs-lookup"><span data-stu-id="e9a36-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="e9a36-104">**摘要：**了解您需要执行配置 Skype 会议广播业务服务器混合部署您的内部部署 Skype 的步骤。</span><span class="sxs-lookup"><span data-stu-id="e9a36-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="e9a36-105">Skype 会议广播是属于 Office 365 的联机服务。</span><span class="sxs-lookup"><span data-stu-id="e9a36-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="e9a36-106">如果正在运行的业务服务器部署 Skype 并且想要在您的环境中使用 Skype 会议广播，您需要按照本主题中的配置步骤。</span><span class="sxs-lookup"><span data-stu-id="e9a36-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="e9a36-107">在开始之前，您的环境需要配置，以混合的 Skype 的在线业务。</span><span class="sxs-lookup"><span data-stu-id="e9a36-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="e9a36-108">有关详细信息，请参阅[规划业务服务器和 Skype 的在线业务 Skype 之间的混合连接](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)和[部署混合来临 Skype 业务服务器和 Skype 的在线业务](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="e9a36-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="e9a36-109">为 Skype 会议广播配置混合环境</span><span class="sxs-lookup"><span data-stu-id="e9a36-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="e9a36-110">您需要执行以下操作来准备您的环境以便使用 Skype 会议广播：</span><span class="sxs-lookup"><span data-stu-id="e9a36-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="e9a36-111">配置联合身份验证与 Skype 业务联机资源</span><span class="sxs-lookup"><span data-stu-id="e9a36-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="e9a36-112">配置 SIP 联盟域</span><span class="sxs-lookup"><span data-stu-id="e9a36-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="e9a36-113">配置联合身份验证与 Skype 业务联机资源</span><span class="sxs-lookup"><span data-stu-id="e9a36-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="e9a36-114">要启用联盟与 Skype 业务联机资源，您需要 SIP 联合提供程序配置的外部访问。</span><span class="sxs-lookup"><span data-stu-id="e9a36-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="e9a36-115">为此通过 Skype 业务服务器控件面板执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e9a36-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="e9a36-116">启动 Skype 业务服务器的控制面板，选择左侧的**外部访问**。</span><span class="sxs-lookup"><span data-stu-id="e9a36-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="e9a36-117">选择“SIP 联盟提供程序”****，再单击“新建”****。</span><span class="sxs-lookup"><span data-stu-id="e9a36-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="e9a36-118">使用以下设置配置新的提供程序：</span><span class="sxs-lookup"><span data-stu-id="e9a36-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="e9a36-119">**启用与此提供程序进行通信：**</span><span class="sxs-lookup"><span data-stu-id="e9a36-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="e9a36-120">选中</span><span class="sxs-lookup"><span data-stu-id="e9a36-120">Selected</span></span>  <br/> |
|<span data-ttu-id="e9a36-121">**提供程序名称:**</span><span class="sxs-lookup"><span data-stu-id="e9a36-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="e9a36-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="e9a36-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="e9a36-123">**访问边缘服务(FQDN):**</span><span class="sxs-lookup"><span data-stu-id="e9a36-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="e9a36-124">sipfed.resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="e9a36-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="e9a36-125">**默认验证级别:**</span><span class="sxs-lookup"><span data-stu-id="e9a36-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="e9a36-126">允许用户与使用此提供程序的每个人通信。</span><span class="sxs-lookup"><span data-stu-id="e9a36-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="e9a36-127">您还可以通过 Skype 在运行以下 cmdlet 业务服务器管理外壳程序启用联盟与 Skype 业务联机资源：</span><span class="sxs-lookup"><span data-stu-id="e9a36-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="e9a36-128">配置 SIP 联盟域</span><span class="sxs-lookup"><span data-stu-id="e9a36-128">Configure SIP federated domains</span></span>

<span data-ttu-id="e9a36-129">接下来，您需要将 SIP 的联盟域添加到允许的域列表。</span><span class="sxs-lookup"><span data-stu-id="e9a36-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="e9a36-130">对列出的每个域重复这些步骤，创建 4 个新的 SIP 联盟域。</span><span class="sxs-lookup"><span data-stu-id="e9a36-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="e9a36-131">这些域包含对于区域数据中心中使用的 Skype 的在线业务。</span><span class="sxs-lookup"><span data-stu-id="e9a36-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="e9a36-132">启动 Skype 业务服务器的控制面板，选择左侧的**外部访问**。</span><span class="sxs-lookup"><span data-stu-id="e9a36-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="e9a36-133">选择“SIP 联盟域”****，再单击“新建”****。</span><span class="sxs-lookup"><span data-stu-id="e9a36-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="e9a36-134">对于“域名(或 FQDN):”****，输入域，为以下每个域重复此过程：</span><span class="sxs-lookup"><span data-stu-id="e9a36-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
  - <span data-ttu-id="e9a36-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="e9a36-135">noammeetings.lync.com</span></span>
    
  - <span data-ttu-id="e9a36-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="e9a36-136">emeameetings.lync.com</span></span>
    
  - <span data-ttu-id="e9a36-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="e9a36-137">apacmeetings.lync.com</span></span>
    
  - <span data-ttu-id="e9a36-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="e9a36-138">resources.lync.com</span></span>
    
<span data-ttu-id="e9a36-139">您还可以通过 Skype 在运行以下 cmdlet 业务服务器管理外壳配置联合的 SIP 域的外部访问权限：</span><span class="sxs-lookup"><span data-stu-id="e9a36-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```
New-CsAllowedDomain -Identity "noammeetings.lync.com"
```

```
New-CsAllowedDomain -Identity "emeameetings.lync.com"
```

```
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
```

```
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="e9a36-140">当您完成这些配置步骤可以开始在部署时使用 Skype 会议广播。</span><span class="sxs-lookup"><span data-stu-id="e9a36-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="e9a36-141">关于 Skype 会议广播的详细信息，请参阅[是 Skype 会议广播什么？](https://go.microsoft.com/fwlink/?LinkId=617071)和[Skype 会议广播管理员指南 》](https://go.microsoft.com/fwlink/?LinkId=617075)。</span><span class="sxs-lookup"><span data-stu-id="e9a36-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  

