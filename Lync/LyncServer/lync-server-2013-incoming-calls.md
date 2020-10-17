---
title: Lync Server 2013：传入呼叫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Incoming calls
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994038(v=OCS.15)
ms:contentKeyID: 51803948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05147e469ce120663992e5ae7b8a3ee59acaf78c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526609"
---
# <a name="incoming-calls-in-lync-server-2013"></a><span data-ttu-id="036a6-102">Lync Server 2013 中的传入呼叫</span><span class="sxs-lookup"><span data-stu-id="036a6-102">Incoming calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="036a6-103">_**上次修改的主题：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="036a6-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="036a6-104">为 Location-Based 路由启用的用户传入呼叫的路由取决于用户终结点的位置。</span><span class="sxs-lookup"><span data-stu-id="036a6-104">The routing of incoming calls to users enabled for Location-Based Routing depends on the location of the user’s endpoint.</span></span> <span data-ttu-id="036a6-105">传入呼叫的路由通过以下方式受到影响。</span><span class="sxs-lookup"><span data-stu-id="036a6-105">The routing of incoming calls is affected in the following way.</span></span> <span data-ttu-id="036a6-106">如果用户对位于启用了 Location-Based 路由网络站点中的终结点的传入呼叫，并且终结点位于与 PSTN 网关相同的网络站点中，则将路由该呼叫。</span><span class="sxs-lookup"><span data-stu-id="036a6-106">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in the same network site as the PSTN gateway, the call will be routed.</span></span> <span data-ttu-id="036a6-107">如果用户对位于启用了 Location-Based 路由的网络站点中的终结点的传入呼叫，并且终结点位于与 PSTN 网关不同的网络站点中，则不会路由该呼叫。</span><span class="sxs-lookup"><span data-stu-id="036a6-107">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in a different network site than the PSTN gateway, the call will not be routed.</span></span> <span data-ttu-id="036a6-108">当用户没有与传入呼叫来自的 PSTN 网关位于同一网络站点中的终结点时，传入呼叫将直接路由到用户的语音邮件，并且未接来电通知将发送给被叫方。</span><span class="sxs-lookup"><span data-stu-id="036a6-108">When a user has no endpoints located in the same network site as the PSTN gateway where the incoming call is originating from, the incoming call will be routed directly to the user’s voicemail and a missed call notification will be sent to the called party.</span></span>

<span data-ttu-id="036a6-109">为 Location-Based 路由启用的用户的呼叫转接设置将继续强制实施，但转发的呼叫将受到用户 Location-Based 路由限制的约束。</span><span class="sxs-lookup"><span data-stu-id="036a6-109">The call forwarding settings of a user that is enabled for Location-Based Routing will continue to be enforced, however, calls forwarded will be subject to Location-Based Routing restrictions of the user.</span></span>

<span data-ttu-id="036a6-110">下表说明了 Location-Based 路由如何影响入站呼叫的路由，具体取决于被叫方的终结点的位置。</span><span class="sxs-lookup"><span data-stu-id="036a6-110">The following table illustrates how Location-Based Routing affects the routing of inbound calls depending on the location of the callee’s endpoint.</span></span> <span data-ttu-id="036a6-111">PSTN 网关的网络站点已启用 Location-Based 路由，Location-Based 路由仅允许将 PSTN 呼叫路由到同一网络站点中的终结点。</span><span class="sxs-lookup"><span data-stu-id="036a6-111">The network site of the PSTN gateway is enabled for Location-Based Routing, and Location-Based Routing only permits routing of PSTN calls to endpoints within the same network site.</span></span>

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a><span data-ttu-id="036a6-112">被呼叫者从 PSTN 接收入站呼叫</span><span class="sxs-lookup"><span data-stu-id="036a6-112">Callee receiving an inbound call from the PSTN</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="036a6-113">被呼叫方的终结点位于与 PSTN 网关相同的网络站点中</span><span class="sxs-lookup"><span data-stu-id="036a6-113">Callee’s endpoint located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="036a6-114">被叫方的终结点不与 PSTN 网关位于同一网络站点中</span><span class="sxs-lookup"><span data-stu-id="036a6-114">Callee’s endpoint not located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="036a6-115">被呼叫者的终结点位于未知网络站点中，或者未启用 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="036a6-115">Callee’s endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="036a6-116">传入 PSTN 呼叫的路由</span><span class="sxs-lookup"><span data-stu-id="036a6-116">Routing of inbound PSTN call</span></span></p></td>
<td><p><span data-ttu-id="036a6-117">传入呼叫路由到被呼叫者的终结点</span><span class="sxs-lookup"><span data-stu-id="036a6-117">Incoming call is routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="036a6-118">传入呼叫未路由到被呼叫者的终结点</span><span class="sxs-lookup"><span data-stu-id="036a6-118">Incoming call is not routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="036a6-119">传入呼叫未路由到被呼叫者的终结点</span><span class="sxs-lookup"><span data-stu-id="036a6-119">Incoming call is not routed to callee’s endpoints</span></span></p></td>
</tr>
</tbody>
</table>

  

<div>

## <a name="see-also"></a><span data-ttu-id="036a6-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="036a6-120">See Also</span></span>


[<span data-ttu-id="036a6-121">Lync Server 2013 中 Location-Based 路由的方案</span><span class="sxs-lookup"><span data-stu-id="036a6-121">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

