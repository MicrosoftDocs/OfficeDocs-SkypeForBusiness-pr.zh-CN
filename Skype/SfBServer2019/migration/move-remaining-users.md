---
title: 迁移剩余用户
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '你可以使用 Skype for business Server 控制面板或 Skype for business Server Management Shell 将用户移动到新的 Skype for business Server 2019 部署。 必须满足某些要求才能确保顺利过渡到 Skype for business Server 2019。 有关完成本主题中的过程的先决条件的详细信息, 请参阅为迁移配置客户端。 有关移动用户的详细步骤, 请参阅第4阶段: 将测试用户移动到试验池。'
ms.openlocfilehash: 67bc2d3b239e65b5b1c83e2dcda81a1610d5a31c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273957"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>将剩余用户移动到 Skype for business Server 2019

你可以使用 Skype for business Server 控制面板或 Skype for business Server Management Shell 将用户移动到新的 Skype for business Server 2019 部署。 必须满足某些要求才能确保顺利过渡到 Skype for business Server 2019。 有关完成本主题中的过程的先决条件的详细信息, 请参阅[为迁移配置客户端](configure-clients-for-migration.md)。 有关移动用户的详细步骤, 请参阅[第4阶段: 将测试用户移动到试验池](phase-4-move-test-users-to-the-pilot-pool.md)。
  
> [!IMPORTANT]
> 不能使用 Active Directory 用户和计算机管理单元或旧版管理工具将用户从旧环境移动到 Skype for business Server 2019。 
  
将用户移动到 Skype for business Server 2019 池时, 用户的数据将移动到与新池关联的后端数据库。 
  
> [!IMPORTANT]
> 这包括由旧版用户创建的活动会议。 例如, 如果旧版用户配置了 **"我的会议**" 会议, 则在用户移动后, 该会议仍将在新的 Skype For business Server 2019 池中可用。 访问该会议的详细信息仍将是相同的**会议 URL 和会议 ID**。 唯一的区别是会议现在托管在 Skype for business Server 2019 池中, 而不是在旧版池中。 
  
> [!NOTE]
> 在 Skype for Business Server 2019 上托管用户不需要同时部署已升级的客户端。 仅当用户升级到新的客户端软件时, 才可使用新功能。 
  
### <a name="post-migration-task"></a>发布迁移任务

1. 移动用户后, 请验证分配给他们的会议策略。 
    
2. 为确保驻留在 Skype for Business Server 2019 上的用户组织的会议与驻留在旧安装中的联盟用户无缝协作, 分配给已迁移用户的会议策略应允许匿名参与者。
    
3. 允许匿名参与者的会议策略允许**参与者邀请**Skype For business Server 2019 控制面板中选定的匿名用户, 并在**AllowAnonymousParticipantsInMeetings**中设置为**True** 。Skype for Business Server 命令行管理程序中的**CsConferencingPolicy** cmdlet 输出。 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

