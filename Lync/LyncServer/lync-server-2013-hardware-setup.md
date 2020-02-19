---
title: Lync Server 2013：硬件安装程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware setup
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425852(v=OCS.15)
ms:contentKeyID: 48183834
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d55ac04a06984889a3038aceee7fd0f311efcfb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardware-setup-for-lync-server-2013"></a><span data-ttu-id="bf9ca-102">Lync Server 2013 的硬件设置</span><span class="sxs-lookup"><span data-stu-id="bf9ca-102">Hardware setup for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf9ca-103">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="bf9ca-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="bf9ca-104">若要在基础结构中设置需要实现拓扑所需的硬件和其他组件，需要在拓扑生成器中发布拓扑之前，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bf9ca-104">Setting up the hardware and other components required in the infrastructure that you need to implement your topology requires that, prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="bf9ca-105">为拓扑设计中使用拓扑生成器创建和保存的每个组件安装硬件，其中包括所有必需的计算机（运行 Lync Server 2013 的服务器、数据库服务器、运行 Internet 信息服务的服务器（IIS）和根据需要反向代理服务器）、网络适配器、硬件负载平衡器和存储设备（如文件服务器）。</span><span class="sxs-lookup"><span data-stu-id="bf9ca-105">Install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="bf9ca-106">确认您已遵循针对网络适配器的数量和速度的建议。</span><span class="sxs-lookup"><span data-stu-id="bf9ca-106">Confirm that you have followed the recommendations for the number and speed for network adapters.</span></span> <span data-ttu-id="bf9ca-107">如果要使用硬件负载平衡器，请确保供应商提供了正确的信息，以便将其配置为与 Lync Server 2013 一起使用。</span><span class="sxs-lookup"><span data-stu-id="bf9ca-107">If you will be using hardware load balancers, make sure that you have the proper information from the vendor to configure them for use with Lync Server 2013.</span></span> <span data-ttu-id="bf9ca-108">如果要使用文件服务器或其他服务器来承载 Lync Server 所需的文件共享，请确保该服务器可用，并且已准备好配置文件共享。</span><span class="sxs-lookup"><span data-stu-id="bf9ca-108">If you will be using a file server or other server to house the file share required by Lync Server, make sure that the server is available and ready for the configuration of the file share.</span></span> <span data-ttu-id="bf9ca-109">有关如何定义拓扑以指定部署所需的组件的详细信息，请参阅[在 Lync Server 2013 中定义和配置拓扑](lync-server-2013-defining-and-configuring-the-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="bf9ca-109">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="bf9ca-110">有关服务器的硬件要求的详细信息，请参阅可支持性文档中的[Lync Server 2013 支持的硬件](lync-server-2013-supported-hardware.md)。</span><span class="sxs-lookup"><span data-stu-id="bf9ca-110">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="bf9ca-111">请确保网络基础结构满足要求。</span><span class="sxs-lookup"><span data-stu-id="bf9ca-111">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="bf9ca-112">有关详细信息，请参阅规划文档中的[Lync Server 2013 的网络基础结构要求](lync-server-2013-network-infrastructure-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bf9ca-112">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="bf9ca-113">设置 Active Directory 域服务。</span><span class="sxs-lookup"><span data-stu-id="bf9ca-113">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="bf9ca-114">设置 AD DS 包括准备 AD DS 和定义要在 AD DS 中部署的所有组件。</span><span class="sxs-lookup"><span data-stu-id="bf9ca-114">Setting up AD DS includes preparing AD DS and defining all components that you want to deploy in AD DS.</span></span> <span data-ttu-id="bf9ca-115">有关准备 AD DS 的详细信息，请参阅部署文档中的[为 Lync Server 2013 准备 Active Directory 域服务](lync-server-2013-preparing-active-directory-domain-services.md)。</span><span class="sxs-lookup"><span data-stu-id="bf9ca-115">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="bf9ca-116">设置创建文件共享所需的权限。</span><span class="sxs-lookup"><span data-stu-id="bf9ca-116">Set up the required permissions for creating the file share.</span></span> <span data-ttu-id="bf9ca-117">由 Lync Server 2013 使用文件共享的权限是在发布拓扑时由拓扑生成器自动配置的。</span><span class="sxs-lookup"><span data-stu-id="bf9ca-117">Permissions for use of file shares by Lync Server 2013 are automatically configured by Topology Builder when you publish your topology.</span></span> <span data-ttu-id="bf9ca-118">但是，用于发布拓扑的用户帐户必须具有对文件共享的完全控制权限（读/写/修改），以便拓扑生成器能够配置所需的权限。</span><span class="sxs-lookup"><span data-stu-id="bf9ca-118">However, the user account used to publish the topology must have full control (read/write/modify) on the file share in order for Topology Builder to configure the required permissions.</span></span> <span data-ttu-id="bf9ca-119">若要确保在拓扑生成器发布过程中可以正确管理文件共享，应将用户所属的用户或域组设为文件共享所在的计算机上本地 Administrators 组的成员。</span><span class="sxs-lookup"><span data-stu-id="bf9ca-119">To make sure that the file share can be managed properly during the Topology Builder publishing process, the user or domain group that the user is a member of should be made a member of the local Administrators group on the machine where the file share is located.</span></span> <span data-ttu-id="bf9ca-120">在多域方案中，域 A 用户或组应该成为文件共享所在域 B 中的计算机上本地 Administrators 组的成员。</span><span class="sxs-lookup"><span data-stu-id="bf9ca-120">In a multi-domain scenario, Domain A user or group should be made a member of the local Administrators group on the machine in Domain B where the file share will be located.</span></span>
    
    <span data-ttu-id="bf9ca-121">有关使用分布式文件系统（DFS）中的文件共享进行更新的详细信息，请参阅[Configure file storage For Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md)。</span><span class="sxs-lookup"><span data-stu-id="bf9ca-121">For details about updating using file shares in a Distributed File System (DFS), see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="bf9ca-122">Lync Server 2013 的文件共享不能位于前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="bf9ca-122">The file share for Lync Server 2013, Enterprise Edition cannot be located on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="bf9ca-123">安装和设置用于 Web 服务的硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="bf9ca-123">Install and set up the hardware load balancer for Web Services.</span></span> <span data-ttu-id="bf9ca-124">部署域名系统 (DNS) 负载平衡后，还需要在这些池中使用硬件负载平衡器，但仅用于 HTTP/HTTPS 流量。</span><span class="sxs-lookup"><span data-stu-id="bf9ca-124">With Domain Name System (DNS) load balancing deployed, you still need to also use hardware load balancers for these pools, but only for HTTP/HTTPS traffic.</span></span> <span data-ttu-id="bf9ca-125">硬件负载平衡器用于客户端通过端口 443 和 80 发送的 HTTPS 流量。</span><span class="sxs-lookup"><span data-stu-id="bf9ca-125">The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span> <span data-ttu-id="bf9ca-126">尽管还需要在这些池中使用硬件负载平衡器，但是主要针对 HTTP/HTTPS 流量进行设置和管理，这都是硬件负载平衡器管理员所熟悉的内容。</span><span class="sxs-lookup"><span data-stu-id="bf9ca-126">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTP/HTTPS traffic, which the administrators of the hardware load balancers are accustomed to.</span></span>

<span data-ttu-id="bf9ca-127">完成本主题中介绍的所有准备任务后，在发布拓扑前，还需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bf9ca-127">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to:</span></span>

  - [<span data-ttu-id="bf9ca-128">在服务器上安装适用于 Lync Server 2013 的操作系统和必备软件</span><span class="sxs-lookup"><span data-stu-id="bf9ca-128">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [<span data-ttu-id="bf9ca-129">为 Lync Server 2013 配置 IIS</span><span class="sxs-lookup"><span data-stu-id="bf9ca-129">Configure IIS for Lync Server 2013</span></span>](lync-server-2013-configure-iis.md)

  - [<span data-ttu-id="bf9ca-130">为 Lync Server 2013 配置 SQL Server</span><span class="sxs-lookup"><span data-stu-id="bf9ca-130">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="bf9ca-131">在 Lync Server 2013 for a 前端池或 Standard Edition Server 中配置 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="bf9ca-131">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

