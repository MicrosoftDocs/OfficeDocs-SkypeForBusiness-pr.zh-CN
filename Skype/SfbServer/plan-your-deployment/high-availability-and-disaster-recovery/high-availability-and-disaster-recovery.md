---
title: 在 Skype for business 服务器中规划高可用性和灾难恢复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: 'Skype for Business 服务器提供高可用性: 服务器池、具有池配对的灾难恢复以及后台服务器高可用性的几种模式, 包括 AlwaysOn 可用性组、数据库镜像和 SQL 故障转移群集。'
ms.openlocfilehash: 3ed1a3e5eff5d793f835c901e2cc5683da22bc77
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297461"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a>在 Skype for business 服务器中规划高可用性和灾难恢复
 
Skype for Business 服务器提供高可用性: 服务器池、具有池配对的灾难恢复以及后台服务器高可用性的几种模式, 包括 AlwaysOn 可用性组、数据库镜像和 SQL 故障转移群集。 
  
高可用性指确保 Skype for business 服务器服务可用, 即使一个或多个服务器出现故障。 Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.
  
在 Lync Server 的早期版本中, Skype for Business 服务器中大多数服务器角色的主高可用性功能是通过池进行服务器冗余。 如果运行特定服务器角色的服务器发生故障，则池中运行相同角色的其他服务器将承担该服务器的负载。 这适用于前端服务器、边缘服务器、中介服务器和控制器。
  
Skype for business 服务器还提供前端池的灾难恢复选项。 你可以在不同的地区设置两个池以相互充当备用池。 然后，如果你的整个池或站点出现故障，备用池可以继续为两个站点的用户提供服务。
  
Skype for Business 服务器还支持后端服务器的四种高可用性模式: SQL 镜像、AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和 SQL 故障转移群集。
  
> [!NOTE]
> 在 Skype for business Server 2015 中提供了 SQL 镜像, 但 Skype for Business Server 2019 不再支持 SQL 镜像。 适用于 Skype for Business Server 2019 的 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和 SQL 故障转移群集方法优先。

> [!NOTE]
> 永久聊天服务器不支持 AlwaysOn 可用性组。 
  
本节对这些功能进行了说明，还介绍了为其他一些服务器角色实现高可用性和灾难恢复所需执行的步骤。 
  
## <a name="see-also"></a>另请参阅

[前端池高可用性和管理](high-availability.md)
  
[Skype for Business 服务器中的前端池灾难恢复](disaster-recovery.md)
  
[Skype for Business 服务器的池故障期间的用户体验](user-experience.md)
  
[Skype for Business 服务器中的后端服务器高可用性](back-end-server.md)
  
[Skype for Business 服务器中的文件共享高可用性](file-sharing.md)
