---
title: Lync Server 2013：会议的 Location-Based 路由
description: Lync Server 2013： Location-Based 用于会议的路由。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location-Based Routing for conferencing
ms:assetid: e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362849(v=OCS.15)
ms:contentKeyID: 56335087
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 979c835e03bbf87c9a9bf86b030cb9a8f4e138e0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554848"
---
# <a name="location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="b609e-103">在 Lync Server 2013 中为会议 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="b609e-103">Location-Based Routing for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b609e-104">_**上次修改的主题：** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="b609e-104">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="b609e-105">Location-Based 路由可以根据呼叫中各方的位置限制 VoIP 终结点和 PSTN 终结点之间的呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="b609e-105">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="b609e-106">对于 Lync Server 2013 的累积更新2，可以在 Lync 会议上强制 Location-Based 路由规则 (即，阻止 PSTN 收费旁路的会议) 。</span><span class="sxs-lookup"><span data-stu-id="b609e-106">With Cumulative Update 2 of Lync Server 2013, Location-Based Routing rules can be enforced on Lync meetings (i.e. conferences) to prevent PSTN toll bypass.</span></span> <span data-ttu-id="b609e-107">应用程序监视活动会议，并根据参与用户的位置强制实施 Location-Based 路由限制。</span><span class="sxs-lookup"><span data-stu-id="b609e-107">The application monitors an active conference and enforces Location-Based Routing restrictions based on the location of users participating.</span></span> <span data-ttu-id="b609e-108">Location-Based 路由会议应用程序还允许将 Location-Based 路由限制强制实施到涉及 PSTN 终结点的咨询式转移。</span><span class="sxs-lookup"><span data-stu-id="b609e-108">The Location-Based Routing Conferencing application additionally enables the enforcement of Location-Based Routing restrictions to consultative transfers involving PSTN endpoints.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b609e-109">本部分内容</span><span class="sxs-lookup"><span data-stu-id="b609e-109">In This Section</span></span>

  - [<span data-ttu-id="b609e-110">Lync Server 2013 中的会议 Location-Based 路由概述</span><span class="sxs-lookup"><span data-stu-id="b609e-110">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="b609e-111">Lync Server 2013 中的基于位置的路由和咨询呼叫转移</span><span class="sxs-lookup"><span data-stu-id="b609e-111">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-and-consultative-call-transfers.md)

  - [<span data-ttu-id="b609e-112">在 Lync Server 2013 中为会议 Location-Based 路由的要求</span><span class="sxs-lookup"><span data-stu-id="b609e-112">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-requirements-for-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="b609e-113">在 Lync Server 2013 中为会议 Location-Based 的路由配置</span><span class="sxs-lookup"><span data-stu-id="b609e-113">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-configuration-of-location-based-routing-for-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

