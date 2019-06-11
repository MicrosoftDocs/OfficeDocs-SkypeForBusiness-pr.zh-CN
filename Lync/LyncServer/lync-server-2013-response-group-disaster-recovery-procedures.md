---
title: Lync Server 2013 响应组灾难恢复过程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response group disaster recovery procedures
ms:assetid: b49577b7-0ca3-4f20-b614-f3a2a0046b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205186(v=OCS.15)
ms:contentKeyID: 48185171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7f28f13d1acdbdae58b1aadd6f73871af270b7d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a><span data-ttu-id="49aa9-102">Lync Server 2013 中的响应组灾难恢复过程</span><span class="sxs-lookup"><span data-stu-id="49aa9-102">Response group disaster recovery procedures in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49aa9-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="49aa9-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="49aa9-104">在灾难恢复的故障转移阶段, 响应组位于多个池中: 在主池 (不可用) 和备份池中。</span><span class="sxs-lookup"><span data-stu-id="49aa9-104">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool.</span></span> <span data-ttu-id="49aa9-105">两个池中的响应组具有相同的名称和相同的所有者 (主池), 但它们具有不同的父池。</span><span class="sxs-lookup"><span data-stu-id="49aa9-105">The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span> <span data-ttu-id="49aa9-106">在这段时间内, 响应组 cmdlet 的工作方式略有不同。</span><span class="sxs-lookup"><span data-stu-id="49aa9-106">During this time, Response Group cmdlets work a little differently.</span></span> <span data-ttu-id="49aa9-107">请确保使用以下过程中指定的参数。</span><span class="sxs-lookup"><span data-stu-id="49aa9-107">Be sure to use parameters as specified in the following procedure.</span></span> <span data-ttu-id="49aa9-108">有关 cmdlet 在故障转移阶段的工作原理的详细信息, 请参阅 NextHop 博客文章 "Lync Server 2013: 在[http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957)灾难恢复期间恢复响应组"。</span><span class="sxs-lookup"><span data-stu-id="49aa9-108">For details about how cmdlets work during the failover phase, see NextHop blog article "Lync Server 2013: Recovering Response Groups During Disaster Recovery" at [http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957).</span></span> <span data-ttu-id="49aa9-109">此博客文章还适用于 Lync Server 2013 的已发布版本。</span><span class="sxs-lookup"><span data-stu-id="49aa9-109">This blog article also applies to the released version of Lync Server 2013.</span></span>

<span data-ttu-id="49aa9-110">使用以下过程中的步骤为 Lync Server 响应组服务准备和执行灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="49aa9-110">Use the steps in the following procedure to prepare for and perform disaster recovery for Lync Server Response Group service.</span></span>

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a><span data-ttu-id="49aa9-111">故障转移和故障回复响应组</span><span class="sxs-lookup"><span data-stu-id="49aa9-111">To fail over and fail back Response Group</span></span>

