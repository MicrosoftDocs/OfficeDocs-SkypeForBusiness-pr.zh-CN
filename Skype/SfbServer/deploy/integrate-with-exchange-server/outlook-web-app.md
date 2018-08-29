---
title: 配置业务服务器的内部部署 Skype 和 Outlook Web App 之间的集成
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
description: 摘要： 将 Skype 集成的企业服务器和 Outlook Web App。
ms.openlocfilehash: 63533e0f592a332e1e5f4ff9829b16cde4b1299f
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2018
ms.locfileid: "23263919"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a><span data-ttu-id="176ef-103">配置业务服务器的内部部署 Skype 和 Outlook Web App 之间的集成</span><span class="sxs-lookup"><span data-stu-id="176ef-103">Configure integration between on-premises Skype for Business Server and Outlook Web App</span></span>

<span data-ttu-id="176ef-104">**摘要：** 将 Skype 集成的企业服务器和 Outlook Web App。</span><span class="sxs-lookup"><span data-stu-id="176ef-104">**Summary:** Integrate Skype for Business Server and Outlook Web App.</span></span>

<span data-ttu-id="176ef-105">使用本地 Skype 业务服务器部署的客户可在混合部署模式下可以配置与 Microsoft Exchange Online 中的 Microsoft Outlook Web App 互操作性。</span><span class="sxs-lookup"><span data-stu-id="176ef-105">Customers who are using on-premises Skype for Business Server deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="176ef-106">互操作性功能包括单一登录和即时消息 (IM) 以及与 Outlook Web App 接口的状态集成。</span><span class="sxs-lookup"><span data-stu-id="176ef-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="176ef-107">若要启用此集成，您必须通过完成以下任务在您的本地 Skype 业务服务器部署中配置边缘服务器：</span><span class="sxs-lookup"><span data-stu-id="176ef-107">To enable this integration, you must configure the Edge Server in your on-premises Skype for Business Server deployment by completing the following tasks:</span></span>

- <span data-ttu-id="176ef-108">配置共享的 SIP 地址空间</span><span class="sxs-lookup"><span data-stu-id="176ef-108">Configure a shared SIP address space</span></span>

- <span data-ttu-id="176ef-109">边缘服务器上配置宿主提供商</span><span class="sxs-lookup"><span data-stu-id="176ef-109">Configure a hosting provider on the Edge Server</span></span>

- <span data-ttu-id="176ef-110">验证复制更新后的中央管理存储</span><span class="sxs-lookup"><span data-stu-id="176ef-110">Verify replication of the updated Central Management store</span></span>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="176ef-111">配置共享的 SIP 地址空间</span><span class="sxs-lookup"><span data-stu-id="176ef-111">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="176ef-112">若要将内部部署 Skype 集成业务 server 与 Exchange Online，必须配置共享的 SIP 地址空间。</span><span class="sxs-lookup"><span data-stu-id="176ef-112">To integrate on-premises Skype for Business Server with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="176ef-113">Skype 业务 server 和 Exchange Online 服务支持相同的 SIP 域地址空间。</span><span class="sxs-lookup"><span data-stu-id="176ef-113">The same SIP domain address space is supported by both Skype for Business Server and the Exchange Online service.</span></span>

<span data-ttu-id="176ef-114">使用 Skype 业务 Server 命令行管理程序，通过运行**Set-csaccessedgeconfiguration** cmdlet，使用下面的示例中显示的参数配置边缘服务器联盟：</span><span class="sxs-lookup"><span data-stu-id="176ef-114">Using the Skype for Business Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters displayed in the following example:</span></span>

