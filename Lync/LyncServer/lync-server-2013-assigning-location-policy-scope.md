---
title: Lync Server 2013：分配位置策略范围
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
ms.openlocfilehash: 395b8a4271338231b4c2c1927f7e40fb21a1cb14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734022"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-location-policy-scope-in-lync-server-2013"></a><span data-ttu-id="ff121-102">在 Lync Server 2013 中分配位置策略范围</span><span class="sxs-lookup"><span data-stu-id="ff121-102">Assigning location policy scope in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff121-103">_**主题上次修改时间：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="ff121-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="ff121-104">与其他 Lync 服务器策略一样，可以在多个作用域级别分配位置策略：全局、网站和用户。</span><span class="sxs-lookup"><span data-stu-id="ff121-104">As with other Lync Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="ff121-105">但是，用户级位置策略的作用与其他 Lync 服务器策略的行为略有不同。</span><span class="sxs-lookup"><span data-stu-id="ff121-105">However, the scope of user-level location policies behaves a bit differently than with other Lync Server policies.</span></span> <span data-ttu-id="ff121-106">每个用户的位置策略不仅可以应用于终结点对象（如用户和常用的区域电话联系人对象），也可以应用于 Lync Server 网络站点。</span><span class="sxs-lookup"><span data-stu-id="ff121-106">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Lync Server network sites.</span></span> <span data-ttu-id="ff121-107">网络站点是地理位置关联的客户端子网的分组（但可能不需要所有子网位于一个中央站点或分支站点）。</span><span class="sxs-lookup"><span data-stu-id="ff121-107">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="ff121-108">连接到一个网络站点的子网的所有客户端将自动挑选分配给该网络站点的位置策略。</span><span class="sxs-lookup"><span data-stu-id="ff121-108">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="ff121-109">在将用户级别的位置策略分配给一个用户和一个网络站点的情况下，基于网络站点的位置策略将覆盖每用户策略设置。</span><span class="sxs-lookup"><span data-stu-id="ff121-109">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>

<span data-ttu-id="ff121-110">每个网络站点均分配有一个位置策略，并且每个策略均分配有不同的 PSTN 用法、通知 URI 和会议 URI 值。</span><span class="sxs-lookup"><span data-stu-id="ff121-110">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ff121-111">此特定策略作用域行为的原因是当驻留在 office 网站的池中的用户访问另一个站点并发出紧急呼叫时，无论该用户分配到的池或站点如何，都将应用与该网络站点对应的 E9-1-1 呼叫路由设置。</span><span class="sxs-lookup"><span data-stu-id="ff121-111">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

