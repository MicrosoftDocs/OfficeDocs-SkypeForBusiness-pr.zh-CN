---
title: Lync Server 2013：规划中央站点语音恢复能力
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for central site voice resiliency
ms:assetid: 52dd0c3e-cd3c-44cf-bef5-8c49ff5e4c7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398347(v=OCS.15)
ms:contentKeyID: 48184164
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16a61a07ae14f004b406aa38ef783a1c873f2128
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="16de5-102">在 Lync Server 2013 中规划中心站点语音恢复</span><span class="sxs-lookup"><span data-stu-id="16de5-102">Planning for central site voice resiliency in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16de5-103">_**上次修改的主题：** 2013-10-30_</span><span class="sxs-lookup"><span data-stu-id="16de5-103">_**Topic Last Modified:** 2013-10-30_</span></span>

<span data-ttu-id="16de5-104">企业在全球拥有多个站点的情况日益普遍。</span><span class="sxs-lookup"><span data-stu-id="16de5-104">Increasingly, enterprises have multiple sites spread across the globe.</span></span> <span data-ttu-id="16de5-105">维护紧急服务、访问技术支持以及在中心站点停止服务时执行关键业务任务的能力对于任何企业语音恢复解决方案来说都至关重要。</span><span class="sxs-lookup"><span data-stu-id="16de5-105">Maintaining emergency services, access to help desk, and the ability to conduct critical business tasks when a central site is out of service is essential for any Enterprise Voice resiliency solution.</span></span> <span data-ttu-id="16de5-106">当中央站点不可用时，必须满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="16de5-106">When a central site becomes unavailable, the following conditions must be met:</span></span>

  - <span data-ttu-id="16de5-107">必须提供语音故障转移。</span><span class="sxs-lookup"><span data-stu-id="16de5-107">Voice failover must be provided.</span></span>

  - <span data-ttu-id="16de5-108">通常在中心网站上向前端池注册的用户必须能够使用备用前端池进行注册。</span><span class="sxs-lookup"><span data-stu-id="16de5-108">Users who ordinarily register with the Front End pool at the central site must be able to register with an alternative Front End pool.</span></span> <span data-ttu-id="16de5-109">可以通过创建多个 DNS SRV 记录来实现此操作，每个记录分别解析为每个中心站点中的控制器池或前端池。</span><span class="sxs-lookup"><span data-stu-id="16de5-109">This can be done by creating multiple DNS SRV records, each of which resolves to a Director pool or Front End pool in each of your central sites.</span></span> <span data-ttu-id="16de5-110">您可以调整 SRV 记录的优先级和权重，以便该中心网站提供服务的用户可以在其他 SRV 记录中获取相应的控制器和前端池。</span><span class="sxs-lookup"><span data-stu-id="16de5-110">You can adjust the priority and weights of the SRV records so that users who are served by that central site get the corresponding Director and Front End pool ahead of those in other SRV records.</span></span>

  - <span data-ttu-id="16de5-111">必须将其他站点的用户发送和接收的呼叫重新路由到 PSTN。</span><span class="sxs-lookup"><span data-stu-id="16de5-111">Calls to and from users located at other sites must be rerouted to the PSTN.</span></span>

<span data-ttu-id="16de5-112">本主题介绍可用于保护中央站点语音恢复能力的安全的推荐解决方案。</span><span class="sxs-lookup"><span data-stu-id="16de5-112">This topic describes the recommended solution for securing central site voice resiliency.</span></span>

<div>

## <a name="architecture-and-topology"></a><span data-ttu-id="16de5-113">体系结构和拓扑</span><span class="sxs-lookup"><span data-stu-id="16de5-113">Architecture and Topology</span></span>