1.  <span data-ttu-id="49aa9-112">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="49aa9-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="49aa9-113">定期执行备份。</span><span class="sxs-lookup"><span data-stu-id="49aa9-113">Routinely perform backups.</span></span> <span data-ttu-id="49aa9-114">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="49aa9-114">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="49aa9-115">例如：</span><span class="sxs-lookup"><span data-stu-id="49aa9-115">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  <span data-ttu-id="49aa9-116">在中断期间, 在故障转移到备份池后, 将响应组导入到备份池。</span><span class="sxs-lookup"><span data-stu-id="49aa9-116">During an outage, after failover to the backup pool, import the response groups to the backup pool.</span></span> <span data-ttu-id="49aa9-117">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="49aa9-117">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="49aa9-118">如果要将备份池中的应用程序级设置替换为主池中的设置, 请包括-ReplaceExistingSettings 参数。</span><span class="sxs-lookup"><span data-stu-id="49aa9-118">If you want to replace the application-level settings in the backup pool with the settings from the primary pool, include the –ReplaceExistingSettings parameter.</span></span> <span data-ttu-id="49aa9-119">例如：</span><span class="sxs-lookup"><span data-stu-id="49aa9-119">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="49aa9-120">如果不替换备份池中的设置, 并且无法恢复主池, 则主池设置将丢失。</span><span class="sxs-lookup"><span data-stu-id="49aa9-120">If you do not replace the settings in the backup pool and the primary pool can't be recovered, the primary pool settings will be lost.</span></span> <span data-ttu-id="49aa9-121">有关详细信息, 请参阅<A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">在 Lync Server 2013 中规划响应组灾难恢复</A>。</span><span class="sxs-lookup"><span data-stu-id="49aa9-121">For details, see <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Planning for response group disaster recovery in Lync Server 2013</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="49aa9-122">通过显示导入的响应组来验证导入是否成功。</span><span class="sxs-lookup"><span data-stu-id="49aa9-122">Verify that the import was successful by displaying the imported response groups.</span></span> <span data-ttu-id="49aa9-123">导入的响应组仍由主池拥有。</span><span class="sxs-lookup"><span data-stu-id="49aa9-123">The imported response groups are still owned by the primary pool.</span></span> <span data-ttu-id="49aa9-124">请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="49aa9-124">Do the following:</span></span>
    
      - <span data-ttu-id="49aa9-125">显示由主池拥有的备份池中的所有工作流, 并验证是否包含所有主池工作流。</span><span class="sxs-lookup"><span data-stu-id="49aa9-125">Display all the workflows in the backup pool that are owned by the primary pool, and verify that all the primary pool workflows are included.</span></span> <span data-ttu-id="49aa9-126">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="49aa9-126">At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="49aa9-127">例如：</span><span class="sxs-lookup"><span data-stu-id="49aa9-127">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - <span data-ttu-id="49aa9-128">显示由主池拥有的备份池中的所有队列, 并验证是否包含所有主池队列。</span><span class="sxs-lookup"><span data-stu-id="49aa9-128">Display all the queues in the backup pool that are owned by the primary pool, and verify that all the primary pool queues are included.</span></span> <span data-ttu-id="49aa9-129">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="49aa9-129">At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="49aa9-130">例如：</span><span class="sxs-lookup"><span data-stu-id="49aa9-130">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="49aa9-131">显示由主池拥有的备份池中的所有代理组, 并验证是否包含所有主池代理组。</span><span class="sxs-lookup"><span data-stu-id="49aa9-131">Display all the agent groups in the backup pool that are owned by the primary pool, and verify that all the primary pool agent groups are included.</span></span> <span data-ttu-id="49aa9-132">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="49aa9-132">At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="49aa9-133">例如：</span><span class="sxs-lookup"><span data-stu-id="49aa9-133">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="49aa9-134">显示由主池拥有的备份池中的所有工作时间, 并验证是否包括所有主池的工作时间。</span><span class="sxs-lookup"><span data-stu-id="49aa9-134">Display all the hours of business in the backup pool that are owned by the primary pool, and verify that all the primary pool hours of business are included.</span></span> <span data-ttu-id="49aa9-135">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="49aa9-135">At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="49aa9-136">例如：</span><span class="sxs-lookup"><span data-stu-id="49aa9-136">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="49aa9-137">显示由主池拥有的备份池中的所有假日集, 并验证是否包含所有主池假日集。</span><span class="sxs-lookup"><span data-stu-id="49aa9-137">Display all the holiday sets in the backup pool that are owned by the primary pool, and verify that all the primary pool holiday sets are included.</span></span> <span data-ttu-id="49aa9-138">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="49aa9-138">At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="49aa9-139">例如：</span><span class="sxs-lookup"><span data-stu-id="49aa9-139">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    <span data-ttu-id="49aa9-140">或者, 你可以显示备份池中的所有响应组, 包括由主池拥有的所有响应组以及由备份池拥有的所有响应组, 方法是使用– ShowAll 参数而不是-Owner 参数。</span><span class="sxs-lookup"><span data-stu-id="49aa9-140">Alternatively, you can display all the response groups in the backup pool, including the ones owned by the primary pool and the ones owned by the backup pool by using the –ShowAll parameter instead of the –Owner parameter.</span></span> <span data-ttu-id="49aa9-141">例如：</span><span class="sxs-lookup"><span data-stu-id="49aa9-141">For example:</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="49aa9-142">你必须使用– ShowAll 参数或– Owner 参数。</span><span class="sxs-lookup"><span data-stu-id="49aa9-142">You must use either the –ShowAll parameter or the –Owner parameter.</span></span> <span data-ttu-id="49aa9-143">如果不使用这两个参数中的任何一个, 则导入到备份池的响应组将不会在 cmdlet 返回的结果中列出。</span><span class="sxs-lookup"><span data-stu-id="49aa9-143">If you do not use either of these parameters, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>

    
    </div>

