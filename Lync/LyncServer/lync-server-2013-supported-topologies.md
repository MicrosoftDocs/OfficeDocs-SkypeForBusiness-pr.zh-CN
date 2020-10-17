---
title: Lync Server 2013 支持的拓扑
description: Lync Server 2013 支持的拓扑。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported topologies
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425833(v=OCS.15)
ms:contentKeyID: 48183832
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39c19577fbda7e377e145abfd473d2cf8e6d4a1a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558018"
---
# <a name="supported-topologies-in-lync-server-2013"></a><span data-ttu-id="a3f00-103">Lync Server 2013 中支持的拓扑</span><span class="sxs-lookup"><span data-stu-id="a3f00-103">Supported topologies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3f00-104">_**上次修改的主题：** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="a3f00-104">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="a3f00-105">Lync Server 2013 支持在组织内部部署网站，并将本地部署与 Lync Online 部署（称为混合部署）集成。</span><span class="sxs-lookup"><span data-stu-id="a3f00-105">Lync Server 2013 supports deployment of sites on premises in an organization and integration of on-premises deployments with Lync Online deployments, which is known as a hybrid deployment.</span></span> <span data-ttu-id="a3f00-106">在混合部署中，有些用户驻留在内部部署中，有些用户驻留在联机部署中。</span><span class="sxs-lookup"><span data-stu-id="a3f00-106">In a hybrid deployment, some users are homed on-premises and some users are homed online.</span></span>

<span data-ttu-id="a3f00-107">对于本地部署，Lync Server 2013 支持部署一个或多个可进行扩展的网站，以满足高可用性和位置要求。</span><span class="sxs-lookup"><span data-stu-id="a3f00-107">For on-premises deployments, Lync Server 2013 supports deployment of one or more sites that can be scaled to meet high availability and location requirements.</span></span> <span data-ttu-id="a3f00-108">可以构造这些站点及其组件来满足组织的访问和复原要求。</span><span class="sxs-lookup"><span data-stu-id="a3f00-108">You can structure these sites and their components to meet the access and resiliency requirements of your organization.</span></span>

