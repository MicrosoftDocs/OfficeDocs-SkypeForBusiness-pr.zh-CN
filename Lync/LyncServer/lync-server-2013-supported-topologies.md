---
title: Lync Server 2013 支持的拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported topologies
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425833(v=OCS.15)
ms:contentKeyID: 48183832
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 295d0cfc212fcf09b9752c43e918861f49ec7a88
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-topologies-in-lync-server-2013"></a><span data-ttu-id="7f023-102">Lync Server 2013 中支持的拓扑</span><span class="sxs-lookup"><span data-stu-id="7f023-102">Supported topologies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f023-103">_**主题上次修改时间:** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="7f023-103">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="7f023-104">Lync Server 2013 支持在组织内部部署网站, 并使用 Lync Online 部署 (称为混合部署) 集成本地部署。</span><span class="sxs-lookup"><span data-stu-id="7f023-104">Lync Server 2013 supports deployment of sites on premises in an organization and integration of on-premises deployments with Lync Online deployments, which is known as a hybrid deployment.</span></span> <span data-ttu-id="7f023-105">在混合部署中, 某些用户在本地托管, 某些用户是在线托管的。</span><span class="sxs-lookup"><span data-stu-id="7f023-105">In a hybrid deployment, some users are homed on-premises and some users are homed online.</span></span>

<span data-ttu-id="7f023-106">对于本地部署, Lync Server 2013 支持部署一个或多个可缩放的网站, 以满足高可用性和位置要求。</span><span class="sxs-lookup"><span data-stu-id="7f023-106">For on-premises deployments, Lync Server 2013 supports deployment of one or more sites that can be scaled to meet high availability and location requirements.</span></span> <span data-ttu-id="7f023-107">你可以组织这些网站及其组件, 以满足你的组织的访问权限和复原要求。</span><span class="sxs-lookup"><span data-stu-id="7f023-107">You can structure these sites and their components to meet the access and resiliency requirements of your organization.</span></span>

