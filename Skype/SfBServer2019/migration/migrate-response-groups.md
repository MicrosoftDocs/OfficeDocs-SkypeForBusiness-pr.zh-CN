---
title: 迁移响应组
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 将用户移动到 Skype for business Server 2019 池后，您可以迁移响应组。 迁移响应组包括将代理组、队列、工作流、音频文件和移动响应组联系人对象从旧部署复制到 Skype for business Server 2019 池。 迁移旧版响应组后，对响应组的呼叫由 Skype for Business Server 2019 池中的响应组应用程序处理。 不再通过旧版池处理对响应组的调用。
ms.openlocfilehash: 9e7605daf92646e5bb53626eeed2371888bf9cb1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813460"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="a592f-106">迁移响应组</span><span class="sxs-lookup"><span data-stu-id="a592f-106">Migrate response groups</span></span>

<span data-ttu-id="a592f-107">将用户移动到 Skype for business Server 2019 池后，您可以迁移响应组。</span><span class="sxs-lookup"><span data-stu-id="a592f-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="a592f-108">迁移响应组包括将代理组、队列、工作流、音频文件和移动响应组联系人对象从旧部署复制到 Skype for business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="a592f-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="a592f-109">迁移旧版响应组后，对响应组的呼叫由 Skype for Business Server 2019 池中的响应组应用程序处理。</span><span class="sxs-lookup"><span data-stu-id="a592f-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="a592f-110">不再通过旧版池处理对响应组的调用。</span><span class="sxs-lookup"><span data-stu-id="a592f-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a592f-111">虽然你可以在将所有用户移动到 Skype for Business Server 2019 池之前迁移响应组，但我们建议先移动所有用户。</span><span class="sxs-lookup"><span data-stu-id="a592f-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="a592f-112">特别是，响应组代理的用户在移动到 Skype for business Server 2019 池之前不具有新功能的完整功能。</span><span class="sxs-lookup"><span data-stu-id="a592f-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="a592f-113">在迁移响应组之前，必须已部署包含响应组应用程序的 Skype for business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="a592f-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="a592f-114">部署企业语音时，将默认安装并激活 "响应组" 应用程序。</span><span class="sxs-lookup"><span data-stu-id="a592f-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="a592f-115">你可以通过运行**CsService-ApplicationServer** cmdlet 来确保响应组应用程序已安装。</span><span class="sxs-lookup"><span data-stu-id="a592f-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a592f-116">在迁移传统的响应组之前，您可以在 Skype for business Server 2019 池中创建新的 Skype for business Server 2019 响应组。</span><span class="sxs-lookup"><span data-stu-id="a592f-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="a592f-117">若要将响应组从旧版池迁移到 Skype for business Server 2019，请运行**CsRgsConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a592f-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a592f-118">响应组迁移 cmdlet 移动整个池的响应组配置。</span><span class="sxs-lookup"><span data-stu-id="a592f-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="a592f-119">您不能选择要迁移的特定组、队列或工作流。</span><span class="sxs-lookup"><span data-stu-id="a592f-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="a592f-120">迁移响应组后，你需要使用 Skype for business 服务器控制面板或 Skype for Business Server Management Shell cmdlet 验证是否成功移动了所有代理组、队列和工作流。</span><span class="sxs-lookup"><span data-stu-id="a592f-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="a592f-121">当您迁移响应组时，不会删除旧的响应组。</span><span class="sxs-lookup"><span data-stu-id="a592f-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="a592f-122">通过使用 Skype for business Server 控制面板或 Skype for business Server Management Shell 管理迁移后的响应组，你可以同时看到旧式响应组和 Skype for business Server 2019 响应组。</span><span class="sxs-lookup"><span data-stu-id="a592f-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="a592f-123">你应该仅将更新应用到 Skype for Business Server 2019 响应组。</span><span class="sxs-lookup"><span data-stu-id="a592f-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="a592f-124">旧的响应组仅保留用于回退用途。</span><span class="sxs-lookup"><span data-stu-id="a592f-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="a592f-125">完成迁移并创建新的响应组后，Skype for business Server 控制面板和 Skype for business Server Management Shell 将显示每个响应的旧版和 Skype for business Server 2019 版本。团队.</span><span class="sxs-lookup"><span data-stu-id="a592f-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="a592f-126">请勿使用 Skype for Business 服务器控制面板或 Skype for business Server Management Shell 删除旧式响应组。</span><span class="sxs-lookup"><span data-stu-id="a592f-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="a592f-127">如果确实删除了一个，则迁移期间创建的相应响应组将停止工作。</span><span class="sxs-lookup"><span data-stu-id="a592f-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="a592f-128">当您停止旧版的池时，旧的响应组将被删除。</span><span class="sxs-lookup"><span data-stu-id="a592f-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a592f-129">我们建议您不要从以前的部署中删除任何数据，直到解除池。</span><span class="sxs-lookup"><span data-stu-id="a592f-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="a592f-130">此外，我们强烈建议您在迁移后立即导出响应组。</span><span class="sxs-lookup"><span data-stu-id="a592f-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="a592f-131">如果传统响应组应被删除，则可以从备份还原响应组，以使 Skype for business Server 2019 响应组再次运行。</span><span class="sxs-lookup"><span data-stu-id="a592f-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="a592f-132">Skype for Business Server 2019 引入了名为 "**工作流类型**" 的新响应组功能。</span><span class="sxs-lookup"><span data-stu-id="a592f-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="a592f-133">**工作流类型**可以是**托管**或**非托管**。</span><span class="sxs-lookup"><span data-stu-id="a592f-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="a592f-134">将使用**工作流类型**设置为**非托管**并使用空管理器列表迁移所有响应组。</span><span class="sxs-lookup"><span data-stu-id="a592f-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="a592f-135">当你运行**CsRgsConfiguration** cmdlet 时，代理组、队列、工作流和音频文件将保留在旧版池中，以便进行回退。</span><span class="sxs-lookup"><span data-stu-id="a592f-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="a592f-136">但是，如果确实需要回退到旧版池，则需要运行**CsApplicationEndpoint** cmdlet 以将联系人对象移回旧版池。</span><span class="sxs-lookup"><span data-stu-id="a592f-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="a592f-137">用于迁移响应组配置的以下过程假定你的旧池和 Skype for business Server 2019 池之间具有一对一关系。</span><span class="sxs-lookup"><span data-stu-id="a592f-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="a592f-138">如果你计划在迁移和部署期间合并或拆分池，你需要规划哪些旧式池映射到哪些 Skype for business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="a592f-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="a592f-139">迁移响应组配置</span><span class="sxs-lookup"><span data-stu-id="a592f-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="a592f-140">使用属于 RTCUniversalServerAdmins 组的成员的帐户登录到计算机，或具有等效的管理员权利和权限。</span><span class="sxs-lookup"><span data-stu-id="a592f-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="a592f-141">启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft skype for business server 2019**"，然后单击 " **skype for business 服务器管理外壳**"。</span><span class="sxs-lookup"><span data-stu-id="a592f-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a592f-142">运行：</span><span class="sxs-lookup"><span data-stu-id="a592f-142">Run:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    <span data-ttu-id="a592f-143">例如：</span><span class="sxs-lookup"><span data-stu-id="a592f-143">For example:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. <span data-ttu-id="a592f-144">将响应组和代理迁移到 Skype for Business Server 2019 池后，代理用于登录和注销的 URL 是 Skype for business Server 2019 URL，可从 "**工具**" 菜单中获取。</span><span class="sxs-lookup"><span data-stu-id="a592f-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="a592f-145">提醒代理将任何引用（如书签）更新到新 URL。</span><span class="sxs-lookup"><span data-stu-id="a592f-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a592f-146">使用 "Skype for Business 服务器" 控制面板验证响应组迁移</span><span class="sxs-lookup"><span data-stu-id="a592f-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a592f-147">使用属于 RTCUniversalReadOnlyAdmins 组成员的帐户登录到计算机，或者将该帐户的成员最少 CsViewOnlyAdministrator 角色的成员。</span><span class="sxs-lookup"><span data-stu-id="a592f-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="a592f-148">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="a592f-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="a592f-149">有关可用于启动 Skype for Business 服务器控制面板的不同方法的详细信息，请参阅[打开 skype for Business server 2019 管理工具](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx)。</span><span class="sxs-lookup"><span data-stu-id="a592f-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="a592f-150">在左侧导航窗格中，单击 "**响应组**"。</span><span class="sxs-lookup"><span data-stu-id="a592f-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="a592f-151">在 "**工作流**" 选项卡上，验证您的旧环境中的所有工作流是否都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="a592f-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="a592f-152">单击 "**队列**" 选项卡，然后验证您的旧环境中的所有队列是否都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="a592f-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="a592f-153">单击 "**组**" 选项卡，然后验证您的旧环境中的所有代理组是否都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="a592f-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a592f-154">使用 Skype for Business Server 命令行管理程序验证响应组迁移</span><span class="sxs-lookup"><span data-stu-id="a592f-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="a592f-155">使用属于 RTCUniversalReadOnlyAdmins 组成员的帐户登录到计算机，或者将该帐户的成员最少 CsViewOnlyAdministrator 角色的成员。</span><span class="sxs-lookup"><span data-stu-id="a592f-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="a592f-156">启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft skype for business server 2019**"，然后单击 " **skype for business 服务器管理外壳**"。</span><span class="sxs-lookup"><span data-stu-id="a592f-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="a592f-157">有关以下 cmdlet 的详细信息，请运行：</span><span class="sxs-lookup"><span data-stu-id="a592f-157">For details about the following cmdlets, run:</span></span>
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. <span data-ttu-id="a592f-158">运行：</span><span class="sxs-lookup"><span data-stu-id="a592f-158">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. <span data-ttu-id="a592f-159">验证你的旧环境中的所有代理组是否都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="a592f-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="a592f-160">运行：</span><span class="sxs-lookup"><span data-stu-id="a592f-160">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. <span data-ttu-id="a592f-161">验证您的旧环境中的所有队列是否都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="a592f-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="a592f-162">运行：</span><span class="sxs-lookup"><span data-stu-id="a592f-162">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. <span data-ttu-id="a592f-163">验证您的旧环境中的所有工作流是否都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="a592f-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
    

