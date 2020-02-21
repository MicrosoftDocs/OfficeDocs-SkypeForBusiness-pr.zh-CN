---
title: Lync Server 2013：基于位置的路由概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85d24aeb94a0c16e93d885c5b6db20385cdf0f26
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="d1377-102">Lync Server 2013 中基于位置的路由概述</span><span class="sxs-lookup"><span data-stu-id="d1377-102">Overview of Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1377-103">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d1377-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d1377-104">基于位置的路由引入了一组新的规则，这些规则可修改国内和国际 PSTN 呼叫的路由以防止收费绕过。</span><span class="sxs-lookup"><span data-stu-id="d1377-104">Location-Based Routing introduces a new set of rules that modifies the routing of national and international PSTN calls to prevent toll bypass.</span></span> <span data-ttu-id="d1377-105">基于位置的路由可以灵活地将这些规则限定为特定区域、特定网关或仅特定用户集。</span><span class="sxs-lookup"><span data-stu-id="d1377-105">Location-Based Routing provides the flexibility to scope these rules to specific regions, specific gateways or to specific set of users only.</span></span>

<span data-ttu-id="d1377-106">以下方案说明了可以强制实施基于位置的限制的主要路由类型：</span><span class="sxs-lookup"><span data-stu-id="d1377-106">The following scenarios illustrate the main types of restrictions Location-Based Routing can enforce:</span></span>

  - <span data-ttu-id="d1377-107">出局呼叫–基于位置的路由可以强制传出呼叫从位于与呼叫者阻止 PSTN 收费旁路的 PSTN 网关传出的传出呼叫，这样可以防止从位于不同区域的 PSTN 网关传出的传出呼叫者.</span><span class="sxs-lookup"><span data-stu-id="d1377-107">Egress calls – Location-Based Routing can enforce outgoing calls to egress from a PSTN gateway that is located in the same region as where the caller is to prevent PSTN toll bypass, which prevents calls to egress from a PSTN gateway located in a different region as the caller.</span></span>

  - <span data-ttu-id="d1377-108">入站呼叫–基于位置的路由可以阻止传入 PSTN 呼叫拨打 Lync 终结点，如果传入呼叫与被呼叫 Lync 用户不在同一区域中。</span><span class="sxs-lookup"><span data-stu-id="d1377-108">Ingress calls – Location-Based Routing can prevent incoming PSTN calls to ring Lync endpoints if the PSTN gateway routing the incoming call is not located in the same region as the called Lync user.</span></span>

  - <span data-ttu-id="d1377-109">未知区域–基于位置的路由将传入和传出 PSTN 呼叫限制在不确定位置（即从 Internet 连接或位于未知区域的远程用户）中的用户。</span><span class="sxs-lookup"><span data-stu-id="d1377-109">Unknown regions – Location-Based Routing restricts incoming and outgoing PSTN calls to and from users that are located in undetermined locations (i.e. remote users connecting from the Internet or located in unknown regions).</span></span>

  - <span data-ttu-id="d1377-110">国际区域–如果找不到用户所在位置的网关，则基于位置的路由会强制通过国际 PSTN 网关路由传出呼叫。</span><span class="sxs-lookup"><span data-stu-id="d1377-110">International regions – Location-Based Routing enforces routing of outgoing calls through international PSTN gateways if a gateway local to the user’s location cannot be found.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d1377-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1377-111">See Also</span></span>


[<span data-ttu-id="d1377-112">在 Lync Server 2013 中规划基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="d1377-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

