---
title: 配置 Outlook Web App 业务服务器 2015年的内部部署 Skype 之间的集成
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/7/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 摘要： 集成业务服务器和 Outlook Web App Skype。
ms.openlocfilehash: 4ac4d6a71f8006e813d09631f8ccf28742940ff2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-2015-and-outlook-web-app"></a><span data-ttu-id="ee7ad-103">配置 Outlook Web App 业务服务器 2015年的内部部署 Skype 之间的集成</span><span class="sxs-lookup"><span data-stu-id="ee7ad-103">Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App</span></span>
 
<span data-ttu-id="ee7ad-104">**摘要：**集成业务服务器和 Outlook Web App，Skype。</span><span class="sxs-lookup"><span data-stu-id="ee7ad-104">**Summary:** Integrate Skype for Business Server and Outlook Web App.</span></span>
  
<span data-ttu-id="ee7ad-105">使用内部部署 Skype 业务服务器 2015年部署的客户可以与 Microsoft Outlook Web App 在 Microsoft Exchange Online 配置互操作性，混合部署模式。</span><span class="sxs-lookup"><span data-stu-id="ee7ad-105">Customers who are using on-premises Skype for Business Server 2015 deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="ee7ad-106">互操作性功能包括单一登录和即时消息 (IM) 以及与 Outlook Web App 接口的状态集成。</span><span class="sxs-lookup"><span data-stu-id="ee7ad-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="ee7ad-107">若要启用此集成，必须配置边缘服务器在您的内部部署 Skype 业务服务器部署通过完成以下任务：</span><span class="sxs-lookup"><span data-stu-id="ee7ad-107">To enable this integration, you must configure the Edge Server in your on-premises Skype for Business Server deployment by completing the following tasks:</span></span> 
  
- <span data-ttu-id="ee7ad-108">配置共享的 SIP 地址空间</span><span class="sxs-lookup"><span data-stu-id="ee7ad-108">Configure a shared SIP address space</span></span>
    
- <span data-ttu-id="ee7ad-109">在边缘服务器上配置宿主提供程序</span><span class="sxs-lookup"><span data-stu-id="ee7ad-109">Configure a hosting provider on the Edge Server</span></span>
    
- <span data-ttu-id="ee7ad-110">验证已更新的中央管理存储的复制</span><span class="sxs-lookup"><span data-stu-id="ee7ad-110">Verify replication of the updated Central Management store</span></span>
    
## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="ee7ad-111">配置共享的 SIP 地址空间</span><span class="sxs-lookup"><span data-stu-id="ee7ad-111">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="ee7ad-112">对于使用 Exchange Online 的业务服务器 2015年集成内部 Skype，您必须配置一个共享的 SIP 地址空间。</span><span class="sxs-lookup"><span data-stu-id="ee7ad-112">To integrate on-premises Skype for Business Server 2015 with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="ee7ad-113">通过 Skype 业务服务器和 Exchange 联机服务支持 SIP 域的同一个地址空间。</span><span class="sxs-lookup"><span data-stu-id="ee7ad-113">The same SIP domain address space is supported by both Skype for Business Server and the Exchange Online service.</span></span>
  
<span data-ttu-id="ee7ad-114">使用 Skype 业务服务器管理外壳，通过运行**一组 CSAccessEdgeConfiguration** cmdlet，使用下面的示例中显示的参数来配置联盟边缘服务器：</span><span class="sxs-lookup"><span data-stu-id="ee7ad-114">Using the Skype for Business Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters displayed in the following example:</span></span>
  
```
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- <span data-ttu-id="ee7ad-115">**AllowFederatedUsers**参数指定是否允许内部用户与来自联盟域的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="ee7ad-115">**AllowFederatedUsers** parameter specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="ee7ad-116">此属性还可确定内部用户可以与用户在共享 SIP 地址空间方案与 Skype 业务服务器和 Exchange 联机通信。</span><span class="sxs-lookup"><span data-stu-id="ee7ad-116">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Skype for Business Server and Exchange Online.</span></span>
    
<span data-ttu-id="ee7ad-117">有关使用 Skype 业务服务器管理程序的详细信息，请参阅[业务服务器 2015年管理外壳的 Skype](../../manage/management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="ee7ad-117">For details about using the Skype for Business Server Management Shell, see [Skype for Business Server 2015 Management Shell](../../manage/management-shell.md).</span></span>
  
## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="ee7ad-118">在边缘服务器上配置宿主提供程序</span><span class="sxs-lookup"><span data-stu-id="ee7ad-118">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="ee7ad-119">使用 Skype 业务服务器管理外壳，配置宿主提供商边缘服务器上运行**新建 CsHostingProvider** cmdlet，在下面的示例中使用的参数：</span><span class="sxs-lookup"><span data-stu-id="ee7ad-119">Using the Skype for Business Server Management Shell, configure a hosting provider on the Edge Server by running the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>
  
```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> <span data-ttu-id="ee7ad-120">如果您在中国使用 21Vianet 运营的 Office 365，请将此示例中 **ProxyFqdn** 参数的值（“exap.um.outlook.com”）替换为 21Vianet 运营的服务的 FQDN：“exap.um.partner.outlook.cn”。</span><span class="sxs-lookup"><span data-stu-id="ee7ad-120">If you are using Office 365 operated by 21Vianet in China, replace the value for the **ProxyFqdn** parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span>
  