5.  <span data-ttu-id="49aa9-144">通过在导入的响应组中拨打电话并验证是否正确处理了呼叫, 验证导入是否成功。</span><span class="sxs-lookup"><span data-stu-id="49aa9-144">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="49aa9-145">请求代理是正式代理组的成员, 以登录到备份池中的代理组。</span><span class="sxs-lookup"><span data-stu-id="49aa9-145">Request agents who are members of formal agent groups to sign in to their agent groups in the backup pool.</span></span>

7.  <span data-ttu-id="49aa9-146">照常管理和修改导入的响应组。</span><span class="sxs-lookup"><span data-stu-id="49aa9-146">Manage and modify the imported response groups as usual.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="49aa9-147">当响应组位于备份池中时, 你需要使用 Lync Server Management Shell 管理它们。</span><span class="sxs-lookup"><span data-stu-id="49aa9-147">While the response groups are in the backup pool, you need to use Lync Server Management Shell to manage them.</span></span> <span data-ttu-id="49aa9-148">无法使用 Lync Server "控制面板" 管理导入到备份池中的响应组。</span><span class="sxs-lookup"><span data-stu-id="49aa9-148">You cannot use Lync Server Control Panel to manage the response groups that you imported to the backup pool.</span></span>

    
    </div>

8.  <span data-ttu-id="49aa9-149">在还原主池并完成故障回复后, 请导出已导入到备份池中的主要池响应组。</span><span class="sxs-lookup"><span data-stu-id="49aa9-149">After the primary pool is restored and failback is complete, export the primary pool response groups that were imported to the backup pool.</span></span> <span data-ttu-id="49aa9-150">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="49aa9-150">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  <span data-ttu-id="49aa9-151">将响应组导入回主池。</span><span class="sxs-lookup"><span data-stu-id="49aa9-151">Import the response groups back to the primary pool.</span></span> <span data-ttu-id="49aa9-152">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="49aa9-152">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    <span data-ttu-id="49aa9-153">例如：</span><span class="sxs-lookup"><span data-stu-id="49aa9-153">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="49aa9-154">如果你在恢复期间重新生成池, 而不是使用相同或不同的完全限定的域名 (FQDN), 则需要使用-OverwriteOwner 参数。</span><span class="sxs-lookup"><span data-stu-id="49aa9-154">If you rebuild a pool during recovery, whether with the same or a different fully qualified domain name (FQDN), you need to use the –OverwriteOwner parameter.</span></span> <span data-ttu-id="49aa9-155">根据经验法则, 将响应组导入到主池时, 始终可以使用– OverwriteOwner 参数。</span><span class="sxs-lookup"><span data-stu-id="49aa9-155">As a rule of thumb, you can always use the –OverwriteOwner parameter when you import response groups back to the primary pool.</span></span>

    
    </div>
    
    <span data-ttu-id="49aa9-156">如果你部署了新池 (具有相同或不同的 FQDN) 来替换主池, 并且希望使用新池的备份池中的应用程序级别设置, 请包含-ReplaceExistingSettings 参数。</span><span class="sxs-lookup"><span data-stu-id="49aa9-156">If you deployed a new pool (with the same or a different FQDN) to replace the primary pool, and you want to use the application-level settings from the backup pool for the new pool, include the –ReplaceExistingSettings parameter.</span></span> <span data-ttu-id="49aa9-157">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="49aa9-157">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    <span data-ttu-id="49aa9-158">例如：</span><span class="sxs-lookup"><span data-stu-id="49aa9-158">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="49aa9-159">如果您不想将新池的应用程序级设置和默认的音乐保留音频文件替换为具有备份池中的设置, 则新池将使用默认的应用程序级设置。</span><span class="sxs-lookup"><span data-stu-id="49aa9-159">If you don't want to replace the application-level settings and default music-on-hold audio file for the new pool with the settings from the backup pool, the new pool will use the default application-level settings.</span></span>

    
    </div>

