---
title: 迁移响应组
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 对于业务服务器 2019年池用户移动到 Skype 后，您可以迁移响应组。 迁移响应组包括复制代理组、 队列、 工作流、 音频文件，并将从旧部署的响应组联系人对象移动到业务服务器 2019年池 Skype。 迁移旧版响应组后，对响应组呼叫处理中为 Business Server 2019 池 Skype 的响应组应用程序。 由旧池不再处理响应组呼叫。
ms.openlocfilehash: bdff9b96b73e925fb68b4a2f9bebb9b23edb4b56
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028017"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="ba67f-106">迁移响应组</span><span class="sxs-lookup"><span data-stu-id="ba67f-106">Migrate response groups</span></span>

<span data-ttu-id="ba67f-107">对于业务服务器 2019年池用户移动到 Skype 后，您可以迁移响应组。</span><span class="sxs-lookup"><span data-stu-id="ba67f-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="ba67f-108">迁移响应组包括复制代理组、 队列、 工作流、 音频文件，并将从旧部署的响应组联系人对象移动到业务服务器 2019年池 Skype。</span><span class="sxs-lookup"><span data-stu-id="ba67f-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="ba67f-109">迁移旧版响应组后，对响应组呼叫处理中为 Business Server 2019 池 Skype 的响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="ba67f-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="ba67f-110">由旧池不再处理响应组呼叫。</span><span class="sxs-lookup"><span data-stu-id="ba67f-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ba67f-111">将所有用户都移动到业务服务器 2019年池 Skype 之前，您可以迁移响应组，尽管我们建议您先都移动所有用户。</span><span class="sxs-lookup"><span data-stu-id="ba67f-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="ba67f-112">具体而言，响应组代理的用户将不具有新功能完整的功能，直到他们会移动到 Skype 业务服务器 2019年池。</span><span class="sxs-lookup"><span data-stu-id="ba67f-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="ba67f-113">迁移响应组之前，必须部署包括响应组应用程序的业务服务器 2019年池 Skype。</span><span class="sxs-lookup"><span data-stu-id="ba67f-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="ba67f-114">安装和部署企业语音时，默认情况下激活响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="ba67f-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="ba67f-115">您可以确保通过运行**Get-csservice ApplicationServer** cmdlet 安装了响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="ba67f-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ba67f-116">在迁移旧版响应组之前，您可以在业务服务器 2019年池 Skype 创建新的 Skype 业务服务器 2019年响应组。</span><span class="sxs-lookup"><span data-stu-id="ba67f-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="ba67f-117">若要迁移响应组从旧池中到 Skype 业务服务器 2019年，您可以运行**Move-csrgsconfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ba67f-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="ba67f-118">响应组迁移 cmdlet 移动整个池的响应组配置。</span><span class="sxs-lookup"><span data-stu-id="ba67f-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="ba67f-119">不能选择要迁移的特定组、 队列或工作流。</span><span class="sxs-lookup"><span data-stu-id="ba67f-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="ba67f-120">迁移响应组后，您需要使用 Skype 业务 Server Control Panel 或 Skype 业务 Server Management Shell cmdlet 验证所有代理组、 队列和工作流都已成功。</span><span class="sxs-lookup"><span data-stu-id="ba67f-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="ba67f-121">迁移响应组时，不会删除旧版响应组。</span><span class="sxs-lookup"><span data-stu-id="ba67f-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="ba67f-122">在迁移后管理响应组时使用任一 Skype 业务 Server Control Panel 或 Skype for Business Server 命令行管理程序，您可以看到旧版响应组和 Skype 业务服务器 2019年响应组。</span><span class="sxs-lookup"><span data-stu-id="ba67f-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="ba67f-123">您应更新仅适用于业务服务器 2019年响应组 Skype。</span><span class="sxs-lookup"><span data-stu-id="ba67f-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="ba67f-124">只是为了回滚保留旧的响应组。</span><span class="sxs-lookup"><span data-stu-id="ba67f-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="ba67f-125">业务 Server Control Panel Skype 和业务 Server 命令行管理程序 Skype 迁移已完成并已经创建了新的响应组后，将显示旧和 Skype 业务服务器 2019年版本的每个响应组。</span><span class="sxs-lookup"><span data-stu-id="ba67f-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="ba67f-126">不要使用 Skype 业务 Server Control Panel 或 Skype 的业务 Server 命令行管理程序删除旧版响应组。</span><span class="sxs-lookup"><span data-stu-id="ba67f-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="ba67f-127">如果您删除一个，迁移过程中创建相应的响应组将停止工作。</span><span class="sxs-lookup"><span data-stu-id="ba67f-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="ba67f-128">停用旧池时，将删除旧版响应组。</span><span class="sxs-lookup"><span data-stu-id="ba67f-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="ba67f-129">我们建议您执行操作不删除任何数据从以前部署之前停用池。</span><span class="sxs-lookup"><span data-stu-id="ba67f-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="ba67f-130">此外，我们强烈建议您在迁移后立即导出响应组。</span><span class="sxs-lookup"><span data-stu-id="ba67f-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="ba67f-131">如果应获取删除旧的响应组，您可以从要获得再次运行业务服务器 2019年响应组的 Skype 的备份中还原您的响应组。</span><span class="sxs-lookup"><span data-stu-id="ba67f-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="ba67f-132">Skype 的业务服务器 2019年引入了一个称为**工作流类型**的新响应组功能。</span><span class="sxs-lookup"><span data-stu-id="ba67f-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="ba67f-133">**工作流类型**可以是**托管**或**非托管**。</span><span class="sxs-lookup"><span data-stu-id="ba67f-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="ba67f-134">所有响应组会都迁移与**工作流类型**设置为**非托管**和一个空的管理器列表。</span><span class="sxs-lookup"><span data-stu-id="ba67f-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="ba67f-135">运行**Move-csrgsconfiguration** cmdlet 时，代理组、 队列、 工作流和音频文件将保留在旧池回滚为了中。</span><span class="sxs-lookup"><span data-stu-id="ba67f-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="ba67f-136">如果需要回滚到旧池中，但是，您需要运行**Move-csapplicationendpoint** cmdlet 以将联系对象移回旧池。</span><span class="sxs-lookup"><span data-stu-id="ba67f-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="ba67f-137">迁移响应组配置下面的过程假定您具有旧池与业务服务器 2019年池的 Skype 之间一对一关系。</span><span class="sxs-lookup"><span data-stu-id="ba67f-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="ba67f-138">如果您计划合并或拆分池迁移和部署期间，您需要哪些旧池映射到业务服务器 2019年池的 Skype 的计划。</span><span class="sxs-lookup"><span data-stu-id="ba67f-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="ba67f-139">迁移响应组配置</span><span class="sxs-lookup"><span data-stu-id="ba67f-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="ba67f-140">登录到使用具有 RTCUniversalServerAdmins 组的成员或具有等效管理员权限的帐户的计算机上。</span><span class="sxs-lookup"><span data-stu-id="ba67f-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="ba67f-141">为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**，都单击**Microsoft Skype 的业务服务器 2019年**，，然后都单击**Skype 的业务 Server Management Shell**。</span><span class="sxs-lookup"><span data-stu-id="ba67f-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="ba67f-142">运行：</span><span class="sxs-lookup"><span data-stu-id="ba67f-142">Run:</span></span>
    
  ```
  Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
  ```

    <span data-ttu-id="ba67f-143">例如：</span><span class="sxs-lookup"><span data-stu-id="ba67f-143">For example:</span></span>
    
  ```
  Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
  ```

