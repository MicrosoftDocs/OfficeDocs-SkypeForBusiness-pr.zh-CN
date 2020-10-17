---
title: Lync Server 2013：持久聊天服务器的容量规划
description: Lync Server 2013：持久聊天服务器的容量规划。
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
ms.openlocfilehash: f78f9f3666fb272b808ef36da2d3010f451d0079
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544488"
---
# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="8feba-103">Lync Server 2013 中持久聊天服务器的容量规划</span><span class="sxs-lookup"><span data-stu-id="8feba-103">Capacity planning for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8feba-104">_**上次修改的主题：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="8feba-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="8feba-105">持久聊天服务器可以执行多用户实时聊天，可以持续进行，以便将来检索和搜索。</span><span class="sxs-lookup"><span data-stu-id="8feba-105">Persistent Chat Server can perform multi-user real-time chat that can persist for future retrieval and search.</span></span> <span data-ttu-id="8feba-106">与在用户邮箱中保存的组即时消息 (IM) 的不同之处是，如果配置了对话历史记录，则持久聊天服务器会话将保持打开状态，并将内容保存在服务器上，同时还会在正在进行的会话中的邮件、文件、Url 和其他数据中进行保存。</span><span class="sxs-lookup"><span data-stu-id="8feba-106">Unlike group instant messaging (IM) that is saved in a user’s mailbox if conversation history is configured, a Persistent Chat Server session stays open longer, and the content is saved on a server, along with the messages, files, URLs, and other data that are part of an ongoing conversation.</span></span>

<span data-ttu-id="8feba-107">容量规划是准备部署持久聊天服务器的重要部分。</span><span class="sxs-lookup"><span data-stu-id="8feba-107">Capacity planning is an important part of preparing to deploy Persistent Chat Server.</span></span> <span data-ttu-id="8feba-108">本主题提供了有关受支持的持久聊天服务器拓扑和容量规划表的详细信息，您可以使用这些表来确定适用于您的部署的最佳配置。</span><span class="sxs-lookup"><span data-stu-id="8feba-108">This topic provides details about supported Persistent Chat Server topologies and capacity planning tables that you can use to determine the best configuration for your deployment.</span></span> <span data-ttu-id="8feba-109">此外，还介绍了如何最好地管理在高峰时间需要更大容量的持久聊天服务器部署。</span><span class="sxs-lookup"><span data-stu-id="8feba-109">It also describes how to best manage Persistent Chat Server deployments that require greater capacity at peak times.</span></span>

<span data-ttu-id="8feba-110">若要下载持久聊天服务器，请参阅在上的 "Microsoft Lync Server 13 持久聊天服务器" [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539) 。</span><span class="sxs-lookup"><span data-stu-id="8feba-110">To download Persistent Chat Server, see "Microsoft Lync Server 13 Persistent Chat Server" at [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539).</span></span>

