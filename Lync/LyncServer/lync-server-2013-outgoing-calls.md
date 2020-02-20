---
title: Lync Server 2013：传出呼叫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Outgoing calls
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994049(v=OCS.15)
ms:contentKeyID: 51803960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5626e5e60a72967c84a79b6ec9aca818d8d62800
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="outgoing-calls-in-lync-server-2013"></a><span data-ttu-id="da8f0-102">Lync Server 2013 中的传出呼叫</span><span class="sxs-lookup"><span data-stu-id="da8f0-102">Outgoing calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da8f0-103">_**上次修改的主题：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="da8f0-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="da8f0-104">对启用了基于位置的路由的用户的出站呼叫的路由受用户终结点的网络位置的影响。</span><span class="sxs-lookup"><span data-stu-id="da8f0-104">The routing of outbound calls of users enabled for Location-Based Routing is affected by the network location of the user’s endpoint.</span></span> <span data-ttu-id="da8f0-105">下表说明了基于位置的路由如何影响出站呼叫的路由，具体取决于呼叫者终结点的位置。</span><span class="sxs-lookup"><span data-stu-id="da8f0-105">The following table illustrates how Location-Based Routing affects the routing of outbound calls depending on the location of the caller’s endpoint.</span></span>

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a><span data-ttu-id="da8f0-106">向 PSTN 发出出站呼叫的呼叫者</span><span class="sxs-lookup"><span data-stu-id="da8f0-106">Caller placing an outbound call to the PSTN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="da8f0-107">位于启用了基于位置的路由的网络站点中的用户终结点</span><span class="sxs-lookup"><span data-stu-id="da8f0-107">User endpoint located in a network site enabled for Location-Based Routing</span></span></th>
<th><span data-ttu-id="da8f0-108">用户终结点位于未知网络站点中，或未启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="da8f0-108">User endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da8f0-109">出站呼叫的授权</span><span class="sxs-lookup"><span data-stu-id="da8f0-109">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="da8f0-110">根据用户的语音策略对呼叫进行授权</span><span class="sxs-lookup"><span data-stu-id="da8f0-110">Call is authorized based on user’s voice policy</span></span></p></td>
<td><p><span data-ttu-id="da8f0-111">根据用户的语音策略对呼叫进行授权</span><span class="sxs-lookup"><span data-stu-id="da8f0-111">Call is authorized based on user’s voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da8f0-112">出站呼叫的路由</span><span class="sxs-lookup"><span data-stu-id="da8f0-112">Routing of outbound call</span></span></p></td>
<td><p><span data-ttu-id="da8f0-113">根据网络站点的语音路由策略路由呼叫</span><span class="sxs-lookup"><span data-stu-id="da8f0-113">Call is routed according to the network site’s voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="da8f0-114">呼叫是根据用户的语音策略路由的，并且只能通过中继启用基于位置的路由（如果可用）</span><span class="sxs-lookup"><span data-stu-id="da8f0-114">Call is routed according to user’s voice policy and only through trunks not enabled for Location-Based Routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="da8f0-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da8f0-115">See Also</span></span>


[<span data-ttu-id="da8f0-116">Lync Server 2013 中基于位置的路由的方案</span><span class="sxs-lookup"><span data-stu-id="da8f0-116">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

