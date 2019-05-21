---
title: 对池进行故障转移和故障回复
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: .
ms.openlocfilehash: 2848261164ac568d3db4dd05160b7e50ec3981d3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303884"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a><span data-ttu-id="1ec9e-103">在 Skype for Business 服务器中故障转移和恢复池失败</span><span class="sxs-lookup"><span data-stu-id="1ec9e-103">Failing over and failing back a pool in Skype for Business Server</span></span> 

<span data-ttu-id="1ec9e-104">如果单个前端池出现故障且需要故障转移, 或者遇到灾难的池重新联机, 并且你需要将部署还原到正常工作状态, 请使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-104">Use the following procedures if a single Front End pool has failed and needs to be failed over, or the pool that experienced the disaster is back online and you need to restore your deployment to regular working status.</span></span> <span data-ttu-id="1ec9e-105">此外, 还可了解如何故障转移和故障回复用于 Skype for business federation 或 XMPP federation 的边缘池, 或更改与前端池关联的边缘池。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-105">Also  learn how to fail over and fail back the Edge pool used for Skype for Business federation or XMPP federation, or change the Edge pool associated with a Front End pool.</span></span>

- [<span data-ttu-id="1ec9e-106">故障转移前端池</span><span class="sxs-lookup"><span data-stu-id="1ec9e-106">Fail over a Front End pool</span></span>](#fail-over-a-front-end-pool)
- [<span data-ttu-id="1ec9e-107">故障回复池</span><span class="sxs-lookup"><span data-stu-id="1ec9e-107">Fail back a pool</span></span>](#fail-back-a-pool)
- [<span data-ttu-id="1ec9e-108">故障切换用于 Skype for business 服务器联合的边缘池</span><span class="sxs-lookup"><span data-stu-id="1ec9e-108">Fail over the Edge pool used for Skype for Business Server federation</span></span>](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [<span data-ttu-id="1ec9e-109">在 Skype for Business 服务器中针对 XMPP 联盟使用的边缘池故障转移</span><span class="sxs-lookup"><span data-stu-id="1ec9e-109">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span>](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [<span data-ttu-id="1ec9e-110">故障回复用于 Skype for Business 服务器联盟或 XMPP 联合身份验证的边缘池</span><span class="sxs-lookup"><span data-stu-id="1ec9e-110">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span>](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [<span data-ttu-id="1ec9e-111">更改与前端池关联的边缘池</span><span class="sxs-lookup"><span data-stu-id="1ec9e-111">Change the Edge pool associated with a Front End pool</span></span>](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a><span data-ttu-id="1ec9e-112">故障转移前端池</span><span class="sxs-lookup"><span data-stu-id="1ec9e-112">Fail over a Front End pool</span></span>

<span data-ttu-id="1ec9e-113">在此过程中, Datacenter1 包含 Pool1, 而 Pool1 失败。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-113">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="1ec9e-114">您将在 Datacenter2 中故障转移到 Pool2。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-114">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="1ec9e-115">对于池故障转移, 大部分工作都涉及到中央管理存储的故障 (如果需要)。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-115">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="1ec9e-116">这一点很重要, 因为中央管理存储在池的用户故障转移时必须正常工作。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-116">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="1ec9e-117">此外, 如果前端池出现故障, 但该站点上的边缘池仍在运行, 则必须知道 Edge 池是否将失败的池用作下一个跃点池。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-117">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool.</span></span> <span data-ttu-id="1ec9e-118">如果是, 则必须将 Edge 池更改为使用不同的前端池, 然后再进行故障转移失败的前端池。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-118">If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool.</span></span> <span data-ttu-id="1ec9e-119">更改下一个跃点设置的方式取决于边缘是将同一站点上的池用作边缘池还是其他网站。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-119">How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="1ec9e-120">**将 "边缘池" 设置为在同一站点使用下一个跃点池**</span><span class="sxs-lookup"><span data-stu-id="1ec9e-120">**To set an Edge pool to use a next hop pool at the same site**</span></span>

1.  <span data-ttu-id="1ec9e-121">打开拓扑生成器, 右键单击需要更改的边缘池, 然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-121">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="1ec9e-122">单击 "**下一跃点**"。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-122">Click **Next Hop**.</span></span> <span data-ttu-id="1ec9e-123">从**下一个 "跃点池:** " 列表中, 选择现在将用作下一个跃点池的池。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-123">From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="1ec9e-124">单击 **"确定**", 然后发布所做的更改。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-124">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="1ec9e-125">**将边缘池设置为在其他网站上使用下一个跃点池**</span><span class="sxs-lookup"><span data-stu-id="1ec9e-125">**To set an Edge pool to use a next hop pool at a different site**</span></span>

1.  <span data-ttu-id="1ec9e-126">打开 Skype for Business 服务器管理外壳窗口, 键入以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1ec9e-126">Open a Skype for Business Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="1ec9e-127">**在灾难中故障转移池**</span><span class="sxs-lookup"><span data-stu-id="1ec9e-127">**To fail over a pool in a disaster**</span></span>

1.  <span data-ttu-id="1ec9e-128">通过在 Pool2 中的前端服务器上键入以下 cmdlet 来查找哪个池是中央管理服务器的主机:</span><span class="sxs-lookup"><span data-stu-id="1ec9e-128">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="1ec9e-129">此 cmdlet 的结果显示当前托管中央管理服务器的池。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-129">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="1ec9e-130">在此过程的其余部分中, 此池称为 CMS\_池。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-130">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="1ec9e-131">使用拓扑生成器查找 CMS\_池中运行的 Skype For business 服务器版本。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-131">Use Topology Builder to find the version of Skype for Business Server running on the CMS\_Pool.</span></span> <span data-ttu-id="1ec9e-132">如果它运行的是 Skype for Business 服务器, 请使用以下 cmdlet 查找池1的备份池。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-132">If it is running Skype for Business Server, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="1ec9e-133">让备份\_池成为备份池。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-133">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="1ec9e-134">通过以下 cmdlet 检查中央管理存储的状态:</span><span class="sxs-lookup"><span data-stu-id="1ec9e-134">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="1ec9e-135">此 cmdlet 应显示 ActiveMasterFQDN 和 ActiveFileTransferAgents 都指向 CMS\_池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-135">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="1ec9e-136">如果它们为空, 则中央管理服务器不可用, 您必须将其故障转移。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-136">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="1ec9e-137">如果中央管理存储不可用, 或者中央管理存储在 Pool1 上运行 (即失败的池), 则必须先通过中央管理服务器进行故障转移, 然后才能故障转移池。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-137">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="1ec9e-138">如果需要在运行 Skype for Business Server 的池中托管的中央管理服务器上失败, 请使用此过程步骤5中的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-138">If you need to fail over the Central Management Server that was hosted on a pool running Skype for Business Server, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="1ec9e-139">如果不需要故障转移中央管理服务器, 请跳到此过程的步骤7。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-139">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="1ec9e-140">要在运行 Skype for Business Server 的池上故障转移中央管理存储, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="1ec9e-140">To fail over the Central Management store on a pool running Skype for Business Server, do the following:</span></span>
    
      - <span data-ttu-id="1ec9e-141">首先, 检查备份\_池中的后端服务器通过键入以下内容来运行中央管理存储的主体实例:</span><span class="sxs-lookup"><span data-stu-id="1ec9e-141">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="1ec9e-142">如果备份\_池中的主后端服务器是主体, 请键入:</span><span class="sxs-lookup"><span data-stu-id="1ec9e-142">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="1ec9e-143">如果备份\_池中的镜像后端服务器是主体, 请键入:</span><span class="sxs-lookup"><span data-stu-id="1ec9e-143">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="1ec9e-144">验证中央管理服务器故障转移是否已完成。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-144">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="1ec9e-145">键入以下内容:</span><span class="sxs-lookup"><span data-stu-id="1ec9e-145">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="1ec9e-146">检查 ActiveMasterFQDN 和 ActiveFileTransferAgents 是否都指向备份\_池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-146">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="1ec9e-147">最后, 通过键入以下内容检查所有前端服务器的副本状态:</span><span class="sxs-lookup"><span data-stu-id="1ec9e-147">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="1ec9e-148">检查所有副本的值是否均为 True。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-148">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="1ec9e-149">跳转到此过程中的步骤7。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-149">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="1ec9e-150">在备份\_池的后端服务器上安装中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-150">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="1ec9e-151">首先, 运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="1ec9e-151">First, run the following command:</span></span>
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="1ec9e-152">在备份\_池的前端服务器之一上运行下一个命令以强制移动中央管理存储:</span><span class="sxs-lookup"><span data-stu-id="1ec9e-152">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="1ec9e-153">验证移动是否已完成:</span><span class="sxs-lookup"><span data-stu-id="1ec9e-153">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="1ec9e-154">检查 ActiveMasterFQDN 和 ActiveFileTransferAgents 是否都指向备份\_池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-154">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="1ec9e-155">通过键入以下内容检查所有前端服务器的副本状态:</span><span class="sxs-lookup"><span data-stu-id="1ec9e-155">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="1ec9e-156">检查所有副本的值是否均为 True。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-156">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="1ec9e-157">在备份\_池中的其他前端服务器上安装中央管理服务器服务。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-157">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="1ec9e-158">若要执行此操作, 请在所有前端服务器上运行以下命令, 除了在此过程前面强制执行中央管理存储移动时使用的所有服务器:</span><span class="sxs-lookup"><span data-stu-id="1ec9e-158">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="1ec9e-159">通过在 Skype for Business Server Management Shell 窗口中运行以下 cmdlet, 将用户从 Pool1 故障转移到 Pool2:</span><span class="sxs-lookup"><span data-stu-id="1ec9e-159">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Skype for Business Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="1ec9e-160">由于本过程的前面部分中所执行的检查中央管理存储状态的步骤不是通用的, 因此此 cmdlet 仍会失败, 因为中央管理存储尚未完全故障转移。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-160">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="1ec9e-161">在这种情况下, 你必须根据你看到的错误消息修复中央管理存储, 然后再次运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-161">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="1ec9e-162">如果你看到以下错误消息, 则你需要更改此网站上的边缘池, 以便在对池进行故障转移之前使用其他池作为下一个跃点。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-162">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool.</span></span> <span data-ttu-id="1ec9e-163">有关详细信息, 请参阅本主题开头的过程。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-163">For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a><span data-ttu-id="1ec9e-164">故障回复池</span><span class="sxs-lookup"><span data-stu-id="1ec9e-164">Fail back a pool</span></span>

<span data-ttu-id="1ec9e-165">在发生灾难的池重新联机后 (即在此示例中为 Pool1), 请执行以下步骤将你的部署还原到正常的工作状态。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-165">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="1ec9e-166">请注意, 故障回复过程需要几分钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-166">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="1ec9e-167">作为参考，对于用户数为 20,000 的池而言，预期最多需要 60 分钟。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-167">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="1ec9e-168">通过键入以下 cmdlet 对最初驻留在 Pool1 中的用户进行故障回复, 并已故障转移到 Pool2:</span><span class="sxs-lookup"><span data-stu-id="1ec9e-168">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="1ec9e-169">无需执行其他步骤。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-169">No other steps are necessary.</span></span> <span data-ttu-id="1ec9e-170">如果您通过中央管理服务器进行了故障转移, 您可以将其保留在 Pool2 中。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-170">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a><span data-ttu-id="1ec9e-171">故障切换用于 Skype for business 服务器联合的边缘池</span><span class="sxs-lookup"><span data-stu-id="1ec9e-171">Fail over the Edge pool used for Skype for Business Server federation</span></span> 

<span data-ttu-id="1ec9e-172">如果您的 Skype for business Server 联合身份验证配置所在的边缘池已关闭, 则必须将联合身份更改为使用不同的边缘池才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-172">If the Edge pool where you have Skype for Business Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

1.  <span data-ttu-id="1ec9e-173">在前端服务器上, 打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-173">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="1ec9e-174">展开 "**边缘池**", 然后右键单击当前为联盟配置的边缘服务器或边缘服务器池。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-174">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="1ec9e-175">选择 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-175">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="1ec9e-176">在 "**编辑属性**" 下的 "**常规**" 下, 清除 "**为此边缘池启用联盟 (端口 5061)**"。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-176">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="1ec9e-177">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-177">Click **OK**.</span></span>

3.  <span data-ttu-id="1ec9e-178">展开 "**边缘池**", 然后右键单击要用于联盟的边缘服务器或边缘服务器池。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-178">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="1ec9e-179">选择 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-179">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="1ec9e-180">在 "**常规**" 下的 "**编辑属性**" 下, 选择 "**为此边缘池启用联盟 (端口 5061)**"。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-180">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="1ec9e-181">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-181">Click **OK**.</span></span>

5.  <span data-ttu-id="1ec9e-182">单击 "**操作**", 选择 "**拓扑**", 选择 "**发布**"。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-182">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="1ec9e-183">当系统提示**发布拓扑**时, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-183">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="1ec9e-184">发布完成后, 单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-184">When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="1ec9e-185">在边缘服务器上, 打开 "Skype for Business 服务器部署" 向导。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-185">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="1ec9e-186">单击 "**安装或更新 skype for Business 服务器系统**", 然后单击 "**设置" 或 "删除 Skype For business 服务器组件**"。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-186">Click **Install or Update Skype for Business Server System**, and then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="1ec9e-187">再次单击 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-187">Click **Run Again**.</span></span>

7.  <span data-ttu-id="1ec9e-188">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-188">Click **Next**.</span></span> <span data-ttu-id="1ec9e-189">"摘要" 屏幕将显示执行时的操作。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-189">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="1ec9e-190">部署完成后, 单击 "**查看日志**" 以查看可用的日志文件。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-190">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="1ec9e-191">单击 "**完成**" 以完成部署。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-191">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="1ec9e-192">如果包含失败的 Edge 池的网站包含仍在运行的前端服务器, 则必须更新这些前端池上的 Web 会议服务和 A/V 会议服务, 才能使用仍在运行的远程网站中的边缘池。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-192">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a><span data-ttu-id="1ec9e-193">在 Skype for Business 服务器中针对 XMPP 联盟使用的边缘池故障转移</span><span class="sxs-lookup"><span data-stu-id="1ec9e-193">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span> 

<span data-ttu-id="1ec9e-194">在你的组织中, 有一个边界池指定为用于 XMPP 联合身份验证的池。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-194">In your organization, there is one Edge pool designated as the pool to use for XMPP federation.</span></span> <span data-ttu-id="1ec9e-195">如果此池停止运行, 则必须故障转移 XMPP 联合身份验证才能使用其他边缘池, 然后 XMPP 联盟才能再次工作。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-195">If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="1ec9e-196">当你首次安装 Edge 池并启用 XMPP 联合身份验证时, 你可以通过为 XMPP 联盟的所有边缘池设置外部 DNS SRV 记录 (而不是仅一个) 来简化灾难恢复过程。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-196">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="1ec9e-197">其中每个 SRV 记录都必须具有不同的优先级集。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-197">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="1ec9e-198">所有 XMPP 联盟流量都将经历具有最高优先级的 SRV 记录的池。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-198">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> 

<span data-ttu-id="1ec9e-199">在以下过程中, EdgePool1 是最初托管 XMPP 联盟的池, EdgePool2 是池, 它现在将托管 XMPP 联合。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-199">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="1ec9e-200">故障切换用于 XMPP 联盟的边缘池</span><span class="sxs-lookup"><span data-stu-id="1ec9e-200">To fail over the Edge pool used for XMPP federation</span></span>

1.  <span data-ttu-id="1ec9e-201">如果尚未部署另一个边缘池 (除了当前已关闭的), 请部署该池。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-201">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> 

2.  <span data-ttu-id="1ec9e-202">在现在将托管 XMPP 联合身份验证 (EdgePool2) 的新边缘池中的每个边缘服务器上, 运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1ec9e-202">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="1ec9e-203">运行以下 cmdlet 以将 XMPP 联盟路由 repoint 到 EdgePool2:</span><span class="sxs-lookup"><span data-stu-id="1ec9e-203">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="1ec9e-204">在此示例中, Site2 是包含边缘池的网站, 它现在将托管 XMPP 联合路由, EdgeServer2.contoso.com 是该池中的边缘服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-204">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="1ec9e-205">在外部 DNS 服务器上, 将 XMPP 联合的 DNS A 记录更改为指向 EdgeServer2.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-205">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="1ec9e-206">如果你还没有可解析为 XMPP 联合的 DNS SRV 记录, 并且该记录将托管到将托管 XMPP 联合的边缘池, 则必须添加它, 如下例所示。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-206">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="1ec9e-207">此 SRV 记录必须具有端口值5269。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-207">This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="1ec9e-208">验证现在将托管 XMPP 联合身份验证的边缘池是否具有端口5269在外部打开。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-208">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="1ec9e-209">在边缘池中的所有边缘服务器上启动服务, 现在将托管 XMPP 联合身份验证:</span><span class="sxs-lookup"><span data-stu-id="1ec9e-209">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a><span data-ttu-id="1ec9e-210">故障回复用于 Skype for Business 服务器联盟或 XMPP 联合身份验证的边缘池</span><span class="sxs-lookup"><span data-stu-id="1ec9e-210">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span> 

<span data-ttu-id="1ec9e-211">在将用于托管联合身份验证的边缘池重新联机后, 请使用此过程来故障回复 Skype for Business Server 联合身份验证路由和/或 XMPP 联盟路由, 以再次使用此还原的 Edge 池。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-211">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Skype for Business Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

1.  <span data-ttu-id="1ec9e-212">在现在再次可用的 Edge 池中, 启动 Edge 服务。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-212">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="1ec9e-213">如果你希望恢复 Skype for business Server 联合身份验证路由以使用还原的边缘服务器, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="1ec9e-213">If you want to fail back the Skype for Business Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="1ec9e-214">在前端服务器上, 打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-214">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="1ec9e-215">展开 "**边缘池**", 然后右键单击当前为联盟配置的边缘服务器或边缘服务器池。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-215">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="1ec9e-216">选择 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-216">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="1ec9e-217">在 "**编辑属性**" 下的 "**常规**" 下, 清除 "**为此边缘池启用联盟 (端口 5061)**"。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-217">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="1ec9e-218">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-218">Click **OK**.</span></span>
    
      - <span data-ttu-id="1ec9e-219">展开 "**边缘池**", 然后右键单击要用于联盟的原始边缘服务器或边缘服务器池。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-219">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="1ec9e-220">选择 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-220">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="1ec9e-221">在 "**常规**" 下的 "**编辑属性**" 下, 选择 "**为此边缘池启用联盟 (端口 5061)**"。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-221">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="1ec9e-222">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-222">Click **OK**.</span></span>
    
      - <span data-ttu-id="1ec9e-223">单击 "**操作**", 选择 "**拓扑**", 选择 "**发布**"。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-223">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="1ec9e-224">当系统提示**发布拓扑**时, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-224">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="1ec9e-225">发布完成后, 单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-225">When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="1ec9e-226">在边缘服务器上, 打开 "Skype for Business 服务器部署" 向导。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-226">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="1ec9e-227">单击 "**安装或更新 skype for Business 服务器系统**", 然后单击 "**设置" 或 "删除 Skype For business 服务器组件**"。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-227">Click **Install or Update Skype for Business Server System**, then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="1ec9e-228">再次单击 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-228">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="1ec9e-229">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-229">Click **Next**.</span></span> <span data-ttu-id="1ec9e-230">"摘要" 屏幕将显示执行时的操作。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-230">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="1ec9e-231">部署完成后, 单击 "**查看日志**" 以查看可用的日志文件。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-231">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="1ec9e-232">单击 "**完成**" 以完成部署。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-232">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="1ec9e-233">如果想要恢复 XMPP 联盟路由以使用还原的边缘服务器, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="1ec9e-233">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="1ec9e-234">运行以下 cmdlet 以将 XMPP 联盟路由 repoint 到边缘池, 该池现在将托管 XMPP 联合身份验证 (在此示例中, EdgeServer1):</span><span class="sxs-lookup"><span data-stu-id="1ec9e-234">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="1ec9e-235">在此示例中, Site1 是包含边缘池的网站, 它现在将托管 XMPP 联合路由, EdgeServer1.contoso.com 是该池中的边缘服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-235">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="1ec9e-236">如果你还没有可解析为 XMPP 联合的 DNS SRV 记录, 并且该记录将托管到将托管 XMPP 联合的边缘池, 则必须添加它, 如下例所示。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-236">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="1ec9e-237">此 SRV 记录必须具有端口值5269。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-237">This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="1ec9e-238">在外部 DNS 服务器上, 将 XMPP 联合的 DNS A 记录更改为指向 EdgeServer2.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-238">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="1ec9e-239">验证现在将托管 XMPP 联合身份验证的边缘池是否具有端口5269在外部打开。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-239">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="1ec9e-240">如果前端池仍在包含发生故障且已还原的边缘池的网站中运行, 则应在这些前端池上更新 Web 会议服务和 A/V 会议服务, 再次使用其本地网站上的边缘池。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-240">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span>

5.  <span data-ttu-id="1ec9e-241">如果与失败的 Edge 池位于同一站点的前端池也失败, 您现在可以使用 Invoke-CsPoolFailback 来故障回复前端池。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-241">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="1ec9e-242">更改与前端池关联的边缘池</span><span class="sxs-lookup"><span data-stu-id="1ec9e-242">Change the Edge pool associated with a Front End pool</span></span>

<span data-ttu-id="1ec9e-243">如果边缘池已关闭, 但同一网站上的前端池仍在运行, 则需要将前端池设置为在其他网站上使用边缘池, 直到还原失败的边缘池。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-243">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

1.  <span data-ttu-id="1ec9e-244">在拓扑生成器中, 导航到需要更改的前端池的名称。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-244">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="1ec9e-245">右键单击该池, 然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-245">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="1ec9e-246">在 "**关联**" 部分中的 "**关联 Edge 池 (对于媒体组件)**" 下, 使用下拉框选择要与之关联的 "前端" 池的边缘池。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-246">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="1ec9e-247">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="1ec9e-247">Click **OK**.</span></span>
