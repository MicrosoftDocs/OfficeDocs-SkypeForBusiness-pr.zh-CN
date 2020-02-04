---
title: Lync Server 2013：高可用性和灾难恢复支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: High availability and disaster recovery support
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204866(v=OCS.15)
ms:contentKeyID: 48184053
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b73f6605f2fff063858a0180d61a306f7dd2d746
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a><span data-ttu-id="f2a4f-102">Lync Server 2013 中的高可用性和灾难恢复支持</span><span class="sxs-lookup"><span data-stu-id="f2a4f-102">High availability and disaster recovery support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2a4f-103">_**主题上次修改时间：** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="f2a4f-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="f2a4f-104">Lync Server 2013 通过池进行服务器冗余来提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="f2a4f-104">Lync Server 2013 provides high availability by server redundancy via pooling.</span></span> <span data-ttu-id="f2a4f-105">如果运行特定服务器角色的服务器发生故障，则池中运行相同角色的其他服务器将承担该服务器的负载。</span><span class="sxs-lookup"><span data-stu-id="f2a4f-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="f2a4f-106">这适用于前端服务器、边缘服务器、中介服务器和控制器。</span><span class="sxs-lookup"><span data-stu-id="f2a4f-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span> <span data-ttu-id="f2a4f-107">有关服务器角色的详细信息，请参阅[Lync server 2013 中的服务器角色](lync-server-2013-server-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="f2a4f-107">For details about server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="f2a4f-108">Lync Server 2013 还通过启用池配对来提供灾难恢复措施。</span><span class="sxs-lookup"><span data-stu-id="f2a4f-108">Lync Server 2013 also provides disaster recovery measures by enabling pool pairing.</span></span> <span data-ttu-id="f2a4f-109">如果您部署了此拓扑，则将指定前端池对，对中的每个池位于不同地理区域的不同数据中心。</span><span class="sxs-lookup"><span data-stu-id="f2a4f-109">If you deploy this topology, you will designate pairs of Front End pools, with each pool in a pair located in a separate data center, and in a separate geographical area.</span></span> <span data-ttu-id="f2a4f-110">如果一个池或一个站点不可用，则可将该池中的用户重定向至使用对中的其他池，并且对服务的干扰程度可以忽略不计。</span><span class="sxs-lookup"><span data-stu-id="f2a4f-110">If one pool or site goes down, you can redirect the users of that pool to use the other pool in the pair, with minimal interruption of service.</span></span>

<span data-ttu-id="f2a4f-111">Lync Server 2013 还支持后端服务器高可用性。</span><span class="sxs-lookup"><span data-stu-id="f2a4f-111">Lync Server 2013 also supports Back End Server high availability.</span></span> <span data-ttu-id="f2a4f-112">这是一个可选拓扑，你可以在其中部署前端池的两个后端服务器，并为在后端服务器上运行的所有 Lync 数据库设置同步 SQL Server 镜像。</span><span class="sxs-lookup"><span data-stu-id="f2a4f-112">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL Server mirroring for all the Lync databases running on the Back End Servers.</span></span>

<span data-ttu-id="f2a4f-113">有关池配对和后端服务器镜像的详细信息，请参阅[在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="f2a4f-113">For details about pool pairing and Back End Server mirroring, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="f2a4f-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2a4f-114">See Also</span></span>


[<span data-ttu-id="f2a4f-115">Lync Server 2013 中的服务器角色</span><span class="sxs-lookup"><span data-stu-id="f2a4f-115">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="f2a4f-116">在 Lync Server 2013 中规划高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="f2a4f-116">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

