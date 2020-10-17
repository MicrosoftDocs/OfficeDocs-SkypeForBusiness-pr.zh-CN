---
title: Lync Server 2013：用户的位置
description: Lync Server 2013：用户的位置。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User's location
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994073(v=OCS.15)
ms:contentKeyID: 51803984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a92ec780809cdb3e1ee582ce6c348c884bbb5890
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561208"
---
# <a name="users-location-in-lync-server-2013"></a><span data-ttu-id="6e830-103">Lync Server 2013 中的用户位置</span><span class="sxs-lookup"><span data-stu-id="6e830-103">User's location in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e830-104">_**上次修改的主题：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="6e830-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="6e830-105">Location-Based 路由利用了在 Lync Server 中定义的、由 E9-1-1、CAC 和媒体旁路使用的相同网络区域、站点和子网，以应用呼叫路由限制以防止 PSTN 收费旁路。</span><span class="sxs-lookup"><span data-stu-id="6e830-105">Location-Based Routing leverages the same network regions, sites and subnets as defined in Lync Server used by E9-1-1, CAC and Media Bypass to apply call routing restrictions to prevent PSTN toll bypass.</span></span> <span data-ttu-id="6e830-106">用户的位置由连接的 Lync 终结点 (s) 的 IP 子网决定。</span><span class="sxs-lookup"><span data-stu-id="6e830-106">A user’s location is determined by the IP subnet of the user’s Lync endpoint(s) are connected from.</span></span> <span data-ttu-id="6e830-107">每个 IP 子网都与一个网络站点相关联，该站点聚合到由管理员定义的网络区域中。</span><span class="sxs-lookup"><span data-stu-id="6e830-107">Each IP subnet is associated to a network site, which are aggregated into network regions defined by the administrator.</span></span> <span data-ttu-id="6e830-108">根据用户的网络站点强制执行 Location-Based 路由。</span><span class="sxs-lookup"><span data-stu-id="6e830-108">Location-Based Routing is enforced based on the user’s network site.</span></span>

<span data-ttu-id="6e830-109">Location-Based 路由规则是针对每个网络站点应用的，这意味着给定的一组规则将应用于为位于同一网络站点内的 Location-Based 路由启用的所有终结点。</span><span class="sxs-lookup"><span data-stu-id="6e830-109">Location-Based Routing rules are applied on a per network site basis, meaning that a given set of rules will be applied to all endpoints enabled for Location-Based Routing that are located within the same network site.</span></span> <span data-ttu-id="6e830-110">管理员可以将 Location-Based 路由应用到需要它的网络站点。</span><span class="sxs-lookup"><span data-stu-id="6e830-110">Administrators can apply Location-Based Routing to network sites that require it.</span></span>

<span data-ttu-id="6e830-111">可以在每个网络站点上定义语音路由策略，以定义应由位于网络站点中的所有用户用来呼叫 PSTN 电话号码的特定 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="6e830-111">Voice routing policies can be defined on a per network site basis to define a particular PSTN gateway that should be used by all users located in the network site to call PSTN phone numbers.</span></span> <span data-ttu-id="6e830-112">当用户位于为 Location-Based 路由启用的网络站点中时，此类语音路由策略将优先于由用户语音策略定义的路由，并且它将阻止通过为 Location-Based 路由启用的其他 PSTN 网关路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="6e830-112">Such voice routing policies will take precedence over the routing defined by the user’s voice policy when the user is located in a network site enabled for Location-Based Routing, and it will prevent the routing of calls via other PSTN gateways that are enabled for Location-Based Routing.</span></span> <span data-ttu-id="6e830-113">当 Lync 用户发出 PSTN 呼叫时，用户的语音策略将确定是否可以授权用户发出呼叫。</span><span class="sxs-lookup"><span data-stu-id="6e830-113">When a Lync user places a PSTN call, the user’s voice policy determines whether the user can be authorized to place the call.</span></span> <span data-ttu-id="6e830-114">如果用户的语音策略允许用户发出呼叫，Location-Based 路由决定了呼叫应传出的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="6e830-114">If the user’s voice policy allows the user to place the call, Location-Based Routing determines which PSTN gateway the call should egress from.</span></span> <span data-ttu-id="6e830-115">Location-Based 路由根据用户的位置做出此决定。</span><span class="sxs-lookup"><span data-stu-id="6e830-115">Location-Based Routing makes this determination based on the user’s location.</span></span>

<span data-ttu-id="6e830-116">可以通过以下方式对用户位置进行分类：</span><span class="sxs-lookup"><span data-stu-id="6e830-116">A user location can be categorized in the following ways:</span></span>

  - <span data-ttu-id="6e830-117">用户位于为 Location-Based 路由启用的已知网络站点，且其 (的 "直接向内拨号) 号码" 在位于同一网络站点 (的 PSTN 网关处终止例如 office) 。</span><span class="sxs-lookup"><span data-stu-id="6e830-117">The user is located in a known network site enabled for Location-Based Routing and his DID (Direct Inward Dial) number terminates on a PSTN gateway placed in the same network site (i.e. office).</span></span> <span data-ttu-id="6e830-118">出站呼叫的路由将通过用户所在的网络站点的语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="6e830-118">The routing of outbound calls will be through the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="6e830-119">对用户的传入 PSTN 呼叫将路由到位于与 PSTN 网关相同的网络站点中的终结点。</span><span class="sxs-lookup"><span data-stu-id="6e830-119">Incoming PSTN calls to the user are routed to endpoints that are located in the same network site as the PSTN gateway.</span></span>

  - <span data-ttu-id="6e830-120">用户位于与 PSTN 网关所在的网络站点不同的已知网络站点中。</span><span class="sxs-lookup"><span data-stu-id="6e830-120">The user is located in a known network site that is in different from the network site where the PSTN gateway is located.</span></span> <span data-ttu-id="6e830-121"> (即向其他企业办公室旅行) 的用户。</span><span class="sxs-lookup"><span data-stu-id="6e830-121">(i.e. the user traveled to another corporate office).</span></span> <span data-ttu-id="6e830-122">出站呼叫的路由将使用用户所在的网络站点的语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="6e830-122">The routing of outbound calls will be using the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="6e830-123">对用户的传入 PSTN 呼叫不会路由到位于与 PSTN 网关不同的其他站点的终结点，从而防止 PSTN 收费绕过。</span><span class="sxs-lookup"><span data-stu-id="6e830-123">Incoming PSTN calls to the user will not be routed to endpoints that are located in different sites than the PSTN gateway to prevent PSTN toll bypassing.</span></span>

  - <span data-ttu-id="6e830-124">当用户位于 Lync Server 部署无法识别的网络站点中时，出站呼叫的路由将基于为用户分配的语音策略，而不是绑定到 Location-Based 路由限制的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="6e830-124">When a user is located in a network site that is unknown to the Lync Server deployment, the routing of outbound calls will be based on the voice policy assigned to the user to PSTN gateways not bound to Location-Based Routing restrictions.</span></span> <span data-ttu-id="6e830-125">传入 PSTN 呼叫不会路由到位于未知网络站点中的终结点，从而防止 PSTN 收费绕过。</span><span class="sxs-lookup"><span data-stu-id="6e830-125">Incoming PSTN calls will not be routed to endpoints that are located in unknown network sites to prevent PSTN toll bypassing.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="6e830-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e830-126">See Also</span></span>


[<span data-ttu-id="6e830-127">Lync Server 2013 中 Location-Based 路由的指南</span><span class="sxs-lookup"><span data-stu-id="6e830-127">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

