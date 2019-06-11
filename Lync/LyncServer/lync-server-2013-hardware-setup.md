---
title: Lync Server 2013：硬件安装
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardware setup
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425852(v=OCS.15)
ms:contentKeyID: 48183834
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e2d05db28ffa61ea25dbb237c388c37a87ac5a0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-setup-for-lync-server-2013"></a><span data-ttu-id="24c6e-102">Lync Server 2013 的硬件安装</span><span class="sxs-lookup"><span data-stu-id="24c6e-102">Hardware setup for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24c6e-103">_**主题上次修改时间:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="24c6e-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="24c6e-104">在需要用于实现拓扑的基础结构中设置硬件和其他组件需要在拓扑生成器中发布拓扑之前执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="24c6e-104">Setting up the hardware and other components required in the infrastructure that you need to implement your topology requires that, prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="24c6e-105">使用拓扑生成器创建和保存的拓扑设计中的每个组件安装硬件, 包括所有所需的计算机 (运行 Lync Server 2013、数据库服务器、运行 Internet 信息服务 (IIS) 的服务器) 和反向代理服务器 (根据需要)、网络适配器、硬件负载平衡器和存储设备 (如文件服务器)。</span><span class="sxs-lookup"><span data-stu-id="24c6e-105">Install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="24c6e-106">确认已遵循网络适配器的号码和速度建议。</span><span class="sxs-lookup"><span data-stu-id="24c6e-106">Confirm that you have followed the recommendations for the number and speed for network adapters.</span></span> <span data-ttu-id="24c6e-107">如果你要使用硬件负载平衡器, 请确保你拥有来自供应商的适当信息, 以便将其配置为与 Lync Server 2013 配合使用。</span><span class="sxs-lookup"><span data-stu-id="24c6e-107">If you will be using hardware load balancers, make sure that you have the proper information from the vendor to configure them for use with Lync Server 2013.</span></span> <span data-ttu-id="24c6e-108">如果你将使用文件服务器或其他服务器来承载 Lync Server 所需的文件共享, 请确保服务器可用, 并且已准备好配置文件共享。</span><span class="sxs-lookup"><span data-stu-id="24c6e-108">If you will be using a file server or other server to house the file share required by Lync Server, make sure that the server is available and ready for the configuration of the file share.</span></span> <span data-ttu-id="24c6e-109">有关如何定义拓扑以指定部署所需的组件的详细信息, 请参阅[在 Lync Server 2013 中定义和配置拓扑](lync-server-2013-defining-and-configuring-the-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="24c6e-109">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="24c6e-110">有关服务器硬件要求的详细信息, 请参阅支持文档中的[Lync Server 2013 支持的硬件](lync-server-2013-supported-hardware.md)。</span><span class="sxs-lookup"><span data-stu-id="24c6e-110">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="24c6e-111">请确保网络基础结构满足要求。</span><span class="sxs-lookup"><span data-stu-id="24c6e-111">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="24c6e-112">有关详细信息, 请参阅规划文档中[Lync Server 2013 的网络基础结构要求](lync-server-2013-network-infrastructure-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="24c6e-112">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="24c6e-113">设置 Active Directory 域服务。</span><span class="sxs-lookup"><span data-stu-id="24c6e-113">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="24c6e-114">设置 AD DS 包括准备 AD DS 和定义要在 AD DS 中部署的所有组件。</span><span class="sxs-lookup"><span data-stu-id="24c6e-114">Setting up AD DS includes preparing AD DS and defining all components that you want to deploy in AD DS.</span></span> <span data-ttu-id="24c6e-115">有关准备 AD DS 的详细信息, 请参阅部署文档中的[准备适用于 Lync Server 2013 的 Active Directory 域服务](lync-server-2013-preparing-active-directory-domain-services.md)。</span><span class="sxs-lookup"><span data-stu-id="24c6e-115">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="24c6e-116">设置创建文件共享所需的权限。</span><span class="sxs-lookup"><span data-stu-id="24c6e-116">Set up the required permissions for creating the file share.</span></span> <span data-ttu-id="24c6e-117">在发布拓扑时, 由 Lync Server 2013 使用文件共享的权限会自动配置为拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="24c6e-117">Permissions for use of file shares by Lync Server 2013 are automatically configured by Topology Builder when you publish your topology.</span></span> <span data-ttu-id="24c6e-118">但是, 用于发布拓扑的用户帐户必须具有文件共享的完全控制 (读/写/修改) 才能使拓扑生成器配置所需的权限。</span><span class="sxs-lookup"><span data-stu-id="24c6e-118">However, the user account used to publish the topology must have full control (read/write/modify) on the file share in order for Topology Builder to configure the required permissions.</span></span> <span data-ttu-id="24c6e-119">若要确保可在拓扑生成器发布过程中正确管理文件共享, 应将用户所属的用户或域组作为文件共享所在的计算机上的本地管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="24c6e-119">To make sure that the file share can be managed properly during the Topology Builder publishing process, the user or domain group that the user is a member of should be made a member of the local Administrators group on the machine where the file share is located.</span></span> <span data-ttu-id="24c6e-120">在多域方案中, 域 A 用户或组应成为文件共享所在的域 B 中计算机上的本地管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="24c6e-120">In a multi-domain scenario, Domain A user or group should be made a member of the local Administrators group on the machine in Domain B where the file share will be located.</span></span>
    
    <span data-ttu-id="24c6e-121">有关使用分布式文件系统 (DFS) 中的文件共享进行更新的详细信息, 请参阅[为 Lync Server 2013 配置文件存储](lync-server-2013-configure-dfs-file-storage.md)。</span><span class="sxs-lookup"><span data-stu-id="24c6e-121">For details about updating using file shares in a Distributed File System (DFS), see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="24c6e-122">Lync Server 2013 的文件共享无法在前端服务器上找到。</span><span class="sxs-lookup"><span data-stu-id="24c6e-122">The file share for Lync Server 2013, Enterprise Edition cannot be located on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="24c6e-123">安装和设置用于 Web 服务的硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="24c6e-123">Install and set up the hardware load balancer for Web Services.</span></span> <span data-ttu-id="24c6e-124">在部署了域名系统 (DNS) 负载平衡的情况下, 你仍然需要对这些池使用硬件负载平衡器, 但仅适用于 HTTP/HTTPS 流量。</span><span class="sxs-lookup"><span data-stu-id="24c6e-124">With Domain Name System (DNS) load balancing deployed, you still need to also use hardware load balancers for these pools, but only for HTTP/HTTPS traffic.</span></span> <span data-ttu-id="24c6e-125">硬件负载平衡器用于来自端口443和80的客户端的 HTTPS 流量。</span><span class="sxs-lookup"><span data-stu-id="24c6e-125">The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span> <span data-ttu-id="24c6e-126">虽然您仍需要这些池的硬件负载平衡器, 但它们的设置和管理主要用于 HTTP/HTTPS 流量, 这些流量习惯于硬件负载平衡器的管理员。</span><span class="sxs-lookup"><span data-stu-id="24c6e-126">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTP/HTTPS traffic, which the administrators of the hardware load balancers are accustomed to.</span></span>

<span data-ttu-id="24c6e-127">完成本主题中所述的所有准备任务后, 在发布拓扑之前, 您还需要:</span><span class="sxs-lookup"><span data-stu-id="24c6e-127">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to:</span></span>

  - [<span data-ttu-id="24c6e-128">在服务器上安装适用于 Lync Server 2013 的操作系统和必备软件</span><span class="sxs-lookup"><span data-stu-id="24c6e-128">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [<span data-ttu-id="24c6e-129">为 Lync Server 2013 配置 IIS</span><span class="sxs-lookup"><span data-stu-id="24c6e-129">Configure IIS for Lync Server 2013</span></span>](lync-server-2013-configure-iis.md)

  - [<span data-ttu-id="24c6e-130">为 Lync Server 2013 配置 SQL Server</span><span class="sxs-lookup"><span data-stu-id="24c6e-130">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="24c6e-131">在 Lync Server 2013 中配置前端池或 Standard Edition 服务器的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="24c6e-131">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

