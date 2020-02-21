---
title: Lync Server 2013 响应组灾难恢复过程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group disaster recovery procedures
ms:assetid: b49577b7-0ca3-4f20-b614-f3a2a0046b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205186(v=OCS.15)
ms:contentKeyID: 48185171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 254f9e95edfb445d996948a17064ae460dbdb7d8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214868"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a><span data-ttu-id="c04ee-102">Lync Server 2013 中的响应组灾难恢复过程</span><span class="sxs-lookup"><span data-stu-id="c04ee-102">Response group disaster recovery procedures in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c04ee-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c04ee-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c04ee-104">在灾难恢复的故障转移阶段内，响应组位于多个池中：主池（无法使用）和备份池。</span><span class="sxs-lookup"><span data-stu-id="c04ee-104">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool.</span></span> <span data-ttu-id="c04ee-105">这两个池中的响应组具有相同的名称和相同的所有者（主池），但是它们具有不同的父项。</span><span class="sxs-lookup"><span data-stu-id="c04ee-105">The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span> <span data-ttu-id="c04ee-106">在这段时间内，响应组 cmdlet 的工作方式略有不同。</span><span class="sxs-lookup"><span data-stu-id="c04ee-106">During this time, Response Group cmdlets work a little differently.</span></span> <span data-ttu-id="c04ee-107">请务必使用以下过程中指定的参数。</span><span class="sxs-lookup"><span data-stu-id="c04ee-107">Be sure to use parameters as specified in the following procedure.</span></span> <span data-ttu-id="c04ee-108">有关在故障转移阶段中 cmdlet 的工作原理的详细信息，请参阅 NextHop 博客文章 "Lync Server 2013：在灾难恢复过程[https://go.microsoft.com/fwlink/p/?LinkId=263957](https://go.microsoft.com/fwlink/p/?linkid=263957)中恢复响应组"，时间为。</span><span class="sxs-lookup"><span data-stu-id="c04ee-108">For details about how cmdlets work during the failover phase, see NextHop blog article "Lync Server 2013: Recovering Response Groups During Disaster Recovery" at [https://go.microsoft.com/fwlink/p/?LinkId=263957](https://go.microsoft.com/fwlink/p/?linkid=263957).</span></span> <span data-ttu-id="c04ee-109">此博客文章也适用于 Lync Server 2013 的已发布版本。</span><span class="sxs-lookup"><span data-stu-id="c04ee-109">This blog article also applies to the released version of Lync Server 2013.</span></span>

<span data-ttu-id="c04ee-110">使用以下过程中的步骤来准备和执行 Lync Server 响应组服务的灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="c04ee-110">Use the steps in the following procedure to prepare for and perform disaster recovery for Lync Server Response Group service.</span></span>

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a><span data-ttu-id="c04ee-111">对响应组进行故障转移和故障回复</span><span class="sxs-lookup"><span data-stu-id="c04ee-111">To fail over and fail back Response Group</span></span>

1.  <span data-ttu-id="c04ee-112">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c04ee-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c04ee-p102">定期执行备份。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="c04ee-p102">Routinely perform backups. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="c04ee-115">例如：</span><span class="sxs-lookup"><span data-stu-id="c04ee-115">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  <span data-ttu-id="c04ee-p103">在中断期间，在故障转移到备份池后，将响应组导入备份池。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="c04ee-p103">During an outage, after failover to the backup pool, import the response groups to the backup pool. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="c04ee-p104">如果您想要将备份池中的应用程序级别设置替换为主池中的设置，请包括 –ReplaceExistingSettings 参数。例如：</span><span class="sxs-lookup"><span data-stu-id="c04ee-p104">If you want to replace the application-level settings in the backup pool with the settings from the primary pool, include the –ReplaceExistingSettings parameter. For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="c04ee-120">如果您未替换备份池中的设置，并且无法恢复主池，则主池设置将会丢失。</span><span class="sxs-lookup"><span data-stu-id="c04ee-120">If you do not replace the settings in the backup pool and the primary pool can't be recovered, the primary pool settings will be lost.</span></span> <span data-ttu-id="c04ee-121">有关详细信息，请参阅<A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">在 Lync Server 2013 中规划响应组灾难恢复</A>。</span><span class="sxs-lookup"><span data-stu-id="c04ee-121">For details, see <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Planning for response group disaster recovery in Lync Server 2013</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="c04ee-p106">通过显示导入的响应组来验证导入是否成功。导入的响应组仍归主池所有。请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c04ee-p106">Verify that the import was successful by displaying the imported response groups. The imported response groups are still owned by the primary pool. Do the following:</span></span>
    
      - <span data-ttu-id="c04ee-p107">显示备份池中归主池所有的全部工作流，并验证是否包含所有主池工作流。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="c04ee-p107">Display all the workflows in the backup pool that are owned by the primary pool, and verify that all the primary pool workflows are included. At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="c04ee-127">例如：</span><span class="sxs-lookup"><span data-stu-id="c04ee-127">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - <span data-ttu-id="c04ee-p108">显示备份池中归主池所有的全部队列，并验证是否包含所有主池队列。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="c04ee-p108">Display all the queues in the backup pool that are owned by the primary pool, and verify that all the primary pool queues are included. At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="c04ee-130">例如：</span><span class="sxs-lookup"><span data-stu-id="c04ee-130">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="c04ee-p109">显示备份池中归主池所有的全部代理组，并验证是否包含所有主池代理组。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="c04ee-p109">Display all the agent groups in the backup pool that are owned by the primary pool, and verify that all the primary pool agent groups are included. At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="c04ee-133">例如：</span><span class="sxs-lookup"><span data-stu-id="c04ee-133">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="c04ee-p110">显示备份池中归主池所有的全部工作时间，并验证是否包含所有主池工作时间。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="c04ee-p110">Display all the hours of business in the backup pool that are owned by the primary pool, and verify that all the primary pool hours of business are included. At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="c04ee-136">例如：</span><span class="sxs-lookup"><span data-stu-id="c04ee-136">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="c04ee-p111">显示备份池中归主池所有的全部假日集，并验证是否包含所有主池假日集。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="c04ee-p111">Display all the holiday sets in the backup pool that are owned by the primary pool, and verify that all the primary pool holiday sets are included. At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="c04ee-139">例如：</span><span class="sxs-lookup"><span data-stu-id="c04ee-139">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    <span data-ttu-id="c04ee-p112">或者，您可以使用 –ShowAll 参数而不是 –Owner 参数来显示备份池中的所有响应组，包括主池所拥有的响应组和备份池所拥有的响应组。例如：</span><span class="sxs-lookup"><span data-stu-id="c04ee-p112">Alternatively, you can display all the response groups in the backup pool, including the ones owned by the primary pool and the ones owned by the backup pool by using the –ShowAll parameter instead of the –Owner parameter. For example:</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c04ee-p113">您必须使用 –ShowAll 参数或 –Owner 参数。如果没有使用其中任一参数，则导入到备份池的响应组不会在 cmdlet 返回的结果中列出。</span><span class="sxs-lookup"><span data-stu-id="c04ee-p113">You must use either the –ShowAll parameter or the –Owner parameter. If you do not use either of these parameters, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>

    
    </div>

5.  <span data-ttu-id="c04ee-144">通过呼叫导入的响应组并验证呼叫是否正确处理来验证导入是否成功。</span><span class="sxs-lookup"><span data-stu-id="c04ee-144">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="c04ee-145">请求属于正式代理组的成员的代理登录到其在备份池中的代理组。</span><span class="sxs-lookup"><span data-stu-id="c04ee-145">Request agents who are members of formal agent groups to sign in to their agent groups in the backup pool.</span></span>

7.  <span data-ttu-id="c04ee-146">像往常一样管理和修改导入的响应组。</span><span class="sxs-lookup"><span data-stu-id="c04ee-146">Manage and modify the imported response groups as usual.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c04ee-147">当响应组位于备份池中时，您需要使用 Lync Server 命令行管理程序来管理它们。</span><span class="sxs-lookup"><span data-stu-id="c04ee-147">While the response groups are in the backup pool, you need to use Lync Server Management Shell to manage them.</span></span> <span data-ttu-id="c04ee-148">您不能使用 Lync Server 控制面板管理导入到备份池中的响应组。</span><span class="sxs-lookup"><span data-stu-id="c04ee-148">You cannot use Lync Server Control Panel to manage the response groups that you imported to the backup pool.</span></span>

    
    </div>

8.  <span data-ttu-id="c04ee-p115">在恢复主池并完成故障回复之后，导出已导入备份池的主池响应组。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="c04ee-p115">After the primary pool is restored and failback is complete, export the primary pool response groups that were imported to the backup pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  <span data-ttu-id="c04ee-p116">将响应组重新导入到主池。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="c04ee-p116">Import the response groups back to the primary pool. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    <span data-ttu-id="c04ee-153">例如：</span><span class="sxs-lookup"><span data-stu-id="c04ee-153">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c04ee-p117">如果在恢复期间重建池，则无论完全限定域名 (FQDN) 相同还是不同，您都需要使用 –OverwriteOwner 参数。根据经验法则，在将响应组导回到主池时，您可以始终使用 –OverwriteOwner 参数。</span><span class="sxs-lookup"><span data-stu-id="c04ee-p117">If you rebuild a pool during recovery, whether with the same or a different fully qualified domain name (FQDN), you need to use the –OverwriteOwner parameter. As a rule of thumb, you can always use the –OverwriteOwner parameter when you import response groups back to the primary pool.</span></span>

    
    </div>
    
    <span data-ttu-id="c04ee-p118">如果您部署一个新池（具有相同或不同的 FQDN）来替换主池，并且想要针对新池使用备份池中的应用程序级别设置，请包括 –ReplaceExistingSettings 参数。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="c04ee-p118">If you deployed a new pool (with the same or a different FQDN) to replace the primary pool, and you want to use the application-level settings from the backup pool for the new pool, include the –ReplaceExistingSettings parameter. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    <span data-ttu-id="c04ee-158">例如：</span><span class="sxs-lookup"><span data-stu-id="c04ee-158">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c04ee-159">如果您不想将新池的应用程序级别设置和默认保持音乐音频文件替换为备份池中的设置，则新池将使用默认应用程序级别设置。</span><span class="sxs-lookup"><span data-stu-id="c04ee-159">If you don't want to replace the application-level settings and default music-on-hold audio file for the new pool with the settings from the backup pool, the new pool will use the default application-level settings.</span></span>

    
    </div>

10. <span data-ttu-id="c04ee-p119">通过显示导入的响应组配置来验证导回至主池是否成功。请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c04ee-p119">Verify that the import back to the primary pool was successful by displaying the imported response group configuration. Do the following:</span></span>
    
      - <span data-ttu-id="c04ee-p120">显示主池中的所有工作流，并验证是否包含所有导入的工作流。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="c04ee-p120">Display all the workflows in the primary pool, and verify that all the imported workflows are included. At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="c04ee-164">例如：</span><span class="sxs-lookup"><span data-stu-id="c04ee-164">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="c04ee-p121">显示主池中的所有队列，并验证是否包含所有导入的队列。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="c04ee-p121">Display all the queues in the primary pool, and verify that all the imported queues are included. At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="c04ee-167">例如：</span><span class="sxs-lookup"><span data-stu-id="c04ee-167">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="c04ee-p122">显示主池中的所有代理组，并验证是否包含所有导入的代理组。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="c04ee-p122">Display all the agent groups in the primary pool, and verify that all the imported agent groups are included. At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="c04ee-170">例如：</span><span class="sxs-lookup"><span data-stu-id="c04ee-170">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="c04ee-p123">显示主池中的所有工作时间，并验证是否包含所有导入的工作时间。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="c04ee-p123">Display all the hours of business in the primary pool, and verify that all the imported hours of business are included. At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="c04ee-173">例如：</span><span class="sxs-lookup"><span data-stu-id="c04ee-173">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="c04ee-p124">显示主池中的所有假日集，并验证是否包含所有导入的假日集。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="c04ee-p124">Display all the holiday sets in the primary pool, and verify that all the imported holiday sets are included. At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="c04ee-176">例如：</span><span class="sxs-lookup"><span data-stu-id="c04ee-176">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. <span data-ttu-id="c04ee-177">通过呼叫导入的响应组并验证呼叫是否正确处理来验证导入是否成功。</span><span class="sxs-lookup"><span data-stu-id="c04ee-177">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

12. <span data-ttu-id="c04ee-p125">或者，从备份池中删除主池拥有的响应组。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="c04ee-p125">Optionally, remove the response groups owned by the primary pool from the backup pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    <span data-ttu-id="c04ee-180">例如：</span><span class="sxs-lookup"><span data-stu-id="c04ee-180">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c04ee-181">此步骤将使用导出的配置创建新文件，然后将该文件从备份池中删除。</span><span class="sxs-lookup"><span data-stu-id="c04ee-181">This step creates a new file with the exported configuration, and then removes it from the backup pool.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

