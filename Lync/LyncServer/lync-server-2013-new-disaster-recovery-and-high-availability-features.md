---
title: Lync Server 2013：新的灾难恢复和高可用性功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New disaster recovery and high availability features
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48184130
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aabac29c5e866c4bfeff8ad79d392578d52ba650
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757516"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a><span data-ttu-id="0a62d-102">Lync Server 2013 中新的灾难恢复和高可用性功能</span><span class="sxs-lookup"><span data-stu-id="0a62d-102">New disaster recovery and high availability features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a62d-103">_**主题上次修改时间：** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="0a62d-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="0a62d-104">与 Lync Server 2010 中一样，Lync Server 2013 的主高可用性（HA）方案基于服务器冗余（通过池划分）。</span><span class="sxs-lookup"><span data-stu-id="0a62d-104">As in Lync Server 2010, the main high availability (HA) scheme for Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="0a62d-105">如果运行特定服务器角色的服务器发生故障，则池中运行相同角色的其他服务器将承担该服务器的负载。</span><span class="sxs-lookup"><span data-stu-id="0a62d-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="0a62d-106">这适用于前端服务器、边缘服务器、中介服务器和控制器。</span><span class="sxs-lookup"><span data-stu-id="0a62d-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="0a62d-107">Lync Server 2013 通过使你能够对位于两个数据中心的前端池进行配对来添加新的灾难恢复措施。</span><span class="sxs-lookup"><span data-stu-id="0a62d-107">Lync Server 2013 adds new disaster recovery measures by enabling you to pair Front End pools located in two datacenters.</span></span> <span data-ttu-id="0a62d-108">如果其中一个配对的池出现故障，则管理员可以将该池中的用户故障转移到该池中的另一个池，以便提供服务的延续。</span><span class="sxs-lookup"><span data-stu-id="0a62d-108">If one of the paired pools goes down, an administrator can fail over the users from that pool to the other pool in the pair, to provide continuation of service.</span></span> <span data-ttu-id="0a62d-109">此功能不需要昂贵的网络或硬件解决方案，例如存储网络或共享磁盘。</span><span class="sxs-lookup"><span data-stu-id="0a62d-109">This functionality does not require expensive network or hardware solutions such as storage networks or shared disks.</span></span>

<span data-ttu-id="0a62d-110">Lync Server 2013 还添加了后端服务器高可用性。</span><span class="sxs-lookup"><span data-stu-id="0a62d-110">Lync Server 2013 also adds Back End Server high availability.</span></span> <span data-ttu-id="0a62d-111">这是一个可选拓扑，你可以在其中部署前端池的两个后端服务器，并为在后端服务器上运行的所有 Lync 数据库设置同步 SQL 镜像。</span><span class="sxs-lookup"><span data-stu-id="0a62d-111">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL mirroring for all the Lync databases running on the Back End Servers.</span></span> <span data-ttu-id="0a62d-112">你可以选择是否为镜像部署见证。</span><span class="sxs-lookup"><span data-stu-id="0a62d-112">You may choose whether to deploy a witness for the mirror.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="0a62d-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a62d-113">See Also</span></span>


[<span data-ttu-id="0a62d-114">在 Lync Server 2013 中规划高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="0a62d-114">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

