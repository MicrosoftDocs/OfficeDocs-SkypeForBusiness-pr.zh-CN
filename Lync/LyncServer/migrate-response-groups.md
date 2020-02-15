---
title: 迁移响应组
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02d69bcdffdb420d0c79d049f83ab5fa23ddc968
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a><span data-ttu-id="183d3-102">迁移响应组</span><span class="sxs-lookup"><span data-stu-id="183d3-102">Migrate response groups</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="183d3-103">_**上次修改的主题：** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="183d3-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="183d3-104">将用户移动到 Lync Server 2013 池之后，可以迁移响应组。</span><span class="sxs-lookup"><span data-stu-id="183d3-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="183d3-105">迁移响应组包括将代理组、队列、工作流、音频文件和移动响应组联系人对象从旧部署复制到 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="183d3-105">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="183d3-106">迁移旧版响应组后，对响应组的呼叫由 Lync Server 2013 池中的响应组应用程序进行处理。</span><span class="sxs-lookup"><span data-stu-id="183d3-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="183d3-107">旧版池不再处理对响应组的调用。</span><span class="sxs-lookup"><span data-stu-id="183d3-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="183d3-108">虽然您可以在将所有用户移动到 Lync Server 2013 池之前迁移响应组，但我们建议您首先移动所有用户。</span><span class="sxs-lookup"><span data-stu-id="183d3-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="183d3-109">特别是，响应组代理的用户在移动到 Lync Server 2013 池之前，不会具有新功能的完整功能。</span><span class="sxs-lookup"><span data-stu-id="183d3-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="183d3-110">在迁移响应组之前，必须已部署包含响应组应用程序的 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="183d3-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="183d3-111">默认情况下，在部署企业语音时，会安装并激活响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="183d3-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="183d3-112">您可以通过运行**get-csservice – ApplicationServer** cmdlet 来确保响应组应用程序已安装。</span><span class="sxs-lookup"><span data-stu-id="183d3-112">You can ensure that the Response Group application is installed by running the **Get-CsService –ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="183d3-113">您可以先在 Lync Server 2013 池中创建新的 Lync Server 2013 响应组，然后再迁移旧版响应组。</span><span class="sxs-lookup"><span data-stu-id="183d3-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="183d3-114">若要将响应组从旧版池迁移到 Lync Server 2013，请运行**CsRgsConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="183d3-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="183d3-115">响应组迁移 cmdlet 将移动整个池的响应组配置。</span><span class="sxs-lookup"><span data-stu-id="183d3-115">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="183d3-116">您不能选择特定组、队列或工作流进行迁移。</span><span class="sxs-lookup"><span data-stu-id="183d3-116">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="183d3-117">迁移响应组之后，需要使用 Lync Server 控制面板或 Lync Server 命令行管理程序 cmdlet 来验证是否已成功移动所有代理组、队列和工作流。</span><span class="sxs-lookup"><span data-stu-id="183d3-117">After you migrate the response groups, you need to use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<span data-ttu-id="183d3-118">迁移响应组时，不会删除 Lync Server 2010 响应组。</span><span class="sxs-lookup"><span data-stu-id="183d3-118">When you migrate response groups, the Lync Server 2010 response groups are not removed.</span></span> <span data-ttu-id="183d3-119">在迁移后使用 Lync Server 控制面板或 Lync Server 命令行管理程序管理响应组时，您可以看到 Lync Server 2010 响应组和 Lync Server 2013 响应组。</span><span class="sxs-lookup"><span data-stu-id="183d3-119">When you manage response groups after migration by using either Lync Server Control Panel or Lync Server Management Shell, you can see both the Lync Server 2010 response groups and the Lync Server 2013 response groups.</span></span> <span data-ttu-id="183d3-120">应仅将更新应用到 Lync Server 2013 响应组。</span><span class="sxs-lookup"><span data-stu-id="183d3-120">You should apply updates only to the Lync Server 2013 response groups.</span></span> <span data-ttu-id="183d3-121">仅出于回滚目的保留 Lync Server 2010 响应组。</span><span class="sxs-lookup"><span data-stu-id="183d3-121">The Lync Server 2010 response groups are retained only for rollback purposes.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="183d3-122">在完成迁移并创建新的响应组之后，Lync Server 控制面板和 Lync Server 命令行管理程序将显示每个响应组的 Lync Server 2010 和 Lync Server 2013 版本。</span><span class="sxs-lookup"><span data-stu-id="183d3-122">After the migration has been completed and the new response groups have been created, the Lync Server Control Panel and the Lync Server Management Shell will display the Lync Server 2010 and Lync Server 2013 versions of each response group.</span></span> <span data-ttu-id="183d3-123">请勿使用 Lync Server 控制面板或 Lync Server 命令行管理程序删除 Lync Server 2010 响应组。</span><span class="sxs-lookup"><span data-stu-id="183d3-123">Do not use Lync Server Control Panel or Lync Server Management Shell to remove the Lync Server 2010 response groups.</span></span> <span data-ttu-id="183d3-124">如果确实删除了一个，则在迁移过程中创建的相应响应组将停止工作。</span><span class="sxs-lookup"><span data-stu-id="183d3-124">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="183d3-125">当您停止 Lync Server 2010 池时，将删除 Lync Server 2010 响应组。</span><span class="sxs-lookup"><span data-stu-id="183d3-125">The Lync Server 2010 response groups will be removed when you decommission the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="183d3-126">建议在停用池之前不要删除之前的部署中的任何数据。</span><span class="sxs-lookup"><span data-stu-id="183d3-126">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="183d3-127">此外，强烈建议在迁移后立即导出响应组。</span><span class="sxs-lookup"><span data-stu-id="183d3-127">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="183d3-128">如果应删除 Lync Server 2010 响应组，则可以从备份中还原响应组，以获取 Lync Server 2013 响应组再次运行。</span><span class="sxs-lookup"><span data-stu-id="183d3-128">If a Lync Server 2010 response group should get removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="183d3-129">Lync Server 2013 引入了名为 "**工作流类型**" 的新响应组功能。</span><span class="sxs-lookup"><span data-stu-id="183d3-129">Lync Server 2013 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="183d3-130">“工作流类型”\*\*\*\* 可以是“托管”\*\*\*\* 的，也可以是“非托管”\*\*\*\* 的。</span><span class="sxs-lookup"><span data-stu-id="183d3-130">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="183d3-131">所有响应组都是使用设置为“非托管”\*\*\*\* 的“工作流类型”\*\*\*\* 和空管理员列表进行迁移的。</span><span class="sxs-lookup"><span data-stu-id="183d3-131">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span>