<span data-ttu-id="16de5-114">若要在中央站点规划语音弹性，需要对 Lync Server 2013 注册机构在启用语音故障转移时扮演的中心角色有一个基本的了解。</span><span class="sxs-lookup"><span data-stu-id="16de5-114">Planning for voice resiliency at a central site requires a basic understanding of the central role played by the Lync Server 2013 Registrar in enabling voice failover.</span></span> <span data-ttu-id="16de5-115">Lync Server 注册器是一种服务器角色，可启用客户端注册和身份验证并提供路由服务。</span><span class="sxs-lookup"><span data-stu-id="16de5-115">The Lync Server Registrar is a server role that enables client registration and authentication and provides routing services.</span></span> <span data-ttu-id="16de5-116">它与 Standard Edition server、前端服务器、控制器或 Survivable 分支设备上的其他组件驻留在一起。</span><span class="sxs-lookup"><span data-stu-id="16de5-116">It resides along with other components on a Standard Edition server, Front End Server, Director, or Survivable Branch Appliance.</span></span> <span data-ttu-id="16de5-117">注册器池由在前端池上运行并驻留在同一站点上的注册机构服务组成。</span><span class="sxs-lookup"><span data-stu-id="16de5-117">A Registrar pool consists of Registrar Services running on the Front End pool and residing at the same site.</span></span> <span data-ttu-id="16de5-118">前端池必须进行负载平衡。</span><span class="sxs-lookup"><span data-stu-id="16de5-118">The Front End pool must be load balanced.</span></span> <span data-ttu-id="16de5-119">建议使用 DNS 负载平衡，但也支持使用硬件负载平衡。</span><span class="sxs-lookup"><span data-stu-id="16de5-119">DNS load balancing is recommended, but hardware load balancing is acceptable.</span></span> <span data-ttu-id="16de5-120">Lync 客户端通过以下发现机制发现前端池：</span><span class="sxs-lookup"><span data-stu-id="16de5-120">A Lync client discovers the Front End pool through the following discovery mechanism:</span></span>

1.  <span data-ttu-id="16de5-121">DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="16de5-121">DNS SRV record</span></span>

2.  <span data-ttu-id="16de5-122">自动发现 Web 服务（Lync Server 2013 中的新增项）</span><span class="sxs-lookup"><span data-stu-id="16de5-122">Autodiscovery Web Service (new in Lync Server 2013)</span></span>

3.  <span data-ttu-id="16de5-123">DHCP 选项 120</span><span class="sxs-lookup"><span data-stu-id="16de5-123">DHCP option 120</span></span>

<span data-ttu-id="16de5-124">Lync 客户端连接到前端池之后，它会被负载平衡器定向到池中的前端服务器之一。</span><span class="sxs-lookup"><span data-stu-id="16de5-124">After the Lync client connects to the Front End pool, it is directed by the load balancer to one of the Front End Servers in the pool.</span></span> <span data-ttu-id="16de5-125">而该前端服务器又会将客户端重定向到池中的首选注册器。</span><span class="sxs-lookup"><span data-stu-id="16de5-125">That Front End Server, in turn, redirects the client to a preferred Registrar in the pool.</span></span>

<span data-ttu-id="16de5-126">为企业语音启用的每个用户都将分配给特定的注册器池，这将成为该用户的主注册器池。</span><span class="sxs-lookup"><span data-stu-id="16de5-126">Each user enabled for Enterprise Voice is assigned to a particular Registrar pool, which becomes that user’s primary Registrar pool.</span></span> <span data-ttu-id="16de5-127">在给定的站点上，通常成百上千个用户共享一个主注册器池。</span><span class="sxs-lookup"><span data-stu-id="16de5-127">At a given site, hundreds or thousands of users typically share a single primary Registrar pool.</span></span> <span data-ttu-id="16de5-128">要说明其状态、会议或故障转移依赖于中央站点的任何分支站点用户使用中央站点资源的情况，建议您将每个分支站点用户视作已在中央站点注册的用户。</span><span class="sxs-lookup"><span data-stu-id="16de5-128">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as though the user were a user registered with the central site.</span></span> <span data-ttu-id="16de5-129">对分支站点用户的数量（包括在 Survivable 分支设备中注册的用户），目前没有限制。</span><span class="sxs-lookup"><span data-stu-id="16de5-129">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>

