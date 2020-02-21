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
ms.openlocfilehash: 7845f919f04985e67d6825b8722904a9158606b7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a><span data-ttu-id="694c8-102">Lync Server 2013 中的新的灾难恢复和高可用性功能</span><span class="sxs-lookup"><span data-stu-id="694c8-102">New disaster recovery and high availability features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="694c8-103">_**上次修改的主题：** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="694c8-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="694c8-104">与 Lync Server 2010 中一样，Lync Server 2013 的主高可用性（HA）方案基于服务器冗余（通过池划分）。</span><span class="sxs-lookup"><span data-stu-id="694c8-104">As in Lync Server 2010, the main high availability (HA) scheme for Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="694c8-105">如果运行特定服务器角色的服务器发生故障，那么池中运行同一角色的其他服务器将接纳该服务器的负荷。</span><span class="sxs-lookup"><span data-stu-id="694c8-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="694c8-106">这适用于前端服务器、边缘服务器、中介服务器和控制器。</span><span class="sxs-lookup"><span data-stu-id="694c8-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="694c8-107">Lync Server 2013 通过使您能够对位于两个数据中心的前端池进行配对，从而添加了新的灾难恢复措施。</span><span class="sxs-lookup"><span data-stu-id="694c8-107">Lync Server 2013 adds new disaster recovery measures by enabling you to pair Front End pools located in two datacenters.</span></span> <span data-ttu-id="694c8-108">如果其中一个配对池不可用，则管理员可将该池中的用户故障转移到配对中的其他池，以继续提供服务。</span><span class="sxs-lookup"><span data-stu-id="694c8-108">If one of the paired pools goes down, an administrator can fail over the users from that pool to the other pool in the pair, to provide continuation of service.</span></span> <span data-ttu-id="694c8-109">此功能无需昂贵的网络或硬件解决方案，如存储网络或共享磁盘。</span><span class="sxs-lookup"><span data-stu-id="694c8-109">This functionality does not require expensive network or hardware solutions such as storage networks or shared disks.</span></span>

<span data-ttu-id="694c8-110">Lync Server 2013 还添加了后端服务器高可用性。</span><span class="sxs-lookup"><span data-stu-id="694c8-110">Lync Server 2013 also adds Back End Server high availability.</span></span> <span data-ttu-id="694c8-111">这是一个可选拓扑，可在其中为前端池部署两台后端服务器，并为在后端服务器上运行的所有 Lync 数据库设置同步的 SQL 镜像。</span><span class="sxs-lookup"><span data-stu-id="694c8-111">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL mirroring for all the Lync databases running on the Back End Servers.</span></span> <span data-ttu-id="694c8-112">您可选择是否为镜像部署见证。</span><span class="sxs-lookup"><span data-stu-id="694c8-112">You may choose whether to deploy a witness for the mirror.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="694c8-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="694c8-113">See Also</span></span>


[<span data-ttu-id="694c8-114">在 Lync Server 2013 中规划高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="694c8-114">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

