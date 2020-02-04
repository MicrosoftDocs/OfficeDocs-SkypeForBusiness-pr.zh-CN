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
ms.openlocfilehash: 1bcdb0d30bccfe628fd02861d257d79268046b77
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="simultaneous-ringing-in-lync-server-2013"></a><span data-ttu-id="927b4-102">Lync Server 2013 中的同时响铃</span><span class="sxs-lookup"><span data-stu-id="927b4-102">Simultaneous ringing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="927b4-103">_**主题上次修改时间：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="927b4-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="927b4-104">当被呼叫方启用同时震铃时，基于位置的路由会分析呼叫方的位置和被呼叫方的终结点，以确定是否应路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="927b4-104">When the called party has simultaneous ringing enabled, Location-Based Routing analyzes the location of the calling party and the endpoints of the called parties to determine whether the call should be routed.</span></span>

<span data-ttu-id="927b4-105">下表说明配置了同时响铃的用户，同时响铃目标是位于相同网络站点中的用户、位于不同网络站点中的用户或者位于未知网络站点中的用户。</span><span class="sxs-lookup"><span data-stu-id="927b4-105">The following table illustrates a user configured with simultaneous ringing, and the simultaneous ringing target is a user in the same network site, in a different network site, or in an unknown network site.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="927b4-106">传入 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="927b4-106">Incoming PSTN call for</span></span></th>
<th><span data-ttu-id="927b4-107">位于与被呼叫者相同的网络站点中</span><span class="sxs-lookup"><span data-stu-id="927b4-107">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="927b4-108">位于与被呼叫者不同的网络站点中</span><span class="sxs-lookup"><span data-stu-id="927b4-108">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="927b4-109">位于未知网络网站中，或者未启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="927b4-109">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="927b4-110">Lync 用户</span><span class="sxs-lookup"><span data-stu-id="927b4-110">Lync user</span></span></p></td>
<td><p><span data-ttu-id="927b4-111">允许同时响铃</span><span class="sxs-lookup"><span data-stu-id="927b4-111">Simultaneous ring allowed</span></span></p></td>
<td><p><span data-ttu-id="927b4-112">不允许同时响铃</span><span class="sxs-lookup"><span data-stu-id="927b4-112">Simultaneous ring not allowed</span></span></p></td>
<td><p><span data-ttu-id="927b4-113">不允许同时响铃</span><span class="sxs-lookup"><span data-stu-id="927b4-113">Simultaneous ring not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="927b4-114">下表说明了来自同一网络站点、不同网络站点或来自未知网络站点的 Lync 用户（即 Lync 呼叫者）的呼叫。</span><span class="sxs-lookup"><span data-stu-id="927b4-114">The following table illustrates a call from a Lync user (i.e. Lync caller) in the same network site, in a different network site, or from an unknown network site.</span></span> <span data-ttu-id="927b4-115">被呼叫者将 PSTN 终结点（如移动电话）配置为同时响铃目标。</span><span class="sxs-lookup"><span data-stu-id="927b4-115">The callee has a PSTN endpoint (i.e. cellphone) configured as a simultaneous ring target.</span></span> <span data-ttu-id="927b4-116">在此方案中，基于位置的路由将确定是否应将呼叫路由到被呼叫方的同时环目标（即手机）。</span><span class="sxs-lookup"><span data-stu-id="927b4-116">In this scenario, Location-Based Routing will determine whether the call should be routed to the simultaneous ring target (i.e. cellphone) of the callee or not.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="927b4-117">同时响铃目标</span><span class="sxs-lookup"><span data-stu-id="927b4-117">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="927b4-118">位于与被呼叫者相同的网络站点中</span><span class="sxs-lookup"><span data-stu-id="927b4-118">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="927b4-119">位于与被呼叫者不同的网络站点中</span><span class="sxs-lookup"><span data-stu-id="927b4-119">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="927b4-120">位于未知网络网站中，或者未启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="927b4-120">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="927b4-121">PSTN 终结点</span><span class="sxs-lookup"><span data-stu-id="927b4-121">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="927b4-122">允许通过呼叫者的站点语音路由策略同时响铃</span><span class="sxs-lookup"><span data-stu-id="927b4-122">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="927b4-123">允许通过呼叫者的站点语音路由策略同时响铃</span><span class="sxs-lookup"><span data-stu-id="927b4-123">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="927b4-124">允许通过呼叫者的语音策略向未启用基于位置的路由的中继同时响铃</span><span class="sxs-lookup"><span data-stu-id="927b4-124">Simultaneous ring allowed through the caller’s voice policy to trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="927b4-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="927b4-125">See Also</span></span>


[<span data-ttu-id="927b4-126">Lync Server 2013 中基于位置的路由的方案</span><span class="sxs-lookup"><span data-stu-id="927b4-126">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

