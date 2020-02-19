---
title: Lync Server 2013 会议用户模型
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
ms.openlocfilehash: fa7cc640f0ed6ae4de2c0b8b25b83a3ec6bb89bc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="the-conferencing-user-model-in-lync-server-2013"></a><span data-ttu-id="edce9-102">Lync Server 2013 中的会议用户模型</span><span class="sxs-lookup"><span data-stu-id="edce9-102">The conferencing user model in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="edce9-103">_**上次修改的主题：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="edce9-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="edce9-104">Lync Server 会议用户模型的关键部分是会议大小。</span><span class="sxs-lookup"><span data-stu-id="edce9-104">A critical part of the Lync Server conferencing user model is meeting size.</span></span> <span data-ttu-id="edce9-105">从多个数据点收集数据（如上一节中所述）之后，我们确定了以下内容：</span><span class="sxs-lookup"><span data-stu-id="edce9-105">After collecting data from the multiple data points (as described in the previous section), we determined the following:</span></span>

  - <span data-ttu-id="edce9-106">大多数会议实际上都是平均有四到六位参与者的小型协作会议</span><span class="sxs-lookup"><span data-stu-id="edce9-106">Most meetings are actually small collaborative meetings with an average of four to six participants</span></span>

  - <span data-ttu-id="edce9-107">大约 80% 的会议的参与者不到 20 人。</span><span class="sxs-lookup"><span data-stu-id="edce9-107">Approximately 80 percent of meetings have fewer than 20 participants.</span></span>

  - <span data-ttu-id="edce9-108">99.98% 的会议的参与者不到 100 人。</span><span class="sxs-lookup"><span data-stu-id="edce9-108">99.98 percent of meetings have fewer than 100 participants.</span></span>

<span data-ttu-id="edce9-109">除了会议规模以外，会议用户模型还考虑到各种因素，如：</span><span class="sxs-lookup"><span data-stu-id="edce9-109">In addition to meeting size, the conferencing user model also takes into account a variety of factors, such as:</span></span>

  - <span data-ttu-id="edce9-110">**并发会议**   同时需要多少用户同时参与会议？</span><span class="sxs-lookup"><span data-stu-id="edce9-110">**Concurrent meetings**   How many users are expected to be in meetings at the same time?</span></span>

  - <span data-ttu-id="edce9-111">**媒体组合**   哪些类型的媒体可用并预期由会议中的用户使用？</span><span class="sxs-lookup"><span data-stu-id="edce9-111">**Media mix**   What types of media are available and expected to be used by users in meetings?</span></span>

  - <span data-ttu-id="edce9-112">**用户类型**   是用户内部用户、远程用户、联合用户还是匿名用户？</span><span class="sxs-lookup"><span data-stu-id="edce9-112">**User types**   Are users internal users, remote users, federated users, or anonymous users?</span></span>

  - <span data-ttu-id="edce9-113">**会议加速**   会议的所有用户加入会议需要多长时间？</span><span class="sxs-lookup"><span data-stu-id="edce9-113">**Meeting ramp up time**   How long does it take for all users of a meeting to join a meeting?</span></span>

<span data-ttu-id="edce9-114">有关用户模型的详细信息，请参阅[Lync Server 2013 中的用户模型](lync-server-2013-user-models.md)。</span><span class="sxs-lookup"><span data-stu-id="edce9-114">For details about the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="edce9-115">为了确定要用于测试的会议数和用户数，我们执行了以下操作：</span><span class="sxs-lookup"><span data-stu-id="edce9-115">To determine the number of meetings and users to use for testing, we did the following:</span></span>

  - <span data-ttu-id="edce9-116">将组织中的用户总数（例如，80,000 位用户）乘以会议并发率（例如，所有用户的 5%），以确定预计同时参加会议的用户总数（在此示例中，为 4000 位用户）。</span><span class="sxs-lookup"><span data-stu-id="edce9-116">Took the total number of users in an organization (for example, 80,000 users) and multiplied it by the meeting concurrency rate (for example, 5% of all users) to determine the total number of users expected to be in meetings at the same time (in this example, 4000 users).</span></span>

  - <span data-ttu-id="edce9-117">将总用户数除以部署中的 Lync Server 2013、前端服务器数（例如，8台服务器），以确定每个前端服务器的估计会议参与者数（在此示例中，每个前端服务器500个用户）。</span><span class="sxs-lookup"><span data-stu-id="edce9-117">Divided the total number of users by the number of Lync Server 2013, Front End Servers in the deployment (for example, 8 servers) to determine the estimated number of meeting participants per Front End Server (in this example, 500 users per Front End Server).</span></span>

  - <span data-ttu-id="edce9-118">将每个前端服务器的用户数除以平均会议大小（例如，4个用户），以确定每个前端服务器的估计平均会议数（在此示例中，每台前端服务器125个会议）。</span><span class="sxs-lookup"><span data-stu-id="edce9-118">Divided the number of users per Front End Server by the average meeting size (for example, 4 users) to determine the estimated average number of meetings per Front End Server (in this example, 125 meetings per Front End Server).</span></span>

  - <span data-ttu-id="edce9-119">若要在每台前端服务器上获取每个媒体负载，我们估计媒体组合。</span><span class="sxs-lookup"><span data-stu-id="edce9-119">To get the per media load on each Front End Server, we estimated the media mix.</span></span> <span data-ttu-id="edce9-120">例如，假设75% 的会议要求的不只是音频支持，而这些会议的50% 需要应用程序共享，则平均47会议和188用户同时连接到每个前端服务器以进行应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="edce9-120">For example, assuming that 75% of the meetings require more than just audio support and 50% of those meetings require application sharing, an average of 47 meetings and 188 users connect concurrently to each Front End Server for application sharing.</span></span>

  - <span data-ttu-id="edce9-121">对各种会议规模进行测试（基于共享池中多达 250 位用户的用户模型），以确保服务器可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="edce9-121">Tested a variety of meeting sizes (based our user model of up to 250 users in a shared pool) to ensure server scalability.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

