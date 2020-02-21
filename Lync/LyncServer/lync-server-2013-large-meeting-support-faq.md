---
title: Lync Server 2013：大型会议支持常见问题解答
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server large meeting support FAQ
ms:assetid: 34b4fb6a-e35c-47e8-8ab1-f8331741fed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204804(v=OCS.15)
ms:contentKeyID: 48183837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bcb5e8ecf3843a8997daa818ed75b33162cfb70
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="large-meeting-support-faq-for-lync-server-2013"></a><span data-ttu-id="c8514-102">Lync Server 2013 的大型会议支持常见问题解答</span><span class="sxs-lookup"><span data-stu-id="c8514-102">Large meeting support FAQ for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8514-103">_**上次修改的主题：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="c8514-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="c8514-104">以下各节提供有关创建和运行大型会议的常见问题的解答。</span><span class="sxs-lookup"><span data-stu-id="c8514-104">The following sections provide answers to common questions for creating and running large meetings.</span></span>

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a><span data-ttu-id="c8514-105">问：可以参与大型会议的用户数是多少？</span><span class="sxs-lookup"><span data-stu-id="c8514-105">Q: How many users can participate in a large meeting?</span></span>

<span data-ttu-id="c8514-106">Lync Server 用户模型指定在专用于大型会议的池中的共享池或1000用户中的250个用户的限制，但这些号码只代表我们测试的用户数，并且仅代表我们在测试中使用的特定硬件集。</span><span class="sxs-lookup"><span data-stu-id="c8514-106">The Lync Server user model specifies limits of 250 users in a shared pool or 1000 users in a pool dedicated to large meetings, but these numbers only represent the number of users we tested and only for the specific set of hardware that we used in our testing.</span></span> <span data-ttu-id="c8514-107">根据我们的测试，建议将这些限制作为最大大小。</span><span class="sxs-lookup"><span data-stu-id="c8514-107">Based on our testing, we recommend those limits for maximum sizes.</span></span> <span data-ttu-id="c8514-108">但是，通过配置一个或多个会议策略（使用 Lync Server 命令行管理程序中的 Windows PowerShell cmdlet 或使用 Lync Server 配置），可以控制组织中的会议允许的实际人数。控制面版）。</span><span class="sxs-lookup"><span data-stu-id="c8514-108">However, you control the actual number of participants allowed in meetings in your organization by configuring one or more conferencing policies (which you configure using Windows PowerShell cmdlets in the Lync Server Management Shell or using the Lync Server Control Panel).</span></span> <span data-ttu-id="c8514-109">您在会议策略中指定的数字可以是 1 到 4,294,967,295 之间的任意 32 位整数，但建议大小为 2 到 250（包括 2 和 250）位参与者；默认值为 250。</span><span class="sxs-lookup"><span data-stu-id="c8514-109">The number that you specify in a conferencing policy can be any 32-bit whole number between 1 and 4,294,967,295, but the recommended size is between 2 and 250 participants, inclusive; and the default value is 250.</span></span>

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a><span data-ttu-id="c8514-110">问：可以在专用于大型会议的池中召开的会议数或运行的其他工作负载是多少？</span><span class="sxs-lookup"><span data-stu-id="c8514-110">Q: How many meetings or other workloads can I have in a pool that is dedicated to large meetings?</span></span>

<span data-ttu-id="c8514-p102">为确保在多达 1000 位参与者的大型会议中获得最佳用户体验，建议您在专用于大型会议的池中一次仅召开一个会议。还建议在大型会议进行时不要允许其他任何工作负载在该池中运行。</span><span class="sxs-lookup"><span data-stu-id="c8514-p102">To ensure the best user experience in large meetings of up to 1000 participants, we recommend hosting only a single large meeting at a time on a pool that is dedicated to large meetings. We also recommend not allowing any other workloads to run on that pool when the large meeting is in progress.</span></span>

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a><span data-ttu-id="c8514-113">问：大型会议的组织者是否应托管在专用池中？</span><span class="sxs-lookup"><span data-stu-id="c8514-113">Q: Should the organizers of large meeting be homed on the dedicated pool?</span></span>

