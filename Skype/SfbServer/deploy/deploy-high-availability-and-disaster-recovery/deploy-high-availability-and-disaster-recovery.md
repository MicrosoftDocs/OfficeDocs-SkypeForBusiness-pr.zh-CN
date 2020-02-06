---
title: 部署高可用性和灾难恢复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype for Business 服务器提供高可用性：服务器池、具有池配对的灾难恢复以及后台服务器高可用性的几种模式，包括 AlwaysOn 可用性组、数据库镜像和 SQL 故障转移群集。
ms.openlocfilehash: 68c6a12f80ac2d915c678f69146d0001daedbe5c
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790120"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a>部署高可用性和灾难恢复
 
Skype for Business 服务器提供高可用性：服务器池、具有池配对的灾难恢复以及后台服务器高可用性的几种模式，包括 AlwaysOn 可用性组、数据库镜像和 SQL 故障转移群集。 
  
高可用性指确保 Skype for business 服务器服务可用，即使一个或多个服务器出现故障。灾难恢复是指让服务在发生自然或人工导致灾难时，并在灾难发生之前保留尽可能多的数据。
  
本节介绍如何部署这些功能，还介绍了为其他一些服务器角色实现高可用性和灾难恢复所需执行的步骤。

> [!NOTE]
> 在 Skype for Business Server 2015 中可以使用 SQL 镜像，但 Skype for Business Server 2019 不再支持该功能。 对于 Skype for Business Server 2019，首选 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和 SQL 故障转移群集方法。
  
## <a name="related-sections"></a>相关部分

[在 Skype for business 服务器中规划高可用性和灾难恢复](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a>另请参阅

[在 Skype for Business 服务器的后端服务器上部署 AlwaysOn 可用性组](alwayson-availability-group.md)

[在 Skype for business Server 中部署用于灾难恢复的配对的前端池](front-end-pools-for-disaster-recovery.md)
  
[在 Skype for Business Server 2015 中针对后端服务器高可用性部署 SQL 镜像](sql-mirroring-for-high-availability.md)
  
