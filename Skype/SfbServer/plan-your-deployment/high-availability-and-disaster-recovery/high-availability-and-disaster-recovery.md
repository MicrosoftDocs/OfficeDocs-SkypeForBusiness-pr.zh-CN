---
title: 在 Skype for Business Server 2015 中规划高可用性和灾难恢复
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 1/29/2018
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype 业务服务器与池，与池中的配对和后端服务器的高可用性，包括 AlwaysOn 可用性组、 数据库镜像和 SQL 故障切换群集的几种模式的灾难恢复服务器提供高可用性。
ms.openlocfilehash: e2e433112146e3be771abb12ef50e09749e8e325
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server-2015"></a><span data-ttu-id="7ed41-103">在 Skype for Business Server 2015 中规划高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="7ed41-103">Plan for high availability and disaster recovery in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7ed41-104">Skype 业务服务器与池，与池中的配对和后端服务器的高可用性，包括 AlwaysOn 可用性组、 数据库镜像和 SQL 故障切换群集的几种模式的灾难恢复服务器提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="7ed41-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="7ed41-105">高可用性是指即使一个或多个服务器出现故障，确保 Skype 业务服务器服务可用。</span><span class="sxs-lookup"><span data-stu-id="7ed41-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="7ed41-106">灾难恢复指的是在出现自然或人为灾难时，维持服务运行并在灾难发生之前保留尽可能多的数据。</span><span class="sxs-lookup"><span data-stu-id="7ed41-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="7ed41-107">与以前版本的 Lync Server，Skype 业务服务器中的大多数服务器角色的主要的高可用性功能是通过共用服务器冗余。</span><span class="sxs-lookup"><span data-stu-id="7ed41-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="7ed41-108">如果运行特定服务器角色的服务器发生故障，则池中运行相同角色的其他服务器将承担该服务器的负载。</span><span class="sxs-lookup"><span data-stu-id="7ed41-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="7ed41-109">这适用于前端服务器、边缘服务器、中介服务器和控制器。</span><span class="sxs-lookup"><span data-stu-id="7ed41-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="7ed41-110">Skype 业务服务器还提供灾难恢复选项的前端池。</span><span class="sxs-lookup"><span data-stu-id="7ed41-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="7ed41-111">你可以在不同的地区设置两个池以相互充当备用池。</span><span class="sxs-lookup"><span data-stu-id="7ed41-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="7ed41-112">然后，如果你的整个池或站点出现故障，备用池可以继续为两个站点的用户提供服务。</span><span class="sxs-lookup"><span data-stu-id="7ed41-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="7ed41-113">Skype 业务服务器还支持后端服务器的高可用性的四种模式： 数据库镜像、 AlwaysOn 可用性组、 AlwaysOn 故障转移群集实例 (FCI)，以及 SQL 故障切换群集。</span><span class="sxs-lookup"><span data-stu-id="7ed41-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: database mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7ed41-114">AlwaysOn 可用性组与持久聊天服务器不支持。</span><span class="sxs-lookup"><span data-stu-id="7ed41-114">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="7ed41-115">本节对这些功能进行了说明，还介绍了为其他一些服务器角色实现高可用性和灾难恢复所需执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="7ed41-115">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7ed41-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ed41-116">See also</span></span>

#### 

[<span data-ttu-id="7ed41-117">前结束池高可用性和管理</span><span class="sxs-lookup"><span data-stu-id="7ed41-117">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="7ed41-118">为业务服务器 2015年前结束池在 Skype 的灾难恢复</span><span class="sxs-lookup"><span data-stu-id="7ed41-118">Front End pool disaster recovery in Skype for Business Server 2015</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="7ed41-119">业务服务器 2015年期间池失败在 Skype 的用户体验</span><span class="sxs-lookup"><span data-stu-id="7ed41-119">User experience during pool failure in Skype for Business Server 2015</span></span>](user-experience.md)
  
[<span data-ttu-id="7ed41-120">在 Skype 业务服务器 2015年的后端服务器高可用性</span><span class="sxs-lookup"><span data-stu-id="7ed41-120">Back End Server high availability in Skype for Business Server 2015</span></span>](back-end-server.md)
  
[<span data-ttu-id="7ed41-121">在 Skype 业务服务器 2015年文件共享的高可用性</span><span class="sxs-lookup"><span data-stu-id="7ed41-121">File sharing high availability in Skype for Business Server 2015</span></span>](file-sharing.md)

