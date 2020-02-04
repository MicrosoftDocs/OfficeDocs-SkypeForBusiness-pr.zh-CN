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
ms.openlocfilehash: 07a7db57d506b892fd030efccfb304c7103e1e9f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755506"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="d19ff-102">Lync Server 2013 中基于位置的路由概述</span><span class="sxs-lookup"><span data-stu-id="d19ff-102">Overview of Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d19ff-103">_**主题上次修改时间：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d19ff-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d19ff-p101">基于位置的路由引入了一组新规则，它们可修改国内和国际 PSTN 呼叫的路由以防止收费绕路情形。使用基于位置的路由可灵活地将这些规则限定为仅特定区域、特定网关或特定用户集。</span><span class="sxs-lookup"><span data-stu-id="d19ff-p101">Location-Based Routing introduces a new set of rules that modifies the routing of national and international PSTN calls to prevent toll bypass. Location-Based Routing provides the flexibility to scope these rules to specific regions, specific gateways or to specific set of users only.</span></span>

<span data-ttu-id="d19ff-106">以下方案说明了基于位置的主要路由可强制执行的主要类型：</span><span class="sxs-lookup"><span data-stu-id="d19ff-106">The following scenarios illustrate the main types of restrictions Location-Based Routing can enforce:</span></span>

  - <span data-ttu-id="d19ff-107">外出呼叫–基于位置的路由可以强制传出调用来自与呼叫者在同一区域中的传出呼叫，该网关位于与呼叫者阻止 PSTN 免绕过的位置，从而阻止从其他区域中的 PSTN 网关传出的传出呼叫程序.</span><span class="sxs-lookup"><span data-stu-id="d19ff-107">Egress calls – Location-Based Routing can enforce outgoing calls to egress from a PSTN gateway that is located in the same region as where the caller is to prevent PSTN toll bypass, which prevents calls to egress from a PSTN gateway located in a different region as the caller.</span></span>

  - <span data-ttu-id="d19ff-108">入站呼叫-基于位置的路由可以阻止传入的 PSTN 呼叫拨打 Lync 终结点，前提是传入呼叫与被呼叫的 Lync 用户没有位于同一区域。</span><span class="sxs-lookup"><span data-stu-id="d19ff-108">Ingress calls – Location-Based Routing can prevent incoming PSTN calls to ring Lync endpoints if the PSTN gateway routing the incoming call is not located in the same region as the called Lync user.</span></span>

  - <span data-ttu-id="d19ff-109">未知区域-基于位置的路由对位于不确定位置（即从 Internet 连接或位于未知区域中的远程用户）的用户限制传入和传出 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="d19ff-109">Unknown regions – Location-Based Routing restricts incoming and outgoing PSTN calls to and from users that are located in undetermined locations (i.e. remote users connecting from the Internet or located in unknown regions).</span></span>

  - <span data-ttu-id="d19ff-110">国际区域-基于位置的路由通过国际 PSTN 网关（如果找不到用户位置的本地网关）来强制路由传出呼叫。</span><span class="sxs-lookup"><span data-stu-id="d19ff-110">International regions – Location-Based Routing enforces routing of outgoing calls through international PSTN gateways if a gateway local to the user’s location cannot be found.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d19ff-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d19ff-111">See Also</span></span>


[<span data-ttu-id="d19ff-112">在 Lync Server 2013 中规划基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="d19ff-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

