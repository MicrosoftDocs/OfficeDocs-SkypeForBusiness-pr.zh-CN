---
title: Lync Server 2013：部署持久聊天服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Persistent Chat Server
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48185717
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83a23190033bca9047a3d1a6d70b914d02017db8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="eee3d-102">在 Lync Server 2013 中部署持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="eee3d-102">Deploying Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eee3d-103">_**上次修改的主题：** 2014-03-31_</span><span class="sxs-lookup"><span data-stu-id="eee3d-103">_**Topic Last Modified:** 2014-03-31_</span></span>

<span data-ttu-id="eee3d-104">Lync Server 2013，持久聊天服务器是 Lync Server 2013 基础结构的一部分。</span><span class="sxs-lookup"><span data-stu-id="eee3d-104">Lync Server 2013, Persistent Chat Server is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="eee3d-105">部署持久聊天服务器要求您执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="eee3d-105">Deploying Persistent Chat Server requires that you:</span></span>

  - <span data-ttu-id="eee3d-106">使用拓扑生成器定义或导入您的拓扑，并随后发布您要部署的组件。</span><span class="sxs-lookup"><span data-stu-id="eee3d-106">Use Topology Builder to define, or import, and subsequently publish your topology and the components that you want to deploy.</span></span>

  - <span data-ttu-id="eee3d-107">准备部署持久聊天服务器组件的环境。</span><span class="sxs-lookup"><span data-stu-id="eee3d-107">Prepare your environment for deploying Persistent Chat Server components.</span></span>

  - <span data-ttu-id="eee3d-108">为您的部署安装和配置持久聊天服务器组件。</span><span class="sxs-lookup"><span data-stu-id="eee3d-108">Install and configure Persistent Chat Server components for your deployment.</span></span>

<span data-ttu-id="eee3d-109">在 Lync Server 2013 Enterprise Edition 中将持久聊天服务器作为单独的池（而不是与 Enterprise Edition 前端服务器的并置）一起使用。</span><span class="sxs-lookup"><span data-stu-id="eee3d-109">Persistent Chat Server is available with Lync Server 2013 Enterprise Edition as a separate pool (not collocated with the Enterprise Edition Front End Servers).</span></span> <span data-ttu-id="eee3d-110">持久聊天服务器要求企业版池中的 SQL Server 后端服务器存储聊天室内容和其他相关元数据。</span><span class="sxs-lookup"><span data-stu-id="eee3d-110">Persistent Chat Server requires a SQL Server Back End Server in your Enterprise Edition pool to store the chat room content and other relevant metadata.</span></span> <span data-ttu-id="eee3d-111">我们建议您在专用 SQL Server 后端服务器上安装**PersistentChatStore** ，但支持在同一 sql server 实例上并置 Lync Server 2013 后端服务器和**PersistentChatStore** 。</span><span class="sxs-lookup"><span data-stu-id="eee3d-111">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server, although collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance is supported.</span></span>

<span data-ttu-id="eee3d-112">持久聊天服务器也可以使用 Lync Server 2013 Standard Edition 进行部署。</span><span class="sxs-lookup"><span data-stu-id="eee3d-112">Persistent Chat Server can also be deployed with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="eee3d-113">在这种情况下， **PersistentChatService**前端服务器在 Standard Edition 计算机上为并置， **PersistentChatStore**后端服务器可以部署在本地 SQL Server Express 实例上。</span><span class="sxs-lookup"><span data-stu-id="eee3d-113">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition computer, and the **PersistentChatStore** Back End Server can be deployed on the local SQL Server Express instance.</span></span>

<span data-ttu-id="eee3d-114">有关支持的 colocation 配置的详细信息，请参阅[Lync server 2013 中的支持的服务器并置](lync-server-2013-supported-server-collocation.md)。</span><span class="sxs-lookup"><span data-stu-id="eee3d-114">For details about supported colocation configurations, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="eee3d-115">我们不支持持久聊天服务器&nbsp;Standard Edition 的高可用性。</span><span class="sxs-lookup"><span data-stu-id="eee3d-115">We do not support high availability for Persistent Chat Server&nbsp;Standard Edition.</span></span> <span data-ttu-id="eee3d-116">性能和规模将受到限制。</span><span class="sxs-lookup"><span data-stu-id="eee3d-116">Performance and scale will be limited.</span></span> <span data-ttu-id="eee3d-117">此外，我们仅支持新的持久聊天&nbsp;服务器 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="eee3d-117">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server.</span></span> <span data-ttu-id="eee3d-118">我们不支持将 Lync Server 2010、Group Chat Server 升级为 Lync Server 2013&nbsp;持久聊天服务器&nbsp;Standard Edition。</span><span class="sxs-lookup"><span data-stu-id="eee3d-118">We do not support upgrading Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<span data-ttu-id="eee3d-119">如果您的组织需要合规性支持，则可以在持久聊天服务器前端服务器上安装持久聊天服务器合规性服务。</span><span class="sxs-lookup"><span data-stu-id="eee3d-119">If your organization requires compliance support, you can install the Persistent Chat Server Compliance service on the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="eee3d-120">合规性需要单独的数据库。</span><span class="sxs-lookup"><span data-stu-id="eee3d-120">A separate database is required for compliance.</span></span>

