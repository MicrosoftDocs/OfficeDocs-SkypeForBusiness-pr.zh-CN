---
title: Lync Server 2013：呼叫转移和呼叫转接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d5b0661cfaaef2e514f070260f44abc4ea00572
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a><span data-ttu-id="64109-102">Lync Server 2013 中的呼叫转移和呼叫转接</span><span class="sxs-lookup"><span data-stu-id="64109-102">Call transfers and call forwarding in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64109-103">_**主题上次修改时间:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="64109-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="64109-104">当涉及 PSTN 终结点时, 基于位置的路由会分析 calle 终结点的位置以及呼叫将被转移或转发到的终结点 (例如, 传输/转发目标)。</span><span class="sxs-lookup"><span data-stu-id="64109-104">When a PSTN endpoint is involved, Location-Based Routing analyzes the location of the calle’s endpoint and the endpoint where the call will be transferred or forwarded to (i.e. transfer/forward target).</span></span> <span data-ttu-id="64109-105">基于位置的路由确定是否应根据两个终结点的位置来转移或转发呼叫。</span><span class="sxs-lookup"><span data-stu-id="64109-105">Location-Based Routing determines whether the call should be transferred or forwarded depending on the location of both endpoints.</span></span>

<span data-ttu-id="64109-106">下表说明了使用 PSTN 终结点的呼叫中 Lync 用户的方案, 以及 Lync 用户将呼叫转移到另一个 Lync 用户。</span><span class="sxs-lookup"><span data-stu-id="64109-106">The following table illustrates the scenario of a Lync user in a call with a PSTN endpoint, and the Lync user transfers the call to another Lync user.</span></span> <span data-ttu-id="64109-107">根据 transferee 终结点的网络站点位置, 基于位置的路由会影响呼叫转移或转发的路由。</span><span class="sxs-lookup"><span data-stu-id="64109-107">Depending on the network site location of the transferee’s endpoint, Location-Based Routing affects the routing of the call transfer or forward.</span></span>

### <a name="initiating-call-transfer-or-forward"></a><span data-ttu-id="64109-108">发起呼叫转接</span><span class="sxs-lookup"><span data-stu-id="64109-108">Initiating call transfer or forward</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="64109-109">发起呼叫转接的用户</span><span class="sxs-lookup"><span data-stu-id="64109-109">User initiating the call transfer/forward</span></span></th>
<th><span data-ttu-id="64109-110">目标终结点位于与发起呼叫转接的用户相同的网络站点中</span><span class="sxs-lookup"><span data-stu-id="64109-110">Target endpoint is in same network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="64109-111">目标终结点位于与发起呼叫转接的用户不同的网络站点中</span><span class="sxs-lookup"><span data-stu-id="64109-111">Target endpoint is in different network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="64109-112">目标终结点位于未知的网络网站中, 或者没有为基于位置的路由启用网络网站</span><span class="sxs-lookup"><span data-stu-id="64109-112">Target endpoint is in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64109-113">Lync 用户</span><span class="sxs-lookup"><span data-stu-id="64109-113">Lync user</span></span></p></td>
<td><p><span data-ttu-id="64109-114">允许呼叫转接</span><span class="sxs-lookup"><span data-stu-id="64109-114">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="64109-115">不允许呼叫转接</span><span class="sxs-lookup"><span data-stu-id="64109-115">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="64109-116">不允许呼叫转接</span><span class="sxs-lookup"><span data-stu-id="64109-116">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="64109-117">例如: 使用 PSTN 终结点进行呼叫的 Lync 用户将呼叫转移到位于同一网络站点中的另一个 Lync 用户。</span><span class="sxs-lookup"><span data-stu-id="64109-117">For example: a Lync user in a call with a PSTN endpoint transfers the call to another Lync user that is in the same network site.</span></span> <span data-ttu-id="64109-118">在这种情况下，允许进行呼叫转接。</span><span class="sxs-lookup"><span data-stu-id="64109-118">In this case, the call transfer is allowed.</span></span>

<span data-ttu-id="64109-119">下表说明了使用另一个 Lync 用户的呼叫中 Lync 用户的方案, 其中一个用户将呼叫转移到 PSTN 终结点。</span><span class="sxs-lookup"><span data-stu-id="64109-119">The following table illustrates the scenario of a Lync user in a call with another Lync user, and one of the users transfers the call to a PSTN endpoint.</span></span> <span data-ttu-id="64109-120">根据呼叫转接至的用户的位置，表格详细介绍了基于位置的路由如何影响呼叫。</span><span class="sxs-lookup"><span data-stu-id="64109-120">Depending on the location of the user the call is being transferred to, the table details how Location-Based Routing affects the call.</span></span>

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a><span data-ttu-id="64109-121">呼叫转接至 PSTN 终结点</span><span class="sxs-lookup"><span data-stu-id="64109-121">Call transfer or forward to PSTN endpoint</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="64109-122">呼叫转接终结点目标</span><span class="sxs-lookup"><span data-stu-id="64109-122">Call transfer/forward endpoint target</span></span></th>
<th><span data-ttu-id="64109-123">同一网络网站中的 Lync 用户</span><span class="sxs-lookup"><span data-stu-id="64109-123">Lync users in same network site</span></span></th>
<th><span data-ttu-id="64109-124">不同网络站点中的 Lync 用户</span><span class="sxs-lookup"><span data-stu-id="64109-124">Lync users in different network sites</span></span></th>
<th><span data-ttu-id="64109-125">在未知网络网站或网络网站中的一个或两个 Lync 用户未启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="64109-125">One or both Lync users in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64109-126">PSTN 终结点</span><span class="sxs-lookup"><span data-stu-id="64109-126">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="64109-127">转接用户的站点语音路由策略允许呼叫转接</span><span class="sxs-lookup"><span data-stu-id="64109-127">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="64109-128">转接用户的站点语音路由策略允许呼叫转接</span><span class="sxs-lookup"><span data-stu-id="64109-128">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="64109-129">转接用户的语音策略仅允许通过未启用基于位置的路由的中继进行呼叫转接</span><span class="sxs-lookup"><span data-stu-id="64109-129">Call forward or transfer allowed by the transferred user’s voice policy only through trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="64109-130">例如: 与同一网络站点中的另一个 Lync 用户进行的呼叫中的 Lync 用户将呼叫转移到 PSTN 终结点, 并允许呼叫转移。</span><span class="sxs-lookup"><span data-stu-id="64109-130">For example: a Lync user in a call with another Lync user that is in the same network site transfers the call to a PSTN endpoint and the call transfer is allowed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="64109-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64109-131">See Also</span></span>


[<span data-ttu-id="64109-132">Lync Server 2013 中基于位置的路由的方案</span><span class="sxs-lookup"><span data-stu-id="64109-132">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

