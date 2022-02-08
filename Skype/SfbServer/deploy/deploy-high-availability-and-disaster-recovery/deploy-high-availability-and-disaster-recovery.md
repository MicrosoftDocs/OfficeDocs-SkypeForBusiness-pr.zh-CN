---
title: 部署高可用性和灾难恢复
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype for Business Server服务器池、通过池配对进行灾难恢复以及多种模式的后端服务器高可用性（包括 AlwaysOn 可用性组、数据库镜像和故障转移群集）SQL高可用性。
ms.openlocfilehash: df77652840c127e011042172f618eba37d916f85
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394320"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a>部署高可用性和灾难恢复
 
Skype for Business Server服务器池、通过池配对进行灾难恢复以及多种模式的后端服务器高可用性（包括 AlwaysOn 可用性组、数据库镜像和故障转移群集）SQL高可用性。 
  
高可用性是指确保 Skype for Business Server服务可用，即使一个或多个服务器不可用。灾难恢复是指在发生自然或人为灾难时使服务继续工作，并尽可能保留灾难发生之前尽可能多的数据。
  
本节介绍了如何部署这些功能，还介绍了您可以采取哪些步骤实现某些其他服务器角色的高可用性和灾难恢复。

> [!NOTE]
> SQL镜像在 Skype for Business Server 2015 中可用，但在 2019 年 2 月不再Skype for Business Server支持。 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和 SQL 故障转移群集方法在 Skype for Business Server 2019 中是首选。
  
## <a name="related-sections"></a>相关部分

[规划 Skype for Business Server 中的高可用性和Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a>另请参阅

[在 Skype for Business Server 中的后端服务器上部署 AlwaysOn 可用性Skype for Business Server](alwayson-availability-group.md)

[部署配对的前端池，以在 Skype for Business Server](front-end-pools-for-disaster-recovery.md)
  
[Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015](sql-mirroring-for-high-availability.md)
  
