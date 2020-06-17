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
localization_priority: Normal
description: 您可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序将用户移动到新的 Skype for Business Server 2019 部署。 您必须满足某些要求才能确保顺利过渡到 Skype for business Server 2019。 有关完成本主题中的过程的先决条件的详细信息，请参阅 Configure clients for 迁移。 有关移动用户的详细步骤，请参阅第4阶段：将测试用户移动到试点池。
ms.openlocfilehash: 0c4135ed8c3eaae25e57e6af1c67a18eb933b190
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753710"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>将其余用户移动到 Skype for Business Server 2019

您可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序将用户移动到新的 Skype for Business Server 2019 部署。 您必须满足某些要求才能确保顺利过渡到 Skype for business Server 2019。 有关完成本主题中的过程的先决条件的详细信息，请参阅[Configure clients for 迁移](configure-clients-for-migration.md)。 有关移动用户的详细步骤，请参阅[第4阶段：将测试用户移动到试点池](phase-4-move-test-users-to-the-pilot-pool.md)。
  
> [!IMPORTANT]
> 您不能使用 Active Directory 用户和计算机管理单元或旧管理工具将用户从旧版环境移动到 Skype for business Server 2019。 
  
将用户移动到 Skype for business Server 2019 池时，用户的数据将移动到与新池关联的后端数据库中。 
  
> [!IMPORTANT]
> 这包括由旧用户创建的活动会议。 例如，如果旧版用户配置了**我的会议**会议，则在用户移动后，该会议仍将在新的 Skype For business Server 2019 池中可用。 访问该会议时仍要使用相同的**会议 URL 和会议 ID**。 唯一的区别是会议现在托管在 Skype for Business Server 2019 池中，而不是在旧版池中托管。 
  
> [!NOTE]
> 在 Skype for business Server 2019 上托管用户不需要同时部署已升级的客户端。 仅在升级到新客户端软件后，用户才能使用新功能。 
  
### <a name="post-migration-task"></a>迁移后任务

1. 移动用户后，确保向他们分配会议策略。 
    
2. 为了确保由驻留在 Skype for Business Server 2019 上的用户组织的会议与驻留在旧安装中的联合用户无缝协作，分配给迁移用户的会议策略应允许匿名参与者。
    
3. 允许匿名参与者的会议策略**允许参与者邀请**在 skype for business Server 2019 控制面板中选择的匿名用户，并在 skype For Business Server 命令行管理程序中**的 set-csconferencingpolicy** cmdlet 的输出中将**AllowAnonymousParticipantsInMeetings**设置为**True** 。 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

