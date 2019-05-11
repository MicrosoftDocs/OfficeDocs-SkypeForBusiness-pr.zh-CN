---
title: 部署高可用性和灾难恢复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype 业务服务器与池，池配对，与后端服务器高可用性，包括 AlwaysOn 可用性组、 数据库镜像，和 SQL 故障转移群集的几种模式下的灾难恢复的服务器提供高可用性。
ms.openlocfilehash: 96e1f0614aac72197f0b34b8432b65d2c859c4ed
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894589"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="96a67-103">部署高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="96a67-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="96a67-104">Skype 业务服务器与池，池配对，与后端服务器高可用性，包括 AlwaysOn 可用性组、 数据库镜像，和 SQL 故障转移群集的几种模式下的灾难恢复的服务器提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="96a67-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="96a67-105">高可用性指的是确保业务 Server 服务的 Skype 有，即使一个或多个服务器不可用。灾难恢复是指保留服务发生自然或 human 导致灾难时，并保留尽可能灾难发生之前从尽可能数据。</span><span class="sxs-lookup"><span data-stu-id="96a67-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="96a67-106">本节介绍如何部署这些功能，还介绍了为其他一些服务器角色实现高可用性和灾难恢复所需执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="96a67-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>

> [!NOTE]
> <span data-ttu-id="96a67-107">SQL 镜像的业务服务器 2015 Skype 中可用，但业务服务器 2019年不再支持在 Skype。</span><span class="sxs-lookup"><span data-stu-id="96a67-107">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="96a67-108">AlwaysOn 可用性组、 AlwaysOn 故障转移群集实例 (FCI)，和 SQL 故障转移群集方法是首选与 Skype 的业务服务器 2019年。</span><span class="sxs-lookup"><span data-stu-id="96a67-108">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="96a67-109">相关的章节</span><span class="sxs-lookup"><span data-stu-id="96a67-109">Related sections</span></span>

[<span data-ttu-id="96a67-110">规划业务 Server Skype 中的高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="96a67-110">Plan for high availability and disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="96a67-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96a67-111">See also</span></span>

[<span data-ttu-id="96a67-112">为业务服务器部署中 Skype 的后端服务器上的 AlwaysOn 可用性组</span><span class="sxs-lookup"><span data-stu-id="96a67-112">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server</span></span>](alwayson-availability-group.md)

[<span data-ttu-id="96a67-113">为业务服务器部署已配对的前端池 Skype 中的灾难恢复</span><span class="sxs-lookup"><span data-stu-id="96a67-113">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="96a67-114">在 Skype for Business Server 2015 中针对后端服务器高可用性部署 SQL 镜像</span><span class="sxs-lookup"><span data-stu-id="96a67-114">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
