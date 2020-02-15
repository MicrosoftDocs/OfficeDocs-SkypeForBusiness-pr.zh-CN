---
title: Lync Server 2013：规划响应组灾难恢复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for response group disaster recovery
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204699(v=OCS.15)
ms:contentKeyID: 48183482
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 049e07e72efba508add2135c6b77aebed2c38954
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050634"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="3a093-102">在 Lync Server 2013 中规划响应组灾难恢复</span><span class="sxs-lookup"><span data-stu-id="3a093-102">Planning for response group disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a093-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3a093-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3a093-104">本节介绍准备对响应组进行灾难恢复的一些方法，并提供灾难恢复过程的概述。</span><span class="sxs-lookup"><span data-stu-id="3a093-104">This section describes some ways to prepare response groups for disaster recovery and provides an overview of the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a><span data-ttu-id="3a093-105">为响应组灾难恢复做准备</span><span class="sxs-lookup"><span data-stu-id="3a093-105">Preparing for Response Group Disaster Recovery</span></span>

<span data-ttu-id="3a093-106">在准备和执行灾难恢复过程时，请谨记以下做法。</span><span class="sxs-lookup"><span data-stu-id="3a093-106">Keep the following in mind when you prepare for and carry out disaster recovery procedures.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3a093-107">在共存环境中，本文档中所述的灾难恢复过程仅支持 Lync Server 2013 响应组。</span><span class="sxs-lookup"><span data-stu-id="3a093-107">In a coexistence environment, only the Lync Server 2013 response groups are supported for the disaster recovery procedures described in this document.</span></span>



