---
title: Lync Server 2013 拓扑更改
description: Lync Server 2013 拓扑更改。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topology changes
ms:assetid: 9e40ef93-9ab0-498c-9bbf-f94584353e53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688153(v=OCS.15)
ms:contentKeyID: 49733756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 562766eae939e4510a0d3af20e40b4731c361040
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549098"
---
# <a name="topology-changes-in-lync-server-2013"></a><span data-ttu-id="1b768-103">Lync Server 2013 中的拓扑更改</span><span class="sxs-lookup"><span data-stu-id="1b768-103">Topology changes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b768-104">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="1b768-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="1b768-105">Lync Server 2013 的拓扑要求和注意事项与早期版本的拓扑要求和注意事项不同，如本节中所述。</span><span class="sxs-lookup"><span data-stu-id="1b768-105">Topology requirements and considerations for Lync Server 2013 are different from those for earlier releases, as described in this section.</span></span>

<div>

## <a name="new-front-end-pools-architecture"></a><span data-ttu-id="1b768-106">新的前端池体系结构</span><span class="sxs-lookup"><span data-stu-id="1b768-106">New Front End Pools Architecture</span></span>

<span data-ttu-id="1b768-107">在 Lync Server 2013 中，企业版前端池的体系结构已更改为分布式系统体系结构。</span><span class="sxs-lookup"><span data-stu-id="1b768-107">In Lync Server 2013, the architecture of Enterprise Edition Front End pools has changed to a distributed systems architecture.</span></span>

<span data-ttu-id="1b768-p101">有了此新的体系结构，后端数据库不再是池中的实时数据存储。有关特定用户的信息将保存在池中的三个前端服务器中。对于每个用户，一个前端服务器充当用户信息的主存储，而另外两个前端服务器充当副存储。如果一个前端服务器不可用，则充当副存储的其他前端服务器将自动提升为主存储。</span><span class="sxs-lookup"><span data-stu-id="1b768-p101">With this new architecture, the Back End database is no longer the real-time data store in a pool. Information about a particular user is kept on three Front End Servers in the pool. For each user, one Front End Server acts as the master for that user’s information, and two other Front End Servers serve as replicas. If a Front End Server goes down, another Front End Server which served as a replica is automatically promoted to master.</span></span>

<span data-ttu-id="1b768-112">这将在后台进行，管理员不必知道哪些前端服务器是哪些用户的主存储。</span><span class="sxs-lookup"><span data-stu-id="1b768-112">This happens behind the scenes, and administrators do not need to know which Front End Servers are the masters for which users.</span></span> <span data-ttu-id="1b768-113">此数据存储的分布可提高池内的性能和可伸缩性，并消除单个后端服务器的单一故障点。</span><span class="sxs-lookup"><span data-stu-id="1b768-113">This distribution of data storage improves performance and scalability within the pool, and eliminates the single point of failure of a single Back End Server.</span></span>

<span data-ttu-id="1b768-114">后端服务器充当用户和会议数据的备份存储，并且还是其他数据库（如响应组数据库）的主存储。</span><span class="sxs-lookup"><span data-stu-id="1b768-114">The Back End Server serves as backup storage for user and conference data, and is also the primary storage for other databases such as the Response Group database.</span></span>

<span data-ttu-id="1b768-115">这些改进还意味着规划和维护池的方式有了变化。</span><span class="sxs-lookup"><span data-stu-id="1b768-115">These improvements also mean there are changes in how you plan and maintain your pools.</span></span> <span data-ttu-id="1b768-116">我们建议您的所有 Enterprise Edition 前端池至少包含三台前端服务器，以提供前端池体系结构设计的完整数量的副本。</span><span class="sxs-lookup"><span data-stu-id="1b768-116">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers, to provide the full number of replicas that the Front End pool architecture is designed for.</span></span> <span data-ttu-id="1b768-117">此外，在将服务器添加到前端池、从服务器中删除服务器或升级服务器时，必须遵循某些过程。</span><span class="sxs-lookup"><span data-stu-id="1b768-117">Additionally, you must follow certain procedures when adding servers to a Front End pool, removing servers from it, or upgrading servers.</span></span> <span data-ttu-id="1b768-118">有关详细信息，请参阅 [Lync Server 2013 中的前端服务器、即时消息和状态的拓扑和组件](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="1b768-118">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<div>

## <a name="server-role-topology-changes"></a><span data-ttu-id="1b768-119">服务器角色拓扑更改</span><span class="sxs-lookup"><span data-stu-id="1b768-119">Server Role Topology Changes</span></span>

<span data-ttu-id="1b768-120">之前在各台服务器上运行的部分服务器角色现已并置为前端服务器角色，使您节约了硬件成本</span><span class="sxs-lookup"><span data-stu-id="1b768-120">Some server roles that previously ran on separate servers are now consolidated into the Front End Server role, enabling you to save on hardware costs</span></span>

  - <span data-ttu-id="1b768-121">在 Lync Server 2013 中，A/V 会议服务器始终与前端服务器并置。</span><span class="sxs-lookup"><span data-stu-id="1b768-121">In Lync Server 2013, A/V Conferencing Server is always collocated with Front End Server.</span></span>

  - <span data-ttu-id="1b768-p104">监控和存档的前端现已与前端服务器并置。监控和存档仍需要单独的后端数据库，该数据库可在与前端池的后端数据库相同的服务器上进行并置，也可以驻留在各台后端服务器上。</span><span class="sxs-lookup"><span data-stu-id="1b768-p104">The front ends for both Monitoring and Archiving are now always collocated with Front End Server. Monitoring and Archiving each still require a separate Back-End Database, which can be collocated on the same server as the Front End Pool’s back-end database, or can be hosted on separate Back-End Servers.</span></span>

  - <span data-ttu-id="1b768-124">持久聊天服务器现在是一个服务器角色。</span><span class="sxs-lookup"><span data-stu-id="1b768-124">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="1b768-125">在 Microsoft Lync Server 2010 中，组聊天服务器是 Microsoft Lync Server 2010 的第三方受信任应用程序。</span><span class="sxs-lookup"><span data-stu-id="1b768-125">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="1b768-126">在 Lync Server 2013 中，持久聊天服务器功能是使用三个新的服务器角色实现的：</span><span class="sxs-lookup"><span data-stu-id="1b768-126">In Lync Server 2013, Persistent Chat Server functionality is implemented using three new server roles:</span></span>
    
      - <span data-ttu-id="1b768-127">**PersistentChatService：** 作为前端角色实施的主持久聊天服务器服务</span><span class="sxs-lookup"><span data-stu-id="1b768-127">**PersistentChatService:** Main Persistent Chat Server services implemented as a front end role</span></span>
    
      - <span data-ttu-id="1b768-128">**PersistentChatStore：** 后端服务器角色</span><span class="sxs-lookup"><span data-stu-id="1b768-128">**PersistentChatStore:** Back End Server role</span></span>
    
      - <span data-ttu-id="1b768-129">**PersistentChatComplianceStore：** 持久聊天合规性的后端服务器角色</span><span class="sxs-lookup"><span data-stu-id="1b768-129">**PersistentChatComplianceStore:** Back End Server role for Persistent Chat Compliance</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