<span data-ttu-id="7f023-108">Lync Server 2013 内部部署包含以下内容:</span><span class="sxs-lookup"><span data-stu-id="7f023-108">A Lync Server 2013 on-premises deployment consists of the following:</span></span>

  - <span data-ttu-id="7f023-109">你的部署必须包含至少一个中心网站 (也称为数据中心)。</span><span class="sxs-lookup"><span data-stu-id="7f023-109">Your deployment must include at least one central site (also known as a data center).</span></span> <span data-ttu-id="7f023-110">每个中心网站必须包含至少一个企业版前端池或一个标准版服务器。</span><span class="sxs-lookup"><span data-stu-id="7f023-110">Each central site must contain at least one Enterprise Edition Front End pool or one Standard Edition server.</span></span> <span data-ttu-id="7f023-111">其中包括以下内容:</span><span class="sxs-lookup"><span data-stu-id="7f023-111">These consist of the following:</span></span>
    
      - <span data-ttu-id="7f023-112">企业版前端池, 由一个或多个前端服务器 (通常是至少两个前端服务器的可伸缩性) 和单独的后端服务器组成。</span><span class="sxs-lookup"><span data-stu-id="7f023-112">Enterprise Edition Front End pool, which consists of one or more Front End Servers (typically, at least two Front End Servers for scalability) and a separate Back End Server.</span></span> <span data-ttu-id="7f023-113">前端池最多可以包含十二个前端服务器。</span><span class="sxs-lookup"><span data-stu-id="7f023-113">A Front End pool can contain a maximum of twelve Front End Servers.</span></span> <span data-ttu-id="7f023-114">对于多个前端服务器, 需要负载平衡。</span><span class="sxs-lookup"><span data-stu-id="7f023-114">Load balancing is required for multiple Front End Servers.</span></span> <span data-ttu-id="7f023-115">对于 SIP 流量, 我们建议采用 DNS 负载平衡, 但硬件负载平衡也受支持。</span><span class="sxs-lookup"><span data-stu-id="7f023-115">For SIP traffic, we recommend DNS load balancing, but hardware load balancing is also supported.</span></span> <span data-ttu-id="7f023-116">如果你对 SIP 流量使用 DNS 负载平衡, 你仍然需要用于 HTTP 流量的硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="7f023-116">If you use DNS load balancing for SIP traffic, you still need a hardware load balancer for HTTP traffic.</span></span> <span data-ttu-id="7f023-117">我们建议 SQL Server 镜像以实现数据库的高可用性。</span><span class="sxs-lookup"><span data-stu-id="7f023-117">We recommend SQL Server mirroring for high availability of databases.</span></span> <span data-ttu-id="7f023-118">后端数据库需要单独的实例, 但你可以将存档数据库、监视数据库、持久聊天数据库和持久聊天合规性数据库 collocate。</span><span class="sxs-lookup"><span data-stu-id="7f023-118">The back-end database requires a separate instance, but you can collocate the archiving database, monitoring database, persistent chat database, and persistent chat compliance database with it.</span></span> <span data-ttu-id="7f023-119">Lync Server 2013 支持对部署中的文件共享使用共享群集。</span><span class="sxs-lookup"><span data-stu-id="7f023-119">Lync Server 2013 supports the use of a shared cluster for the file shares in your deployment.</span></span> <span data-ttu-id="7f023-120">有关数据库存储要求的详细信息, 请参阅[Lync Server 2013 中的数据库软件支持](lync-server-2013-database-software-support.md)。</span><span class="sxs-lookup"><span data-stu-id="7f023-120">For details about database storage requirements, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="7f023-121">有关文件存储要求的详细信息, 请参阅[Lync Server 2013 中的文件存储支持](lync-server-2013-file-storage-support.md)。</span><span class="sxs-lookup"><span data-stu-id="7f023-121">For details about file storage requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="7f023-122">如果您 collocate Lync Server 数据库, 我们强烈建议评估可能影响可用性和性能的所有因素。</span><span class="sxs-lookup"><span data-stu-id="7f023-122">If you collocate Lync Server databases, we highly recommend assessing all factors that might affect availability and performance.</span></span> <span data-ttu-id="7f023-123">若要验证故障转移功能，建议您测试所有故障转移方案。</span><span class="sxs-lookup"><span data-stu-id="7f023-123">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>

        
        </div>
    
      - <span data-ttu-id="7f023-124">标准版服务器, 其中包括 collocated SQL Server Express 数据库。</span><span class="sxs-lookup"><span data-stu-id="7f023-124">Standard Edition server, which includes a collocated SQL Server Express database.</span></span>

  - <span data-ttu-id="7f023-125">您的部署还可以有一个或多个与中央站点相关联的分支站点。</span><span class="sxs-lookup"><span data-stu-id="7f023-125">Your deployment can also have one or more branch sites associated with a central site.</span></span>

