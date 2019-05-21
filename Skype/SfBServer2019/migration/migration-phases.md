---
title: 迁移阶段
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 在 Skype for Business Server 2019 中, 你可以在网络上定义包含 Skype for Business Server 2019 组件的网站。 站点是一组计算机, 这些计算机通过高速、低延迟网络连接, 如单个局域网 (LAN) 或通过高速光纤网络连接的两个网络。
ms.openlocfilehash: 8f50f25536e330a03440702614f81c09ce74518a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298160"
---
# <a name="migration-phases"></a><span data-ttu-id="63125-104">迁移阶段</span><span class="sxs-lookup"><span data-stu-id="63125-104">Migration phases</span></span>

<span data-ttu-id="63125-105">在 Skype for Business Server 2019 中, 你可以在网络上定义包含 Skype for Business Server 2019 组件的网站。</span><span class="sxs-lookup"><span data-stu-id="63125-105">In Skype for Business Server 2019, you define sites on your network that contain Skype for Business Server 2019 components.</span></span> <span data-ttu-id="63125-106">站点是一组计算机, 这些计算机通过高速、低延迟网络连接, 如单个局域网 (LAN) 或通过高速光纤网络连接的两个网络。</span><span class="sxs-lookup"><span data-stu-id="63125-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> 
  
<span data-ttu-id="63125-107">前端池是一组前端服务器, 这些服务器配置相同, 并且协同工作以提供一组通用用户的服务。</span><span class="sxs-lookup"><span data-stu-id="63125-107">A Front End pool is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="63125-108">池为你的用户提供了可伸缩性和故障转移功能。</span><span class="sxs-lookup"><span data-stu-id="63125-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="63125-109">池中的每台服务器必须运行一个或多个相同的服务器角色。</span><span class="sxs-lookup"><span data-stu-id="63125-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="63125-110">适用于小型组织的标准版服务器还定义了一个池并在单个服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="63125-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="63125-111">这使您能够以更低的成本购买 Skype for Business Server 2019 功能, 但不提供真正高可用性的解决方案。</span><span class="sxs-lookup"><span data-stu-id="63125-111">This enables you to have Skype for Business Server 2019 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span> 
  
<span data-ttu-id="63125-112">以下阶段介绍了到 Skype for business Server 2019 的池迁移过程。</span><span class="sxs-lookup"><span data-stu-id="63125-112">The following phases describe the process of a pool migration to Skype for Business Server 2019.</span></span> <span data-ttu-id="63125-113">对于包含多个池的多个网站, 每个单独的池应遵循这种分段方法。</span><span class="sxs-lookup"><span data-stu-id="63125-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>
  
1. [<span data-ttu-id="63125-114">第 1 阶段：规划迁移</span><span class="sxs-lookup"><span data-stu-id="63125-114">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
2. [<span data-ttu-id="63125-115">第 2 阶段：准备迁移</span><span class="sxs-lookup"><span data-stu-id="63125-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
3. [<span data-ttu-id="63125-116">第3阶段: 部署 Skype for Business Server 2019 试用版池</span><span class="sxs-lookup"><span data-stu-id="63125-116">Phase 3: Deploy Skype for Business Server 2019 pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
4. [<span data-ttu-id="63125-117">第4阶段: 将测试用户移动到试验池</span><span class="sxs-lookup"><span data-stu-id="63125-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [<span data-ttu-id="63125-118">第5阶段: 将 Skype for Business Server 2019 边缘服务器添加到试验池</span><span class="sxs-lookup"><span data-stu-id="63125-118">Phase 5: Add Skype for Business Server 2019 Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [<span data-ttu-id="63125-119">第 6 阶段：从试点部署移动到生产中</span><span class="sxs-lookup"><span data-stu-id="63125-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [<span data-ttu-id="63125-120">第 7 阶段：完成迁移后任务</span><span class="sxs-lookup"><span data-stu-id="63125-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
8. [<span data-ttu-id="63125-121">第 8 阶段：停用旧池</span><span class="sxs-lookup"><span data-stu-id="63125-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