- <span data-ttu-id="ee7ad-121">**标识**指定承载提供程序 （例如"Exchange Online"） 所创建的唯一字符串值的标识符。</span><span class="sxs-lookup"><span data-stu-id="ee7ad-121">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="ee7ad-122">包含空格的值必须用双引号括起来。</span><span class="sxs-lookup"><span data-stu-id="ee7ad-122">Values that contain spaces must be in double quotes.</span></span>
    
- <span data-ttu-id="ee7ad-123">**Enabled ** 指示您的域与承载服务提供商之间的网络连接是否已启用。</span><span class="sxs-lookup"><span data-stu-id="ee7ad-123">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="ee7ad-124">必须将其设置为 True。</span><span class="sxs-lookup"><span data-stu-id="ee7ad-124">This must be set to True.</span></span>
    
- <span data-ttu-id="ee7ad-125">**EnabledSharedAddressSpace**表示承载提供程序是否将使用共享的 SIP 地址空间方案中。</span><span class="sxs-lookup"><span data-stu-id="ee7ad-125">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="ee7ad-126">必须将其设置为 True。</span><span class="sxs-lookup"><span data-stu-id="ee7ad-126">This must be set to True.</span></span>
    
- <span data-ttu-id="ee7ad-127">**HostsOCSUsers**表示是否用于承载机构通讯服务器或 Skype 业务服务器承载提供程序。</span><span class="sxs-lookup"><span data-stu-id="ee7ad-127">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Skype for Business Server.</span></span> <span data-ttu-id="ee7ad-128">必须将其设置为 False。</span><span class="sxs-lookup"><span data-stu-id="ee7ad-128">This must be set to False.</span></span>
    
- <span data-ttu-id="ee7ad-129">**ProxyFQDN**指定宿主提供程序使用的代理服务器的完全合格的域名称 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="ee7ad-129">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="ee7ad-130">对于 Exchange Online，FQDN 为 exap.um.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="ee7ad-130">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>
    
- <span data-ttu-id="ee7ad-131">**IsLocal**指示宿主提供程序使用的代理服务器包含在您 Skype 业务服务器拓扑。</span><span class="sxs-lookup"><span data-stu-id="ee7ad-131">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="ee7ad-132">必须将其设置为 False。</span><span class="sxs-lookup"><span data-stu-id="ee7ad-132">This must be set to False.</span></span>
    
- <span data-ttu-id="ee7ad-133">**VerificationLevel**指示与宿主提供程序发送的邮件所允许的验证级别。</span><span class="sxs-lookup"><span data-stu-id="ee7ad-133">**VerificationLevel** Indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="ee7ad-134">指定**UseSourceVerification**，它依赖于宿主提供程序发送的消息中包含的验证级别。</span><span class="sxs-lookup"><span data-stu-id="ee7ad-134">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="ee7ad-135">如果不指定此级别，则消息将被拒绝作为不可验证。</span><span class="sxs-lookup"><span data-stu-id="ee7ad-135">If this level is not specified, the message will be rejected as being unverifiable.</span></span>
    
## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="ee7ad-136">确保复制更新后的中央管理存储</span><span class="sxs-lookup"><span data-stu-id="ee7ad-136">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="ee7ad-137">通过前面章节中使用 cmdlet 所做的更改将自动应用于边缘服务器，并通常花费不到一分钟即可复制。</span><span class="sxs-lookup"><span data-stu-id="ee7ad-137">The changes you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than a minute to replicate.</span></span> <span data-ttu-id="ee7ad-138">您可以验证复制状态并确认到边缘服务器应用了更改，通过使用以下 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ee7ad-138">You can validate replication status, and then confirm that the changes were applied to your Edge Server by using the following cmdlets.</span></span>
  
<span data-ttu-id="ee7ad-139">要验证复制的更新，您的业务服务器部署中，Skype 在内部服务器上运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ee7ad-139">To verify replication updates, on a server internal in your Skype for Business Server deployment, run the following cmdlet:</span></span>
  
```
Get-CsManagementStoreReplicationStatus
```

<span data-ttu-id="ee7ad-140">若要确认已应用所做的更改，在边缘服务器上，运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ee7ad-140">To confirm that the changes were applied, on the Edge Server, run the following cmdlet:</span></span>
  
```
Get-CsHostingProvider -LocalStore
```

## <a name="see-also"></a><span data-ttu-id="ee7ad-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee7ad-141">See also</span></span>

#### 

[<span data-ttu-id="ee7ad-142">提供业务服务器 2015 Skype 用户语音上 UM 承载 Exchange 邮件</span><span class="sxs-lookup"><span data-stu-id="ee7ad-142">Providing Skype for Business Server 2015 users voice mail on hosted Exchange UM</span></span>](http://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)
  
[<span data-ttu-id="ee7ad-143">承载的 Exchange 统一消息集成在 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="ee7ad-143">Hosted Exchange Unified Messaging integration in Skype for Business Server 2015</span></span>](http://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)

