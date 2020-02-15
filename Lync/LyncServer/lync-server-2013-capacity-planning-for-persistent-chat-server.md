---
title: Lync Server 2013：持久聊天服务器的容量规划
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Persistent Chat Server
ms:assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615006(v=OCS.15)
ms:contentKeyID: 48184580
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f20d297e1d127d167aa8acc059f5b6f89cc96d13
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036502"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="e323f-102">Lync Server 2013 中持久聊天服务器的容量规划</span><span class="sxs-lookup"><span data-stu-id="e323f-102">Capacity planning for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e323f-103">_**上次修改的主题：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="e323f-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="e323f-104">持久聊天服务器可以执行多用户实时聊天，可以持续进行，以便将来检索和搜索。</span><span class="sxs-lookup"><span data-stu-id="e323f-104">Persistent Chat Server can perform multi-user real-time chat that can persist for future retrieval and search.</span></span> <span data-ttu-id="e323f-105">与存储在用户邮箱中的组即时消息（IM）不同，如果配置了对话历史记录，持久聊天服务器会话将保持打开状态，并将内容保存在服务器上，同时还会在邮件、文件、Url 和其他属于正在进行对话。</span><span class="sxs-lookup"><span data-stu-id="e323f-105">Unlike group instant messaging (IM) that is saved in a user’s mailbox if conversation history is configured, a Persistent Chat Server session stays open longer, and the content is saved on a server, along with the messages, files, URLs, and other data that are part of an ongoing conversation.</span></span>

<span data-ttu-id="e323f-106">容量规划是准备部署持久聊天服务器的重要部分。</span><span class="sxs-lookup"><span data-stu-id="e323f-106">Capacity planning is an important part of preparing to deploy Persistent Chat Server.</span></span> <span data-ttu-id="e323f-107">本主题提供了有关受支持的持久聊天服务器拓扑和容量规划表的详细信息，您可以使用这些表来确定适用于您的部署的最佳配置。</span><span class="sxs-lookup"><span data-stu-id="e323f-107">This topic provides details about supported Persistent Chat Server topologies and capacity planning tables that you can use to determine the best configuration for your deployment.</span></span> <span data-ttu-id="e323f-108">此外，还介绍了如何最好地管理在高峰时间需要更大容量的持久聊天服务器部署。</span><span class="sxs-lookup"><span data-stu-id="e323f-108">It also describes how to best manage Persistent Chat Server deployments that require greater capacity at peak times.</span></span>

<span data-ttu-id="e323f-109">若要下载持久聊天服务器，请参阅在上的[http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539)"Microsoft Lync Server 13 持久聊天服务器"。</span><span class="sxs-lookup"><span data-stu-id="e323f-109">To download Persistent Chat Server, see "Microsoft Lync Server 13 Persistent Chat Server" at [http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539).</span></span>

