---
title: 迁移响应组
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
description: 将用户移动到 Skype for business Server 2019 池之后，可以迁移响应组。 迁移响应组包括将代理组、队列、工作流、音频文件和移动响应组联系人对象从旧版部署复制到 Skype for business Server 2019 池。 迁移旧版响应组后，对响应组的呼叫由 Skype for Business Server 2019 池中的响应组应用程序处理。 旧版池不再处理对响应组的调用。
ms.openlocfilehash: 03b0ffd900b5d7c23dd6ff680d56c0c4db53d8dc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752674"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="a2f07-106">迁移响应组</span><span class="sxs-lookup"><span data-stu-id="a2f07-106">Migrate response groups</span></span>

<span data-ttu-id="a2f07-107">将用户移动到 Skype for business Server 2019 池之后，可以迁移响应组。</span><span class="sxs-lookup"><span data-stu-id="a2f07-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="a2f07-108">迁移响应组包括将代理组、队列、工作流、音频文件和移动响应组联系人对象从旧版部署复制到 Skype for business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="a2f07-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="a2f07-109">迁移旧版响应组后，对响应组的呼叫由 Skype for Business Server 2019 池中的响应组应用程序处理。</span><span class="sxs-lookup"><span data-stu-id="a2f07-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="a2f07-110">旧版池不再处理对响应组的调用。</span><span class="sxs-lookup"><span data-stu-id="a2f07-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a2f07-111">虽然您可以在将所有用户移动到 Skype for Business Server 2019 池之前迁移响应组，但我们建议您首先移动所有用户。</span><span class="sxs-lookup"><span data-stu-id="a2f07-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="a2f07-112">特别是，响应组代理的用户在移动到 Skype for Business Server 2019 池之前，不会具有新功能的完整功能。</span><span class="sxs-lookup"><span data-stu-id="a2f07-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="a2f07-113">在迁移响应组之前，必须已部署包含响应组应用程序的 Skype for Business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="a2f07-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="a2f07-114">默认情况下，在部署企业语音时，会安装并激活响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="a2f07-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="a2f07-115">您可以通过运行**get-csservice-ApplicationServer** cmdlet 来确保响应组应用程序已安装。</span><span class="sxs-lookup"><span data-stu-id="a2f07-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a2f07-116">您可以先在 Skype for business Server 2019 池中创建新的 Skype for Business Server 2019 响应组，然后再迁移您的旧版响应组。</span><span class="sxs-lookup"><span data-stu-id="a2f07-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="a2f07-117">若要将响应组从旧版池迁移到 Skype for Business Server 2019，请运行**CsRgsConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a2f07-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a2f07-118">响应组迁移 cmdlet 将移动整个池的响应组配置。</span><span class="sxs-lookup"><span data-stu-id="a2f07-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="a2f07-119">您不能选择特定组、队列或工作流进行迁移。</span><span class="sxs-lookup"><span data-stu-id="a2f07-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="a2f07-120">迁移响应组之后，需要使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序 cmdlet 来验证是否成功移动了所有代理组、队列和工作流。</span><span class="sxs-lookup"><span data-stu-id="a2f07-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="a2f07-121">迁移响应组时，不会删除旧响应组。</span><span class="sxs-lookup"><span data-stu-id="a2f07-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="a2f07-122">在迁移后使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序管理响应组时，您可以看到旧版响应组和 Skype for Business Server 2019 响应组。</span><span class="sxs-lookup"><span data-stu-id="a2f07-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="a2f07-123">您应该仅将更新应用到 Skype for Business Server 2019 响应组。</span><span class="sxs-lookup"><span data-stu-id="a2f07-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="a2f07-124">旧响应组仅为回滚而保留。</span><span class="sxs-lookup"><span data-stu-id="a2f07-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="a2f07-125">在完成迁移并创建新的响应组之后，Skype for Business Server 控制面板和 Skype for Business Server 命令行管理程序将显示每个响应组的旧版和 Skype for business Server 2019 版本。</span><span class="sxs-lookup"><span data-stu-id="a2f07-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="a2f07-126">请勿使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序删除旧版响应组。</span><span class="sxs-lookup"><span data-stu-id="a2f07-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="a2f07-127">如果确实删除了一个，则在迁移过程中创建的相应响应组将停止工作。</span><span class="sxs-lookup"><span data-stu-id="a2f07-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="a2f07-128">停用旧版池时，将删除旧版响应组。</span><span class="sxs-lookup"><span data-stu-id="a2f07-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a2f07-129">建议在停用池之前不要删除之前的部署中的任何数据。</span><span class="sxs-lookup"><span data-stu-id="a2f07-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="a2f07-130">此外，强烈建议在迁移后立即导出响应组。</span><span class="sxs-lookup"><span data-stu-id="a2f07-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="a2f07-131">如果应删除旧响应组，则可以从备份中还原响应组，以获取 Skype for business Server 2019 响应组再次运行。</span><span class="sxs-lookup"><span data-stu-id="a2f07-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="a2f07-132">Skype for Business Server 2019 引入了名为 "**工作流类型**" 的新响应组功能。</span><span class="sxs-lookup"><span data-stu-id="a2f07-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="a2f07-133">“工作流类型”\*\*\*\* 可以是“托管”\*\*\*\* 的，也可以是“非托管”\*\*\*\* 的。</span><span class="sxs-lookup"><span data-stu-id="a2f07-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="a2f07-134">所有响应组都是使用设置为“非托管”\*\*\*\* 的“工作流类型”\*\*\*\* 和空管理员列表进行迁移的。</span><span class="sxs-lookup"><span data-stu-id="a2f07-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="a2f07-135">在运行 **Move-CsRgsConfiguration** cmdlet 时，代理组、队列、工作流和音频文件保留在旧版池中以用于回滚。</span><span class="sxs-lookup"><span data-stu-id="a2f07-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="a2f07-136">但如果您确实需要回滚到旧版池，则需要运行 **Move-CsApplicationEndpoint** cmdlet 将联系对象移回旧版池。</span><span class="sxs-lookup"><span data-stu-id="a2f07-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="a2f07-137">下面的迁移响应组配置的过程假设您的旧版池和 Skype for Business Server 2019 池之间具有一对一关系。</span><span class="sxs-lookup"><span data-stu-id="a2f07-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="a2f07-138">如果您计划在迁移和部署期间合并或拆分池，则需要规划哪些旧版池映射到哪个 Skype for business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="a2f07-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="a2f07-139">迁移响应组配置</span><span class="sxs-lookup"><span data-stu-id="a2f07-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="a2f07-140">使用具有 RTCUniversalServerAdmins 组成员身份或同等管理员权限的帐户登录到计算机。</span><span class="sxs-lookup"><span data-stu-id="a2f07-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="a2f07-141">启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Skype for business server 2019**"，然后单击 " **Skype for business server Management Shell**"。</span><span class="sxs-lookup"><span data-stu-id="a2f07-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a2f07-142">以</span><span class="sxs-lookup"><span data-stu-id="a2f07-142">Run:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    <span data-ttu-id="a2f07-143">例如：</span><span class="sxs-lookup"><span data-stu-id="a2f07-143">For example:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. <span data-ttu-id="a2f07-144">将响应组和代理迁移到 Skype for Business Server 2019 池之后，代理用于登录和注销的 URL 是 Skype for Business Server 2019 URL，可从 "**工具**" 菜单中获取。</span><span class="sxs-lookup"><span data-stu-id="a2f07-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="a2f07-145">提醒代理更新对新 URL 的所有引用（例如书签）。</span><span class="sxs-lookup"><span data-stu-id="a2f07-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a2f07-146">使用 Skype for Business Server 控制面板验证响应组迁移的具体方法</span><span class="sxs-lookup"><span data-stu-id="a2f07-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a2f07-147">使用 RTCUniversalReadOnlyAdmins 组成员帐户，或至少使用 CsViewOnlyAdministrator 角色成员帐户登录计算机。</span><span class="sxs-lookup"><span data-stu-id="a2f07-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="a2f07-148">打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="a2f07-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="a2f07-149">有关可用于启动 Skype for Business Server 控制面板的不同方法的详细信息，请参阅[Open Skype For Business server 2019 管理工具](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx)。</span><span class="sxs-lookup"><span data-stu-id="a2f07-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="a2f07-150">在左侧导航窗格中，单击“响应组”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2f07-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="a2f07-151">在 "**工作流**" 选项卡上，验证您的旧环境中的所有工作流是否都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="a2f07-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="a2f07-152">单击 "**队列**" 选项卡，并验证您的旧环境中的所有队列是否都包含在该列表中。</span><span class="sxs-lookup"><span data-stu-id="a2f07-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="a2f07-153">单击 "**组**" 选项卡，并验证您的旧环境中的所有代理组是否都包含在该列表中。</span><span class="sxs-lookup"><span data-stu-id="a2f07-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a2f07-154">使用 Skype for Business Server 命令行管理程序验证响应组迁移</span><span class="sxs-lookup"><span data-stu-id="a2f07-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="a2f07-155">使用 RTCUniversalReadOnlyAdmins 组成员帐户，或至少使用 CsViewOnlyAdministrator 角色成员帐户登录计算机。</span><span class="sxs-lookup"><span data-stu-id="a2f07-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="a2f07-156">启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Skype for business server 2019**"，然后单击 " **Skype for business server Management Shell**"。</span><span class="sxs-lookup"><span data-stu-id="a2f07-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="a2f07-157">若要了解有关以下 cmdlet 的详细信息，请运行：</span><span class="sxs-lookup"><span data-stu-id="a2f07-157">For details about the following cmdlets, run:</span></span>
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. <span data-ttu-id="a2f07-158">以</span><span class="sxs-lookup"><span data-stu-id="a2f07-158">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. <span data-ttu-id="a2f07-159">确认您的旧环境中的所有代理组都包含在该列表中。</span><span class="sxs-lookup"><span data-stu-id="a2f07-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="a2f07-160">以</span><span class="sxs-lookup"><span data-stu-id="a2f07-160">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. <span data-ttu-id="a2f07-161">验证您的旧环境中的所有队列是否都包含在该列表中。</span><span class="sxs-lookup"><span data-stu-id="a2f07-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="a2f07-162">以</span><span class="sxs-lookup"><span data-stu-id="a2f07-162">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. <span data-ttu-id="a2f07-163">验证您的旧环境中的所有工作流是否都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="a2f07-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
    

