---
title: Lync Server 2013：托管 Exchange UM 集成体系结构
description: Lync Server 2013：托管 Exchange UM 集成体系结构。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM integration architecture
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398067(v=OCS.15)
ms:contentKeyID: 48183222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2399fa421b59a5ea1fd83b1a86225fc12de1f2ca
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552458"
---
# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a><span data-ttu-id="0650a-103">Lync Server 2013 中的托管 Exchange UM 集成体系结构</span><span class="sxs-lookup"><span data-stu-id="0650a-103">Hosted Exchange UM integration architecture in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0650a-104">_**上次修改的主题：** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="0650a-104">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="0650a-105">Lync Server 2013 ExUM 路由应用程序支持与本地 Exchange 统一消息的集成 (UM) 部署，Exchange UM 由服务提供商托管，或二者的组合。</span><span class="sxs-lookup"><span data-stu-id="0650a-105">The Lync Server 2013 ExUM Routing application supports integration with an on-premises Exchange Unified Messaging (UM) deployment, with Exchange UM hosted by a service provider, or with a combination of the two.</span></span> <span data-ttu-id="0650a-106">下图显示了所有这三种可能性。</span><span class="sxs-lookup"><span data-stu-id="0650a-106">The following diagram shows all three possibilities.</span></span>

<span data-ttu-id="0650a-107">**与一个本地 Exchange UM 部署和两个 Exchange 提供商托管的 Exchange UM 集成**</span><span class="sxs-lookup"><span data-stu-id="0650a-107">**Integration with an on-premises Exchange UM deployment and two hosted Exchange providers**</span></span>

<span data-ttu-id="0650a-108">![本地 Lync Server Exchange UM 部署](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "本地 Lync Server Exchange UM 部署")</span><span class="sxs-lookup"><span data-stu-id="0650a-108">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="0650a-109">支持以下模式：</span><span class="sxs-lookup"><span data-stu-id="0650a-109">The following modes are supported:</span></span>

  - <span data-ttu-id="0650a-110">**本地部署：** Lync Server 2013 和 Exchange UM 都部署在企业中的本地服务器上。</span><span class="sxs-lookup"><span data-stu-id="0650a-110">**On-premises deployment:** Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="0650a-111">**跨界部署：** Lync Server 2013 部署在企业内的本地服务器上，Exchange UM 托管在联机服务提供商的设施中，如 Microsoft Exchange Online 数据中心。</span><span class="sxs-lookup"><span data-stu-id="0650a-111">**Cross-premises deployment:** Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="0650a-112">**混合部署：** 你的 Lync Server 2013 部署将一些用户邮箱驻留在企业内的本地 Exchange 服务器上，而某些邮箱驻留在托管 Exchange 服务数据中心中。</span><span class="sxs-lookup"><span data-stu-id="0650a-112">**Mixed deployment:** Your Lync Server 2013 deployment has some user mailboxes homed on local Exchange servers within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0650a-113">混合部署可以用作评估用户或将用户分阶段迁移至托管 Exchange UM 期间的过渡性解决方案，或者，如果选择在转移部分用户后将其他用户的 Exchange UM 服务保留在内部，则可以将混合部署用作永久性解决方案。</span><span class="sxs-lookup"><span data-stu-id="0650a-113">The mixed deployment can be used as a transitional solution during evaluation and phased migration of users to hosted Exchange UM, or a permanent solution if you opt to keep some users’ Exchange UM services on-premises after transferring others.</span></span>

    
    </div>

<div>

## <a name="shared-sip-address-space"></a><span data-ttu-id="0650a-114">共享 SIP 地址空间</span><span class="sxs-lookup"><span data-stu-id="0650a-114">Shared SIP Address Space</span></span>