<span data-ttu-id="8feba-111">有关安装持久聊天服务器的详细信息，请参阅部署文档中的在 [Lync server 2013 中安装持久聊天服务器](lync-server-2013-installing-persistent-chat-server.md) 和 [在 lync Server 2013 中配置持久聊天服务器](lync-server-2013-configuring-persistent-chat-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="8feba-111">For details about installing Persistent Chat Server, see [Installing Persistent Chat Server in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) and [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="8feba-112">支持工具（如 Lync Server 规划工具）可以进一步帮助您进行容量规划。</span><span class="sxs-lookup"><span data-stu-id="8feba-112">Support tools, such as Lync Server Planning Tool, can further assist you with capacity planning.</span></span> <span data-ttu-id="8feba-113">有关规划工具的详细信息，请参阅规划文档中的 [开始规划 Lync Server 2013 的规划过程](lync-server-2013-beginning-the-planning-process.md) 。</span><span class="sxs-lookup"><span data-stu-id="8feba-113">For details about the Planning Tool, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<div>

## <a name="persistent-chat-server-supported-topologies"></a><span data-ttu-id="8feba-114">持久聊天服务器支持的拓扑</span><span class="sxs-lookup"><span data-stu-id="8feba-114">Persistent Chat Server Supported Topologies</span></span>

<span data-ttu-id="8feba-115">您可以在单服务器或多服务器池中部署持久聊天服务器，也可以使用单一池或多池拓扑。</span><span class="sxs-lookup"><span data-stu-id="8feba-115">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span>

<span data-ttu-id="8feba-116">现在，我们还支持适用于新的 Lync Server 2013 部署的 Standard Edition server 上的持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="8feba-116">We now also support Persistent Chat Server on Standard Edition server for new Lync Server 2013 deployments.</span></span> <span data-ttu-id="8feba-117">但是，性能和规模将受到影响，由于没有适用于此新部署的高可用性选项，因此我们预计您将主要用于概念验证、评估等目的。</span><span class="sxs-lookup"><span data-stu-id="8feba-117">However, performance and scale will be affected, and because there is no high availability option for this new deployment, we expect you to use this primarily for the purposes of proof of concept, evaluation, and so on.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8feba-118">有关这两种拓扑的更多详细信息，请参阅部署文档中的在 lync server 2013 中的 "在 <A href="lync-server-2013-planning-for-persistent-chat-server.md">lync server 中规划持久聊天服务器</A> " 和 " <A href="lync-server-2013-deploying-persistent-chat-server.md">在 lync Server 2013 中部署持久聊天服务器</A> "。</span><span class="sxs-lookup"><span data-stu-id="8feba-118">For additional details about both topologies, see <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for Persistent Chat Server in Lync Server 2013</A> in this documentation set and <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="8feba-119">单服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="8feba-119">Single-Server Topology</span></span>

<span data-ttu-id="8feba-120">持久聊天服务器的最小配置和最简单部署是一个持久聊天服务器前端服务器拓扑。</span><span class="sxs-lookup"><span data-stu-id="8feba-120">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="8feba-121">此部署需要运行持久聊天服务器 (的单个服务器，如果符合性已启用，则可以选择运行合规性服务) 、承载 SQL Server 数据库的服务器以及是否需要合规性，以存储合规性数据的 SQL Server 数据库为依据。</span><span class="sxs-lookup"><span data-stu-id="8feba-121">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8feba-122">您不能向作为拓扑生成器中的单个服务器部署启动的持久聊天服务器池添加其他服务器。</span><span class="sxs-lookup"><span data-stu-id="8feba-122">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="8feba-123">我们建议使用多服务器池拓扑，即使您使用的是一台服务器。</span><span class="sxs-lookup"><span data-stu-id="8feba-123">We recommend using the multiple-server pool topology, even if you’re using a single server.</span></span> <span data-ttu-id="8feba-124">这样，你将能够在以后添加更多服务器（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="8feba-124">This is so that you’ll be able to add more servers later, if it's necessary.</span></span> 


</div>

<span data-ttu-id="8feba-125">下图显示了符合条件的单个持久聊天服务器前端服务器的拓扑的所有必需组件和可选组件。</span><span class="sxs-lookup"><span data-stu-id="8feba-125">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="8feba-126">**单个持久聊天服务器**</span><span class="sxs-lookup"><span data-stu-id="8feba-126">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="8feba-127">![单服务器拓扑与合规性服务](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "单服务器拓扑与合规性服务")</span><span class="sxs-lookup"><span data-stu-id="8feba-127">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="8feba-128">多服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="8feba-128">Multiple-Server Topology</span></span>

<span data-ttu-id="8feba-129">若要提供更大的容量和可靠性，可以部署多服务器拓扑，如在 [Lync server 2013 中规划持久聊天服务器中](lync-server-2013-planning-for-persistent-chat-server.md)所述。</span><span class="sxs-lookup"><span data-stu-id="8feba-129">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="8feba-130">多服务器拓扑可以包含多达四个运行持久聊天服务器的活动计算机 (高可用性和灾难恢复配置最多允许8个，但只有四个活动可以处于活动状态，并且在待机) 的其余四个。</span><span class="sxs-lookup"><span data-stu-id="8feba-130">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="8feba-131">每个服务器最多可以支持多达20000个并发用户，共80000个并发用户连接到具有4台服务器的持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="8feba-131">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="8feba-132">多服务器拓扑与单服务器拓扑相同，不同之处在于多个服务器承载持久聊天服务器，并且可以扩展到更高级别。</span><span class="sxs-lookup"><span data-stu-id="8feba-132">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="8feba-133">运行持久聊天服务器的多台计算机应驻留在与 Lync Server 和合规性服务相同的 Active Directory 域服务域中。</span><span class="sxs-lookup"><span data-stu-id="8feba-133">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="8feba-134">下图显示了多个服务器拓扑的所有组件，其中包含多个运行持久聊天服务器、可选合规性服务和独立合规性数据库的计算机。</span><span class="sxs-lookup"><span data-stu-id="8feba-134">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="8feba-135">**多个持久聊天服务器**</span><span class="sxs-lookup"><span data-stu-id="8feba-135">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="8feba-136">![多服务器拓扑](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "多服务器拓扑")</span><span class="sxs-lookup"><span data-stu-id="8feba-136">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="8feba-137">在四个服务器的持久聊天服务器部署中，其中80000个用户可以同时登录并使用持久聊天，每个服务器在20000个用户之间平均分布负载。</span><span class="sxs-lookup"><span data-stu-id="8feba-137">In a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to and using Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="8feba-138">如果一台服务器变得不可用，则连接到该服务器的用户将失去其对持久聊天服务器的访问权限。</span><span class="sxs-lookup"><span data-stu-id="8feba-138">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="8feba-139">断开连接的用户将自动转接到其余的服务器，直到该不可用的服务器恢复使用。</span><span class="sxs-lookup"><span data-stu-id="8feba-139">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> <span data-ttu-id="8feba-140">此传输可能需要几分钟或更长时间，具体取决于网络上的持久聊天流量量。</span><span class="sxs-lookup"><span data-stu-id="8feba-140">Depending on the amount of Persistent Chat traffic on the network, this transfer can take a few minutes or longer.</span></span> <span data-ttu-id="8feba-141">由于剩余的每个服务器都可能承载多达30000个用户，因此我们建议您尽可能快地还原不可用服务器以避免性能问题。</span><span class="sxs-lookup"><span data-stu-id="8feba-141">Because each of the remaining servers might be hosting as many as 30,000 users, we recommend that you restore the unavailable server as quickly as possible to avoid performance issues.</span></span> <span data-ttu-id="8feba-142">否则，可以使用拓扑生成器或 Windows PowerShell cmdlet，将另一个持久聊天服务器设为可用， **set-cspersistentchatactiveserver**。</span><span class="sxs-lookup"><span data-stu-id="8feba-142">Otherwise, you can make another Persistent Chat Server available by using the Topology Builder or the Windows PowerShell cmdlet, **set-CsPersistentChatActiveServer**.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a><span data-ttu-id="8feba-143">持久聊天服务器容量规划</span><span class="sxs-lookup"><span data-stu-id="8feba-143">Persistent Chat Server Capacity Planning</span></span>

<span data-ttu-id="8feba-144">下表可帮助您对持久聊天服务器进行容量规划。</span><span class="sxs-lookup"><span data-stu-id="8feba-144">The following tables can help you with capacity planning for Persistent Chat Server.</span></span> <span data-ttu-id="8feba-145">它们对更改各种持久聊天服务器设置有何影响容量功能进行了建模。</span><span class="sxs-lookup"><span data-stu-id="8feba-145">They model how changing various Persistent Chat Server settings affect capacity capabilities.</span></span>

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a><span data-ttu-id="8feba-146">规划持久聊天服务器的最大容量</span><span class="sxs-lookup"><span data-stu-id="8feba-146">Planning Your Maximum Capacity for Persistent Chat Server</span></span>

<span data-ttu-id="8feba-147">使用下面的示例表决定可以支持的用户数。</span><span class="sxs-lookup"><span data-stu-id="8feba-147">Use the following sample table to determine the number of users you will be able to support.</span></span>

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a><span data-ttu-id="8feba-148">持久聊天服务器池最大容量示例</span><span class="sxs-lookup"><span data-stu-id="8feba-148">Persistent Chat Server pool Maximum Capacity Sample</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8feba-149">活动的持久聊天服务实例</span><span class="sxs-lookup"><span data-stu-id="8feba-149">Active Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="8feba-150"><em>4</em></span><span class="sxs-lookup"><span data-stu-id="8feba-150"><em>4</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-151">持久聊天服务实例</span><span class="sxs-lookup"><span data-stu-id="8feba-151">Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="8feba-152"><em>8 (4 必须为非活动状态;最多只能有4个活动) </em></span><span class="sxs-lookup"><span data-stu-id="8feba-152"><em>8 (4 must be inactive; only a maximum of 4 can be active)</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-153">连接的活动用户</span><span class="sxs-lookup"><span data-stu-id="8feba-153">Active users connected</span></span></p></td>
<td><p><span data-ttu-id="8feba-154"><em>80000</em></span><span class="sxs-lookup"><span data-stu-id="8feba-154"><em>80,000</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-155">设置的用户总数</span><span class="sxs-lookup"><span data-stu-id="8feba-155">Total provisioned users</span></span></p></td>
<td><p><span data-ttu-id="8feba-156">150000</span><span class="sxs-lookup"><span data-stu-id="8feba-156">150,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-157">终结点的数目</span><span class="sxs-lookup"><span data-stu-id="8feba-157">Number of endpoints</span></span></p></td>
<td><p><span data-ttu-id="8feba-158">120000</span><span class="sxs-lookup"><span data-stu-id="8feba-158">120,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8feba-159">在上面的示例中，计划支持持久聊天服务器允许的最大用户数：持久聊天服务 (的四个服务器/实例可以有四个以上的被动服务器，它们为高可用性和灾难) 恢复提供了四个更多的被动服务器，每个服务器包含20000个用户，总共是80000个活动用户。</span><span class="sxs-lookup"><span data-stu-id="8feba-159">In the preceding sample, the plan is to support the maximum number of users that Persistent Chat Server allows: four servers/instances of the Persistent Chat service (can have four more passive servers running Persistent Chat Server for high availability and disaster recovery) and 20,000 users per server, for a total of 80,000 active users.</span></span>

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a><span data-ttu-id="8feba-160">管理持久聊天室访问的容量规划</span><span class="sxs-lookup"><span data-stu-id="8feba-160">Capacity Planning for Managing Persistent Chat Room Access</span></span>

<span data-ttu-id="8feba-161">下面的示例表可帮助您规划如何在持久聊天服务器池中管理持久聊天室访问。</span><span class="sxs-lookup"><span data-stu-id="8feba-161">The following sample table can help you plan for managing Persistent Chat room access in a Persistent Chat Server pool.</span></span>

### <a name="managing-chat-room-access-sample"></a><span data-ttu-id="8feba-162">管理聊天室访问示例</span><span class="sxs-lookup"><span data-stu-id="8feba-162">Managing Chat Room Access Sample</span></span>

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
<th><span data-ttu-id="8feba-163">小聊天室</span><span class="sxs-lookup"><span data-stu-id="8feba-163">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="8feba-164">中型聊天室</span><span class="sxs-lookup"><span data-stu-id="8feba-164">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="8feba-165">大型聊天室</span><span class="sxs-lookup"><span data-stu-id="8feba-165">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="8feba-166">总计</span><span class="sxs-lookup"><span data-stu-id="8feba-166">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8feba-167">聊天室的大小 (连接的用户数) </span><span class="sxs-lookup"><span data-stu-id="8feba-167">Size of chat rooms (number of users connected)</span></span></p></td>
<td><p><span data-ttu-id="8feba-168">每个会议室30个</span><span class="sxs-lookup"><span data-stu-id="8feba-168">30 per room</span></span></p></td>
<td><p><span data-ttu-id="8feba-169">每个会议室150</span><span class="sxs-lookup"><span data-stu-id="8feba-169">150 per room</span></span></p></td>
<td><p><span data-ttu-id="8feba-170">每个会议室16000</span><span class="sxs-lookup"><span data-stu-id="8feba-170">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-171">聊天室</span><span class="sxs-lookup"><span data-stu-id="8feba-171">Chat rooms</span></span></p></td>
<td><p><span data-ttu-id="8feba-172">32000</span><span class="sxs-lookup"><span data-stu-id="8feba-172">32,000</span></span></p></td>
<td><p><span data-ttu-id="8feba-173">1067</span><span class="sxs-lookup"><span data-stu-id="8feba-173">1,067</span></span></p></td>
<td><p><span data-ttu-id="8feba-174">10  </span><span class="sxs-lookup"><span data-stu-id="8feba-174">10</span></span></p></td>
<td><p><span data-ttu-id="8feba-175">33077</span><span class="sxs-lookup"><span data-stu-id="8feba-175">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-176">大会堂的会议室百分比</span><span class="sxs-lookup"><span data-stu-id="8feba-176">% of rooms that are auditorium</span></span></p></td>
<td><p><span data-ttu-id="8feba-177">1</span><span class="sxs-lookup"><span data-stu-id="8feba-177">1%</span></span></p></td>
<td><p><span data-ttu-id="8feba-178">1</span><span class="sxs-lookup"><span data-stu-id="8feba-178">1%</span></span></p></td>
<td><p><span data-ttu-id="8feba-179">50%</span><span class="sxs-lookup"><span data-stu-id="8feba-179">50%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-180">打开的会议室的百分比</span><span class="sxs-lookup"><span data-stu-id="8feba-180">% of rooms that are open</span></span></p></td>
<td><p><span data-ttu-id="8feba-181">第三章</span><span class="sxs-lookup"><span data-stu-id="8feba-181">3%</span></span></p></td>
<td><p><span data-ttu-id="8feba-182">第三章</span><span class="sxs-lookup"><span data-stu-id="8feba-182">3%</span></span></p></td>
<td><p><span data-ttu-id="8feba-183">50%</span><span class="sxs-lookup"><span data-stu-id="8feba-183">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-184">打开会议室 (无显式成员资格) </span><span class="sxs-lookup"><span data-stu-id="8feba-184">Open rooms (no explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="8feba-185">960</span><span class="sxs-lookup"><span data-stu-id="8feba-185">960</span></span></p></td>
<td><p><span data-ttu-id="8feba-186">32</span><span class="sxs-lookup"><span data-stu-id="8feba-186">32</span></span></p></td>
<td><p><span data-ttu-id="8feba-187">5 </span><span class="sxs-lookup"><span data-stu-id="8feba-187">5</span></span></p></td>
<td><p><span data-ttu-id="8feba-188">997</span><span class="sxs-lookup"><span data-stu-id="8feba-188">997</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-189">未打开的聊天室 (带有显式成员资格的常规聊天室) </span><span class="sxs-lookup"><span data-stu-id="8feba-189">Non-open rooms (regular rooms with explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="8feba-190">31040</span><span class="sxs-lookup"><span data-stu-id="8feba-190">31,040</span></span></p></td>
<td><p><span data-ttu-id="8feba-191">1.035</span><span class="sxs-lookup"><span data-stu-id="8feba-191">1.035</span></span></p></td>
<td><p><span data-ttu-id="8feba-192">5 </span><span class="sxs-lookup"><span data-stu-id="8feba-192">5</span></span></p></td>
<td><p><span data-ttu-id="8feba-193">32080</span><span class="sxs-lookup"><span data-stu-id="8feba-193">32,080</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-194">大会堂会议室 (其他演示者条目) </span><span class="sxs-lookup"><span data-stu-id="8feba-194">Auditorium rooms (additional presenters entry)</span></span></p></td>
<td><p><span data-ttu-id="8feba-195">0</span><span class="sxs-lookup"><span data-stu-id="8feba-195">0</span></span></p></td>
<td><p><span data-ttu-id="8feba-196">32</span><span class="sxs-lookup"><span data-stu-id="8feba-196">32</span></span></p></td>
<td><p><span data-ttu-id="8feba-197">5 </span><span class="sxs-lookup"><span data-stu-id="8feba-197">5</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-198">通过直接成员管理的聊天室</span><span class="sxs-lookup"><span data-stu-id="8feba-198">Rooms managed by direct membership</span></span></p></td>
<td><p><span data-ttu-id="8feba-199">50%</span><span class="sxs-lookup"><span data-stu-id="8feba-199">50%</span></span></p></td>
<td><p><span data-ttu-id="8feba-200">10</span><span class="sxs-lookup"><span data-stu-id="8feba-200">10%</span></span></p></td>
<td><p><span data-ttu-id="8feba-201">0%</span><span class="sxs-lookup"><span data-stu-id="8feba-201">0%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-202">用户组管理的聊天室比率</span><span class="sxs-lookup"><span data-stu-id="8feba-202">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="8feba-203">50%</span><span class="sxs-lookup"><span data-stu-id="8feba-203">50%</span></span></p></td>
<td><p><span data-ttu-id="8feba-204">90%</span><span class="sxs-lookup"><span data-stu-id="8feba-204">90%</span></span></p></td>
<td><p><span data-ttu-id="8feba-205">100%</span><span class="sxs-lookup"><span data-stu-id="8feba-205">100%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-206">打开聊天室的每个聊天室的成员资格列表中的用户组 (未明确指定) </span><span class="sxs-lookup"><span data-stu-id="8feba-206">User groups in each chat room's membership list for open rooms (not specified explicitly)</span></span></p></td>
<td><p><span data-ttu-id="8feba-207">0</span><span class="sxs-lookup"><span data-stu-id="8feba-207">0</span></span></p></td>
<td><p><span data-ttu-id="8feba-208">0</span><span class="sxs-lookup"><span data-stu-id="8feba-208">0</span></span></p></td>
<td><p><span data-ttu-id="8feba-209">0</span><span class="sxs-lookup"><span data-stu-id="8feba-209">0</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-210">非打开聊天室的每个聊天室的成员资格列表中的用户</span><span class="sxs-lookup"><span data-stu-id="8feba-210">Users in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="8feba-211">30</span><span class="sxs-lookup"><span data-stu-id="8feba-211">30</span></span></p></td>
<td><p><span data-ttu-id="8feba-212">150</span><span class="sxs-lookup"><span data-stu-id="8feba-212">150</span></span></p></td>
<td><p><span data-ttu-id="8feba-213">16000</span><span class="sxs-lookup"><span data-stu-id="8feba-213">16,000</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-214">非打开聊天室的每个聊天室的成员资格列表中的用户组</span><span class="sxs-lookup"><span data-stu-id="8feba-214">User groups in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="8feba-215">第三章</span><span class="sxs-lookup"><span data-stu-id="8feba-215">3</span></span></p></td>
<td><p><span data-ttu-id="8feba-216">5 </span><span class="sxs-lookup"><span data-stu-id="8feba-216">5</span></span></p></td>
<td><p><span data-ttu-id="8feba-217">10  </span><span class="sxs-lookup"><span data-stu-id="8feba-217">10</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-218">每个聊天室的管理器列表中的用户和用户组 (开放和非打开的会议室) </span><span class="sxs-lookup"><span data-stu-id="8feba-218">Users and user groups in each chat room's manager list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="8feba-219">6 </span><span class="sxs-lookup"><span data-stu-id="8feba-219">6</span></span></p></td>
<td><p><span data-ttu-id="8feba-220">6 </span><span class="sxs-lookup"><span data-stu-id="8feba-220">6</span></span></p></td>
<td><p><span data-ttu-id="8feba-221">6 </span><span class="sxs-lookup"><span data-stu-id="8feba-221">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-222">每个大会堂聊天室的演示者列表中的用户和用户组打开和未打开的会议室 () </span><span class="sxs-lookup"><span data-stu-id="8feba-222">Users and user groups in each auditorium chat room's presenters list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="8feba-223">6 </span><span class="sxs-lookup"><span data-stu-id="8feba-223">6</span></span></p></td>
<td><p><span data-ttu-id="8feba-224">6 </span><span class="sxs-lookup"><span data-stu-id="8feba-224">6</span></span></p></td>
<td><p><span data-ttu-id="8feba-225">6 </span><span class="sxs-lookup"><span data-stu-id="8feba-225">6</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-226">跨所有非开放聊天室的基于用户的成员资格实体</span><span class="sxs-lookup"><span data-stu-id="8feba-226">User-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="8feba-227">465600</span><span class="sxs-lookup"><span data-stu-id="8feba-227">465,600</span></span></p></td>
<td><p><span data-ttu-id="8feba-228">15520</span><span class="sxs-lookup"><span data-stu-id="8feba-228">15,520</span></span></p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-229">跨所有非开放聊天室的基于用户组的成员实体</span><span class="sxs-lookup"><span data-stu-id="8feba-229">User-group-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="8feba-230">46560</span><span class="sxs-lookup"><span data-stu-id="8feba-230">46,560</span></span></p></td>
<td><p><span data-ttu-id="8feba-231">4656</span><span class="sxs-lookup"><span data-stu-id="8feba-231">4656</span></span></p></td>
<td><p><span data-ttu-id="8feba-232">50</span><span class="sxs-lookup"><span data-stu-id="8feba-232">50</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-233">跨所有大会堂聊天室的基于用户和用户组的实体</span><span class="sxs-lookup"><span data-stu-id="8feba-233">Users and user groups based entities across all auditorium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="8feba-234">0</span><span class="sxs-lookup"><span data-stu-id="8feba-234">0</span></span></p></td>
<td><p><span data-ttu-id="8feba-235">192</span><span class="sxs-lookup"><span data-stu-id="8feba-235">192</span></span></p></td>
<td><p><span data-ttu-id="8feba-236">50</span><span class="sxs-lookup"><span data-stu-id="8feba-236">50</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-237">跨所有聊天室管理器列表的基于用户和用户组的管理器实体</span><span class="sxs-lookup"><span data-stu-id="8feba-237">Users and user groups based manager entities across all chat rooms manager lists</span></span></p></td>
<td><p><span data-ttu-id="8feba-238">192000</span><span class="sxs-lookup"><span data-stu-id="8feba-238">192,000</span></span></p></td>
<td><p><span data-ttu-id="8feba-239">6400</span><span class="sxs-lookup"><span data-stu-id="8feba-239">6,400</span></span></p></td>
<td><p><span data-ttu-id="8feba-240">60</span><span class="sxs-lookup"><span data-stu-id="8feba-240">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-241">每个聊天室的活动用户数</span><span class="sxs-lookup"><span data-stu-id="8feba-241">Active users per chat room</span></span></p></td>
<td><p><span data-ttu-id="8feba-242"><em>30</em></span><span class="sxs-lookup"><span data-stu-id="8feba-242"><em>30</em></span></span></p></td>
<td><p><span data-ttu-id="8feba-243"><em>150</em></span><span class="sxs-lookup"><span data-stu-id="8feba-243"><em>150</em></span></span></p></td>
<td><p><span data-ttu-id="8feba-244"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="8feba-244"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-245">每个用户的聊天室数量</span><span class="sxs-lookup"><span data-stu-id="8feba-245">Chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="8feba-246"><em>12</em></span><span class="sxs-lookup"><span data-stu-id="8feba-246"><em>12</em></span></span></p></td>
<td><p><span data-ttu-id="8feba-247"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="8feba-247"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="8feba-248"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="8feba-248"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="8feba-249"><em>位</em></span><span class="sxs-lookup"><span data-stu-id="8feba-249"><em>16</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-250">每个聊天室成员列表中用户组的数量</span><span class="sxs-lookup"><span data-stu-id="8feba-250">User groups in each chat room’s membership list</span></span></p></td>
<td><p><span data-ttu-id="8feba-251"><em>10</em></span><span class="sxs-lookup"><span data-stu-id="8feba-251"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="8feba-252"><em>10</em></span><span class="sxs-lookup"><span data-stu-id="8feba-252"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="8feba-253"><em>个</em></span><span class="sxs-lookup"><span data-stu-id="8feba-253"><em>15</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-254">用户组管理的聊天室比率</span><span class="sxs-lookup"><span data-stu-id="8feba-254">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="8feba-255"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="8feba-255"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="8feba-256"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="8feba-256"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="8feba-257"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="8feba-257"><em>50%</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-258">所有聊天室中基于用户组的成员实体数量</span><span class="sxs-lookup"><span data-stu-id="8feba-258">User-group-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="8feba-259">155200</span><span class="sxs-lookup"><span data-stu-id="8feba-259">155,200</span></span></p></td>
<td><p><span data-ttu-id="8feba-260">5173</span><span class="sxs-lookup"><span data-stu-id="8feba-260">5173</span></span></p></td>
<td><p><span data-ttu-id="8feba-261">68</span><span class="sxs-lookup"><span data-stu-id="8feba-261">68</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-262">所有聊天室中基于用户的成员实体数量</span><span class="sxs-lookup"><span data-stu-id="8feba-262">User-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="8feba-263">465600</span><span class="sxs-lookup"><span data-stu-id="8feba-263">465,600</span></span></p></td>
<td><p><span data-ttu-id="8feba-264">77600</span><span class="sxs-lookup"><span data-stu-id="8feba-264">77,600</span></span></p></td>
<td><p><span data-ttu-id="8feba-265">72000</span><span class="sxs-lookup"><span data-stu-id="8feba-265">72,000</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-266">每个聊天室的管理者、演示者和范围列表中的用户和用户组数量</span><span class="sxs-lookup"><span data-stu-id="8feba-266">Users and user groups in each chat room's manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="8feba-267">6 </span><span class="sxs-lookup"><span data-stu-id="8feba-267">6</span></span></p></td>
<td><p><span data-ttu-id="8feba-268">6 </span><span class="sxs-lookup"><span data-stu-id="8feba-268">6</span></span></p></td>
<td><p><span data-ttu-id="8feba-269">6 </span><span class="sxs-lookup"><span data-stu-id="8feba-269">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-270">跨聊天室的管理者、演示者和范围列表中的用户和用户组</span><span class="sxs-lookup"><span data-stu-id="8feba-270">Users and user groups across all chat rooms' manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="8feba-271">192000</span><span class="sxs-lookup"><span data-stu-id="8feba-271">192,000</span></span></p></td>
<td><p><span data-ttu-id="8feba-272">6400</span><span class="sxs-lookup"><span data-stu-id="8feba-272">6400</span></span></p></td>
<td><p><span data-ttu-id="8feba-273">60</span><span class="sxs-lookup"><span data-stu-id="8feba-273">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-274">访问控制项数量</span><span class="sxs-lookup"><span data-stu-id="8feba-274">Access control entries</span></span></p></td>
<td><p><span data-ttu-id="8feba-275">704160</span><span class="sxs-lookup"><span data-stu-id="8feba-275">704,160</span></span></p></td>
<td><p><span data-ttu-id="8feba-276">26768</span><span class="sxs-lookup"><span data-stu-id="8feba-276">26,768</span></span></p></td>
<td><p><span data-ttu-id="8feba-277">160</span><span class="sxs-lookup"><span data-stu-id="8feba-277">160</span></span></p></td>
<td><p><span data-ttu-id="8feba-278">731088</span><span class="sxs-lookup"><span data-stu-id="8feba-278">731,088</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-279">最大访问控制项数量</span><span class="sxs-lookup"><span data-stu-id="8feba-279">Maximum access control entries</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="8feba-280">2000000</span><span class="sxs-lookup"><span data-stu-id="8feba-280">2,000,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8feba-281">在上面的示例中，当您根据建议的准则部署持久聊天服务器时，他们可以跨启用了合规性的四个服务器池处理最多80000个活动用户。</span><span class="sxs-lookup"><span data-stu-id="8feba-281">In the preceding sample, when you deploy the Persistent Chat Servers according to the recommended guidelines, they can handle up to 80,000 active users across a four-server pool with compliance enabled.</span></span>

<span data-ttu-id="8feba-282">本示例显示了在任意给定时间) 、中型 (150 活动用户) 和大型 (16000 活跃用户) 中分类为 (30 个活动用户的聊天工作室。</span><span class="sxs-lookup"><span data-stu-id="8feba-282">This sample shows chat rooms categorized as small (30 active users at any given time), medium (150 active users), and large (16,000 active users).</span></span> <span data-ttu-id="8feba-283">根据以下总数计算特定大小的聊天室数量：</span><span class="sxs-lookup"><span data-stu-id="8feba-283">The number of chat rooms of a certain size is computed based on the total number of:</span></span>

  - <span data-ttu-id="8feba-284">系统中的活动用户数量</span><span class="sxs-lookup"><span data-stu-id="8feba-284">Active users in the system</span></span>

  - <span data-ttu-id="8feba-285">给定大小的聊天室中的活动用户数量</span><span class="sxs-lookup"><span data-stu-id="8feba-285">Active users in chat rooms of the given size</span></span>

  - <span data-ttu-id="8feba-286">单个用户加入的给定大小的聊天室数量</span><span class="sxs-lookup"><span data-stu-id="8feba-286">Chat rooms of the given size that a single user joins</span></span>

<span data-ttu-id="8feba-287">对于每个聊天室，上述容量规划表指定与聊天室相关联的访问控制条目数，包括直接分配到聊天室的条目。</span><span class="sxs-lookup"><span data-stu-id="8feba-287">For each chat room, the preceding capacity planning table specifies the number of access control entries that are associated with the chat room, including entries that are assigned directly to the chat room.</span></span> <span data-ttu-id="8feba-288">您可以通过使用访问控制列表 (Acl) 来控制对各个聊天室的访问。</span><span class="sxs-lookup"><span data-stu-id="8feba-288">You can control access to individual chat rooms by using access control lists (ACLs).</span></span> <span data-ttu-id="8feba-289">您还可以在类别级别控制访问权限。</span><span class="sxs-lookup"><span data-stu-id="8feba-289">You can also control access at the category level.</span></span> <span data-ttu-id="8feba-290">在 ACL 中，单个访问控制项可以是用户组（例如，安全组、通讯组列表或单个用户）。</span><span class="sxs-lookup"><span data-stu-id="8feba-290">In an ACL, an individual access control entry can be either a user group—for example, a security group, a distribution list, or a single user.</span></span> <span data-ttu-id="8feba-291">您可以为聊天室管理者、演示者和成员定义访问控制条目。</span><span class="sxs-lookup"><span data-stu-id="8feba-291">You can define access control entries for chat room managers, presenters, and members.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8feba-292">在规划管理聊天室的策略时，请记住允许的访问控制条目总数为2000000。</span><span class="sxs-lookup"><span data-stu-id="8feba-292">In planning your strategy for managing chat rooms, keep in mind that the total number of allowed access control entries is 2 million.</span></span> <span data-ttu-id="8feba-293">如果计算出的访问控制条目超过2000000，服务器性能可能会显著降低。</span><span class="sxs-lookup"><span data-stu-id="8feba-293">If the calculated access control entries exceed 2 million, server performance could degrade significantly.</span></span> <span data-ttu-id="8feba-294">若要避免此问题，请尽可能确保您的访问控制项是用户组而不是单个用户。</span><span class="sxs-lookup"><span data-stu-id="8feba-294">To avoid this issue, whenever possible, be sure that your access control entries are user groups instead of individual users.</span></span>



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a><span data-ttu-id="8feba-295">管理邀请的聊天室访问的容量规划</span><span class="sxs-lookup"><span data-stu-id="8feba-295">Capacity Planning for Managing Chat Room Access by Invitation</span></span>

<span data-ttu-id="8feba-296">您可以使用以下容量规划表来了解持久聊天服务器在配置为发送邀请时在持久聊天数据库中创建和存储的邀请数。</span><span class="sxs-lookup"><span data-stu-id="8feba-296">You can use the following capacity planning table to understand the number of invitations that Persistent Chat Server creates and stores in the Persistent Chat database when it is configured to send invitations.</span></span> <span data-ttu-id="8feba-297">您可以使用 Lync Server 控制面板中的 " **聊天室类别设置** " 页或使用 Windows PowerShell Cmdlet 管理类别上的邀请。 **csPersistentChatCategory**。</span><span class="sxs-lookup"><span data-stu-id="8feba-297">You manage invitations on the Category by using the **Chat Room Category settings** page in the Lync Server Control Panel, or by using the Windows PowerShell cmdlet, **set-csPersistentChatCategory**.</span></span> <span data-ttu-id="8feba-298">您可以通过使用从 Lync 客户端启动的 " **会议室管理** " 页或使用 Windows PowerShell cmdlet **set-cspersistentchatroom**在 (聊天室上管理邀请，具体取决于该类别允许的) 。</span><span class="sxs-lookup"><span data-stu-id="8feba-298">You can manage invitations on a chat room (in line with what the category allows) by using the **Room Management** page launched from the Lync client, or by using a Windows PowerShell cmdlet, **set-csPersistentChatRoom**.</span></span>

<span data-ttu-id="8feba-299">下表中的示例数据假定，在所有聊天室的50% 的 **聊天室设置** 页上，" **邀请** " 选项设置为 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="8feba-299">The sample data in the following table assumes that, on the **Chat room settings** page for 50 percent of all chat rooms, the **Invitations** option is set to **Yes**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8feba-300">如果服务器生成的邀请数的计算值超过1000000，服务器性能可能会显著降低。</span><span class="sxs-lookup"><span data-stu-id="8feba-300">If the calculated value for the number of invitations that is generated by the server exceeds 1 million, server performance could degrade significantly.</span></span> <span data-ttu-id="8feba-301">若要避免此问题，请确保将配置为发送邀请的聊天室的数量减至，或限制可加入聊天室的用户数，这些聊天室已配置为发送邀请。</span><span class="sxs-lookup"><span data-stu-id="8feba-301">To avoid this issue, be sure that you minimize the number of chat rooms that are configured to send invitations or restrict the number of users who can join chat rooms that have been configured to send invitations.</span></span>



</div>

### <a name="chat-room-access-by-invitation-sample"></a><span data-ttu-id="8feba-302">邀请的聊天室访问示例</span><span class="sxs-lookup"><span data-stu-id="8feba-302">Chat Room Access by Invitation Sample</span></span>

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
<th><span data-ttu-id="8feba-303">小聊天室</span><span class="sxs-lookup"><span data-stu-id="8feba-303">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="8feba-304">中型聊天室</span><span class="sxs-lookup"><span data-stu-id="8feba-304">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="8feba-305">大型聊天室</span><span class="sxs-lookup"><span data-stu-id="8feba-305">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="8feba-306">总计</span><span class="sxs-lookup"><span data-stu-id="8feba-306">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8feba-307">可以访问聊天室的用户</span><span class="sxs-lookup"><span data-stu-id="8feba-307">Users who can access chat room</span></span></p></td>
<td><p><span data-ttu-id="8feba-308">每个会议室30个</span><span class="sxs-lookup"><span data-stu-id="8feba-308">30 per room</span></span></p></td>
<td><p><span data-ttu-id="8feba-309">每个会议室150</span><span class="sxs-lookup"><span data-stu-id="8feba-309">150 per room</span></span></p></td>
<td><p><span data-ttu-id="8feba-310">每个会议室16000</span><span class="sxs-lookup"><span data-stu-id="8feba-310">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-311">具有邀请的聊天室的百分比</span><span class="sxs-lookup"><span data-stu-id="8feba-311">Percentage of rooms that have invitations</span></span></p></td>
<td><p><span data-ttu-id="8feba-312">50%</span><span class="sxs-lookup"><span data-stu-id="8feba-312">50%</span></span></p></td>
<td><p><span data-ttu-id="8feba-313">50%</span><span class="sxs-lookup"><span data-stu-id="8feba-313">50%</span></span></p></td>
<td><p><span data-ttu-id="8feba-314">50%</span><span class="sxs-lookup"><span data-stu-id="8feba-314">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-315">配置为发送邀请的聊天室数量</span><span class="sxs-lookup"><span data-stu-id="8feba-315">Chat rooms configured to send invitations</span></span></p></td>
<td><p><span data-ttu-id="8feba-316"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="8feba-316"><em>16,000</em></span></span></p></td>
<td><p><span data-ttu-id="8feba-317"><em>533</em></span><span class="sxs-lookup"><span data-stu-id="8feba-317"><em>533</em></span></span></p></td>
<td><p><span data-ttu-id="8feba-318"><em>5</em></span><span class="sxs-lookup"><span data-stu-id="8feba-318"><em>5</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-319">可以访问聊天室的用户数</span><span class="sxs-lookup"><span data-stu-id="8feba-319">Users who can access the chat room</span></span></p></td>
<td><p><span data-ttu-id="8feba-320"><em>60</em></span><span class="sxs-lookup"><span data-stu-id="8feba-320"><em>60</em></span></span></p></td>
<td><p><span data-ttu-id="8feba-321"><em>225</em></span><span class="sxs-lookup"><span data-stu-id="8feba-321"><em>225</em></span></span></p></td>
<td><p><span data-ttu-id="8feba-322"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="8feba-322"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-323">持久聊天服务器生成的邀请</span><span class="sxs-lookup"><span data-stu-id="8feba-323">Invitations generated by Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="8feba-324">960000</span><span class="sxs-lookup"><span data-stu-id="8feba-324">960,000</span></span></p></td>
<td><p><span data-ttu-id="8feba-325">120000</span><span class="sxs-lookup"><span data-stu-id="8feba-325">120,000</span></span></p></td>
<td><p><span data-ttu-id="8feba-326">80000</span><span class="sxs-lookup"><span data-stu-id="8feba-326">80,000</span></span></p></td>
<td><p><span data-ttu-id="8feba-327">1160000</span><span class="sxs-lookup"><span data-stu-id="8feba-327">1,160,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-328">允许的最大邀请数量</span><span class="sxs-lookup"><span data-stu-id="8feba-328">Maximum allowable number of invitations</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="8feba-329">2000000</span><span class="sxs-lookup"><span data-stu-id="8feba-329">2,000,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-330">模型 1-以预期的每天每个会议室的邮件数开头</span><span class="sxs-lookup"><span data-stu-id="8feba-330">Model 1 - Start with expected number of messages per room per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-331">每天 (每个会议室的聊天费率) </span><span class="sxs-lookup"><span data-stu-id="8feba-331">Chat Rate Per Room (per day)</span></span></p></td>
<td><p><span data-ttu-id="8feba-332">50</span><span class="sxs-lookup"><span data-stu-id="8feba-332">50</span></span></p></td>
<td><p><span data-ttu-id="8feba-333">500</span><span class="sxs-lookup"><span data-stu-id="8feba-333">500</span></span></p></td>
<td><p><span data-ttu-id="8feba-334">100</span><span class="sxs-lookup"><span data-stu-id="8feba-334">100</span></span></p></td>
<td><p><span data-ttu-id="8feba-335">650</span><span class="sxs-lookup"><span data-stu-id="8feba-335">650</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-336">所有聊天室每秒 (的聊天速率) </span><span class="sxs-lookup"><span data-stu-id="8feba-336">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="8feba-337">55.56</span><span class="sxs-lookup"><span data-stu-id="8feba-337">55.56</span></span></p></td>
<td><p><span data-ttu-id="8feba-338">18.52</span><span class="sxs-lookup"><span data-stu-id="8feba-338">18.52</span></span></p></td>
<td><p><span data-ttu-id="8feba-339">0.03</span><span class="sxs-lookup"><span data-stu-id="8feba-339">0.03</span></span></p></td>
<td><p><span data-ttu-id="8feba-340">74</span><span class="sxs-lookup"><span data-stu-id="8feba-340">74</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-341">模型 2-以每个用户每天发布的邮件数开头</span><span class="sxs-lookup"><span data-stu-id="8feba-341">Model 2 - Start with number of messages posted per user per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-342">每个用户每天的聊天速率</span><span class="sxs-lookup"><span data-stu-id="8feba-342">Chat rate per user per day</span></span></p></td>
<td><p><span data-ttu-id="8feba-343">15 </span><span class="sxs-lookup"><span data-stu-id="8feba-343">15</span></span></p></td>
<td><p><span data-ttu-id="8feba-344">5 </span><span class="sxs-lookup"><span data-stu-id="8feba-344">5</span></span></p></td>
<td><p><span data-ttu-id="8feba-345">0.1</span><span class="sxs-lookup"><span data-stu-id="8feba-345">0.1</span></span></p></td>
<td><p><span data-ttu-id="8feba-346">20</span><span class="sxs-lookup"><span data-stu-id="8feba-346">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-347">每天 (每个会议室的聊天费率) </span><span class="sxs-lookup"><span data-stu-id="8feba-347">Chat rate per room (per day)</span></span></p></td>
<td><p><span data-ttu-id="8feba-348">38</span><span class="sxs-lookup"><span data-stu-id="8feba-348">38</span></span></p></td>
<td><p><span data-ttu-id="8feba-349">375</span><span class="sxs-lookup"><span data-stu-id="8feba-349">375</span></span></p></td>
<td><p><span data-ttu-id="8feba-350">800</span><span class="sxs-lookup"><span data-stu-id="8feba-350">800</span></span></p></td>
<td><p><span data-ttu-id="8feba-351">1213</span><span class="sxs-lookup"><span data-stu-id="8feba-351">1,213</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-352">所有聊天室每秒 (的聊天速率) </span><span class="sxs-lookup"><span data-stu-id="8feba-352">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="8feba-353">41.67</span><span class="sxs-lookup"><span data-stu-id="8feba-353">41.67</span></span></p></td>
<td><p><span data-ttu-id="8feba-354">13.89</span><span class="sxs-lookup"><span data-stu-id="8feba-354">13.89</span></span></p></td>
<td><p><span data-ttu-id="8feba-355">0.28</span><span class="sxs-lookup"><span data-stu-id="8feba-355">0.28</span></span></p></td>
<td><p><span data-ttu-id="8feba-356">56</span><span class="sxs-lookup"><span data-stu-id="8feba-356">56</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="8feba-357">持久聊天服务器性能用户模型</span><span class="sxs-lookup"><span data-stu-id="8feba-357">Persistent Chat Server Performance User Model</span></span>

<span data-ttu-id="8feba-358">下表介绍持久聊天服务器的用户模型。</span><span class="sxs-lookup"><span data-stu-id="8feba-358">The following table describes the user model for Persistent Chat Server.</span></span> <span data-ttu-id="8feba-359">它提供了容量规划要求的基础，并表示在四台服务器上有80000个并发用户的典型组织。</span><span class="sxs-lookup"><span data-stu-id="8feba-359">It provides the basis for the capacity planning requirements and represents a typical organization with 80,000 concurrent users on four servers.</span></span>

### <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="8feba-360">持久聊天服务器性能用户模型</span><span class="sxs-lookup"><span data-stu-id="8feba-360">Persistent Chat Server Performance User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8feba-361">连接的活动用户数</span><span class="sxs-lookup"><span data-stu-id="8feba-361">Number of active users connected</span></span></p></td>
<td><p><span data-ttu-id="8feba-362">80000</span><span class="sxs-lookup"><span data-stu-id="8feba-362">80,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-363">持久聊天服务器服务实例的数量</span><span class="sxs-lookup"><span data-stu-id="8feba-363">Number of Persistent Chat Server service instances</span></span></p></td>
<td><p><span data-ttu-id="8feba-364">4 </span><span class="sxs-lookup"><span data-stu-id="8feba-364">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-365">小聊天室的大小</span><span class="sxs-lookup"><span data-stu-id="8feba-365">Size of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="8feba-366">30 个用户</span><span class="sxs-lookup"><span data-stu-id="8feba-366">30 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-367">中聊天室的大小</span><span class="sxs-lookup"><span data-stu-id="8feba-367">Size of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="8feba-368">150 个用户</span><span class="sxs-lookup"><span data-stu-id="8feba-368">150 users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-369">大聊天室的大小</span><span class="sxs-lookup"><span data-stu-id="8feba-369">Size of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="8feba-370">16000用户</span><span class="sxs-lookup"><span data-stu-id="8feba-370">16,000 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-371">聊天室的总数</span><span class="sxs-lookup"><span data-stu-id="8feba-371">Total number of chat rooms</span></span></p></td>
<td><p><span data-ttu-id="8feba-372">33077</span><span class="sxs-lookup"><span data-stu-id="8feba-372">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-373">小聊天室的数量</span><span class="sxs-lookup"><span data-stu-id="8feba-373">Number of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="8feba-374">32000</span><span class="sxs-lookup"><span data-stu-id="8feba-374">32,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-375">中聊天室的数量</span><span class="sxs-lookup"><span data-stu-id="8feba-375">Number of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="8feba-376">1067</span><span class="sxs-lookup"><span data-stu-id="8feba-376">1,067</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-377">大聊天室的数量</span><span class="sxs-lookup"><span data-stu-id="8feba-377">Number of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="8feba-378">10  </span><span class="sxs-lookup"><span data-stu-id="8feba-378">10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-379">每个用户的聊天室总数</span><span class="sxs-lookup"><span data-stu-id="8feba-379">Total number of chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="8feba-380">16 </span><span class="sxs-lookup"><span data-stu-id="8feba-380">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-381">每个用户的小聊天室数量</span><span class="sxs-lookup"><span data-stu-id="8feba-381">Number of small chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="8feba-382">12 </span><span class="sxs-lookup"><span data-stu-id="8feba-382">12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-383">每个用户的中聊天室数量</span><span class="sxs-lookup"><span data-stu-id="8feba-383">Number of medium chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="8feba-384">双面</span><span class="sxs-lookup"><span data-stu-id="8feba-384">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-385">每个用户的大聊天室数量</span><span class="sxs-lookup"><span data-stu-id="8feba-385">Number of large chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="8feba-386">双面</span><span class="sxs-lookup"><span data-stu-id="8feba-386">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-387">每个用户加入的聊天室数</span><span class="sxs-lookup"><span data-stu-id="8feba-387">Number of rooms joined per user</span></span></p></td>
<td><p><span data-ttu-id="8feba-388">24</span><span class="sxs-lookup"><span data-stu-id="8feba-388">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-389">峰值加入速率</span><span class="sxs-lookup"><span data-stu-id="8feba-389">Peak join rate</span></span></p></td>
<td><p><span data-ttu-id="8feba-390">10/秒</span><span class="sxs-lookup"><span data-stu-id="8feba-390">10/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-391">总聊天速率</span><span class="sxs-lookup"><span data-stu-id="8feba-391">Total chat rate</span></span></p></td>
<td><p><span data-ttu-id="8feba-392">24/秒</span><span class="sxs-lookup"><span data-stu-id="8feba-392">24/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-393">小聊天室的聊天速率</span><span class="sxs-lookup"><span data-stu-id="8feba-393">Chat rate for small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="8feba-394">22.22/秒</span><span class="sxs-lookup"><span data-stu-id="8feba-394">22.22/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-395">中聊天室的聊天速率</span><span class="sxs-lookup"><span data-stu-id="8feba-395">Chat rate for medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="8feba-396">1.67/秒</span><span class="sxs-lookup"><span data-stu-id="8feba-396">1.67/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-397">大聊天室的聊天速率</span><span class="sxs-lookup"><span data-stu-id="8feba-397">Chat rate for large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="8feba-398">~ 0.15/秒</span><span class="sxs-lookup"><span data-stu-id="8feba-398">~0.15/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-399">为邀请配置的聊天室的百分比</span><span class="sxs-lookup"><span data-stu-id="8feba-399">Percentage of chat rooms configured for invitations</span></span></p></td>
<td><p><span data-ttu-id="8feba-400">50%</span><span class="sxs-lookup"><span data-stu-id="8feba-400">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-401">直接成员身份的百分比</span><span class="sxs-lookup"><span data-stu-id="8feba-401">Percentage of direct memberships</span></span></p></td>
<td><p><span data-ttu-id="8feba-402">50%</span><span class="sxs-lookup"><span data-stu-id="8feba-402">50%</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-403">组成员身份的百分比</span><span class="sxs-lookup"><span data-stu-id="8feba-403">Percentage of group memberships</span></span></p></td>
<td><p><span data-ttu-id="8feba-404">50%</span><span class="sxs-lookup"><span data-stu-id="8feba-404">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-405">Active Directory 域服务中的平均祖先隶属关系数</span><span class="sxs-lookup"><span data-stu-id="8feba-405">Average number of ancestor affiliations in Active Directory Domain Services</span></span></p></td>
<td><p><span data-ttu-id="8feba-406">100 - 200</span><span class="sxs-lookup"><span data-stu-id="8feba-406">100 - 200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-407">每个用户的订阅联系人数</span><span class="sxs-lookup"><span data-stu-id="8feba-407">Number of subscribed contacts per user</span></span></p></td>
<td><p><span data-ttu-id="8feba-408">80</span><span class="sxs-lookup"><span data-stu-id="8feba-408">80</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-409">每个用户的平均终结点数</span><span class="sxs-lookup"><span data-stu-id="8feba-409">Average number of endpoints per user</span></span></p></td>
<td><p><span data-ttu-id="8feba-410">1.5</span><span class="sxs-lookup"><span data-stu-id="8feba-410">1.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-411">每个终结点的平均可见聊天室数</span><span class="sxs-lookup"><span data-stu-id="8feba-411">Average number of visible chat rooms per endpoint</span></span></p></td>
<td><p><span data-ttu-id="8feba-412">1.5</span><span class="sxs-lookup"><span data-stu-id="8feba-412">1.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-413">每个用户的平均可见聊天室数</span><span class="sxs-lookup"><span data-stu-id="8feba-413">Average number of visible chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="8feba-414">2.25 (50%，共1个会议室，50% 为2个会议室) ;最多6个会议室打开，每个显示器一个</span><span class="sxs-lookup"><span data-stu-id="8feba-414">2.25 (50% for 1 room and 50% for 2 rooms); Up to 6 rooms open, one per monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-415">每个时间间隔轮询的参与者数量</span><span class="sxs-lookup"><span data-stu-id="8feba-415">Number of participants polled per interval</span></span></p></td>
<td><p><span data-ttu-id="8feba-416">每个可见聊天室25个</span><span class="sxs-lookup"><span data-stu-id="8feba-416">25 per visible chat room</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-417">轮询间隔时长</span><span class="sxs-lookup"><span data-stu-id="8feba-417">Length of polling interval</span></span></p></td>
<td><p><span data-ttu-id="8feba-418">5 分钟</span><span class="sxs-lookup"><span data-stu-id="8feba-418">5 minutes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-419">每秒钟轮询的参与者数量</span><span class="sxs-lookup"><span data-stu-id="8feba-419">Number of participants polled per second</span></span></p></td>
<td><p><span data-ttu-id="8feba-420">15,000</span><span class="sxs-lookup"><span data-stu-id="8feba-420">15,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8feba-421">每个用户每小时的状态更改数量</span><span class="sxs-lookup"><span data-stu-id="8feba-421">Number of presence changes per hour per user</span></span></p></td>
<td><p><span data-ttu-id="8feba-422">6 </span><span class="sxs-lookup"><span data-stu-id="8feba-422">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8feba-423">每秒钟的状态更改数量</span><span class="sxs-lookup"><span data-stu-id="8feba-423">Number of presence changes per second</span></span></p></td>
<td><p><span data-ttu-id="8feba-424">133.33</span><span class="sxs-lookup"><span data-stu-id="8feba-424">133.33</span></span></p></td>
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

