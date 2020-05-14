---
title: 配置本地 Skype for Business Server 和 Outlook Web App 之间的集成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 摘要：集成 Skype for Business Server 和 Outlook Web App。
ms.openlocfilehash: ee5676c0dbe88568af78a1c278eea8a46457cb5c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221182"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a><span data-ttu-id="e7e2f-103">配置本地 Skype for Business Server 和 Outlook Web App 之间的集成</span><span class="sxs-lookup"><span data-stu-id="e7e2f-103">Configure integration between on-premises Skype for Business Server and Outlook Web App</span></span>

<span data-ttu-id="e7e2f-104">**摘要：** 集成 Skype for Business Server 和 Outlook Web App。</span><span class="sxs-lookup"><span data-stu-id="e7e2f-104">**Summary:** Integrate Skype for Business Server and Outlook Web App.</span></span>

<span data-ttu-id="e7e2f-105">使用本地 Skype for Business Server 部署的客户可以在混合部署模式下在 Microsoft Exchange Online 中配置与 Microsoft Outlook Web App 的互操作性。</span><span class="sxs-lookup"><span data-stu-id="e7e2f-105">Customers who are using on-premises Skype for Business Server deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="e7e2f-106">互操作性功能包括单一登录和即时消息（IM）以及与 Outlook Web App 界面的状态集成。</span><span class="sxs-lookup"><span data-stu-id="e7e2f-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="e7e2f-107">若要启用此集成，您必须完成以下任务，在本地 Skype for Business Server 部署中配置边缘服务器：</span><span class="sxs-lookup"><span data-stu-id="e7e2f-107">To enable this integration, you must configure the Edge Server in your on-premises Skype for Business Server deployment by completing the following tasks:</span></span>

- <span data-ttu-id="e7e2f-108">配置共享 SIP 地址空间</span><span class="sxs-lookup"><span data-stu-id="e7e2f-108">Configure a shared SIP address space</span></span>

- <span data-ttu-id="e7e2f-109">在边缘服务器上配置托管提供程序</span><span class="sxs-lookup"><span data-stu-id="e7e2f-109">Configure a hosting provider on the Edge Server</span></span>

- <span data-ttu-id="e7e2f-110">验证更新的中央管理存储的复制</span><span class="sxs-lookup"><span data-stu-id="e7e2f-110">Verify replication of the updated Central Management store</span></span>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="e7e2f-111">配置共享 SIP 地址空间</span><span class="sxs-lookup"><span data-stu-id="e7e2f-111">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="e7e2f-112">若要将本地 Skype for Business Server 与 Exchange Online 集成，必须配置共享 SIP 地址空间。</span><span class="sxs-lookup"><span data-stu-id="e7e2f-112">To integrate on-premises Skype for Business Server with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="e7e2f-113">Skype for Business Server 和 Exchange Online 服务均支持相同的 SIP 域地址空间。</span><span class="sxs-lookup"><span data-stu-id="e7e2f-113">The same SIP domain address space is supported by both Skype for Business Server and the Exchange Online service.</span></span>

<span data-ttu-id="e7e2f-114">使用 Skype for Business Server 命令行管理程序，通过运行**set-csaccessedgeconfiguration** cmdlet，使用以下示例中所示的参数来配置联合服务器以进行联盟：</span><span class="sxs-lookup"><span data-stu-id="e7e2f-114">Using the Skype for Business Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters displayed in the following example:</span></span>

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- <span data-ttu-id="e7e2f-115">**AllowFederatedUsers**参数指定是否允许内部用户与联盟域中的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="e7e2f-115">**AllowFederatedUsers** parameter specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="e7e2f-116">此属性还确定内部用户是否可以使用 Skype for Business Server 和 Exchange Online 与共享 SIP 地址空间方案中的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="e7e2f-116">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Skype for Business Server and Exchange Online.</span></span>

<span data-ttu-id="e7e2f-117">有关使用 Skype for Business Server 命令行管理程序的详细信息，请参阅[skype For Business Server 命令行管理](../../manage/management-shell.md)程序。</span><span class="sxs-lookup"><span data-stu-id="e7e2f-117">For details about using the Skype for Business Server Management Shell, see [Skype for Business Server Management Shell](../../manage/management-shell.md).</span></span>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="e7e2f-118">在边缘服务器上配置托管提供程序</span><span class="sxs-lookup"><span data-stu-id="e7e2f-118">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="e7e2f-119">使用 Skype for Business Server 命令行管理程序，使用以下示例中的参数运行**CsHostingProvider** cmdlet，在边缘服务器上配置承载提供程序：</span><span class="sxs-lookup"><span data-stu-id="e7e2f-119">Using the Skype for Business Server Management Shell, configure a hosting provider on the Edge Server by running the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> <span data-ttu-id="e7e2f-120">如果使用的是由世纪互联运营的 Microsoft 365 或 Office 365，请将此示例中的 ProxyFqdn 参数的值替换为由世纪互联运营的服务的 FQDN （"exap.um.outlook.com"）： "exap.um.partner.outlook.cn"。</span><span class="sxs-lookup"><span data-stu-id="e7e2f-120">If you are using Microsoft 365 or Office 365 operated by 21Vianet in China, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span> <span data-ttu-id="e7e2f-121">如果使用的是 Microsoft 365 或 Office 365 GCC 高版，请将此示例（"exap.um.outlook.com"）中的 ProxyFqdn 参数的值替换为 "GCC High" 的 FQDN： "exap.um.office365.us"。</span><span class="sxs-lookup"><span data-stu-id="e7e2f-121">If you are using Microsoft 365 or Office 365 GCC High, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for GCC High: “exap.um.office365.us”.</span></span>