<span data-ttu-id="0650a-115">若要将 Lync Server 2013 与本地 Exchange UM 部署集成，请授予 Lync Server 2013 读取 Exchange UM Active Directory 域服务对象的权限。</span><span class="sxs-lookup"><span data-stu-id="0650a-115">To integrate Lync Server 2013 with an on-premises Exchange UM deployment, you grant Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects.</span></span> <span data-ttu-id="0650a-116">但是，此方法不适用于与托管 Exchange UM 集成，因为 Lync Server 2013 和 Exchange UM 安装在单独的林中，它们之间没有任何信任关系。</span><span class="sxs-lookup"><span data-stu-id="0650a-116">This approach does not work for integration with hosted Exchange UM, however, because Lync Server 2013 and Exchange UM are installed in separate forests with no trust between them.</span></span>

<span data-ttu-id="0650a-117">若要将 Lync Server 2013 与托管 Exchange UM 集成，必须配置 *共享 SIP 地址空间*。</span><span class="sxs-lookup"><span data-stu-id="0650a-117">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space*.</span></span> <span data-ttu-id="0650a-118">在此配置中，同时对 Lync Server 2013 和托管 Exchange UM 服务提供商提供了相同的 SIP 域地址空间。</span><span class="sxs-lookup"><span data-stu-id="0650a-118">In this configuration, the same SIP domain address space is available to both Lync Server 2013 and the hosted Exchange UM service provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0650a-119">共享 SIP 地址空间的使用类似于跨界 Lync Server 2013 环境中使用的方法，其中某些用户驻留在本地部署中，一些用户驻留在托管部署 (如 Lync Online) 中。</span><span class="sxs-lookup"><span data-stu-id="0650a-119">Use of the shared SIP address space is similar to the approach used in a cross-premises Lync Server 2013 environment, in which some users are homed in the on-premises deployment and some are homed in a hosted deployment (such as Lync Online).</span></span> <span data-ttu-id="0650a-120">在它们之间对 SIP 域进行了拆分。</span><span class="sxs-lookup"><span data-stu-id="0650a-120">The SIP domain is split between them.</span></span> <span data-ttu-id="0650a-121">将 Lync Server 2013 与托管 Exchange UM 集成时，请确保在共享 SIP 地址空间中包含 Exchange UM 服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="0650a-121">When you integrate Lync Server 2013 with hosted Exchange UM, ensure that you include the Exchange UM service provider in the shared SIP address space.</span></span>



</div>

<span data-ttu-id="0650a-122">要将共享 SIP 地址空间配置为与 Exchange UM 服务提供商集成，需要按下面所示配置边缘服务器：</span><span class="sxs-lookup"><span data-stu-id="0650a-122">To configure the shared SIP address space for integrating with an Exchange UM service provider, you need to configure your Edge Server as follows:</span></span>

1.  <span data-ttu-id="0650a-123">通过运行 **Set-CsAccessEdgeConfiguration** cmdlet 设置以下参数，为联盟配置边缘服务器：</span><span class="sxs-lookup"><span data-stu-id="0650a-123">Configure the Edge Server for federation by running the **Set-CsAccessEdgeConfiguration** cmdlet to set the following parameters:</span></span>
    
      - <span data-ttu-id="0650a-124">**UseDnsSrvRouting** 指定发送和接收联盟请求时，边缘服务器将依赖 DNS SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="0650a-124">**UseDnsSrvRouting** specifies that Edge Servers will rely on DNS SRV records when sending and receiving federation requests.</span></span>
    
      - <span data-ttu-id="0650a-p105">**AllowFederatedUsers** 指定是否允许内部用户与来自联盟域的用户进行通信。此属性也可以确定内部用户是否可以与拆分域方案中的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="0650a-p105">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains. This property also determines whether internal users can communicate with users in a split domain scenario.</span></span>
    
      - <span data-ttu-id="0650a-127">**EnablePartnerDiscovery** 指定 Lync Server 2013 是否将使用 DNS 记录来尝试发现未在 Active Directory 允许的域列表中列出的合作伙伴域。</span><span class="sxs-lookup"><span data-stu-id="0650a-127">**EnablePartnerDiscovery** specifies whether Lync Server 2013 will use DNS records to try to discover partner domains that are not listed in the Active Directory allowed domains list.</span></span> <span data-ttu-id="0650a-128">如果为 False，Lync Server 2013 将仅与在允许的域列表中找到的域联合。</span><span class="sxs-lookup"><span data-stu-id="0650a-128">If False, Lync Server 2013 will federate only with domains that are found on the allowed domains list.</span></span> <span data-ttu-id="0650a-129">如果使用 DNS 服务路由，则需要此参数。</span><span class="sxs-lookup"><span data-stu-id="0650a-129">This parameter is required if you use DNS service routing.</span></span> <span data-ttu-id="0650a-130">在大多数部署中，值会设置为 False，以避免向所有合作伙伴打开联盟。</span><span class="sxs-lookup"><span data-stu-id="0650a-130">In most deployments, the value is set to false to avoid opening up federation to all partners.</span></span>

