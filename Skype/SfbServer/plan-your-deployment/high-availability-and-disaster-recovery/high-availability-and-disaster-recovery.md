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
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a>在 Skype for Business Server 中规划高可用性和灾难恢复
 
Skype for Business Server 通过服务器池、通过池配对进行灾难恢复以及多种模式的后端服务器高可用性（包括 AlwaysOn 可用性组、数据库镜像和 SQL群集）提供高可用性。 
  
高可用性是指确保 Skype for Business Server 服务可用，即使一台或多台服务器不可用。 灾难恢复是指在自然或人为灾难时使服务继续工作，并尽可能保留灾难之前尽可能多的数据。
  
与早期版本的 Lync Server 一样，Skype for Business Server 中大多数服务器角色的主要高可用性功能是通过池实现服务器冗余。 如果运行特定服务器角色的服务器发生故障，那么池中运行同一角色的其他服务器将接纳该服务器的负荷。 这适用于前端服务器、边缘服务器、中介服务器和控制器。
  
Skype for Business Server 还为前端池提供灾难恢复选项。 您可以在不同的地理区域设置两个池，以用作彼此的备份。 然后，如果整个池或站点关闭，备份池可以继续为两个站点的用户提供服务。
  
Skype for Business Server 还支持后端服务器的四种高可用性模式：SQL 镜像、AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和 SQL 故障转移群集。
  
> [!NOTE]
> SQL镜像在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和 SQL 故障转移群集方法是 Skype for Business Server 2019 的首选。

> [!NOTE]
> 持久聊天服务器不支持 AlwaysOn 可用性组。 
  
本节介绍这些功能，还介绍了您可以为某些其他服务器角色实现高可用性和灾难恢复所执行的步骤。 
  
## <a name="see-also"></a>另请参阅

[前端池高可用性和管理](high-availability.md)
  
[Skype for Business Server 中的前端池灾难恢复](disaster-recovery.md)
  
[Skype for Business Server 中的池故障期间用户体验](user-experience.md)
  
[Skype for Business Server 中的后端服务器高可用性](back-end-server.md)
  
[Skype for Business Server 中的文件共享高可用性](file-sharing.md)