<span data-ttu-id="16de5-130">为确保中央站点具有发生故障时的语音恢复能力，主注册器池必须有一个单独指定的备份注册器池，该注册器池位于另一个站点。</span><span class="sxs-lookup"><span data-stu-id="16de5-130">To assure voice resiliency in the event of a central site failure, the primary Registrar pool must have a single designated backup Registrar pool located at another site.</span></span> <span data-ttu-id="16de5-131">可以使用拓扑生成器恢复能力设置来配置备份。</span><span class="sxs-lookup"><span data-stu-id="16de5-131">The backup can be configured by using Topology Builder resiliency settings.</span></span> <span data-ttu-id="16de5-132">假定两个站点之间有一个可恢复的 WAN 链路，其主注册器池不再可用的用户将自动定向到备份注册器池。</span><span class="sxs-lookup"><span data-stu-id="16de5-132">Assuming a resilient WAN link between the two sites, users whose primary Registrar pool is no longer available are automatically directed to the backup Registrar pool.</span></span>

<span data-ttu-id="16de5-133">以下步骤介绍了客户端发现和注册过程：</span><span class="sxs-lookup"><span data-stu-id="16de5-133">The following steps describe the client discovery and registration process:</span></span>

1.  <span data-ttu-id="16de5-134">客户端通过 DNS SRV 记录发现 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="16de5-134">A client discovers Lync Server through DNS SRV records.</span></span> <span data-ttu-id="16de5-135">在 Lync Server 2013 中，可以将 DNS SRV 记录配置为将多个 FQDN 返回给 DNS SRV 查询。</span><span class="sxs-lookup"><span data-stu-id="16de5-135">In Lync Server 2013, DNS SRV records can be configured to return more than one FQDN to the DNS SRV query.</span></span> <span data-ttu-id="16de5-136">例如，如果企业 Contoso 具有三个中央站点（北美、欧洲和亚太），且每个中央站点有一个控制器池，则 DNS SRV 记录可以指向每个位置中的控制器池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="16de5-136">For example, if enterprise Contoso has three central sites (North America, Europe, and Asia-Pacific) and a Director pool at each central site, DNS SRV records can point to the Director pool FQDNs in each of the three locations.</span></span> <span data-ttu-id="16de5-137">只要其中一个位置中的控制器池可用，客户端就可以连接到第一个跃点 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="16de5-137">As long as the Director pool in one of the locations is available, the client can connect to the first hop Lync Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="16de5-138">使用控制器池是可选的。</span><span class="sxs-lookup"><span data-stu-id="16de5-138">Using a Director pool is optional.</span></span> <span data-ttu-id="16de5-139">可以改为使用前端池。</span><span class="sxs-lookup"><span data-stu-id="16de5-139">A Front End pool can be used instead.</span></span>

    
    </div>

2.  <span data-ttu-id="16de5-140">控制器池通知 Lync 客户端用户的主注册器池和备份注册器池。</span><span class="sxs-lookup"><span data-stu-id="16de5-140">The Director pool informs the Lync client about the user’s primary Registrar pool and backup Registrar pool.</span></span>

3.  <span data-ttu-id="16de5-141">Lync 客户端首先尝试连接到用户的主注册器池。</span><span class="sxs-lookup"><span data-stu-id="16de5-141">The Lync client attempts to connect to the user’s primary Registrar pool first.</span></span> <span data-ttu-id="16de5-142">如果主注册器池可用，则该注册器接受注册。</span><span class="sxs-lookup"><span data-stu-id="16de5-142">If the primary Registrar pool is available, the Registrar accepts the registration.</span></span> <span data-ttu-id="16de5-143">如果主注册器池不可用，Lync 客户端将尝试连接到备份注册器池。</span><span class="sxs-lookup"><span data-stu-id="16de5-143">If the primary Registrar pool is unavailable, the Lync client attempts to connect to the backup Registrar pool.</span></span> <span data-ttu-id="16de5-144">如果备份注册器池可用且已确定用户的主注册器池不可用（检测出指定故障转移间隔期间检测信号不足），则备份注册器池将接受用户的注册。</span><span class="sxs-lookup"><span data-stu-id="16de5-144">If the backup Registrar pool is available and has determined that the user’s primary Registrar pool is unavailable (by detecting a lack of heartbeat for a specified failover interval) the backup Registrar pool accepts the user’s registration.</span></span> <span data-ttu-id="16de5-145">在备份注册器检测到主注册器再次可用后，备份注册器池会将故障转移 Lync 客户端重定向到其主池。</span><span class="sxs-lookup"><span data-stu-id="16de5-145">After the backup Registrar detects that the primary Registrar is again available, the backup Registrar pool will redirect failover Lync clients to their primary pool.</span></span>

