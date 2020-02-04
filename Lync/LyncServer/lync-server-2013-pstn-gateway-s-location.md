---
title: Lync Server 2013：PSTN 网关的位置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway's location
ms:assetid: 49693a35-fad3-49ee-a71e-c7e4537b79aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994031(v=OCS.15)
ms:contentKeyID: 51803940
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5d15589f37b18015f91e3717e19415d5ade6b6c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateways-location-in-lync-server-2013"></a><span data-ttu-id="d2dd4-102">Lync Server 2013 中 PSTN 网关的位置</span><span class="sxs-lookup"><span data-stu-id="d2dd4-102">PSTN gateway's location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2dd4-103">_**主题上次修改时间：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="d2dd4-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="d2dd4-104">通过 PSTN 网关和 Pbx 路由的通话可能需要基于位置的路由限制，具体取决于此类系统的位置。</span><span class="sxs-lookup"><span data-stu-id="d2dd4-104">Calls routed via PSTN gateways and PBXs might require Location-Based Routing restrictions depending on the location of such systems.</span></span> <span data-ttu-id="d2dd4-105">基于位置的路由可以按每个干线的粒度来启用。</span><span class="sxs-lookup"><span data-stu-id="d2dd4-105">Location-Based Routing can be enabled at the granularity on a per trunk basis.</span></span>

<span data-ttu-id="d2dd4-106">基于位置的路由在主干上启用时引入以下规则集：</span><span class="sxs-lookup"><span data-stu-id="d2dd4-106">Location-Based Routing introduces the following set of rules when enabled on a trunk:</span></span>

  - <span data-ttu-id="d2dd4-107">在每个主干基础上启用基于位置的路由时，在该主干上定义的规则将仅应用于通过该主干路由的呼叫。</span><span class="sxs-lookup"><span data-stu-id="d2dd4-107">When Location-Based Routing is enabled on a per trunk basis, the rules define on that trunk will be applied only to calls routed through that trunk.</span></span>

  - <span data-ttu-id="d2dd4-108">为了防止 PSTN tolls 绕过从网络站点（PSTN 网关所在的网络站点不同）的网络站点进行调用的位置，基于位置的路由引入了网络站点与给定主干的关联。</span><span class="sxs-lookup"><span data-stu-id="d2dd4-108">To prevent PSTN tolls bypass where calls originate from a network site different that the network site where the PSTN gateway is located, Location-Based Routing introduces the association of a network site to a given trunk.</span></span> <span data-ttu-id="d2dd4-109">这定义了允许呼叫路由到给定中继的网络站点。</span><span class="sxs-lookup"><span data-stu-id="d2dd4-109">This defines the network site that allows calls to be routed to a given trunk.</span></span>

<span data-ttu-id="d2dd4-110">可以通过以下两种方式为基于位置的路由启用中继：</span><span class="sxs-lookup"><span data-stu-id="d2dd4-110">Trunks can be enabled for Location-Based Routing in two ways:</span></span>

  - <span data-ttu-id="d2dd4-p103">为中继定义将呼叫发出到 PSTN 的 PSTN 网关。此类型的中继路由的传入呼叫只能路由到位于与中继相同的网络站点中的终结点。</span><span class="sxs-lookup"><span data-stu-id="d2dd4-p103">The trunk is defined for a PSTN gateway that egresses calls to the PSTN. Incoming calls routed by a trunk of this type will be routed only to endpoints located within the same network site as the trunk.</span></span>

  - <span data-ttu-id="d2dd4-113">主干是针对中介服务器对等方定义的，它不会向在静态位置（即 PBX 手机）中使用旧式电话的 PSTN 和服务用户传出呼叫。</span><span class="sxs-lookup"><span data-stu-id="d2dd4-113">The trunk is defined for a Mediation Server peer that doesn’t egress calls to the PSTN and services users with legacy phones in a static locations (i.e. PBX phones).</span></span> <span data-ttu-id="d2dd4-114">对于此特殊配置，此类型的中继路由的传入呼叫将视为来自与中继相同的网络站点。</span><span class="sxs-lookup"><span data-stu-id="d2dd4-114">For this particular configuration, all incoming calls routed by a trunk of this type will be considered to be originating from the same network site as the trunk.</span></span> <span data-ttu-id="d2dd4-115">来自 PBX 用户的呼叫将与与主干的同一网络站点中的 Lync 用户具有相同的基于位置的路由强制。</span><span class="sxs-lookup"><span data-stu-id="d2dd4-115">Calls from PBX users will have the same Location-Based Routing enforcement as Lync users who are located in the same network site as the trunk.</span></span> <span data-ttu-id="d2dd4-116">如果位于单独网络站点的两个 PBX 系统通过 Lync Server 连接，基于位置的路由将允许从一个网络站点中的一个 PBX 终结点路由到另一个网络站点中的另一个 PBX 终结点。</span><span class="sxs-lookup"><span data-stu-id="d2dd4-116">If two PBX systems located in separate network sites are connected through Lync Server, Location-Based Routing will allow routing from one PBX endpoint in one network site to another PBX endpoint in the other network site.</span></span> <span data-ttu-id="d2dd4-117">此方案不会被基于位置的路由阻止。</span><span class="sxs-lookup"><span data-stu-id="d2dd4-117">This scenario will not be blocked by Location-Based Routing.</span></span> <span data-ttu-id="d2dd4-118">除了此方案以及与同一位置的 Lync 用户类似的情况下，连接到具有此配置的中介服务器对等的终结点将能够在不将调用路由到 PSTN （i）的其他中介服务器对等上进行或接收呼叫。e. 连接到其他 PBX 的终结点，与中介服务器对等关联的网络站点无关。</span><span class="sxs-lookup"><span data-stu-id="d2dd4-118">In addition to this scenario and in a similar way as a Lync user in the same location, endpoints connected to a Mediation Server peer with this configuration will be able to make or receive calls to and from other Mediation Server peer that do not route calls to the PSTN (i.e. an endpoint connected to a different PBX) regardless of the network site to which the Mediation Server peer is associated.</span></span> <span data-ttu-id="d2dd4-119">所有入站呼叫、出站呼叫、呼叫转接和涉及 PSTN 终结点的转接将根据基于位置的路由，仅使用定义为本中介服务器对等的本地的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="d2dd4-119">All inbound calls, outbound calls, call transfers and call forwards involving PSTN endpoints will be subject to Location Based Routing to use only PSTN gateways that are defined as local to such Mediation Server peer.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d2dd4-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2dd4-120">See Also</span></span>


[<span data-ttu-id="d2dd4-121">Lync Server 2013 中基于位置的路由指南</span><span class="sxs-lookup"><span data-stu-id="d2dd4-121">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

