---
title: 移动其余用户
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
description: 您可以使用控制面板或命令行管理Skype for Business Server将用户移动到 Skype for Business Server 2019 Skype for Business Server部署。 您必须满足一些要求，以确保顺利过渡到 Skype for Business Server 2019。 有关完成本主题中的过程的先决条件的详细信息，请参阅配置客户端进行迁移。 有关移动用户的详细步骤，请参阅阶段 4：将测试用户移动到试点池。
ms.openlocfilehash: 60742068bc684470d181593e94615da2a8d79ff6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623104"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>将其余用户移动到 2019 Skype for Business Server 2019

您可以使用控制面板或命令行管理Skype for Business Server将用户移动到 Skype for Business Server 2019 Skype for Business Server部署。 您必须满足一些要求，以确保顺利过渡到 Skype for Business Server 2019。 有关完成本主题中的过程的先决条件的详细信息，请参阅配置 [客户端进行迁移](configure-clients-for-migration.md)。 有关移动用户的详细步骤，请参阅阶段 [4：将测试用户移动到试点池](phase-4-move-test-users-to-the-pilot-pool.md)。
  
> [!IMPORTANT]
> 不能使用 Active Directory 用户和计算机管理单元或旧版管理工具将用户从旧环境移动到 Skype for Business Server 2019。 
  
当您将用户移动到 Skype for Business Server 2019 池时，该用户的数据将移动到与新池关联的后端数据库。 
  
> [!IMPORTANT]
> 这包括由旧用户创建的活动会议。 例如，如果旧用户已配置我的会议，那么在移动用户后，该会议仍将位于新的 Skype for Business Server 2019 池中。 访问该会议时仍要使用相同的 **会议 URL 和会议 ID**。 唯一的区别是会议现在托管在 Skype for Business Server 2019 池中，而不是旧池中。 
  
> [!NOTE]
> 在 2019 Skype for Business Server用户不需要同时部署升级的客户端。 仅在升级到新客户端软件后，用户才能使用新功能。 
  
### <a name="post-migration-task"></a>迁移后任务

1. 移动用户后，确保向他们分配会议策略。 
    
2. 为确保由 Skype for Business Server 2019 上用户组织的会议与位于旧版安装上的联盟用户无缝协作，分配给迁移用户的会议策略应允许匿名参与者。
    
3. 允许匿名参与者的会议策略在 Skype for Business Server  2019 控制面板中选择了"允许参与者邀请匿名用户"，并且将 Skype for Business Server 命令行管理程序 **中 Get-CsConferencingPolicy** cmdlet 的输出中的 **AllowAnonymousParticipantsInMeetings** 设置为 **True。** 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

