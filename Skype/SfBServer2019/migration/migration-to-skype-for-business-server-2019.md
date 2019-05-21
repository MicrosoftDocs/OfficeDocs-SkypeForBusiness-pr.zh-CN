---
title: 迁移到 Skype for Business 服务器2019
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本部分中的主题将指导你完成迁移到 Skype for Business Server 2019 的过程。
ms.openlocfilehash: bd1513e5ca2a33449f982394e4abc15b9616393b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298146"
---
# <a name="migration-to-skype-for-business-server-2019"></a>迁移到 Skype for Business 服务器2019

本部分中的主题将指导你完成迁移到 Skype for Business Server 2019 的过程。 本文介绍将 Lync Server 2013 或 Skype for business Server 2015 迁移到 Skype for business Server 2019。

> [!IMPORTANT]
> 在整个内容中, 我们使用术语 "*旧版*" 指的是要迁移到 Skype For business server 2019 的旧版 Lync server 2013 或 skype For business server 2015。
  
> [!IMPORTANT]
> 本指南介绍了完成迁移的每个阶段通常需要执行的步骤。 它不能解决每个可能的旧部署拓扑或每种可能的迁移方案。 因此, 你可能不需要执行所述的每个步骤, 或者你可能需要执行其他步骤, 具体取决于你的部署。 本指南还提供了验证步骤的示例。 提供这些验证步骤旨在帮助你了解需要查找的内容, 以确保每个阶段在你的迁移过程中成功完成。 将这些验证步骤定制到特定迁移过程。 
  
本指南提供有关升级现有部署的特定信息。 它不介绍如何更改现有拓扑。 本指南不介绍新功能的实现。 当详细过程记录在其他位置时, 本指南将指导你查看文章或文章部分。 
  
本文将根据下表中的指定来定义术语。
  
**迁移:** 将生产部署从 Lync Server 2013 或 Skype for business Server 2015 移动到 Skype for business Server 2019。
    
**共存:** 在迁移过程中, 当某些功能迁移到 Skype for business Server 2019 且其他功能仍在以前的版本上时, 在迁移期间存在的临时环境。
    
**互操作性:** 部署在共存期间成功运行的能力。

**旧版:** 您要从中迁移的系统, 即 Lync Server 2013 或 Skype for business Server 2015。
    
## <a name="in-this-section"></a>本节内容

- [开始迁移之前的准备工作](before-you-begin-the-migration.md)
    
- [第 1 阶段：规划迁移](phase-1-plan-your-migration.md)
    
- [第 2 阶段：准备迁移](phase-2-prepare-for-migration.md)
    
- [第 3 阶段：部署试点池](phase-3-deploy-pilot-pool.md)
    
- [第4阶段: 将测试用户移动到试验池](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [第 5 阶段：在试点池中添加 Edge Server](phase-5-add-edge-server-to-pilot-pool.md)
    
- [第 6 阶段：从试点部署移动到生产中](phase-6-move-from-pilot-deployment-into-production.md)
    
- [第 7 阶段：完成迁移后任务](phase-7-complete-post-migration-tasks.md)
    
- [第 8 阶段：停用旧池](phase-8-decommission-legacy-pools.md)
    

