---
title: 部署高可用性和灾难恢复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: 'Skype for Business 服务器提供高可用性: 服务器池、具有池配对的灾难恢复以及后台服务器高可用性的几种模式, 包括 AlwaysOn 可用性组、数据库镜像和 SQL 故障转移群集。'
ms.openlocfilehash: 7997f71fb1f45801436caa50c4d6b258cc1b843b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306676"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="00340-103">部署高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="00340-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="00340-104">Skype for Business 服务器提供高可用性: 服务器池、具有池配对的灾难恢复以及后台服务器高可用性的几种模式, 包括 AlwaysOn 可用性组、数据库镜像和 SQL 故障转移群集。</span><span class="sxs-lookup"><span data-stu-id="00340-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="00340-105">高可用性指确保 Skype for business 服务器服务可用, 即使一个或多个服务器出现故障。灾难恢复是指让服务在发生自然或人工导致灾难时, 并在灾难发生之前保留尽可能多的数据。</span><span class="sxs-lookup"><span data-stu-id="00340-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="00340-106">本节介绍如何部署这些功能，还介绍了为其他一些服务器角色实现高可用性和灾难恢复所需执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="00340-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>

> [!NOTE]
> <span data-ttu-id="00340-107">在 Skype for business Server 2015 中提供了 SQL 镜像, 但 Skype for Business Server 2019 不再支持 SQL 镜像。</span><span class="sxs-lookup"><span data-stu-id="00340-107">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="00340-108">适用于 Skype for Business Server 2019 的 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和 SQL 故障转移群集方法优先。</span><span class="sxs-lookup"><span data-stu-id="00340-108">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="00340-109">相关部分</span><span class="sxs-lookup"><span data-stu-id="00340-109">Related sections</span></span>

[<span data-ttu-id="00340-110">在 Skype for business 服务器中规划高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="00340-110">Plan for high availability and disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="00340-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00340-111">See also</span></span>

[<span data-ttu-id="00340-112">在 Skype for Business 服务器的后端服务器上部署 AlwaysOn 可用性组</span><span class="sxs-lookup"><span data-stu-id="00340-112">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server</span></span>](alwayson-availability-group.md)

[<span data-ttu-id="00340-113">在 Skype for business Server 中部署用于灾难恢复的配对的前端池</span><span class="sxs-lookup"><span data-stu-id="00340-113">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="00340-114">在 Skype for Business Server 2015 中针对后端服务器高可用性部署 SQL 镜像</span><span class="sxs-lookup"><span data-stu-id="00340-114">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
