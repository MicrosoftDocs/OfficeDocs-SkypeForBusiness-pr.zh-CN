---
title: 迁移阶段
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 在 Skype for Business Server 2019 中，定义网络上包含 2019 Skype for Business Server的站点。 站点是一组通过高速度、低延迟网络（例如单个局域网 (LAN) 或由高速光纤网络连接的两个网络）正确连接的计算机。
ms.openlocfilehash: 8066e9ed7e46c54e6a6eac89bcf65dca1447aa57
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58587984"
---
# <a name="migration-phases"></a>迁移阶段

在 Skype for Business Server 2019 中，定义网络上包含 2019 Skype for Business Server的站点。 站点是一组通过高速度、低延迟网络（例如单个局域网 (LAN) 或由高速光纤网络连接的两个网络）正确连接的计算机。 
  
前端池 是一组配置相同的前端服务器，这些服务器协同工作来为公用组用户提供服务。 池为用户提供可伸缩性和故障转移功能。 池中的每台服务器必须运行一个或多个相同的服务器角色。 一Standard Edition为小型组织设计的服务器，它还定义了一个池，并运行在单台服务器上。 这样一来，您Skype for Business Server 2019 功能，但无法提供真正的高可用性解决方案。 
  
以下阶段介绍了到 2019 年 10 月Skype for Business Server过程。 对于包含多个池的多个站点，每个池都应遵循此分阶段方法。
  
1. [第 1 阶段：规划迁移](phase-1-plan-your-migration.md)
    
2. [第 2 阶段：准备迁移](phase-2-prepare-for-migration.md)
    
3. [第 3 阶段：Skype for Business Server 2019 试点池](phase-3-deploy-pilot-pool.md)
    
4. [阶段 4：将测试用户移至试点池](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [第 5 阶段：Skype for Business Server 2019 边缘服务器添加到试点池](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [第 6 阶段：从试点部署移动到生产中](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [第 7 阶段：完成迁移后任务](phase-7-complete-post-migration-tasks.md)
    
8. [第 8 阶段：停用旧池](phase-8-decommission-legacy-pools.md)
    