<span data-ttu-id="183d3-132">在运行 **Move-CsRgsConfiguration** cmdlet 时，代理组、队列、工作流和音频文件保留在旧版池中以用于回滚。</span><span class="sxs-lookup"><span data-stu-id="183d3-132">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="183d3-133">但如果您确实需要回滚到旧版池，则需要运行 **Move-CsApplicationEndpoint** cmdlet 将联系对象移回旧版池。</span><span class="sxs-lookup"><span data-stu-id="183d3-133">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<span data-ttu-id="183d3-134">下面的迁移响应组配置的过程假设您的旧版池和 Lync Server 2013 池之间具有一对一关系。</span><span class="sxs-lookup"><span data-stu-id="183d3-134">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="183d3-135">如果您计划在迁移和部署期间合并或拆分池，则需要规划哪些旧版池映射到哪个 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="183d3-135">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="183d3-136">迁移响应组配置</span><span class="sxs-lookup"><span data-stu-id="183d3-136">To migrate Response Group configurations</span></span>

1.  <span data-ttu-id="183d3-137">使用具有 RTCUniversalServerAdmins 组成员身份或同等管理员权限的帐户登录到计算机。</span><span class="sxs-lookup"><span data-stu-id="183d3-137">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

2.  <span data-ttu-id="183d3-138">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="183d3-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="183d3-139">以</span><span class="sxs-lookup"><span data-stu-id="183d3-139">Run:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="183d3-140">例如：</span><span class="sxs-lookup"><span data-stu-id="183d3-140">For example:</span></span>
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  <span data-ttu-id="183d3-141">将响应组和代理迁移到 Lync Server 2013 池之后，代理用于登录和注销的 URL 是 Lync Server 2013 URL，可从 "**工具**" 菜单中获取。</span><span class="sxs-lookup"><span data-stu-id="183d3-141">After you migrate response groups and agents to the Lync Server 2013 pool, the URL that agents use to sign in and sign out is a Lync Server 2013 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="183d3-142">提醒代理更新对新 URL 的所有引用（例如书签）。</span><span class="sxs-lookup"><span data-stu-id="183d3-142">Remind agents to update any references, such as bookmarks, to the new URL.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="183d3-143">使用 Lync Server 控制面板验证响应组迁移</span><span class="sxs-lookup"><span data-stu-id="183d3-143">To verify Response Group migration by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="183d3-144">使用 RTCUniversalReadOnlyAdmins 组成员帐户，或至少使用 CsViewOnlyAdministrator 角色成员帐户登录计算机。</span><span class="sxs-lookup"><span data-stu-id="183d3-144">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="183d3-145">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="183d3-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="183d3-146">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="183d3-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="183d3-147">在左侧导航窗格中，单击“响应组”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="183d3-147">In the left navigation pane, click **Response Groups**.</span></span>

