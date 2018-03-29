---
title: 部署高可用性和灾难恢复
ms.author: heidip
author: microsoftheidi
ms.date: 9/1/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype for Business Server 提供了采用服务器池化的高可用性、采用池配对的灾难恢复，以及多种模式的后端服务器高可用性，包括 AlwaysOn 可用性组、数据库镜像和 SQL 故障转移群集。
ms.openlocfilehash: f8f7916a48f6aa03c51d78cfb99aa81bc220ab30
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="87a14-103">部署高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="87a14-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="87a14-104">Skype for Business Server 提供了采用服务器池化的高可用性、采用池配对的灾难恢复，以及多种模式的后端服务器高可用性，包括 AlwaysOn 可用性组、数据库镜像和 SQL 故障转移群集。</span><span class="sxs-lookup"><span data-stu-id="87a14-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availibility, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="87a14-105">高可用性是指即使一个或多个服务器出现故障，确保 Skype 业务服务器服务可用。灾难恢复指的是保持服务在发生自然或人类造成灾难，并保留尽可能灾难之前尽可能多的数据。</span><span class="sxs-lookup"><span data-stu-id="87a14-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="87a14-106">本节介绍如何部署这些功能，还介绍了为其他一些服务器角色实现高可用性和灾难恢复所需执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="87a14-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="87a14-107">相关的章节</span><span class="sxs-lookup"><span data-stu-id="87a14-107">Related sections</span></span>

[<span data-ttu-id="87a14-108">在 Skype 的高可用性和灾难恢复规划的业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="87a14-108">Plan for high availability and disaster recovery in Skype for Business Server 2015</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="87a14-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87a14-109">See also</span></span>

#### 

[<span data-ttu-id="87a14-110">AlwaysOn 可用性组在 Skype 的后端服务器上部署业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="87a14-110">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server 2015</span></span>](alwayson-availability-group.md)
#### 

[<span data-ttu-id="87a14-111">为业务服务器 2015年部署成对的前端池在 Skype 的灾难恢复</span><span class="sxs-lookup"><span data-stu-id="87a14-111">Deploy paired Front End pools for disaster recovery in Skype for Business Server 2015</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="87a14-112">部署 SQL 后端服务器高可用性在 Skype 业务服务器 2015年镜像</span><span class="sxs-lookup"><span data-stu-id="87a14-112">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
[<span data-ttu-id="87a14-113">为业务服务器 2015年配置在 Skype 的持久聊天服务器的高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="87a14-113">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

