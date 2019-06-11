---
title: 迁移响应组
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60a5bb2b2124b84adeb6a494f6f33ce867f7d416
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a><span data-ttu-id="fcfb8-102">迁移响应组</span><span class="sxs-lookup"><span data-stu-id="fcfb8-102">Migrate response groups</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fcfb8-103">_**主题上次修改时间:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="fcfb8-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="fcfb8-104">将用户移动到 Lync Server 2013 池后, 您可以迁移响应组。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="fcfb8-105">迁移响应组包括将代理组、队列、工作流、音频文件和移动响应组联系人对象从旧部署复制到 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-105">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="fcfb8-106">迁移旧版响应组后, 对响应组的呼叫由 Lync Server 2013 池中的响应组应用程序处理。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="fcfb8-107">不再通过旧版池处理对响应组的调用。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fcfb8-108">虽然你可以在将所有用户移到 Lync Server 2013 池之前迁移响应组, 但我们建议你先移动所有用户。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="fcfb8-109">特别是, 响应组代理的用户在移动到 Lync Server 2013 池之前不具有新功能的完整功能。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="fcfb8-110">在迁移响应组之前, 必须已部署包含响应组应用程序的 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="fcfb8-111">部署企业语音时, 将默认安装并激活 "响应组" 应用程序。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="fcfb8-112">你可以通过运行**CsService-ApplicationServer** cmdlet 来确保响应组应用程序已安装。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-112">You can ensure that the Response Group application is installed by running the **Get-CsService –ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fcfb8-113">在迁移旧版响应组之前, 您可以在 Lync Server 2013 池中创建新的 Lync Server 2013 响应组。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="fcfb8-114">若要将响应组从旧版池迁移到 Lync Server 2013, 请运行**CsRgsConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fcfb8-115">响应组迁移 cmdlet 移动整个池的响应组配置。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-115">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="fcfb8-116">您不能选择要迁移的特定组、队列或工作流。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-116">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="fcfb8-117">迁移响应组后, 你需要使用 Lync Server 控制面板或 Lync Server Management Shell cmdlet 验证是否已成功移动所有代理组、队列和工作流。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-117">After you migrate the response groups, you need to use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<span data-ttu-id="fcfb8-118">迁移响应组时, 不会删除 Lync Server 2010 响应组。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-118">When you migrate response groups, the Lync Server 2010 response groups are not removed.</span></span> <span data-ttu-id="fcfb8-119">如果你在迁移后通过使用 Lync Server 控制面板或 Lync Server 命令行管理程序管理响应组, 你可以同时看到 Lync Server 2010 响应组和 Lync Server 2013 响应组。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-119">When you manage response groups after migration by using either Lync Server Control Panel or Lync Server Management Shell, you can see both the Lync Server 2010 response groups and the Lync Server 2013 response groups.</span></span> <span data-ttu-id="fcfb8-120">应仅将更新应用于 Lync Server 2013 响应组。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-120">You should apply updates only to the Lync Server 2013 response groups.</span></span> <span data-ttu-id="fcfb8-121">Lync Server 2010 响应组仅为回滚而保留。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-121">The Lync Server 2010 response groups are retained only for rollback purposes.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="fcfb8-122">完成迁移并创建新的响应组后, Lync Server 控制面板和 Lync Server 命令行管理程序将显示每个响应组的 Lync Server 2010 和 Lync Server 2013 版本。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-122">After the migration has been completed and the new response groups have been created, the Lync Server Control Panel and the Lync Server Management Shell will display the Lync Server 2010 and Lync Server 2013 versions of each response group.</span></span> <span data-ttu-id="fcfb8-123">请勿使用 Lync Server 控制面板或 Lync Server 命令行管理程序删除 Lync Server 2010 响应组。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-123">Do not use Lync Server Control Panel or Lync Server Management Shell to remove the Lync Server 2010 response groups.</span></span> <span data-ttu-id="fcfb8-124">如果确实删除了一个, 则迁移期间创建的相应响应组将停止工作。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-124">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="fcfb8-125">当您解除 Lync Server 2010 池时, 将删除 Lync Server 2010 响应组。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-125">The Lync Server 2010 response groups will be removed when you decommission the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fcfb8-126">我们建议您不要从以前的部署中删除任何数据, 直到解除池。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-126">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="fcfb8-127">此外, 我们强烈建议您在迁移后立即导出响应组。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-127">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="fcfb8-128">如果 Lync Server 2010 响应组应被删除, 则可以从备份还原响应组, 以使 Lync Server 2013 响应组再次运行。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-128">If a Lync Server 2010 response group should get removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="fcfb8-129">Lync Server 2013 引入了名为 "**工作流类型**" 的新响应组功能。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-129">Lync Server 2013 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="fcfb8-130">**工作流类型**可以是**托管**或**非托管**。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-130">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="fcfb8-131">将使用**工作流类型**设置为**非托管**并使用空管理器列表迁移所有响应组。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-131">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span>

