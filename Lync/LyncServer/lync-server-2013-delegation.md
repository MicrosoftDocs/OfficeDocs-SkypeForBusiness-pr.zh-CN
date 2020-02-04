---
title: Lync Server 2013：委派
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegation
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994045(v=OCS.15)
ms:contentKeyID: 51803956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8da9568ae4cd613dcba0760fb4a8b20295fbb68d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739802"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegation-in-lync-server-2013"></a><span data-ttu-id="6f15b-102">Lync Server 2013 中的委派</span><span class="sxs-lookup"><span data-stu-id="6f15b-102">Delegation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f15b-103">_**主题上次修改时间：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="6f15b-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="6f15b-104">Lync 中的委派功能受基于位置的路由以下列方式受到影响：</span><span class="sxs-lookup"><span data-stu-id="6f15b-104">The delegation capabilities in Lync are affected by Location-Based Routing in the following manner:</span></span>

  - <span data-ttu-id="6f15b-105">当为基于位置的路由启用代理人代表经理呼叫时，代理人的语音政策将用于授权呼叫，代理人的网站语音路由策略将用于路由呼叫</span><span class="sxs-lookup"><span data-stu-id="6f15b-105">When a delegate enabled for Location-Based Routing places a call on behalf of a manager, the delegate’s voice policy is used to authorize the call and the delegate’s site voice routing policy will be used to route the call</span></span>

  - <span data-ttu-id="6f15b-106">对于打给经理的传入 PSTN 呼叫，适用于呼叫转接或同时响铃的相同规则将按照呼叫转接和同时响铃主题所述进行应用。</span><span class="sxs-lookup"><span data-stu-id="6f15b-106">For incoming PSTN calls to a manager, the same rules applicable for call forwarding or simultaneously ringing will apply as described in the Call transfers and forwarding and Simultaneous ringing topics.</span></span>

  - <span data-ttu-id="6f15b-107">当代理人将 PSTN 终结点设置为同时响铃目标时，对于打给经理的传入呼叫，与传入中继相关联的站点的语音路由策略将用于将呼叫路由到代理人的 PSTN 终结点。</span><span class="sxs-lookup"><span data-stu-id="6f15b-107">When a delegate sets a PSTN endpoint as a simultaneous ring target, for an incoming call to the manager, the voice routing policy of the site that is associated to the incoming trunk will be used to route the call to the delegate’s PSTN endpoint.</span></span>

  - <span data-ttu-id="6f15b-108">对于委派，通常建议经理及其关联的代理人位于相同网络站点中。</span><span class="sxs-lookup"><span data-stu-id="6f15b-108">For delegation, it’s recommended that the manager and his associated delegates to be usually located in the same network site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="6f15b-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f15b-109">See Also</span></span>


[<span data-ttu-id="6f15b-110">Lync Server 2013 中基于位置的路由的方案</span><span class="sxs-lookup"><span data-stu-id="6f15b-110">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

