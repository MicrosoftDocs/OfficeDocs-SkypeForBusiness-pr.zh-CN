---
title: 部署高可用性和灾难恢复
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype for Business Server 通过服务器池、通过池配对进行灾难恢复以及多种模式的后端服务器高可用性（包括 AlwaysOn 可用性组、数据库镜像和 SQL群集）提供高可用性。
ms.openlocfilehash: 68baae183ff45571e38e922035d287e733bcc930
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830612"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="2f363-103">部署高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="2f363-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="2f363-104">Skype for Business Server 通过服务器池、通过池配对进行灾难恢复以及多种模式的后端服务器高可用性（包括 AlwaysOn 可用性组、数据库镜像和 SQL群集）提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="2f363-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="2f363-105">高可用性是指确保 Skype for Business Server 服务可用，即使一台或多台服务器不可用。灾难恢复是指在自然或人为灾难时使服务继续工作，并尽可能保留灾难之前尽可能多的数据。</span><span class="sxs-lookup"><span data-stu-id="2f363-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="2f363-106">本节介绍了如何部署这些功能，还介绍了您可以为某些其他服务器角色的高可用性和灾难恢复采取哪些步骤。</span><span class="sxs-lookup"><span data-stu-id="2f363-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>

> [!NOTE]
> <span data-ttu-id="2f363-107">SQL镜像在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="2f363-107">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="2f363-108">AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和 SQL 故障转移群集方法是 Skype for Business Server 2019 的首选。</span><span class="sxs-lookup"><span data-stu-id="2f363-108">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="2f363-109">相关章节</span><span class="sxs-lookup"><span data-stu-id="2f363-109">Related sections</span></span>

[<span data-ttu-id="2f363-110">在 Skype for Business Server 中规划高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="2f363-110">Plan for high availability and disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="2f363-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f363-111">See also</span></span>

[<span data-ttu-id="2f363-112">在 Skype for Business Server 的后端服务器上部署 AlwaysOn 可用性组</span><span class="sxs-lookup"><span data-stu-id="2f363-112">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server</span></span>](alwayson-availability-group.md)

[<span data-ttu-id="2f363-113">在 Skype for Business Server 中部署配对前端池进行灾难恢复</span><span class="sxs-lookup"><span data-stu-id="2f363-113">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="2f363-114">在 skype SQL Server 2015 中部署后端服务器高可用性的镜像</span><span class="sxs-lookup"><span data-stu-id="2f363-114">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
