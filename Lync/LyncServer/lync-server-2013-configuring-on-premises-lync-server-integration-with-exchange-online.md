---
title: 配置本地 Lync Server 与 Exchange Online 的集成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring on-premises Lync Server integration with Exchange Online
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh533880(v=OCS.15)
ms:contentKeyID: 48184900
ms.date: 03/30/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c4900beab738f9aa792919cceec015bb0c3ad0f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a><span data-ttu-id="ff875-102">配置本地 Lync Server 2013 与 Exchange Online 集成</span><span class="sxs-lookup"><span data-stu-id="ff875-102">Configuring on-premises Lync Server 2013 integration with Exchange Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff875-103">_**上次修改的主题：** 2018-03-30_</span><span class="sxs-lookup"><span data-stu-id="ff875-103">_**Topic Last Modified:** 2018-03-30_</span></span>

<span data-ttu-id="ff875-104">使用本地 Lync Server 2013 部署的客户可以在混合部署模式下在 Microsoft Exchange Online 中配置与 Microsoft Outlook Web App 的互操作性。</span><span class="sxs-lookup"><span data-stu-id="ff875-104">Customers who are using on-premises Lync Server 2013 deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="ff875-105">互操作性功能包括单一登录和即时消息（IM）以及与 Outlook Web App 界面的状态集成。</span><span class="sxs-lookup"><span data-stu-id="ff875-105">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="ff875-106">若要启用此集成，您必须完成以下任务，在本地 Lync Server 部署中配置边缘服务器：</span><span class="sxs-lookup"><span data-stu-id="ff875-106">To enable this integration, you must configure the Edge Server in your on-premises Lync Server deployment by completing the following tasks:</span></span>

  - <span data-ttu-id="ff875-107">配置共享 SIP 地址空间</span><span class="sxs-lookup"><span data-stu-id="ff875-107">Configure a shared SIP address space</span></span>

  - <span data-ttu-id="ff875-108">在边缘服务器上配置托管提供程序</span><span class="sxs-lookup"><span data-stu-id="ff875-108">Configure a hosting provider on the Edge Server</span></span>

  - <span data-ttu-id="ff875-109">验证更新的中央管理存储的复制</span><span class="sxs-lookup"><span data-stu-id="ff875-109">Verify replication of the updated Central Management store</span></span>

<span data-ttu-id="ff875-110">如果 Lync Server 2013 与 Exchange Online 集成，则尝试从 OWA 登录 IM 的用户被视为远程用户或外部用户。</span><span class="sxs-lookup"><span data-stu-id="ff875-110">If Lync Server 2013 is integrated with Exchange Online, a user who is trying to sign in to IM from OWA is considered a remote or external user.</span></span> <span data-ttu-id="ff875-111">在这种情况下，必须为此用户分配一个已选择以下选项的外部访问策略：</span><span class="sxs-lookup"><span data-stu-id="ff875-111">In this scenario, this user must have an external access policy assigned that has the following option selected:</span></span>

<span data-ttu-id="ff875-112">**启用与远程用户的通信**</span><span class="sxs-lookup"><span data-stu-id="ff875-112">**Enable communications with remote users**</span></span>

<span data-ttu-id="ff875-113">如果您希望组织中的用户（如正在旅行的远程办公和用户）能够通过 Internet 连接到 Lync Server，请启用此选项。</span><span class="sxs-lookup"><span data-stu-id="ff875-113">Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