2.  <span data-ttu-id="0650a-131">将中央管理存储复制到边缘服务器并验证复制。</span><span class="sxs-lookup"><span data-stu-id="0650a-131">Replicate the Central Management store to the Edge Server and verify the replication.</span></span> <span data-ttu-id="0650a-132">有关详细信息，请参阅部署文档中的 [导出 Lync Server 2013 拓扑并将其复制到外部媒体以进行边缘安装](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) 。</span><span class="sxs-lookup"><span data-stu-id="0650a-132">For details, see [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="0650a-133">通过运行 **New-CsHostingProvider** cmdlet 设置以下参数，在边缘服务器上配置*托管服务提供商*：</span><span class="sxs-lookup"><span data-stu-id="0650a-133">Configure a *hosting provider* on the Edge Server by running the **New-CsHostingProvider** cmdlet to set the following parameters:</span></span>
    
      - <span data-ttu-id="0650a-134">**Identity** 为正在创建的托管服务提供商指定唯一的字符串值标识符，如 **Hosted Exchange UM**。</span><span class="sxs-lookup"><span data-stu-id="0650a-134">**Identity** specifies a unique string value identifier for the hosting provider that you are creating, for example, **Hosted Exchange UM**.</span></span>
    
      - <span data-ttu-id="0650a-p108">**Enabled** 指示您的域与承载服务提供商之间的网络连接是否已启用。必须设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="0650a-p108">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled. Must be set to **True**.</span></span>
    
      - <span data-ttu-id="0650a-p109">**EnabledSharedAddressSpace** 指示是否要在共享 SIP 地址空间方案中使用承载服务提供商。必须设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="0650a-p109">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario. Must be set to **True**.</span></span>
    
      - <span data-ttu-id="0650a-139">**HostsOCSUsers** 指示是否使用托管提供程序来承载 Lync Server 2013 帐户。</span><span class="sxs-lookup"><span data-stu-id="0650a-139">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server 2013 accounts.</span></span> <span data-ttu-id="0650a-140">必须设置为 **False**。</span><span class="sxs-lookup"><span data-stu-id="0650a-140">Must be set to **False**.</span></span>
    
      - <span data-ttu-id="0650a-141">**ProxyFQDN** 为承载服务提供商使用的代理服务器指定完全限定域名 (FQDN)，如 **proxyserver.fabrikam.com**。</span><span class="sxs-lookup"><span data-stu-id="0650a-141">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider, for example, **proxyserver.fabrikam.com**.</span></span> <span data-ttu-id="0650a-142">有关此信息，请与承载服务提供商联系。</span><span class="sxs-lookup"><span data-stu-id="0650a-142">Contact your hosting provider for this information.</span></span> <span data-ttu-id="0650a-143">不能修改此值。</span><span class="sxs-lookup"><span data-stu-id="0650a-143">This value cannot be modified.</span></span> <span data-ttu-id="0650a-144">如果承载服务提供商更改了其代理服务器，则您必须删除该条目，然后为提供商重新创建相应条目。</span><span class="sxs-lookup"><span data-stu-id="0650a-144">If the hosting provider changes its proxy server, you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="0650a-145">**IsLocal** 指示由托管提供程序使用的代理服务器是否包含在 Lync server 2013 拓扑中。</span><span class="sxs-lookup"><span data-stu-id="0650a-145">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server 2013 topology.</span></span> <span data-ttu-id="0650a-146">必须设置为 **False**。</span><span class="sxs-lookup"><span data-stu-id="0650a-146">Must be set to **False**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