<span data-ttu-id="eee3d-121">每个拓扑至少需要安装了 Lync Server 2013 的服务器和一个安装了 SQL Server 数据库软件的服务器。</span><span class="sxs-lookup"><span data-stu-id="eee3d-121">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span>

<span data-ttu-id="eee3d-122">使用拓扑生成器将持久聊天服务器添加到 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="eee3d-122">Use Topology Builder to add Persistent Chat Server to your Lync Server 2013 deployments.</span></span> <span data-ttu-id="eee3d-123">您可以选择使用拓扑生成器添加一个或多个持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="eee3d-123">You can choose to add one or more Persistent Chat Server pools using Topology Builder.</span></span> <span data-ttu-id="eee3d-124">按照与对任意池相同的方式部署多个持久聊天服务器池的相同部署说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="eee3d-124">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool.</span></span> <span data-ttu-id="eee3d-125">有关详细信息，请参阅部署文档中的[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="eee3d-125">For details, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="eee3d-126">有关可用拓扑的详细信息以及安装持久聊天服务器的技术和软件要求，请参阅规划文档中的 "在[lync server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)"、规划文档、部署文档或操作文档中的[持久聊天服务器的工作2013原理](lync-server-2013-how-persistent-chat-server-works.md)，以及可支持性文档中的[lync server 2013 支持的硬件](lync-server-2013-supported-hardware.md)。</span><span class="sxs-lookup"><span data-stu-id="eee3d-126">For details about available topologies and the technical and software requirements for installing Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation, and [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

<span data-ttu-id="eee3d-127">有关获取证书、创建 SQL Server 数据库和创建文件存储的详细信息，请参阅部署文档中的[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="eee3d-127">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="eee3d-128">一个持久聊天服务器前端服务器可支持20000个活动用户。</span><span class="sxs-lookup"><span data-stu-id="eee3d-128">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="eee3d-129">您可以拥有一个持久聊天服务器池和最高4个活动前端服务器，共支持80000个并发用户。</span><span class="sxs-lookup"><span data-stu-id="eee3d-129">You can have a Persistent Chat Server pool with up to 4 active Front End Servers supporting a total of 80,000 concurrent users.</span></span>

<span data-ttu-id="eee3d-130">虚拟服务器上也支持持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="eee3d-130">Persistent Chat Server is also supported on a virtual server.</span></span> <span data-ttu-id="eee3d-131">如果虚拟服务器与物理服务器的规格一致，则最多可支持 20,000 个并发用户。</span><span class="sxs-lookup"><span data-stu-id="eee3d-131">The virtual server can support up to 20,000 concurrent users if it matches the specifications of the physical server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="eee3d-132">必须在 NTFS 文件系统上安装持久聊天服务器，以帮助强制实施文件系统安全。</span><span class="sxs-lookup"><span data-stu-id="eee3d-132">Persistent Chat Server must be installed on an NTFS file system to help enforce file system security.</span></span> <span data-ttu-id="eee3d-133">FAT32 不是持久聊天服务器支持的文件系统。</span><span class="sxs-lookup"><span data-stu-id="eee3d-133">FAT32 is not a supported file system for Persistent Chat Server.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="eee3d-134">本部分内容</span><span class="sxs-lookup"><span data-stu-id="eee3d-134">In This Section</span></span>

  - [<span data-ttu-id="eee3d-135">Lync Server 2013 中持久聊天服务器的工作原理</span><span class="sxs-lookup"><span data-stu-id="eee3d-135">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="eee3d-136">Lync Server 2013 中持久聊天服务器的部署清单</span><span class="sxs-lookup"><span data-stu-id="eee3d-136">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [<span data-ttu-id="eee3d-137">Lync Server 2013 中持久聊天服务器的技术要求</span><span class="sxs-lookup"><span data-stu-id="eee3d-137">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="eee3d-138">在 Lync Server 2013 中为持久聊天服务器设置系统和基础结构</span><span class="sxs-lookup"><span data-stu-id="eee3d-138">Setting up systems and infrastructure for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [<span data-ttu-id="eee3d-139">将持久聊天服务器添加到 Lync Server 2013 中的部署</span><span class="sxs-lookup"><span data-stu-id="eee3d-139">Adding Persistent Chat Server to your deployment in Lync Server 2013</span></span>](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [<span data-ttu-id="eee3d-140">在 Lync Server 2013 中安装持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="eee3d-140">Installing Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-installing-persistent-chat-server.md)

  - [<span data-ttu-id="eee3d-141">在 Lync Server 2013 中添加持久聊天管理员</span><span class="sxs-lookup"><span data-stu-id="eee3d-141">Adding a Persistent Chat administrator in Lync Server 2013</span></span>](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [<span data-ttu-id="eee3d-142">在 Lync Server 2013 中配置持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="eee3d-142">Configuring Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server.md)

  - [<span data-ttu-id="eee3d-143">使用 Windows PowerShell cmdlet 配置持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="eee3d-143">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="eee3d-144">在 Lync Server 2013 中使用 Windows PowerShell cmdlet 对持久聊天服务器配置进行故障排除</span><span class="sxs-lookup"><span data-stu-id="eee3d-144">Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="eee3d-145">在 Lync Server 2013 中配置持久聊天服务器以实现高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="eee3d-145">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="eee3d-146">在 Lync Server 2013 中对持久聊天服务器进行故障转移和故障回复</span><span class="sxs-lookup"><span data-stu-id="eee3d-146">Failing over and failing back Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