- <span data-ttu-id="e7e2f-122">**Identity**为要创建的宿主提供程序指定唯一的字符串值标识符（例如，"Exchange Online"）。</span><span class="sxs-lookup"><span data-stu-id="e7e2f-122">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="e7e2f-123">包含空格的值必须用双引号括起来。</span><span class="sxs-lookup"><span data-stu-id="e7e2f-123">Values that contain spaces must be in double quotes.</span></span>

- <span data-ttu-id="e7e2f-124">**Enabled** 指示您的域与承载服务提供商之间的网络连接是否已启用。</span><span class="sxs-lookup"><span data-stu-id="e7e2f-124">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="e7e2f-125">必须将其设置为 True。</span><span class="sxs-lookup"><span data-stu-id="e7e2f-125">This must be set to True.</span></span>

- <span data-ttu-id="e7e2f-126">**EnabledSharedAddressSpace** 指示是否要在共享 SIP 地址空间方案中使用承载服务提供商。</span><span class="sxs-lookup"><span data-stu-id="e7e2f-126">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="e7e2f-127">必须将其设置为 True。</span><span class="sxs-lookup"><span data-stu-id="e7e2f-127">This must be set to True.</span></span>

- <span data-ttu-id="e7e2f-128">**HostsOCSUsers**指示承载提供程序是否用于承载 Office 通信服务器或 Skype For business server。</span><span class="sxs-lookup"><span data-stu-id="e7e2f-128">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Skype for Business Server.</span></span> <span data-ttu-id="e7e2f-129">必须将其设置为 False。</span><span class="sxs-lookup"><span data-stu-id="e7e2f-129">This must be set to False.</span></span>

- <span data-ttu-id="e7e2f-130">**ProxyFQDN** 指定托管服务提供商使用的代理服务器的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="e7e2f-130">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="e7e2f-131">对于 Exchange Online，FQDN 为 exap.um.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="e7e2f-131">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

- <span data-ttu-id="e7e2f-132">**IsLocal**指示托管提供程序使用的代理服务器是否包含在您的 Skype For business server 拓扑中。</span><span class="sxs-lookup"><span data-stu-id="e7e2f-132">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="e7e2f-133">必须将其设置为 False。</span><span class="sxs-lookup"><span data-stu-id="e7e2f-133">This must be set to False.</span></span>

- <span data-ttu-id="e7e2f-134">**VerificationLevel**指示允许用于发送到托管提供程序的邮件的验证级别。</span><span class="sxs-lookup"><span data-stu-id="e7e2f-134">**VerificationLevel** Indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="e7e2f-135">指定 **UseSourceVerification**，它依赖于从宿主提供程序发送的邮件中包含的验证级别。</span><span class="sxs-lookup"><span data-stu-id="e7e2f-135">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="e7e2f-136">如果未指定此级别，则邮件将因无法验证而被拒绝。</span><span class="sxs-lookup"><span data-stu-id="e7e2f-136">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="e7e2f-137">验证更新的中央管理存储的复制</span><span class="sxs-lookup"><span data-stu-id="e7e2f-137">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="e7e2f-138">使用前面各节中的 cmdlet 所做的更改会自动应用到边缘服务器，并且通常需要的时间不超过一分钟即可进行复制。</span><span class="sxs-lookup"><span data-stu-id="e7e2f-138">The changes you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than a minute to replicate.</span></span> <span data-ttu-id="e7e2f-139">您可以验证复制状态，然后通过使用以下 cmdlet 确认是否已将更改应用到边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="e7e2f-139">You can validate replication status, and then confirm that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="e7e2f-140">若要验证复制更新，请在 Skype for Business Server 内部部署的服务器上运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e7e2f-140">To verify replication updates, on a server internal in your Skype for Business Server deployment, run the following cmdlet:</span></span>

```powershell
Get-CsManagementStoreReplicationStatus
```
<span data-ttu-id="e7e2f-141">检查是否为所有副本显示 UpToDate 值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="e7e2f-141">Check if UpToDate value is showing TRUE for all Replicas.</span></span>

<span data-ttu-id="e7e2f-142">若要确认是否已应用所做的更改，请在边缘服务器上运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e7e2f-142">To confirm that the changes were applied, on the Edge Server, run the following cmdlet:</span></span>

```powershell
Get-CsHostingProvider -LocalStore
```
<span data-ttu-id="e7e2f-143">仔细检查所显示的信息是否与之前步骤中提交的更改相匹配。</span><span class="sxs-lookup"><span data-stu-id="e7e2f-143">Double check if the information shown matches the changes committed in the previous steps.</span></span>

## <a name="see-also"></a><span data-ttu-id="e7e2f-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7e2f-144">See also</span></span>

[<span data-ttu-id="e7e2f-145">在托管 Exchange UM 上为 Skype for business Server 用户提供语音邮件</span><span class="sxs-lookup"><span data-stu-id="e7e2f-145">Providing Skype for Business Server users voice mail on hosted Exchange UM</span></span>](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[<span data-ttu-id="e7e2f-146">Skype for Business Server 中的托管 Exchange 统一消息集成</span><span class="sxs-lookup"><span data-stu-id="e7e2f-146">Hosted Exchange Unified Messaging integration in Skype for Business Server</span></span>](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
