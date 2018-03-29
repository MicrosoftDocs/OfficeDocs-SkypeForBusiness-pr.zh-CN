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
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中规划高可用性和灾难恢复
 
Skype 业务服务器与池，与池中的配对和后端服务器的高可用性，包括 AlwaysOn 可用性组、 数据库镜像和 SQL 故障切换群集的几种模式的灾难恢复服务器提供高可用性。 
  
高可用性是指即使一个或多个服务器出现故障，确保 Skype 业务服务器服务可用。 灾难恢复指的是在出现自然或人为灾难时，维持服务运行并在灾难发生之前保留尽可能多的数据。
  
与以前版本的 Lync Server，Skype 业务服务器中的大多数服务器角色的主要的高可用性功能是通过共用服务器冗余。 如果运行特定服务器角色的服务器发生故障，则池中运行相同角色的其他服务器将承担该服务器的负载。 这适用于前端服务器、边缘服务器、中介服务器和控制器。
  
Skype 业务服务器还提供灾难恢复选项的前端池。 你可以在不同的地区设置两个池以相互充当备用池。 然后，如果你的整个池或站点出现故障，备用池可以继续为两个站点的用户提供服务。
  
Skype 业务服务器还支持后端服务器的高可用性的四种模式： 数据库镜像、 AlwaysOn 可用性组、 AlwaysOn 故障转移群集实例 (FCI)，以及 SQL 故障切换群集。
  
> [!NOTE]
> AlwaysOn 可用性组与持久聊天服务器不支持。 
  
本节对这些功能进行了说明，还介绍了为其他一些服务器角色实现高可用性和灾难恢复所需执行的步骤。 
  
## <a name="see-also"></a>另请参阅

#### 

[前结束池高可用性和管理](high-availability.md)
  
[为业务服务器 2015年前结束池在 Skype 的灾难恢复](disaster-recovery.md)
  
[业务服务器 2015年期间池失败在 Skype 的用户体验](user-experience.md)
  
[在 Skype 业务服务器 2015年的后端服务器高可用性](back-end-server.md)
  
[在 Skype 业务服务器 2015年文件共享的高可用性](file-sharing.md)

