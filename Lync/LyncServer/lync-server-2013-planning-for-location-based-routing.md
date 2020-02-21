---
title: Lync Server 2013：规划基于位置的路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Location-Based Routing
ms:assetid: bb035924-6b52-4f0f-8e05-b76864fb9ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994068(v=OCS.15)
ms:contentKeyID: 51803979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef077c82a273a480977a21ca1e2e8b14043cae46
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="fa912-102">在 Lync Server 2013 中规划基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="fa912-102">Planning for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa912-103">_**上次修改的主题：** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="fa912-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="fa912-104">本主题中的信息适用于 Lync Server 2013 的累积更新：二月份2013。</span><span class="sxs-lookup"><span data-stu-id="fa912-104">The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>

<span data-ttu-id="fa912-105">基于位置的路由使您可以根据呼叫中各方的位置限制 VoIP 终结点和 PSTN 终结点之间的呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="fa912-105">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="fa912-106">基于位置的路由是 Lync Server 2013 企业语音基础结构的一部分。</span><span class="sxs-lookup"><span data-stu-id="fa912-106">Location-Based Routing is part of the Lync Server 2013 Enterprise Voice infrastructure.</span></span> <span data-ttu-id="fa912-107">基于位置的路由是呼叫管理功能，用于控制 Lync Server 2013 CU1 路由呼叫的方式。</span><span class="sxs-lookup"><span data-stu-id="fa912-107">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="fa912-108">根据 Lync 呼叫者的地理位置，它会强制执行呼叫授权规则，以确定是否可以将呼叫路由到 PBX 或 PSTN 终结点。</span><span class="sxs-lookup"><span data-stu-id="fa912-108">It enforces call authorization rules on whether calls can be routed to PBX or PSTN endpoints based on the Lync caller’s geographic location.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fa912-109">本部分内容</span><span class="sxs-lookup"><span data-stu-id="fa912-109">In This Section</span></span>

  - [<span data-ttu-id="fa912-110">Lync Server 2013 中基于位置的路由概述</span><span class="sxs-lookup"><span data-stu-id="fa912-110">Overview of Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing.md)

  - [<span data-ttu-id="fa912-111">Lync Server 2013 中基于位置的路由指南</span><span class="sxs-lookup"><span data-stu-id="fa912-111">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)

  - [<span data-ttu-id="fa912-112">Lync Server 2013 中基于位置的路由的方案</span><span class="sxs-lookup"><span data-stu-id="fa912-112">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)

  - [<span data-ttu-id="fa912-113">Lync Server 2013 中基于位置的路由的技术注意事项</span><span class="sxs-lookup"><span data-stu-id="fa912-113">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-technical-considerations-for-location-based-routing.md)

  - [<span data-ttu-id="fa912-114">在 Lync Server 2013 中对基于位置的路由的客户端和服务器支持</span><span class="sxs-lookup"><span data-stu-id="fa912-114">Client and server support for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-client-and-server-support-for-location-based-routing.md)

  - [<span data-ttu-id="fa912-115">Lync Server 2013 中基于位置的路由不支持的功能</span><span class="sxs-lookup"><span data-stu-id="fa912-115">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-capabilities-not-supported-by-location-based-routing.md)

  - [<span data-ttu-id="fa912-116">Lync Server 2013 中基于位置的路由的部署过程</span><span class="sxs-lookup"><span data-stu-id="fa912-116">Deployment process for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-location-based-routing.md)

  - [<span data-ttu-id="fa912-117">Lync Server 2013 中的会议的基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="fa912-117">Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-for-conferencing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fa912-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa912-118">See Also</span></span>


[<span data-ttu-id="fa912-119">在 Lync Server 2013 中规划企业语音</span><span class="sxs-lookup"><span data-stu-id="fa912-119">Planning for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

