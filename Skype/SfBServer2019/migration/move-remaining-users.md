---
title: 迁移剩余用户
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 使用任一 Skype 业务 Server Control Panel 或 Skype for Business Server 命令行管理程序，则可以移到业务服务器 2019年部署新的 Skype 用户。 您必须满足某些要求，以确保顺利过渡到 Skype 的业务服务器 2019年。 有关为完成本主题中的过程的先决条件的详细信息，请参阅配置迁移客户端。 有关移动用户的详细的步骤，请参阅阶段 4： 将测试用户移至试点池。
ms.openlocfilehash: 9f984b7fac919decce521c6dafc587a4ac86de50
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231586"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>为业务服务器 2019年将剩余用户移至 Skype

使用任一 Skype 业务 Server Control Panel 或 Skype for Business Server 命令行管理程序，则可以移到业务服务器 2019年部署新的 Skype 用户。 您必须满足某些要求，以确保顺利过渡到 Skype 的业务服务器 2019年。 有关为完成本主题中的过程的先决条件的详细信息，请参阅[配置迁移客户端](configure-clients-for-migration.md)。 有关移动用户的详细步骤，请参阅[第 4 阶段： 将测试用户移至试点池](phase-4-move-test-users-to-the-pilot-pool.md)。
  
> [!IMPORTANT]
> 不能使用 Active Directory 用户和计算机管理单元或旧的管理工具将用户从旧环境迁移到 Skype 的业务服务器 2019年。 
  
时将用户移至 Skype 业务服务器 2019年池时，用户的数据会移至与新池关联的后端数据库。 
  
> [!IMPORTANT]
> 这包括旧版用户创建的活动会议。 例如，如果旧用户配置了**我的会议**会议，会议将仍可在业务服务器 2019年池的新 Skype 后移动该用户。 要访问的会议的详细信息仍将相同的**会议 URL 和会议 ID**。 唯一的区别是业务服务器 2019年池 Skype 而不是旧池现已承载会议。 
  
> [!NOTE]
> 承载用户 Skype 的业务服务器 2019年不需要同时部署已升级的客户端。 仅当它们已升级到新的客户端软件时，将对用户可用的新功能。 
  
### <a name="post-migration-task"></a>迁移后任务

1. 移动用户后，验证会议策略分配给它们。 
    
2. 若要确保用户组织的会议驻留在 Skype，无缝地与联盟用户驻留在旧安装上的业务服务器 2019年工作，分配给迁移用户的会议策略应允许匿名参与者。
    
3. 允许匿名参与者具有业务 Server 2019 控制面板的 Skype 中选择**允许参与者邀请匿名用户**且具有**AllowAnonymousParticipantsInMeetings**的会议策略设置为**True**中从中 Skype 的**Get-csconferencingpolicy** cmdlet 输出的业务 Server Management Shell。 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

