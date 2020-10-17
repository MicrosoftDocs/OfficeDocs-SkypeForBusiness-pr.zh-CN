---
title: Lync Server 2013： Location-Based 路由概述
description: Lync Server 2013： Location-Based 路由的概述。
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
ms.openlocfilehash: 0b1e026791a8562629231b91b58d7e7eff569ffa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562808"
---
# <a name="overview-of-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="f24ea-103">Lync Server 2013 中的 Location-Based 路由概述</span><span class="sxs-lookup"><span data-stu-id="f24ea-103">Overview of Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f24ea-104">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f24ea-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f24ea-105">Location-Based 传送引入了一组新的规则，这些规则可修改国内和国际 PSTN 呼叫的路由以防止收费绕过。</span><span class="sxs-lookup"><span data-stu-id="f24ea-105">Location-Based Routing introduces a new set of rules that modifies the routing of national and international PSTN calls to prevent toll bypass.</span></span> <span data-ttu-id="f24ea-106">Location-Based 路由可以灵活地将这些规则限定为特定区域、特定网关或仅特定用户集。</span><span class="sxs-lookup"><span data-stu-id="f24ea-106">Location-Based Routing provides the flexibility to scope these rules to specific regions, specific gateways or to specific set of users only.</span></span>

<span data-ttu-id="f24ea-107">以下方案说明了 Location-Based 路由可以强制执行的主要限制类型：</span><span class="sxs-lookup"><span data-stu-id="f24ea-107">The following scenarios illustrate the main types of restrictions Location-Based Routing can enforce:</span></span>

  - <span data-ttu-id="f24ea-108">出局呼叫– Location-Based 路由可以强制传出呼叫从位于与呼叫者阻止 PSTN 收费旁路的 PSTN 网关的传出呼叫，这将阻止从位于不同区域中的 PSTN 网关传出的传出呼叫呼叫者。</span><span class="sxs-lookup"><span data-stu-id="f24ea-108">Egress calls – Location-Based Routing can enforce outgoing calls to egress from a PSTN gateway that is located in the same region as where the caller is to prevent PSTN toll bypass, which prevents calls to egress from a PSTN gateway located in a different region as the caller.</span></span>

  - <span data-ttu-id="f24ea-109">入站呼叫–如果 PSTN 网关路由传入呼叫不在与被叫 Lync 用户相同的区域中，则 Location-Based 路由可以阻止传入 PSTN 呼叫拨打 Lync 终结点。</span><span class="sxs-lookup"><span data-stu-id="f24ea-109">Ingress calls – Location-Based Routing can prevent incoming PSTN calls to ring Lync endpoints if the PSTN gateway routing the incoming call is not located in the same region as the called Lync user.</span></span>

  - <span data-ttu-id="f24ea-110">未知区域– Location-Based 路由将传入和传出 PSTN 呼叫限制在不确定位置的用户 (例如，从 Internet 连接或位于未知区域中的远程用户) 。</span><span class="sxs-lookup"><span data-stu-id="f24ea-110">Unknown regions – Location-Based Routing restricts incoming and outgoing PSTN calls to and from users that are located in undetermined locations (i.e. remote users connecting from the Internet or located in unknown regions).</span></span>

  - <span data-ttu-id="f24ea-111">国际区域–如果找不到用户位置的网关，则路由通过国际 PSTN 网关执行传出呼叫的路由（如果找不到用户位置的网关 Location-Based）。</span><span class="sxs-lookup"><span data-stu-id="f24ea-111">International regions – Location-Based Routing enforces routing of outgoing calls through international PSTN gateways if a gateway local to the user’s location cannot be found.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="f24ea-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f24ea-112">See Also</span></span>


[<span data-ttu-id="f24ea-113">在 Lync Server 2013 中规划 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="f24ea-113">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

