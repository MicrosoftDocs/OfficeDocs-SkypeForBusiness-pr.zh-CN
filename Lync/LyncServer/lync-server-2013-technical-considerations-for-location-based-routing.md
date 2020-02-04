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
ms.openlocfilehash: 978590484cbb6bd3c23fac26422c186847662e49
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="c72b6-102">Lync Server 2013 中基于位置的路由的技术注意事项</span><span class="sxs-lookup"><span data-stu-id="c72b6-102">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c72b6-103">_**主题上次修改时间：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="c72b6-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="c72b6-104">规划基于位置的路由时，应考虑对以下方案的影响。</span><span class="sxs-lookup"><span data-stu-id="c72b6-104">When planning Location-Based Routing, you should consider the impact to the following scenarios.</span></span>

<div>

## <a name="disaster-recovery"></a><span data-ttu-id="c72b6-105">灾难恢复</span><span class="sxs-lookup"><span data-stu-id="c72b6-105">Disaster Recovery</span></span>

<span data-ttu-id="c72b6-106">在将主池故障转移到备份池以及将正常操作还原到主池的过程中，在灾难和恢复过程中始终强制执行基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="c72b6-106">During a failover from the primary pool to a backup pool as well as when restoring normal operations to the primary pool, Location-Based Routing remains enforced at all times during a disaster and recovery procedure.</span></span>

</div>

<div>

## <a name="survivable-branch-appliance"></a><span data-ttu-id="c72b6-107">Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="c72b6-107">Survivable Branch Appliance</span></span>

<span data-ttu-id="c72b6-108">配置基于位置的路由会影响你部署与 Survivable 分支机构相关联的网关的位置的规划。</span><span class="sxs-lookup"><span data-stu-id="c72b6-108">Configuring Location-Based Routing impacts the planning of where you deploy the gateways associated to your Survivable Branch Appliances.</span></span> <span data-ttu-id="c72b6-109">与你的 SBA 关联的网关必须与 Survivable 分支装置位于同一网络站点;否则，如果配置基于位置的路由，则不允许驻留在 Survivable 分支设备上的用户进行出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="c72b6-109">The gateway associated to your SBA must be located in the same network site as your Survivable Branch Appliance; otherwise, users homed on your Survivable Branch Appliance will not be permitted to place outbound calls if Location-Based Routing is configured.</span></span> <span data-ttu-id="c72b6-110">当 Survivable 分支设备和中心网站之间的 WAN 连接关闭时，基于位置的路由限制将保持强制实施。</span><span class="sxs-lookup"><span data-stu-id="c72b6-110">When the WAN connection between your Survivable Branch Appliance and the central site is down, Location-Based Routing restrictions remains enforced.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c72b6-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c72b6-111">See Also</span></span>


[<span data-ttu-id="c72b6-112">在 Lync Server 2013 中规划基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="c72b6-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