</div>

  - <span data-ttu-id="3a093-108">在进行容量规划时，应制定灾难恢复计划。</span><span class="sxs-lookup"><span data-stu-id="3a093-108">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="3a093-109">对于灾难恢复容量，配对池中的每个池应能够处理两个池中所有响应组的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="3a093-109">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of all the response groups in both pools.</span></span> <span data-ttu-id="3a093-110">有关响应组容量规划的详细信息，请参阅[Lync Server 2013 中的容量规划（针对响应组](lync-server-2013-capacity-planning-for-response-group.md)）。</span><span class="sxs-lookup"><span data-stu-id="3a093-110">For details about Response Group capacity planning, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span></span>

  - <span data-ttu-id="3a093-111">使用本文档中所述的 export 过程，对部署了响应组应用程序的所有前端池中的所有响应组配置执行常规备份副本。</span><span class="sxs-lookup"><span data-stu-id="3a093-111">Take regular backup copies of all the response group configurations in all the Front End pools where you deployed the Response Group application by using the export procedure described in this document.</span></span> <span data-ttu-id="3a093-112">有关详细信息，请参阅[Lync Server 2013 中的响应组灾难恢复过程](lync-server-2013-response-group-disaster-recovery-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="3a093-112">For details, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span> <span data-ttu-id="3a093-113">请将备份副本保存到安全的位置。</span><span class="sxs-lookup"><span data-stu-id="3a093-113">Keep the backup copies in a safe location.</span></span>

  - <span data-ttu-id="3a093-114">为响应组应用程序保留您使用的所有原始音频文件的单独备份副本，包括任何录制和包含音乐的文件。</span><span class="sxs-lookup"><span data-stu-id="3a093-114">Keep a separate backup copy of all the original audio files you used for the Response Group application, including any recordings and music-on-hold files.</span></span> <span data-ttu-id="3a093-115">请将备份文件保存到安全的位置。</span><span class="sxs-lookup"><span data-stu-id="3a093-115">Keep the backup files in a safe location.</span></span>

  - <span data-ttu-id="3a093-116">对于 Lync Server 2013 灾难恢复，所有响应组设置必须在您的部署中具有唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="3a093-116">For Lync Server 2013 disaster recovery, all Response Group settings must have unique names across your deployment.</span></span> <span data-ttu-id="3a093-117">此要求适用于工作流、队列、代理组、假日集和工作时间。</span><span class="sxs-lookup"><span data-stu-id="3a093-117">This requirement applies to workflows, queues, agent groups, holiday sets, and hours of business.</span></span> <span data-ttu-id="3a093-118">在主池和备份池仍处于活动状态时，并且在您需要启动任何故障转移过程之前，您应该确认是否符合此要求。</span><span class="sxs-lookup"><span data-stu-id="3a093-118">You should verify that this requirement is met when the primary and backup pools are still active, and before you need to initiate any failover procedure.</span></span> <span data-ttu-id="3a093-119">如果在将响应组数据导入备份池时遇到名称冲突，导入将失败。</span><span class="sxs-lookup"><span data-stu-id="3a093-119">If you encounter name conflicts while importing response group data to the backup pool, the import fails.</span></span> <span data-ttu-id="3a093-120">若要完成导入和故障转移过程，您需要解决名称冲突，具体方法是在备份池中重命名响应组对象，或将 **Import-CsRgsConfiguration** cmdlet 与 –ResolveNameConflicts 参数结合使用，以通过向响应组对象附加唯一的标识号来自动解决冲突。</span><span class="sxs-lookup"><span data-stu-id="3a093-120">To complete the import and failover procedure, you need to resolve the name conflicts by renaming the response group object in the backup pool or by using the **Import-CsRgsConfiguration** cmdlet with the –ResolveNameConflicts parameter to automatically resolve the conflict by appending a unique identifying number to the response group object.</span></span>

  - <span data-ttu-id="3a093-p105">通常，建议您执行日常备份，但如果您要进行大量更改，那么您可能希望安排更为频繁的备份。您在发生灾难期间可能丢失的信息量取决于您的备份频率，以及更改频率和更改量。</span><span class="sxs-lookup"><span data-stu-id="3a093-p105">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups. The amount of information you can lose in the event of a disaster depends on the frequency of your backups, as well as the frequency and volume of changes.</span></span>

  - <span data-ttu-id="3a093-123">可以在发生灾难或执行故障转移操作之前，先将响应组导入备份池。</span><span class="sxs-lookup"><span data-stu-id="3a093-123">It is possible to import response groups to a backup pool before a disaster or failover operation occurs.</span></span> <span data-ttu-id="3a093-124">提前导入响应组会减少停机时间，因为一旦将呼叫路由到备份池，就可以在备份池中还原 Lync Server 响应组服务。</span><span class="sxs-lookup"><span data-stu-id="3a093-124">Importing response groups in advance reduces downtime, because the Lync Server Response Group service can be restored in the backup pool as soon as calls are routed to the backup pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3a093-125">在故障转移完成之前，响应组应用程序无法访问驻留在非活动池中的任何代理。</span><span class="sxs-lookup"><span data-stu-id="3a093-125">The Response Group application cannot reach any agents homed in an inactive pool until failover is complete.</span></span> <span data-ttu-id="3a093-126">在这段时间内，响应组应用程序将像这些代理不可用那样处理调用。</span><span class="sxs-lookup"><span data-stu-id="3a093-126">During this time, the Response Group application processes calls as if those agents are unavailable.</span></span>

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a><span data-ttu-id="3a093-127">响应组灾难恢复过程</span><span class="sxs-lookup"><span data-stu-id="3a093-127">Response Group Disaster Recovery Process</span></span>

<span data-ttu-id="3a093-128">发生灾难时，可以使用以下任一恢复方法恢复响应组：</span><span class="sxs-lookup"><span data-stu-id="3a093-128">In the event of a disaster, you can recover response groups by using either of the following recovery approaches:</span></span>

  - <span data-ttu-id="3a093-129">故障转移至备份池，然后再故障转移回原始池。</span><span class="sxs-lookup"><span data-stu-id="3a093-129">Fail over to a backup pool and then fail back to the original pool.</span></span>

  - <span data-ttu-id="3a093-130">故障转移至备份池，用不同的完全限定域名 (FQDN) 创建新池，然后将响应组导入新池。</span><span class="sxs-lookup"><span data-stu-id="3a093-130">Fail over to a backup pool, create a new pool with a different fully qualified domain name (FQDN), and then import the response groups to the new pool.</span></span>

<span data-ttu-id="3a093-p108">在灾难恢复的故障转移阶段，响应组驻留在多个池中：在主池（不可用）和备份池中。响应组在两个池中具有相同的名称和相同的所有者（主池），但具有不同的父级。</span><span class="sxs-lookup"><span data-stu-id="3a093-p108">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool. The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span>

<span data-ttu-id="3a093-133">在通过创建具有不同 FQDN 的新池来恢复时，需要在导入响应组时将该新池指定为响应组的所有者。</span><span class="sxs-lookup"><span data-stu-id="3a093-133">When you recover by creating a new pool with a different FQDN, you need to assign the new pool as the owner of the response groups when you import them.</span></span> <span data-ttu-id="3a093-134">除非或直到您结合使用 –OverwriteOwner 参数和 **Import-CsRgsConfiguration** cmdlet 来明确重新分配所有权，响应组的所有权将一直属于原始池。</span><span class="sxs-lookup"><span data-stu-id="3a093-134">Ownership of response groups remains with the original pool unless or until you explicitly reassign ownership by using the –OverwriteOwner parameter with the **Import-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3a093-135">如果在恢复期间重建池（即响应组数据库为空），则还需要使用– OverwriteOwner 参数，而不管您是否使用相同的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3a093-135">You also need to use the –OverwriteOwner parameter if you rebuilt the pool during the recovery (that is, the Response Group database is empty), whether or not you use the same FQDN.</span></span> <span data-ttu-id="3a093-136">如果不重建池，则无需使用 –OverwriteOwner 参数，但在将响应组导入回主池时，允许使用此参数。</span><span class="sxs-lookup"><span data-stu-id="3a093-136">You do not need to use the –OverwriteOwner parameter if you did not rebuild the pool, but it is permissible to use this parameter whenever you import response groups back to the primary pool.</span></span>



</div>

<span data-ttu-id="3a093-137">您只能为每个池定义一组应用程序级响应组配置设置。</span><span class="sxs-lookup"><span data-stu-id="3a093-137">You can define only one set of application-level Response Group configuration settings per pool.</span></span> <span data-ttu-id="3a093-138">这些设置包括默认的保持音乐配置、默认的保持音乐音频文件、代理回响宽限期和调用上下文配置。</span><span class="sxs-lookup"><span data-stu-id="3a093-138">These settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="3a093-139">若要查看这些配置设置，请运行 **Get-CsRgsConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3a093-139">To view these configuration settings, run the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="3a093-140">有关**CsRgsConfiguration** cmdlet 的详细信息，请参阅[CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="3a093-140">For details about the **Get-CsRgsConfiguration** cmdlet, see [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span></span>

<span data-ttu-id="3a093-141">通过将 **Import-CsRgsConfiguration** cmdlet 与 –ReplaceExistingSettings 参数结合使用可将这些应用程序级别的设置从一个池传送至其他池，但这样做会覆盖目标池中的设置。</span><span class="sxs-lookup"><span data-stu-id="3a093-141">You can transfer these application-level settings from one pool to another by using the **Import-CsRgsConfiguration** cmdlet with the –ReplaceExistingSettings parameter, but doing so overrides the settings in the destination pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3a093-p112">有关向其他池传送设置的这一约束仅适用于应用程序级别设置和默认的保持音乐音频文件。它不适用于代理组、队列、工作流、工作时间和假日集。</span><span class="sxs-lookup"><span data-stu-id="3a093-p112">This constraint about transferring settings to another pool is true only for the application-level settings and the default music-on-hold audio file. It does not apply to agent groups, queues, workflows, business hours, and holiday sets.</span></span>



</div>

<span data-ttu-id="3a093-p113">如果不想在灾难期间替换备份池中的应用程序级别设置并且主池无法恢复，则主池中的应用程序级别设置将丢失。如果在恢复期间需要创建新池来替换主池（具有同一 FQDN 或不同 FQDN），则无法恢复原始的应用程序级别设置。在此情况下，需要用这些设置配置新池并包括保持音乐音频文件。</span><span class="sxs-lookup"><span data-stu-id="3a093-p113">If you don't want to replace the application-level settings in the backup pool during a disaster and the primary pool can't be recovered, the application-level settings from the primary pool will be lost. If you need to create a new pool to replace the primary pool during recovery, either with the same FQDN or with a different FQDN, you can't recover the original application-level settings. In this case, you need to configure the new pool with these settings and include the music-on-hold audio file.</span></span>

<span data-ttu-id="3a093-147">如果决定在灾难期间使用 **Import-CsRgsConfiguration** cmdlet 来将应用程序级别的设置从主池传送至备份池，然后在恢复期间便可采用从主池向备份池传送设置的同样方式将设置从备份池传送至新池。</span><span class="sxs-lookup"><span data-stu-id="3a093-147">If you decide to use the **Import-CsRgsConfiguration** cmdlet to transfer application-level settings from the primary pool to the backup pool during a disaster, you can then transfer the settings from the backup pool to the new pool during recovery in the same way that you transferred them from the primary pool to the backup pool.</span></span>

<span data-ttu-id="3a093-148">下表是恢复响应组时所涉及步骤的概述。</span><span class="sxs-lookup"><span data-stu-id="3a093-148">The following table is an overview of the steps involved in recovering response groups.</span></span>

<span data-ttu-id="3a093-149">有关执行这些步骤的详细信息，请参阅[Lync Server 2013 中的响应组灾难恢复过程](lync-server-2013-response-group-disaster-recovery-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="3a093-149">For details about performing these steps, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span>

### <a name="response-group-disaster-recovery-steps"></a><span data-ttu-id="3a093-150">响应组灾难恢复步骤</span><span class="sxs-lookup"><span data-stu-id="3a093-150">Response Group Disaster Recovery Steps</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3a093-151">阶段</span><span class="sxs-lookup"><span data-stu-id="3a093-151">Phase</span></span></th>
<th><span data-ttu-id="3a093-152">步骤</span><span class="sxs-lookup"><span data-stu-id="3a093-152">Steps</span></span></th>
<th><span data-ttu-id="3a093-153">所需的组和角色</span><span class="sxs-lookup"><span data-stu-id="3a093-153">Required groups and roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3a093-154">中断前</span><span class="sxs-lookup"><span data-stu-id="3a093-154">Before outage</span></span></p></td>
<td><p><span data-ttu-id="3a093-155">定期运行<strong>CsRgsConfiguration</strong> cmdlet，以在部署响应组应用程序的所有前端池中创建所有响应组配置的备份。</span><span class="sxs-lookup"><span data-stu-id="3a093-155">On a routine basis, run the <strong>Export-CsRgsConfiguration</strong> cmdlet to create backups of all Response Group configurations in all Front End pools where Response Group application is deployed.</span></span></p></td>
<td><p><span data-ttu-id="3a093-156">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3a093-156">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="3a093-157">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="3a093-157">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a093-158">中断期间</span><span class="sxs-lookup"><span data-stu-id="3a093-158">During outage</span></span></p></td>
<td><p><span data-ttu-id="3a093-159">运行<strong>CsRgsConfiguration</strong> cmdlet，将备份的 Lync Server 响应组服务配置从主池导入到备份池。</span><span class="sxs-lookup"><span data-stu-id="3a093-159">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the backed up Lync Server Response Group service configuration from the primary pool to the backup pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="3a093-160">如果要将备份池中的应用程序级响应组设置替换为主池的设置，请使用– ReplaceExistingSettings 参数。</span><span class="sxs-lookup"><span data-stu-id="3a093-160">Use the –ReplaceExistingSettings parameter if you want to replace application-level Response Group settings in the backup pool with the settings from the primary pool.</span></span> <span data-ttu-id="3a093-161">如果不从主池向备份池传送应用程序级别的设置，则无法恢复主池，您将丢失主池中的设置。</span><span class="sxs-lookup"><span data-stu-id="3a093-161">If you do not transfer the application-level settings from the primary pool to the backup pool, and the primary pool can't be recovered, you will lose the settings from the primary pool.</span></span>


</div></td>
<td><p><span data-ttu-id="3a093-162">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3a093-162">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="3a093-163">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="3a093-163">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a093-164">导入后</span><span class="sxs-lookup"><span data-stu-id="3a093-164">After importing</span></span></p></td>
<td><p><span data-ttu-id="3a093-165">使用– ShowAll 参数（显示所有响应组）或– Owner 参数（仅显示导入的响应组）运行响应组 cmdlet，以验证是否已将所有响应组配置导入备份池。</span><span class="sxs-lookup"><span data-stu-id="3a093-165">Run Response Group cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were imported to the backup pool.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="3a093-166">如果不使用 –ShowAll 参数或 –Owner 参数，导入备份池的响应组将不会列在 cmdlet 返回的结果中。</span><span class="sxs-lookup"><span data-stu-id="3a093-166">If you do not use either the –ShowAll parameter or the –Owner parameter, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>


</div>
<p><span data-ttu-id="3a093-167">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3a093-167">Run the following cmdlets:</span></span></p>
<ul>
<li><p><span data-ttu-id="3a093-168"><strong>CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="3a093-168"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="3a093-169"><strong>CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="3a093-169"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="3a093-170"><strong>CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="3a093-170"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="3a093-171"><strong>CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="3a093-171"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="3a093-172"><strong>CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="3a093-172"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3a093-173">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3a093-173">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="3a093-174">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="3a093-174">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a093-175">故障转移后</span><span class="sxs-lookup"><span data-stu-id="3a093-175">After failover</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3a093-176">对已导入备份池的响应组执行测试呼叫，并确认能够正确处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="3a093-176">Place a test call to a response group that was imported to the backup pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="3a093-177">所有正式代理必须重新登录到它们在备份池中的正式组。</span><span class="sxs-lookup"><span data-stu-id="3a093-177">All formal agents must sign in again to their formal groups on backup pool.</span></span></p></li>
<li><p><span data-ttu-id="3a093-178">管理配置更改：</span><span class="sxs-lookup"><span data-stu-id="3a093-178">Manage configuration changes:</span></span></p>
<p><span data-ttu-id="3a093-179">备份池中的响应组（无论是导入备份池中的还是由备份池所拥有）在出现故障时均可正常修改。</span><span class="sxs-lookup"><span data-stu-id="3a093-179">Response groups in the backup pool, whether imported to the backup pool or owned by the backup pool, can be modified as usual during the outage.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="3a093-180">必须使用 Lync Server 命令行管理程序来管理已导入到备份池中的响应组。</span><span class="sxs-lookup"><span data-stu-id="3a093-180">You must use Lync Server Management Shell to manage the response groups that you imported to the backup pool.</span></span> <span data-ttu-id="3a093-181">当这些响应组位于备份池中时，不能使用 Lync Server 控制面板管理这些响应组。</span><span class="sxs-lookup"><span data-stu-id="3a093-181">You cannot use Lync Server Control Panel to manage these response groups while they are in the backup pool.</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="3a093-182">不适用</span><span class="sxs-lookup"><span data-stu-id="3a093-182">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a093-183">恢复后，故障回复前</span><span class="sxs-lookup"><span data-stu-id="3a093-183">After recovery, before failback</span></span></p></td>
<td><p><span data-ttu-id="3a093-184">运行 <strong>Export-CsRgsConfiguration</strong> cmdlet，将 -Source 参数指定为备份池，而将 –Owner 参数指定为主池，以便从备份池导出由主池所拥有的响应组。</span><span class="sxs-lookup"><span data-stu-id="3a093-184">Run the <strong>Export-CsRgsConfiguration</strong> cmdlet specifying the -Source parameter as the backup pool and the –Owner parameter as the primary pool to export the response groups owned by the primary pool from the backup pool.</span></span></p></td>
<td><p><span data-ttu-id="3a093-185">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3a093-185">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="3a093-186">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="3a093-186">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a093-187">故障回复后</span><span class="sxs-lookup"><span data-stu-id="3a093-187">After failback</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3a093-188">运行 <strong>Import-CsRgsConfiguration</strong> cmdlet 以将响应组导入回主池。</span><span class="sxs-lookup"><span data-stu-id="3a093-188">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the response groups back to the primary pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="3a093-p116">如果无法恢复主池并且您要部署新池来替换它，可使用 –ReplaceExistingSettings 参数将应用程序级别的设置从备份池传送到新池。如果不从备份池传送设置，新池将使用默认设置。</span><span class="sxs-lookup"><span data-stu-id="3a093-p116">If the primary pool can't be recovered and you deploy a new pool to replace it, use the –ReplaceExistingSettings parameter to transfer the application-level settings from the backup pool to the new pool. If you do not transfer the settings from the backup pool, the new pool will use the default settings.</span></span>


</div></li>
<li><p><span data-ttu-id="3a093-191">带 –ShowAll 参数（显示所有响应组）或 –Owner 参数（只显示已导入的响应组）运行以下 cmdlet，以确认所有响应组配置均已成功导入回主池：</span><span class="sxs-lookup"><span data-stu-id="3a093-191">Run the following cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were successfully imported back to the primary pool:</span></span></p>
<ul>
<li><p><span data-ttu-id="3a093-192"><strong>CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="3a093-192"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="3a093-193"><strong>CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="3a093-193"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="3a093-194"><strong>CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="3a093-194"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="3a093-195"><strong>CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="3a093-195"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="3a093-196"><strong>CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="3a093-196"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="3a093-197">对导入回主池的响应组执行测试呼叫，并确认能够正确处理该呼叫。</span><span class="sxs-lookup"><span data-stu-id="3a093-197">Place a test call to a response group that was imported back to the primary pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="3a093-198">或者，使用 –RemoveExportedConfiguration 参数对备份池运行 <strong>Export-CsRgsConfiguration</strong> cmdlet 以从备份池中删除主池所拥有的响应组。</span><span class="sxs-lookup"><span data-stu-id="3a093-198">Optionally, run the <strong>Export-CsRgsConfiguration</strong> cmdlet on the backup pool with the –RemoveExportedConfiguration parameter to remove the response groups owned by the primary pool from the backup pool.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3a093-199">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3a093-199">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="3a093-200">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="3a093-200">CsResponseGroupAdministrator</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

