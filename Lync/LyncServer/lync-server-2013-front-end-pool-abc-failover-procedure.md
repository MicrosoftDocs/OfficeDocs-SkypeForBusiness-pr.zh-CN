---
title: Lync Server 2013：前端池 ABC 故障转移过程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool ABC failover procedure
ms:assetid: 67763ad3-6796-45eb-a486-901f21ac1a95
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945635(v=OCS.15)
ms:contentKeyID: 51541486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa82180853e8835782d1e39d56fe595e5c7b09b2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500799"
---
# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a><span data-ttu-id="90739-102">Lync Server 2013 中的前端池 ABC 故障转移过程</span><span class="sxs-lookup"><span data-stu-id="90739-102">Front End pool ABC failover procedure in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90739-103">_**上次修改的主题：** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="90739-103">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="90739-104">使用以下步骤执行 ABC 故障转移过程。</span><span class="sxs-lookup"><span data-stu-id="90739-104">Use the following steps to perform the ABC failover procedure.</span></span> <span data-ttu-id="90739-105">此过程包含每个步骤的简要说明，以及要针对每个步骤运行的命令和 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="90739-105">This procedure contains a high-level description of each step, followed by commands and cmdlets to be run for each step.</span></span>

<span data-ttu-id="90739-106">若要运行 cmdlet，请使用 "以管理员身份运行" 打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="90739-106">To run the cmdlets, open a Lync Server Management Shell using Run as Administrator.</span></span>

<div>

## <a name="to-perform-an-abc-failover"></a><span data-ttu-id="90739-107">执行 ABC 故障转移</span><span class="sxs-lookup"><span data-stu-id="90739-107">To Perform an ABC Failover</span></span>

1.  <span data-ttu-id="90739-108">检查池 A 是否是中央管理服务器 (CMS) 的主机。</span><span class="sxs-lookup"><span data-stu-id="90739-108">Check whether the pool A is the host for the Central Management Server (CMS).</span></span>
    
      - <span data-ttu-id="90739-109">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="90739-109">Run the following cmdlet:</span></span>
        
            Get-CsService -CentralManagement
        
        <span data-ttu-id="90739-110">如果活动 CMS 的 Identity 字段指向池 A 的 (FQDN) 的完全限定的域名，则可以使用此过程中的步骤2和步骤3先对中央管理服务器进行故障转移。</span><span class="sxs-lookup"><span data-stu-id="90739-110">If the Identity field of the active CMS points to the fully qualified domain name (FQDN) of Pool A, then you use steps 2 and 3 of this procedure to fail over the Central Management Server first.</span></span> <span data-ttu-id="90739-111">否则，请跳到步骤4。</span><span class="sxs-lookup"><span data-stu-id="90739-111">Otherwise, skip to step 4.</span></span>

