---
title: 在 Skype for Business Server 中规划高可用性和灾难恢复
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.custom:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype for Business Server 通过服务器池、通过池配对进行灾难恢复以及多种模式的后端服务器高可用性（包括 AlwaysOn 可用性组、数据库镜像和 SQL群集）提供高可用性。
ms.openlocfilehash: 61b720bc9dce5bc8dc54a6c493429b0a3c9b27d2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802812"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="ec261-103">在 Skype for Business Server 中规划高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="ec261-103">Plan for high availability and disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="ec261-104">Skype for Business Server 通过服务器池、通过池配对进行灾难恢复以及多种模式的后端服务器高可用性（包括 AlwaysOn 可用性组、数据库镜像和 SQL群集）提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="ec261-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="ec261-105">高可用性是指确保 Skype for Business Server 服务可用，即使一台或多台服务器不可用。</span><span class="sxs-lookup"><span data-stu-id="ec261-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="ec261-106">灾难恢复是指在自然或人为灾难时使服务继续工作，并尽可能保留灾难之前尽可能多的数据。</span><span class="sxs-lookup"><span data-stu-id="ec261-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="ec261-107">与早期版本的 Lync Server 一样，Skype for Business Server 中大多数服务器角色的主要高可用性功能是通过池实现服务器冗余。</span><span class="sxs-lookup"><span data-stu-id="ec261-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="ec261-108">如果运行特定服务器角色的服务器发生故障，那么池中运行同一角色的其他服务器将接纳该服务器的负荷。</span><span class="sxs-lookup"><span data-stu-id="ec261-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="ec261-109">这适用于前端服务器、边缘服务器、中介服务器和控制器。</span><span class="sxs-lookup"><span data-stu-id="ec261-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="ec261-110">Skype for Business Server 还为前端池提供灾难恢复选项。</span><span class="sxs-lookup"><span data-stu-id="ec261-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="ec261-111">您可以在不同的地理区域设置两个池，以用作彼此的备份。</span><span class="sxs-lookup"><span data-stu-id="ec261-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="ec261-112">然后，如果整个池或站点关闭，备份池可以继续为两个站点的用户提供服务。</span><span class="sxs-lookup"><span data-stu-id="ec261-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="ec261-113">Skype for Business Server 还支持后端服务器的四种高可用性模式：SQL 镜像、AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和 SQL 故障转移群集。</span><span class="sxs-lookup"><span data-stu-id="ec261-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: SQL mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ec261-114">SQL镜像在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="ec261-114">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="ec261-115">AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和 SQL 故障转移群集方法是 Skype for Business Server 2019 的首选。</span><span class="sxs-lookup"><span data-stu-id="ec261-115">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="ec261-116">持久聊天服务器不支持 AlwaysOn 可用性组。</span><span class="sxs-lookup"><span data-stu-id="ec261-116">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="ec261-117">本节介绍这些功能，还介绍了您可以为某些其他服务器角色实现高可用性和灾难恢复所执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="ec261-117">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ec261-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec261-118">See also</span></span>

[<span data-ttu-id="ec261-119">前端池高可用性和管理</span><span class="sxs-lookup"><span data-stu-id="ec261-119">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="ec261-120">Skype for Business Server 中的前端池灾难恢复</span><span class="sxs-lookup"><span data-stu-id="ec261-120">Front End pool disaster recovery in Skype for Business Server</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="ec261-121">Skype for Business Server 中的池故障期间用户体验</span><span class="sxs-lookup"><span data-stu-id="ec261-121">User experience during pool failure in Skype for Business Server</span></span>](user-experience.md)
  
[<span data-ttu-id="ec261-122">Skype for Business Server 中的后端服务器高可用性</span><span class="sxs-lookup"><span data-stu-id="ec261-122">Back End Server high availability in Skype for Business Server</span></span>](back-end-server.md)
  
[<span data-ttu-id="ec261-123">Skype for Business Server 中的文件共享高可用性</span><span class="sxs-lookup"><span data-stu-id="ec261-123">File sharing high availability in Skype for Business Server</span></span>](file-sharing.md)
