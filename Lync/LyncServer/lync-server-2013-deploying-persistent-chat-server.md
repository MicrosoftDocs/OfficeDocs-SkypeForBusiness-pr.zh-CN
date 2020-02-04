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
ms.openlocfilehash: 7fe18bf750eabdb1f53c97a349b553da4f13dec8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740862"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="df2e7-102">在 Lync Server 2013 中部署持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="df2e7-102">Deploying Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df2e7-103">_**主题上次修改时间：** 2014-03-31_</span><span class="sxs-lookup"><span data-stu-id="df2e7-103">_**Topic Last Modified:** 2014-03-31_</span></span>

<span data-ttu-id="df2e7-104">Lync server 2013，持久聊天服务器是 Lync Server 2013 基础结构的一部分。</span><span class="sxs-lookup"><span data-stu-id="df2e7-104">Lync Server 2013, Persistent Chat Server is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="df2e7-105">部署持久聊天服务器需要：</span><span class="sxs-lookup"><span data-stu-id="df2e7-105">Deploying Persistent Chat Server requires that you:</span></span>

  - <span data-ttu-id="df2e7-106">使用拓扑生成器定义或导入拓扑，以及随后发布你要部署的组件。</span><span class="sxs-lookup"><span data-stu-id="df2e7-106">Use Topology Builder to define, or import, and subsequently publish your topology and the components that you want to deploy.</span></span>

  - <span data-ttu-id="df2e7-107">准备环境以部署持久聊天服务器组件。</span><span class="sxs-lookup"><span data-stu-id="df2e7-107">Prepare your environment for deploying Persistent Chat Server components.</span></span>

  - <span data-ttu-id="df2e7-108">为你的部署安装和配置持久聊天服务器组件。</span><span class="sxs-lookup"><span data-stu-id="df2e7-108">Install and configure Persistent Chat Server components for your deployment.</span></span>

<span data-ttu-id="df2e7-109">使用 Lync Server 2013 企业版作为单独的池（与企业版前端服务器不 collocated）的持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="df2e7-109">Persistent Chat Server is available with Lync Server 2013 Enterprise Edition as a separate pool (not collocated with the Enterprise Edition Front End Servers).</span></span> <span data-ttu-id="df2e7-110">持久聊天服务器要求企业版池中的 SQL Server 后端服务器存储聊天室内容和其他相关的元数据。</span><span class="sxs-lookup"><span data-stu-id="df2e7-110">Persistent Chat Server requires a SQL Server Back End Server in your Enterprise Edition pool to store the chat room content and other relevant metadata.</span></span> <span data-ttu-id="df2e7-111">我们建议你在专用 SQL Server 后端服务器上安装**PersistentChatStore** ，但支持在同一 sql server 实例上 Collocating Lync Server 2013 后端服务器和**PersistentChatStore** 。</span><span class="sxs-lookup"><span data-stu-id="df2e7-111">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server, although collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance is supported.</span></span>

<span data-ttu-id="df2e7-112">持久聊天服务器也可以与 Lync Server 2013 标准版一起部署。</span><span class="sxs-lookup"><span data-stu-id="df2e7-112">Persistent Chat Server can also be deployed with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="df2e7-113">在这种情况下， **PersistentChatService**前端服务器在标准版计算机上 Collocated， **PersistentChatStore**后端服务器可以部署在本地 SQL Server Express 实例上。</span><span class="sxs-lookup"><span data-stu-id="df2e7-113">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition computer, and the **PersistentChatStore** Back End Server can be deployed on the local SQL Server Express instance.</span></span>

<span data-ttu-id="df2e7-114">有关支持的 colocation 配置的详细信息，请参阅[Lync server 2013 中的支持的服务器 collocation](lync-server-2013-supported-server-collocation.md)。</span><span class="sxs-lookup"><span data-stu-id="df2e7-114">For details about supported colocation configurations, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="df2e7-115">我们不支持持久聊天服务器&nbsp;标准版的高可用性。</span><span class="sxs-lookup"><span data-stu-id="df2e7-115">We do not support high availability for Persistent Chat Server&nbsp;Standard Edition.</span></span> <span data-ttu-id="df2e7-116">性能和规模将受到限制。</span><span class="sxs-lookup"><span data-stu-id="df2e7-116">Performance and scale will be limited.</span></span> <span data-ttu-id="df2e7-117">此外，我们仅支持新的持久聊天&nbsp;服务器标准版服务器。</span><span class="sxs-lookup"><span data-stu-id="df2e7-117">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server.</span></span> <span data-ttu-id="df2e7-118">我们不支持将 Lync Server 2010、群组聊天服务器升级到 Lync Server 2013&nbsp;持久聊天服务器&nbsp;标准版。</span><span class="sxs-lookup"><span data-stu-id="df2e7-118">We do not support upgrading Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<span data-ttu-id="df2e7-119">如果你的组织需要合规性支持，你可以在永久聊天服务器前端服务器上安装持久聊天服务器合规性服务。</span><span class="sxs-lookup"><span data-stu-id="df2e7-119">If your organization requires compliance support, you can install the Persistent Chat Server Compliance service on the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="df2e7-120">需要单独的数据库才能实现合规性。</span><span class="sxs-lookup"><span data-stu-id="df2e7-120">A separate database is required for compliance.</span></span>

<span data-ttu-id="df2e7-121">每个拓扑至少需要安装有 Lync Server 2013 的服务器和安装有 SQL Server 数据库软件的服务器。</span><span class="sxs-lookup"><span data-stu-id="df2e7-121">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span>

