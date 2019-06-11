---
title: Lync Server 2013：传出呼叫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Outgoing calls
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994049(v=OCS.15)
ms:contentKeyID: 51803960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2ccd095cfe27f173ff0fe7ac0dac92ca51a7c1d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="outgoing-calls-in-lync-server-2013"></a><span data-ttu-id="23bab-102">Lync Server 2013 中的传出呼叫</span><span class="sxs-lookup"><span data-stu-id="23bab-102">Outgoing calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23bab-103">_**主题上次修改时间:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="23bab-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="23bab-104">对启用了基于位置的路由的用户的出站呼叫的路由受用户终结点的网络位置的影响。</span><span class="sxs-lookup"><span data-stu-id="23bab-104">The routing of outbound calls of users enabled for Location-Based Routing is affected by the network location of the user’s endpoint.</span></span> <span data-ttu-id="23bab-105">下表说明了基于位置的路由如何影响出站呼叫路由, 具体取决于呼叫者终结点的位置。</span><span class="sxs-lookup"><span data-stu-id="23bab-105">The following table illustrates how Location-Based Routing affects the routing of outbound calls depending on the location of the caller’s endpoint.</span></span>

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a><span data-ttu-id="23bab-106">向 PSTN 发出出站呼叫的呼叫者</span><span class="sxs-lookup"><span data-stu-id="23bab-106">Caller placing an outbound call to the PSTN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="23bab-107">位于启用了基于位置的路由的网络站点中的用户终结点</span><span class="sxs-lookup"><span data-stu-id="23bab-107">User endpoint located in a network site enabled for Location-Based Routing</span></span></th>
<th><span data-ttu-id="23bab-108">位于未知网络站点或者未启用基于位置的路由的网络站点中的用户终结点</span><span class="sxs-lookup"><span data-stu-id="23bab-108">User endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23bab-109">出站呼叫授权</span><span class="sxs-lookup"><span data-stu-id="23bab-109">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="23bab-110">基于用户的语音策略授权呼叫</span><span class="sxs-lookup"><span data-stu-id="23bab-110">Call is authorized based on user’s voice policy</span></span></p></td>
<td><p><span data-ttu-id="23bab-111">基于用户的语音策略授权呼叫</span><span class="sxs-lookup"><span data-stu-id="23bab-111">Call is authorized based on user’s voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23bab-112">出站呼叫路由</span><span class="sxs-lookup"><span data-stu-id="23bab-112">Routing of outbound call</span></span></p></td>
<td><p><span data-ttu-id="23bab-113">根据网络站点的语音路由策略路由呼叫</span><span class="sxs-lookup"><span data-stu-id="23bab-113">Call is routed according to the network site’s voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="23bab-114">根据用户的语音策略仅通过未启用基于位置的路由的中继路由呼叫（如果可用）</span><span class="sxs-lookup"><span data-stu-id="23bab-114">Call is routed according to user’s voice policy and only through trunks not enabled for Location-Based Routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="23bab-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23bab-115">See Also</span></span>


[<span data-ttu-id="23bab-116">Lync Server 2013 中基于位置的路由的方案</span><span class="sxs-lookup"><span data-stu-id="23bab-116">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