<span data-ttu-id="ff875-114">有关详细信息，请参阅[在 Lync Server 2013 中管理外部访问策略](lync-server-2013-manage-external-access-policy-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="ff875-114">For more information, see [Manage external access policy in Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).</span></span>

<div>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="ff875-115">配置共享 SIP 地址空间</span><span class="sxs-lookup"><span data-stu-id="ff875-115">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="ff875-116">若要将本地 Lync Server 2013 与 Exchange Online 集成，必须配置共享 SIP 地址空间。</span><span class="sxs-lookup"><span data-stu-id="ff875-116">To integrate on-premises Lync Server 2013 with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="ff875-117">Lync Server 和 Exchange Online 服务均支持相同的 SIP 域地址空间。</span><span class="sxs-lookup"><span data-stu-id="ff875-117">The same SIP domain address space is supported by both Lync Server and the Exchange Online service.</span></span>

<span data-ttu-id="ff875-118">使用 Lync Server 命令行管理程序，使用以下示例中显示的参数运行**set-csaccessedgeconfiguration** cmdlet，从而配置边缘服务器以进行联合身份验证：</span><span class="sxs-lookup"><span data-stu-id="ff875-118">Using the Lync Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters that are displayed in the following example:</span></span>

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - <span data-ttu-id="ff875-119">**AllowFederatedUsers** 指定是否允许内部用户与来自联盟域的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="ff875-119">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="ff875-120">此属性还确定内部用户是否可以使用 Lync Server 和 Exchange Online 与共享 SIP 地址空间方案中的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="ff875-120">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Lync Server and Exchange Online.</span></span>

<span data-ttu-id="ff875-121">有关如何使用 Lync Server 命令行管理程序的详细信息，请参阅[Lync server 2013 命令行管理](lync-server-2013-lync-server-management-shell.md)程序。</span><span class="sxs-lookup"><span data-stu-id="ff875-121">For details about how to use the Lync Server Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="ff875-122">在边缘服务器上配置托管提供程序</span><span class="sxs-lookup"><span data-stu-id="ff875-122">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="ff875-123">使用 Lync Server 命令行管理程序在边缘服务器上配置托管提供程序。</span><span class="sxs-lookup"><span data-stu-id="ff875-123">Use the Lync Server Management Shell to configure a hosting provider on the Edge Server.</span></span> <span data-ttu-id="ff875-124">为此，请使用以下示例中的参数运行**CsHostingProvider** cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ff875-124">To do this, run the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> <span data-ttu-id="ff875-125">如果使用由世纪互联运营的 Office 365，请将此示例（"exap.um.outlook.com"）中的<STRONG>ProxyFqdn</STRONG>参数的值替换为由世纪互联运营的服务的 FQDN： "exap.um.partner.outlook.cn"。</span><span class="sxs-lookup"><span data-stu-id="ff875-125">If you are using Office 365 operated by 21Vianet in China, replace the value for the <STRONG>ProxyFqdn</STRONG> parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span>



</div>

  - <span data-ttu-id="ff875-126">**Identity**为要创建的宿主提供程序指定唯一的字符串值标识符（例如，"Exchange Online"）。</span><span class="sxs-lookup"><span data-stu-id="ff875-126">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="ff875-127">包含空格的值必须用双引号引起来。</span><span class="sxs-lookup"><span data-stu-id="ff875-127">Values that contain spaces must be in double quotation marks.</span></span>

  - <span data-ttu-id="ff875-128">**Enabled** 指示您的域与承载服务提供商之间的网络连接是否已启用。</span><span class="sxs-lookup"><span data-stu-id="ff875-128">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="ff875-129">必须将其设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="ff875-129">This must be set to **True**.</span></span>

  - <span data-ttu-id="ff875-130">**EnabledSharedAddressSpace** 指示是否要在共享 SIP 地址空间方案中使用承载服务提供商。</span><span class="sxs-lookup"><span data-stu-id="ff875-130">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="ff875-131">必须将其设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="ff875-131">This must be set to **True**.</span></span>

  - <span data-ttu-id="ff875-132">**HostsOCSUsers**指示承载提供程序是否用于承载 Office 通信服务器或 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="ff875-132">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Lync Server.</span></span> <span data-ttu-id="ff875-133">必须将其设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="ff875-133">This must be set to **False**.</span></span>

  - <span data-ttu-id="ff875-134">**ProxyFQDN** 指定托管服务提供商使用的代理服务器的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="ff875-134">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="ff875-135">对于 Exchange Online，FQDN 为 exap.um.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="ff875-135">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

  - <span data-ttu-id="ff875-136">**IsLocal**指示承载提供程序使用的代理服务器是否包含在你的 Lync server 拓扑中。</span><span class="sxs-lookup"><span data-stu-id="ff875-136">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server topology.</span></span> <span data-ttu-id="ff875-137">必须将其设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="ff875-137">This must be set to **False**.</span></span>

  - <span data-ttu-id="ff875-138">**VerificationLevel**指示对托管提供程序发送和接收的邮件允许的验证级别。</span><span class="sxs-lookup"><span data-stu-id="ff875-138">**VerificationLevel** indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="ff875-139">指定**UseSourceVerification**。</span><span class="sxs-lookup"><span data-stu-id="ff875-139">Specify **UseSourceVerification**.</span></span> <span data-ttu-id="ff875-140">此选项依赖于从托管提供程序发送的邮件中包含的验证级别。</span><span class="sxs-lookup"><span data-stu-id="ff875-140">This option relies on the verification level that is included in messages that are sent from the hosting provider.</span></span> <span data-ttu-id="ff875-141">如果未指定此级别，则邮件将因无法验证而被拒绝。</span><span class="sxs-lookup"><span data-stu-id="ff875-141">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="ff875-142">验证更新的中央管理存储的复制</span><span class="sxs-lookup"><span data-stu-id="ff875-142">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="ff875-143">使用前面各节中的 cmdlet 所做的更改将自动应用于边缘服务器，并且通常需要不到一分钟的时间来进行复制。</span><span class="sxs-lookup"><span data-stu-id="ff875-143">The changes that you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than one minute to replicate.</span></span> <span data-ttu-id="ff875-144">您可以使用以下 cmdlet 验证复制状态以及是否已将更改应用到边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="ff875-144">You can verify the replication status and that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="ff875-145">若要验证 Lync Server 部署中的内部服务器上的复制更新，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ff875-145">To verify replication updates on a server internal in your Lync Server deployment, run the following cmdlet:</span></span>

    Get-CsManagementStoreReplicationStatus

<span data-ttu-id="ff875-146">若要验证是否已应用所做的更改，请在边缘服务器上运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ff875-146">To verify that the changes were applied, run the following cmdlet on the Edge Server:</span></span>

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ff875-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff875-147">See Also</span></span>


[<span data-ttu-id="ff875-148">在托管 Exchange UM 上提供 Lync Server 2013 用户语音邮件</span><span class="sxs-lookup"><span data-stu-id="ff875-148">Providing Lync Server 2013 users voice mail on hosted Exchange UM</span></span>](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[<span data-ttu-id="ff875-149">Lync Server 2013 中的托管 Exchange 统一消息集成</span><span class="sxs-lookup"><span data-stu-id="ff875-149">Hosted Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

