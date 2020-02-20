---
title: Lync Server 2013：同时响铃
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Simultaneous ringing
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994079(v=OCS.15)
ms:contentKeyID: 51803990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c05122bb2d6f8f0c9b21aeb12c6e889e3f98750
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142738"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="simultaneous-ringing-in-lync-server-2013"></a><span data-ttu-id="4460a-102">Lync Server 2013 中的同时响铃</span><span class="sxs-lookup"><span data-stu-id="4460a-102">Simultaneous ringing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4460a-103">_**上次修改的主题：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="4460a-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="4460a-104">当呼叫方启用同时响铃时，基于位置的路由将分析呼叫方的位置和被叫方的终结点，以确定是否应路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="4460a-104">When the called party has simultaneous ringing enabled, Location-Based Routing analyzes the location of the calling party and the endpoints of the called parties to determine whether the call should be routed.</span></span>

<span data-ttu-id="4460a-105">下表说明了配置了同时响铃的用户，同时响铃目标是同一网络站点、不同网络站点或未知网络站点中的用户。</span><span class="sxs-lookup"><span data-stu-id="4460a-105">The following table illustrates a user configured with simultaneous ringing, and the simultaneous ringing target is a user in the same network site, in a different network site, or in an unknown network site.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4460a-106">的传入 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="4460a-106">Incoming PSTN call for</span></span></th>
<th><span data-ttu-id="4460a-107">位于与被呼叫方相同的网络站点中</span><span class="sxs-lookup"><span data-stu-id="4460a-107">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="4460a-108">位于与被呼叫者不同的网络站点中</span><span class="sxs-lookup"><span data-stu-id="4460a-108">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="4460a-109">位于未知网络站点中，或未启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="4460a-109">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4460a-110">Lync 用户</span><span class="sxs-lookup"><span data-stu-id="4460a-110">Lync user</span></span></p></td>
<td><p><span data-ttu-id="4460a-111">允许同时振铃</span><span class="sxs-lookup"><span data-stu-id="4460a-111">Simultaneous ring allowed</span></span></p></td>
<td><p><span data-ttu-id="4460a-112">不允许同时振铃</span><span class="sxs-lookup"><span data-stu-id="4460a-112">Simultaneous ring not allowed</span></span></p></td>
<td><p><span data-ttu-id="4460a-113">不允许同时振铃</span><span class="sxs-lookup"><span data-stu-id="4460a-113">Simultaneous ring not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="4460a-114">下表说明了来自同一网络站点、不同网络站点或未知网络站点中 Lync 用户（即 Lync 呼叫者）的呼叫。</span><span class="sxs-lookup"><span data-stu-id="4460a-114">The following table illustrates a call from a Lync user (i.e. Lync caller) in the same network site, in a different network site, or from an unknown network site.</span></span> <span data-ttu-id="4460a-115">被叫方具有配置为同时振铃目标的 PSTN 终结点（即手机）。</span><span class="sxs-lookup"><span data-stu-id="4460a-115">The callee has a PSTN endpoint (i.e. cellphone) configured as a simultaneous ring target.</span></span> <span data-ttu-id="4460a-116">在这种情况下，基于位置的路由将确定是否应将呼叫路由到被呼叫方的同时环目标（即手机）。</span><span class="sxs-lookup"><span data-stu-id="4460a-116">In this scenario, Location-Based Routing will determine whether the call should be routed to the simultaneous ring target (i.e. cellphone) of the callee or not.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4460a-117">同时振铃目标</span><span class="sxs-lookup"><span data-stu-id="4460a-117">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="4460a-118">位于与被呼叫方相同的网络站点中</span><span class="sxs-lookup"><span data-stu-id="4460a-118">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="4460a-119">位于与被呼叫者不同的网络站点中</span><span class="sxs-lookup"><span data-stu-id="4460a-119">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="4460a-120">位于未知网络站点中，或未启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="4460a-120">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4460a-121">PSTN 终结点</span><span class="sxs-lookup"><span data-stu-id="4460a-121">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="4460a-122">通过呼叫者的站点语音路由策略允许同时响铃</span><span class="sxs-lookup"><span data-stu-id="4460a-122">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="4460a-123">通过呼叫者的站点语音路由策略允许同时响铃</span><span class="sxs-lookup"><span data-stu-id="4460a-123">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="4460a-124">允许通过呼叫者的语音策略同时振铃到未启用基于位置的路由的中继</span><span class="sxs-lookup"><span data-stu-id="4460a-124">Simultaneous ring allowed through the caller’s voice policy to trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="4460a-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4460a-125">See Also</span></span>


[<span data-ttu-id="4460a-126">Lync Server 2013 中基于位置的路由的方案</span><span class="sxs-lookup"><span data-stu-id="4460a-126">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

