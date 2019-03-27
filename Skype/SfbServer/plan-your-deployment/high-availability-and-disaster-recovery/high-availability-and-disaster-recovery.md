---
title: 规划业务 Server Skype 中的高可用性和灾难恢复
ms.reviewer: ''
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
ms.openlocfilehash: 9e48fa65572dea5c0e6a297397d2a502cefcdc36
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875255"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a>规划业务 Server Skype 中的高可用性和灾难恢复
 
Skype 业务服务器与池，池配对，与后端服务器高可用性，包括 AlwaysOn 可用性组、 数据库镜像，和 SQL 故障转移群集的几种模式下的灾难恢复的服务器提供高可用性。 
  
高可用性指的是确保业务 Server 服务的 Skype 有，即使一个或多个服务器不可用。 Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.
  
与以前版本的 Lync Server，Skype 业务服务器中的大多数服务器角色的主高可用性功能是通过池服务器冗余性。 如果运行特定服务器角色的服务器发生故障，则池中运行相同角色的其他服务器将承担该服务器的负载。 这适用于前端服务器、边缘服务器、中介服务器和控制器。
  
Skype 业务服务器还提供灾难恢复选项的前端池。 你可以在不同的地区设置两个池以相互充当备用池。 然后，如果你的整个池或站点出现故障，备用池可以继续为两个站点的用户提供服务。
  
Skype 业务 server 还支持您的后端服务器的高可用性的四种模式： SQL 镜像，AlwaysOn 可用性组、 AlwaysOn 故障转移群集实例 (FCI)，和 SQL 故障转移群集。
  
> [!NOTE]
> SQL 镜像的业务服务器 2015 Skype 中可用，但业务服务器 2019年不再支持在 Skype。 AlwaysOn 可用性组、 AlwaysOn 故障转移群集实例 (FCI)，和 SQL 故障转移群集方法是首选与 Skype 的业务服务器 2019年。

> [!NOTE]
> 与持久聊天服务器不支持 AlwaysOn 可用性组。 
  
本节对这些功能进行了说明，还介绍了为其他一些服务器角色实现高可用性和灾难恢复所需执行的步骤。 
  
## <a name="see-also"></a>另请参阅

[前端池高可用性和管理](high-availability.md)
  
[为业务 Server 前端中 Skype 的最终池灾难恢复](disaster-recovery.md)
  
[业务服务器中 Skype 的池故障期间的用户体验](user-experience.md)
  
[后端服务器高可用性 Skype 业务服务器](back-end-server.md)
  
[为业务 Server Skype 中文件共享高可用性](file-sharing.md)
