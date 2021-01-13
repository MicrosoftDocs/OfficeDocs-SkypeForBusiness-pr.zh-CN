---
title: 对池进行故障转移和故障回复
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: .
ms.openlocfilehash: 1ebd4e8110b8783c869530d95eda0646a895b88e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826562"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a><span data-ttu-id="9f075-103">在 Skype for Business Server 中对池进行故障备份和故障</span><span class="sxs-lookup"><span data-stu-id="9f075-103">Failing over and failing back a pool in Skype for Business Server</span></span> 

<span data-ttu-id="9f075-104">如果单个前端池出现故障且需要进行故障备份，或者遇到灾难的池恢复联机，并且您需要将部署还原到正常工作状态，请使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="9f075-104">Use the following procedures if a single Front End pool has failed and needs to be failed over, or the pool that experienced the disaster is back online and you need to restore your deployment to regular working status.</span></span> <span data-ttu-id="9f075-105">此外，还了解如何对用于 Skype for Business 联盟或 XMPP 联盟的边缘池进行故障转移和故障回复，或更改与前端池关联的边缘池。</span><span class="sxs-lookup"><span data-stu-id="9f075-105">Also  learn how to fail over and fail back the Edge pool used for Skype for Business federation or XMPP federation, or change the Edge pool associated with a Front End pool.</span></span>

