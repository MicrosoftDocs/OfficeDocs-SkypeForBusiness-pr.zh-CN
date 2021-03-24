---
title: 配置本地 Skype for Business Server 与 Outlook Web App
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: daa9430034d82a3a8dee980a9b075b2fc5656c86
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109688"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a><span data-ttu-id="245f4-103">配置本地 Skype for Business Server 与 Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="245f4-103">Configure integration between on-premises Skype for Business Server and Outlook Web App</span></span>

<span data-ttu-id="245f4-104">**摘要：** 集成 Skype for Business Server 和 Outlook Web App。</span><span class="sxs-lookup"><span data-stu-id="245f4-104">**Summary:** Integrate Skype for Business Server and Outlook Web App.</span></span>

<span data-ttu-id="245f4-105">使用本地 Skype for Business Server 部署的客户可以在混合部署模式下Outlook Web App配置与 Microsoft Microsoft Exchange Online 的互操作性。</span><span class="sxs-lookup"><span data-stu-id="245f4-105">Customers who are using on-premises Skype for Business Server deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="245f4-106">互操作性功能包括单一登录和即时消息 (IM) 以及状态与 Outlook Web App 接口集成。</span><span class="sxs-lookup"><span data-stu-id="245f4-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="245f4-107">要启用此集成，必须通过完成以下任务在本地 Skype for Business Server 部署中配置边缘服务器：</span><span class="sxs-lookup"><span data-stu-id="245f4-107">To enable this integration, you must configure the Edge Server in your on-premises Skype for Business Server deployment by completing the following tasks:</span></span>

- <span data-ttu-id="245f4-108">配置共享 SIP 地址空间</span><span class="sxs-lookup"><span data-stu-id="245f4-108">Configure a shared SIP address space</span></span>

- <span data-ttu-id="245f4-109">在边缘服务器上配置宿主提供商</span><span class="sxs-lookup"><span data-stu-id="245f4-109">Configure a hosting provider on the Edge Server</span></span>

- <span data-ttu-id="245f4-110">验证更新的中央管理存储的复制</span><span class="sxs-lookup"><span data-stu-id="245f4-110">Verify replication of the updated Central Management store</span></span>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="245f4-111">配置共享 SIP 地址空间</span><span class="sxs-lookup"><span data-stu-id="245f4-111">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="245f4-112">若要将本地 Skype for Business Server 与 Exchange Online 集成，必须配置共享 SIP 地址空间。</span><span class="sxs-lookup"><span data-stu-id="245f4-112">To integrate on-premises Skype for Business Server with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="245f4-113">Skype for Business Server 和 Exchange Online 服务都支持相同的 SIP 域地址空间。</span><span class="sxs-lookup"><span data-stu-id="245f4-113">The same SIP domain address space is supported by both Skype for Business Server and the Exchange Online service.</span></span>

<span data-ttu-id="245f4-114">使用 Skype for Business Server 命令行管理程序，使用以下示例中显示的参数运行 **Set-CSAccessEdgeConfiguration** cmdlet，为联盟配置边缘服务器：</span><span class="sxs-lookup"><span data-stu-id="245f4-114">Using the Skype for Business Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters displayed in the following example:</span></span>

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- <span data-ttu-id="245f4-115">**AllowFederatedUsers** 参数指定是否允许内部用户与联盟域中的用户通信。</span><span class="sxs-lookup"><span data-stu-id="245f4-115">**AllowFederatedUsers** parameter specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="245f4-116">此属性还确定内部用户是否可以与 Skype for Business Server 和 Exchange Online 共享 SIP 地址空间方案中的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="245f4-116">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Skype for Business Server and Exchange Online.</span></span>

