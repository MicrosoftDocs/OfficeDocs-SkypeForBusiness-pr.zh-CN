---
title: 规划业务 Server Skype 中的高可用性和灾难恢复
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype 业务服务器与池，池配对，与后端服务器高可用性，包括 AlwaysOn 可用性组、 数据库镜像，和 SQL 故障转移群集的几种模式下的灾难恢复的服务器提供高可用性。
ms.openlocfilehash: 94db95c097fca62e31a01efd1d254ab6d3cd6d37
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20996457"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="295c8-103">规划业务 Server Skype 中的高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="295c8-103">Plan for high availability and disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="295c8-104">Skype 业务服务器与池，池配对，与后端服务器高可用性，包括 AlwaysOn 可用性组、 数据库镜像，和 SQL 故障转移群集的几种模式下的灾难恢复的服务器提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="295c8-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="295c8-105">高可用性指的是确保业务 Server 服务的 Skype 有，即使一个或多个服务器不可用。</span><span class="sxs-lookup"><span data-stu-id="295c8-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="295c8-106">灾难恢复指的是在出现自然或人为灾难时，维持服务运行并在灾难发生之前保留尽可能多的数据。</span><span class="sxs-lookup"><span data-stu-id="295c8-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="295c8-107">与以前版本的 Lync Server，Skype 业务服务器中的大多数服务器角色的主高可用性功能是通过池服务器冗余性。</span><span class="sxs-lookup"><span data-stu-id="295c8-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="295c8-108">如果运行特定服务器角色的服务器发生故障，则池中运行相同角色的其他服务器将承担该服务器的负载。</span><span class="sxs-lookup"><span data-stu-id="295c8-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="295c8-109">这适用于前端服务器、边缘服务器、中介服务器和控制器。</span><span class="sxs-lookup"><span data-stu-id="295c8-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="295c8-110">Skype 业务服务器还提供灾难恢复选项的前端池。</span><span class="sxs-lookup"><span data-stu-id="295c8-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="295c8-111">你可以在不同的地区设置两个池以相互充当备用池。</span><span class="sxs-lookup"><span data-stu-id="295c8-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="295c8-112">然后，如果你的整个池或站点出现故障，备用池可以继续为两个站点的用户提供服务。</span><span class="sxs-lookup"><span data-stu-id="295c8-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="295c8-113">Skype 业务 server 还支持您的后端服务器的高可用性的四种模式： SQL 镜像，AlwaysOn 可用性组、 AlwaysOn 故障转移群集实例 (FCI)，和 SQL 故障转移群集。</span><span class="sxs-lookup"><span data-stu-id="295c8-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: SQL mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="295c8-114">SQL 镜像的业务服务器 2015 Skype 中可用，但业务服务器 2019年不再支持在 Skype。</span><span class="sxs-lookup"><span data-stu-id="295c8-114">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="295c8-115">AlwaysOn 可用性组、 AlwaysOn 故障转移群集实例 (FCI)，和 SQL 故障转移群集方法是首选与 Skype 的业务服务器 2019年。</span><span class="sxs-lookup"><span data-stu-id="295c8-115">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="295c8-116">与持久聊天服务器不支持 AlwaysOn 可用性组。</span><span class="sxs-lookup"><span data-stu-id="295c8-116">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="295c8-117">本节对这些功能进行了说明，还介绍了为其他一些服务器角色实现高可用性和灾难恢复所需执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="295c8-117">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="295c8-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="295c8-118">See also</span></span>

[<span data-ttu-id="295c8-119">前端池高可用性和管理</span><span class="sxs-lookup"><span data-stu-id="295c8-119">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="295c8-120">为业务 Server 前端中 Skype 的最终池灾难恢复</span><span class="sxs-lookup"><span data-stu-id="295c8-120">Front End pool disaster recovery in Skype for Business Server</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="295c8-121">业务服务器中 Skype 的池故障期间的用户体验</span><span class="sxs-lookup"><span data-stu-id="295c8-121">User experience during pool failure in Skype for Business Server</span></span>](user-experience.md)
  
[<span data-ttu-id="295c8-122">后端服务器高可用性 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="295c8-122">Back End Server high availability in Skype for Business Server</span></span>](back-end-server.md)
  
[<span data-ttu-id="295c8-123">为业务 Server Skype 中文件共享高可用性</span><span class="sxs-lookup"><span data-stu-id="295c8-123">File sharing high availability in Skype for Business Server</span></span>](file-sharing.md)