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
# <a name="deploy-high-availability-and-disaster-recovery"></a>部署高可用性和灾难恢复
 
Skype for Business Server 通过服务器池、通过池配对进行灾难恢复以及多种模式的后端服务器高可用性（包括 AlwaysOn 可用性组、数据库镜像和 SQL群集）提供高可用性。 
  
高可用性是指确保 Skype for Business Server 服务可用，即使一台或多台服务器不可用。灾难恢复是指在自然或人为灾难时使服务继续工作，并尽可能保留灾难之前尽可能多的数据。
  
本节介绍了如何部署这些功能，还介绍了您可以为某些其他服务器角色的高可用性和灾难恢复采取哪些步骤。

> [!NOTE]
> SQL镜像在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和 SQL 故障转移群集方法是 Skype for Business Server 2019 的首选。
  
## <a name="related-sections"></a>相关章节

[在 Skype for Business Server 中规划高可用性和灾难恢复](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a>另请参阅

[在 Skype for Business Server 的后端服务器上部署 AlwaysOn 可用性组](alwayson-availability-group.md)

[在 Skype for Business Server 中部署配对前端池进行灾难恢复](front-end-pools-for-disaster-recovery.md)
  
[在 skype SQL Server 2015 中部署后端服务器高可用性的镜像](sql-mirroring-for-high-availability.md)
  
