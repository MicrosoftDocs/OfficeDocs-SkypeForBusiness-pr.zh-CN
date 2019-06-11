---
title: Lync Server 2013 拓扑更改
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topology changes
ms:assetid: 9e40ef93-9ab0-498c-9bbf-f94584353e53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688153(v=OCS.15)
ms:contentKeyID: 49733756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f0ea02d1643a686e16d3d1984e756a48311b421
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topology-changes-in-lync-server-2013"></a><span data-ttu-id="90794-102">Lync Server 2013 中的拓扑更改</span><span class="sxs-lookup"><span data-stu-id="90794-102">Topology changes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90794-103">_**主题上次修改时间:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="90794-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="90794-104">Lync Server 2013 的拓扑要求和注意事项与早期版本的拓扑要求和注意事项不同, 如本节中所述。</span><span class="sxs-lookup"><span data-stu-id="90794-104">Topology requirements and considerations for Lync Server 2013 are different from those for earlier releases, as described in this section.</span></span>

<div>

## <a name="new-front-end-pools-architecture"></a><span data-ttu-id="90794-105">新的前端池体系结构</span><span class="sxs-lookup"><span data-stu-id="90794-105">New Front End Pools Architecture</span></span>

<span data-ttu-id="90794-106">在 Lync Server 2013 中, 企业版前端池的体系结构已更改为分布式系统体系结构。</span><span class="sxs-lookup"><span data-stu-id="90794-106">In Lync Server 2013, the architecture of Enterprise Edition Front End pools has changed to a distributed systems architecture.</span></span>

<span data-ttu-id="90794-107">使用此新体系结构, 后端数据库将不再是池中的实时数据存储。</span><span class="sxs-lookup"><span data-stu-id="90794-107">With this new architecture, the Back End database is no longer the real-time data store in a pool.</span></span> <span data-ttu-id="90794-108">有关特定用户的信息保存在池中的三个前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="90794-108">Information about a particular user is kept on three Front End Servers in the pool.</span></span> <span data-ttu-id="90794-109">对于每个用户, 一台前端服务器充当该用户的信息的主服务器, 另外两个其他前端服务器充当副本。</span><span class="sxs-lookup"><span data-stu-id="90794-109">For each user, one Front End Server acts as the master for that user’s information, and two other Front End Servers serve as replicas.</span></span> <span data-ttu-id="90794-110">如果前端服务器出现故障, 则作为副本提供的另一台前端服务器将自动提升为 master。</span><span class="sxs-lookup"><span data-stu-id="90794-110">If a Front End Server goes down, another Front End Server which served as a replica is automatically promoted to master.</span></span>

<span data-ttu-id="90794-111">这会在后台发生, 管理员无需知道哪些前端服务器是哪些前端服务器是其用户。</span><span class="sxs-lookup"><span data-stu-id="90794-111">This happens behind the scenes, and administrators do not need to know which Front End Servers are the masters for which users.</span></span> <span data-ttu-id="90794-112">此数据存储的分布提高了池中的性能和可伸缩性, 并消除了单个后端服务器的单点故障。</span><span class="sxs-lookup"><span data-stu-id="90794-112">This distribution of data storage improves performance and scalability within the pool, and eliminates the single point of failure of a single Back End Server.</span></span>

<span data-ttu-id="90794-113">后端服务器充当用户和会议数据的备份存储, 也是其他数据库 (如响应组数据库) 的主存储。</span><span class="sxs-lookup"><span data-stu-id="90794-113">The Back End Server serves as backup storage for user and conference data, and is also the primary storage for other databases such as the Response Group database.</span></span>

<span data-ttu-id="90794-114">这些改进还意味着你计划和维护池的方式有更改。</span><span class="sxs-lookup"><span data-stu-id="90794-114">These improvements also mean there are changes in how you plan and maintain your pools.</span></span> <span data-ttu-id="90794-115">我们建议, 所有的企业版前端池至少包含三个前端服务器, 以提供前端池体系结构设计所需的完整的副本数。</span><span class="sxs-lookup"><span data-stu-id="90794-115">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers, to provide the full number of replicas that the Front End pool architecture is designed for.</span></span> <span data-ttu-id="90794-116">此外, 在将服务器添加到前端池、从服务器中删除服务器或升级服务器时, 必须遵循某些过程。</span><span class="sxs-lookup"><span data-stu-id="90794-116">Additionally, you must follow certain procedures when adding servers to a Front End pool, removing servers from it, or upgrading servers.</span></span> <span data-ttu-id="90794-117">有关详细信息, 请参阅[Lync Server 2013 中前端服务器、即时消息和状态的拓扑和组件](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="90794-117">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<div>

## <a name="server-role-topology-changes"></a><span data-ttu-id="90794-118">服务器角色拓扑更改</span><span class="sxs-lookup"><span data-stu-id="90794-118">Server Role Topology Changes</span></span>

<span data-ttu-id="90794-119">以前在单独的服务器上运行的一些服务器角色现在合并到前端服务器角色中, 使你能够节省硬件成本</span><span class="sxs-lookup"><span data-stu-id="90794-119">Some server roles that previously ran on separate servers are now consolidated into the Front End Server role, enabling you to save on hardware costs</span></span>

  - <span data-ttu-id="90794-120">在 Lync Server 2013 中, A/V 会议服务器始终与前端服务器 collocated。</span><span class="sxs-lookup"><span data-stu-id="90794-120">In Lync Server 2013, A/V Conferencing Server is always collocated with Front End Server.</span></span>

  - <span data-ttu-id="90794-121">监视和存档的前端现在始终与前端服务器 collocated。</span><span class="sxs-lookup"><span data-stu-id="90794-121">The front ends for both Monitoring and Archiving are now always collocated with Front End Server.</span></span> <span data-ttu-id="90794-122">监视和存档每个设备仍需要单独的后端数据库, 该数据库可以在与前端池的后端数据库相同的服务器上 collocated, 也可以托管在单独的后端服务器上。</span><span class="sxs-lookup"><span data-stu-id="90794-122">Monitoring and Archiving each still require a separate Back-End Database, which can be collocated on the same server as the Front End Pool’s back-end database, or can be hosted on separate Back-End Servers.</span></span>

  - <span data-ttu-id="90794-123">持久聊天服务器现在是服务器角色。</span><span class="sxs-lookup"><span data-stu-id="90794-123">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="90794-124">在 Microsoft Lync Server 2010 中, 群组聊天服务器是 Microsoft Lync Server 2010 的第三方受信任的应用程序。</span><span class="sxs-lookup"><span data-stu-id="90794-124">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="90794-125">在 Lync Server 2013 中, 持续聊天服务器功能是使用三个新的服务器角色实现的:</span><span class="sxs-lookup"><span data-stu-id="90794-125">In Lync Server 2013, Persistent Chat Server functionality is implemented using three new server roles:</span></span>
    
      - <span data-ttu-id="90794-126">**PersistentChatService:** 作为前端角色实现的主持久聊天服务器服务</span><span class="sxs-lookup"><span data-stu-id="90794-126">**PersistentChatService:** Main Persistent Chat Server services implemented as a front end role</span></span>
    
      - <span data-ttu-id="90794-127">**PersistentChatStore:** 后端服务器角色</span><span class="sxs-lookup"><span data-stu-id="90794-127">**PersistentChatStore:** Back End Server role</span></span>
    
      - <span data-ttu-id="90794-128">**PersistentChatComplianceStore:** 持久的聊天合规性的后端服务器角色</span><span class="sxs-lookup"><span data-stu-id="90794-128">**PersistentChatComplianceStore:** Back End Server role for Persistent Chat Compliance</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

