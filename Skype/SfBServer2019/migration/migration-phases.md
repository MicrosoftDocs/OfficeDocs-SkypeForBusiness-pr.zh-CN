---
title: 迁移阶段
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 在业务服务器 2019年的 Skype，业务服务器 2019年组件包含 Skype 网络上定义的网站。 网站是一组由高速、 低延迟网络，如单个局域网 (LAN) 或由高速光纤光纤网络连接的两个网络连接良好的计算机。
ms.openlocfilehash: d34351b551262450dee852efd7679f17cbe1e161
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886525"
---
# <a name="migration-phases"></a><span data-ttu-id="c34e5-104">迁移阶段</span><span class="sxs-lookup"><span data-stu-id="c34e5-104">Migration phases</span></span>

<span data-ttu-id="c34e5-105">在业务服务器 2019年的 Skype，业务服务器 2019年组件包含 Skype 网络上定义的网站。</span><span class="sxs-lookup"><span data-stu-id="c34e5-105">In Skype for Business Server 2019, you define sites on your network that contain Skype for Business Server 2019 components.</span></span> <span data-ttu-id="c34e5-106">网站是一组由高速、 低延迟网络，如单个局域网 (LAN) 或由高速光纤光纤网络连接的两个网络连接良好的计算机。</span><span class="sxs-lookup"><span data-stu-id="c34e5-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> 
  
<span data-ttu-id="c34e5-107">前端池是一组配置相同的前端服务器和工作同时为公用组用户提供服务。</span><span class="sxs-lookup"><span data-stu-id="c34e5-107">A Front End pool is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="c34e5-108">池向用户提供可伸缩性和故障转移功能。</span><span class="sxs-lookup"><span data-stu-id="c34e5-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="c34e5-109">池中的每台服务器必须运行一个或多个相同的服务器角色。</span><span class="sxs-lookup"><span data-stu-id="c34e5-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="c34e5-110">Standard Edition server，小型组织的设计还定义一个池，并在单台服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="c34e5-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="c34e5-111">这使您能够具有 Skype 业务服务器 2019年功能较少的成本，但并未提供，则返回 true 的高可用性解决方案。</span><span class="sxs-lookup"><span data-stu-id="c34e5-111">This enables you to have Skype for Business Server 2019 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span> 
  
<span data-ttu-id="c34e5-112">以下阶段介绍业务服务器 2019年池迁移到 Skype 的过程。</span><span class="sxs-lookup"><span data-stu-id="c34e5-112">The following phases describe the process of a pool migration to Skype for Business Server 2019.</span></span> <span data-ttu-id="c34e5-113">对于包含多个池的多个网站，每个个别池应该遵循此分阶段的方法。</span><span class="sxs-lookup"><span data-stu-id="c34e5-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>
  
1. [<span data-ttu-id="c34e5-114">第 1 阶段：规划迁移</span><span class="sxs-lookup"><span data-stu-id="c34e5-114">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
2. [<span data-ttu-id="c34e5-115">第 2 阶段：准备迁移</span><span class="sxs-lookup"><span data-stu-id="c34e5-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
3. [<span data-ttu-id="c34e5-116">第 3 阶段： 部署 Skype 业务服务器 2019年试点池</span><span class="sxs-lookup"><span data-stu-id="c34e5-116">Phase 3: Deploy Skype for Business Server 2019 pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
4. [<span data-ttu-id="c34e5-117">第 4 阶段： 将测试用户移至试点池</span><span class="sxs-lookup"><span data-stu-id="c34e5-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [<span data-ttu-id="c34e5-118">第 5 阶段： 将 Skype 业务 Server 2019 边缘服务器添加到试点池</span><span class="sxs-lookup"><span data-stu-id="c34e5-118">Phase 5: Add Skype for Business Server 2019 Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [<span data-ttu-id="c34e5-119">第 6 阶段：从试点部署移动到生产中</span><span class="sxs-lookup"><span data-stu-id="c34e5-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [<span data-ttu-id="c34e5-120">第 7 阶段：完成迁移后任务</span><span class="sxs-lookup"><span data-stu-id="c34e5-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
8. [<span data-ttu-id="c34e5-121">第 8 阶段：停用旧池</span><span class="sxs-lookup"><span data-stu-id="c34e5-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

