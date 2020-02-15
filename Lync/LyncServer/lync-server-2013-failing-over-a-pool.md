---
title: Lync Server 2013：对池进行故障转移
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a pool
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204678(v=OCS.15)
ms:contentKeyID: 48183432
ms.date: 10/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7de00de8361ac8bc5827fd76ea2486ae790a66d4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-pool-in-lync-server-2013"></a><span data-ttu-id="78ae6-102">在 Lync Server 2013 中对池进行故障转移</span><span class="sxs-lookup"><span data-stu-id="78ae6-102">Failing over a pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78ae6-103">_**上次修改的主题：** 2014-10-10_</span><span class="sxs-lookup"><span data-stu-id="78ae6-103">_**Topic Last Modified:** 2014-10-10_</span></span>

<span data-ttu-id="78ae6-p101">如果某个前端池发生故障并需要进行故障转移，请使用以下过程。在此过程中，Datacenter1 包含 Pool1，而 Pool1 发生了故障。此时，您可以故障转移至位于 Datacenter2 中的 Pool2。</span><span class="sxs-lookup"><span data-stu-id="78ae6-p101">If a single Front End pool has failed and needs to be failed over, use the following procedure. In this procedure, Datacenter1 contains Pool1, and Pool1 has failed. You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="78ae6-107">大多数池故障转移的工作涉及到中央管理存储的故障转移（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="78ae6-107">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="78ae6-108">这一点很重要，因为当池的用户进行故障转移时，中央管理存储必须正常工作。</span><span class="sxs-lookup"><span data-stu-id="78ae6-108">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="78ae6-p103">此外，如果某一前端池发生了故障，但该站点中的边缘池仍在运行，则必须知道边缘池是否将发生故障的池用作下一个跃点池。如果是这样，必须在故障转移发生故障的前端池之前，将边缘池更改为使用其他前端池。更改下一个跃点设置的方式取决于边缘要使用的池与边缘池在同一站点中还是在不同站点中。</span><span class="sxs-lookup"><span data-stu-id="78ae6-p103">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool. If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool. How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="78ae6-112">**设置边缘池以使用同一站点中的下一个跃点池**</span><span class="sxs-lookup"><span data-stu-id="78ae6-112">**To Set an Edge Pool to Use a Next Hop Pool at the Same Site**</span></span>

1.  <span data-ttu-id="78ae6-113">打开拓扑生成器，右键单击需要更改的边缘池，然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="78ae6-113">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="78ae6-p104">单击“下一个跃点”\*\*\*\*。从“下一个跃点池:”\*\*\*\* 列表中，选择现在将用作下一个跃点池的池。</span><span class="sxs-lookup"><span data-stu-id="78ae6-p104">Click **Next Hop**. From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="78ae6-116">单击“确定”\*\*\*\*，然后发布更改。</span><span class="sxs-lookup"><span data-stu-id="78ae6-116">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="78ae6-117">**设置边缘池以使用不同站点中的下一个跃点池**</span><span class="sxs-lookup"><span data-stu-id="78ae6-117">**To Set an Edge Pool to Use a Next Hop Pool at a Different Site**</span></span>

1.  <span data-ttu-id="78ae6-118">打开 Lync Server 命令行管理程序窗口并键入以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="78ae6-118">Open a Lync Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="78ae6-119">**在发生灾难时对池进行故障转移**</span><span class="sxs-lookup"><span data-stu-id="78ae6-119">**To Fail Over a Pool in a Disaster**</span></span>