4.  <span data-ttu-id="183d3-148">在 "**工作流**" 选项卡上，验证 "Lync Server 2010" 环境中的所有工作流是否都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="183d3-148">On the **Workflow** tab, verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="183d3-149">单击 "**队列**" 选项卡，并验证 "Lync Server 2010" 环境中的所有队列是否都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="183d3-149">Click the **Queue** tab, and verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

6.  <span data-ttu-id="183d3-150">单击 "**组**" 选项卡，并验证您在 Lync Server 2010 环境中的所有代理组是否都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="183d3-150">Click the **Group** tab, and verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a><span data-ttu-id="183d3-151">使用 Lync Server 命令行管理程序验证响应组迁移</span><span class="sxs-lookup"><span data-stu-id="183d3-151">To verify Response Group migration by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="183d3-152">使用 RTCUniversalReadOnlyAdmins 组成员帐户，或至少使用 CsViewOnlyAdministrator 角色成员帐户登录计算机。</span><span class="sxs-lookup"><span data-stu-id="183d3-152">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="183d3-153">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="183d3-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <span data-ttu-id="183d3-154">若要了解有关以下 cmdlet 的详细信息，请运行：</span><span class="sxs-lookup"><span data-stu-id="183d3-154">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

3.  <span data-ttu-id="183d3-155">以</span><span class="sxs-lookup"><span data-stu-id="183d3-155">Run:</span></span>
    
        Get-CsRgsAgentGroup

4.  <span data-ttu-id="183d3-156">验证 Lync Server 2010 环境中的所有代理组是否都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="183d3-156">Verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="183d3-157">以</span><span class="sxs-lookup"><span data-stu-id="183d3-157">Run:</span></span>
    
        Get-CsRgsQueue

6.  <span data-ttu-id="183d3-158">验证 Lync Server 2010 环境中的所有队列是否都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="183d3-158">Verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

7.  <span data-ttu-id="183d3-159">以</span><span class="sxs-lookup"><span data-stu-id="183d3-159">Run:</span></span>
    
        Get-CsRgsWorkflow

8.  <span data-ttu-id="183d3-160">验证 Lync Server 2010 环境中的所有工作流是否都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="183d3-160">Verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

