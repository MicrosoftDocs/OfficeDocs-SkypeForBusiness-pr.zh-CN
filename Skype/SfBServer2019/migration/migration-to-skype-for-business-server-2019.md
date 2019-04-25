---
title: 迁移到 Skype 业务服务器 2019
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本节中的主题将指导您完成的迁移到 Skype for Business Server 2019 过程。
ms.openlocfilehash: 32babd6fedd5defc756f73bbf001716c7c0b8a72
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231607"
---
# <a name="migration-to-skype-for-business-server-2019"></a>迁移到 Skype 业务服务器 2019

本节中的主题将指导您完成的迁移到 Skype for Business Server 2019 过程。 本文介绍了迁移的 Lync Server 2013 或 Skype 的业务服务器 2015 到 Skype 的业务服务器 2019年。

> [!IMPORTANT]
> 整个内容，我们使用术语*旧*引用旧式 Lync Server 2013 或 Skype 的要在业务服务器 2019年到 Skype 迁移的业务服务器 2015年。
  
> [!IMPORTANT]
> 本指南介绍通常所需完成迁移的每个阶段的步骤。 它不讨论每个可能的旧部署拓扑或每个可能的迁移方案。 因此，您可能不需要执行每个步骤所述，或需要执行附加步骤，具体取决于您的部署。 本指南还提供了示例验证步骤。 以下验证步骤提供可帮助您了解您需要查找以确保的每个阶段完成成功进行的迁移。 定制到特定的迁移过程以下验证步骤。 
  
本指南提供特定于升级现有部署的信息。 它并不介绍如何更改现有的拓扑。 本指南不涉及新功能的实现。 时使用的详细的过程已在其他文档，本指南可引导您对文章或文章部分。 
  
本文术语的定义如以下列表中指定。
  
**迁移：** 进入生产部署从 Lync Server 2013 或 Skype 的业务服务器 2015 Skype 的业务服务器 2019年。
    
**共存：** 某些功能已迁移至 Skype 业务服务器 2019年和其他功能迁移期间存在的临时环境仍保留在早期版本上。
    
**互操作性：** 成功运行共存阶段部署的功能。

**旧：** 系统进行迁移时远离，这 Lync Server 2013 或业务服务器 2015年的 Skype。
    
## <a name="in-this-section"></a>本节内容

- [开始迁移之前的准备工作](before-you-begin-the-migration.md)
    
- [第 1 阶段：规划迁移](phase-1-plan-your-migration.md)
    
- [第 2 阶段：准备迁移](phase-2-prepare-for-migration.md)
    
- [第 3 阶段：部署试点池](phase-3-deploy-pilot-pool.md)
    
- [第 4 阶段： 将测试用户移至试点池](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [第 5 阶段：在试点池中添加 Edge Server](phase-5-add-edge-server-to-pilot-pool.md)
    
- [第 6 阶段：从试点部署移动到生产中](phase-6-move-from-pilot-deployment-into-production.md)
    
- [第 7 阶段：完成迁移后任务](phase-7-complete-post-migration-tasks.md)
    
- [第 8 阶段：停用旧池](phase-8-decommission-legacy-pools.md)
    