1.  <span data-ttu-id="78ae6-120">通过在 Pool2 中的前端服务器上键入以下 cmdlet 来查找哪个池是中央管理服务器的主机：</span><span class="sxs-lookup"><span data-stu-id="78ae6-120">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="78ae6-121">此 cmdlet 的结果显示当前承载中央管理服务器的池。</span><span class="sxs-lookup"><span data-stu-id="78ae6-121">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="78ae6-122">在此过程的其余部分，此池称为 CMS\_池。</span><span class="sxs-lookup"><span data-stu-id="78ae6-122">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="78ae6-123">使用拓扑生成器查找 CMS\_池上运行的 Lync Server 的版本。</span><span class="sxs-lookup"><span data-stu-id="78ae6-123">Use Topology Builder to find the version of Lync Server running on the CMS\_Pool.</span></span> <span data-ttu-id="78ae6-124">如果它运行的是 Lync Server 2013，请使用以下 cmdlet 查找池1的备份池。</span><span class="sxs-lookup"><span data-stu-id="78ae6-124">If it is running Lync Server 2013, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="78ae6-125">让备份\_池成为备份池。</span><span class="sxs-lookup"><span data-stu-id="78ae6-125">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="78ae6-126">使用以下 cmdlet 检查中央管理存储的状态：</span><span class="sxs-lookup"><span data-stu-id="78ae6-126">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="78ae6-127">此 cmdlet 应显示 ActiveMasterFQDN 和 ActiveFileTransferAgents 都指向 CMS\_池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="78ae6-127">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="78ae6-128">如果它们是空的，则中央管理服务器不可用，您必须将其故障转移。</span><span class="sxs-lookup"><span data-stu-id="78ae6-128">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="78ae6-129">如果中央管理存储不可用，或者中央管理存储在 Pool1 上运行（即失败的池），则必须先对中央管理服务器进行故障转移，然后再对池进行故障转移。</span><span class="sxs-lookup"><span data-stu-id="78ae6-129">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="78ae6-130">如果需要对运行 Lync Server 2013 的池上承载的中央管理服务器进行故障转移，请使用此过程的步骤5中的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="78ae6-130">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2013, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="78ae6-131">如果需要对运行 Lync Server 2010 的池上承载的中央管理服务器进行故障转移，请使用此过程的步骤6中的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="78ae6-131">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2010, use the cmdlet in step 6 of this procedure.</span></span> <span data-ttu-id="78ae6-132">如果不需要对中央管理服务器进行故障转移，请跳到此过程的步骤7。</span><span class="sxs-lookup"><span data-stu-id="78ae6-132">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="78ae6-133">若要在运行 Lync Server 2013 的池中对中央管理存储进行故障转移，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="78ae6-133">To fail over the Central Management store on a pool running Lync Server 2013, do the following:</span></span>
    
      - <span data-ttu-id="78ae6-134">首先，通过键入以下命令，检查备份\_池中的哪个后端服务器运行中央管理存储的主体实例：</span><span class="sxs-lookup"><span data-stu-id="78ae6-134">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="78ae6-135">如果备份\_池中的主后端服务器是主体，请键入：</span><span class="sxs-lookup"><span data-stu-id="78ae6-135">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="78ae6-136">如果 Backup\_Pool 中的镜像后端服务器是主体，请键入：</span><span class="sxs-lookup"><span data-stu-id="78ae6-136">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="78ae6-137">验证中央管理服务器故障转移是否已完成。</span><span class="sxs-lookup"><span data-stu-id="78ae6-137">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="78ae6-138">键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="78ae6-138">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="78ae6-139">检查 ActiveMasterFQDN 和 ActiveFileTransferAgents 是否都指向备份\_池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="78ae6-139">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="78ae6-140">最后，通过键入以下命令检查所有前端服务器的副本状态：</span><span class="sxs-lookup"><span data-stu-id="78ae6-140">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="78ae6-141">检查所有副本的值是否为 True。</span><span class="sxs-lookup"><span data-stu-id="78ae6-141">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="78ae6-142">跳至此过程的第 7 步。</span><span class="sxs-lookup"><span data-stu-id="78ae6-142">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="78ae6-143">在备份\_池的后端服务器上安装中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="78ae6-143">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="78ae6-144">首先，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="78ae6-144">First, run the following command:</span></span>
        
        ```PowerShell 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="78ae6-145">在备份\_池的前端服务器之一上运行下一个命令，以强制移动中央管理存储：</span><span class="sxs-lookup"><span data-stu-id="78ae6-145">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="78ae6-146">验证移动是否完成：</span><span class="sxs-lookup"><span data-stu-id="78ae6-146">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="78ae6-147">检查 ActiveMasterFQDN 和 ActiveFileTransferAgents 是否都指向备份\_池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="78ae6-147">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="78ae6-148">通过键入以下命令检查所有前端服务器的副本状态：</span><span class="sxs-lookup"><span data-stu-id="78ae6-148">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="78ae6-149">检查所有副本的值是否为 True。</span><span class="sxs-lookup"><span data-stu-id="78ae6-149">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="78ae6-150">在备份\_池中的其余前端服务器上安装中央管理服务器服务。</span><span class="sxs-lookup"><span data-stu-id="78ae6-150">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="78ae6-151">若要执行此操作，请在所有前端服务器上运行以下命令，但在此过程前面强制实施中央管理存储移动时使用的服务器除外：</span><span class="sxs-lookup"><span data-stu-id="78ae6-151">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="78ae6-152">通过在 Lync Server 命令行管理程序窗口中运行以下 cmdlet，将用户从 Pool1 故障转移到 Pool2：</span><span class="sxs-lookup"><span data-stu-id="78ae6-152">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Lync Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="78ae6-153">由于在此过程的前几部分中执行的检查中央管理存储状态的步骤并不是通用的，因此此 cmdlet 仍有机会失败，因为中央管理存储尚未完全故障转移。</span><span class="sxs-lookup"><span data-stu-id="78ae6-153">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="78ae6-154">在这种情况下，您必须根据您看到的错误消息来修复中央管理存储，然后再次运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="78ae6-154">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="78ae6-p112">如果您看到下面的错误消息，则需将此站点中的边缘池更改为使用其他池作为其下一个跃点，然后再故障转移该池。有关详细信息，请参阅本主题开头的过程。</span><span class="sxs-lookup"><span data-stu-id="78ae6-p112">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool. For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.

</div>

<span> </span>

</div>

</div>

</div>

