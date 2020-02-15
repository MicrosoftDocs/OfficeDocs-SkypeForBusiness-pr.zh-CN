---
title: Lync Server 2013：基于位置的路由的技术注意事项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical considerations for Location-Based Routing
ms:assetid: 2e2a9199-7c6f-48d3-9adb-3873fc4f8c4e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994027(v=OCS.15)
ms:contentKeyID: 51803936
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcdebdccd0584d31b27120709212be674e8d3c2a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049264"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="c7aeb-102">Lync Server 2013 中基于位置的路由的技术注意事项</span><span class="sxs-lookup"><span data-stu-id="c7aeb-102">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7aeb-103">_**上次修改的主题：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="c7aeb-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="c7aeb-104">在规划基于位置的路由时，应考虑对以下方案的影响。</span><span class="sxs-lookup"><span data-stu-id="c7aeb-104">When planning Location-Based Routing, you should consider the impact to the following scenarios.</span></span>

<div>

## <a name="disaster-recovery"></a><span data-ttu-id="c7aeb-105">灾难恢复</span><span class="sxs-lookup"><span data-stu-id="c7aeb-105">Disaster Recovery</span></span>

<span data-ttu-id="c7aeb-106">在将主池故障转移到备份池以及将正常操作还原到主池的过程中，在灾难和恢复过程中始终强制实施基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="c7aeb-106">During a failover from the primary pool to a backup pool as well as when restoring normal operations to the primary pool, Location-Based Routing remains enforced at all times during a disaster and recovery procedure.</span></span>

</div>

<div>

## <a name="survivable-branch-appliance"></a><span data-ttu-id="c7aeb-107">Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="c7aeb-107">Survivable Branch Appliance</span></span>

<span data-ttu-id="c7aeb-108">配置基于位置的路由会影响规划与 Survivable 分支设备关联的网关的部署位置。</span><span class="sxs-lookup"><span data-stu-id="c7aeb-108">Configuring Location-Based Routing impacts the planning of where you deploy the gateways associated to your Survivable Branch Appliances.</span></span> <span data-ttu-id="c7aeb-109">与您的 SBA 关联的网关必须位于与您的 Survivable 分支装置相同的网络站点中;否则，如果配置基于位置的路由，则不允许驻留在 Survivable 分支设备上的用户发出出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="c7aeb-109">The gateway associated to your SBA must be located in the same network site as your Survivable Branch Appliance; otherwise, users homed on your Survivable Branch Appliance will not be permitted to place outbound calls if Location-Based Routing is configured.</span></span> <span data-ttu-id="c7aeb-110">当您的 Survivable 分支设备与中心站点之间的 WAN 连接关闭时，基于位置的路由限制仍将强制实施。</span><span class="sxs-lookup"><span data-stu-id="c7aeb-110">When the WAN connection between your Survivable Branch Appliance and the central site is down, Location-Based Routing restrictions remains enforced.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c7aeb-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7aeb-111">See Also</span></span>


[<span data-ttu-id="c7aeb-112">在 Lync Server 2013 中规划基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="c7aeb-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

