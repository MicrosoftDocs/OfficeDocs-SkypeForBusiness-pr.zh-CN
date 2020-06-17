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
description: 本节中的主题将指导您完成迁移到 Skype for business Server 2019 的过程。
ms.openlocfilehash: 860fce550de33ed726bbbe723c8c7677ff09fc1c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752614"
---
# <a name="migration-to-skype-for-business-server-2019"></a>迁移到 Skype for Business Server 2019

本节中的主题将指导您完成迁移到 Skype for business Server 2019 的过程。 本文介绍了如何将 Lync Server 2013 或 Skype for business Server 2015 迁移到 Skype for Business Server 2019。

> [!IMPORTANT]
> 在整个内容中，我们使用*旧式的旧版*Lync server 2013 或 skype For business server 2015 迁移到 Skype For business server 2019。
  
> [!IMPORTANT]
> 本指南介绍了完成每个迁移阶段通常需要执行的步骤。 它并非适用于每种可能的旧部署拓扑或每种可能的迁移方案。 因此，您可能不需要执行所述的每个步骤，也可能需要执行额外步骤，具体取决于您的部署。 本指南还提供了验证步骤的示例。 提供这些验证步骤是为了帮助您了解需要查看哪些内容，以确保执行迁移时每个阶段都成功完成。 请根据您的特定迁移过程定制这些验证步骤。 
  
本指南提供专用于升级现有部署的信息。 它未解释如何更改现有拓扑。 本指南不涉及新功能的实现。 在其他地方记录详细过程时，本指南将指导您使用文章或文章部分。 
  
本文定义了以下列表中指定的术语。
  
**迁移：** 将你的生产部署从 Lync Server 2013 或 Skype for business Server 2015 迁移到 Skype for business Server 2019。
    
**共存：** 在迁移过程中，如果将某些功能迁移到 Skype for business Server 2019，并且其他功能仍保留在以前的版本中，则在迁移过程中存在的临时环境。
    
**互操作性：** 您的部署在共存期间成功运行的能力。

**旧版：** 您要从中迁移的系统，即 Lync Server 2013 或 Skype for Business Server 2015。
    
## <a name="in-this-section"></a>本节内容

- [开始迁移之前的准备工作](before-you-begin-the-migration.md)
    
- [第 1 阶段：规划迁移](phase-1-plan-your-migration.md)
    
- [第 2 阶段：准备迁移](phase-2-prepare-for-migration.md)
    
- [第 3 阶段：部署试点池](phase-3-deploy-pilot-pool.md)
    
- [第4阶段：将测试用户移动到引导池](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [第 5 阶段：在试点池中添加 Edge Server](phase-5-add-edge-server-to-pilot-pool.md)
    
- [第 6 阶段：从试点部署移动到生产中](phase-6-move-from-pilot-deployment-into-production.md)
    
- [第 7 阶段：完成迁移后任务](phase-7-complete-post-migration-tasks.md)
    
- [第 8 阶段：停用旧池](phase-8-decommission-legacy-pools.md)
    

