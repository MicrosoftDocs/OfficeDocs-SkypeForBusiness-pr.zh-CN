---
title: Lync Server 2013 与 Lync Server 2010 大都市网站恢复兼容性
description: Lync Server 2013 与 Lync Server 2010 大都市网站恢复兼容性。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2010 metropolitan site resiliency
ms:assetid: 18673ff6-b664-4a57-a89b-cbda8b129e6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204715(v=OCS.15)
ms:contentKeyID: 48183526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec72f261ac593b24bad13dcd400f495ba7ba0722
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576928"
---
# <a name="lync-server-2010-metropolitan-site-resiliency"></a><span data-ttu-id="b3a1b-103">Lync Server 2010 大都市站点恢复能力</span><span class="sxs-lookup"><span data-stu-id="b3a1b-103">Lync Server 2010 metropolitan site resiliency</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3a1b-104">_**上次修改的主题：** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="b3a1b-104">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="b3a1b-105">Lync Server 2013 不支持 Lync Server 2010 支持的大都市站点恢复解决方案。</span><span class="sxs-lookup"><span data-stu-id="b3a1b-105">The metropolitan site resiliency solution supported for Lync Server 2010 is not supported for Lync Server 2013.</span></span> <span data-ttu-id="b3a1b-106">此解决方案涉及在同一都市圈中的两个数据中心之间跨越使用一个前端池。</span><span class="sxs-lookup"><span data-stu-id="b3a1b-106">This solution involved spanning a single Front End pool across two data centers in the same metropolitan area.</span></span>

<span data-ttu-id="b3a1b-107">大都市站点恢复解决方案旨在从丢失完整数据中心时进行恢复。</span><span class="sxs-lookup"><span data-stu-id="b3a1b-107">The metropolitan site resiliency solution was designed to recover from the loss of a full datacenter.</span></span> <span data-ttu-id="b3a1b-108">跨两个数据中心跨越池时，通常会在一个数据中心中放置半个前端，在第二个数据中心中放置另一半。</span><span class="sxs-lookup"><span data-stu-id="b3a1b-108">When you span your pool across two datacenters, you typically put half of your front ends in one datacenter and the other half in the second datacenter.</span></span> <span data-ttu-id="b3a1b-109">如果丢失整个数据中心，则会丢失一半前端服务器。</span><span class="sxs-lookup"><span data-stu-id="b3a1b-109">If you lose an entire datacenter, you have lost half of your Front End Servers.</span></span> <span data-ttu-id="b3a1b-110">在 Lync Server 2013 中，这可能会导致前端池的新分布式系统模型出现问题。</span><span class="sxs-lookup"><span data-stu-id="b3a1b-110">This can cause issues with the new distributed system model for Front End Pools in Lync Server 2013.</span></span> <span data-ttu-id="b3a1b-111">有关详细信息，请参阅 [Lync Server 2013 中的前端服务器、即时消息和状态的拓扑和组件](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="b3a1b-111">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