<span data-ttu-id="fcfb8-132">当你运行**CsRgsConfiguration** cmdlet 时, 代理组、队列、工作流和音频文件将保留在旧版池中, 以便进行回退。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-132">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="fcfb8-133">但是, 如果确实需要回退到旧版池, 则需要运行**CsApplicationEndpoint** cmdlet 以将联系人对象移回旧版池。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-133">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<span data-ttu-id="fcfb8-134">用于迁移响应组配置的以下过程假定你的旧池和 Lync Server 2013 池之间具有一对一关系。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-134">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="fcfb8-135">如果你计划在迁移和部署期间合并或拆分池, 你需要规划哪些旧式池映射到哪些 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-135">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="fcfb8-136">迁移响应组配置</span><span class="sxs-lookup"><span data-stu-id="fcfb8-136">To migrate Response Group configurations</span></span>

1.  <span data-ttu-id="fcfb8-137">使用属于 RTCUniversalServerAdmins 组的成员的帐户登录到计算机, 或具有等效的管理员权利和权限。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-137">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

2.  <span data-ttu-id="fcfb8-138">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="fcfb8-139">运行：</span><span class="sxs-lookup"><span data-stu-id="fcfb8-139">Run:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="fcfb8-140">例如：</span><span class="sxs-lookup"><span data-stu-id="fcfb8-140">For example:</span></span>
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  <span data-ttu-id="fcfb8-141">将响应组和代理迁移到 Lync Server 2013 池后, 代理用于登录和注销的 URL 是 Lync Server 2013 URL, 可从 "**工具**" 菜单中访问。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-141">After you migrate response groups and agents to the Lync Server 2013 pool, the URL that agents use to sign in and sign out is a Lync Server 2013 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="fcfb8-142">提醒代理将任何引用 (如书签) 更新到新 URL。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-142">Remind agents to update any references, such as bookmarks, to the new URL.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="fcfb8-143">使用 Lync Server "控制面板" 验证响应组迁移</span><span class="sxs-lookup"><span data-stu-id="fcfb8-143">To verify Response Group migration by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="fcfb8-144">使用属于 RTCUniversalReadOnlyAdmins 组成员的帐户登录到计算机, 或者将该帐户的成员最少 CsViewOnlyAdministrator 角色的成员。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-144">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="fcfb8-145">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fcfb8-146">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fcfb8-147">在左侧导航窗格中, 单击 "**响应组**"。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-147">In the left navigation pane, click **Response Groups**.</span></span>

4.  <span data-ttu-id="fcfb8-148">在 "**工作流**" 选项卡上, 验证您的 Lync Server 2010 环境中的所有工作流是否都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-148">On the **Workflow** tab, verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="fcfb8-149">单击 "**队列**" 选项卡, 然后验证您的 Lync Server 2010 环境中的所有队列是否都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-149">Click the **Queue** tab, and verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

6.  <span data-ttu-id="fcfb8-150">单击 "**组**" 选项卡, 然后验证您的 Lync Server 2010 环境中的所有代理组是否都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-150">Click the **Group** tab, and verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a><span data-ttu-id="fcfb8-151">使用 Lync Server 命令行管理程序验证响应组迁移</span><span class="sxs-lookup"><span data-stu-id="fcfb8-151">To verify Response Group migration by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="fcfb8-152">使用属于 RTCUniversalReadOnlyAdmins 组成员的帐户登录到计算机, 或者将该帐户的成员最少 CsViewOnlyAdministrator 角色的成员。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-152">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="fcfb8-153">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <span data-ttu-id="fcfb8-154">有关以下 cmdlet 的详细信息, 请运行:</span><span class="sxs-lookup"><span data-stu-id="fcfb8-154">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

3.  <span data-ttu-id="fcfb8-155">运行：</span><span class="sxs-lookup"><span data-stu-id="fcfb8-155">Run:</span></span>
    
        Get-CsRgsAgentGroup

4.  <span data-ttu-id="fcfb8-156">验证您的 Lync Server 2010 环境中的所有代理组是否都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-156">Verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="fcfb8-157">运行：</span><span class="sxs-lookup"><span data-stu-id="fcfb8-157">Run:</span></span>
    
        Get-CsRgsQueue

6.  <span data-ttu-id="fcfb8-158">验证您的 Lync Server 2010 环境中的所有队列是否都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-158">Verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

7.  <span data-ttu-id="fcfb8-159">运行：</span><span class="sxs-lookup"><span data-stu-id="fcfb8-159">Run:</span></span>
    
        Get-CsRgsWorkflow

8.  <span data-ttu-id="fcfb8-160">验证您的 Lync Server 2010 环境中的所有工作流是否都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-160">Verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