```
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- <span data-ttu-id="176ef-115">**AllowFederatedUsers**参数指定是否允许内部用户与联盟域中的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="176ef-115">**AllowFederatedUsers** parameter specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="176ef-116">此属性还决定内部用户可以与 Skype 的共享 SIP 地址空间情况用户 Business Server 和 Exchange Online 的通信。</span><span class="sxs-lookup"><span data-stu-id="176ef-116">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Skype for Business Server and Exchange Online.</span></span>

<span data-ttu-id="176ef-117">有关为业务 Server 命令行管理程序中使用 Skype 的详细信息，请参阅[Business Server Management Shell 的 Skype](../../manage/management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="176ef-117">For details about using the Skype for Business Server Management Shell, see [Skype for Business Server Management Shell](../../manage/management-shell.md).</span></span>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="176ef-118">在边缘服务器上配置宿主提供程序</span><span class="sxs-lookup"><span data-stu-id="176ef-118">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="176ef-119">使用 Skype 业务 Server 命令行管理程序，以边缘服务器上配置宿主提供商，通过运行**New-cshostingprovider** cmdlet，使用下面的示例中的参数：</span><span class="sxs-lookup"><span data-stu-id="176ef-119">Using the Skype for Business Server Management Shell, configure a hosting provider on the Edge Server by running the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> <span data-ttu-id="176ef-120">如果您在中国使用 21Vianet 运营的 Office 365，请将此示例中 ProxyFqdn 参数的值（“exap.um.outlook.com”）替换为 21Vianet 运营的服务的 FQDN：“exap.um.partner.outlook.cn”。</span><span class="sxs-lookup"><span data-stu-id="176ef-120">If you are using Office 365 operated by 21Vianet in China, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span> <span data-ttu-id="176ef-121">如果您使用 Office 365 GCC 高，值替换 ProxyFqdn 参数在本示例中 ("exap.um.outlook.com") 的 FQDN 为 GCC 高:"exap.um.office365.us"。</span><span class="sxs-lookup"><span data-stu-id="176ef-121">If you are using Office 365 GCC High, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for GCC High: “exap.um.office365.us”.</span></span>

- <span data-ttu-id="176ef-122">**标识**要创建 （例如，"Exchange Online"） 的宿主提供商指定唯一的字符串值标识符。</span><span class="sxs-lookup"><span data-stu-id="176ef-122">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="176ef-123">包含空格的值必须用双引号括起来。</span><span class="sxs-lookup"><span data-stu-id="176ef-123">Values that contain spaces must be in double quotes.</span></span>

- <span data-ttu-id="176ef-124">**Enabled ** 指示您的域与承载服务提供商之间的网络连接是否已启用。</span><span class="sxs-lookup"><span data-stu-id="176ef-124">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="176ef-125">必须将其设置为 True。</span><span class="sxs-lookup"><span data-stu-id="176ef-125">This must be set to True.</span></span>

- <span data-ttu-id="176ef-126">**EnabledSharedAddressSpace**指示是否将共享 SIP 地址空间方案中使用的宿主提供商。</span><span class="sxs-lookup"><span data-stu-id="176ef-126">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="176ef-127">必须将其设置为 True。</span><span class="sxs-lookup"><span data-stu-id="176ef-127">This must be set to True.</span></span>

- <span data-ttu-id="176ef-128">**HostsOCSUsers**指示承载服务提供商是否用于承载 Office Communications Server 或 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="176ef-128">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Skype for Business Server.</span></span> <span data-ttu-id="176ef-129">必须将其设置为 False。</span><span class="sxs-lookup"><span data-stu-id="176ef-129">This must be set to False.</span></span>

- <span data-ttu-id="176ef-130">**ProxyFQDN**指定的宿主提供商使用的代理服务器的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="176ef-130">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="176ef-131">对于 Exchange Online，FQDN 为 exap.um.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="176ef-131">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

- <span data-ttu-id="176ef-132">**IsLocal**指示承载服务提供商使用的代理服务器是否包含您 Skype 企业服务器拓扑中。</span><span class="sxs-lookup"><span data-stu-id="176ef-132">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="176ef-133">必须将其设置为 False。</span><span class="sxs-lookup"><span data-stu-id="176ef-133">This must be set to False.</span></span>

- <span data-ttu-id="176ef-134">**VerificationLevel**指示允许与宿主提供程序发送的邮件的验证级别。</span><span class="sxs-lookup"><span data-stu-id="176ef-134">**VerificationLevel** Indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="176ef-135">指定**UseSourceVerification**，它依赖于从托管服务提供商发送的消息中包括的验证级别。</span><span class="sxs-lookup"><span data-stu-id="176ef-135">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="176ef-136">如果未指定此级别，则邮件将被拒绝为无法验证。</span><span class="sxs-lookup"><span data-stu-id="176ef-136">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="176ef-137">确保复制更新后的中央管理存储</span><span class="sxs-lookup"><span data-stu-id="176ef-137">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="176ef-138">使用 cmdlet 上述各节中所做的更改会自动应用到边缘服务器，并通常执行小于分钟时间才能复制。</span><span class="sxs-lookup"><span data-stu-id="176ef-138">The changes you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than a minute to replicate.</span></span> <span data-ttu-id="176ef-139">您可以验证复制状态，并确认已应用更改到边缘服务器使用以下 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="176ef-139">You can validate replication status, and then confirm that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="176ef-140">若要验证复制更新，在您 Skype 业务服务器部署中的内部服务器上运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="176ef-140">To verify replication updates, on a server internal in your Skype for Business Server deployment, run the following cmdlet:</span></span>

```
Get-CsManagementStoreReplicationStatus
```

<span data-ttu-id="176ef-141">若要确认已应用所做的更改，在边缘服务器上，运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="176ef-141">To confirm that the changes were applied, on the Edge Server, run the following cmdlet:</span></span>

```
Get-CsHostingProvider -LocalStore
```

## <a name="see-also"></a><span data-ttu-id="176ef-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="176ef-142">See also</span></span>

[<span data-ttu-id="176ef-143">为业务服务器提供 Skype 用户语音邮件上承载的 Exchange UM</span><span class="sxs-lookup"><span data-stu-id="176ef-143">Providing Skype for Business Server users voice mail on hosted Exchange UM</span></span>](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[<span data-ttu-id="176ef-144">托管的 Exchange 统一消息集成在 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="176ef-144">Hosted Exchange Unified Messaging integration in Skype for Business Server</span></span>](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)