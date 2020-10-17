---
title: 迁移阶段
description: 迁移阶段。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72ef47cb9b6c9eba75c395eb9bd94c887ca5a433
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547048"
---
# <a name="migration-phases"></a><span data-ttu-id="12307-103">迁移阶段</span><span class="sxs-lookup"><span data-stu-id="12307-103">Migration phases</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12307-104">_**上次修改的主题：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="12307-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="12307-105">在 Lync Server 2013 中，您在网络上定义包含 Lync Server 2013 组件的网站。</span><span class="sxs-lookup"><span data-stu-id="12307-105">In Lync Server 2013, you define sites on your network that contain Lync Server 2013 components.</span></span> <span data-ttu-id="12307-106">站点是一组通过高速度、低延迟网络（例如单个局域网 (LAN) 或由高速光纤网络连接的两个网络）正确连接的计算机。</span><span class="sxs-lookup"><span data-stu-id="12307-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span>

<span data-ttu-id="12307-107">*前端池* 是一组配置相同的前端服务器，这些服务器协同工作来为公用组用户提供服务。</span><span class="sxs-lookup"><span data-stu-id="12307-107">A *Front End pool* is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="12307-108">池为用户提供可伸缩性和故障转移功能。</span><span class="sxs-lookup"><span data-stu-id="12307-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="12307-109">池中的每台服务器必须运行一个或多个相同的服务器角色。</span><span class="sxs-lookup"><span data-stu-id="12307-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="12307-110">适用于小型组织的 Standard Edition 服务器还定义了一个池，并在一台服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="12307-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="12307-111">这使您能够以较低的成本获取 Lync Server 2013 功能，但不提供真正的高可用性解决方案。</span><span class="sxs-lookup"><span data-stu-id="12307-111">This enables you to have Lync Server 2013 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="12307-112">以下阶段介绍了从 Lync Server 2010 迁移到 Lync Server 2013 的池过程。</span><span class="sxs-lookup"><span data-stu-id="12307-112">The following phases describe the process of a pool migration from Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="12307-113">对于包含多个池的多个站点，每个池都应遵循此分阶段方法。</span><span class="sxs-lookup"><span data-stu-id="12307-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>

1.  [<span data-ttu-id="12307-114">第1阶段：从 Lync Server 2010 规划迁移</span><span class="sxs-lookup"><span data-stu-id="12307-114">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [<span data-ttu-id="12307-115">第 2 阶段：准备迁移</span><span class="sxs-lookup"><span data-stu-id="12307-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

3.  [<span data-ttu-id="12307-116">第3阶段：部署 Lync Server 2013 试点池</span><span class="sxs-lookup"><span data-stu-id="12307-116">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [<span data-ttu-id="12307-117">第4阶段：将测试用户移动到引导池</span><span class="sxs-lookup"><span data-stu-id="12307-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [<span data-ttu-id="12307-118">第5阶段：将 Lync Server 2013 边缘服务器添加到引导池</span><span class="sxs-lookup"><span data-stu-id="12307-118">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [<span data-ttu-id="12307-119">第 6 阶段：从试点部署移动到生产中</span><span class="sxs-lookup"><span data-stu-id="12307-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

7.  [<span data-ttu-id="12307-120">第 7 阶段：完成迁移后任务</span><span class="sxs-lookup"><span data-stu-id="12307-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

8.  [<span data-ttu-id="12307-121">第 8 阶段：停用旧池</span><span class="sxs-lookup"><span data-stu-id="12307-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

