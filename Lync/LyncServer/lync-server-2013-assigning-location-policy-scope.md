---
title: Lync Server 2013：分配位置策略作用域
description: Lync Server 2013：分配位置策略作用域。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning location policy scope
ms:assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205360(v=OCS.15)
ms:contentKeyID: 48185734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f6c46150241b0b224e8005556c0f2f594d8bce5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563378"
---
# <a name="assigning-location-policy-scope-in-lync-server-2013"></a><span data-ttu-id="37a1c-103">在 Lync Server 2013 中分配位置策略作用域</span><span class="sxs-lookup"><span data-stu-id="37a1c-103">Assigning location policy scope in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37a1c-104">_**上次修改的主题：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="37a1c-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="37a1c-105">与其他 Lync Server 策略一样，可在多个作用域级别分配位置策略：全局、站点和用户。</span><span class="sxs-lookup"><span data-stu-id="37a1c-105">As with other Lync Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="37a1c-106">但是，用户级位置策略的作用与其他 Lync Server 策略的行为略有不同。</span><span class="sxs-lookup"><span data-stu-id="37a1c-106">However, the scope of user-level location policies behaves a bit differently than with other Lync Server policies.</span></span> <span data-ttu-id="37a1c-107">每用户位置策略不仅可应用于终结点对象 (例如用户和公用区域电话联系人对象) ，它们也可应用于 Lync Server 网络站点。</span><span class="sxs-lookup"><span data-stu-id="37a1c-107">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Lync Server network sites.</span></span> <span data-ttu-id="37a1c-108">网络站点是与地理位置关联的客户端子网的分组（但是不一定全部都为整个中央站点或分支站点中的子网）。</span><span class="sxs-lookup"><span data-stu-id="37a1c-108">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="37a1c-109">任何连接到网络站点子网的客户端都自动拾取分配给该网络站点的位置策略。</span><span class="sxs-lookup"><span data-stu-id="37a1c-109">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="37a1c-110">在将用户级别的位置策略分配给用户和网络站点的情况下，基于网络站点的位置策略将覆盖任何每用户策略设置。</span><span class="sxs-lookup"><span data-stu-id="37a1c-110">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>

<span data-ttu-id="37a1c-111">每个网络站点都有为其分配的位置策略，而且每个策略都有为其分配的不同 PSTN 用途、通知 URI 和会议 URI 值。</span><span class="sxs-lookup"><span data-stu-id="37a1c-111">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="37a1c-112">此特殊策略作用域行为的原因是，当某个用户驻留在某个 office 网站上的某个池访问另一个网站并需要进行紧急呼叫时，无论用户分配到哪个池或站点，都将应用适用于该网络网站的 E9-1-1 呼叫路由设置。</span><span class="sxs-lookup"><span data-stu-id="37a1c-112">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

