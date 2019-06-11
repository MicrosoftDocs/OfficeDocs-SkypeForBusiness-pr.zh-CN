---
title: Lync Server 2013：准备基础结构和系统
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing the infrastructure and systems
ms:assetid: 1254ee38-0679-4714-b293-1050f107c158
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398205(v=OCS.15)
ms:contentKeyID: 48183458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e724dd3b6105be3f4601c523dbbf558c91ca9f3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a><span data-ttu-id="8441d-102">为 Lync Server 2013 准备基础结构和系统</span><span class="sxs-lookup"><span data-stu-id="8441d-102">Preparing the infrastructure and systems for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8441d-103">_**主题上次修改时间:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="8441d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="8441d-104">部署 Lync Server 2013 需要使用拓扑生成器来定义和发布拓扑设计。</span><span class="sxs-lookup"><span data-stu-id="8441d-104">Deployment of Lync Server 2013 requires the use of Topology Builder to define and publish the topology design.</span></span> <span data-ttu-id="8441d-105">若要确定拓扑所需的组件, 请使用拓扑生成器创建和保存拓扑设计。</span><span class="sxs-lookup"><span data-stu-id="8441d-105">To identify the components required for your topology, you use Topology Builder to create and save a topology design.</span></span> <span data-ttu-id="8441d-106">在拓扑生成器中发布拓扑之前, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="8441d-106">Prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="8441d-107">获取并安装拓扑结构设计中使用拓扑生成器创建和保存的每个组件的硬件, 包括所有所需的计算机 (运行 Lync Server 2013 的服务器、数据库服务器、运行 Internet 信息服务的服务器) (IIS) 和反向代理服务器 (根据需要)、网络适配器、硬件负载平衡器和存储设备 (如文件服务器)。</span><span class="sxs-lookup"><span data-stu-id="8441d-107">Acquire and install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="8441d-108">有关如何定义拓扑以指定部署所需的组件的详细信息, 请参阅[在 Lync Server 2013 中定义和配置拓扑](lync-server-2013-defining-and-configuring-the-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="8441d-108">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="8441d-109">有关服务器硬件要求的详细信息, 请参阅支持文档中的[Lync Server 2013 支持的硬件](lync-server-2013-supported-hardware.md)。</span><span class="sxs-lookup"><span data-stu-id="8441d-109">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="8441d-110">请确保网络基础结构满足要求。</span><span class="sxs-lookup"><span data-stu-id="8441d-110">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="8441d-111">有关详细信息, 请参阅规划文档中[Lync Server 2013 的网络基础结构要求](lync-server-2013-network-infrastructure-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8441d-111">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="8441d-112">设置 Active Directory 域服务。</span><span class="sxs-lookup"><span data-stu-id="8441d-112">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="8441d-113">若要发布和启用拓扑, 你需要由 AD DS 中的计算机帐户表示的内部服务器。</span><span class="sxs-lookup"><span data-stu-id="8441d-113">To publish and enable the topology, you need the internal servers to be represented by computer accounts in AD DS.</span></span> <span data-ttu-id="8441d-114">这可通过将计算机加入到 AD DS 来完成。</span><span class="sxs-lookup"><span data-stu-id="8441d-114">This is accomplished by joining the computers to AD DS.</span></span> <span data-ttu-id="8441d-115">有关准备 AD DS 的详细信息, 请参阅[准备适用于 Lync Server 2013 的 Active Directory 域服务](lync-server-2013-preparing-active-directory-domain-services.md)。</span><span class="sxs-lookup"><span data-stu-id="8441d-115">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

  - <span data-ttu-id="8441d-116">创建文件共享。</span><span class="sxs-lookup"><span data-stu-id="8441d-116">Create a file share.</span></span> <span data-ttu-id="8441d-117">标准版服务器可以托管所需文件的文件共享, 而在企业部署中, 文件共享不能托管在前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="8441d-117">Standard Edition servers can host the file share for the required file, while in an Enterprise deployment the file share cannot be hosted on the front end server.</span></span> <span data-ttu-id="8441d-118">必须正确设置用于部署和设置文件夹和共享的访问控制列表 (ACL) 所需的权限和组成员身份, 拓扑生成器才能成功完成。</span><span class="sxs-lookup"><span data-stu-id="8441d-118">The permissions and group memberships required for deploying and setting the access control list (ACL) on the folder and the share must be set correctly for Topology Builder to complete successfully.</span></span> <span data-ttu-id="8441d-119">应确保运行拓扑生成器的人员具有下列权限和组成员身份:</span><span class="sxs-lookup"><span data-stu-id="8441d-119">You should make sure that the person running Topology Builder has the following permissions and group memberships:</span></span>
    
      - <span data-ttu-id="8441d-120">本地管理员的成员</span><span class="sxs-lookup"><span data-stu-id="8441d-120">Member of Local Administrators</span></span>
    
      - <span data-ttu-id="8441d-121">域用户的成员</span><span class="sxs-lookup"><span data-stu-id="8441d-121">Member of Domain Users</span></span>
    
      - <span data-ttu-id="8441d-122">文件存储的 "共享和文件夹" 的 "完全控制"</span><span class="sxs-lookup"><span data-stu-id="8441d-122">Full Control on share and folder of file store</span></span>

  - <span data-ttu-id="8441d-123">对于企业版, 请安装并配置 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="8441d-123">For Enterprise Edition, install and configure SQL Server.</span></span> <span data-ttu-id="8441d-124">若要使 SQL Server 安装成功, 基于 SQL Server 的服务器必须处于联机状态, 并且发布拓扑的人员是 SQL Server 上的本地管理员, 并且必须是 sql server 实例上 SQL Server sysadmin 组的成员。</span><span class="sxs-lookup"><span data-stu-id="8441d-124">For SQL Server setup to succeed the SQL Server-based server must be online and the person publishing the topology be a local admin on the SQL Server and must be a member of the SQL Server sysadmin group on the SQL Server instance.</span></span>

<span data-ttu-id="8441d-125">完成本主题中所述的所有准备任务后, 在发布拓扑之前, 还需要执行其他准备任务, 包括安装 Windows 操作系统和其他必备软件, 设置IIS 和配置 DNS。</span><span class="sxs-lookup"><span data-stu-id="8441d-125">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to perform the other preparation tasks, including installing the Windows operating systems and other prerequisite software, setting up IIS, and configuring DNS.</span></span> <span data-ttu-id="8441d-126">有关这些任务的详细信息, 请参阅[运行 Lync server 2013 的服务器的系统要求](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md)、[配置 lync SERVER 2013 的 IIS](lync-server-2013-configure-iis.md)以及[准备适用于 lync server 2013 的基础结构和系统](lync-server-2013-preparing-the-infrastructure-and-systems.md)。</span><span class="sxs-lookup"><span data-stu-id="8441d-126">For details about these tasks, see [System requirements for servers running Lync Server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Configure IIS for Lync Server 2013](lync-server-2013-configure-iis.md), and [Preparing the infrastructure and systems for Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md).</span></span> <span data-ttu-id="8441d-127">此外, 你应该熟悉客户和客户端要求。</span><span class="sxs-lookup"><span data-stu-id="8441d-127">Additionally, you should familiarize yourself with the clients and client requirements.</span></span> <span data-ttu-id="8441d-128">有关详细信息, 请参阅[在 Lync Server 2013 中部署客户端和设备](lync-server-2013-deploying-clients-and-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="8441d-128">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8441d-129">本节内容</span><span class="sxs-lookup"><span data-stu-id="8441d-129">In This Section</span></span>

  - [<span data-ttu-id="8441d-130">Lync Server 2013 的硬件安装</span><span class="sxs-lookup"><span data-stu-id="8441d-130">Hardware setup for Lync Server 2013</span></span>](lync-server-2013-hardware-setup.md)

  - [<span data-ttu-id="8441d-131">Lync Server 2013 的软件安装</span><span class="sxs-lookup"><span data-stu-id="8441d-131">Software setup for Lync Server 2013</span></span>](lync-server-2013-software-setup.md)

  - [<span data-ttu-id="8441d-132">为 Lync Server 2013 准备 Active Directory 域服务</span><span class="sxs-lookup"><span data-stu-id="8441d-132">Preparing Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-preparing-active-directory-domain-services.md)

  - [<span data-ttu-id="8441d-133">为 Lync Server 2013 配置 SQL Server</span><span class="sxs-lookup"><span data-stu-id="8441d-133">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="8441d-134">在 Lync Server 2013 中配置前端池或 Standard Edition 服务器的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="8441d-134">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="8441d-135">安装 Lync Server 2013 管理工具</span><span class="sxs-lookup"><span data-stu-id="8441d-135">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

