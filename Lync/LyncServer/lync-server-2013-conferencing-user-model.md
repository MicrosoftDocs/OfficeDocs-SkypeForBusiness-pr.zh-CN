---
title: Lync Server 2013 会议用户模型
description: Lync Server 2013 会议用户模型。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: The conferencing user model
ms:assetid: ba4bbba9-f2e3-4cab-8eba-b51f12133cab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205199(v=OCS.15)
ms:contentKeyID: 48185229
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 699f41303b82f4d8fd2864cbf1b29a1c601b826e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555978"
---
# <a name="the-conferencing-user-model-in-lync-server-2013"></a><span data-ttu-id="5da9c-103">Lync Server 2013 中的会议用户模型</span><span class="sxs-lookup"><span data-stu-id="5da9c-103">The conferencing user model in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5da9c-104">_**上次修改的主题：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="5da9c-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="5da9c-105">Lync Server 会议用户模型的关键部分是会议大小。</span><span class="sxs-lookup"><span data-stu-id="5da9c-105">A critical part of the Lync Server conferencing user model is meeting size.</span></span> <span data-ttu-id="5da9c-106">从多个数据点收集数据（如上一节中所述）之后，我们确定了以下内容：</span><span class="sxs-lookup"><span data-stu-id="5da9c-106">After collecting data from the multiple data points (as described in the previous section), we determined the following:</span></span>

  - <span data-ttu-id="5da9c-107">大多数会议实际上都是平均有四到六位参与者的小型协作会议</span><span class="sxs-lookup"><span data-stu-id="5da9c-107">Most meetings are actually small collaborative meetings with an average of four to six participants</span></span>

  - <span data-ttu-id="5da9c-108">大约 80% 的会议的参与者不到 20 人。</span><span class="sxs-lookup"><span data-stu-id="5da9c-108">Approximately 80 percent of meetings have fewer than 20 participants.</span></span>

  - <span data-ttu-id="5da9c-109">99.98% 的会议的参与者不到 100 人。</span><span class="sxs-lookup"><span data-stu-id="5da9c-109">99.98 percent of meetings have fewer than 100 participants.</span></span>

<span data-ttu-id="5da9c-110">除了会议规模以外，会议用户模型还考虑到各种因素，如：</span><span class="sxs-lookup"><span data-stu-id="5da9c-110">In addition to meeting size, the conferencing user model also takes into account a variety of factors, such as:</span></span>

  - <span data-ttu-id="5da9c-111">**并发会议**    在会议中，需要有多少个用户同时参与？</span><span class="sxs-lookup"><span data-stu-id="5da9c-111">**Concurrent meetings**   How many users are expected to be in meetings at the same time?</span></span>

  - <span data-ttu-id="5da9c-112">**媒体组合**    哪些类型的媒体可用并预期由会议中的用户使用？</span><span class="sxs-lookup"><span data-stu-id="5da9c-112">**Media mix**   What types of media are available and expected to be used by users in meetings?</span></span>

  - <span data-ttu-id="5da9c-113">**用户类型**    用户是用户内部用户、远程用户、联合用户还是匿名用户？</span><span class="sxs-lookup"><span data-stu-id="5da9c-113">**User types**   Are users internal users, remote users, federated users, or anonymous users?</span></span>

  - <span data-ttu-id="5da9c-114">**会议提升时间**    会议的所有用户加入会议需要多长时间？</span><span class="sxs-lookup"><span data-stu-id="5da9c-114">**Meeting ramp up time**   How long does it take for all users of a meeting to join a meeting?</span></span>

<span data-ttu-id="5da9c-115">有关用户模型的详细信息，请参阅 [Lync Server 2013 中的用户模型](lync-server-2013-user-models.md)。</span><span class="sxs-lookup"><span data-stu-id="5da9c-115">For details about the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="5da9c-116">为了确定要用于测试的会议数和用户数，我们执行了以下操作：</span><span class="sxs-lookup"><span data-stu-id="5da9c-116">To determine the number of meetings and users to use for testing, we did the following:</span></span>

  - <span data-ttu-id="5da9c-117">将组织中的用户总数（例如，80,000 位用户）乘以会议并发率（例如，所有用户的 5%），以确定预计同时参加会议的用户总数（在此示例中，为 4000 位用户）。</span><span class="sxs-lookup"><span data-stu-id="5da9c-117">Took the total number of users in an organization (for example, 80,000 users) and multiplied it by the meeting concurrency rate (for example, 5% of all users) to determine the total number of users expected to be in meetings at the same time (in this example, 4000 users).</span></span>

  - <span data-ttu-id="5da9c-118">将用户总数除以部署中的 Lync Server 2013、前端服务器数 (例如，8台服务器) ，以确定每个前端服务器的估计会议参与者数 (在此示例中，每个前端服务器) 500 个用户。</span><span class="sxs-lookup"><span data-stu-id="5da9c-118">Divided the total number of users by the number of Lync Server 2013, Front End Servers in the deployment (for example, 8 servers) to determine the estimated number of meeting participants per Front End Server (in this example, 500 users per Front End Server).</span></span>

  - <span data-ttu-id="5da9c-119">将每个前端服务器的用户数除以平均会议大小 (例如，4个用户) 以确定每个前端服务器的估计平均会议数 (在此示例中，每个前端服务器) 125 个会议。</span><span class="sxs-lookup"><span data-stu-id="5da9c-119">Divided the number of users per Front End Server by the average meeting size (for example, 4 users) to determine the estimated average number of meetings per Front End Server (in this example, 125 meetings per Front End Server).</span></span>

  - <span data-ttu-id="5da9c-120">若要在每台前端服务器上获取每个媒体负载，我们估计媒体组合。</span><span class="sxs-lookup"><span data-stu-id="5da9c-120">To get the per media load on each Front End Server, we estimated the media mix.</span></span> <span data-ttu-id="5da9c-121">例如，假设75% 的会议要求的不只是音频支持，而这些会议的50% 需要应用程序共享，则平均47会议和188用户同时连接到每个前端服务器以进行应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="5da9c-121">For example, assuming that 75% of the meetings require more than just audio support and 50% of those meetings require application sharing, an average of 47 meetings and 188 users connect concurrently to each Front End Server for application sharing.</span></span>

  - <span data-ttu-id="5da9c-122">对各种会议规模进行测试（基于共享池中多达 250 位用户的用户模型），以确保服务器可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="5da9c-122">Tested a variety of meeting sizes (based our user model of up to 250 users in a shared pool) to ensure server scalability.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