<span data-ttu-id="a3f00-109">Lync Server 2013 本地部署包含以下内容：</span><span class="sxs-lookup"><span data-stu-id="a3f00-109">A Lync Server 2013 on-premises deployment consists of the following:</span></span>

  - <span data-ttu-id="a3f00-p103">部署中必须至少包含一个中央站点（也称为数据中心）。每个中央站点必须至少包含一个 Enterprise Edition 前端池或一个 Standard Edition 服务器。由以下内容构成：</span><span class="sxs-lookup"><span data-stu-id="a3f00-p103">Your deployment must include at least one central site (also known as a data center). Each central site must contain at least one Enterprise Edition Front End pool or one Standard Edition server. These consist of the following:</span></span>
    
      - <span data-ttu-id="a3f00-113">Enterprise Edition 前端池，它由一台或多台前端服务器（出于可伸缩性考虑，通常至少包括两台前端服务器）和一台单独的后端服务器构成。</span><span class="sxs-lookup"><span data-stu-id="a3f00-113">Enterprise Edition Front End pool, which consists of one or more Front End Servers (typically, at least two Front End Servers for scalability) and a separate Back End Server.</span></span> <span data-ttu-id="a3f00-114">前端池最多可以包含12台前端服务器。</span><span class="sxs-lookup"><span data-stu-id="a3f00-114">A Front End pool can contain a maximum of twelve Front End Servers.</span></span> <span data-ttu-id="a3f00-115">多台前端服务器需要负载平衡。</span><span class="sxs-lookup"><span data-stu-id="a3f00-115">Load balancing is required for multiple Front End Servers.</span></span> <span data-ttu-id="a3f00-116">对于 SIP 流量，建议使用 DNS 负载平衡，但也支持硬件负载平衡。</span><span class="sxs-lookup"><span data-stu-id="a3f00-116">For SIP traffic, we recommend DNS load balancing, but hardware load balancing is also supported.</span></span> <span data-ttu-id="a3f00-117">如果对 SIP 流量使用 DNS 负载平衡，您仍需对 HTTP 流量使用硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="a3f00-117">If you use DNS load balancing for SIP traffic, you still need a hardware load balancer for HTTP traffic.</span></span> <span data-ttu-id="a3f00-118">我们建议 SQL Server 镜像以实现数据库的高可用性。</span><span class="sxs-lookup"><span data-stu-id="a3f00-118">We recommend SQL Server mirroring for high availability of databases.</span></span> <span data-ttu-id="a3f00-119">后端数据库需要一个单独的实例，但可将存档数据库、监控数据库、持久聊天数据库和持久聊天合规性服务器与其并置。</span><span class="sxs-lookup"><span data-stu-id="a3f00-119">The back-end database requires a separate instance, but you can collocate the archiving database, monitoring database, persistent chat database, and persistent chat compliance database with it.</span></span> <span data-ttu-id="a3f00-120">Lync Server 2013 支持对部署中的文件共享使用共享群集。</span><span class="sxs-lookup"><span data-stu-id="a3f00-120">Lync Server 2013 supports the use of a shared cluster for the file shares in your deployment.</span></span> <span data-ttu-id="a3f00-121">有关数据库存储要求的详细信息，请参阅 [Lync Server 2013 中的数据库软件支持](lync-server-2013-database-software-support.md)。</span><span class="sxs-lookup"><span data-stu-id="a3f00-121">For details about database storage requirements, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="a3f00-122">有关文件存储要求的详细信息，请参阅 [Lync Server 2013 中的文件存储支持](lync-server-2013-file-storage-support.md)。</span><span class="sxs-lookup"><span data-stu-id="a3f00-122">For details about file storage requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="a3f00-123">如果您并置 Lync Server 数据库，我们强烈建议评估可能影响可用性和性能的所有因素。</span><span class="sxs-lookup"><span data-stu-id="a3f00-123">If you collocate Lync Server databases, we highly recommend assessing all factors that might affect availability and performance.</span></span> <span data-ttu-id="a3f00-124">若要验证故障转移功能，建议您测试所有故障转移方案。</span><span class="sxs-lookup"><span data-stu-id="a3f00-124">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>

        
        </div>
    
      - <span data-ttu-id="a3f00-125">Standard Edition Server，包含一个并置的 SQL Server Express 数据库。</span><span class="sxs-lookup"><span data-stu-id="a3f00-125">Standard Edition server, which includes a collocated SQL Server Express database.</span></span>

  - <span data-ttu-id="a3f00-126">部署中还可以有一个或多个与中央站点关联的分支站点。</span><span class="sxs-lookup"><span data-stu-id="a3f00-126">Your deployment can also have one or more branch sites associated with a central site.</span></span>

