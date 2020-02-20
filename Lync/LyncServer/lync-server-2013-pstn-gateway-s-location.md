---
title: Lync Server 2013： PSTN 网关的位置
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
ms.openlocfilehash: ef9c58115349e8fedaf25d6f8bc4e1991b65a963
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152306"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="pstn-gateways-location-in-lync-server-2013"></a><span data-ttu-id="08ac8-102">Lync Server 2013 中的 PSTN 网关的位置</span><span class="sxs-lookup"><span data-stu-id="08ac8-102">PSTN gateway's location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08ac8-103">_**上次修改的主题：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="08ac8-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="08ac8-104">通过 PSTN 网关和 Pbx 路由的呼叫可能需要基于位置的路由限制，具体取决于此类系统的位置。</span><span class="sxs-lookup"><span data-stu-id="08ac8-104">Calls routed via PSTN gateways and PBXs might require Location-Based Routing restrictions depending on the location of such systems.</span></span> <span data-ttu-id="08ac8-105">可以基于每个中继的粒度启用基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="08ac8-105">Location-Based Routing can be enabled at the granularity on a per trunk basis.</span></span>

<span data-ttu-id="08ac8-106">基于位置的路由在中继上启用时引入了以下一组规则：</span><span class="sxs-lookup"><span data-stu-id="08ac8-106">Location-Based Routing introduces the following set of rules when enabled on a trunk:</span></span>

  - <span data-ttu-id="08ac8-107">在每个中继基础上启用基于位置的路由时，在该中继上定义的规则将仅应用于通过该中继路由的呼叫。</span><span class="sxs-lookup"><span data-stu-id="08ac8-107">When Location-Based Routing is enabled on a per trunk basis, the rules define on that trunk will be applied only to calls routed through that trunk.</span></span>

  - <span data-ttu-id="08ac8-108">为了防止 PSTN 费绕过 PSTN 网关所在的网络站点之外的网络站点进行呼叫，基于位置的路由引入了网络站点与给定中继的关联。</span><span class="sxs-lookup"><span data-stu-id="08ac8-108">To prevent PSTN tolls bypass where calls originate from a network site different that the network site where the PSTN gateway is located, Location-Based Routing introduces the association of a network site to a given trunk.</span></span> <span data-ttu-id="08ac8-109">这将定义允许呼叫路由到给定中继的网络站点。</span><span class="sxs-lookup"><span data-stu-id="08ac8-109">This defines the network site that allows calls to be routed to a given trunk.</span></span>

<span data-ttu-id="08ac8-110">可以通过两种方式为基于位置的路由启用中继：</span><span class="sxs-lookup"><span data-stu-id="08ac8-110">Trunks can be enabled for Location-Based Routing in two ways:</span></span>

  - <span data-ttu-id="08ac8-111">为发出对 PSTN 的呼叫的 PSTN 网关定义中继。</span><span class="sxs-lookup"><span data-stu-id="08ac8-111">The trunk is defined for a PSTN gateway that egresses calls to the PSTN.</span></span> <span data-ttu-id="08ac8-112">由这种类型的中继路由的传入呼叫将仅路由到与中继位于同一网络站点内的终结点。</span><span class="sxs-lookup"><span data-stu-id="08ac8-112">Incoming calls routed by a trunk of this type will be routed only to endpoints located within the same network site as the trunk.</span></span>

  - <span data-ttu-id="08ac8-113">中继是为中介服务器对等方定义的，它不会向 PSTN 和服务用户提供静态位置（即 PBX 电话）中的旧版电话的传出呼叫。</span><span class="sxs-lookup"><span data-stu-id="08ac8-113">The trunk is defined for a Mediation Server peer that doesn’t egress calls to the PSTN and services users with legacy phones in a static locations (i.e. PBX phones).</span></span> <span data-ttu-id="08ac8-114">对于此特定配置，由这种类型的中继路由的所有传入呼叫都将被视为来自与中继相同的网络站点。</span><span class="sxs-lookup"><span data-stu-id="08ac8-114">For this particular configuration, all incoming calls routed by a trunk of this type will be considered to be originating from the same network site as the trunk.</span></span> <span data-ttu-id="08ac8-115">来自 PBX 用户的呼叫将与与中继位于同一网络站点的 Lync 用户具有相同的基于位置的路由强制实施。</span><span class="sxs-lookup"><span data-stu-id="08ac8-115">Calls from PBX users will have the same Location-Based Routing enforcement as Lync users who are located in the same network site as the trunk.</span></span> <span data-ttu-id="08ac8-116">如果位于不同网络站点的两个 PBX 系统通过 Lync Server 连接，基于位置的路由将允许从一个网络站点中的一个 PBX 终结点路由到其他网络站点中的另一个 PBX 终结点。</span><span class="sxs-lookup"><span data-stu-id="08ac8-116">If two PBX systems located in separate network sites are connected through Lync Server, Location-Based Routing will allow routing from one PBX endpoint in one network site to another PBX endpoint in the other network site.</span></span> <span data-ttu-id="08ac8-117">此方案不会被基于位置的路由阻止。</span><span class="sxs-lookup"><span data-stu-id="08ac8-117">This scenario will not be blocked by Location-Based Routing.</span></span> <span data-ttu-id="08ac8-118">除了此方案和相同位置中的 Lync 用户的类似方式之外，与此配置连接到中介服务器对等方的终结点可以在不将呼叫路由到 PSTN （i）的其他中介服务器对等方发出或接收呼叫。e. 连接到不同 PBX 的终结点），而不管中介服务器对等端与之关联的网络站点。</span><span class="sxs-lookup"><span data-stu-id="08ac8-118">In addition to this scenario and in a similar way as a Lync user in the same location, endpoints connected to a Mediation Server peer with this configuration will be able to make or receive calls to and from other Mediation Server peer that do not route calls to the PSTN (i.e. an endpoint connected to a different PBX) regardless of the network site to which the Mediation Server peer is associated.</span></span> <span data-ttu-id="08ac8-119">涉及 PSTN 终结点的所有入站呼叫、出站呼叫、呼叫转移和呼叫转接将受基于位置的路由的制约，仅使用定义为此中介服务器对等的本地的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="08ac8-119">All inbound calls, outbound calls, call transfers and call forwards involving PSTN endpoints will be subject to Location Based Routing to use only PSTN gateways that are defined as local to such Mediation Server peer.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="08ac8-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08ac8-120">See Also</span></span>


[<span data-ttu-id="08ac8-121">Lync Server 2013 中基于位置的路由指南</span><span class="sxs-lookup"><span data-stu-id="08ac8-121">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

