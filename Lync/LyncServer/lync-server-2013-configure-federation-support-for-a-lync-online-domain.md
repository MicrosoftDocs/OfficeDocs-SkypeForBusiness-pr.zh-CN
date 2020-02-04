---
title: Lync Server 2013：为 Lync Online 域配置联合身份验证支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation support for a Lync Online domain
ms:assetid: 19d5d5be-cd7f-47b8-b6c5-651a3191def7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202166(v=OCS.15)
ms:contentKeyID: 48183530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f883e8d730e63788b4cbe0ccd3315f21e6fea97
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a><span data-ttu-id="151a6-102">在 Lync Server 2013 中配置 Lync Online 域的联合身份验证支持</span><span class="sxs-lookup"><span data-stu-id="151a6-102">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="151a6-103">_**主题上次修改时间：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="151a6-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="151a6-104">要与 Microsoft Lync Online 2010 客户进行联盟，您需要完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="151a6-104">Federating with a Microsoft Lync Online 2010 customer requires you to complete the following steps:</span></span>

  - <span data-ttu-id="151a6-105">配置对 Lync Online 2010 客户的域的支持（例如，contoso.onmicrosoft.com）。</span><span class="sxs-lookup"><span data-stu-id="151a6-105">Configure support for the domain of the Lync Online 2010 customer (for example, contoso.onmicrosoft.com).</span></span> <span data-ttu-id="151a6-106">正如在本文档的 "Lync Server 2013" 部分中的 "[与 Lync Online 客户进行联盟](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)" 的先决条件中所指定，你应该已为你的组织启用联盟。</span><span class="sxs-lookup"><span data-stu-id="151a6-106">As specified in the [Prerequisites for federating with a Lync Online customer in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) section of this documentation, you should have already enabled federation for your organization.</span></span> <span data-ttu-id="151a6-107">启用联盟需要指定用于控制联盟域的访问的方法。</span><span class="sxs-lookup"><span data-stu-id="151a6-107">Enabling federation requires specifying the method to be used to control access by federated domains.</span></span> <span data-ttu-id="151a6-108">如果将组织配置为使用发现，则将域添加到组织的允许列表是可选的。</span><span class="sxs-lookup"><span data-stu-id="151a6-108">If you configured your organization to use discovery, adding the domain to your organization’s allowed list is optional.</span></span> <span data-ttu-id="151a6-109">如果未启用域发现，则必须将 Lync Online 客户的域名添加到 "允许的域" 列表。</span><span class="sxs-lookup"><span data-stu-id="151a6-109">If you did not enable domain discovery, then you must add the domain name of the Lync Online customer to your allowed domains list.</span></span> <span data-ttu-id="151a6-110">你可以通过使用 Lync Server 控制面板或运行**CSAllowedDomain** cmdlet 来添加域名。</span><span class="sxs-lookup"><span data-stu-id="151a6-110">You can add a domain name either by using Lync Server Control Panel or by running the **New-CSAllowedDomain** cmdlet.</span></span> <span data-ttu-id="151a6-111">有关使用 Lync Server 控制面板（包括启用域发现）的详细信息，请参阅操作文档中的[在 Lync Server 2013 中管理您的组织的 SIP 联合提供商](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="151a6-111">For details about using Lync Server Control Panel, including enabling discovery of domains, see [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span> <span data-ttu-id="151a6-112">有关使用**CSAllowedDomain** cmdlet 添加域的详细信息，请参阅 "操作" 文档中的 "[新建-CSAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) "。</span><span class="sxs-lookup"><span data-stu-id="151a6-112">For details about using the **New-CSAllowedDomain** cmdlet to add a domain, see [New-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) in the Operations documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="151a6-113">Lync Online 客户可以有多个域。</span><span class="sxs-lookup"><span data-stu-id="151a6-113">A Lync Online customer can have multiple domains.</span></span> <span data-ttu-id="151a6-114">如果你想要与多个域联盟，则必须为要对其支持联盟的每个单独域配置支持，并且 Lync Online 客户的管理员必须为要进行联盟的每个域启用联盟。</span><span class="sxs-lookup"><span data-stu-id="151a6-114">If you want to federate with more than one of the domains, you must configure support for each individual domain with which you want to support federation, and the administrator of the Lync Online customer must enable federation for each of the domains to be federated.</span></span>

    
    </div>

  - <span data-ttu-id="151a6-115">配置对要与其进行联盟的 Lync Online 2010 客户域的托管提供商的支持。</span><span class="sxs-lookup"><span data-stu-id="151a6-115">Configure support for the hosting provider of the Lync Online 2010 customer domain with which you want to federate.</span></span> <span data-ttu-id="151a6-116">使用此部分中的过程配置对托管提供程序的支持。</span><span class="sxs-lookup"><span data-stu-id="151a6-116">Use the procedure in this section to configure support for hosting provider.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="151a6-117">只有具有 Lync Online 客户的域的联盟才需要此步骤，而不是用于联盟伙伴位置上部署的任何域的联盟。</span><span class="sxs-lookup"><span data-stu-id="151a6-117">This step is required only for federation with a domain of a Lync Online customer, not for federation with any domain that is deployed on-premises at a federated partner’s location.</span></span>

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a><span data-ttu-id="151a6-118">为托管提供商配置支持</span><span class="sxs-lookup"><span data-stu-id="151a6-118">To configure support for a hosting provider</span></span>

1.  <span data-ttu-id="151a6-119">从前端服务器，启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft lync server 2013**"，然后单击 " **Lync server Management Shell**"。</span><span class="sxs-lookup"><span data-stu-id="151a6-119">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="151a6-120">运行**CsHostingProvider** cmdlet 以创建和配置托管提供程序。</span><span class="sxs-lookup"><span data-stu-id="151a6-120">Run the **New-CsHostingProvider** cmdlet to create and configure the hosting provider.</span></span> <span data-ttu-id="151a6-121">例如，运行：</span><span class="sxs-lookup"><span data-stu-id="151a6-121">For example, run:</span></span>
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    <span data-ttu-id="151a6-122">上述示例设置了以下参数：</span><span class="sxs-lookup"><span data-stu-id="151a6-122">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="151a6-123">**标识**为你创建的托管提供程序指定唯一的字符串值标识符。</span><span class="sxs-lookup"><span data-stu-id="151a6-123">**Identity** specifies a unique string value identifier for the hosting provider that you are creating.</span></span> <span data-ttu-id="151a6-124">请注意，如果某个现有提供商已使用该 Identity 进行配置，该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="151a6-124">Note that the command will fail if an existing provider has already been configured with that Identity.</span></span>
    
      - <span data-ttu-id="151a6-125">**ProxyFQDN** 指定宿主提供程序所使用的代理服务器的完全限定域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="151a6-125">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="151a6-126">不能修改此值。</span><span class="sxs-lookup"><span data-stu-id="151a6-126">This value cannot be modified.</span></span> <span data-ttu-id="151a6-127">如果承载服务提供商更改了其代理服务器，则您必须删除该条目，然后为提供商重新创建相应条目。</span><span class="sxs-lookup"><span data-stu-id="151a6-127">If the hosting provider changes its proxy server you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="151a6-128">**VerificationLevel**指定如何验证从托管提供程序发送的消息（或 if）以确保它们是从该提供商处发送的。</span><span class="sxs-lookup"><span data-stu-id="151a6-128">**VerificationLevel** specifies how (or if) messages sent from a hosting provider are verified to ensure that they were sent from that provider.</span></span>
    
      - <span data-ttu-id="151a6-p107">\*\*Enabled \*\* 指示您的域与承载服务提供商之间的网络连接是否已启用。除非此值设置为 \*\*True \*\*，否则无法在这两个组织之间交换消息。</span><span class="sxs-lookup"><span data-stu-id="151a6-p107">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled. Messages cannot be exchanged between the two organizations until this value is set to **True**.</span></span>
    
      - <span data-ttu-id="151a6-131">\*\*EnabledSharedAddressSpace \*\* 指示是否在共享 SIP 地址空间（拆分域）方案中使用此承载服务提供商。</span><span class="sxs-lookup"><span data-stu-id="151a6-131">**EnabledSharedAddressSpace** indicates whether the hosting provider is being used in a shared SIP address space (split domain) scenario.</span></span>
    
      - <span data-ttu-id="151a6-132">**HostsOCSUsers**指示托管提供程序是否用于托管 Lync Server 帐户。</span><span class="sxs-lookup"><span data-stu-id="151a6-132">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server accounts.</span></span> <span data-ttu-id="151a6-133">如果设置为 \*\*False \*\*，则提供商承载其他帐户类型，例如 Microsoft Exchange 帐户。</span><span class="sxs-lookup"><span data-stu-id="151a6-133">If **False**, the provider hosts other account types, such as Microsoft Exchange accounts.</span></span>
    
      - <span data-ttu-id="151a6-134">**IsLocal**指示你的 Lync server 拓扑中是否包含托管提供程序使用的代理服务器。</span><span class="sxs-lookup"><span data-stu-id="151a6-134">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server topology.</span></span>
    
    <span data-ttu-id="151a6-135">有关使用此 cmdlet 的详细信息，请参阅操作文档中的[CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) 。</span><span class="sxs-lookup"><span data-stu-id="151a6-135">For details about using this cmdlet, see [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