<span data-ttu-id="e323f-110">有关安装持久聊天服务器的详细信息，请参阅部署文档中的在[Lync server 2013 中安装持久聊天服务器](lync-server-2013-installing-persistent-chat-server.md)和[在 lync Server 2013 中配置持久聊天服务器](lync-server-2013-configuring-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="e323f-110">For details about installing Persistent Chat Server, see [Installing Persistent Chat Server in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) and [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="e323f-111">支持工具（如 Lync Server 规划工具）可以进一步帮助您进行容量规划。</span><span class="sxs-lookup"><span data-stu-id="e323f-111">Support tools, such as Lync Server Planning Tool, can further assist you with capacity planning.</span></span> <span data-ttu-id="e323f-112">有关规划工具的详细信息，请参阅规划文档中的[开始规划 Lync Server 2013 的规划过程](lync-server-2013-beginning-the-planning-process.md)。</span><span class="sxs-lookup"><span data-stu-id="e323f-112">For details about the Planning Tool, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<div>

## <a name="persistent-chat-server-supported-topologies"></a><span data-ttu-id="e323f-113">持久聊天服务器支持的拓扑</span><span class="sxs-lookup"><span data-stu-id="e323f-113">Persistent Chat Server Supported Topologies</span></span>

<span data-ttu-id="e323f-114">您可以在单服务器或多服务器池中部署持久聊天服务器，也可以使用单一池或多池拓扑。</span><span class="sxs-lookup"><span data-stu-id="e323f-114">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span>

<span data-ttu-id="e323f-115">现在，我们还支持适用于新的 Lync Server 2013 部署的 Standard Edition server 上的持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="e323f-115">We now also support Persistent Chat Server on Standard Edition server for new Lync Server 2013 deployments.</span></span> <span data-ttu-id="e323f-116">但是，性能和规模将受到影响，由于没有适用于此新部署的高可用性选项，因此我们预计您将主要用于概念验证、评估等目的。</span><span class="sxs-lookup"><span data-stu-id="e323f-116">However, performance and scale will be affected, and because there is no high availability option for this new deployment, we expect you to use this primarily for the purposes of proof of concept, evaluation, and so on.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e323f-117">有关这两种拓扑的更多详细信息，请参阅部署文档中的在 lync server 2013 中的 "在<A href="lync-server-2013-planning-for-persistent-chat-server.md">lync server 中规划持久聊天服务器</A>" 和 "<A href="lync-server-2013-deploying-persistent-chat-server.md">在 lync Server 2013 中部署持久聊天服务器</A>"。</span><span class="sxs-lookup"><span data-stu-id="e323f-117">For additional details about both topologies, see <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for Persistent Chat Server in Lync Server 2013</A> in this documentation set and <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="e323f-118">单服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="e323f-118">Single-Server Topology</span></span>

<span data-ttu-id="e323f-119">持久聊天服务器的最小配置和最简单部署是一个持久聊天服务器前端服务器拓扑。</span><span class="sxs-lookup"><span data-stu-id="e323f-119">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="e323f-120">此部署需要运行持久聊天服务器（如果合规性已启用）的一台服务器、承载 SQL Server 数据库的服务器，以及如果需要合规性，则为 SQL Server 数据库存储合规性数据。</span><span class="sxs-lookup"><span data-stu-id="e323f-120">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e323f-121">您不能向作为拓扑生成器中的单个服务器部署启动的持久聊天服务器池添加其他服务器。</span><span class="sxs-lookup"><span data-stu-id="e323f-121">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="e323f-122">我们建议使用多服务器池拓扑，即使您使用的是一台服务器。</span><span class="sxs-lookup"><span data-stu-id="e323f-122">We recommend using the multiple-server pool topology, even if you’re using a single server.</span></span> <span data-ttu-id="e323f-123">这样，你将能够在以后添加更多服务器（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="e323f-123">This is so that you’ll be able to add more servers later, if it's necessary.</span></span> 


</div>

<span data-ttu-id="e323f-124">下图显示了符合条件的单个持久聊天服务器前端服务器的拓扑的所有必需组件和可选组件。</span><span class="sxs-lookup"><span data-stu-id="e323f-124">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="e323f-125">**单个持久聊天服务器**</span><span class="sxs-lookup"><span data-stu-id="e323f-125">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="e323f-126">![单服务器拓扑与合规性服务](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "单服务器拓扑与合规性服务")</span><span class="sxs-lookup"><span data-stu-id="e323f-126">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="e323f-127">多服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="e323f-127">Multiple-Server Topology</span></span>

<span data-ttu-id="e323f-128">若要提供更大的容量和可靠性，可以部署多服务器拓扑，如在[Lync server 2013 中规划持久聊天服务器中](lync-server-2013-planning-for-persistent-chat-server.md)所述。</span><span class="sxs-lookup"><span data-stu-id="e323f-128">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="e323f-129">多服务器拓扑可以包括多达四个运行持久聊天服务器的活动计算机（高可用性和灾难恢复配置允许最多八个，但只有四个活动，并且在待机时剩下四个）。</span><span class="sxs-lookup"><span data-stu-id="e323f-129">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="e323f-130">每个服务器最多可以支持多达20000个并发用户，共80000个并发用户连接到具有4台服务器的持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="e323f-130">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="e323f-131">多服务器拓扑与单服务器拓扑相同，不同之处在于多个服务器承载持久聊天服务器，并且可以扩展到更高级别。</span><span class="sxs-lookup"><span data-stu-id="e323f-131">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="e323f-132">运行持久聊天服务器的多台计算机应驻留在与 Lync Server 和合规性服务相同的 Active Directory 域服务域中。</span><span class="sxs-lookup"><span data-stu-id="e323f-132">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="e323f-133">下图显示了多个服务器拓扑的所有组件，其中包含多个运行持久聊天服务器、可选合规性服务和独立合规性数据库的计算机。</span><span class="sxs-lookup"><span data-stu-id="e323f-133">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="e323f-134">**多个持久聊天服务器**</span><span class="sxs-lookup"><span data-stu-id="e323f-134">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="e323f-135">![多服务器拓扑](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "多服务器拓扑")</span><span class="sxs-lookup"><span data-stu-id="e323f-135">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="e323f-136">在四个服务器的持久聊天服务器部署中，其中80000个用户可以同时登录并使用持久聊天，每个服务器在20000个用户之间平均分布负载。</span><span class="sxs-lookup"><span data-stu-id="e323f-136">In a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to and using Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="e323f-137">如果一台服务器变得不可用，则连接到该服务器的用户将失去其对持久聊天服务器的访问权限。</span><span class="sxs-lookup"><span data-stu-id="e323f-137">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="e323f-138">断开连接的用户将自动转接到其余的服务器，直到该不可用的服务器恢复使用。</span><span class="sxs-lookup"><span data-stu-id="e323f-138">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> <span data-ttu-id="e323f-139">此传输可能需要几分钟或更长时间，具体取决于网络上的持久聊天流量量。</span><span class="sxs-lookup"><span data-stu-id="e323f-139">Depending on the amount of Persistent Chat traffic on the network, this transfer can take a few minutes or longer.</span></span> <span data-ttu-id="e323f-140">由于剩余的每个服务器都可能承载多达30000个用户，因此我们建议您尽可能快地还原不可用服务器以避免性能问题。</span><span class="sxs-lookup"><span data-stu-id="e323f-140">Because each of the remaining servers might be hosting as many as 30,000 users, we recommend that you restore the unavailable server as quickly as possible to avoid performance issues.</span></span> <span data-ttu-id="e323f-141">否则，可以使用拓扑生成器或 Windows PowerShell cmdlet，将另一个持久聊天服务器设为可用， **set-cspersistentchatactiveserver**。</span><span class="sxs-lookup"><span data-stu-id="e323f-141">Otherwise, you can make another Persistent Chat Server available by using the Topology Builder or the Windows PowerShell cmdlet, **set-CsPersistentChatActiveServer**.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a><span data-ttu-id="e323f-142">持久聊天服务器容量规划</span><span class="sxs-lookup"><span data-stu-id="e323f-142">Persistent Chat Server Capacity Planning</span></span>

<span data-ttu-id="e323f-143">下表可帮助您对持久聊天服务器进行容量规划。</span><span class="sxs-lookup"><span data-stu-id="e323f-143">The following tables can help you with capacity planning for Persistent Chat Server.</span></span> <span data-ttu-id="e323f-144">它们对更改各种持久聊天服务器设置有何影响容量功能进行了建模。</span><span class="sxs-lookup"><span data-stu-id="e323f-144">They model how changing various Persistent Chat Server settings affect capacity capabilities.</span></span>

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a><span data-ttu-id="e323f-145">规划持久聊天服务器的最大容量</span><span class="sxs-lookup"><span data-stu-id="e323f-145">Planning Your Maximum Capacity for Persistent Chat Server</span></span>

<span data-ttu-id="e323f-146">使用下面的示例表决定可以支持的用户数。</span><span class="sxs-lookup"><span data-stu-id="e323f-146">Use the following sample table to determine the number of users you will be able to support.</span></span>

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a><span data-ttu-id="e323f-147">持久聊天服务器池最大容量示例</span><span class="sxs-lookup"><span data-stu-id="e323f-147">Persistent Chat Server pool Maximum Capacity Sample</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e323f-148">活动的持久聊天服务实例</span><span class="sxs-lookup"><span data-stu-id="e323f-148">Active Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="e323f-149"><em>4</em></span><span class="sxs-lookup"><span data-stu-id="e323f-149"><em>4</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-150">持久聊天服务实例</span><span class="sxs-lookup"><span data-stu-id="e323f-150">Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="e323f-151"><em>8（4必须是非活动的，最多只能有4个活动）</em></span><span class="sxs-lookup"><span data-stu-id="e323f-151"><em>8 (4 must be inactive; only a maximum of 4 can be active)</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-152">连接的活动用户</span><span class="sxs-lookup"><span data-stu-id="e323f-152">Active users connected</span></span></p></td>
<td><p><span data-ttu-id="e323f-153"><em>80000</em></span><span class="sxs-lookup"><span data-stu-id="e323f-153"><em>80,000</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-154">设置的用户总数</span><span class="sxs-lookup"><span data-stu-id="e323f-154">Total provisioned users</span></span></p></td>
<td><p><span data-ttu-id="e323f-155">150000</span><span class="sxs-lookup"><span data-stu-id="e323f-155">150,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-156">终结点的数目</span><span class="sxs-lookup"><span data-stu-id="e323f-156">Number of endpoints</span></span></p></td>
<td><p><span data-ttu-id="e323f-157">120000</span><span class="sxs-lookup"><span data-stu-id="e323f-157">120,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e323f-158">在上面的示例中，计划支持持久聊天服务器允许的最大用户数：持久聊天服务的四个服务器/实例（可以有四个更多的被动服务器运行持久聊天服务器以实现高可用性和灾难恢复）和20000个用户（共80000个活动用户）和每个服务器个用户。</span><span class="sxs-lookup"><span data-stu-id="e323f-158">In the preceding sample, the plan is to support the maximum number of users that Persistent Chat Server allows: four servers/instances of the Persistent Chat service (can have four more passive servers running Persistent Chat Server for high availability and disaster recovery) and 20,000 users per server, for a total of 80,000 active users.</span></span>

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a><span data-ttu-id="e323f-159">管理持久聊天室访问的容量规划</span><span class="sxs-lookup"><span data-stu-id="e323f-159">Capacity Planning for Managing Persistent Chat Room Access</span></span>

<span data-ttu-id="e323f-160">下面的示例表可帮助您规划如何在持久聊天服务器池中管理持久聊天室访问。</span><span class="sxs-lookup"><span data-stu-id="e323f-160">The following sample table can help you plan for managing Persistent Chat room access in a Persistent Chat Server pool.</span></span>

### <a name="managing-chat-room-access-sample"></a><span data-ttu-id="e323f-161">管理聊天室访问示例</span><span class="sxs-lookup"><span data-stu-id="e323f-161">Managing Chat Room Access Sample</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="e323f-162">小聊天室</span><span class="sxs-lookup"><span data-stu-id="e323f-162">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="e323f-163">中型聊天室</span><span class="sxs-lookup"><span data-stu-id="e323f-163">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="e323f-164">大型聊天室</span><span class="sxs-lookup"><span data-stu-id="e323f-164">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="e323f-165">总计</span><span class="sxs-lookup"><span data-stu-id="e323f-165">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e323f-166">聊天室的大小（连接的用户数）</span><span class="sxs-lookup"><span data-stu-id="e323f-166">Size of chat rooms (number of users connected)</span></span></p></td>
<td><p><span data-ttu-id="e323f-167">每个会议室30个</span><span class="sxs-lookup"><span data-stu-id="e323f-167">30 per room</span></span></p></td>
<td><p><span data-ttu-id="e323f-168">每个会议室150</span><span class="sxs-lookup"><span data-stu-id="e323f-168">150 per room</span></span></p></td>
<td><p><span data-ttu-id="e323f-169">每个会议室16000</span><span class="sxs-lookup"><span data-stu-id="e323f-169">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-170">聊天室</span><span class="sxs-lookup"><span data-stu-id="e323f-170">Chat rooms</span></span></p></td>
<td><p><span data-ttu-id="e323f-171">32000</span><span class="sxs-lookup"><span data-stu-id="e323f-171">32,000</span></span></p></td>
<td><p><span data-ttu-id="e323f-172">1067</span><span class="sxs-lookup"><span data-stu-id="e323f-172">1,067</span></span></p></td>
<td><p><span data-ttu-id="e323f-173">10 </span><span class="sxs-lookup"><span data-stu-id="e323f-173">10</span></span></p></td>
<td><p><span data-ttu-id="e323f-174">33077</span><span class="sxs-lookup"><span data-stu-id="e323f-174">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-175">大会堂的会议室百分比</span><span class="sxs-lookup"><span data-stu-id="e323f-175">% of rooms that are auditorium</span></span></p></td>
<td><p><span data-ttu-id="e323f-176">1</span><span class="sxs-lookup"><span data-stu-id="e323f-176">1%</span></span></p></td>
<td><p><span data-ttu-id="e323f-177">1</span><span class="sxs-lookup"><span data-stu-id="e323f-177">1%</span></span></p></td>
<td><p><span data-ttu-id="e323f-178">50%</span><span class="sxs-lookup"><span data-stu-id="e323f-178">50%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-179">打开的会议室的百分比</span><span class="sxs-lookup"><span data-stu-id="e323f-179">% of rooms that are open</span></span></p></td>
<td><p><span data-ttu-id="e323f-180">第三章</span><span class="sxs-lookup"><span data-stu-id="e323f-180">3%</span></span></p></td>
<td><p><span data-ttu-id="e323f-181">第三章</span><span class="sxs-lookup"><span data-stu-id="e323f-181">3%</span></span></p></td>
<td><p><span data-ttu-id="e323f-182">50%</span><span class="sxs-lookup"><span data-stu-id="e323f-182">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-183">打开聊天室（无显式成员资格）</span><span class="sxs-lookup"><span data-stu-id="e323f-183">Open rooms (no explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="e323f-184">960</span><span class="sxs-lookup"><span data-stu-id="e323f-184">960</span></span></p></td>
<td><p><span data-ttu-id="e323f-185">32</span><span class="sxs-lookup"><span data-stu-id="e323f-185">32</span></span></p></td>
<td><p><span data-ttu-id="e323f-186">5 </span><span class="sxs-lookup"><span data-stu-id="e323f-186">5</span></span></p></td>
<td><p><span data-ttu-id="e323f-187">997</span><span class="sxs-lookup"><span data-stu-id="e323f-187">997</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-188">未打开的聊天室（具有显式成员资格的常规聊天室）</span><span class="sxs-lookup"><span data-stu-id="e323f-188">Non-open rooms (regular rooms with explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="e323f-189">31040</span><span class="sxs-lookup"><span data-stu-id="e323f-189">31,040</span></span></p></td>
<td><p><span data-ttu-id="e323f-190">1.035</span><span class="sxs-lookup"><span data-stu-id="e323f-190">1.035</span></span></p></td>
<td><p><span data-ttu-id="e323f-191">5 </span><span class="sxs-lookup"><span data-stu-id="e323f-191">5</span></span></p></td>
<td><p><span data-ttu-id="e323f-192">32080</span><span class="sxs-lookup"><span data-stu-id="e323f-192">32,080</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-193">大会堂会议室（其他演示者条目）</span><span class="sxs-lookup"><span data-stu-id="e323f-193">Auditorium rooms (additional presenters entry)</span></span></p></td>
<td><p><span data-ttu-id="e323f-194">0</span><span class="sxs-lookup"><span data-stu-id="e323f-194">0</span></span></p></td>
<td><p><span data-ttu-id="e323f-195">32</span><span class="sxs-lookup"><span data-stu-id="e323f-195">32</span></span></p></td>
<td><p><span data-ttu-id="e323f-196">5 </span><span class="sxs-lookup"><span data-stu-id="e323f-196">5</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-197">通过直接成员管理的聊天室</span><span class="sxs-lookup"><span data-stu-id="e323f-197">Rooms managed by direct membership</span></span></p></td>
<td><p><span data-ttu-id="e323f-198">50%</span><span class="sxs-lookup"><span data-stu-id="e323f-198">50%</span></span></p></td>
<td><p><span data-ttu-id="e323f-199">10</span><span class="sxs-lookup"><span data-stu-id="e323f-199">10%</span></span></p></td>
<td><p><span data-ttu-id="e323f-200">0%</span><span class="sxs-lookup"><span data-stu-id="e323f-200">0%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-201">用户组管理的聊天室比率</span><span class="sxs-lookup"><span data-stu-id="e323f-201">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="e323f-202">50%</span><span class="sxs-lookup"><span data-stu-id="e323f-202">50%</span></span></p></td>
<td><p><span data-ttu-id="e323f-203">90%</span><span class="sxs-lookup"><span data-stu-id="e323f-203">90%</span></span></p></td>
<td><p><span data-ttu-id="e323f-204">100%</span><span class="sxs-lookup"><span data-stu-id="e323f-204">100%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-205">打开的聊天室的每个聊天室的成员资格列表中的用户组（未显式指定）</span><span class="sxs-lookup"><span data-stu-id="e323f-205">User groups in each chat room's membership list for open rooms (not specified explicitly)</span></span></p></td>
<td><p><span data-ttu-id="e323f-206">0</span><span class="sxs-lookup"><span data-stu-id="e323f-206">0</span></span></p></td>
<td><p><span data-ttu-id="e323f-207">0</span><span class="sxs-lookup"><span data-stu-id="e323f-207">0</span></span></p></td>
<td><p><span data-ttu-id="e323f-208">0</span><span class="sxs-lookup"><span data-stu-id="e323f-208">0</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-209">非打开聊天室的每个聊天室的成员资格列表中的用户</span><span class="sxs-lookup"><span data-stu-id="e323f-209">Users in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="e323f-210">30</span><span class="sxs-lookup"><span data-stu-id="e323f-210">30</span></span></p></td>
<td><p><span data-ttu-id="e323f-211">150</span><span class="sxs-lookup"><span data-stu-id="e323f-211">150</span></span></p></td>
<td><p><span data-ttu-id="e323f-212">16000</span><span class="sxs-lookup"><span data-stu-id="e323f-212">16,000</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-213">非打开聊天室的每个聊天室的成员资格列表中的用户组</span><span class="sxs-lookup"><span data-stu-id="e323f-213">User groups in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="e323f-214">3 </span><span class="sxs-lookup"><span data-stu-id="e323f-214">3</span></span></p></td>
<td><p><span data-ttu-id="e323f-215">5 </span><span class="sxs-lookup"><span data-stu-id="e323f-215">5</span></span></p></td>
<td><p><span data-ttu-id="e323f-216">10 </span><span class="sxs-lookup"><span data-stu-id="e323f-216">10</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-217">每个聊天室的管理器列表中的用户和用户组（对于开放和非打开的会议室）</span><span class="sxs-lookup"><span data-stu-id="e323f-217">Users and user groups in each chat room's manager list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="e323f-218">6 </span><span class="sxs-lookup"><span data-stu-id="e323f-218">6</span></span></p></td>
<td><p><span data-ttu-id="e323f-219">6 </span><span class="sxs-lookup"><span data-stu-id="e323f-219">6</span></span></p></td>
<td><p><span data-ttu-id="e323f-220">6 </span><span class="sxs-lookup"><span data-stu-id="e323f-220">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-221">每个大会堂聊天室的演示者列表中的用户和用户组（针对开放和非打开的会议室）</span><span class="sxs-lookup"><span data-stu-id="e323f-221">Users and user groups in each auditorium chat room's presenters list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="e323f-222">6 </span><span class="sxs-lookup"><span data-stu-id="e323f-222">6</span></span></p></td>
<td><p><span data-ttu-id="e323f-223">6 </span><span class="sxs-lookup"><span data-stu-id="e323f-223">6</span></span></p></td>
<td><p><span data-ttu-id="e323f-224">6 </span><span class="sxs-lookup"><span data-stu-id="e323f-224">6</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-225">跨所有非开放聊天室的基于用户的成员资格实体</span><span class="sxs-lookup"><span data-stu-id="e323f-225">User-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="e323f-226">465600</span><span class="sxs-lookup"><span data-stu-id="e323f-226">465,600</span></span></p></td>
<td><p><span data-ttu-id="e323f-227">15520</span><span class="sxs-lookup"><span data-stu-id="e323f-227">15,520</span></span></p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-228">跨所有非开放聊天室的基于用户组的成员实体</span><span class="sxs-lookup"><span data-stu-id="e323f-228">User-group-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="e323f-229">46560</span><span class="sxs-lookup"><span data-stu-id="e323f-229">46,560</span></span></p></td>
<td><p><span data-ttu-id="e323f-230">4656</span><span class="sxs-lookup"><span data-stu-id="e323f-230">4656</span></span></p></td>
<td><p><span data-ttu-id="e323f-231">50</span><span class="sxs-lookup"><span data-stu-id="e323f-231">50</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-232">跨所有大会堂聊天室的基于用户和用户组的实体</span><span class="sxs-lookup"><span data-stu-id="e323f-232">Users and user groups based entities across all auditorium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="e323f-233">0</span><span class="sxs-lookup"><span data-stu-id="e323f-233">0</span></span></p></td>
<td><p><span data-ttu-id="e323f-234">192</span><span class="sxs-lookup"><span data-stu-id="e323f-234">192</span></span></p></td>
<td><p><span data-ttu-id="e323f-235">50</span><span class="sxs-lookup"><span data-stu-id="e323f-235">50</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-236">跨所有聊天室管理器列表的基于用户和用户组的管理器实体</span><span class="sxs-lookup"><span data-stu-id="e323f-236">Users and user groups based manager entities across all chat rooms manager lists</span></span></p></td>
<td><p><span data-ttu-id="e323f-237">192000</span><span class="sxs-lookup"><span data-stu-id="e323f-237">192,000</span></span></p></td>
<td><p><span data-ttu-id="e323f-238">6400</span><span class="sxs-lookup"><span data-stu-id="e323f-238">6,400</span></span></p></td>
<td><p><span data-ttu-id="e323f-239">60</span><span class="sxs-lookup"><span data-stu-id="e323f-239">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-240">每个聊天室的活动用户数</span><span class="sxs-lookup"><span data-stu-id="e323f-240">Active users per chat room</span></span></p></td>
<td><p><span data-ttu-id="e323f-241"><em>30</em></span><span class="sxs-lookup"><span data-stu-id="e323f-241"><em>30</em></span></span></p></td>
<td><p><span data-ttu-id="e323f-242"><em>150</em></span><span class="sxs-lookup"><span data-stu-id="e323f-242"><em>150</em></span></span></p></td>
<td><p><span data-ttu-id="e323f-243"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="e323f-243"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-244">每个用户的聊天室数量</span><span class="sxs-lookup"><span data-stu-id="e323f-244">Chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="e323f-245"><em>12</em></span><span class="sxs-lookup"><span data-stu-id="e323f-245"><em>12</em></span></span></p></td>
<td><p><span data-ttu-id="e323f-246"><em>双面</em></span><span class="sxs-lookup"><span data-stu-id="e323f-246"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="e323f-247"><em>双面</em></span><span class="sxs-lookup"><span data-stu-id="e323f-247"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="e323f-248"><em>位</em></span><span class="sxs-lookup"><span data-stu-id="e323f-248"><em>16</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-249">每个聊天室成员列表中用户组的数量</span><span class="sxs-lookup"><span data-stu-id="e323f-249">User groups in each chat room’s membership list</span></span></p></td>
<td><p><span data-ttu-id="e323f-250"><em>10</em></span><span class="sxs-lookup"><span data-stu-id="e323f-250"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="e323f-251"><em>10</em></span><span class="sxs-lookup"><span data-stu-id="e323f-251"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="e323f-252"><em>个</em></span><span class="sxs-lookup"><span data-stu-id="e323f-252"><em>15</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-253">用户组管理的聊天室比率</span><span class="sxs-lookup"><span data-stu-id="e323f-253">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="e323f-254"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="e323f-254"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="e323f-255"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="e323f-255"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="e323f-256"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="e323f-256"><em>50%</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-257">所有聊天室中基于用户组的成员实体数量</span><span class="sxs-lookup"><span data-stu-id="e323f-257">User-group-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="e323f-258">155200</span><span class="sxs-lookup"><span data-stu-id="e323f-258">155,200</span></span></p></td>
<td><p><span data-ttu-id="e323f-259">5173</span><span class="sxs-lookup"><span data-stu-id="e323f-259">5173</span></span></p></td>
<td><p><span data-ttu-id="e323f-260">68</span><span class="sxs-lookup"><span data-stu-id="e323f-260">68</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-261">所有聊天室中基于用户的成员实体数量</span><span class="sxs-lookup"><span data-stu-id="e323f-261">User-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="e323f-262">465600</span><span class="sxs-lookup"><span data-stu-id="e323f-262">465,600</span></span></p></td>
<td><p><span data-ttu-id="e323f-263">77600</span><span class="sxs-lookup"><span data-stu-id="e323f-263">77,600</span></span></p></td>
<td><p><span data-ttu-id="e323f-264">72000</span><span class="sxs-lookup"><span data-stu-id="e323f-264">72,000</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-265">每个聊天室的管理者、演示者和范围列表中的用户和用户组数量</span><span class="sxs-lookup"><span data-stu-id="e323f-265">Users and user groups in each chat room's manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="e323f-266">6 </span><span class="sxs-lookup"><span data-stu-id="e323f-266">6</span></span></p></td>
<td><p><span data-ttu-id="e323f-267">6 </span><span class="sxs-lookup"><span data-stu-id="e323f-267">6</span></span></p></td>
<td><p><span data-ttu-id="e323f-268">6 </span><span class="sxs-lookup"><span data-stu-id="e323f-268">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-269">跨聊天室的管理者、演示者和范围列表中的用户和用户组</span><span class="sxs-lookup"><span data-stu-id="e323f-269">Users and user groups across all chat rooms' manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="e323f-270">192000</span><span class="sxs-lookup"><span data-stu-id="e323f-270">192,000</span></span></p></td>
<td><p><span data-ttu-id="e323f-271">6400</span><span class="sxs-lookup"><span data-stu-id="e323f-271">6400</span></span></p></td>
<td><p><span data-ttu-id="e323f-272">60</span><span class="sxs-lookup"><span data-stu-id="e323f-272">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-273">访问控制项数量</span><span class="sxs-lookup"><span data-stu-id="e323f-273">Access control entries</span></span></p></td>
<td><p><span data-ttu-id="e323f-274">704160</span><span class="sxs-lookup"><span data-stu-id="e323f-274">704,160</span></span></p></td>
<td><p><span data-ttu-id="e323f-275">26768</span><span class="sxs-lookup"><span data-stu-id="e323f-275">26,768</span></span></p></td>
<td><p><span data-ttu-id="e323f-276">160</span><span class="sxs-lookup"><span data-stu-id="e323f-276">160</span></span></p></td>
<td><p><span data-ttu-id="e323f-277">731088</span><span class="sxs-lookup"><span data-stu-id="e323f-277">731,088</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-278">最大访问控制项数量</span><span class="sxs-lookup"><span data-stu-id="e323f-278">Maximum access control entries</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="e323f-279">2000000</span><span class="sxs-lookup"><span data-stu-id="e323f-279">2,000,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e323f-280">在上面的示例中，当您根据建议的准则部署持久聊天服务器时，他们可以跨启用了合规性的四个服务器池处理最多80000个活动用户。</span><span class="sxs-lookup"><span data-stu-id="e323f-280">In the preceding sample, when you deploy the Persistent Chat Servers according to the recommended guidelines, they can handle up to 80,000 active users across a four-server pool with compliance enabled.</span></span>

<span data-ttu-id="e323f-281">此示例显示了分类为小型（在任意给定时间为30个活动用户）、中型（150活动用户）和大型（16000个活动用户）的聊天工作室。</span><span class="sxs-lookup"><span data-stu-id="e323f-281">This sample shows chat rooms categorized as small (30 active users at any given time), medium (150 active users), and large (16,000 active users).</span></span> <span data-ttu-id="e323f-282">根据以下总数计算特定大小的聊天室数量：</span><span class="sxs-lookup"><span data-stu-id="e323f-282">The number of chat rooms of a certain size is computed based on the total number of:</span></span>

  - <span data-ttu-id="e323f-283">系统中的活动用户数量</span><span class="sxs-lookup"><span data-stu-id="e323f-283">Active users in the system</span></span>

  - <span data-ttu-id="e323f-284">给定大小的聊天室中的活动用户数量</span><span class="sxs-lookup"><span data-stu-id="e323f-284">Active users in chat rooms of the given size</span></span>

  - <span data-ttu-id="e323f-285">单个用户加入的给定大小的聊天室数量</span><span class="sxs-lookup"><span data-stu-id="e323f-285">Chat rooms of the given size that a single user joins</span></span>

<span data-ttu-id="e323f-286">对于每个聊天室，上述容量规划表指定与聊天室相关联的访问控制条目数，包括直接分配到聊天室的条目。</span><span class="sxs-lookup"><span data-stu-id="e323f-286">For each chat room, the preceding capacity planning table specifies the number of access control entries that are associated with the chat room, including entries that are assigned directly to the chat room.</span></span> <span data-ttu-id="e323f-287">您可以通过使用访问控制列表（Acl）来控制对各个聊天室的访问。</span><span class="sxs-lookup"><span data-stu-id="e323f-287">You can control access to individual chat rooms by using access control lists (ACLs).</span></span> <span data-ttu-id="e323f-288">您还可以在类别级别控制访问权限。</span><span class="sxs-lookup"><span data-stu-id="e323f-288">You can also control access at the category level.</span></span> <span data-ttu-id="e323f-289">在 ACL 中，单个访问控制项可以是用户组（例如，安全组、通讯组列表或单个用户）。</span><span class="sxs-lookup"><span data-stu-id="e323f-289">In an ACL, an individual access control entry can be either a user group—for example, a security group, a distribution list, or a single user.</span></span> <span data-ttu-id="e323f-290">您可以为聊天室管理者、演示者和成员定义访问控制条目。</span><span class="sxs-lookup"><span data-stu-id="e323f-290">You can define access control entries for chat room managers, presenters, and members.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e323f-291">在规划管理聊天室的策略时，请记住允许的访问控制条目总数为2000000。</span><span class="sxs-lookup"><span data-stu-id="e323f-291">In planning your strategy for managing chat rooms, keep in mind that the total number of allowed access control entries is 2 million.</span></span> <span data-ttu-id="e323f-292">如果计算出的访问控制条目超过2000000，服务器性能可能会显著降低。</span><span class="sxs-lookup"><span data-stu-id="e323f-292">If the calculated access control entries exceed 2 million, server performance could degrade significantly.</span></span> <span data-ttu-id="e323f-293">若要避免此问题，请尽可能确保您的访问控制项是用户组而不是单个用户。</span><span class="sxs-lookup"><span data-stu-id="e323f-293">To avoid this issue, whenever possible, be sure that your access control entries are user groups instead of individual users.</span></span>



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a><span data-ttu-id="e323f-294">管理邀请的聊天室访问的容量规划</span><span class="sxs-lookup"><span data-stu-id="e323f-294">Capacity Planning for Managing Chat Room Access by Invitation</span></span>

<span data-ttu-id="e323f-295">您可以使用以下容量规划表来了解持久聊天服务器在配置为发送邀请时在持久聊天数据库中创建和存储的邀请数。</span><span class="sxs-lookup"><span data-stu-id="e323f-295">You can use the following capacity planning table to understand the number of invitations that Persistent Chat Server creates and stores in the Persistent Chat database when it is configured to send invitations.</span></span> <span data-ttu-id="e323f-296">您可以使用 Lync Server 控制面板中的 "**聊天室类别设置**" 页或使用 Windows PowerShell Cmdlet 管理类别上的邀请。 **csPersistentChatCategory**。</span><span class="sxs-lookup"><span data-stu-id="e323f-296">You manage invitations on the Category by using the **Chat Room Category settings** page in the Lync Server Control Panel, or by using the Windows PowerShell cmdlet, **set-csPersistentChatCategory**.</span></span> <span data-ttu-id="e323f-297">您可以使用从 Lync 客户端启动的**会议室管理**页面或使用 Windows PowerShell Cmdlet （ **set-cspersistentchatroom**）来管理聊天室上的邀请（根据类别允许的方式）。</span><span class="sxs-lookup"><span data-stu-id="e323f-297">You can manage invitations on a chat room (in line with what the category allows) by using the **Room Management** page launched from the Lync client, or by using a Windows PowerShell cmdlet, **set-csPersistentChatRoom**.</span></span>

<span data-ttu-id="e323f-298">下表中的示例数据假定，在所有聊天室的50% 的**聊天室设置**页上，"**邀请**" 选项设置为 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="e323f-298">The sample data in the following table assumes that, on the **Chat room settings** page for 50 percent of all chat rooms, the **Invitations** option is set to **Yes**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e323f-299">如果服务器生成的邀请数的计算值超过1000000，服务器性能可能会显著降低。</span><span class="sxs-lookup"><span data-stu-id="e323f-299">If the calculated value for the number of invitations that is generated by the server exceeds 1 million, server performance could degrade significantly.</span></span> <span data-ttu-id="e323f-300">若要避免此问题，请确保将配置为发送邀请的聊天室的数量减至，或限制可加入聊天室的用户数，这些聊天室已配置为发送邀请。</span><span class="sxs-lookup"><span data-stu-id="e323f-300">To avoid this issue, be sure that you minimize the number of chat rooms that are configured to send invitations or restrict the number of users who can join chat rooms that have been configured to send invitations.</span></span>



</div>

### <a name="chat-room-access-by-invitation-sample"></a><span data-ttu-id="e323f-301">邀请的聊天室访问示例</span><span class="sxs-lookup"><span data-stu-id="e323f-301">Chat Room Access by Invitation Sample</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="e323f-302">小聊天室</span><span class="sxs-lookup"><span data-stu-id="e323f-302">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="e323f-303">中型聊天室</span><span class="sxs-lookup"><span data-stu-id="e323f-303">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="e323f-304">大型聊天室</span><span class="sxs-lookup"><span data-stu-id="e323f-304">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="e323f-305">总计</span><span class="sxs-lookup"><span data-stu-id="e323f-305">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e323f-306">可以访问聊天室的用户</span><span class="sxs-lookup"><span data-stu-id="e323f-306">Users who can access chat room</span></span></p></td>
<td><p><span data-ttu-id="e323f-307">每个会议室30个</span><span class="sxs-lookup"><span data-stu-id="e323f-307">30 per room</span></span></p></td>
<td><p><span data-ttu-id="e323f-308">每个会议室150</span><span class="sxs-lookup"><span data-stu-id="e323f-308">150 per room</span></span></p></td>
<td><p><span data-ttu-id="e323f-309">每个会议室16000</span><span class="sxs-lookup"><span data-stu-id="e323f-309">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-310">具有邀请的聊天室的百分比</span><span class="sxs-lookup"><span data-stu-id="e323f-310">Percentage of rooms that have invitations</span></span></p></td>
<td><p><span data-ttu-id="e323f-311">50%</span><span class="sxs-lookup"><span data-stu-id="e323f-311">50%</span></span></p></td>
<td><p><span data-ttu-id="e323f-312">50%</span><span class="sxs-lookup"><span data-stu-id="e323f-312">50%</span></span></p></td>
<td><p><span data-ttu-id="e323f-313">50%</span><span class="sxs-lookup"><span data-stu-id="e323f-313">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-314">配置为发送邀请的聊天室数量</span><span class="sxs-lookup"><span data-stu-id="e323f-314">Chat rooms configured to send invitations</span></span></p></td>
<td><p><span data-ttu-id="e323f-315"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="e323f-315"><em>16,000</em></span></span></p></td>
<td><p><span data-ttu-id="e323f-316"><em>533</em></span><span class="sxs-lookup"><span data-stu-id="e323f-316"><em>533</em></span></span></p></td>
<td><p><span data-ttu-id="e323f-317"><em>5</em></span><span class="sxs-lookup"><span data-stu-id="e323f-317"><em>5</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-318">可以访问聊天室的用户数</span><span class="sxs-lookup"><span data-stu-id="e323f-318">Users who can access the chat room</span></span></p></td>
<td><p><span data-ttu-id="e323f-319"><em>60</em></span><span class="sxs-lookup"><span data-stu-id="e323f-319"><em>60</em></span></span></p></td>
<td><p><span data-ttu-id="e323f-320"><em>225</em></span><span class="sxs-lookup"><span data-stu-id="e323f-320"><em>225</em></span></span></p></td>
<td><p><span data-ttu-id="e323f-321"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="e323f-321"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-322">持久聊天服务器生成的邀请</span><span class="sxs-lookup"><span data-stu-id="e323f-322">Invitations generated by Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="e323f-323">960000</span><span class="sxs-lookup"><span data-stu-id="e323f-323">960,000</span></span></p></td>
<td><p><span data-ttu-id="e323f-324">120000</span><span class="sxs-lookup"><span data-stu-id="e323f-324">120,000</span></span></p></td>
<td><p><span data-ttu-id="e323f-325">80000</span><span class="sxs-lookup"><span data-stu-id="e323f-325">80,000</span></span></p></td>
<td><p><span data-ttu-id="e323f-326">1160000</span><span class="sxs-lookup"><span data-stu-id="e323f-326">1,160,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-327">允许的最大邀请数量</span><span class="sxs-lookup"><span data-stu-id="e323f-327">Maximum allowable number of invitations</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="e323f-328">2000000</span><span class="sxs-lookup"><span data-stu-id="e323f-328">2,000,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-329">模型 1-以预期的每天每个会议室的邮件数开头</span><span class="sxs-lookup"><span data-stu-id="e323f-329">Model 1 - Start with expected number of messages per room per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-330">每个会议室的聊天速率（每天）</span><span class="sxs-lookup"><span data-stu-id="e323f-330">Chat Rate Per Room (per day)</span></span></p></td>
<td><p><span data-ttu-id="e323f-331">50</span><span class="sxs-lookup"><span data-stu-id="e323f-331">50</span></span></p></td>
<td><p><span data-ttu-id="e323f-332">500</span><span class="sxs-lookup"><span data-stu-id="e323f-332">500</span></span></p></td>
<td><p><span data-ttu-id="e323f-333">100</span><span class="sxs-lookup"><span data-stu-id="e323f-333">100</span></span></p></td>
<td><p><span data-ttu-id="e323f-334">650</span><span class="sxs-lookup"><span data-stu-id="e323f-334">650</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-335">所有聊天室的聊天速率（每秒）</span><span class="sxs-lookup"><span data-stu-id="e323f-335">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="e323f-336">55.56</span><span class="sxs-lookup"><span data-stu-id="e323f-336">55.56</span></span></p></td>
<td><p><span data-ttu-id="e323f-337">18.52</span><span class="sxs-lookup"><span data-stu-id="e323f-337">18.52</span></span></p></td>
<td><p><span data-ttu-id="e323f-338">0.03</span><span class="sxs-lookup"><span data-stu-id="e323f-338">0.03</span></span></p></td>
<td><p><span data-ttu-id="e323f-339">74</span><span class="sxs-lookup"><span data-stu-id="e323f-339">74</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-340">模型 2-以每个用户每天发布的邮件数开头</span><span class="sxs-lookup"><span data-stu-id="e323f-340">Model 2 - Start with number of messages posted per user per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-341">每个用户每天的聊天速率</span><span class="sxs-lookup"><span data-stu-id="e323f-341">Chat rate per user per day</span></span></p></td>
<td><p><span data-ttu-id="e323f-342">15 </span><span class="sxs-lookup"><span data-stu-id="e323f-342">15</span></span></p></td>
<td><p><span data-ttu-id="e323f-343">5 </span><span class="sxs-lookup"><span data-stu-id="e323f-343">5</span></span></p></td>
<td><p><span data-ttu-id="e323f-344">0.1</span><span class="sxs-lookup"><span data-stu-id="e323f-344">0.1</span></span></p></td>
<td><p><span data-ttu-id="e323f-345">20</span><span class="sxs-lookup"><span data-stu-id="e323f-345">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-346">每个会议室的聊天速率（每天）</span><span class="sxs-lookup"><span data-stu-id="e323f-346">Chat rate per room (per day)</span></span></p></td>
<td><p><span data-ttu-id="e323f-347">38</span><span class="sxs-lookup"><span data-stu-id="e323f-347">38</span></span></p></td>
<td><p><span data-ttu-id="e323f-348">375</span><span class="sxs-lookup"><span data-stu-id="e323f-348">375</span></span></p></td>
<td><p><span data-ttu-id="e323f-349">800</span><span class="sxs-lookup"><span data-stu-id="e323f-349">800</span></span></p></td>
<td><p><span data-ttu-id="e323f-350">1213</span><span class="sxs-lookup"><span data-stu-id="e323f-350">1,213</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-351">所有聊天室的聊天速率（每秒）</span><span class="sxs-lookup"><span data-stu-id="e323f-351">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="e323f-352">41.67</span><span class="sxs-lookup"><span data-stu-id="e323f-352">41.67</span></span></p></td>
<td><p><span data-ttu-id="e323f-353">13.89</span><span class="sxs-lookup"><span data-stu-id="e323f-353">13.89</span></span></p></td>
<td><p><span data-ttu-id="e323f-354">0.28</span><span class="sxs-lookup"><span data-stu-id="e323f-354">0.28</span></span></p></td>
<td><p><span data-ttu-id="e323f-355">56</span><span class="sxs-lookup"><span data-stu-id="e323f-355">56</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="e323f-356">持久聊天服务器性能用户模型</span><span class="sxs-lookup"><span data-stu-id="e323f-356">Persistent Chat Server Performance User Model</span></span>

<span data-ttu-id="e323f-357">下表介绍持久聊天服务器的用户模型。</span><span class="sxs-lookup"><span data-stu-id="e323f-357">The following table describes the user model for Persistent Chat Server.</span></span> <span data-ttu-id="e323f-358">它提供了容量规划要求的基础，并表示在四台服务器上有80000个并发用户的典型组织。</span><span class="sxs-lookup"><span data-stu-id="e323f-358">It provides the basis for the capacity planning requirements and represents a typical organization with 80,000 concurrent users on four servers.</span></span>

### <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="e323f-359">持久聊天服务器性能用户模型</span><span class="sxs-lookup"><span data-stu-id="e323f-359">Persistent Chat Server Performance User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e323f-360">连接的活动用户数</span><span class="sxs-lookup"><span data-stu-id="e323f-360">Number of active users connected</span></span></p></td>
<td><p><span data-ttu-id="e323f-361">80000</span><span class="sxs-lookup"><span data-stu-id="e323f-361">80,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-362">持久聊天服务器服务实例的数量</span><span class="sxs-lookup"><span data-stu-id="e323f-362">Number of Persistent Chat Server service instances</span></span></p></td>
<td><p><span data-ttu-id="e323f-363">4 </span><span class="sxs-lookup"><span data-stu-id="e323f-363">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-364">小聊天室的大小</span><span class="sxs-lookup"><span data-stu-id="e323f-364">Size of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="e323f-365">30 个用户</span><span class="sxs-lookup"><span data-stu-id="e323f-365">30 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-366">中聊天室的大小</span><span class="sxs-lookup"><span data-stu-id="e323f-366">Size of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="e323f-367">150 个用户</span><span class="sxs-lookup"><span data-stu-id="e323f-367">150 users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-368">大聊天室的大小</span><span class="sxs-lookup"><span data-stu-id="e323f-368">Size of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="e323f-369">16000用户</span><span class="sxs-lookup"><span data-stu-id="e323f-369">16,000 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-370">聊天室的总数</span><span class="sxs-lookup"><span data-stu-id="e323f-370">Total number of chat rooms</span></span></p></td>
<td><p><span data-ttu-id="e323f-371">33077</span><span class="sxs-lookup"><span data-stu-id="e323f-371">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-372">小聊天室的数量</span><span class="sxs-lookup"><span data-stu-id="e323f-372">Number of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="e323f-373">32000</span><span class="sxs-lookup"><span data-stu-id="e323f-373">32,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-374">中聊天室的数量</span><span class="sxs-lookup"><span data-stu-id="e323f-374">Number of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="e323f-375">1067</span><span class="sxs-lookup"><span data-stu-id="e323f-375">1,067</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-376">大聊天室的数量</span><span class="sxs-lookup"><span data-stu-id="e323f-376">Number of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="e323f-377">10 </span><span class="sxs-lookup"><span data-stu-id="e323f-377">10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-378">每个用户的聊天室总数</span><span class="sxs-lookup"><span data-stu-id="e323f-378">Total number of chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="e323f-379">16 </span><span class="sxs-lookup"><span data-stu-id="e323f-379">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-380">每个用户的小聊天室数量</span><span class="sxs-lookup"><span data-stu-id="e323f-380">Number of small chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="e323f-381">12 </span><span class="sxs-lookup"><span data-stu-id="e323f-381">12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-382">每个用户的中聊天室数量</span><span class="sxs-lookup"><span data-stu-id="e323f-382">Number of medium chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="e323f-383">2 </span><span class="sxs-lookup"><span data-stu-id="e323f-383">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-384">每个用户的大聊天室数量</span><span class="sxs-lookup"><span data-stu-id="e323f-384">Number of large chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="e323f-385">2 </span><span class="sxs-lookup"><span data-stu-id="e323f-385">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-386">每个用户加入的聊天室数</span><span class="sxs-lookup"><span data-stu-id="e323f-386">Number of rooms joined per user</span></span></p></td>
<td><p><span data-ttu-id="e323f-387">24</span><span class="sxs-lookup"><span data-stu-id="e323f-387">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-388">峰值加入速率</span><span class="sxs-lookup"><span data-stu-id="e323f-388">Peak join rate</span></span></p></td>
<td><p><span data-ttu-id="e323f-389">10/秒</span><span class="sxs-lookup"><span data-stu-id="e323f-389">10/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-390">总聊天速率</span><span class="sxs-lookup"><span data-stu-id="e323f-390">Total chat rate</span></span></p></td>
<td><p><span data-ttu-id="e323f-391">24/秒</span><span class="sxs-lookup"><span data-stu-id="e323f-391">24/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-392">小聊天室的聊天速率</span><span class="sxs-lookup"><span data-stu-id="e323f-392">Chat rate for small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="e323f-393">22.22/秒</span><span class="sxs-lookup"><span data-stu-id="e323f-393">22.22/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-394">中聊天室的聊天速率</span><span class="sxs-lookup"><span data-stu-id="e323f-394">Chat rate for medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="e323f-395">1.67/秒</span><span class="sxs-lookup"><span data-stu-id="e323f-395">1.67/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-396">大聊天室的聊天速率</span><span class="sxs-lookup"><span data-stu-id="e323f-396">Chat rate for large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="e323f-397">~ 0.15/秒</span><span class="sxs-lookup"><span data-stu-id="e323f-397">~0.15/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-398">为邀请配置的聊天室的百分比</span><span class="sxs-lookup"><span data-stu-id="e323f-398">Percentage of chat rooms configured for invitations</span></span></p></td>
<td><p><span data-ttu-id="e323f-399">50%</span><span class="sxs-lookup"><span data-stu-id="e323f-399">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-400">直接成员身份的百分比</span><span class="sxs-lookup"><span data-stu-id="e323f-400">Percentage of direct memberships</span></span></p></td>
<td><p><span data-ttu-id="e323f-401">50%</span><span class="sxs-lookup"><span data-stu-id="e323f-401">50%</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-402">组成员身份的百分比</span><span class="sxs-lookup"><span data-stu-id="e323f-402">Percentage of group memberships</span></span></p></td>
<td><p><span data-ttu-id="e323f-403">50%</span><span class="sxs-lookup"><span data-stu-id="e323f-403">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-404">Active Directory 域服务中的平均祖先隶属关系数</span><span class="sxs-lookup"><span data-stu-id="e323f-404">Average number of ancestor affiliations in Active Directory Domain Services</span></span></p></td>
<td><p><span data-ttu-id="e323f-405">100 - 200</span><span class="sxs-lookup"><span data-stu-id="e323f-405">100 - 200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-406">每个用户的订阅联系人数</span><span class="sxs-lookup"><span data-stu-id="e323f-406">Number of subscribed contacts per user</span></span></p></td>
<td><p><span data-ttu-id="e323f-407">80</span><span class="sxs-lookup"><span data-stu-id="e323f-407">80</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-408">每个用户的平均终结点数</span><span class="sxs-lookup"><span data-stu-id="e323f-408">Average number of endpoints per user</span></span></p></td>
<td><p><span data-ttu-id="e323f-409">1.5</span><span class="sxs-lookup"><span data-stu-id="e323f-409">1.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-410">每个终结点的平均可见聊天室数</span><span class="sxs-lookup"><span data-stu-id="e323f-410">Average number of visible chat rooms per endpoint</span></span></p></td>
<td><p><span data-ttu-id="e323f-411">1.5</span><span class="sxs-lookup"><span data-stu-id="e323f-411">1.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-412">每个用户的平均可见聊天室数</span><span class="sxs-lookup"><span data-stu-id="e323f-412">Average number of visible chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="e323f-413">2.25 （50%，共1个会议室，2个会议室为50%）;最多6个会议室打开，每个显示器一个</span><span class="sxs-lookup"><span data-stu-id="e323f-413">2.25 (50% for 1 room and 50% for 2 rooms); Up to 6 rooms open, one per monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-414">每个时间间隔轮询的参与者数量</span><span class="sxs-lookup"><span data-stu-id="e323f-414">Number of participants polled per interval</span></span></p></td>
<td><p><span data-ttu-id="e323f-415">每个可见聊天室25个</span><span class="sxs-lookup"><span data-stu-id="e323f-415">25 per visible chat room</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-416">轮询间隔时长</span><span class="sxs-lookup"><span data-stu-id="e323f-416">Length of polling interval</span></span></p></td>
<td><p><span data-ttu-id="e323f-417">5 分钟</span><span class="sxs-lookup"><span data-stu-id="e323f-417">5 minutes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-418">每秒钟轮询的参与者数量</span><span class="sxs-lookup"><span data-stu-id="e323f-418">Number of participants polled per second</span></span></p></td>
<td><p><span data-ttu-id="e323f-419">15,000</span><span class="sxs-lookup"><span data-stu-id="e323f-419">15,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e323f-420">每个用户每小时的状态更改数量</span><span class="sxs-lookup"><span data-stu-id="e323f-420">Number of presence changes per hour per user</span></span></p></td>
<td><p><span data-ttu-id="e323f-421">6 </span><span class="sxs-lookup"><span data-stu-id="e323f-421">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e323f-422">每秒钟的状态更改数量</span><span class="sxs-lookup"><span data-stu-id="e323f-422">Number of presence changes per second</span></span></p></td>
<td><p><span data-ttu-id="e323f-423">133.33</span><span class="sxs-lookup"><span data-stu-id="e323f-423">133.33</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