- [<span data-ttu-id="9f075-106">对前端池进行故障转移</span><span class="sxs-lookup"><span data-stu-id="9f075-106">Fail over a Front End pool</span></span>](#fail-over-a-front-end-pool)
- [<span data-ttu-id="9f075-107">对池进行故障回复</span><span class="sxs-lookup"><span data-stu-id="9f075-107">Fail back a pool</span></span>](#fail-back-a-pool)
- [<span data-ttu-id="9f075-108">对用于 Skype for Business Server 联盟的边缘池进行故障转移</span><span class="sxs-lookup"><span data-stu-id="9f075-108">Fail over the Edge pool used for Skype for Business Server federation</span></span>](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [<span data-ttu-id="9f075-109">对 Skype for Business Server 中用于 XMPP 联盟的边缘池进行故障转移</span><span class="sxs-lookup"><span data-stu-id="9f075-109">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span>](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [<span data-ttu-id="9f075-110">对用于 Skype for Business Server 联盟或 XMPP 联盟的边缘池进行故障回复</span><span class="sxs-lookup"><span data-stu-id="9f075-110">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span>](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [<span data-ttu-id="9f075-111">更改与前端池关联的边缘池</span><span class="sxs-lookup"><span data-stu-id="9f075-111">Change the Edge pool associated with a Front End pool</span></span>](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a><span data-ttu-id="9f075-112">对前端池进行故障转移</span><span class="sxs-lookup"><span data-stu-id="9f075-112">Fail over a Front End pool</span></span>

<span data-ttu-id="9f075-113">在此过程中，Datacenter1 包含 Pool1，而 Pool1 发生了故障。</span><span class="sxs-lookup"><span data-stu-id="9f075-113">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="9f075-114">此时，您可以故障转移至位于 Datacenter2 中的 Pool2。</span><span class="sxs-lookup"><span data-stu-id="9f075-114">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="9f075-115">池故障转移的多数工作都涉及对中央管理存储进行故障转移（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="9f075-115">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="9f075-116">这一点很重要，因为中央管理存储必须在池用户进行故障处理时正常运行。</span><span class="sxs-lookup"><span data-stu-id="9f075-116">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="9f075-p104">此外，如果某一前端池发生了故障，但该站点中的边缘池仍在运行，则必须知道边缘池是否将发生故障的池用作下一个跃点池。如果是这样，必须在故障转移发生故障的前端池之前，将边缘池更改为使用其他前端池。更改下一个跃点设置的方式取决于边缘要使用的池与边缘池在同一站点中还是在不同站点中。</span><span class="sxs-lookup"><span data-stu-id="9f075-p104">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool. If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool. How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="9f075-120">**将边缘池设置为在同一站点使用下一个跃点池**</span><span class="sxs-lookup"><span data-stu-id="9f075-120">**To set an Edge pool to use a next hop pool at the same site**</span></span>

1.  <span data-ttu-id="9f075-121">打开拓扑生成器，右键单击需要更改的边缘池，然后单击"编辑 **属性"。**</span><span class="sxs-lookup"><span data-stu-id="9f075-121">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="9f075-p105">单击“下一个跃点”。从“下一个跃点池:”列表中，选择现在将用作下一个跃点池的池。</span><span class="sxs-lookup"><span data-stu-id="9f075-p105">Click **Next Hop**. From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="9f075-124">单击“确定”，然后发布更改。</span><span class="sxs-lookup"><span data-stu-id="9f075-124">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="9f075-125">**将边缘池设置为在不同站点使用下一个跃点池**</span><span class="sxs-lookup"><span data-stu-id="9f075-125">**To set an Edge pool to use a next hop pool at a different site**</span></span>

1.  <span data-ttu-id="9f075-126">打开 Skype for Business Server 命令行管理程序 窗口并键入以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="9f075-126">Open a Skype for Business Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="9f075-127">**在灾难中对池进行故障转移**</span><span class="sxs-lookup"><span data-stu-id="9f075-127">**To fail over a pool in a disaster**</span></span>

1.  <span data-ttu-id="9f075-128">在 Pool2 的前端服务器上键入以下 cmdlet，查找哪个池是中央管理服务器的主机：</span><span class="sxs-lookup"><span data-stu-id="9f075-128">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="9f075-129">此 cmdlet 的结果显示当前承载中央管理服务器的池。</span><span class="sxs-lookup"><span data-stu-id="9f075-129">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="9f075-130">在此过程的其余部分中，此池称为 CMS \_ 池。</span><span class="sxs-lookup"><span data-stu-id="9f075-130">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="9f075-131">使用拓扑生成器查找在 CMS 池上运行的 Skype for Business Server \_ 的版本。</span><span class="sxs-lookup"><span data-stu-id="9f075-131">Use Topology Builder to find the version of Skype for Business Server running on the CMS\_Pool.</span></span> <span data-ttu-id="9f075-132">如果它运行的是 Skype for Business Server，请使用以下 cmdlet 查找池 1 的备份池。</span><span class="sxs-lookup"><span data-stu-id="9f075-132">If it is running Skype for Business Server, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="9f075-133">让备份 \_ 池成为备份池。</span><span class="sxs-lookup"><span data-stu-id="9f075-133">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="9f075-134">使用以下 cmdlet 检查中央管理存储的状态：</span><span class="sxs-lookup"><span data-stu-id="9f075-134">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="9f075-135">此 cmdlet 应显示 ActiveMasterFQDN 和 ActiveFileTransferAgents 都指向 CMS 池的 \_ FQDN。</span><span class="sxs-lookup"><span data-stu-id="9f075-135">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="9f075-136">如果为空，则中央管理服务器不可用，您必须进行故障转移。</span><span class="sxs-lookup"><span data-stu-id="9f075-136">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="9f075-137">如果中央管理存储不可用，或者中央管理存储在 Pool1 (（即已失败) 的池）上运行，则必须在对池进行故障转移之前对中央管理服务器进行故障转移。</span><span class="sxs-lookup"><span data-stu-id="9f075-137">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="9f075-138">如果需要对托管在运行 Skype for Business Server 的池上的中央管理服务器进行故障转移，请使用此过程的步骤 5 中的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9f075-138">If you need to fail over the Central Management Server that was hosted on a pool running Skype for Business Server, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="9f075-139">如果不需要对中央管理服务器进行故障转移，请跳至此过程的步骤 7。</span><span class="sxs-lookup"><span data-stu-id="9f075-139">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="9f075-140">若要对运行 Skype for Business Server 的池上的中央管理存储进行故障转移，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="9f075-140">To fail over the Central Management store on a pool running Skype for Business Server, do the following:</span></span>
    
      - <span data-ttu-id="9f075-141">首先，键入以下代码，检查备份池中哪个后端服务器运行中央管理存储 \_ 的主体实例：</span><span class="sxs-lookup"><span data-stu-id="9f075-141">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="9f075-142">如果备份池中的主后端 \_ 服务器是主体，请键入：</span><span class="sxs-lookup"><span data-stu-id="9f075-142">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="9f075-143">如果备份池中的镜像后端 \_ 服务器是主体，请键入：</span><span class="sxs-lookup"><span data-stu-id="9f075-143">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="9f075-144">验证中央管理服务器故障转移是否已完成。</span><span class="sxs-lookup"><span data-stu-id="9f075-144">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="9f075-145">键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="9f075-145">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="9f075-146">检查 ActiveMasterFQDN 和 ActiveFileTransferAgents 是否指向备份池的 \_ FQDN。</span><span class="sxs-lookup"><span data-stu-id="9f075-146">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="9f075-147">最后，键入以下代码，检查所有前端服务器的副本状态：</span><span class="sxs-lookup"><span data-stu-id="9f075-147">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="9f075-148">检查所有副本的值是否为 True。</span><span class="sxs-lookup"><span data-stu-id="9f075-148">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="9f075-149">跳至此过程的第 7 步。</span><span class="sxs-lookup"><span data-stu-id="9f075-149">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="9f075-150">在备份池的后端服务器上安装中央管理 \_ 存储。</span><span class="sxs-lookup"><span data-stu-id="9f075-150">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="9f075-151">首先，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="9f075-151">First, run the following command:</span></span>
        ```PowerShell
         
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="9f075-152">在备份池的一台前端服务器上运行下一个命令以强制移动 \_ 中央管理存储：</span><span class="sxs-lookup"><span data-stu-id="9f075-152">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="9f075-153">验证移动是否完成：</span><span class="sxs-lookup"><span data-stu-id="9f075-153">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="9f075-154">检查 ActiveMasterFQDN 和 ActiveFileTransferAgents 是否指向备份池的 \_ FQDN。</span><span class="sxs-lookup"><span data-stu-id="9f075-154">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="9f075-155">通过键入以下命令检查所有前端服务器的副本状态：</span><span class="sxs-lookup"><span data-stu-id="9f075-155">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="9f075-156">检查所有副本的值是否为 True。</span><span class="sxs-lookup"><span data-stu-id="9f075-156">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="9f075-157">在备份池中的其余前端服务器上安装中央管理服务器 \_ 服务。</span><span class="sxs-lookup"><span data-stu-id="9f075-157">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="9f075-158">为此，请在所有前端服务器上运行以下命令，但在此过程中之前强制中央管理存储移动时所使用的命令除外：</span><span class="sxs-lookup"><span data-stu-id="9f075-158">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="9f075-159">在 Skype for Business Server 命令行管理程序窗口中运行以下 cmdlet，将用户从 Pool1 故障转移到 Pool2：</span><span class="sxs-lookup"><span data-stu-id="9f075-159">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Skype for Business Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="9f075-160">由于此过程的前面部分为检查中央管理存储状态而执行的步骤并不通用，因此此 cmdlet 仍然可能会失败，因为中央管理存储尚未完全故障转移。</span><span class="sxs-lookup"><span data-stu-id="9f075-160">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="9f075-161">在这种情况下，您必须基于看到的错误消息修复中央管理存储，然后再次运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9f075-161">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="9f075-p113">如果您看到下面的错误消息，则需将此站点中的边缘池更改为使用其他池作为其下一个跃点，然后再故障转移该池。有关详细信息，请参阅本主题开头的过程。</span><span class="sxs-lookup"><span data-stu-id="9f075-p113">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool. For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a><span data-ttu-id="9f075-164">对池进行故障回复</span><span class="sxs-lookup"><span data-stu-id="9f075-164">Fail back a pool</span></span>

<span data-ttu-id="9f075-165">在经历灾难的池恢复联机（即此示例中的 Pool1）后，执行以下步骤来使部署恢复常规工作状态。</span><span class="sxs-lookup"><span data-stu-id="9f075-165">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="9f075-166">请注意，故障回复过程需要几分钟时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="9f075-166">Note that the failback process takes several minute to complete.</span></span>  <span data-ttu-id="9f075-167">一个 20,000 个用户的池需要占用 60 分钟的时间，可以此为参考。</span><span class="sxs-lookup"><span data-stu-id="9f075-167">For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="9f075-168">通过键入以下 cmdlet 返回到最初驻留在 Pool1 中并已故障转移到 Pool2 的用户：</span><span class="sxs-lookup"><span data-stu-id="9f075-168">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="9f075-169">无需执行其他步骤。</span><span class="sxs-lookup"><span data-stu-id="9f075-169">No other steps are necessary.</span></span> <span data-ttu-id="9f075-170">如果对中央管理服务器进行失败，可以将它留在 Pool2 中。</span><span class="sxs-lookup"><span data-stu-id="9f075-170">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a><span data-ttu-id="9f075-171">对用于 Skype for Business Server 联盟的边缘池进行故障转移</span><span class="sxs-lookup"><span data-stu-id="9f075-171">Fail over the Edge pool used for Skype for Business Server federation</span></span> 

<span data-ttu-id="9f075-172">如果配置了 Skype for Business Server 联盟的边缘池关闭，则必须更改联盟以使用不同的边缘池使联盟正常工作。</span><span class="sxs-lookup"><span data-stu-id="9f075-172">If the Edge pool where you have Skype for Business Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

1.  <span data-ttu-id="9f075-173">在前端服务器上，打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="9f075-173">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="9f075-174">展开 **边缘池**，然后右键单击当前为联盟配置的边缘服务器或边缘服务器池。</span><span class="sxs-lookup"><span data-stu-id="9f075-174">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="9f075-175">选择“编辑属性”。</span><span class="sxs-lookup"><span data-stu-id="9f075-175">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="9f075-176">在“编辑属性”中的“常规”下，清除“为此边缘池启用联盟（端口 5061）”。</span><span class="sxs-lookup"><span data-stu-id="9f075-176">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="9f075-177">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="9f075-177">Click **OK**.</span></span>

3.  <span data-ttu-id="9f075-178">展开 **边缘池**，然后右键单击现在要用于联盟的边缘服务器或边缘服务器池。</span><span class="sxs-lookup"><span data-stu-id="9f075-178">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="9f075-179">选择“编辑属性”。</span><span class="sxs-lookup"><span data-stu-id="9f075-179">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="9f075-p119">在“编辑属性”中的“常规”下，选择“为此边缘池启用联盟（端口 5061）”。单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="9f075-p119">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>

5.  <span data-ttu-id="9f075-p120">单击“操作”，选择“拓扑”，再选择“发布”。当“发布拓扑”中出现提示时，单击“下一步”。完成发布后，单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="9f075-p120">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="9f075-185">在边缘服务器上，打开 Skype for Business Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="9f075-185">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="9f075-186">单击 **"安装或更新 Skype for Business Server 系统**"，然后单击"**安装或删除 Skype for Business Server 组件"。**</span><span class="sxs-lookup"><span data-stu-id="9f075-186">Click **Install or Update Skype for Business Server System**, and then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="9f075-187">单击“再次运行”。</span><span class="sxs-lookup"><span data-stu-id="9f075-187">Click **Run Again**.</span></span>

7.  <span data-ttu-id="9f075-188">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="9f075-188">Click **Next**.</span></span> <span data-ttu-id="9f075-189">摘要屏幕将显示已执行的操作。</span><span class="sxs-lookup"><span data-stu-id="9f075-189">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="9f075-190">部署完成后，单击“查看日志”可查看可用日志文件。</span><span class="sxs-lookup"><span data-stu-id="9f075-190">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="9f075-191">单击“完成”以完成部署。</span><span class="sxs-lookup"><span data-stu-id="9f075-191">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="9f075-192">如果包含故障边缘池的站点包含仍在运行的前端服务器，则必须更新这些前端池上的 Web 会议服务和 A/V 会议服务才能在仍在运行的远程站点中使用边缘池。</span><span class="sxs-lookup"><span data-stu-id="9f075-192">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a><span data-ttu-id="9f075-193">对 Skype for Business Server 中用于 XMPP 联盟的边缘池进行故障转移</span><span class="sxs-lookup"><span data-stu-id="9f075-193">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span> 

<span data-ttu-id="9f075-p123">在您的组织中，已将一个边缘池指定为用于 XMPP 联盟的池。如果该池出现故障，您必须先对 XMPP 联盟进行故障转移以使用其他边缘池，直到 XMPP 联盟可重新正常工作。</span><span class="sxs-lookup"><span data-stu-id="9f075-p123">In your organization, there is one Edge pool designated as the pool to use for XMPP federation. If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="9f075-196">在您首次安装边缘池并启用 XMPP 联盟时，您可以通过为 XMPP 联盟的所有（而不只是一个）边缘池设置外部 DNS SRV 记录来简化灾难恢复过程。</span><span class="sxs-lookup"><span data-stu-id="9f075-196">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="9f075-197">所有这些 SRV 记录都必须具有不同的优先级设置。</span><span class="sxs-lookup"><span data-stu-id="9f075-197">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="9f075-198">所有 XMPP 联盟流量将通过具有优先级最高的 SRV 记录的池。</span><span class="sxs-lookup"><span data-stu-id="9f075-198">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> 

<span data-ttu-id="9f075-199">在以下过程中，EdgePool1 是最初承载 XMPP 联盟的池，EdgePool2 是现在承载 XMPP 联盟的池。</span><span class="sxs-lookup"><span data-stu-id="9f075-199">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="9f075-200">对用于 XMPP 联盟的边缘池进行故障转移</span><span class="sxs-lookup"><span data-stu-id="9f075-200">To fail over the Edge pool used for XMPP federation</span></span>

1.  <span data-ttu-id="9f075-201">如果您尚未部署另一个边缘池（当前出现故障的边缘池之外的池），请部署该池。</span><span class="sxs-lookup"><span data-stu-id="9f075-201">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> 

2.  <span data-ttu-id="9f075-202">在现在承载 XMPP 联盟的新边缘池 (EdgePool2) 中的每个边缘服务器上，运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="9f075-202">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="9f075-203">运行以下 cmdlet 可将 XMPP 联盟路由重新指向 EdgePool2：</span><span class="sxs-lookup"><span data-stu-id="9f075-203">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="9f075-204">在此示例中，Site2 是包括现在承载 XMPP 联盟路由的边缘池的站点，EdgeServer2.contoso.com 是该池中某个边缘服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="9f075-204">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="9f075-205">在外部 DNS 服务器上，将 XMPP 联盟的 DNS A 记录更改为指向 EdgeServer2.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="9f075-205">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="9f075-p125">如果您尚不具有解析为现在承载 XMPP 联盟的边缘池的 XMPP 联盟的 DNS SRV 记录，则必须添加它，如以下示例中所示。此 SRV 记录的端口值必须为 5269。</span><span class="sxs-lookup"><span data-stu-id="9f075-p125">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="9f075-208">确认现在承载 XMPP 联盟的边缘池具有已外部打开的端口 5269。</span><span class="sxs-lookup"><span data-stu-id="9f075-208">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="9f075-209">在现在承载 XMPP 联盟的边缘池中的所有边缘服务器上启动服务：</span><span class="sxs-lookup"><span data-stu-id="9f075-209">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a><span data-ttu-id="9f075-210">对用于 Skype for Business Server 联盟或 XMPP 联盟的边缘池进行故障回复</span><span class="sxs-lookup"><span data-stu-id="9f075-210">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span> 

<span data-ttu-id="9f075-211">在用于托管联盟的故障边缘池重新联机后，使用此过程对 Skype for Business Server 联盟路由和/或 XMPP 联盟路由进行故障回复，以再次使用此还原的边缘池。</span><span class="sxs-lookup"><span data-stu-id="9f075-211">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Skype for Business Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

1.  <span data-ttu-id="9f075-212">在此时再次可用的边缘池上，启动边缘服务。</span><span class="sxs-lookup"><span data-stu-id="9f075-212">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="9f075-213">如果要对 Skype for Business Server 联盟路由进行故障回复以使用还原的边缘服务器，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="9f075-213">If you want to fail back the Skype for Business Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="9f075-p126">在前端服务器上，打开拓扑生成器。展开“边缘池”，然后右键单击当前为联盟配置的边缘服务器或边缘服务器池。选择“编辑属性”。</span><span class="sxs-lookup"><span data-stu-id="9f075-p126">On a Front End server, open Topology Builder. Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="9f075-p127">在“编辑属性”中的“常规”下，清除“为此边缘池启用联盟（端口 5061）”。单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="9f075-p127">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="9f075-p128">展开“边缘池”，然后右键单击您想再次用于联盟的原始边缘服务器或边缘服务器池。选择“编辑属性”。</span><span class="sxs-lookup"><span data-stu-id="9f075-p128">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="9f075-p129">在“编辑属性”中的“常规”下，选择“为此边缘池启用联盟（端口 5061）”。单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="9f075-p129">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="9f075-p130">单击“操作”，选择“拓扑”，再选择“发布”。当“发布拓扑”中出现提示时，单击“下一步”。完成发布后，单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="9f075-p130">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="9f075-226">在边缘服务器上，打开 Skype for Business Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="9f075-226">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="9f075-227">单击 **"安装或更新 Skype for Business Server 系统**"，然后单击 **"安装或删除 Skype for Business Server 组件"。**</span><span class="sxs-lookup"><span data-stu-id="9f075-227">Click **Install or Update Skype for Business Server System**, then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="9f075-228">单击“再次运行”。</span><span class="sxs-lookup"><span data-stu-id="9f075-228">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="9f075-229">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="9f075-229">Click **Next**.</span></span> <span data-ttu-id="9f075-230">摘要屏幕将显示已执行的操作。</span><span class="sxs-lookup"><span data-stu-id="9f075-230">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="9f075-231">部署完成后，单击“查看日志”可查看可用日志文件。</span><span class="sxs-lookup"><span data-stu-id="9f075-231">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="9f075-232">单击“完成”以完成部署。</span><span class="sxs-lookup"><span data-stu-id="9f075-232">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="9f075-233">如果想要对 XMPP 联盟路由进行故障回复以使用恢复的边缘服务器，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9f075-233">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="9f075-234">运行以下 cmdlet 以将 XMPP 联盟路由重新指向此时将承载 XMPP 联盟的服务器（在此示例中为 EdgeServer1）：</span><span class="sxs-lookup"><span data-stu-id="9f075-234">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="9f075-235">在此示例中，Site1 是包含此时将承载 XMPP 联盟路由的边缘池的站点，EdgeServer1.contoso.com 是该池中边缘服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="9f075-235">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="9f075-p133">如果您尚未拥有解析到此时将承载 XMPP 联盟的边缘池的 XMPP 联盟的 DNS SRV 记录，则必须添加该记录，如下例所示。该 SRV 记录的端口值必须为 5269。</span><span class="sxs-lookup"><span data-stu-id="9f075-p133">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="9f075-238">在外部 DNS 服务器上，将 XMPP 联盟的 DNS A 记录更改为指向 EdgeServer2.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="9f075-238">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="9f075-239">确认此时将承载 XMPP 联盟的边缘池已将端口 5269 向外部开放。</span><span class="sxs-lookup"><span data-stu-id="9f075-239">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="9f075-240">如果前端池在含有出过故障并且已恢复的边缘池的站点中持续运行，则应该更新这些前端池上的 Web 会议服务和 A/V 会议服务，以在其本地站点上再次使用边缘池。</span><span class="sxs-lookup"><span data-stu-id="9f075-240">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span>

5.  <span data-ttu-id="9f075-241">如果在出现了故障边缘池的同一站点上的前端池也出现故障，则现在可以使用 Invoke–CsPoolFailback 对前端池进行故障回复。</span><span class="sxs-lookup"><span data-stu-id="9f075-241">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="9f075-242">更改与前端池关联的边缘池</span><span class="sxs-lookup"><span data-stu-id="9f075-242">Change the Edge pool associated with a Front End pool</span></span>

<span data-ttu-id="9f075-243">如果边缘池出现故障，但同一站点中的前端池仍在运行，您将需要将前端池设置为使用其他站点中的边缘池，直到故障池恢复。</span><span class="sxs-lookup"><span data-stu-id="9f075-243">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

1.  <span data-ttu-id="9f075-244">在拓扑生成器中，导航到需要更改的前端池的名称。</span><span class="sxs-lookup"><span data-stu-id="9f075-244">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="9f075-245">右键单击该池，然后单击“编辑属性”。</span><span class="sxs-lookup"><span data-stu-id="9f075-245">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="9f075-246">在“关联”部分的“关联边缘池(用于媒体组件)”下，使用下拉框选择要与此前端池关联的边缘池。</span><span class="sxs-lookup"><span data-stu-id="9f075-246">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="9f075-247">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="9f075-247">Click **OK**.</span></span>
