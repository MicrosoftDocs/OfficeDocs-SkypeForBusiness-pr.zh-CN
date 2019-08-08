---
title: 迁移剩余用户
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '你可以使用 Skype for business Server 控制面板或 Skype for business Server Management Shell 将用户移动到新的 Skype for business Server 2019 部署。 必须满足某些要求才能确保顺利过渡到 Skype for business Server 2019。 有关完成本主题中的过程的先决条件的详细信息, 请参阅为迁移配置客户端。 有关移动用户的详细步骤, 请参阅第4阶段: 将测试用户移动到试验池。'
ms.openlocfilehash: 8c12ca52e162c4317dabc59d5de9b74082730882
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244563"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a><span data-ttu-id="d9664-106">将剩余用户移动到 Skype for business Server 2019</span><span class="sxs-lookup"><span data-stu-id="d9664-106">Move remaining users to Skype for Business Server 2019</span></span>

<span data-ttu-id="d9664-107">你可以使用 Skype for business Server 控制面板或 Skype for business Server Management Shell 将用户移动到新的 Skype for business Server 2019 部署。</span><span class="sxs-lookup"><span data-stu-id="d9664-107">You can move users to the new Skype for Business Server 2019 deployment by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> <span data-ttu-id="d9664-108">必须满足某些要求才能确保顺利过渡到 Skype for business Server 2019。</span><span class="sxs-lookup"><span data-stu-id="d9664-108">You must meet some requirements to ensure a smooth transition to Skype for Business Server 2019.</span></span> <span data-ttu-id="d9664-109">有关完成本主题中的过程的先决条件的详细信息, 请参阅[为迁移配置客户端](configure-clients-for-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="d9664-109">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="d9664-110">有关移动用户的详细步骤, 请参阅[第4阶段: 将测试用户移动到试验池](phase-4-move-test-users-to-the-pilot-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="d9664-110">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d9664-111">不能使用 Active Directory 用户和计算机管理单元或旧版管理工具将用户从旧环境移动到 Skype for business Server 2019。</span><span class="sxs-lookup"><span data-stu-id="d9664-111">You cannot use the Active Directory Users and Computers snap-in or the legacy administrative tools to move users from your legacy environment to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="d9664-112">将用户移动到 Skype for business Server 2019 池时, 用户的数据将移动到与新池关联的后端数据库。</span><span class="sxs-lookup"><span data-stu-id="d9664-112">When you move a user to a Skype for Business Server 2019 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="d9664-113">这包括由旧版用户创建的活动会议。</span><span class="sxs-lookup"><span data-stu-id="d9664-113">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="d9664-114">例如, 如果旧版用户配置了 **"我的会议**" 会议, 则在用户移动后, 该会议仍将在新的 Skype For business Server 2019 池中可用。</span><span class="sxs-lookup"><span data-stu-id="d9664-114">For example, if a legacy user has configured a **my meeting** conference, that conference will still be available in the new Skype for Business Server 2019 pool after the user has been moved.</span></span> <span data-ttu-id="d9664-115">访问该会议的详细信息仍将是相同的**会议 URL 和会议 ID**。</span><span class="sxs-lookup"><span data-stu-id="d9664-115">The details to access that meeting will still be the same **conference URL and conference ID**.</span></span> <span data-ttu-id="d9664-116">唯一的区别是会议现在托管在 Skype for business Server 2019 池中, 而不是在旧版池中。</span><span class="sxs-lookup"><span data-stu-id="d9664-116">The only difference is that the conference is now hosted in the Skype for Business Server 2019 pool, and not in the legacy pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d9664-117">在 Skype for Business Server 2019 上托管用户不需要同时部署已升级的客户端。</span><span class="sxs-lookup"><span data-stu-id="d9664-117">Homing users on Skype for Business Server 2019 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="d9664-118">仅当用户升级到新的客户端软件时, 才可使用新功能。</span><span class="sxs-lookup"><span data-stu-id="d9664-118">New functionality will be available to users only when they have upgraded to the new client software.</span></span> 
  
### <a name="post-migration-task"></a><span data-ttu-id="d9664-119">发布迁移任务</span><span class="sxs-lookup"><span data-stu-id="d9664-119">Post migration task</span></span>

1. <span data-ttu-id="d9664-120">移动用户后, 请验证分配给他们的会议策略。</span><span class="sxs-lookup"><span data-stu-id="d9664-120">After you move users, verify the conferencing policy that is assigned to them.</span></span> 
    
2. <span data-ttu-id="d9664-121">为确保驻留在 Skype for Business Server 2019 上的用户组织的会议与驻留在旧安装中的联盟用户无缝协作, 分配给已迁移用户的会议策略应允许匿名参与者。</span><span class="sxs-lookup"><span data-stu-id="d9664-121">To ensure that meetings organized by users homed on Skype for Business Server 2019 work seamlessly with federated users who are homed on legacy install, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>
    
3. <span data-ttu-id="d9664-122">允许匿名参与者的会议策略允许**参与者邀请**Skype For business Server 2019 控制面板中选定的匿名用户, 并在**AllowAnonymousParticipantsInMeetings**中设置为**True** 。Skype for Business Server 命令行管理程序中的**CsConferencingPolicy** cmdlet 输出。</span><span class="sxs-lookup"><span data-stu-id="d9664-122">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Skype for Business Server 2019 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Skype for Business Server Management Shell.</span></span> 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