<span data-ttu-id="a3f00-127">本节介绍 Lync Server 2013 部署的网站和组件。</span><span class="sxs-lookup"><span data-stu-id="a3f00-127">This section describes the sites and components of a Lync Server 2013 deployment.</span></span> <span data-ttu-id="a3f00-128">有关 Lync Server 2013 站点、拓扑和组件规划的详细信息，请参阅规划文档中规划 lync server 2013 和[Lync server 2013 中的参考拓扑](lync-server-2013-reference-topologies.md)[之前必须了解的拓扑基础知识](lync-server-2013-topology-basics-you-must-know-before-planning.md)。</span><span class="sxs-lookup"><span data-stu-id="a3f00-128">For details about Lync Server 2013 site, topology, and component planning, see [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) and [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="a3f00-129">有关以前版本的组件集成的详细信息，请参阅 [Lync Server 2013 中支持的迁移路径和共存方案](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md)。</span><span class="sxs-lookup"><span data-stu-id="a3f00-129">For details about integration of components of previous releases, see [Supported migration paths and coexistence scenarios in Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a3f00-130">前端、边缘、中介和控制器服务器角色不支持延伸池。</span><span class="sxs-lookup"><span data-stu-id="a3f00-130">Stretched pools are not supported for the Front End, Edge, Mediation, and Director server roles.</span></span>



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a><span data-ttu-id="a3f00-131">中央站点拓扑和组件（本地）</span><span class="sxs-lookup"><span data-stu-id="a3f00-131">Central Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="a3f00-132">尽管中央站点拓扑必须包含一个前端池或一个 Standard Edition 服务器，但每个中央站点还可以包含以下内容：</span><span class="sxs-lookup"><span data-stu-id="a3f00-132">Although a central site topology must include one Front End pool or one Standard Edition server, each central site can also contain the following:</span></span>

  - <span data-ttu-id="a3f00-p107">多个前端池，可位于同一个域或不同的域。尽管如此，前端池中的所有前端服务器和该池的后端服务器必须位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="a3f00-p107">Multiple Front End pools, which can be in the same domain or different domains. However, all Front End Servers in a Front End pool, and the Back End Server for that pool, must be in the same domain.</span></span>

  - <span data-ttu-id="a3f00-135">多个 Standard Edition 服务器。</span><span class="sxs-lookup"><span data-stu-id="a3f00-135">Multiple Standard Edition servers.</span></span>

  - <span data-ttu-id="a3f00-136">Office Web Apps Server，用于 Lync Server 2013 中的 Office Web 应用程序，用于处理 Microsoft PowerPoint 演示文稿的共享和呈现。</span><span class="sxs-lookup"><span data-stu-id="a3f00-136">Office Web Apps Server, which is used with Office Web Applications in Lync Server 2013 to handle the sharing and rendering of Microsoft PowerPoint presentations.</span></span>

  - <span data-ttu-id="a3f00-137">边缘服务器或边缘池在外围网络中，如果您希望部署支持联盟伙伴、公共 IM 连接、可扩展消息和状态协议 (XMPP) 网关、远程用户访问、参与会议的匿名用户或 Exchange 统一消息 (UM) 。</span><span class="sxs-lookup"><span data-stu-id="a3f00-137">Edge Server or Edge pool in your perimeter network, if you want your deployment to support federated partners, public IM connectivity, an extensible messaging and presence protocol (XMPP) gateway, remote user access, participation of anonymous users in meetings, or Exchange Unified Messaging (UM).</span></span> <span data-ttu-id="a3f00-138">不能将其他任何服务器角色与边缘服务器并置。</span><span class="sxs-lookup"><span data-stu-id="a3f00-138">You cannot collocate any other server role with an Edge Server.</span></span> <span data-ttu-id="a3f00-139">建议根据需要使用 DNS 负载平衡，但也支持硬件负载平衡。</span><span class="sxs-lookup"><span data-stu-id="a3f00-139">We recommend DNS load balancing, where appropriate, but hardware load balancing is also supported.</span></span> <span data-ttu-id="a3f00-140">内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。</span><span class="sxs-lookup"><span data-stu-id="a3f00-140">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="a3f00-141">您不能在一个边缘接口上使用 DNS 负载平衡的同时，在另一个边缘接口上使用硬件负载平衡。</span><span class="sxs-lookup"><span data-stu-id="a3f00-141">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span> <span data-ttu-id="a3f00-142">有关负载平衡要求和支持的详细信息，请参阅部署文档中的规划文档和在[Lync server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)中的 "[在 lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)"。</span><span class="sxs-lookup"><span data-stu-id="a3f00-142">For details about load balancing requirements and support, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="a3f00-143">中介服务器或池，如果您想要在中央站点的前端池中支持企业语音或电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="a3f00-143">Mediation Server or pool, if you want to support Enterprise Voice or dial-in conferencing in a Front End pool at the central site.</span></span> <span data-ttu-id="a3f00-144">根据您部署企业语音支持的方式，您可以在 (默认) 或部署独立中介服务器或池的前端池中并置中介服务器。</span><span class="sxs-lookup"><span data-stu-id="a3f00-144">Depending on how you deploy Enterprise Voice support, you can collocate the Mediation Server in a Front End pool (the default) or deploy a stand-alone Mediation Server or pool.</span></span> <span data-ttu-id="a3f00-145">当适当的) 从中介服务器池的网关对等分发流量（包括 PSTN 网关、ip-pbx 或 SIP 中继会话边界控制 (SBC) ）时，可以使用 DNS、硬件或应用程序负载平衡 (。有关规划相应中介服务器拓扑的详细信息，请参阅规划文档中的 [Lync server 2013 中的中介服务器部署指南](lync-server-2013-deployment-guidelines-for-mediation-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="a3f00-145">You can use DNS, hardware, or application load balancing (when appropriate) to distribute traffic from a Mediation Server pool’s gateway peer, including a PSTN gateway, IP-PBX, or SIP trunk Session Border Control (SBC).For details about planning the appropriate Mediation Server topology, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="a3f00-146">持久聊天服务器（如果您希望用户能够参与在一段时间内保持的基于主题的会话）。</span><span class="sxs-lookup"><span data-stu-id="a3f00-146">Persistent Chat Server, if you want to users to be able to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="a3f00-147">为了提供更大的容量并提高可靠性，拓扑可以包含多台运行持久聊天服务器的计算机。</span><span class="sxs-lookup"><span data-stu-id="a3f00-147">To provide more capacity and increased reliability, your topology can include multiple computers running Persistent Chat Server.</span></span> <span data-ttu-id="a3f00-148">您不能并置持久聊天服务器与企业版池中的其他服务器角色。</span><span class="sxs-lookup"><span data-stu-id="a3f00-148">You cannot collocate Persistent Chat Server with other server roles in an Enterprise pool.</span></span> <span data-ttu-id="a3f00-149">不过，您可以在 Standard Edition 服务器上并置持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="a3f00-149">However, you can collocate Persistent Chat Server on a Standard Edition server.</span></span> <span data-ttu-id="a3f00-150">持久聊天需要一个数据库，如果实现持久聊天合规性，还需要一个持久聊天合规性数据库，但这些数据库可以与存档数据库或监控数据库并置，或者位于 Enterprise Edition 前端池的后端服务器上。</span><span class="sxs-lookup"><span data-stu-id="a3f00-150">Persistent chat requires a database and, if you implement persistent chat compliance, a persistent chat compliance database, but the databases can be collocated with the Archiving database, Monitoring database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="a3f00-151">有关规划适当的持久聊天服务器拓扑的详细信息，请参阅规划文档中的在 [Lync server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="a3f00-151">For details about planning the appropriate Persistent Chat Server topology, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="a3f00-152">监控（如果要在部署中收集有关企业语音和 A/V 会议的音频/视频用户体验质量 (QoE) 和呼叫详细记录 (CDR) 的数据）。</span><span class="sxs-lookup"><span data-stu-id="a3f00-152">Monitoring, if you want to support data collection for audio/video Quality of Experience (QoE) and call detail recording (CDR) for Enterprise Voice and A/V conferences in your deployment.</span></span> <span data-ttu-id="a3f00-153">（可选）可以将 Microsoft System Center Operations Manager 安装 (以前的 Microsoft Operations Manager) ，它使用监视 CDR 和 QoE 数据生成临近的实时警报，以显示呼叫可靠性和媒体质量的运行状况。</span><span class="sxs-lookup"><span data-stu-id="a3f00-153">Optionally, you can install the Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which uses Monitoring CDR and QoE data to generate near real-time alerts that show the health of call reliability and media quality.</span></span> <span data-ttu-id="a3f00-154">监控功能（如果部署）可位于前端服务器或 Standard Edition 服务器上。</span><span class="sxs-lookup"><span data-stu-id="a3f00-154">Monitoring, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="a3f00-155">监控需要一个数据库，但该数据库可与存档数据库、持久聊天数据库或持久聊天合规性数据库并置，或者位于 Enterprise Edition 前端池的后端服务器上。</span><span class="sxs-lookup"><span data-stu-id="a3f00-155">Monitoring requires a database, but the database can be collocated with the Archiving database, persistent chat database, persistent chat compliance database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span>

  - <span data-ttu-id="a3f00-156">存档（如果要在部署中存档 IM 通信和会议内容（出于合规性考虑））。</span><span class="sxs-lookup"><span data-stu-id="a3f00-156">Archiving, if you want to archive IM communications and meeting content (for compliance reasons) in your deployment.</span></span> <span data-ttu-id="a3f00-157">存档（如果部署）可并置在前端服务器或 Standard Edition 服务器上。</span><span class="sxs-lookup"><span data-stu-id="a3f00-157">Archiving, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="a3f00-158">存档存储需要部署存档数据库或与 Exchange 2013 存储集成。</span><span class="sxs-lookup"><span data-stu-id="a3f00-158">Archiving storage requires either deployment of an Archiving database or integration with Exchange 2013 storage.</span></span> <span data-ttu-id="a3f00-159">如果同时使用这两种方式（称为 *混合模式*），则 exchange 2013 存储用于存储驻留在 Exchange 2013 上的用户的存档数据，而存档数据库用于存档部署中所有其他用户的数据。</span><span class="sxs-lookup"><span data-stu-id="a3f00-159">If you use both, which is known as *mixed mode*, Exchange 2013 storage is used to store archive data for users who are homed on Exchange 2013, and the Archiving database is used to archive data for all other users in your deployment.</span></span> <span data-ttu-id="a3f00-160">如果需要存档数据库，则该数据库可以与监控数据库、持久聊天数据库或持久聊天合规性数据库并置，或者位于前端池的后端服务器上。</span><span class="sxs-lookup"><span data-stu-id="a3f00-160">If you require an Archiving database, the database can be collocated on the Monitoring database, persistent chat database, persistent chat compliance database, or on the Back End Server of a Front End pool.</span></span> <span data-ttu-id="a3f00-161">有关规划适当的存档拓扑的详细信息，请参阅规划文档中的在 [Lync Server 2013 中规划存档](lync-server-2013-planning-for-archiving.md) 。</span><span class="sxs-lookup"><span data-stu-id="a3f00-161">For details about planning the appropriate Archiving topology, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="a3f00-162">Director 或 Director pool，如果要促进 Lync Server 2013 用户请求对用户主池（可以是企业版前端池或 Standard Edition 服务器）的恢复和重定向。</span><span class="sxs-lookup"><span data-stu-id="a3f00-162">Director or Director pool, if you want to facilitate resiliency and redirection of Lync Server 2013 user requests to the user’s home pool, which can be either an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="a3f00-163">我们建议您在支持外部用户访问的每个中央站点和部署一个或多个前端池的每个中央站点部署控制器或控制器池。</span><span class="sxs-lookup"><span data-stu-id="a3f00-163">We recommend that you deploy a Director or Director pool in each central site that supports external user access and in each central site in which you deploy one or more Front End pools.</span></span> <span data-ttu-id="a3f00-164">每个控制器池最多可包含十个控制器。</span><span class="sxs-lookup"><span data-stu-id="a3f00-164">Each Director pool can contain a maximum of ten Directors.</span></span> <span data-ttu-id="a3f00-165">控制器无法与其他任何服务器角色并置。</span><span class="sxs-lookup"><span data-stu-id="a3f00-165">A Director cannot be collocated with any other server role.</span></span> <span data-ttu-id="a3f00-166">有关规划相应控制器拓扑的详细信息，请参阅规划文档中的 [Lync Server 2013 中的 Director 方案](lync-server-2013-scenarios-for-the-director.md) 。</span><span class="sxs-lookup"><span data-stu-id="a3f00-166">For details about planning the appropriate Director topology, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="a3f00-167">反向代理不是 Lync Server 2013 组件，但如果要支持联合用户共享 web 内容或支持移动流量，则此代理是必需的。</span><span class="sxs-lookup"><span data-stu-id="a3f00-167">Reverse proxy, which is not a Lync Server 2013 component, but is required if you want to support sharing of web content for federated users or to support Mobility traffic.</span></span> <span data-ttu-id="a3f00-168">您不能并置具有任何 Lync Server 2013 服务器角色的反向代理服务器，但您可以通过在组织中对其他应用程序使用的现有反向代理服务器上配置支持，从而实现对 Lync Server 2013 部署的反向代理支持。</span><span class="sxs-lookup"><span data-stu-id="a3f00-168">You cannot collocate a reverse proxy server with any Lync Server 2013 server role, but you can implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span> <span data-ttu-id="a3f00-169">有关反向代理服务器的详细信息，请参阅部署文档中的 [为 Lync Server 2013 设置反向代理服务器](lync-server-2013-setting-up-reverse-proxy-servers.md) 。</span><span class="sxs-lookup"><span data-stu-id="a3f00-169">For details about reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a3f00-170">在 Lync Server 2013 中，A/V 会议、监视和存档运行在前端服务器上，不再是单独的服务器角色。</span><span class="sxs-lookup"><span data-stu-id="a3f00-170">In Lync Server 2013, A/V Conferencing, Monitoring, and Archiving run on Front End Servers and are no longer separate server roles.</span></span>



</div>

<span data-ttu-id="a3f00-171">在中央站点部署的所有前端池和 Standard Edition Server 共享为中央站点部署的以下任何内容：</span><span class="sxs-lookup"><span data-stu-id="a3f00-171">All Front End pools and Standard Edition servers that you deploy at a central site share any of the following that you deploy for the central site:</span></span>

  - <span data-ttu-id="a3f00-172">控制器或控制器池</span><span class="sxs-lookup"><span data-stu-id="a3f00-172">Director or Director pool</span></span>

  - <span data-ttu-id="a3f00-173">独立的中介服务器或池</span><span class="sxs-lookup"><span data-stu-id="a3f00-173">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="a3f00-174">Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="a3f00-174">Office Web Apps Server</span></span>

  - <span data-ttu-id="a3f00-175">边缘服务器或边缘池</span><span class="sxs-lookup"><span data-stu-id="a3f00-175">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="a3f00-176">持久聊天服务器或池</span><span class="sxs-lookup"><span data-stu-id="a3f00-176">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="a3f00-177">监控</span><span class="sxs-lookup"><span data-stu-id="a3f00-177">Monitoring</span></span>

  - <span data-ttu-id="a3f00-178">存档</span><span class="sxs-lookup"><span data-stu-id="a3f00-178">Archiving</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a3f00-179">如果要支持 Exchange 2013 统一消息的集成，但它不是 Lync Server 2013 网站的组件，则可以在 Lync Server 2013 部署中实施 Exchange UM 服务器。</span><span class="sxs-lookup"><span data-stu-id="a3f00-179">An Exchange UM Server can be implemented with your Lync Server 2013 deployment if you want to support integration of Exchange 2013 Unified Messaging, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="a3f00-180">多个中央站点还可以共享在一个中央站点部署的以下任何内容：</span><span class="sxs-lookup"><span data-stu-id="a3f00-180">Multiple central sites can also share any of the following that you deploy in one central site:</span></span>

  - <span data-ttu-id="a3f00-181">独立的中介服务器或池</span><span class="sxs-lookup"><span data-stu-id="a3f00-181">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="a3f00-182">边缘服务器或边缘池</span><span class="sxs-lookup"><span data-stu-id="a3f00-182">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="a3f00-183">持久聊天服务器或池</span><span class="sxs-lookup"><span data-stu-id="a3f00-183">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="a3f00-184">存档</span><span class="sxs-lookup"><span data-stu-id="a3f00-184">Archiving</span></span>

  - <span data-ttu-id="a3f00-185">监控</span><span class="sxs-lookup"><span data-stu-id="a3f00-185">Monitoring</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a3f00-186">Exchange UM 服务器可通过 Lync Server 2013 部署实施，并由多个中央站点共享，但它不是 Lync Server 2013 网站的组件。</span><span class="sxs-lookup"><span data-stu-id="a3f00-186">An Exchange UM Server can be implemented with your Lync Server 2013 deployment and shared by multiple central sites, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="a3f00-187">有关 Lync Server 2013 服务器角色和功能的详细信息，请参阅规划文档中的 " [Lync server 2013 中的服务器角色](lync-server-2013-server-roles.md) "。</span><span class="sxs-lookup"><span data-stu-id="a3f00-187">For details about Lync Server 2013 server roles and functionality, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md) in the Planning documentation.</span></span>

<span data-ttu-id="a3f00-188">有关 Lync Server 2013 Server 并置支持的摘要，请参阅 [Lync server 2013 中的受支持的服务器并置](lync-server-2013-supported-server-collocation.md)。</span><span class="sxs-lookup"><span data-stu-id="a3f00-188">For a summary of Lync Server 2013 server collocation support, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<span data-ttu-id="a3f00-189">除了本节前面所述的服务器角色和功能之外，Lync Server 2013 还提供了其他组件和选项，其中可能包括以下部分或全部选项：</span><span class="sxs-lookup"><span data-stu-id="a3f00-189">In addition to the server roles and functionality covered previously in this section, Lync Server 2013 has additional components and options, which can include some or all of the following:</span></span>

  - <span data-ttu-id="a3f00-190">道</span><span class="sxs-lookup"><span data-stu-id="a3f00-190">Firewalls</span></span>

  - <span data-ttu-id="a3f00-191">PSTN 网关（如果部署企业语音）</span><span class="sxs-lookup"><span data-stu-id="a3f00-191">PSTN gateways (if deploying Enterprise Voice)</span></span>

  - <span data-ttu-id="a3f00-192">Exchange UM 服务器</span><span class="sxs-lookup"><span data-stu-id="a3f00-192">Exchange UM Server</span></span>

  - <span data-ttu-id="a3f00-193">DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="a3f00-193">DNS load balancing</span></span>

  - <span data-ttu-id="a3f00-194">硬件负载平衡器</span><span class="sxs-lookup"><span data-stu-id="a3f00-194">Hardware load balancers</span></span>

  - <span data-ttu-id="a3f00-195">SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="a3f00-195">SQL Server databases</span></span>

  - <span data-ttu-id="a3f00-196">文件共享</span><span class="sxs-lookup"><span data-stu-id="a3f00-196">File shares</span></span>

<span data-ttu-id="a3f00-197">有关所有 Lync Server 2013 功能、组件和选项的详细信息，请参阅规划文档。</span><span class="sxs-lookup"><span data-stu-id="a3f00-197">For details about all of the Lync Server 2013 features, components, and options, see the Planning documentation.</span></span>

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a><span data-ttu-id="a3f00-198">分支站点拓扑和组件（本地）</span><span class="sxs-lookup"><span data-stu-id="a3f00-198">Branch Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="a3f00-p115">分支站点与中央站点关联，分支站点中的每个 Survivable Branch Appliance 均与关联中央站点中的 Enterprise Edition 前端池或 Standard Edition 服务器相关联。分支站点的大多数功能都取决于中央站点，因此分支站点的组件仅包含以下内容：</span><span class="sxs-lookup"><span data-stu-id="a3f00-p115">A branch site is associated with a central site, and each Survivable Branch Appliance in a branch site is associated with an Enterprise Edition Front End pool or a Standard Edition server in the associated central site. Branch sites depend on the central site for most of their functionality, so components at a branch site contain only the following:</span></span>

  - <span data-ttu-id="a3f00-201">Survivable 分支设备，它将公共交换电话网络与某些 Lync Server 功能结合 (PSTN) 网关。</span><span class="sxs-lookup"><span data-stu-id="a3f00-201">A Survivable Branch Appliance, which combines a public switched telephone network (PSTN) gateway with some Lync Server functionality.</span></span> <span data-ttu-id="a3f00-202">中介服务器可以与 Survivable 分支设备上的注册器实例并置，也可以部署独立的中介服务器或中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="a3f00-202">A Mediation Server can be collocated with the instance of the Registrar on the Survivable Branch Appliance, and you can deploy a stand-alone Mediation Server or pool of Mediation Servers.</span></span>

  - <span data-ttu-id="a3f00-203">一个 Survivable 分支服务器，它是一个运行 Windows Server 且安装了 Lync Server 2013 注册器和中介服务器软件的服务器。</span><span class="sxs-lookup"><span data-stu-id="a3f00-203">A Survivable Branch Server, which is a server running Windows Server that has Lync Server 2013 Registrar and Mediation Server software installed.</span></span>

  - <span data-ttu-id="a3f00-204">独立的 PSTN 网关（不是 Survivable Branch Appliance 的一部分）和独立的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="a3f00-204">A stand-alone PSTN gateway (not part of the Survivable Branch Appliance) and a stand-alone Mediation Server.</span></span>

<span data-ttu-id="a3f00-205">Survivable 分支服务器的要求与对任何 Lync Server 2013 服务器角色的要求相同。</span><span class="sxs-lookup"><span data-stu-id="a3f00-205">The requirements for Survivable Branch Servers are the same as the requirements for any Lync Server 2013 server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

