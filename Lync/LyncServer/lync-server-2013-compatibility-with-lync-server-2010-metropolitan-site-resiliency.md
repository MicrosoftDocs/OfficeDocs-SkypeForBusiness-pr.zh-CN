---
title: Lync Server 2013 兼容性与 Lync Server 2010 都市站点恢复能力
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2010 metropolitan site resiliency
ms:assetid: 18673ff6-b664-4a57-a89b-cbda8b129e6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204715(v=OCS.15)
ms:contentKeyID: 48183526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3079f05d9860fd659d19df7b71ee633c0cea3fe2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837528"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2010-metropolitan-site-resiliency"></a><span data-ttu-id="2886e-102">Lync Server 2010 都市站点恢复能力</span><span class="sxs-lookup"><span data-stu-id="2886e-102">Lync Server 2010 metropolitan site resiliency</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2886e-103">_**主题上次修改时间:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="2886e-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="2886e-104">Lync Server 2013 不支持 Lync Server 2010 支持的城域网网站复原解决方案。</span><span class="sxs-lookup"><span data-stu-id="2886e-104">The metropolitan site resiliency solution supported for Lync Server 2010 is not supported for Lync Server 2013.</span></span> <span data-ttu-id="2886e-105">此解决方案涉及跨同一大都市区域内的两个数据中心跨越单个前端池。</span><span class="sxs-lookup"><span data-stu-id="2886e-105">This solution involved spanning a single Front End pool across two data centers in the same metropolitan area.</span></span>

<span data-ttu-id="2886e-106">大都市版站点恢复解决方案旨在从丢失完整数据中心中恢复。</span><span class="sxs-lookup"><span data-stu-id="2886e-106">The metropolitan site resiliency solution was designed to recover from the loss of a full datacenter.</span></span> <span data-ttu-id="2886e-107">当你跨两个数据中心跨越你的池时, 通常会在一个数据中心中放置一半的前端, 另一半位于第二个数据中心。</span><span class="sxs-lookup"><span data-stu-id="2886e-107">When you span your pool across two datacenters, you typically put half of your front ends in one datacenter and the other half in the second datacenter.</span></span> <span data-ttu-id="2886e-108">如果丢失整个数据中心, 您将丢失一半的前端服务器。</span><span class="sxs-lookup"><span data-stu-id="2886e-108">If you lose an entire datacenter, you have lost half of your Front End Servers.</span></span> <span data-ttu-id="2886e-109">在 Lync Server 2013 中, 这可能会导致前端池的新分布式系统模型出现问题。</span><span class="sxs-lookup"><span data-stu-id="2886e-109">This can cause issues with the new distributed system model for Front End Pools in Lync Server 2013.</span></span> <span data-ttu-id="2886e-110">有关详细信息, 请参阅[Lync Server 2013 中前端服务器、即时消息和状态的拓扑和组件](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="2886e-110">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

