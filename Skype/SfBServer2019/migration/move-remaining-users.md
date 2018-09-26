---
title: 移动其余用户
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 使用任一 Skype 业务 Server Control Panel 或 Skype for Business Server 命令行管理程序，则可以移到业务服务器 2019年部署新的 Skype 用户。 您必须满足某些要求，以确保顺利过渡到 Skype 的业务服务器 2019年。 有关为完成本主题中的过程的先决条件的详细信息，请参阅配置迁移客户端。 有关移动用户的详细的步骤，请参阅阶段 4： 将测试用户移至试点池。
ms.openlocfilehash: 7bc5d942ddcf30cad84ceb5badf8817de2b254a0
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030495"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a><span data-ttu-id="e36a7-106">为业务服务器 2019年将剩余用户移至 Skype</span><span class="sxs-lookup"><span data-stu-id="e36a7-106">Move remaining users to Skype for Business Server 2019</span></span>

<span data-ttu-id="e36a7-107">使用任一 Skype 业务 Server Control Panel 或 Skype for Business Server 命令行管理程序，则可以移到业务服务器 2019年部署新的 Skype 用户。</span><span class="sxs-lookup"><span data-stu-id="e36a7-107">You can move users to the new Skype for Business Server 2019 deployment by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> <span data-ttu-id="e36a7-108">您必须满足某些要求，以确保顺利过渡到 Skype 的业务服务器 2019年。</span><span class="sxs-lookup"><span data-stu-id="e36a7-108">You must meet some requirements to ensure a smooth transition to Skype for Business Server 2019.</span></span> <span data-ttu-id="e36a7-109">有关为完成本主题中的过程的先决条件的详细信息，请参阅[配置迁移客户端](configure-clients-for-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="e36a7-109">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="e36a7-110">有关移动用户的详细步骤，请参阅[第 4 阶段： 将测试用户移至试点池](phase-4-move-test-users-to-the-pilot-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="e36a7-110">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e36a7-111">不能使用 Active Directory 用户和计算机管理单元或旧的管理工具将用户从旧环境迁移到 Skype 的业务服务器 2019年。</span><span class="sxs-lookup"><span data-stu-id="e36a7-111">You cannot use the Active Directory Users and Computers snap-in or the legacy administrative tools to move users from your legacy environment to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="e36a7-112">时将用户移至 Skype 业务服务器 2019年池时，用户的数据会移至与新池关联的后端数据库。</span><span class="sxs-lookup"><span data-stu-id="e36a7-112">When you move a user to a Skype for Business Server 2019 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="e36a7-113">这包括旧版用户创建的活动会议。</span><span class="sxs-lookup"><span data-stu-id="e36a7-113">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="e36a7-114">例如，如果旧用户配置了**我的会议**会议，会议将仍可在业务服务器 2019年池的新 Skype 后移动该用户。</span><span class="sxs-lookup"><span data-stu-id="e36a7-114">For example, if a legacy user has configured a **my meeting** conference, that conference will still be available in the new Skype for Business Server 2019 pool after the user has been moved.</span></span> <span data-ttu-id="e36a7-115">要访问的会议的详细信息仍将相同的**会议 URL 和会议 ID**。</span><span class="sxs-lookup"><span data-stu-id="e36a7-115">The details to access that meeting will still be the same **conference URL and conference ID**.</span></span> <span data-ttu-id="e36a7-116">唯一的区别是业务服务器 2019年池 Skype 而不是旧池现已承载会议。</span><span class="sxs-lookup"><span data-stu-id="e36a7-116">The only difference is that the conference is now hosted in the Skype for Business Server 2019 pool, and not in the legacy pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e36a7-117">承载用户 Skype 的业务服务器 2019年不需要同时部署已升级的客户端。</span><span class="sxs-lookup"><span data-stu-id="e36a7-117">Homing users on Skype for Business Server 2019 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="e36a7-118">仅当它们已升级到新的客户端软件时，将对用户可用的新功能。</span><span class="sxs-lookup"><span data-stu-id="e36a7-118">New functionality will be available to users only when they have upgraded to the new client software.</span></span> 
  
### <a name="post-migration-task"></a><span data-ttu-id="e36a7-119">迁移后任务</span><span class="sxs-lookup"><span data-stu-id="e36a7-119">Post migration task</span></span>

1. <span data-ttu-id="e36a7-120">移动用户后，验证会议策略分配给它们。</span><span class="sxs-lookup"><span data-stu-id="e36a7-120">After you move users, verify the conferencing policy that is assigned to them.</span></span> 
    
2. <span data-ttu-id="e36a7-121">若要确保用户组织的会议驻留在 Skype，无缝地与联盟用户驻留在旧安装上的业务服务器 2019年工作，分配给迁移用户的会议策略应允许匿名参与者。</span><span class="sxs-lookup"><span data-stu-id="e36a7-121">To ensure that meetings organized by users homed on Skype for Business Server 2019 work seamlessly with federated users who are homed on legacy install, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>
    
3. <span data-ttu-id="e36a7-122">允许匿名参与者具有业务 Server 2019 控制面板的 Skype 中选择**允许参与者邀请匿名用户**且具有**AllowAnonymousParticipantsInMeetings**的会议策略设置为**True**中从中 Skype 的**Get-csconferencingpolicy** cmdlet 输出的业务 Server Management Shell。</span><span class="sxs-lookup"><span data-stu-id="e36a7-122">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Skype for Business Server 2019 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Skype for Business Server Management Shell.</span></span> 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

