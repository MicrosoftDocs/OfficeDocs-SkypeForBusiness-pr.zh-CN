---
title: 在 Skype for business 服务器中规划高可用性和灾难恢复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype for Business 服务器提供高可用性：服务器池、具有池配对的灾难恢复以及后台服务器高可用性的几种模式，包括 AlwaysOn 可用性组、数据库镜像和 SQL 故障转移群集。
ms.openlocfilehash: 31059936249aa4e691f3e6b4b467841fd66a04ea
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695967"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="a06de-103">在 Skype for business 服务器中规划高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="a06de-103">Plan for high availability and disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="a06de-104">Skype for Business 服务器提供高可用性：服务器池、具有池配对的灾难恢复以及后台服务器高可用性的几种模式，包括 AlwaysOn 可用性组、数据库镜像和 SQL 故障转移群集。</span><span class="sxs-lookup"><span data-stu-id="a06de-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="a06de-105">高可用性指确保 Skype for business 服务器服务可用，即使一个或多个服务器出现故障。</span><span class="sxs-lookup"><span data-stu-id="a06de-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="a06de-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span><span class="sxs-lookup"><span data-stu-id="a06de-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="a06de-107">在 Lync Server 的早期版本中，Skype for Business 服务器中大多数服务器角色的主高可用性功能是通过池进行服务器冗余。</span><span class="sxs-lookup"><span data-stu-id="a06de-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="a06de-108">如果运行特定服务器角色的服务器发生故障，则池中运行相同角色的其他服务器将承担该服务器的负载。</span><span class="sxs-lookup"><span data-stu-id="a06de-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="a06de-109">这适用于前端服务器、边缘服务器、中介服务器和控制器。</span><span class="sxs-lookup"><span data-stu-id="a06de-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="a06de-110">Skype for business 服务器还提供前端池的灾难恢复选项。</span><span class="sxs-lookup"><span data-stu-id="a06de-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="a06de-111">你可以在不同的地区设置两个池以相互充当备用池。</span><span class="sxs-lookup"><span data-stu-id="a06de-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="a06de-112">然后，如果你的整个池或站点出现故障，备用池可以继续为两个站点的用户提供服务。</span><span class="sxs-lookup"><span data-stu-id="a06de-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="a06de-113">Skype for Business 服务器还支持后端服务器的四种高可用性模式： SQL 镜像、AlwaysOn 可用性组、AlwaysOn 故障转移群集实例（FCI）和 SQL 故障转移群集。</span><span class="sxs-lookup"><span data-stu-id="a06de-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: SQL mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a06de-114">在 Skype for Business Server 2015 中可以使用 SQL 镜像，但 Skype for Business Server 2019 不再支持该功能。</span><span class="sxs-lookup"><span data-stu-id="a06de-114">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="a06de-115">对于 Skype for Business Server 2019，首选 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和 SQL 故障转移群集方法。</span><span class="sxs-lookup"><span data-stu-id="a06de-115">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="a06de-116">永久聊天服务器不支持 AlwaysOn 可用性组。</span><span class="sxs-lookup"><span data-stu-id="a06de-116">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="a06de-117">本节对这些功能进行了说明，还介绍了为其他一些服务器角色实现高可用性和灾难恢复所需执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="a06de-117">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a06de-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a06de-118">See also</span></span>

[<span data-ttu-id="a06de-119">前端池高可用性和管理</span><span class="sxs-lookup"><span data-stu-id="a06de-119">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="a06de-120">Skype for Business 服务器中的前端池灾难恢复</span><span class="sxs-lookup"><span data-stu-id="a06de-120">Front End pool disaster recovery in Skype for Business Server</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="a06de-121">Skype for Business 服务器的池故障期间的用户体验</span><span class="sxs-lookup"><span data-stu-id="a06de-121">User experience during pool failure in Skype for Business Server</span></span>](user-experience.md)
  
[<span data-ttu-id="a06de-122">Skype for Business 服务器中的后端服务器高可用性</span><span class="sxs-lookup"><span data-stu-id="a06de-122">Back End Server high availability in Skype for Business Server</span></span>](back-end-server.md)
  
[<span data-ttu-id="a06de-123">Skype for Business 服务器中的文件共享高可用性</span><span class="sxs-lookup"><span data-stu-id="a06de-123">File sharing high availability in Skype for Business Server</span></span>](file-sharing.md)
