---
title: 'Lync Server 2013: 大型会议支持常见问题'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server large meeting support FAQ
ms:assetid: 34b4fb6a-e35c-47e8-8ab1-f8331741fed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204804(v=OCS.15)
ms:contentKeyID: 48183837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c8355374a773afe3d6da22c886a2b103b13abd3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-support-faq-for-lync-server-2013"></a><span data-ttu-id="03164-102">适用于 Lync Server 2013 的大型会议支持常见问题</span><span class="sxs-lookup"><span data-stu-id="03164-102">Large meeting support FAQ for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03164-103">_**主题上次修改时间:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="03164-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="03164-104">以下部分提供了有关创建和运行大型会议的常见问题的答案。</span><span class="sxs-lookup"><span data-stu-id="03164-104">The following sections provide answers to common questions for creating and running large meetings.</span></span>

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a><span data-ttu-id="03164-105">问: 有多少用户可以参与大型会议？</span><span class="sxs-lookup"><span data-stu-id="03164-105">Q: How many users can participate in a large meeting?</span></span>

<span data-ttu-id="03164-106">Lync Server 用户模型指定在专用于大型会议的池中的共享池或1000用户中的250用户的限制, 但这些数字仅表示我们测试的用户数, 并且仅表示我们在测试中使用的特定硬件集。</span><span class="sxs-lookup"><span data-stu-id="03164-106">The Lync Server user model specifies limits of 250 users in a shared pool or 1000 users in a pool dedicated to large meetings, but these numbers only represent the number of users we tested and only for the specific set of hardware that we used in our testing.</span></span> <span data-ttu-id="03164-107">根据我们的测试, 我们建议对最大大小的限制。</span><span class="sxs-lookup"><span data-stu-id="03164-107">Based on our testing, we recommend those limits for maximum sizes.</span></span> <span data-ttu-id="03164-108">但是, 你可以通过配置一个或多个会议策略来控制你组织中的会议所允许的实际参与者数 (使用 Lync Server Management Shell 中的 Windows PowerShell cmdlet 或使用 Lync 服务器配置)"控制面板")。</span><span class="sxs-lookup"><span data-stu-id="03164-108">However, you control the actual number of participants allowed in meetings in your organization by configuring one or more conferencing policies (which you configure using Windows PowerShell cmdlets in the Lync Server Management Shell or using the Lync Server Control Panel).</span></span> <span data-ttu-id="03164-109">在会议策略中指定的数字可以是1和4294967295之间的任何32位整数, 但建议的大小介于2和250参与者之间, 包括;默认值为250。</span><span class="sxs-lookup"><span data-stu-id="03164-109">The number that you specify in a conferencing policy can be any 32-bit whole number between 1 and 4,294,967,295, but the recommended size is between 2 and 250 participants, inclusive; and the default value is 250.</span></span>

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a><span data-ttu-id="03164-110">问: 我可以在一个专用于大型会议的池中拥有多少个会议或其他工作负荷？</span><span class="sxs-lookup"><span data-stu-id="03164-110">Q: How many meetings or other workloads can I have in a pool that is dedicated to large meetings?</span></span>

<span data-ttu-id="03164-111">为确保在最多1000参与者的大型会议中获得最佳用户体验, 我们建议在专用于大型会议的池上一次仅托管一个大型会议。</span><span class="sxs-lookup"><span data-stu-id="03164-111">To ensure the best user experience in large meetings of up to 1000 participants, we recommend hosting only a single large meeting at a time on a pool that is dedicated to large meetings.</span></span> <span data-ttu-id="03164-112">我们还建议当大型会议正在进行时, 不允许任何其他工作负荷在该池中运行。</span><span class="sxs-lookup"><span data-stu-id="03164-112">We also recommend not allowing any other workloads to run on that pool when the large meeting is in progress.</span></span>

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a><span data-ttu-id="03164-113">问: 大型会议的组织者是否应该托管在专用池？</span><span class="sxs-lookup"><span data-stu-id="03164-113">Q: Should the organizers of large meeting be homed on the dedicated pool?</span></span>