10. <span data-ttu-id="49aa9-160">通过显示导入的响应组配置来验证是否已成功导入到主池。</span><span class="sxs-lookup"><span data-stu-id="49aa9-160">Verify that the import back to the primary pool was successful by displaying the imported response group configuration.</span></span> <span data-ttu-id="49aa9-161">请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="49aa9-161">Do the following:</span></span>
    
      - <span data-ttu-id="49aa9-162">显示主池中的所有工作流, 并验证是否包含所有导入的工作流。</span><span class="sxs-lookup"><span data-stu-id="49aa9-162">Display all the workflows in the primary pool, and verify that all the imported workflows are included.</span></span> <span data-ttu-id="49aa9-163">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="49aa9-163">At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="49aa9-164">例如：</span><span class="sxs-lookup"><span data-stu-id="49aa9-164">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="49aa9-165">显示主池中的所有队列, 并验证是否包含所有导入的队列。</span><span class="sxs-lookup"><span data-stu-id="49aa9-165">Display all the queues in the primary pool, and verify that all the imported queues are included.</span></span> <span data-ttu-id="49aa9-166">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="49aa9-166">At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="49aa9-167">例如：</span><span class="sxs-lookup"><span data-stu-id="49aa9-167">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="49aa9-168">显示主池中的所有代理组, 并验证是否包含所有导入的代理组。</span><span class="sxs-lookup"><span data-stu-id="49aa9-168">Display all the agent groups in the primary pool, and verify that all the imported agent groups are included.</span></span> <span data-ttu-id="49aa9-169">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="49aa9-169">At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="49aa9-170">例如：</span><span class="sxs-lookup"><span data-stu-id="49aa9-170">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="49aa9-171">显示主池中的所有工作时间, 并验证是否包括所有导入的公司工时。</span><span class="sxs-lookup"><span data-stu-id="49aa9-171">Display all the hours of business in the primary pool, and verify that all the imported hours of business are included.</span></span> <span data-ttu-id="49aa9-172">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="49aa9-172">At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="49aa9-173">例如：</span><span class="sxs-lookup"><span data-stu-id="49aa9-173">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="49aa9-174">显示主池中的所有假日集, 并验证是否包含所有导入的假日集。</span><span class="sxs-lookup"><span data-stu-id="49aa9-174">Display all the holiday sets in the primary pool, and verify that all the imported holiday sets are included.</span></span> <span data-ttu-id="49aa9-175">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="49aa9-175">At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="49aa9-176">例如：</span><span class="sxs-lookup"><span data-stu-id="49aa9-176">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. <span data-ttu-id="49aa9-177">通过在导入的响应组中拨打电话并验证是否正确处理了呼叫, 验证导入是否成功。</span><span class="sxs-lookup"><span data-stu-id="49aa9-177">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

12. <span data-ttu-id="49aa9-178">(可选) 从备份池中删除主池拥有的响应组。</span><span class="sxs-lookup"><span data-stu-id="49aa9-178">Optionally, remove the response groups owned by the primary pool from the backup pool.</span></span> <span data-ttu-id="49aa9-179">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="49aa9-179">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    <span data-ttu-id="49aa9-180">例如：</span><span class="sxs-lookup"><span data-stu-id="49aa9-180">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="49aa9-181">此步骤将使用导出的配置创建一个新文件, 然后将其从备份池中删除。</span><span class="sxs-lookup"><span data-stu-id="49aa9-181">This step creates a new file with the exported configuration, and then removes it from the backup pool.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

