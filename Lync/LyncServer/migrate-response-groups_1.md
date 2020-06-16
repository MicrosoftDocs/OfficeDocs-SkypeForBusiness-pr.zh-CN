---
title: 迁移响应组
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48184250
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de012d0886c51cd70d5003beb24053ff86af05b7
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a><span data-ttu-id="a3c7a-102">迁移响应组</span><span class="sxs-lookup"><span data-stu-id="a3c7a-102">Migrate response groups</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3c7a-103">_**上次修改的主题：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="a3c7a-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="a3c7a-104">将用户移动到 Lync Server 2013 池之后，可以迁移响应组。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="a3c7a-105">迁移响应组包括复制代理组、队列、工作流和音频文件，以及将响应组联系人对象从旧部署移动到 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-105">Migrating response groups includes copying agent groups, queues, workflows, and audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="a3c7a-106">迁移旧版响应组后，对响应组的呼叫由 Lync Server 2013 池中的响应组应用程序进行处理。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="a3c7a-107">旧版池不再处理对响应组的调用。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a3c7a-108">虽然您可以在将所有用户移动到 Lync Server 2013 池之前迁移响应组，但我们建议您首先移动所有用户。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="a3c7a-109">特别是，响应组代理的用户在移动到 Lync Server 2013 池之前，不会具有新功能的完整功能。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="a3c7a-110">在迁移响应组之前，必须已部署包含响应组应用程序的 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="a3c7a-111">默认情况下，在部署企业语音时，会安装并激活响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="a3c7a-112">您可以通过运行**get-csservice – ApplicationServer** cmdlet 来确保响应组应用程序已安装。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-112">You can ensure that the Response Group application is installed by running the **Get-CsService–ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a3c7a-113">您可以先在 Lync Server 2013 池中创建新的 Lync Server 2013 响应组，然后再迁移旧版响应组。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="a3c7a-114">若要将响应组从旧版池迁移到 Lync Server 2013，请运行**CsRgsConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="a3c7a-115">在运行 **Move-CsRgsConfiguration** 之前，您必须先安装 Windows Management Instrumentation (WMI) Backward Compatibility 接口包。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-115">Before you can run **Move-CsRgsConfiguration**, you must first install the Windows Management Instrumentation (WMI) Backward Compatibility interfaces package.</span></span> <span data-ttu-id="a3c7a-116">可通过运行 OCSWMIBC.msi 来安装此应用程序。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-116">Install this application by running OCSWMIBC.msi.</span></span> <span data-ttu-id="a3c7a-117">OCSWMIBC.msi 位于安装介质上的 Setup 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-117">You can find OCSWMIBC.msi on the installation media in the Setup folder.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a3c7a-118">响应组迁移 cmdlet 将移动整个池的响应组配置。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="a3c7a-119">您不能选择特定组、队列或工作流进行迁移。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-119">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="a3c7a-120">迁移响应组之后，需要更新正式代理用于登录到其响应组的 URL，并使用 Lync Server 控制面板或 Lync Server 命令行管理程序 cmdlet 验证是否成功移动了所有代理组、队列和工作流。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-120">After you migrate the response groups, you need to update the URL that formal agents use to sign into and out of their response groups, and use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="a3c7a-121">迁移响应组时，不会删除 Office 通信服务器 2007 R2 响应组。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-121">When you migrate response groups, the Office Communications Server 2007 R2 response groups are not removed.</span></span> <span data-ttu-id="a3c7a-122">请勿删除 Office 通信服务器 2007 R2 响应组。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-122">Do not remove Office Communications Server 2007 R2 response groups.</span></span> <span data-ttu-id="a3c7a-123">如果删除 Office 通信服务器 2007 R2 响应组，Lync Server 2013 中的响应组将停止工作。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-123">If you remove an Office Communications Server 2007 R2 response group, the response groups in Lync Server 2013 stop working.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a3c7a-124">建议在停用池之前不要删除之前的部署中的任何数据。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-124">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="a3c7a-125">此外，强烈建议在迁移后立即导出响应组。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-125">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="a3c7a-126">如果删除了 Office 通信服务器 2007 R2 响应组，则可以从备份中还原响应组，以获取 Lync Server 2013 响应组再次运行。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-126">If an Office Communications Server 2007 R2 response group gets removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="a3c7a-127">在运行 **Move-CsRgsConfiguration** cmdlet 时，代理组、队列、工作流和音频文件保留在旧版池中以用于回滚。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-127">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="a3c7a-128">但如果您确实需要回滚到旧版池，则需要运行 **Move-CsApplicationEndpoint** cmdlet 将联系对象移回旧版池。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-128">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a3c7a-129">建议在停用旧池之前不要删除其中的任何响应组数据。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-129">We recommend that you don't delete any response group data from the legacy pool until you decommission the pool.</span></span>



</div>

<span data-ttu-id="a3c7a-130">迁移响应组配置后遵循的过程假定您的旧池和 Lync Server 2013 池之间具有一对一关系。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-130">The procedure that follows for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="a3c7a-131">如果您计划在迁移和部署期间合并或拆分池，则需要规划哪些旧版池映射到哪个 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-131">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="a3c7a-132">迁移响应组配置</span><span class="sxs-lookup"><span data-stu-id="a3c7a-132">To Migrate Response Group Configurations</span></span>