<span data-ttu-id="7f023-126">本部分介绍 Lync Server 2013 部署的网站和组件。</span><span class="sxs-lookup"><span data-stu-id="7f023-126">This section describes the sites and components of a Lync Server 2013 deployment.</span></span> <span data-ttu-id="7f023-127">有关 Lync Server 2013 网站、拓扑和组件规划的详细信息, 请参阅规划文档中 Lync server 2013 和[Lync server 2013 中的参考拓扑](lync-server-2013-reference-topologies.md)[之前必须了解的拓扑基础知识](lync-server-2013-topology-basics-you-must-know-before-planning.md)。</span><span class="sxs-lookup"><span data-stu-id="7f023-127">For details about Lync Server 2013 site, topology, and component planning, see [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) and [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="7f023-128">有关以前版本的组件集成的详细信息, 请参阅[Lync Server 2013 中支持的迁移路径和共存方案](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md)。</span><span class="sxs-lookup"><span data-stu-id="7f023-128">For details about integration of components of previous releases, see [Supported migration paths and coexistence scenarios in Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7f023-129">前端、Edge、中介和控制器服务器角色不支持延伸池。</span><span class="sxs-lookup"><span data-stu-id="7f023-129">Stretched pools are not supported for the Front End, Edge, Mediation, and Director server roles.</span></span>



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a><span data-ttu-id="7f023-130">中心网站拓扑和组件 (内部部署)</span><span class="sxs-lookup"><span data-stu-id="7f023-130">Central Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="7f023-131">虽然中心站点拓扑必须包括一个前端池或一个标准版服务器, 但每个中心网站也可以包含以下内容:</span><span class="sxs-lookup"><span data-stu-id="7f023-131">Although a central site topology must include one Front End pool or one Standard Edition server, each central site can also contain the following:</span></span>

  - <span data-ttu-id="7f023-132">多个前端池, 可以位于同一个域或不同域中。</span><span class="sxs-lookup"><span data-stu-id="7f023-132">Multiple Front End pools, which can be in the same domain or different domains.</span></span> <span data-ttu-id="7f023-133">但是, 前端池中的所有前端服务器和该池的后端服务器必须位于同一个域中。</span><span class="sxs-lookup"><span data-stu-id="7f023-133">However, all Front End Servers in a Front End pool, and the Back End Server for that pool, must be in the same domain.</span></span>

  - <span data-ttu-id="7f023-134">多个标准版服务器。</span><span class="sxs-lookup"><span data-stu-id="7f023-134">Multiple Standard Edition servers.</span></span>

  - <span data-ttu-id="7f023-135">Office Web Apps 服务器, 可与 Lync Server 2013 中的 Office Web 应用程序一起处理 Microsoft PowerPoint 演示文稿的共享和呈现。</span><span class="sxs-lookup"><span data-stu-id="7f023-135">Office Web Apps Server, which is used with Office Web Applications in Lync Server 2013 to handle the sharing and rendering of Microsoft PowerPoint presentations.</span></span>

  - <span data-ttu-id="7f023-136">如果希望部署支持联盟伙伴、公共 IM 连接、可扩展消息传递和状态协议 (XMPP) 网关、远程用户访问、参与会议中的匿名用户, 请在外围网络中使用边缘服务器或边缘池。或 Exchange 统一消息 (UM)。</span><span class="sxs-lookup"><span data-stu-id="7f023-136">Edge Server or Edge pool in your perimeter network, if you want your deployment to support federated partners, public IM connectivity, an extensible messaging and presence protocol (XMPP) gateway, remote user access, participation of anonymous users in meetings, or Exchange Unified Messaging (UM).</span></span> <span data-ttu-id="7f023-137">您不能与 Edge 服务器 collocate 任何其他服务器角色。</span><span class="sxs-lookup"><span data-stu-id="7f023-137">You cannot collocate any other server role with an Edge Server.</span></span> <span data-ttu-id="7f023-138">我们建议在适当的情况下提供 DNS 负载平衡, 但硬件负载平衡也受支持。</span><span class="sxs-lookup"><span data-stu-id="7f023-138">We recommend DNS load balancing, where appropriate, but hardware load balancing is also supported.</span></span> <span data-ttu-id="7f023-139">内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。</span><span class="sxs-lookup"><span data-stu-id="7f023-139">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="7f023-140">您不能在一个边缘接口上使用 DNS 负载平衡的同时，在另一个边缘接口上使用硬件负载平衡。</span><span class="sxs-lookup"><span data-stu-id="7f023-140">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span> <span data-ttu-id="7f023-141">有关负载平衡要求和支持的详细信息, 请参阅部署文档中的 "在 lync server [2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)" 和 "[在 lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)"。</span><span class="sxs-lookup"><span data-stu-id="7f023-141">For details about load balancing requirements and support, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="7f023-142">中介服务器或池, 如果你想要在中心网站上的前端池中支持企业语音或拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="7f023-142">Mediation Server or pool, if you want to support Enterprise Voice or dial-in conferencing in a Front End pool at the central site.</span></span> <span data-ttu-id="7f023-143">根据部署企业语音支持的方式, 你可以 collocate 前端池中的中介服务器 (默认) 或部署独立的中介服务器或池。</span><span class="sxs-lookup"><span data-stu-id="7f023-143">Depending on how you deploy Enterprise Voice support, you can collocate the Mediation Server in a Front End pool (the default) or deploy a stand-alone Mediation Server or pool.</span></span> <span data-ttu-id="7f023-144">你可以使用 DNS、硬件或应用程序负载平衡 (如果适用) 来分配来自中介服务器池的网关对等的流量, 包括 PSTN 网关、IP PBX 或 SIP 中继会话边界控制 (SBC)。有关规划相应中介服务器拓扑的详细信息, 请参阅规划文档中[Lync server 2013 中的中介服务器部署指南](lync-server-2013-deployment-guidelines-for-mediation-server.md)。</span><span class="sxs-lookup"><span data-stu-id="7f023-144">You can use DNS, hardware, or application load balancing (when appropriate) to distribute traffic from a Mediation Server pool’s gateway peer, including a PSTN gateway, IP-PBX, or SIP trunk Session Border Control (SBC).For details about planning the appropriate Mediation Server topology, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="7f023-145">持久聊天服务器, 如果你希望用户能够参与多个基于主题的对话, 这些对话会随着时间的推移而保留。</span><span class="sxs-lookup"><span data-stu-id="7f023-145">Persistent Chat Server, if you want to users to be able to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="7f023-146">为了提供更大的容量和增强的可靠性, 你的拓扑可以包括多台运行持久聊天服务器的计算机。</span><span class="sxs-lookup"><span data-stu-id="7f023-146">To provide more capacity and increased reliability, your topology can include multiple computers running Persistent Chat Server.</span></span> <span data-ttu-id="7f023-147">您不能将持久聊天服务器与企业版池中的其他服务器角色 collocate。</span><span class="sxs-lookup"><span data-stu-id="7f023-147">You cannot collocate Persistent Chat Server with other server roles in an Enterprise pool.</span></span> <span data-ttu-id="7f023-148">但是, 你可以在标准版服务器上 collocate 持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="7f023-148">However, you can collocate Persistent Chat Server on a Standard Edition server.</span></span> <span data-ttu-id="7f023-149">持久聊天需要数据库, 并且如果你实现持久聊天合规性数据库, 但数据库可以与存档数据库、监视数据库或企业版的后端服务器 collocated前端池。</span><span class="sxs-lookup"><span data-stu-id="7f023-149">Persistent chat requires a database and, if you implement persistent chat compliance, a persistent chat compliance database, but the databases can be collocated with the Archiving database, Monitoring database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="7f023-150">有关规划合适的持久聊天服务器拓扑的详细信息, 请参阅规划文档中的在[Lync server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="7f023-150">For details about planning the appropriate Persistent Chat Server topology, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="7f023-151">监视: 如果你想要支持音频/视频体验质量 (QoE) 的数据收集, 并在你的部署中调用企业语音和 A/V 会议的详细录制 (CDR)。</span><span class="sxs-lookup"><span data-stu-id="7f023-151">Monitoring, if you want to support data collection for audio/video Quality of Experience (QoE) and call detail recording (CDR) for Enterprise Voice and A/V conferences in your deployment.</span></span> <span data-ttu-id="7f023-152">或者, 你可以安装 Microsoft System Center Operations Manager (以前称为 Microsoft Operations Manager), 它使用监视 CDR 和 QoE 数据来生成接近的实时警报, 显示通话可靠性和媒体质量的运行状况。</span><span class="sxs-lookup"><span data-stu-id="7f023-152">Optionally, you can install the Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which uses Monitoring CDR and QoE data to generate near real-time alerts that show the health of call reliability and media quality.</span></span> <span data-ttu-id="7f023-153">监视 (部署后) 在前端服务器或标准版服务器上 collocated。</span><span class="sxs-lookup"><span data-stu-id="7f023-153">Monitoring, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="7f023-154">监视需要数据库, 但数据库可以与存档数据库、持久聊天数据库、持久聊天合规数据库或企业版前端池的后端服务器 collocated。</span><span class="sxs-lookup"><span data-stu-id="7f023-154">Monitoring requires a database, but the database can be collocated with the Archiving database, persistent chat database, persistent chat compliance database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span>

  - <span data-ttu-id="7f023-155">存档: 如果你希望在你的部署中存档 IM 通信和会议内容 (出于合规性原因)。</span><span class="sxs-lookup"><span data-stu-id="7f023-155">Archiving, if you want to archive IM communications and meeting content (for compliance reasons) in your deployment.</span></span> <span data-ttu-id="7f023-156">存档 (部署后) 在前端服务器或标准版服务器上 collocated。</span><span class="sxs-lookup"><span data-stu-id="7f023-156">Archiving, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="7f023-157">存档存储需要部署存档数据库或与 Exchange 2013 存储集成。</span><span class="sxs-lookup"><span data-stu-id="7f023-157">Archiving storage requires either deployment of an Archiving database or integration with Exchange 2013 storage.</span></span> <span data-ttu-id="7f023-158">如果同时使用这两个 (即*混合模式*), exchange 2013 存储用于存储托管在 Exchange 2013 上的用户的存档数据, 而存档数据库用于存档部署中所有其他用户的数据。</span><span class="sxs-lookup"><span data-stu-id="7f023-158">If you use both, which is known as *mixed mode*, Exchange 2013 storage is used to store archive data for users who are homed on Exchange 2013, and the Archiving database is used to archive data for all other users in your deployment.</span></span> <span data-ttu-id="7f023-159">如果需要存档数据库, 可以在监视数据库、持久聊天数据库、持久聊天合规数据库或前端池的后端服务器上 collocated 数据库。</span><span class="sxs-lookup"><span data-stu-id="7f023-159">If you require an Archiving database, the database can be collocated on the Monitoring database, persistent chat database, persistent chat compliance database, or on the Back End Server of a Front End pool.</span></span> <span data-ttu-id="7f023-160">有关规划相应的存档拓扑的详细信息, 请参阅规划文档中的[在 Lync Server 2013 中规划存档](lync-server-2013-planning-for-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="7f023-160">For details about planning the appropriate Archiving topology, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="7f023-161">Director 或控制器池, 如果你想要方便将 Lync Server 2013 用户请求恢复和重定向到用户的主池, 它可以是企业版前端池或标准版服务器。</span><span class="sxs-lookup"><span data-stu-id="7f023-161">Director or Director pool, if you want to facilitate resiliency and redirection of Lync Server 2013 user requests to the user’s home pool, which can be either an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="7f023-162">我们建议你在支持外部用户访问的每个中心网站以及你部署一个或多个前端池的每个中心网站中部署 Director 或控制器池。</span><span class="sxs-lookup"><span data-stu-id="7f023-162">We recommend that you deploy a Director or Director pool in each central site that supports external user access and in each central site in which you deploy one or more Front End pools.</span></span> <span data-ttu-id="7f023-163">每个控制器池最多可包含10个控制器。</span><span class="sxs-lookup"><span data-stu-id="7f023-163">Each Director pool can contain a maximum of ten Directors.</span></span> <span data-ttu-id="7f023-164">Director 不能与任何其他服务器角色 collocated。</span><span class="sxs-lookup"><span data-stu-id="7f023-164">A Director cannot be collocated with any other server role.</span></span> <span data-ttu-id="7f023-165">有关规划合适的控制器拓扑的详细信息, 请参阅规划文档中[Lync Server 2013 中的 Director 的方案](lync-server-2013-scenarios-for-the-director.md)。</span><span class="sxs-lookup"><span data-stu-id="7f023-165">For details about planning the appropriate Director topology, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="7f023-166">反向代理 (不是 Lync Server 2013 组件), 但如果您希望支持对联盟用户的 web 内容的共享或支持移动通信, 则该代理是必需的。</span><span class="sxs-lookup"><span data-stu-id="7f023-166">Reverse proxy, which is not a Lync Server 2013 component, but is required if you want to support sharing of web content for federated users or to support Mobility traffic.</span></span> <span data-ttu-id="7f023-167">不能将反向代理服务器与任何 Lync Server 2013 服务器角色 collocate, 但你可以通过在你的组织中用于其他用户的现有反向代理服务器上配置支持, 为 Lync Server 2013 部署实现反向代理支持应用.</span><span class="sxs-lookup"><span data-stu-id="7f023-167">You cannot collocate a reverse proxy server with any Lync Server 2013 server role, but you can implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span> <span data-ttu-id="7f023-168">有关反向代理服务器的详细信息, 请参阅部署文档中[的 Lync Server 2013 的 "设置反向代理服务器](lync-server-2013-setting-up-reverse-proxy-servers.md)"。</span><span class="sxs-lookup"><span data-stu-id="7f023-168">For details about reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7f023-169">在 Lync Server 2013 中, A/V 会议、监视和存档运行在前端服务器上, 不再是单独的服务器角色。</span><span class="sxs-lookup"><span data-stu-id="7f023-169">In Lync Server 2013, A/V Conferencing, Monitoring, and Archiving run on Front End Servers and are no longer separate server roles.</span></span>



</div>

<span data-ttu-id="7f023-170">您在中心网站上部署的所有前端池和标准版服务器都将共享您为中心网站部署的以下任何内容:</span><span class="sxs-lookup"><span data-stu-id="7f023-170">All Front End pools and Standard Edition servers that you deploy at a central site share any of the following that you deploy for the central site:</span></span>

  - <span data-ttu-id="7f023-171">导演或控制器池</span><span class="sxs-lookup"><span data-stu-id="7f023-171">Director or Director pool</span></span>

  - <span data-ttu-id="7f023-172">独立中介服务器或池</span><span class="sxs-lookup"><span data-stu-id="7f023-172">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="7f023-173">Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="7f023-173">Office Web Apps Server</span></span>

  - <span data-ttu-id="7f023-174">边缘服务器或边缘池</span><span class="sxs-lookup"><span data-stu-id="7f023-174">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="7f023-175">持久聊天服务器或池</span><span class="sxs-lookup"><span data-stu-id="7f023-175">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="7f023-176">监控</span><span class="sxs-lookup"><span data-stu-id="7f023-176">Monitoring</span></span>

  - <span data-ttu-id="7f023-177">存档</span><span class="sxs-lookup"><span data-stu-id="7f023-177">Archiving</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7f023-178">如果你想要支持 Exchange 2013 统一消息的集成, 但它不是 Lync Server 2013 网站的组件, 则可以使用 Lync Server 2013 部署实现 Exchange UM 服务器。</span><span class="sxs-lookup"><span data-stu-id="7f023-178">An Exchange UM Server can be implemented with your Lync Server 2013 deployment if you want to support integration of Exchange 2013 Unified Messaging, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="7f023-179">多个中心网站也可以共享在一个中心网站中部署的以下任何内容:</span><span class="sxs-lookup"><span data-stu-id="7f023-179">Multiple central sites can also share any of the following that you deploy in one central site:</span></span>

  - <span data-ttu-id="7f023-180">独立中介服务器或池</span><span class="sxs-lookup"><span data-stu-id="7f023-180">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="7f023-181">边缘服务器或边缘池</span><span class="sxs-lookup"><span data-stu-id="7f023-181">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="7f023-182">持久聊天服务器或池</span><span class="sxs-lookup"><span data-stu-id="7f023-182">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="7f023-183">存档</span><span class="sxs-lookup"><span data-stu-id="7f023-183">Archiving</span></span>

  - <span data-ttu-id="7f023-184">监控</span><span class="sxs-lookup"><span data-stu-id="7f023-184">Monitoring</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7f023-185">Exchange UM 服务器可以通过 Lync Server 2013 部署实现并由多个中心网站共享, 但它不是 Lync Server 2013 网站的组件。</span><span class="sxs-lookup"><span data-stu-id="7f023-185">An Exchange UM Server can be implemented with your Lync Server 2013 deployment and shared by multiple central sites, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="7f023-186">有关 Lync Server 2013 服务器角色和功能的详细信息, 请参阅规划文档中[Lync server 2013 中的服务器角色](lync-server-2013-server-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="7f023-186">For details about Lync Server 2013 server roles and functionality, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md) in the Planning documentation.</span></span>

<span data-ttu-id="7f023-187">有关 Lync Server 2013 服务器 collocation 支持的摘要, 请参阅[Lync server 2013 中的支持的服务器 collocation](lync-server-2013-supported-server-collocation.md)。</span><span class="sxs-lookup"><span data-stu-id="7f023-187">For a summary of Lync Server 2013 server collocation support, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<span data-ttu-id="7f023-188">除了本部分前面所述的服务器角色和功能之外, Lync Server 2013 还有其他组件和选项, 其中包括以下部分或全部选项:</span><span class="sxs-lookup"><span data-stu-id="7f023-188">In addition to the server roles and functionality covered previously in this section, Lync Server 2013 has additional components and options, which can include some or all of the following:</span></span>

  - <span data-ttu-id="7f023-189">防火墙</span><span class="sxs-lookup"><span data-stu-id="7f023-189">Firewalls</span></span>

  - <span data-ttu-id="7f023-190">PSTN 网关 (如果部署企业语音)</span><span class="sxs-lookup"><span data-stu-id="7f023-190">PSTN gateways (if deploying Enterprise Voice)</span></span>

  - <span data-ttu-id="7f023-191">Exchange UM 服务器</span><span class="sxs-lookup"><span data-stu-id="7f023-191">Exchange UM Server</span></span>

  - <span data-ttu-id="7f023-192">DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="7f023-192">DNS load balancing</span></span>

  - <span data-ttu-id="7f023-193">硬件负载平衡器</span><span class="sxs-lookup"><span data-stu-id="7f023-193">Hardware load balancers</span></span>

  - <span data-ttu-id="7f023-194">SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="7f023-194">SQL Server databases</span></span>

  - <span data-ttu-id="7f023-195">文件共享</span><span class="sxs-lookup"><span data-stu-id="7f023-195">File shares</span></span>

<span data-ttu-id="7f023-196">有关所有 Lync Server 2013 功能、组件和选项的详细信息, 请参阅规划文档。</span><span class="sxs-lookup"><span data-stu-id="7f023-196">For details about all of the Lync Server 2013 features, components, and options, see the Planning documentation.</span></span>

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a><span data-ttu-id="7f023-197">分支站点拓扑和组件 (内部部署)</span><span class="sxs-lookup"><span data-stu-id="7f023-197">Branch Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="7f023-198">分支站点与中央站点相关联, 并且分支站点中的每个 Survivable 分支装置都与关联的中心网站中的企业版前端池或标准版服务器相关联。</span><span class="sxs-lookup"><span data-stu-id="7f023-198">A branch site is associated with a central site, and each Survivable Branch Appliance in a branch site is associated with an Enterprise Edition Front End pool or a Standard Edition server in the associated central site.</span></span> <span data-ttu-id="7f023-199">分支站点依赖于中心网站查看大多数功能, 因此分支网站上的组件仅包含以下内容:</span><span class="sxs-lookup"><span data-stu-id="7f023-199">Branch sites depend on the central site for most of their functionality, so components at a branch site contain only the following:</span></span>

  - <span data-ttu-id="7f023-200">Survivable 分支设备, 它将公共交换电话网络 (PSTN) 网关与某些 Lync 服务器功能结合使用。</span><span class="sxs-lookup"><span data-stu-id="7f023-200">A Survivable Branch Appliance, which combines a public switched telephone network (PSTN) gateway with some Lync Server functionality.</span></span> <span data-ttu-id="7f023-201">中介服务器可以与 Survivable 分支设备上的注册机构实例 collocated, 并且你可以部署独立的中介服务器或中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="7f023-201">A Mediation Server can be collocated with the instance of the Registrar on the Survivable Branch Appliance, and you can deploy a stand-alone Mediation Server or pool of Mediation Servers.</span></span>

  - <span data-ttu-id="7f023-202">Survivable 分支服务器, 它是运行安装了 Lync Server 2013 注册机构和中介服务器软件的 Windows Server 的服务器。</span><span class="sxs-lookup"><span data-stu-id="7f023-202">A Survivable Branch Server, which is a server running Windows Server that has Lync Server 2013 Registrar and Mediation Server software installed.</span></span>

  - <span data-ttu-id="7f023-203">独立的 PSTN 网关 (不属于 Survivable 分支装置) 和独立中介服务器。</span><span class="sxs-lookup"><span data-stu-id="7f023-203">A stand-alone PSTN gateway (not part of the Survivable Branch Appliance) and a stand-alone Mediation Server.</span></span>

<span data-ttu-id="7f023-204">Survivable 分支服务器的要求与任何 Lync Server 2013 服务器角色的要求相同。</span><span class="sxs-lookup"><span data-stu-id="7f023-204">The requirements for Survivable Branch Servers are the same as the requirements for any Lync Server 2013 server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

