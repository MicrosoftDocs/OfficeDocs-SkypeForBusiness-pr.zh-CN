---
title: Lync Server 2013：用户的位置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User's location
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994073(v=OCS.15)
ms:contentKeyID: 51803984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e9eac8fce71d99e0817c57841e2539ed6423f2a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-location-in-lync-server-2013"></a><span data-ttu-id="bceed-102">Lync Server 2013 中用户的位置</span><span class="sxs-lookup"><span data-stu-id="bceed-102">User's location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bceed-103">_**主题上次修改时间:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="bceed-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="bceed-104">基于位置的路由利用由 E9 使用的 Lync Server 中定义的相同网络区域、网站和子网, 以便应用呼叫路由限制以防止 PSTN 免绕过。</span><span class="sxs-lookup"><span data-stu-id="bceed-104">Location-Based Routing leverages the same network regions, sites and subnets as defined in Lync Server used by E9-1-1, CAC and Media Bypass to apply call routing restrictions to prevent PSTN toll bypass.</span></span> <span data-ttu-id="bceed-105">用户的位置由用户的 Lync 终结点连接的 IP 子网确定。</span><span class="sxs-lookup"><span data-stu-id="bceed-105">A user’s location is determined by the IP subnet of the user’s Lync endpoint(s) are connected from.</span></span> <span data-ttu-id="bceed-106">每个 IP 子网都与一个网络站点相关联，它们将聚合到由管理员确定的网络区域中。</span><span class="sxs-lookup"><span data-stu-id="bceed-106">Each IP subnet is associated to a network site, which are aggregated into network regions defined by the administrator.</span></span> <span data-ttu-id="bceed-107">基于位置的路由基于用户的网络站点强制实施。</span><span class="sxs-lookup"><span data-stu-id="bceed-107">Location-Based Routing is enforced based on the user’s network site.</span></span>

<span data-ttu-id="bceed-108">基于位置的路由规则是针对每个网络站点应用的, 这意味着给定的一组规则将应用于为位于同一网络站点内的基于位置的路由启用的所有终结点。</span><span class="sxs-lookup"><span data-stu-id="bceed-108">Location-Based Routing rules are applied on a per network site basis, meaning that a given set of rules will be applied to all endpoints enabled for Location-Based Routing that are located within the same network site.</span></span> <span data-ttu-id="bceed-109">管理员可以将基于位置的路由应用于需要它的网络站点。</span><span class="sxs-lookup"><span data-stu-id="bceed-109">Administrators can apply Location-Based Routing to network sites that require it.</span></span>

<span data-ttu-id="bceed-110">可以在每个网络站点上定义语音路由策略，以定义应由网络站点内的所有用户用于呼叫 PSTN 号码的特殊 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="bceed-110">Voice routing policies can be defined on a per network site basis to define a particular PSTN gateway that should be used by all users located in the network site to call PSTN phone numbers.</span></span> <span data-ttu-id="bceed-111">当用户位于为基于位置的路由启用的网络站点中时, 此类语音路由策略将优先于用户的语音策略所定义的路由, 并且它将阻止通过其他 PSTN 网关启用呼叫路由基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="bceed-111">Such voice routing policies will take precedence over the routing defined by the user’s voice policy when the user is located in a network site enabled for Location-Based Routing, and it will prevent the routing of calls via other PSTN gateways that are enabled for Location-Based Routing.</span></span> <span data-ttu-id="bceed-112">当 Lync 用户发出 PSTN 呼叫时, 用户的语音策略确定是否可以授权用户进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="bceed-112">When a Lync user places a PSTN call, the user’s voice policy determines whether the user can be authorized to place the call.</span></span> <span data-ttu-id="bceed-113">如果用户的语音策略允许用户进行呼叫, 则基于位置的路由确定呼叫应传出的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="bceed-113">If the user’s voice policy allows the user to place the call, Location-Based Routing determines which PSTN gateway the call should egress from.</span></span> <span data-ttu-id="bceed-114">基于位置的路由根据用户的位置进行此确定。</span><span class="sxs-lookup"><span data-stu-id="bceed-114">Location-Based Routing makes this determination based on the user’s location.</span></span>

<span data-ttu-id="bceed-115">用户位置可以通过以下方式进行分类：</span><span class="sxs-lookup"><span data-stu-id="bceed-115">A user location can be categorized in the following ways:</span></span>

  - <span data-ttu-id="bceed-116">用户位于为基于位置的路由启用的已知网络站点, 并且其已完成 (直接拨入式拨号) 号码将在位于同一网络站点 (即 office) 的 PSTN 网关上终止。</span><span class="sxs-lookup"><span data-stu-id="bceed-116">The user is located in a known network site enabled for Location-Based Routing and his DID (Direct Inward Dial) number terminates on a PSTN gateway placed in the same network site (i.e. office).</span></span> <span data-ttu-id="bceed-117">出站呼叫通过用户所在的网络站点的语音路由策略进行路由。</span><span class="sxs-lookup"><span data-stu-id="bceed-117">The routing of outbound calls will be through the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="bceed-118">发往用户的传入 PSTN 呼叫将路由到与 PSTN 网关位于相同网络站点中的终结点。</span><span class="sxs-lookup"><span data-stu-id="bceed-118">Incoming PSTN calls to the user are routed to endpoints that are located in the same network site as the PSTN gateway.</span></span>

  - <span data-ttu-id="bceed-p105">用户所在的已知网络站点不同于 PSTN 网关所在的网络站点。（例如，用户前往另一公司办事处出差。）出站呼叫使用用户所在的网络站点的语音路由策略进行路由。发往用户的传入 PSTN 呼叫不会路由到所在站点与 PSTN 网关不同的终结点，从而防止 PSTN 收费绕路情形。</span><span class="sxs-lookup"><span data-stu-id="bceed-p105">The user is located in a known network site that is in different from the network site where the PSTN gateway is located. (i.e. the user traveled to another corporate office). The routing of outbound calls will be using the voice routing policy of the network site in which the user is located. Incoming PSTN calls to the user will not be routed to endpoints that are located in different sites than the PSTN gateway to prevent PSTN toll bypassing.</span></span>

  - <span data-ttu-id="bceed-123">当用户位于 Lync Server 部署未知的网络网站中时, 出站呼叫的路由将基于分配给用户的语音策略, 而不是绑定到基于位置的路由限制的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="bceed-123">When a user is located in a network site that is unknown to the Lync Server deployment, the routing of outbound calls will be based on the voice policy assigned to the user to PSTN gateways not bound to Location-Based Routing restrictions.</span></span> <span data-ttu-id="bceed-124">传入 PSTN 呼叫不会路由到位于未知网络站点内的终结点，从而防止 PSTN 收费绕路情形。</span><span class="sxs-lookup"><span data-stu-id="bceed-124">Incoming PSTN calls will not be routed to endpoints that are located in unknown network sites to prevent PSTN toll bypassing.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="bceed-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bceed-125">See Also</span></span>


[<span data-ttu-id="bceed-126">Lync Server 2013 中基于位置的路由指南</span><span class="sxs-lookup"><span data-stu-id="bceed-126">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

