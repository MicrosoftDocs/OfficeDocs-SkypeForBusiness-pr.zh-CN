---
title: 'Lync Server 2013: 针对会议的基于位置的路由'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Location-Based Routing for conferencing
ms:assetid: e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362849(v=OCS.15)
ms:contentKeyID: 56335087
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ee4c8f996315ede0fd0f7ccd789a73cad25c4f3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="1ef08-102">Lync Server 2013 中的会议基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="1ef08-102">Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ef08-103">_**主题上次修改时间:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="1ef08-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="1ef08-104">基于位置的路由使您能够根据呼叫中各方的位置限制 VoIP 终结点和 PSTN 终结点之间的通话路由。</span><span class="sxs-lookup"><span data-stu-id="1ef08-104">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="1ef08-105">使用 Lync Server 2013 的累积更新 2, 基于位置的路由规则可在 Lync 会议 (即会议) 上强制实施, 以防止 PSTN 免绕过。</span><span class="sxs-lookup"><span data-stu-id="1ef08-105">With Cumulative Update 2 of Lync Server 2013, Location-Based Routing rules can be enforced on Lync meetings (i.e. conferences) to prevent PSTN toll bypass.</span></span> <span data-ttu-id="1ef08-106">应用程序监视活动会议, 并根据参与用户的位置强制执行基于位置的路由限制。</span><span class="sxs-lookup"><span data-stu-id="1ef08-106">The application monitors an active conference and enforces Location-Based Routing restrictions based on the location of users participating.</span></span> <span data-ttu-id="1ef08-107">基于位置的路由会议应用程序还支持将基于位置的路由限制强制转换为涉及 PSTN 终结点的咨询式转移。</span><span class="sxs-lookup"><span data-stu-id="1ef08-107">The Location-Based Routing Conferencing application additionally enables the enforcement of Location-Based Routing restrictions to consultative transfers involving PSTN endpoints.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1ef08-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="1ef08-108">In This Section</span></span>

  - [<span data-ttu-id="1ef08-109">Lync Server 2013 中的会议基于位置的路由概述</span><span class="sxs-lookup"><span data-stu-id="1ef08-109">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="1ef08-110">Lync Server 2013 中基于位置的路由和咨询式呼叫转移</span><span class="sxs-lookup"><span data-stu-id="1ef08-110">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-and-consultative-call-transfers.md)

  - [<span data-ttu-id="1ef08-111">Lync Server 2013 中基于位置的会议路由的要求</span><span class="sxs-lookup"><span data-stu-id="1ef08-111">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-requirements-for-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="1ef08-112">Lync Server 2013 中会议的基于位置的路由的配置</span><span class="sxs-lookup"><span data-stu-id="1ef08-112">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-configuration-of-location-based-routing-for-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