2.  <span data-ttu-id="90739-112">通过运行以下 cmdlet，在灾难恢复模式下将 CMS 故障转移到 Pool B：</span><span class="sxs-lookup"><span data-stu-id="90739-112">Fail over the CMS to Pool B in disaster recovery mode by running the following cmdlet:</span></span>
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    <span data-ttu-id="90739-113">执行此操作后，我们建议您将 CMS 从池 B 移到另一个现有配对池，以实现额外的恢复。</span><span class="sxs-lookup"><span data-stu-id="90739-113">After you do this, we recommend that you move the CMS from pool B to another existing paired pool for extra resiliency.</span></span> <span data-ttu-id="90739-114">有关详细信息，请参阅 [move-csmanagementserver](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)。。</span><span class="sxs-lookup"><span data-stu-id="90739-114">For details, see [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..</span></span>

3.  <span data-ttu-id="90739-115">如果池 A 包含 CMS，请将 .LIS 配置从 pool A 导入到 pool B 的 .LIS 数据库中 (.Lis) 中。</span><span class="sxs-lookup"><span data-stu-id="90739-115">If Pool A contains CMS, import the LIS configuration from pool A into pool B’s LIS database (Lis.mdf).</span></span> <span data-ttu-id="90739-116">仅当您定期备份 IIS 数据时，这才有效。</span><span class="sxs-lookup"><span data-stu-id="90739-116">This will work only if you have been backing up LIS data on a regular basis.</span></span> <span data-ttu-id="90739-117">若要导入 .LIS 配置，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="90739-117">To import the LIS configuration, run the following cmdlets:</span></span>
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  <span data-ttu-id="90739-118">将已备份的 Lync Server 响应组服务工作流从池 A 导入到池 B。</span><span class="sxs-lookup"><span data-stu-id="90739-118">Import backed-up Lync Server Response Group service workflows from pool A into pool B.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="90739-119">目前， <STRONG>CsRgsConfiguration</STRONG> cmdlet 要求池 A 上的队列和工作流名称与池 B 上的队列和工作流名称不同。如果名称不是唯一的，您将在运行 <STRONG>CsRgsConfiguration</STRONG> cmdlet 时收到错误，在继续执行 <STRONG>CsRgsConfiguration</STRONG> cmdlet 之前，将需要在 pool B 中重命名队列和工作流。</span><span class="sxs-lookup"><span data-stu-id="90739-119">Currently, the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet requires that the queue and workflow names on pool A are distinct from the queue and workflow names on pool B. If the names are not distinct, you will get an error when running the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet, and the queues and workflows will need to be renamed in pool B before proceeding with <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet.</span></span>

    
    </div>
    
    <span data-ttu-id="90739-120">有两种方法可将响应组配置从池 A 导入到池 B。使用哪个选项取决于是否要使用 pool A 中的应用程序级设置覆盖池 B 的应用程序级别设置。</span><span class="sxs-lookup"><span data-stu-id="90739-120">You have two options for importing the Response Group configuration from pool A to pool B. Which option you use depends on whether you want to overwrite the application-level settings of pool B with the application-level settings in pool A.</span></span>
    
      - <span data-ttu-id="90739-121">如果要覆盖 Pool B 设置，请运行带**ReplaceExistingSettings**选项的**CsRgsConfiguration** cmdlet：</span><span class="sxs-lookup"><span data-stu-id="90739-121">If you want to overwrite the Pool B settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="90739-122">如果您不想覆盖池 B 设置，请使用不带**ReplaceExistingSettings**选项的**CsRgsConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="90739-122">If you do not want to overwrite the Pool B settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="90739-123">请注意，如果您不想覆盖备份池的应用程序级别设置 (池 B) 使用主池的设置 (池 A) ，池 A 的应用程序级设置将会丢失（如果池 A 丢失），因为响应组应用程序只能为每个池存储一组应用程序级别的设置。</span><span class="sxs-lookup"><span data-stu-id="90739-123">Keep in mind that if you do not want to overwrite the application-level settings of the backup pool (pool B) with the settings of the primary pool (pool A), pool A’s application-level settings will be lost if pool A is lost, because the Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="90739-124">部署池 C 以替换池 A 时，必须重新配置应用程序级别的设置，包括默认的保持音乐的音频文件。</span><span class="sxs-lookup"><span data-stu-id="90739-124">When pool C is deployed to replace pool A, the application-level settings must be reconfigured, including the default music-on-hold audio file.</span></span>

    
    </div>

5.  <span data-ttu-id="90739-125">运行以下 cmdlet 以验证响应组配置是否成功，并显示导入的响应组。</span><span class="sxs-lookup"><span data-stu-id="90739-125">Verify that the Response Group configuration import was successful by running the following cmdlets to display the imported response groups.</span></span> <span data-ttu-id="90739-126">请注意，导入的响应组仍然归池 A 所有。</span><span class="sxs-lookup"><span data-stu-id="90739-126">Note that the imported response groups are still owned by pool A.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  <span data-ttu-id="90739-127">对于未分配号码，请将使用 "公告" 的未分配号码范围作为选定的宣告服务从池 A 移动到 pool B。为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="90739-127">For Unassigned Numbers, move the Unassigned Number ranges that are using "Announcement" as the selected announcement service from pool A to pool B. To do so:</span></span>
    
      - <span data-ttu-id="90739-128">重新创建在池 B 上的池 A 中部署的所有通知。如果在池 A 中部署通知时使用了任何音频文件，则需要这些文件来重新创建池 B 中的通知。若要在 pool B 中重新创建通知，请使用 **CsAnnouncement** cmdlet，并将 pool b 用作父服务。</span><span class="sxs-lookup"><span data-stu-id="90739-128">Re-create all announcements that were deployed in pool A on pool B. If any audio files were used when deploying the announcements in pool A, these files will be needed to re-create the announcements in pool B. To re-create the announcements in pool B, use the **New-CsAnnouncement** cmdlets, with pool B as the Parent service.</span></span>
    
      - <span data-ttu-id="90739-129">将作为池 A 中的公告的所有未分配号码范围重新设定为 pool B 中新部署的宣告。为目标为池 A 的公告的每个未分配号码范围运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="90739-129">Retarget all the Unassigned Number ranges that are targeting an announcement in pool A to the newly deployed announcements in pool B. Run the following cmdlet for every Unassigned Number range targeting an announcement of pool A:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="90739-130">如果未分配的号码范围将 "Exchange UM" 用作选定的通知服务，则不需要执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="90739-130">This step is not required for unassigned number ranges that use "Exchange UM" as the selected announcement service.</span></span>

    
    </div>

7.  <span data-ttu-id="90739-131">通过运行以下 cmdlet，将灾难恢复中的池 A 故障转移到 Pool B (DR) 模式：</span><span class="sxs-lookup"><span data-stu-id="90739-131">Fail over Pool A to Pool B in Disaster Recovery (DR) mode, by running the following cmdlet:</span></span>
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  <span data-ttu-id="90739-132">构建池 C，但不启动池 C 上的任何服务。</span><span class="sxs-lookup"><span data-stu-id="90739-132">Build pool C, but do not start any services on pool C.</span></span>
    
    <span data-ttu-id="90739-133">请注意，可以使用步骤5和6同时执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="90739-133">Note that this step can be carried out concurrently with steps 5 and 6.</span></span>

9.  <span data-ttu-id="90739-134">通过运行以下 cmdlet 强制驻留在池 A 上的用户移动到池 C：</span><span class="sxs-lookup"><span data-stu-id="90739-134">Force users homed on pool A to move to pool C by running the following cmdlet:</span></span>
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    <span data-ttu-id="90739-135">在这种情况下，驻留在池 A 上的用户将开始遇到服务中断。</span><span class="sxs-lookup"><span data-stu-id="90739-135">At this point, users homed on pool A will begin to experience a service outage.</span></span> <span data-ttu-id="90739-136">此中断将持续到第16步，在此期间启动池 C 上的点服务。</span><span class="sxs-lookup"><span data-stu-id="90739-136">This outage will continue until step 16, at which point services are started on pool C.</span></span>

10. <span data-ttu-id="90739-137">通过运行以下 cmdlet 强制池 A 的会议目录移动到池 C：</span><span class="sxs-lookup"><span data-stu-id="90739-137">Force the conference directory of pool A to move to pool C by running the following cmdlet:</span></span>
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. <span data-ttu-id="90739-138">通过运行以下 cmdlet，强制会议自动助理 (CAA) Contact 对象从池 A 移到池 C：</span><span class="sxs-lookup"><span data-stu-id="90739-138">Force the Conference Auto Attendant (CAA) Contact Object to move from pool A to pool C by running the following cmdlet:</span></span>
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. <span data-ttu-id="90739-139">将会议内容从池 B 复制到池 C。</span><span class="sxs-lookup"><span data-stu-id="90739-139">Copy conference content from pool B to pool C.</span></span>

13. <span data-ttu-id="90739-140">从 pool B 导出用户数据，并通过运行以下 cmdlet 将用户数据导入到池 C 中：</span><span class="sxs-lookup"><span data-stu-id="90739-140">Export user data from pool B and import the user data into pool C by running the following cmdlets:</span></span>
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. <span data-ttu-id="90739-141">将已备份的呼叫寄存应用程序数据从池 A 还原到池 C，并将池 A 的呼叫寄存轨道范围分配给 pool C。</span><span class="sxs-lookup"><span data-stu-id="90739-141">Restore backed-up Call Park application data from pool A into pool C and assign the Call Park orbit ranges of pool A to pool C.</span></span>
    
      - <span data-ttu-id="90739-142">您可以通过 Lync Server 控制面板或 Lync Server 命令行管理程序，将池 A 的呼叫寄存轨道范围重新分配到池 C。</span><span class="sxs-lookup"><span data-stu-id="90739-142">You can reassign a Call Park orbit range of pool A to pool C either through the Lync Server Control Panel or the Lync Server Management Shell.</span></span> <span data-ttu-id="90739-143">对于 Lync Server 命令行管理程序，请为分配给池 A (的每个呼叫寄存通道范围运行以下 cmdlet。请注意，Identity 参数引用属于池 A) 的呼叫寄存轨道范围：</span><span class="sxs-lookup"><span data-stu-id="90739-143">For the Lync Server Management Shell, run the following cmdlet for every Call Park orbit range assigned to pool A (note that the Identity parameter refers to the Call Park Orbit Ranges that belong to pool A):</span></span>
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - <span data-ttu-id="90739-144">如果已为池 A 中的呼叫寄存配置了自定义的已保留音乐，请在池 C 中还原呼叫寄存自定义的保留音乐文件。</span><span class="sxs-lookup"><span data-stu-id="90739-144">If a customized music-on-hold has been configured for Call Park in pool A, restore the Call Park customized music-on-hold file in pool C.</span></span>
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        <span data-ttu-id="90739-145">例如：</span><span class="sxs-lookup"><span data-stu-id="90739-145">For example:</span></span>
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - <span data-ttu-id="90739-146">最后，使用 **CsCpsConfiguration** cmdlet 在 pool C 上重新配置呼叫寄存设置。</span><span class="sxs-lookup"><span data-stu-id="90739-146">Finally, reconfigure the Call Park settings on pool C by using the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="90739-147">呼叫寄存应用程序只能为每个池存储一组设置和一个自定义的音乐保留音频文件，并且在发生灾难时不会备份或保留这些设置。</span><span class="sxs-lookup"><span data-stu-id="90739-147">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool, and these settings are not backed up or preserved in the event of a disaster.</span></span>

15. <span data-ttu-id="90739-148">如果用于持久聊天的下一个跃点池指向池 A，请发出并发布拓扑更改，以便下一个跃点服务器指向池 C。</span><span class="sxs-lookup"><span data-stu-id="90739-148">If the next hop pool for Persistent Chat is pointing to pool A, make and publish topology changes so that the next hop server points to pool C.</span></span>
    
      - <span data-ttu-id="90739-149">在拓扑生成器中，将持久聊天池更改为指向池 C 作为其下一个跃点。</span><span class="sxs-lookup"><span data-stu-id="90739-149">In Topology Builder, change the Persistent Chat pool to point to Pool C as its next hop.</span></span> <span data-ttu-id="90739-150">为此，请右键单击 "持久聊天" 池，然后单击 " **常规** " 选项卡，然后在 " **下一个跃点池**" 中键入 pool C 的名称。</span><span class="sxs-lookup"><span data-stu-id="90739-150">To do so, right-click on the Persistent Chat pool, then click the **General** tab, and then type the name of Pool C in **Next Hop Pool**.</span></span>
    
      - <span data-ttu-id="90739-151">通过运行以下 cmdlet 启动 pool C 上的服务：</span><span class="sxs-lookup"><span data-stu-id="90739-151">Start services on pool C by running the following cmdlet:</span></span>
        
            Start-csWindowsService
    
    <span data-ttu-id="90739-152">在这种情况下，用户最初驻留在池 A 上的服务中断会结束。</span><span class="sxs-lookup"><span data-stu-id="90739-152">At this point, the service outage ends for users originally homed on pool A.</span></span>

16. <span data-ttu-id="90739-153">通过运行以下 cmdlet，导出来自 pool A 的 pool B 所拥有的 Lync Server 响应组服务工作流，以将其导入到 pool C 中：</span><span class="sxs-lookup"><span data-stu-id="90739-153">Export Lync Server Response Group service workflows from pool B owned by pool A for import into pool C by running the following cmdlet:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. <span data-ttu-id="90739-154">将 Lync Server 响应组服务工作流从池 B 导入池 C。</span><span class="sxs-lookup"><span data-stu-id="90739-154">Import Lync Server Response Group service workflows into pool C from pool B.</span></span>
    
    <span data-ttu-id="90739-155">有两种方法可用于将响应组配置从池 B 导入池 C。使用哪个选项取决于您是否要使用池 B 中的应用程序级设置覆盖池 C 的应用程序级别设置。</span><span class="sxs-lookup"><span data-stu-id="90739-155">You have two options are for importing the Response Group configuration from pool B to pool C. Which option you use depends on whether you want to overwrite the application-level settings of pool C with the application-level settings in pool B.</span></span>
    
      - <span data-ttu-id="90739-156">如果要覆盖 Pool C 设置，请运行带**ReplaceExistingSettings**选项的**CsRgsConfiguration** cmdlet：</span><span class="sxs-lookup"><span data-stu-id="90739-156">If you want to overwrite the Pool C settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="90739-157">如果您不想覆盖 Pool C 设置，请使用不带**ReplaceExistingSettings**选项的**CsRgsConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="90739-157">If you do not want to overwrite the Pool C settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="90739-158">请注意，如果您不想使用备份池的设置覆盖池 C 的应用程序级别设置 (池 B) ，池 B 的应用程序级别设置将丢失，因为响应组应用程序只能为每个池存储一组应用程序级别的设置。</span><span class="sxs-lookup"><span data-stu-id="90739-158">Keep in mind that if you do not want to overwrite the application-level settings of Pool C with the settings of the backup pool (pool B), pool B’s application-level settings will be lost because the Response Group application can store only one set of application-level settings per pool.</span></span>

    
    </div>

18. <span data-ttu-id="90739-159">运行以下 cmdlet 以验证响应组配置导入是否成功，以显示已导入到池 C 的响应组。</span><span class="sxs-lookup"><span data-stu-id="90739-159">Verify that the Response Group configuration import was successful by running the following cmdlets to display the response groups that have been imported to Pool C.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. <span data-ttu-id="90739-160">在池 C 中验证导入的配置后，从池 B 中删除主池拥有的响应组。这将最大限度地减少响应组的停机时间。</span><span class="sxs-lookup"><span data-stu-id="90739-160">When the imported configuration has been verified in pool C, remove the response groups owned by the primary pool from pool B. This will minimize the downtime of the response groups.</span></span>
    
    <span data-ttu-id="90739-161">此步骤将使用导出的配置创建一个新文件，然后从池 B 中删除该文件。</span><span class="sxs-lookup"><span data-stu-id="90739-161">This step creates a new file with the exported configuration, and then removes the file from pool B.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. <span data-ttu-id="90739-162">移动到池 C 从池 A 移至池 B 的未分配号码范围。</span><span class="sxs-lookup"><span data-stu-id="90739-162">Move to pool C the Unassigned Number ranges that were moved from pool A to pool B.</span></span>
    
      - <span data-ttu-id="90739-163">在池 C 中重新创建从池 B 中的池 A 重新创建的所有通知。如果在部署要移动的通知时使用了任何音频文件，则需要使用这些文件在 pool C 中重新创建通知。若要在 pool C 中重新创建通知，请使用 **CsAnnouncement** cmdlet，将 pool c 用作父服务。</span><span class="sxs-lookup"><span data-stu-id="90739-163">Re-create in pool C all announcements that were re-created from pool A in pool B. If any audio files were used when deploying the announcements to be moved, you will need to use these files to re-create the announcements in pool C. To re-create the announcements in pool C, use the **New-CsAnnouncement** cmdlets, with pool C as the Parent service.</span></span>
    
      - <span data-ttu-id="90739-164">从池 C 重新定位到池 B 的所有未分配号码范围。为需要重定目标的每个未分配号码范围运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="90739-164">Retarget to pool C all the unassigned number ranges that were retargeted from pool A to pool B. Run the following cmdlet for every Unassigned Number range that needs to be retargeted:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - <span data-ttu-id="90739-165"> (可选) 从池 B 中删除如果它们不再在池 B 中使用，则在池 C 中重新创建的通知。若要删除通知，请使用 **CsAnnouncement** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="90739-165">(Optional) Remove from pool B the announcements that were re-created in pool C if they are no longer in use in pool B. To remove announcements, use the **Remove-CsAnnouncement** cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="90739-166">如果未分配的号码范围将 "Exchange UM" 用作通知服务，则不需要执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="90739-166">This step is not required for unassigned number ranges that use "Exchange UM" as the announcement service.</span></span>

        
        </div>

21. <span data-ttu-id="90739-167">通过运行以下 cmdlet 清除 pool A 中的 pool A 的用户数据：</span><span class="sxs-lookup"><span data-stu-id="90739-167">Clean up user data of pool A in pool B by running the following cmdlet:</span></span>
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. <span data-ttu-id="90739-168">在拓扑生成器中执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="90739-168">Do the following in Topology Builder:</span></span>
    
      - <span data-ttu-id="90739-169">Unpair 池 A 和池 B 对池 B 和池 C。然后，从拓扑中删除池 A 并发布它。</span><span class="sxs-lookup"><span data-stu-id="90739-169">Unpair pool A and pool B. Pair pool B and pool C. Then remove Pool A from the topology and publish it.</span></span> <span data-ttu-id="90739-170">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="90739-170">To do so:</span></span>
        
          - <span data-ttu-id="90739-171">在拓扑生成器中，右键单击 "池 B"，然后单击 " **编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="90739-171">In Topology Builder, right-click on Pool B, and then click **Edit Properties**.</span></span>
        
          - <span data-ttu-id="90739-172">在左窗格中单击 " **弹性** "。</span><span class="sxs-lookup"><span data-stu-id="90739-172">Click **Resiliency** in the left pane.</span></span>
        
          - <span data-ttu-id="90739-173">在 "关联的 **备份池**" 下面的框中，选择 "池 C"。请注意，"关联的备份池" 选择框最初将显示池 A，这是因为以前与此池相关联的池 B。</span><span class="sxs-lookup"><span data-stu-id="90739-173">In the box below **Associated Backup Pool**, select Pool C. Note that the Associated Backup Pool selection box will initially display pool A, because pool B was previously associated with this pool.</span></span>
        
          - <span data-ttu-id="90739-174">选择“语音的自动故障转移和故障回复”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="90739-174">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
            
            <span data-ttu-id="90739-175">当您查看该池的详细信息时，关联的池现在显示在“复原”\*\*\*\* 下的右窗格中。</span><span class="sxs-lookup"><span data-stu-id="90739-175">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span>
        
          - <span data-ttu-id="90739-176">在控制台树中，右键单击 "池 A"，然后单击 "删除"。</span><span class="sxs-lookup"><span data-stu-id="90739-176">In the console tree, right-click pool A, and then click Delete.</span></span>
        
          - <span data-ttu-id="90739-177">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="90739-177">Publish the topology.</span></span>

23. <span data-ttu-id="90739-178">运行 pool C 上的引导应用程序以安装备份服务应用程序，然后通过从池中的本地计算机上的部署文件夹中运行以下命令来启动 backup service 应用程序：</span><span class="sxs-lookup"><span data-stu-id="90739-178">Run the bootstrapping application on pool C to install the backup service application, and then start the backup service application by running the following from the deployment folder on a local machine in pool C:</span></span>
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. <span data-ttu-id="90739-179">运行以下 cmdlet，在池 B 上重新启动备份服务应用程序：</span><span class="sxs-lookup"><span data-stu-id="90739-179">Restart the backup service application on pool B by running the following cmdlets:</span></span>
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. <span data-ttu-id="90739-180">如果 pool C 是标准版 (SE) 池和池 B 拥有 CMS，请通过运行以下 cmdlet 在池 C 上手动安装 CMS 数据库：</span><span class="sxs-lookup"><span data-stu-id="90739-180">If pool C is a Standard Edition (SE) Pool and pool B has CMS, install the CMS database manually on pool C by running the following cmdlet:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. <span data-ttu-id="90739-181">调用备份服务，将旧会议内容从池 B 同步到配对 B 和 C 之前生成的池 C，并将新的会议内容从池 C 同步到在启动池 C 之后生成的池 B，并将 B 和 C 结合在一起。</span><span class="sxs-lookup"><span data-stu-id="90739-181">Invoke the backup service to sync old conferencing content from pool B to pool C that was generated before pairing B and C together, and to sync new conferencing content from pool C to pool B that was generated after starting pool C and before B and C were paired together.</span></span> <span data-ttu-id="90739-182">若要执行此操作，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="90739-182">To do so, run the following cmdlets:</span></span>
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. <span data-ttu-id="90739-183">对于与池 A 关联的每个 Survivable 分支装置 X：</span><span class="sxs-lookup"><span data-stu-id="90739-183">For each Survivable Branch Appliance X associated with pool A:</span></span>
    
      - <span data-ttu-id="90739-184">运行以下 cmdlet 以关闭 SBA X：</span><span class="sxs-lookup"><span data-stu-id="90739-184">Shut down SBA X by running the following cmdlet:</span></span>
        
            Stop-CsWindowsService
    
      - <span data-ttu-id="90739-185">创建一个文件，其中包含驻留在 SBA X 上的用户的列表。当用户移回步骤30中的 SBA X 时，将需要此列表。</span><span class="sxs-lookup"><span data-stu-id="90739-185">Create a file that contains a list of users homed on SBA X. The list will be needed when the users are moved back to SBA X in step 30.</span></span> <span data-ttu-id="90739-186">若要执行此操作，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="90739-186">To do so, run the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - <span data-ttu-id="90739-187">通过运行以下 cmdlet 强制驻留在 SBA X 上的用户移动到池 C：</span><span class="sxs-lookup"><span data-stu-id="90739-187">Force users homed on SBA X to move to pool C by running the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - <span data-ttu-id="90739-188">通过先运行以下 cmdlet 来更新这些用户的数据：</span><span class="sxs-lookup"><span data-stu-id="90739-188">Update the data of these users by first running the following cmdlets:</span></span>
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        <span data-ttu-id="90739-189">然后运行以下脚本：</span><span class="sxs-lookup"><span data-stu-id="90739-189">And then run this script:</span></span>
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="90739-190">对于驻留在 Sba 上且与池 A 关联的用户，如果将这些用户移动到池 C，则会发生服务中断。</span><span class="sxs-lookup"><span data-stu-id="90739-190">A service outage will occur for users who are homed on SBAs that are associated with pool A until these users are moved to pool C.</span></span>

        
        </div>

28. <span data-ttu-id="90739-191">在拓扑生成器中，对于之前与池 A 关联的每个 SBA X，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="90739-191">In Topology Builder, for each SBA X previously associated with Pool A, do the following:</span></span>
    
      - <span data-ttu-id="90739-192">将关联更改为池 C。为此，请单击分支站点，展开 "Survivable Branch 器具" 或 "Servers" 节点，然后单击 " **Survivable Branch 设备**"。</span><span class="sxs-lookup"><span data-stu-id="90739-192">Change the association to Pool C. To do so, click the branch site, expand the Survivable Branch Appliances or Servers node, and click **Survivable Branch Appliance**.</span></span> <span data-ttu-id="90739-193">然后选择 "Survivable" 分支设备将作为池 C 连接到的 " **用户服务" 池** ，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="90739-193">Then select the **Front End pool, User Services Pool** that this Survivable Branch Appliance will connect to as Pool C, and then click **Next**.</span></span>
    
      - <span data-ttu-id="90739-194">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="90739-194">Publish the topology.</span></span> <span data-ttu-id="90739-195">若要执行此操作，请在控制台树中，右键单击新的 **Survivable 分支设备**，单击 " **拓扑**"，然后单击 " **发布**"。</span><span class="sxs-lookup"><span data-stu-id="90739-195">To do so, in the console tree, right-click the new **Survivable Branch Appliance**, click **Topology**, and then click **Publish**.</span></span>

29. <span data-ttu-id="90739-196">对于现在与池 C 关联的每个 SBA X：</span><span class="sxs-lookup"><span data-stu-id="90739-196">For each SBA X now associated with pool C:</span></span>
    
      - <span data-ttu-id="90739-197">通过在 survivable 分支设备上运行以下 cmdlet 来启动 SBA X：</span><span class="sxs-lookup"><span data-stu-id="90739-197">Start SBA X by running the following cmdlet on the survivable branch appliance:</span></span>
        
            Start-CsWindowsService
    
      - <span data-ttu-id="90739-198">通过运行以下 cmdlet，将最初驻留在 SBA X 上的用户从池 C 转移到 SBA X。</span><span class="sxs-lookup"><span data-stu-id="90739-198">Move users who were originally homed on SBA X from pool C to SBA X by running the following cmdlet.</span></span>
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