<span data-ttu-id="df2e7-122">使用拓扑生成器将持久聊天服务器添加到 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="df2e7-122">Use Topology Builder to add Persistent Chat Server to your Lync Server 2013 deployments.</span></span> <span data-ttu-id="df2e7-123">你可以选择使用拓扑生成器添加一个或多个持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="df2e7-123">You can choose to add one or more Persistent Chat Server pools using Topology Builder.</span></span> <span data-ttu-id="df2e7-124">按照相同的部署说明部署多个持久聊天服务器池，就像处理任何池一样。</span><span class="sxs-lookup"><span data-stu-id="df2e7-124">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool.</span></span> <span data-ttu-id="df2e7-125">有关详细信息，请参阅部署文档中的 "[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) "。</span><span class="sxs-lookup"><span data-stu-id="df2e7-125">For details, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="df2e7-126">有关可用拓扑和安装持久聊天服务器的技术和软件要求的详细信息，请参阅规划文档中的 "[在 lync server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)"、"计划文档"、"部署文档" 或 "操作文档" 中的 "永久聊天服务器" 的[2013 工作方式](lync-server-2013-how-persistent-chat-server-works.md)，以及可支持性文档中的[lync server 2013 支持的硬件](lync-server-2013-supported-hardware.md)。</span><span class="sxs-lookup"><span data-stu-id="df2e7-126">For details about available topologies and the technical and software requirements for installing Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation, and [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

<span data-ttu-id="df2e7-127">有关获取证书、创建 SQL Server 数据库和创建文件存储的详细信息，请参阅部署文档中的 "[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) "。</span><span class="sxs-lookup"><span data-stu-id="df2e7-127">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="df2e7-128">单个持久聊天服务器前端服务器可以支持20000活动用户。</span><span class="sxs-lookup"><span data-stu-id="df2e7-128">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="df2e7-129">你可以拥有最多4个活动前端服务器的持久聊天服务器池，这些服务器总共支持80000并行用户。</span><span class="sxs-lookup"><span data-stu-id="df2e7-129">You can have a Persistent Chat Server pool with up to 4 active Front End Servers supporting a total of 80,000 concurrent users.</span></span>

<span data-ttu-id="df2e7-130">虚拟服务器也支持持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="df2e7-130">Persistent Chat Server is also supported on a virtual server.</span></span> <span data-ttu-id="df2e7-131">如果虚拟服务器与物理服务器的规范相匹配，则该虚拟服务器最多可以支持最多20000个并发用户。</span><span class="sxs-lookup"><span data-stu-id="df2e7-131">The virtual server can support up to 20,000 concurrent users if it matches the specifications of the physical server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="df2e7-132">持久聊天服务器必须安装在 NTFS 文件系统上才能帮助强制实施文件系统安全。</span><span class="sxs-lookup"><span data-stu-id="df2e7-132">Persistent Chat Server must be installed on an NTFS file system to help enforce file system security.</span></span> <span data-ttu-id="df2e7-133">FAT32 不是持久聊天服务器支持的文件系统。</span><span class="sxs-lookup"><span data-stu-id="df2e7-133">FAT32 is not a supported file system for Persistent Chat Server.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="df2e7-134">本节内容</span><span class="sxs-lookup"><span data-stu-id="df2e7-134">In This Section</span></span>

  - [<span data-ttu-id="df2e7-135">在 Lync Server 2013 中持久聊天服务器的工作方式</span><span class="sxs-lookup"><span data-stu-id="df2e7-135">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="df2e7-136">Lync Server 2013 中的持久聊天服务器的部署清单</span><span class="sxs-lookup"><span data-stu-id="df2e7-136">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [<span data-ttu-id="df2e7-137">Lync Server 2013 中持久聊天服务器的技术要求</span><span class="sxs-lookup"><span data-stu-id="df2e7-137">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="df2e7-138">在 Lync Server 2013 中设置持久聊天服务器的系统和基础结构</span><span class="sxs-lookup"><span data-stu-id="df2e7-138">Setting up systems and infrastructure for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [<span data-ttu-id="df2e7-139">在 Lync Server 2013 中将持久聊天服务器添加到部署</span><span class="sxs-lookup"><span data-stu-id="df2e7-139">Adding Persistent Chat Server to your deployment in Lync Server 2013</span></span>](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [<span data-ttu-id="df2e7-140">在 Lync Server 2013 中安装持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="df2e7-140">Installing Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-installing-persistent-chat-server.md)

  - [<span data-ttu-id="df2e7-141">在 Lync Server 2013 中添加持久聊天管理员</span><span class="sxs-lookup"><span data-stu-id="df2e7-141">Adding a Persistent Chat administrator in Lync Server 2013</span></span>](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [<span data-ttu-id="df2e7-142">在 Lync Server 2013 中配置持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="df2e7-142">Configuring Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server.md)

  - [<span data-ttu-id="df2e7-143">使用 Windows PowerShell Cmdlet 配置持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="df2e7-143">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="df2e7-144">在 Lync Server 2013 中使用 Windows PowerShell Cmdlet 排查持久聊天服务器配置故障</span><span class="sxs-lookup"><span data-stu-id="df2e7-144">Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="df2e7-145">在 Lync Server 2013 中为持久聊天服务器配置高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="df2e7-145">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="df2e7-146">在 Lync Server 2013 中对持久聊天服务器进行故障转移和故障回复</span><span class="sxs-lookup"><span data-stu-id="df2e7-146">Failing over and failing back Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