<span data-ttu-id="c8514-p103">不是。我们不建议托管除管理专用池中大型会议计划的专门人员以外的任何用户。这可防止其他实时通信流导致该池中托管的大型会议出现问题。您应使用大型会议计划人员的用户帐户安排专用池中的大型会议。您应将会议组织者（请求大型会议的用户）的用户帐户添加为大型会议的演示者。</span><span class="sxs-lookup"><span data-stu-id="c8514-p103">No. We recommend not homing any users other than the dedicated staff that manages scheduling of large meetings on the dedicated pool. This prevents other real-time communications traffic from causing problems with large meetings that are hosted in the pool. You should schedule large meetings on the dedicated pool using a user account of the large meeting scheduling staff. You should add the user account of the meeting organizer (the user who requests a large meeting) as a presenter for the large meeting.</span></span>

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a><span data-ttu-id="c8514-119">问：在大型会议中可以使用哪些媒体形式？</span><span class="sxs-lookup"><span data-stu-id="c8514-119">Q: What media modalities can I use in a large meeting?</span></span>

<span data-ttu-id="c8514-120">多达 1000 位用户的大型会议可以包括音频、视频、PowerPoint 共享、白板以及状态轮询。</span><span class="sxs-lookup"><span data-stu-id="c8514-120">Large meetings with up to 1000 users can include audio, video, PowerPoint sharing, whiteboards, and presence polling.</span></span>

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a><span data-ttu-id="c8514-121">问：是否可以在大型会议中使用组即时消息 (IM)？</span><span class="sxs-lookup"><span data-stu-id="c8514-121">Q: Can I use group instant messaging (IM) in large meetings?</span></span>

<span data-ttu-id="c8514-122">是。</span><span class="sxs-lookup"><span data-stu-id="c8514-122">Yes.</span></span> <span data-ttu-id="c8514-123">但是，大量即时消息可能会因 IM 窗口中的快速文本滚动问题而影响用户体验，特别是在许多会议参与者发送即时消息时。</span><span class="sxs-lookup"><span data-stu-id="c8514-123">However, large numbers of instant messages, especially when sent by a large number of meeting participants, can affect the user experience due to problems with fast text scrolling in the IM window.</span></span> <span data-ttu-id="c8514-124">向多达 1000 位用户发送大量即时消息也可能会产生大量服务器负载，这可能会影响性能。</span><span class="sxs-lookup"><span data-stu-id="c8514-124">Delivering a large amount of instant messages to up to 1000 users can also introduce significant server loads, which can affect performance.</span></span> <span data-ttu-id="c8514-125">通常情况下，只有问题和解答（Q\&As）才需要 IM。</span><span class="sxs-lookup"><span data-stu-id="c8514-125">Generally, IM is only required for questions and answers (Q\&As).</span></span>

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a><span data-ttu-id="c8514-126">用户是否可以通过电话拨入加入大型会议？</span><span class="sxs-lookup"><span data-stu-id="c8514-126">Can users join large meetings by dialing in from a phone?</span></span>

<span data-ttu-id="c8514-127">是。</span><span class="sxs-lookup"><span data-stu-id="c8514-127">Yes.</span></span> <span data-ttu-id="c8514-128">如果已正确部署 Lync Server 2013 池并为其启用电话拨入式会议，则用户将能够通过拨入来加入大型会议。</span><span class="sxs-lookup"><span data-stu-id="c8514-128">If the Lync Server 2013 pool is properly deployed and enabled for dial-in conferencing, users will be able to join the large meetings by dialing in.</span></span> <span data-ttu-id="c8514-129">我们的测试表明在 10 分钟内 1000 位用户中将有多达 15% 的用户可以加入大型会议。</span><span class="sxs-lookup"><span data-stu-id="c8514-129">Our testing has shown that up to 15% of the 1000 users can join the large meeting over a 10 minute period.</span></span>

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a><span data-ttu-id="c8514-130">问：是否可以在虚拟拓扑中托管大型会议？</span><span class="sxs-lookup"><span data-stu-id="c8514-130">Q: Can I host large meetings in a virtual topology?</span></span>

<span data-ttu-id="c8514-131">我们尚未在虚拟拓扑中测试大型会议，因此不支持使用虚拟机托管大型会议的专用池。</span><span class="sxs-lookup"><span data-stu-id="c8514-131">We have not tested large meetings in a virtual topology, so we do not support the use of virtual machines to host a dedicated pool for large meetings.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