<span data-ttu-id="03164-114">不能。</span><span class="sxs-lookup"><span data-stu-id="03164-114">No.</span></span> <span data-ttu-id="03164-115">我们建议不要在专门的人员 (这些员工) 之外的其他任何用户 (在专用的池中管理大型会议的计划) 进行托管。</span><span class="sxs-lookup"><span data-stu-id="03164-115">We recommend not homing any users other than the dedicated staff that manages scheduling of large meetings on the dedicated pool.</span></span> <span data-ttu-id="03164-116">这可防止其他实时通信流量导致在池中托管的大型会议出现问题。</span><span class="sxs-lookup"><span data-stu-id="03164-116">This prevents other real-time communications traffic from causing problems with large meetings that are hosted in the pool.</span></span> <span data-ttu-id="03164-117">你应该使用大型会议计划员工的用户帐户, 在专用池上安排大型会议。</span><span class="sxs-lookup"><span data-stu-id="03164-117">You should schedule large meetings on the dedicated pool using a user account of the large meeting scheduling staff.</span></span> <span data-ttu-id="03164-118">应将会议组织者的用户帐户 (请求大型会议的用户) 添加为大型会议的演示者。</span><span class="sxs-lookup"><span data-stu-id="03164-118">You should add the user account of the meeting organizer (the user who requests a large meeting) as a presenter for the large meeting.</span></span>

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a><span data-ttu-id="03164-119">问: 我可以在大型会议中使用哪些媒体形式？</span><span class="sxs-lookup"><span data-stu-id="03164-119">Q: What media modalities can I use in a large meeting?</span></span>

<span data-ttu-id="03164-120">最多1000个用户的大型会议可以包括音频、视频、PowerPoint 共享、白板和状态轮询。</span><span class="sxs-lookup"><span data-stu-id="03164-120">Large meetings with up to 1000 users can include audio, video, PowerPoint sharing, whiteboards, and presence polling.</span></span>

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a><span data-ttu-id="03164-121">问: 是否可以在大型会议中使用群组即时消息 (IM)？</span><span class="sxs-lookup"><span data-stu-id="03164-121">Q: Can I use group instant messaging (IM) in large meetings?</span></span>

<span data-ttu-id="03164-122">是。</span><span class="sxs-lookup"><span data-stu-id="03164-122">Yes.</span></span> <span data-ttu-id="03164-123">但是, 大量即时消息 (尤其是当由大量的会议参与者发送时) 可能会因在即时消息窗口中快速文本滚动问题而影响用户体验。</span><span class="sxs-lookup"><span data-stu-id="03164-123">However, large numbers of instant messages, especially when sent by a large number of meeting participants, can affect the user experience due to problems with fast text scrolling in the IM window.</span></span> <span data-ttu-id="03164-124">向多达1000用户提供大量即时消息也可能会引入大量的服务器负载, 这可能会影响性能。</span><span class="sxs-lookup"><span data-stu-id="03164-124">Delivering a large amount of instant messages to up to 1000 users can also introduce significant server loads, which can affect performance.</span></span> <span data-ttu-id="03164-125">通常, 只有问题和解答 (Q\&As) 才需要 IM。</span><span class="sxs-lookup"><span data-stu-id="03164-125">Generally, IM is only required for questions and answers (Q\&As).</span></span>

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a><span data-ttu-id="03164-126">通过从电话拨入, 用户能否加入大型会议？</span><span class="sxs-lookup"><span data-stu-id="03164-126">Can users join large meetings by dialing in from a phone?</span></span>

<span data-ttu-id="03164-127">是。</span><span class="sxs-lookup"><span data-stu-id="03164-127">Yes.</span></span> <span data-ttu-id="03164-128">如果 Lync Server 2013 池已正确部署, 并且已启用电话拨入式会议, 则用户可以通过拨入来加入大型会议。</span><span class="sxs-lookup"><span data-stu-id="03164-128">If the Lync Server 2013 pool is properly deployed and enabled for dial-in conferencing, users will be able to join the large meetings by dialing in.</span></span> <span data-ttu-id="03164-129">我们的测试显示, 最多 15% 的1000用户可以在10分钟时间内加入大型会议。</span><span class="sxs-lookup"><span data-stu-id="03164-129">Our testing has shown that up to 15% of the 1000 users can join the large meeting over a 10 minute period.</span></span>

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a><span data-ttu-id="03164-130">问: 我是否可以在虚拟拓扑中托管大型会议？</span><span class="sxs-lookup"><span data-stu-id="03164-130">Q: Can I host large meetings in a virtual topology?</span></span>

<span data-ttu-id="03164-131">我们尚未在虚拟拓扑中测试大型会议, 因此我们不支持使用虚拟机来托管大型会议的专用池。</span><span class="sxs-lookup"><span data-stu-id="03164-131">We have not tested large meetings in a virtual topology, so we do not support the use of virtual machines to host a dedicated pool for large meetings.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

