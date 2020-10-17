---
title: Lync Server 2013 会议负载分发
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
ms.openlocfilehash: 38f7b2d759ec9370bbf7eeeb2844edd3511ba0f1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499199"
---
# <a name="conferencing-load-distribution-in-lync-server-2013"></a><span data-ttu-id="67c46-102">Lync Server 2013 中的会议负载分发</span><span class="sxs-lookup"><span data-stu-id="67c46-102">Conferencing load distribution in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67c46-103">_**上次修改的主题：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="67c46-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="67c46-104">与其他一些专用会议解决方案不同，Lync Server 体系结构是共享硬件模型。</span><span class="sxs-lookup"><span data-stu-id="67c46-104">Unlike some other dedicated conferencing solutions, Lync Server architecture is a shared-hardware model.</span></span> <span data-ttu-id="67c46-105">这意味着很多软件组件共享了相同的硬件，这些组件中的每一个都支持不同的实时通信。</span><span class="sxs-lookup"><span data-stu-id="67c46-105">This means that the same hardware is shared by many software components, each of which supports different real-time communications.</span></span> <span data-ttu-id="67c46-106">每种类型的实时通信都为服务器带来了特定的负载。</span><span class="sxs-lookup"><span data-stu-id="67c46-106">Each type of real-time communications places specific loads on the servers.</span></span> <span data-ttu-id="67c46-107">例如，前端服务器可以运行会话初始协议 (SIP) 路由组件、web 应用程序 (如通讯簿搜索) 、Web 会议服务、A/V 会议服务、企业语音应用程序 (例如，会议助理应用程序和响应组应用程序) 和中介服务器。</span><span class="sxs-lookup"><span data-stu-id="67c46-107">For example, the Front End Server can run the Session Initiation Protocol (SIP) routing components, web applications (such as Address Book search), Web Conferencing service, A/V Conferencing service, Enterprise Voice applications (for example, Conferencing Attendant application and Response Group application), and Mediation Server.</span></span> <span data-ttu-id="67c46-108">前端服务器上的一组数据库还提供了用于用户、联系人、状态、会议和语音路由数据的存储和处理。</span><span class="sxs-lookup"><span data-stu-id="67c46-108">A set of databases on the Front End Server also provide storage and processing for user, contact, presence, conferencing, and voice routing data.</span></span> <span data-ttu-id="67c46-109">由于存在此硬件共享，组件、服务和进程将争用 CPU 和内存资源，因此非会议工作负荷对服务器缩放有直接影响。</span><span class="sxs-lookup"><span data-stu-id="67c46-109">With this hardware sharing, components, services, and processes compete for CPU and memory resources, so non-conferencing workloads have a direct impact on server scaling.</span></span>

<span data-ttu-id="67c46-110">与其他基于硬件端口的会议解决方案相比，Lync Server 会议体系结构是一个无保留模型。</span><span class="sxs-lookup"><span data-stu-id="67c46-110">Compared to other hardware port-based conferencing solutions, Lync Server conferencing architecture is a no-reservation model.</span></span> <span data-ttu-id="67c46-111">当用户安排会议时，Lync Server 在会议数据库中创建一条记录，该记录存储会议数据，但不事先为计划会议预留任何硬件资源。</span><span class="sxs-lookup"><span data-stu-id="67c46-111">When a user schedules a meeting, Lync Server creates a record in the conferencing database, which stores conferencing data, but does not reserve any hardware resources for the scheduled meeting ahead of time.</span></span> <span data-ttu-id="67c46-112">相反，Lync Server 具有内置负载平衡逻辑，以在前端服务器上动态分配会议资源，从而在池中的所有前端服务器上平均分布负载。</span><span class="sxs-lookup"><span data-stu-id="67c46-112">Instead, Lync Server has built-in load balancing logic to dynamically allocate conferencing resources on Front End Servers in a way that distributes loads equally across all Front End Servers in the pool.</span></span> <span data-ttu-id="67c46-113">这样做可以有效地设置和利用硬件资源，但可能难以支持特大型会议（尤其是在没有制定合适的计划时）。</span><span class="sxs-lookup"><span data-stu-id="67c46-113">This effectively provisions and utilizes hardware resources, but makes it challenging to support very large meetings (especially without appropriate planning).</span></span> <span data-ttu-id="67c46-114">例如，当 Lync Server 2013 池的运行接近其顶级容量时，每台前端服务器可能会主持大约125平均大小的会议。</span><span class="sxs-lookup"><span data-stu-id="67c46-114">For example, when a Lync Server 2013 pool is running close to its top capacity, each Front End Server might host approximately 125 average-size meetings.</span></span> <span data-ttu-id="67c46-115">添加另一个小会议并不是一个问题，但为1000用户添加会议是一个问题，因为前端服务器可能无法同时支持其他125会议的大型会议。</span><span class="sxs-lookup"><span data-stu-id="67c46-115">Adding another small meeting would not be a problem, but adding a meeting for 1000 users would be a problem because the Front End Servers would probably not be able to support such a large meeting at the same time as the other 125 meetings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