1.  <span data-ttu-id="a3c7a-133">在安装介质的 Setup 文件夹中找到 OCSWMIBC.msi 并安装它。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-133">Locate OCSWMIBC.msi in the Setup folder of the installation media and install it.</span></span>

2.  <span data-ttu-id="a3c7a-134">使用具有 RTCUniversalServerAdmins 组成员身份或同等管理员权限的帐户登录到计算机。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-134">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

3.  <span data-ttu-id="a3c7a-135">打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-135">Open the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="a3c7a-136">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="a3c7a-136">At the command line, type the following:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="a3c7a-137">例如：</span><span class="sxs-lookup"><span data-stu-id="a3c7a-137">For example:</span></span>
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  <span data-ttu-id="a3c7a-138">如果您在 Office 通信服务器 2007 R2 环境中为 Microsoft Office Communicator 2007 R2 部署了 "响应组" 选项卡，请从 Office Communicator 2007 R2 tabs.xml 文件中删除该选项卡。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-138">If you deployed the Response Group tab for Microsoft Office Communicator 2007 R2 in your Office Communications Server 2007 R2 environment, remove the tab from the Office Communicator 2007 R2 tabs.xml file.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a3c7a-139">正式代理会在接收呼叫之前，先使用响应组选项卡登录其响应组。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-139">Formal agents used the Response Group tab to sign in to their response groups before they could receive calls.</span></span> <span data-ttu-id="a3c7a-140">如果部署了 "响应组" 选项卡，则在部署 Office Communicator 2007 R2 tabs.xml 文件时选择其位置。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-140">If you deployed the Response Group tab, you chose the location for the Office Communicator 2007 R2 tabs.xml file when you deployed it.</span></span>

    
    </div>

6.  <span data-ttu-id="a3c7a-141">向用户提供代理登录和注销其响应组所需的更新 URL。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-141">Provide users with the updated URL that agents need to sign into and out of their response groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a3c7a-142">URL 通常为 https://webpoolFQDN/RgsClients/Tab.aspx ，其中 webpoolFQDN 是与您刚迁移到 Lync Server 2013 的池关联的 web 池的完全限定域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-142">The URL is typically https://webpoolFQDN/RgsClients/Tab.aspx, where webpoolFQDN is the fully qualified domain name (FQDN) of the web pool that is associated with the pool that you just migrated to Lync Server 2013.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a3c7a-143">用户升级到 Lync 2013 后不需要执行此步骤，因为 URL 可从 Lync 的 "<STRONG>工具</STRONG>" 菜单中获取。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-143">This step is not required after users upgrade to Lync 2013 because the URL is available from the <STRONG>Tools</STRONG> menu in Lync.</span></span>

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="a3c7a-144">使用 Lync Server 控制面板验证响应组迁移的具体方法</span><span class="sxs-lookup"><span data-stu-id="a3c7a-144">To Verify Response Group Migration by Using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a3c7a-145">打开“Lync Server 控制面板”。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-145">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="a3c7a-146">在左侧导航窗格中，单击“响应组”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-146">In the left navigation pane, click **Response Groups**.</span></span>

3.  <span data-ttu-id="a3c7a-147">在 "**工作流**" 选项卡上，验证 "Office 通信服务器 2007 R2" 环境中的所有工作流是否都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-147">On the **Workflow** tab, verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="a3c7a-148">单击 "**队列**" 选项卡，并验证 "Office 通信服务器 2007 R2" 环境中的所有队列是否都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-148">Click the **Queue** tab, and verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

5.  <span data-ttu-id="a3c7a-149">单击 "**组**" 选项卡，并验证 "Office 通信服务器 2007 R2" 环境中的所有代理组是否都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-149">Click the **Group** tab, and verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a><span data-ttu-id="a3c7a-150">使用 Cmdlet 验证响应组迁移</span><span class="sxs-lookup"><span data-stu-id="a3c7a-150">To Verify Response Group Migration by Using Cmdlets</span></span>

1.  <span data-ttu-id="a3c7a-151">打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-151">Open the Lync Server Management Shell.</span></span>
    
    <span data-ttu-id="a3c7a-152">若要了解有关以下 cmdlet 的详细信息，请运行：</span><span class="sxs-lookup"><span data-stu-id="a3c7a-152">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

2.  <span data-ttu-id="a3c7a-153">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="a3c7a-153">At the command line, type the following:</span></span>
    
        Get-CsRgsAgentGroup

3.  <span data-ttu-id="a3c7a-154">验证 Office 通信服务器 2007 R2 环境中的所有代理组是否都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-154">Verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="a3c7a-155">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="a3c7a-155">At the command line, type the following:</span></span>
    
        Get-CsRgsQueue

5.  <span data-ttu-id="a3c7a-156">验证 Office 通信服务器 2007 R2 环境中的所有队列是否都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-156">Verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

6.  <span data-ttu-id="a3c7a-157">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="a3c7a-157">At the command line, type the following:</span></span>
    
        Get-CsRgsWorkflow

7.  <span data-ttu-id="a3c7a-158">验证您的 Office 通信服务器 2007 R2 环境中的所有工作流是否都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="a3c7a-158">Verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