4. <span data-ttu-id="ba67f-144">向业务服务器 2019年池 Skype 迁移响应组和代理后，代理用于登录和注销 URL 是业务服务器 2019 URL Skype，可从**工具**菜单。</span><span class="sxs-lookup"><span data-stu-id="ba67f-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="ba67f-145">提醒代理更新为新的 URL 的任何引用，如书签。</span><span class="sxs-lookup"><span data-stu-id="ba67f-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ba67f-146">使用适用于业务 Server Control Panel Skype 验证响应组迁移</span><span class="sxs-lookup"><span data-stu-id="ba67f-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ba67f-147">登录到计算机 RTCUniversalReadOnlyAdmins 组的成员或是至少具有 CsViewOnlyAdministrator 角色成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="ba67f-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="ba67f-148">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="ba67f-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="ba67f-149">有关可用于为业务 Server Control Panel 启动 Skype 的不同方法的详细信息，请参阅[打开 Skype 业务服务器 2019年管理工具](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx)。</span><span class="sxs-lookup"><span data-stu-id="ba67f-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="ba67f-150">在左侧的导航窗格中，单击**响应组**。</span><span class="sxs-lookup"><span data-stu-id="ba67f-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="ba67f-151">在**工作流**选项卡中，确认列表中包含旧环境中的所有工作流。</span><span class="sxs-lookup"><span data-stu-id="ba67f-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="ba67f-152">单击**队列**选项卡，并确认旧环境中的所有队列都包含在列表。</span><span class="sxs-lookup"><span data-stu-id="ba67f-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="ba67f-153">单击**组**选项卡，并确认旧环境中的所有代理组都包含在列表。</span><span class="sxs-lookup"><span data-stu-id="ba67f-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ba67f-154">若要使用 Skype 业务 Server 命令行管理程序验证响应组迁移</span><span class="sxs-lookup"><span data-stu-id="ba67f-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="ba67f-155">登录到计算机 RTCUniversalReadOnlyAdmins 组的成员或是至少具有 CsViewOnlyAdministrator 角色成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="ba67f-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="ba67f-156">为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**，都单击**Microsoft Skype 的业务服务器 2019年**，，然后都单击**Skype 的业务 Server Management Shell**。</span><span class="sxs-lookup"><span data-stu-id="ba67f-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="ba67f-157">有关以下 cmdlet 的详细信息，请运行：</span><span class="sxs-lookup"><span data-stu-id="ba67f-157">For details about the following cmdlets, run:</span></span>
    
  ```
  Get-Help <cmdlet name> -Detailed
  ```

3. <span data-ttu-id="ba67f-158">运行：</span><span class="sxs-lookup"><span data-stu-id="ba67f-158">Run:</span></span>
    
  ```
  Get-CsRgsAgentGroup
  ```

4. <span data-ttu-id="ba67f-159">确认旧环境中的所有代理组都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="ba67f-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="ba67f-160">运行：</span><span class="sxs-lookup"><span data-stu-id="ba67f-160">Run:</span></span>
    
  ```
  Get-CsRgsQueue
  ```

6. <span data-ttu-id="ba67f-161">确认旧环境中的所有队列都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="ba67f-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="ba67f-162">运行：</span><span class="sxs-lookup"><span data-stu-id="ba67f-162">Run:</span></span>
    
  ```
  Get-CsRgsWorkflow
  ```

8. <span data-ttu-id="ba67f-163">确认旧环境中的所有工作流都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="ba67f-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
    

