---
title: 为 Skype 会议直播配置本地部署
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 摘要：了解为本地 Skype for Business Server 混合部署配置 Skype 会议直播需要执行的步骤。
ms.openlocfilehash: b70272ee90146bdac87264acf0c7673b8def05c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103688"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="333ba-103">为 Skype 会议直播配置本地部署</span><span class="sxs-lookup"><span data-stu-id="333ba-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="333ba-104">**摘要：** 了解为本地 Skype for Business Server 混合部署配置 Skype 会议直播需要执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="333ba-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="333ba-105">Skype 会议广播是一项在线服务，属于 Office 365。</span><span class="sxs-lookup"><span data-stu-id="333ba-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="333ba-106">如果你正在本地运行 Skype for Business Server，并且想要在你的环境中使用 Skype 会议直播，则需要遵循本主题中的配置步骤。</span><span class="sxs-lookup"><span data-stu-id="333ba-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="333ba-107">开始之前，需要将环境配置为与 Skype for Business Online 进行混合。</span><span class="sxs-lookup"><span data-stu-id="333ba-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="333ba-108">有关详细信息，请参阅 Plan [hybrid connectivity between Skype for Business Server and Skype for Business Online](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) 和 Deploy hybrid connectivity between Skype for Business Server and Skype for Business [Online](../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)。</span><span class="sxs-lookup"><span data-stu-id="333ba-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="333ba-109">为 Skype 会议直播配置混合环境</span><span class="sxs-lookup"><span data-stu-id="333ba-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="333ba-110">你需要执行以下操作来为 Skype 会议直播准备你的环境：</span><span class="sxs-lookup"><span data-stu-id="333ba-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="333ba-111">配置与 Skype for Business Online 资源的联盟</span><span class="sxs-lookup"><span data-stu-id="333ba-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="333ba-112">配置 SIP 联盟域</span><span class="sxs-lookup"><span data-stu-id="333ba-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="333ba-113">配置与 Skype for Business Online 资源的联盟</span><span class="sxs-lookup"><span data-stu-id="333ba-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="333ba-114">要启用与 Skype for Business Online 资源的联盟，需要为 SIP 联盟提供程序配置外部访问。</span><span class="sxs-lookup"><span data-stu-id="333ba-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="333ba-115">若要使用 Skype for Business Server 控制面板完成此操作，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="333ba-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="333ba-116">启动 Skype for Business Server 控制面板，然后选择 **左侧的"外部** 访问"。</span><span class="sxs-lookup"><span data-stu-id="333ba-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="333ba-117">选择 **"SIP 联盟提供程序"，** 然后单击"新建 **"。**</span><span class="sxs-lookup"><span data-stu-id="333ba-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="333ba-118">使用下列设置配置新提供程序：</span><span class="sxs-lookup"><span data-stu-id="333ba-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="333ba-119">**启用与此提供商的通信：**</span><span class="sxs-lookup"><span data-stu-id="333ba-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="333ba-120">已选定</span><span class="sxs-lookup"><span data-stu-id="333ba-120">Selected</span></span>  <br/> |
|<span data-ttu-id="333ba-121">**提供程序名称：**</span><span class="sxs-lookup"><span data-stu-id="333ba-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="333ba-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="333ba-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="333ba-123">**访问边缘服务 (FQDN) ：**</span><span class="sxs-lookup"><span data-stu-id="333ba-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="333ba-124">sipfed.resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="333ba-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="333ba-125">**默认验证级别：**</span><span class="sxs-lookup"><span data-stu-id="333ba-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="333ba-126">允许用户使用此提供程序与所有人通信。</span><span class="sxs-lookup"><span data-stu-id="333ba-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="333ba-127">还可以在 Skype for Business Server 命令行管理程序 中运行以下 cmdlet，以启用与 Skype for Business Online 资源的联盟：</span><span class="sxs-lookup"><span data-stu-id="333ba-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="333ba-128">配置 SIP 联盟域</span><span class="sxs-lookup"><span data-stu-id="333ba-128">Configure SIP federated domains</span></span>

<span data-ttu-id="333ba-129">接下来，您需要将 SIP 联盟域添加到允许的域列表中。</span><span class="sxs-lookup"><span data-stu-id="333ba-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="333ba-130">对列出的每个域重复这些步骤，创建 4 个新的 SIP 联盟域。</span><span class="sxs-lookup"><span data-stu-id="333ba-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="333ba-131">这些域包括用于 Skype for Business Online 中使用的区域数据中心。</span><span class="sxs-lookup"><span data-stu-id="333ba-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="333ba-132">启动 Skype for Business Server 控制面板，然后选择 **左侧的"外部** 访问"。</span><span class="sxs-lookup"><span data-stu-id="333ba-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="333ba-133">选择 **"SIP 联盟域"，** 然后单击"新建 **"。**</span><span class="sxs-lookup"><span data-stu-id="333ba-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="333ba-134">对于 **"域名 (FQDN) ：**"，输入域，对以下每个域重复此过程：</span><span class="sxs-lookup"><span data-stu-id="333ba-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
   - <span data-ttu-id="333ba-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="333ba-135">noammeetings.lync.com</span></span>
    
   - <span data-ttu-id="333ba-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="333ba-136">emeameetings.lync.com</span></span>
    
   - <span data-ttu-id="333ba-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="333ba-137">apacmeetings.lync.com</span></span>
    
   - <span data-ttu-id="333ba-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="333ba-138">resources.lync.com</span></span>
    
<span data-ttu-id="333ba-139">您还可以在 Skype for Business Server 命令行管理程序 中运行以下 cmdlet，为 SIP 联盟域配置外部访问：</span><span class="sxs-lookup"><span data-stu-id="333ba-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="333ba-140">完成这些配置步骤后，就可以开始在部署中使用 Skype 会议直播。</span><span class="sxs-lookup"><span data-stu-id="333ba-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="333ba-141">有关 Skype 会议直播详细信息，请参阅 [什么是 Skype 会议直播？](https://go.microsoft.com/fwlink/?LinkId=617071) 和 [Skype 会议直播管理指南](../../SfbOnline/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md)。</span><span class="sxs-lookup"><span data-stu-id="333ba-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](../../SfbOnline/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md).</span></span>