<span data-ttu-id="245f4-117">有关使用 Skype for Business Server 命令行管理程序 的详细信息，请参阅 [Skype for Business Server Management Shell](../../manage/management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="245f4-117">For details about using the Skype for Business Server Management Shell, see [Skype for Business Server Management Shell](../../manage/management-shell.md).</span></span>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="245f4-118">在边缘服务器上配置宿主提供商</span><span class="sxs-lookup"><span data-stu-id="245f4-118">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="245f4-119">使用 Skype for Business Server 命令行管理程序，使用以下示例中的参数运行 **New-CsHostingProvider** cmdlet，在边缘服务器上配置宿主提供商：</span><span class="sxs-lookup"><span data-stu-id="245f4-119">Using the Skype for Business Server Management Shell, configure a hosting provider on the Edge Server by running the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> <span data-ttu-id="245f4-120">如果使用的是由世纪银行在中国运营的 Microsoft 365 或 Office 365，请将此示例中 ProxyFqdn 参数的值 ("exap.um.outlook.com") 替换为由世纪银行运营的服务的 FQDN："exap.um.partner.outlook.cn"。</span><span class="sxs-lookup"><span data-stu-id="245f4-120">If you are using Microsoft 365 or Office 365 operated by 21Vianet in China, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span> <span data-ttu-id="245f4-121">如果使用的是 Microsoft 365 或 Office 365 GCC High，请将此示例中 ProxyFqdn 参数的值 ("exap.um.outlook.com") 替换为 GCC High 的 FQDN："exap.um.office365.us"。</span><span class="sxs-lookup"><span data-stu-id="245f4-121">If you are using Microsoft 365 or Office 365 GCC High, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for GCC High: “exap.um.office365.us”.</span></span>

- <span data-ttu-id="245f4-122">**Identity** 为要创建的宿主提供商指定唯一的字符串值标识符 (例如，"Exchange Online") 。</span><span class="sxs-lookup"><span data-stu-id="245f4-122">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="245f4-123">包含空格的值必须用双引号括起来。</span><span class="sxs-lookup"><span data-stu-id="245f4-123">Values that contain spaces must be in double quotes.</span></span>

- <span data-ttu-id="245f4-124">**Enabled** 指示您的域与承载服务提供商之间的网络连接是否已启用。</span><span class="sxs-lookup"><span data-stu-id="245f4-124">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="245f4-125">必须设置为 True。</span><span class="sxs-lookup"><span data-stu-id="245f4-125">This must be set to True.</span></span>

- <span data-ttu-id="245f4-126">**EnabledSharedAddressSpace** 指示是否要在共享 SIP 地址空间方案中使用承载服务提供商。</span><span class="sxs-lookup"><span data-stu-id="245f4-126">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="245f4-127">必须设置为 True。</span><span class="sxs-lookup"><span data-stu-id="245f4-127">This must be set to True.</span></span>

- <span data-ttu-id="245f4-128">**HostsOCSUsers** 指示宿主提供商是用于托管 Office Communications Server 还是 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="245f4-128">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Skype for Business Server.</span></span> <span data-ttu-id="245f4-129">这必须设置为 False。</span><span class="sxs-lookup"><span data-stu-id="245f4-129">This must be set to False.</span></span>

- <span data-ttu-id="245f4-130">**ProxyFQDN** 指定托管服务提供商使用的代理服务器的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="245f4-130">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="245f4-131">对于 Exchange Online，FQDN exap.um.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="245f4-131">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

- <span data-ttu-id="245f4-132">**IsLocal** 指示宿主提供商使用的代理服务器是否包含在 Skype for Business Server 拓扑中。</span><span class="sxs-lookup"><span data-stu-id="245f4-132">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="245f4-133">这必须设置为 False。</span><span class="sxs-lookup"><span data-stu-id="245f4-133">This must be set to False.</span></span>

- <span data-ttu-id="245f4-134">**VerificationLevel** 指示向托管提供程序发送和发送的消息所允许的验证级别。</span><span class="sxs-lookup"><span data-stu-id="245f4-134">**VerificationLevel** Indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="245f4-135">指定 **UseSourceVerification**，它依赖于从宿主提供程序发送的邮件中包含的验证级别。</span><span class="sxs-lookup"><span data-stu-id="245f4-135">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="245f4-136">如果未指定此级别，邮件将因不可验证而被拒绝。</span><span class="sxs-lookup"><span data-stu-id="245f4-136">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="245f4-137">验证更新的中央管理存储的复制</span><span class="sxs-lookup"><span data-stu-id="245f4-137">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="245f4-138">使用上述各节中的 cmdlet 所做的更改会自动应用于边缘服务器，复制通常不到一分钟。</span><span class="sxs-lookup"><span data-stu-id="245f4-138">The changes you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than a minute to replicate.</span></span> <span data-ttu-id="245f4-139">您可以验证复制状态，然后通过以下 cmdlet 确认更改已应用到边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="245f4-139">You can validate replication status, and then confirm that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="245f4-140">要验证复制更新，在 Skype for Business Server 部署中的内部服务器上，运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="245f4-140">To verify replication updates, on a server internal in your Skype for Business Server deployment, run the following cmdlet:</span></span>

```powershell
Get-CsManagementStoreReplicationStatus
```
<span data-ttu-id="245f4-141">检查 UpToDate 值是否显示所有副本的 TRUE。</span><span class="sxs-lookup"><span data-stu-id="245f4-141">Check if UpToDate value is showing TRUE for all Replicas.</span></span>

<span data-ttu-id="245f4-142">若要确认已应用更改，在边缘服务器上运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="245f4-142">To confirm that the changes were applied, on the Edge Server, run the following cmdlet:</span></span>

```powershell
Get-CsHostingProvider -LocalStore
```
<span data-ttu-id="245f4-143">仔细检查显示的信息是否与前面步骤中提交的更改匹配。</span><span class="sxs-lookup"><span data-stu-id="245f4-143">Double check if the information shown matches the changes committed in the previous steps.</span></span>

## <a name="see-also"></a><span data-ttu-id="245f4-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="245f4-144">See also</span></span>

[<span data-ttu-id="245f4-145">在托管 Exchange UM 上提供 Skype for Business Server 用户语音邮件</span><span class="sxs-lookup"><span data-stu-id="245f4-145">Providing Skype for Business Server users voice mail on hosted Exchange UM</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um)

[<span data-ttu-id="245f4-146">Skype for Business Server 中的托管 Exchange 统一消息集成</span><span class="sxs-lookup"><span data-stu-id="245f4-146">Hosted Exchange Unified Messaging integration in Skype for Business Server</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-hosted-exchange-unified-messaging-integration)