<span data-ttu-id="16de5-p110">下图显示了可确保中央站点恢复能力的推荐拓扑。这两个站点由可恢复的 WAN 链路相连。如果中央站点变得不可用，则已分配给该池的用户会定向到备份站点以进行注册。</span><span class="sxs-lookup"><span data-stu-id="16de5-p110">The following figure shows the recommended topology for assuring central site resiliency. The two sites are connected by a resilient WAN link. If the central site becomes unavailable, users who are assigned to that pool are directed to the backup site for registration.</span></span>

<span data-ttu-id="16de5-149">**中央站点语音恢复能力的推荐拓扑**</span><span class="sxs-lookup"><span data-stu-id="16de5-149">**Recommended topology for central site voice resiliency**</span></span>

<span data-ttu-id="16de5-150">![中央站点语音拓扑的拓扑](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "中央站点语音拓扑的拓扑")</span><span class="sxs-lookup"><span data-stu-id="16de5-150">![Topology for central site voice resliency](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topology for central site voice resliency")</span></span>

</div>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="16de5-151">要求与建议</span><span class="sxs-lookup"><span data-stu-id="16de5-151">Requirements and Recommendations</span></span>

<span data-ttu-id="16de5-152">以下有关实现中央站点语音恢复能力的要求和建议适用于大多数组织：</span><span class="sxs-lookup"><span data-stu-id="16de5-152">The following requirements and recommendations for implementing central site voice resiliency are appropriate for most organizations:</span></span>

  - <span data-ttu-id="16de5-153">主注册器池和备份注册器池所在的站点应由可恢复的 WAN 链路相连。</span><span class="sxs-lookup"><span data-stu-id="16de5-153">The sites in which the primary and backup Registrar pools reside should be connected by a resilient WAN link.</span></span>

  - <span data-ttu-id="16de5-154">每个中央站点必须包含由一个或多个注册器组成的注册器池。</span><span class="sxs-lookup"><span data-stu-id="16de5-154">Each central site must contain a Registrar pool consisting of one or more Registrars.</span></span>

  - <span data-ttu-id="16de5-155">每个注册器池都必须使用 DNS 负载平衡和/或硬件负载平衡进行负载平衡。</span><span class="sxs-lookup"><span data-stu-id="16de5-155">Each Registrar pool must be load-balanced by using DNS load balancing, hardware load balancing, or both.</span></span> <span data-ttu-id="16de5-156">有关规划负载平衡配置的详细信息，请参阅[Lync Server 2013 的负载平衡要求](lync-server-2013-load-balancing-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="16de5-156">For detailed information about planning your load balancing configuration, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

  - <span data-ttu-id="16de5-157">必须使用 Lync Server Management Shell **get-csuser** Cmdlet 或 Lync server 控制面板将每个用户分配给主注册器池。</span><span class="sxs-lookup"><span data-stu-id="16de5-157">Each user must be assigned to a primary Registrar pool by using either the Lync Server Management Shell **set-CsUser** cmdlet or the Lync Server Control Panel.</span></span>

  - <span data-ttu-id="16de5-158">主注册器池必须具有单个备份注册器池，该注册器池位于不同的中央站点。</span><span class="sxs-lookup"><span data-stu-id="16de5-158">The primary Registrar pool must have a single backup Registrar pool located in a different central site.</span></span>

  - <span data-ttu-id="16de5-159">必须将主注册器池配置为可故障转移到备份注册器池。</span><span class="sxs-lookup"><span data-stu-id="16de5-159">The primary Registrar pool must be configured to fail over to the backup Registrar pool.</span></span> <span data-ttu-id="16de5-160">默认情况下，将主注册器设置为每隔 300 秒故障转移到备份注册器池。</span><span class="sxs-lookup"><span data-stu-id="16de5-160">By default, the primary Registrar is set to fail over to the backup Registrar pool after an interval of 300 seconds.</span></span> <span data-ttu-id="16de5-161">您可以使用 Lync Server 2013 拓扑生成器来更改此间隔。</span><span class="sxs-lookup"><span data-stu-id="16de5-161">You can change this interval by using the Lync Server 2013 Topology Builder.</span></span>

  - <span data-ttu-id="16de5-162">配置故障转移路由，如规划文档中的 "[在 Lync Server 2013 中配置故障转移路由](lync-server-2013-configuring-a-failover-route.md)" 主题中所述。</span><span class="sxs-lookup"><span data-stu-id="16de5-162">Configure a failover route, as described in the “[Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)” topic in the Planning documentation.</span></span> <span data-ttu-id="16de5-163">配置该路由后，指定网关，该网关的站点与在主路由中指定的网关的站点不同。</span><span class="sxs-lookup"><span data-stu-id="16de5-163">When configuring the route, specify a gateway that is located at a different site from the gateway specified in the primary route.</span></span>

  - <span data-ttu-id="16de5-164">如果中央站点包含主管理服务器且该站点可能还要再关闭一段时间，则需要在备份站点重新安装管理工具，否则将不能更改任何管理设置。</span><span class="sxs-lookup"><span data-stu-id="16de5-164">If the central site contained your primary management server and the site is likely to be down for an extended period, you will need to reinstall your management tools at the backup site; otherwise, you won’t be able to change any management settings.</span></span>

</div>

<div>

## <a name="dependencies"></a><span data-ttu-id="16de5-165">相关性</span><span class="sxs-lookup"><span data-stu-id="16de5-165">Dependencies</span></span>

<span data-ttu-id="16de5-166">Lync Server 取决于以下基础结构和软件组件，以确保语音恢复能力：</span><span class="sxs-lookup"><span data-stu-id="16de5-166">Lync Server depends on the following infrastructure and software components to assure voice resiliency:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16de5-167"><strong>组件</strong></span><span class="sxs-lookup"><span data-stu-id="16de5-167"><strong>Component</strong></span></span></p></td>
<td><p><span data-ttu-id="16de5-168"><strong>完善</strong></span><span class="sxs-lookup"><span data-stu-id="16de5-168"><strong>Functional</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16de5-169">DNS</span><span class="sxs-lookup"><span data-stu-id="16de5-169">DNS</span></span></p></td>
<td><p><span data-ttu-id="16de5-170">解析有关服务器到服务器和服务器到客户端连接的 SRV 记录和 A 记录</span><span class="sxs-lookup"><span data-stu-id="16de5-170">Resolving SRV records and A records for server-server and server-client connectivity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16de5-171">Exchange 和 Exchange Web 服务 (EWS)</span><span class="sxs-lookup"><span data-stu-id="16de5-171">Exchange and Exchange Web Services (EWS)</span></span></p></td>
<td><p><span data-ttu-id="16de5-172">联系人存储；日历数据</span><span class="sxs-lookup"><span data-stu-id="16de5-172">Contact storage; calendar data</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16de5-173">Exchange 统一消息和 Exchange Web 服务</span><span class="sxs-lookup"><span data-stu-id="16de5-173">Exchange Unified Messaging and Exchange Web Services</span></span></p></td>
<td><p><span data-ttu-id="16de5-174">呼叫日志、语音邮件列表、语音邮件</span><span class="sxs-lookup"><span data-stu-id="16de5-174">Call logs, voice mail list, voice mail</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16de5-175">DHCP 选项 120</span><span class="sxs-lookup"><span data-stu-id="16de5-175">DHCP Options 120</span></span></p></td>
<td><p><span data-ttu-id="16de5-176">如果 DNS SRV 不可用，则客户端将尝试使用 DHCP 选项 120 来发现注册器。</span><span class="sxs-lookup"><span data-stu-id="16de5-176">If DNS SRV is unavailable, the client will attempt to use DHCP Option 120 to discover the Registrar.</span></span> <span data-ttu-id="16de5-177">为使其正常工作，必须配置 DHCP 服务器或启用 Lync Server 2013 DHCP。</span><span class="sxs-lookup"><span data-stu-id="16de5-177">For this to work, either a DHCP server must be configured or Lync Server 2013 DHCP must be enabled.</span></span> <span data-ttu-id="16de5-178">有关详细信息，请参阅<a href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013 的分支站点恢复要求</a>中的硬件和软件要求（针对分支站点恢复）部分。</span><span class="sxs-lookup"><span data-stu-id="16de5-178">For details, see Hardware and Software Requirements for Branch-Site Resiliency in <a href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</a> section.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a><span data-ttu-id="16de5-179">Survivable 语音功能</span><span class="sxs-lookup"><span data-stu-id="16de5-179">Survivable Voice Features</span></span>

<span data-ttu-id="16de5-180">如果上述要求和建议已付诸实行，则备份注册器池将提供以下语音功能：</span><span class="sxs-lookup"><span data-stu-id="16de5-180">If the preceding requirements and recommendations have been implemented, the following voice features will be provided by the backup Registrar pool:</span></span>

  - <span data-ttu-id="16de5-181">出站 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="16de5-181">Outbound PSTN calls</span></span>

  - <span data-ttu-id="16de5-182">入站 PSTN 呼叫，前提是电话服务提供商支持故障转移到备份站点的功能</span><span class="sxs-lookup"><span data-stu-id="16de5-182">Inbound PSTN calls, if the telephony service provider supports the ability to fail over to a backup site</span></span>

  - <span data-ttu-id="16de5-183">同一站点的用户间和两个不同站点的用户间的企业呼叫</span><span class="sxs-lookup"><span data-stu-id="16de5-183">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="16de5-184">基本呼叫处理功能（包括呼叫保持、取回和转接）</span><span class="sxs-lookup"><span data-stu-id="16de5-184">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="16de5-185">双方即时消息和在同一站点的用户间共享音频和视频</span><span class="sxs-lookup"><span data-stu-id="16de5-185">Two-party instant messaging and sharing audio and video between users at the same site</span></span>

  - <span data-ttu-id="16de5-186">呼叫转接、终结点同时响铃、呼叫委派和团队呼叫服务，但前提是在同一站点配置呼叫委派的双方或所有团队成员。</span><span class="sxs-lookup"><span data-stu-id="16de5-186">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if both parties to call delegation, or all team members, are configured at the same site.</span></span>

  - <span data-ttu-id="16de5-187">现有电话和客户端继续工作。</span><span class="sxs-lookup"><span data-stu-id="16de5-187">Existing phones and clients continue to work.</span></span>

  - <span data-ttu-id="16de5-188">呼叫详细信息记录 (CDR)</span><span class="sxs-lookup"><span data-stu-id="16de5-188">Call detail recording (CDR)</span></span>

  - <span data-ttu-id="16de5-189">身份验证和授权</span><span class="sxs-lookup"><span data-stu-id="16de5-189">Authentication and authorization</span></span>

<span data-ttu-id="16de5-190">在主中央站点停用时，以下语音功能可能会工作，也可能不会工作，具体取决于配置方式：</span><span class="sxs-lookup"><span data-stu-id="16de5-190">Depending on how they are configured, the following voice features may or may not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="16de5-191">语音邮件处理和检索</span><span class="sxs-lookup"><span data-stu-id="16de5-191">Voice mail deposit and retrieval</span></span>
    
    <span data-ttu-id="16de5-192">如果要使 Exchange UM 在主中央站点停用时可用，必须执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="16de5-192">If you want to make Exchange UM available when the primary central site is out of service, you must do one of the following:</span></span>
    
      - <span data-ttu-id="16de5-193">更改 DNS SRV 记录，使中央站点的 Exchange UM 服务器指向其他站点的备份 Exchange UM 服务器。</span><span class="sxs-lookup"><span data-stu-id="16de5-193">Change DNS SRV records so that the Exchange UM servers at the central site point to backup Exchange UM servers at another site.</span></span>
    
      - <span data-ttu-id="16de5-194">将每个用户的 Exchange UM 拨号计划配置为同时在中心站点和备份站点上包括 Exchange UM 服务器，但将备份 Exchange UM 服务器指定为已禁用。</span><span class="sxs-lookup"><span data-stu-id="16de5-194">Configure each user’s Exchange UM dial plan to include Exchange UM servers at both the central site and the backup site, but designate the backup Exchange UM servers as disabled.</span></span> <span data-ttu-id="16de5-195">如果主站点变得不可用，则 Exchange 管理员必须将备份站点上的 Exchange UM 服务器标记为 "已启用"。</span><span class="sxs-lookup"><span data-stu-id="16de5-195">If the primary site becomes unavailable, the Exchange administrator has to mark the Exchange UM servers at the backup site as enabled.</span></span>
    
    <span data-ttu-id="16de5-196">如果上述解决方案均无法使用，则 Exchange UM 将无法在中心站点不可用的情况下使用。</span><span class="sxs-lookup"><span data-stu-id="16de5-196">If neither of the preceding solutions is possible, then Exchange UM will not be available in the event the central site becomes unavailable.</span></span>

  - <span data-ttu-id="16de5-197">所有类型的会议</span><span class="sxs-lookup"><span data-stu-id="16de5-197">Conferencing of all types</span></span>
    
    <span data-ttu-id="16de5-p116">故障转移到备份站点的用户，可以加入到由其池可用但不能在自己的主池（不再可用）上创建或承载会议的组织者创建或承载的会议。同样，其他用户也不能加入在受影响的用户的主池上承载的会议。</span><span class="sxs-lookup"><span data-stu-id="16de5-p116">A user who has failed over to a backup site can join a conference that is created or hosted by an organizer whose pool is available but cannot create or host a conference on his or her own primary pool, which is no longer available. Similarly, others users cannot join conferences that are hosted on the affected user’s primary pool.</span></span>

<span data-ttu-id="16de5-200">在主中央站点停用时，以下语音功能不会工作：</span><span class="sxs-lookup"><span data-stu-id="16de5-200">The following voice features do not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="16de5-201">会议自动助理</span><span class="sxs-lookup"><span data-stu-id="16de5-201">Conference Auto-Attendant</span></span>

  - <span data-ttu-id="16de5-202">基于状态和 DND 的路由</span><span class="sxs-lookup"><span data-stu-id="16de5-202">Presence and DND-based routing</span></span>

  - <span data-ttu-id="16de5-203">更新呼叫转接设置</span><span class="sxs-lookup"><span data-stu-id="16de5-203">Updating call forwarding settings</span></span>

  - <span data-ttu-id="16de5-204">响应组服务和呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="16de5-204">Response Group service and Call Park</span></span>

  - <span data-ttu-id="16de5-205">设置新的电话和客户端</span><span class="sxs-lookup"><span data-stu-id="16de5-205">Provisioning new phones and clients</span></span>

  - <span data-ttu-id="16de5-206">通讯簿 Web 搜索</span><span class="sxs-lookup"><span data-stu-id="16de5-206">Address Book Web Search</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="16de5-207">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16de5-207">See Also</span></span>


[<span data-ttu-id="16de5-208">在 Lync Server 2013 中规划分支站点语音恢复</span><span class="sxs-lookup"><span data-stu-id="16de5-208">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

