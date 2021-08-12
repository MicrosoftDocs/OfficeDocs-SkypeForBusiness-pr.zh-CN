---
title: 迁移到 Skype for Business Server 2019
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 本节中的主题将指导您完成迁移到 Skype for Business Server 2019 的过程。
ms.openlocfilehash: 1014fe5d491823c427eb588aac86757afb997578b519abf2249f481c91a3d4aa
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303396"
---
# <a name="migration-to-skype-for-business-server-2019"></a>迁移到 Skype for Business Server 2019

本节中的主题将指导您完成迁移到 Skype for Business Server 2019 的过程。 本文介绍如何将 Lync Server 2013 或 Skype for Business Server 2015 迁移到 Skype for Business Server 2019。

> [!IMPORTANT]
> 在整个内容中，我们使用术语 *legacy* 来引用要迁移到 Skype for Business Server 2019 的旧 Lync Server 2013 或 Skype for Business Server 2015。
  
> [!IMPORTANT]
> 本指南介绍完成迁移的每个阶段通常需要执行的步骤。 它并非适用于每种可能的旧部署拓扑或每种可能的迁移方案。 因此，您可能不需要执行所述的每个步骤，也可能需要执行额外步骤，具体取决于您的部署。 本指南还提供了验证步骤的示例。 提供这些验证步骤是为了帮助您了解需要查看哪些内容，以确保执行迁移时每个阶段都成功完成。 请根据您的特定迁移过程定制这些验证步骤。 
  
本指南提供专用于升级现有部署的信息。 它未解释如何更改现有拓扑。 本指南不涉及新功能的实现。 当详细过程记录在其他地方时，本指南将引导您阅读文章或文章部分。 
  
本文定义以下列表中指定的术语。
  
**迁移：** 将生产部署从 Lync Server 2013 或 Skype for Business Server 2015 Skype for Business Server 2019。
    
**共存：** 迁移过程中存在的临时环境，其中某些功能已迁移到 Skype for Business Server 2019，而其他功能仍保留在早期版本上。
    
**互操作性：** 您的部署在共存期间能否成功运行。

**旧版：** 要迁移的系统是 Lync Server 2013 或 Skype for Business Server 2015。
    
## <a name="in-this-section"></a>本节内容

- [开始迁移之前的准备工作](before-you-begin-the-migration.md)
    
- [第 1 阶段：规划迁移](phase-1-plan-your-migration.md)
    
- [第 2 阶段：准备迁移](phase-2-prepare-for-migration.md)
    
- [第 3 阶段：部署试点池](phase-3-deploy-pilot-pool.md)
    
- [阶段 4：将测试用户移至试点池](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [第 5 阶段：在试点池中添加 Edge Server](phase-5-add-edge-server-to-pilot-pool.md)
    
- [第 6 阶段：从试点部署移动到生产中](phase-6-move-from-pilot-deployment-into-production.md)
    
- [第 7 阶段：完成迁移后任务](phase-7-complete-post-migration-tasks.md)
    
- [第 8 阶段：停用旧池](phase-8-decommission-legacy-pools.md)
    

