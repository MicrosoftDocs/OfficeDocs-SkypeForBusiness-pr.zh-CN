---
title: Lync Server 2013 会议加载分发
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing load distribution
ms:assetid: 5901a076-1b6f-4720-8837-95fc7f3c37f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204922(v=OCS.15)
ms:contentKeyID: 48184233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: baa8230470fc765bbda7c3b2bf49e6962b3db22f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741522"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-load-distribution-in-lync-server-2013"></a><span data-ttu-id="692f2-102">Lync Server 2013 中的会议负载分配</span><span class="sxs-lookup"><span data-stu-id="692f2-102">Conferencing load distribution in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="692f2-103">_**主题上次修改时间：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="692f2-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="692f2-104">与其他一些专用会议解决方案不同，Lync 服务器体系结构是共享硬件模型。</span><span class="sxs-lookup"><span data-stu-id="692f2-104">Unlike some other dedicated conferencing solutions, Lync Server architecture is a shared-hardware model.</span></span> <span data-ttu-id="692f2-105">这意味着同一硬件由许多软件组件共享，每个组件都支持不同的实时通信。</span><span class="sxs-lookup"><span data-stu-id="692f2-105">This means that the same hardware is shared by many software components, each of which supports different real-time communications.</span></span> <span data-ttu-id="692f2-106">每种类型的实时通信都将在服务器上放置特定负载。</span><span class="sxs-lookup"><span data-stu-id="692f2-106">Each type of real-time communications places specific loads on the servers.</span></span> <span data-ttu-id="692f2-107">例如，前端服务器可以运行会话初始协议（SIP）路由组件、web 应用程序（如通讯簿搜索）、Web 会议服务、A/V 会议服务、企业语音应用程序（例如，会议助理应用程序和响应组应用程序）和中介服务器。</span><span class="sxs-lookup"><span data-stu-id="692f2-107">For example, the Front End Server can run the Session Initiation Protocol (SIP) routing components, web applications (such as Address Book search), Web Conferencing service, A/V Conferencing service, Enterprise Voice applications (for example, Conferencing Attendant application and Response Group application), and Mediation Server.</span></span> <span data-ttu-id="692f2-108">前端服务器上的一组数据库还为用户、联系人、联机状态、会议和语音路由数据提供存储和处理。</span><span class="sxs-lookup"><span data-stu-id="692f2-108">A set of databases on the Front End Server also provide storage and processing for user, contact, presence, conferencing, and voice routing data.</span></span> <span data-ttu-id="692f2-109">通过这种硬件共享、组件、服务和进程来争用 CPU 和内存资源，因此非会议工作负载对服务器缩放有直接影响。</span><span class="sxs-lookup"><span data-stu-id="692f2-109">With this hardware sharing, components, services, and processes compete for CPU and memory resources, so non-conferencing workloads have a direct impact on server scaling.</span></span>

<span data-ttu-id="692f2-110">与其他基于硬件的其他会议解决方案相比，Lync Server 会议体系结构是一个无保留模型。</span><span class="sxs-lookup"><span data-stu-id="692f2-110">Compared to other hardware port-based conferencing solutions, Lync Server conferencing architecture is a no-reservation model.</span></span> <span data-ttu-id="692f2-111">当用户安排会议时，Lync Server 在会议数据库中创建记录，该记录用于存储会议数据，但不会提前为计划会议保留任何硬件资源。</span><span class="sxs-lookup"><span data-stu-id="692f2-111">When a user schedules a meeting, Lync Server creates a record in the conferencing database, which stores conferencing data, but does not reserve any hardware resources for the scheduled meeting ahead of time.</span></span> <span data-ttu-id="692f2-112">因此，Lync Server 具有内置负载平衡逻辑，可通过在池中的所有前端服务器上平均分配负载的方式在前端服务器上动态分配会议资源。</span><span class="sxs-lookup"><span data-stu-id="692f2-112">Instead, Lync Server has built-in load balancing logic to dynamically allocate conferencing resources on Front End Servers in a way that distributes loads equally across all Front End Servers in the pool.</span></span> <span data-ttu-id="692f2-113">这将有效地预配和利用硬件资源，但这使得支持超大型会议非常困难（特别是不恰当的计划）。</span><span class="sxs-lookup"><span data-stu-id="692f2-113">This effectively provisions and utilizes hardware resources, but makes it challenging to support very large meetings (especially without appropriate planning).</span></span> <span data-ttu-id="692f2-114">例如，当 Lync Server 2013 池的运行速度接近其最高容量时，每台前端服务器可能会主持大约125平均大小的会议。</span><span class="sxs-lookup"><span data-stu-id="692f2-114">For example, when a Lync Server 2013 pool is running close to its top capacity, each Front End Server might host approximately 125 average-size meetings.</span></span> <span data-ttu-id="692f2-115">再添加一个小型会议不会有问题，但是添加一个 1000 用户的会议就会出现问题，因为前端服务器可能无法在已有其他 125 个会议的同时支持这样的大型会议。</span><span class="sxs-lookup"><span data-stu-id="692f2-115">Adding another small meeting would not be a problem, but adding a meeting for 1000 users would be a problem because the Front End Servers would probably not be able to support such a large meeting at the same time as the other 125 meetings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

