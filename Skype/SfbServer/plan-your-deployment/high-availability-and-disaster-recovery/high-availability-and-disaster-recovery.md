---
title: 规划 Skype for Business Server 中的高可用性和Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.custom:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype for Business Server服务器池、通过池配对进行灾难恢复以及多种模式的后端服务器高可用性（包括 AlwaysOn 可用性组、数据库镜像和故障转移群集）SQL高可用性。
ms.openlocfilehash: ef5275ccb11e6428a4084bec1b7f2f0b2dddcd5f
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62416455"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a>规划 Skype for Business Server 中的高可用性和Skype for Business Server
 
Skype for Business Server服务器池、通过池配对进行灾难恢复以及多种模式的后端服务器高可用性（包括 AlwaysOn 可用性组、数据库镜像和故障转移群集）SQL高可用性。 
  
高可用性是指确保 Skype for Business Server服务可用，即使一个或多个服务器不可用。 灾难恢复是指在发生自然或人为灾难时使服务继续工作，并尽可能保留灾难发生之前尽可能多的数据。
  
与以前版本的 Lync Server 一样，Lync Server 中大多数服务器角色的主要高可用性功能Skype for Business Server池实现服务器冗余。 如果运行特定服务器角色的服务器发生故障，那么池中运行同一角色的其他服务器将接纳该服务器的负荷。 这适用于前端服务器、边缘服务器、中介服务器和控制器。
  
Skype for Business Server还提供了前端池的灾难恢复选项。 您可以在不同地理区域设置两个池，以相互用作备份。 然后，如果整个池或站点关闭，备份池可以继续为两个站点的用户提供服务。
  
Skype for Business Server还支持后端服务器的四种高可用性模式：SQL 镜像、AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和 SQL 故障转移群集。
  
> [!NOTE]
> SQL镜像在 Skype for Business Server 2015 中可用，但在 2019 年 2 月不再Skype for Business Server支持。 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和 SQL 故障转移群集方法在 Skype for Business Server 2019 中是首选。

> [!NOTE]
> 持久聊天服务器不支持 AlwaysOn 可用性组。 
  
本节介绍这些功能，还介绍了您可以为某些其他服务器角色实现高可用性和灾难恢复而执行的步骤。 
  
## <a name="see-also"></a>另请参阅

[前端池高可用性和管理](high-availability.md)
  
[前端池的灾难恢复Skype for Business Server](disaster-recovery.md)
  
[池中池故障期间Skype for Business Server](user-experience.md)
  
[后端服务器高可用性Skype for Business Server](back-end-server.md)
  
[文件共享高可用性Skype for Business Server](file-sharing.md)
