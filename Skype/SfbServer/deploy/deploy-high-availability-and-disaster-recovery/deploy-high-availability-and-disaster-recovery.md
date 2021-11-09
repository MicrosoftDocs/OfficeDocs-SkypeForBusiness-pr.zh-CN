---
title: 部署高可用性和灾难恢复
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype for Business Server通过服务器池、通过池配对进行灾难恢复以及多种模式的后端服务器高可用性（包括 AlwaysOn 可用性组、数据库镜像和 SQL群集）提供高可用性。
ms.openlocfilehash: 897bd52d265a123d3eebec2bc16d71d95ba6185e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60865299"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a>部署高可用性和灾难恢复
 
Skype for Business Server通过服务器池、通过池配对进行灾难恢复以及多种模式的后端服务器高可用性（包括 AlwaysOn 可用性组、数据库镜像和 SQL群集）提供高可用性。 
  
高可用性是指确保即使一Skype for Business Server台或多台服务器不可用，也可以使用高可用性服务。灾难恢复是指在发生自然或人为灾难时使服务继续工作，并尽可能保留灾难发生之前尽可能多的数据。
  
本节介绍了如何部署这些功能，还介绍了您可以采取哪些步骤实现某些其他服务器角色的高可用性和灾难恢复。

> [!NOTE]
> SQL镜像在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和 SQL 故障转移群集方法在 Skype for Business Server 2019 中是首选。
  
## <a name="related-sections"></a>相关部分

[规划 Skype for Business Server 中的高可用性和Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a>另请参阅

[在 Skype for Business Server 中的后端服务器上部署 AlwaysOn 可用性Skype for Business Server](alwayson-availability-group.md)

[部署配对的前端池，以在 Skype for Business Server](front-end-pools-for-disaster-recovery.md)
  
[Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015](sql-mirroring-for-high-availability.md)
  
