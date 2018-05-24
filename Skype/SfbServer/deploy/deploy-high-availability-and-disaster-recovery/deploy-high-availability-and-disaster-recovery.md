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
ms.openlocfilehash: 91324a4bbc0c6a2439a3190661320165670a6e11
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="83523-103">部署高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="83523-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="83523-104">Skype for Business Server 提供了采用服务器池化的高可用性、采用池配对的灾难恢复，以及多种模式的后端服务器高可用性，包括 AlwaysOn 可用性组、数据库镜像和 SQL 故障转移群集。</span><span class="sxs-lookup"><span data-stu-id="83523-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availibility, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="83523-105">高可用性指的是确保业务 Server 服务的 Skype 有，即使一个或多个服务器不可用。灾难恢复是指保留服务发生自然或 human 导致灾难时，并保留尽可能灾难发生之前从尽可能数据。</span><span class="sxs-lookup"><span data-stu-id="83523-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="83523-106">本节介绍如何部署这些功能，还介绍了为其他一些服务器角色实现高可用性和灾难恢复所需执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="83523-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="83523-107">相关的章节</span><span class="sxs-lookup"><span data-stu-id="83523-107">Related sections</span></span>

[<span data-ttu-id="83523-108">规划业务服务器 2015 Skype 中的高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="83523-108">Plan for high availability and disaster recovery in Skype for Business Server 2015</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="83523-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="83523-109">See also</span></span>

#### 

[<span data-ttu-id="83523-110">部署业务服务器 2015年中 Skype 的后端服务器上的 AlwaysOn 可用性组</span><span class="sxs-lookup"><span data-stu-id="83523-110">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server 2015</span></span>](alwayson-availability-group.md)

[<span data-ttu-id="83523-111">为业务服务器 2015年部署已配对的前端池 Skype 中的灾难恢复</span><span class="sxs-lookup"><span data-stu-id="83523-111">Deploy paired Front End pools for disaster recovery in Skype for Business Server 2015</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="83523-112">部署 SQL 镜像的后端服务器高可用性 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="83523-112">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
[<span data-ttu-id="83523-113">为业务服务器 2015年对于 Persistent Chat Server in Skype 配置高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="83523-113">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

