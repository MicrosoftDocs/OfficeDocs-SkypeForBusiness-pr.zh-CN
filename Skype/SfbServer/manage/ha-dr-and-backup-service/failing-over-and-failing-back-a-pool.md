---
title: 出现故障后超过和失败的池
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: .
ms.openlocfilehash: 23b70817ba75f3a0a6e73cc42a9df9026e17b2d7
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223505"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a><span data-ttu-id="99f38-103">业务服务器失败后超过和失败的 Skype 池中</span><span class="sxs-lookup"><span data-stu-id="99f38-103">Failing over and failing back a pool in Skype for Business Server</span></span> 

<span data-ttu-id="99f38-104">如果单个前端池已失败和需要进行故障转移或经历灾难的池恢复联机，您需要部署恢复常规工作状态，请使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="99f38-104">Use the following procedures if a single Front End pool has failed and needs to be failed over, or the pool that experienced the disaster is back online and you need to restore your deployment to regular working status.</span></span> <span data-ttu-id="99f38-105">此外了解如何进行故障转移和故障回复用于 Skype 业务联盟或 XMPP 联盟的边缘池，或更改与前端池关联的边缘池。</span><span class="sxs-lookup"><span data-stu-id="99f38-105">Also  learn how to fail over and fail back the Edge pool used for Skype for Business federation or XMPP federation, or change the Edge pool associated with a Front End pool.</span></span>

- [<span data-ttu-id="99f38-106">故障转移前端池</span><span class="sxs-lookup"><span data-stu-id="99f38-106">Fail over a Front End pool</span></span>](#fail-over-a-front-end-pool)
- [<span data-ttu-id="99f38-107">故障回复池</span><span class="sxs-lookup"><span data-stu-id="99f38-107">Fail back a pool</span></span>](#fail-back-a-pool)
- [<span data-ttu-id="99f38-108">故障转移用于 Skype Business Server 联盟的边缘池</span><span class="sxs-lookup"><span data-stu-id="99f38-108">Fail over the Edge pool used for Skype for Business Server federation</span></span>](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [<span data-ttu-id="99f38-109">故障转移用于 XMPP 联盟中 Skype 业务服务器的边缘池</span><span class="sxs-lookup"><span data-stu-id="99f38-109">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span>](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [<span data-ttu-id="99f38-110">故障回复用于 Skype Business Server 联盟或 XMPP 联盟的边缘池</span><span class="sxs-lookup"><span data-stu-id="99f38-110">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span>](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [<span data-ttu-id="99f38-111">更改与前端池关联的边缘池</span><span class="sxs-lookup"><span data-stu-id="99f38-111">Change the Edge pool associated with a Front End pool</span></span>](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a><span data-ttu-id="99f38-112">故障转移前端池</span><span class="sxs-lookup"><span data-stu-id="99f38-112">Fail over a Front End pool</span></span>

<span data-ttu-id="99f38-113">在此过程中，Datacenter1 包含 Pool1，和 Pool1 失败。</span><span class="sxs-lookup"><span data-stu-id="99f38-113">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="99f38-114">您要故障转移到 Pool2 位于 Datacenter2。</span><span class="sxs-lookup"><span data-stu-id="99f38-114">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="99f38-115">池故障转移的工时的大多数涉及失败通过中央管理存储中，如果需要。</span><span class="sxs-lookup"><span data-stu-id="99f38-115">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="99f38-116">这是重要，因为中央管理存储的池的用户都将故障转移时必须能够正常运行。</span><span class="sxs-lookup"><span data-stu-id="99f38-116">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="99f38-117">此外，如果前端池失败，但仍在运行该站点的边缘池，您必须知道的边缘池是否为下一个跃点池使用发生故障的池。</span><span class="sxs-lookup"><span data-stu-id="99f38-117">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool.</span></span> <span data-ttu-id="99f38-118">如果是这样，您必须更改要通过发生故障的前端池使用不同的前端池失败前的边缘池。</span><span class="sxs-lookup"><span data-stu-id="99f38-118">If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool.</span></span> <span data-ttu-id="99f38-119">更改下一个跃点设置的方式取决于是否边缘将使用池的同一站点的边缘池，或不同的网站。</span><span class="sxs-lookup"><span data-stu-id="99f38-119">How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="99f38-120">**设置要在同一站点中使用的下一个跃点池的边缘池**</span><span class="sxs-lookup"><span data-stu-id="99f38-120">**To set an Edge pool to use a next hop pool at the same site**</span></span>

1.  <span data-ttu-id="99f38-121">打开拓扑生成器，右键单击边缘池，需要进行更改，然后单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="99f38-121">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="99f38-122">单击**下一个跃点**。</span><span class="sxs-lookup"><span data-stu-id="99f38-122">Click **Next Hop**.</span></span> <span data-ttu-id="99f38-123">从**下一个跃点池：** 列表中，选择现在将作为下一个跃点池的池。</span><span class="sxs-lookup"><span data-stu-id="99f38-123">From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="99f38-124">单击**确定**，然后发布更改。</span><span class="sxs-lookup"><span data-stu-id="99f38-124">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="99f38-125">**设置边缘池用于下一个跃点池位于不同站点**</span><span class="sxs-lookup"><span data-stu-id="99f38-125">**To set an Edge pool to use a next hop pool at a different site**</span></span>

1.  <span data-ttu-id="99f38-126">打开 Skype 业务 Server 命令行管理程序窗口并键入以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="99f38-126">Open a Skype for Business Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="99f38-127">**故障转移中灾难的池**</span><span class="sxs-lookup"><span data-stu-id="99f38-127">**To fail over a pool in a disaster**</span></span>

1.  <span data-ttu-id="99f38-128">找到哪个池是中央管理服务器的主机，通过在 Pool2 的前端服务器上键入以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="99f38-128">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="99f38-129">此 cmdlet 显示哪个池当前承载中央管理服务器的结果。</span><span class="sxs-lookup"><span data-stu-id="99f38-129">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="99f38-130">此过程的其余部分，此池被称为 CMS\_池。</span><span class="sxs-lookup"><span data-stu-id="99f38-130">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="99f38-131">使用拓扑生成器来查找业务 Server 上对 CMS 运行 Skype 版\_池。</span><span class="sxs-lookup"><span data-stu-id="99f38-131">Use Topology Builder to find the version of Skype for Business Server running on the CMS\_Pool.</span></span> <span data-ttu-id="99f38-132">如果它业务服务器运行 Skype，使用以下 cmdlet 来查找池 1 的备份池。</span><span class="sxs-lookup"><span data-stu-id="99f38-132">If it is running Skype for Business Server, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="99f38-133">让备份\_池成为备份池。</span><span class="sxs-lookup"><span data-stu-id="99f38-133">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="99f38-134">检查以下 cmdlet 的中央管理存储的状态：</span><span class="sxs-lookup"><span data-stu-id="99f38-134">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="99f38-135">此 cmdlet 应显示 ActiveMasterFQDN 和 activefiletransferagents 是否指向 CMS FQDN\_池。</span><span class="sxs-lookup"><span data-stu-id="99f38-135">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="99f38-136">它们是否为空，中央管理服务器不可用，您必须故障转移。</span><span class="sxs-lookup"><span data-stu-id="99f38-136">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="99f38-137">如果中央管理存储不可用或中央管理存储在 Pool1 上运行 （即，已失败的池），您必须通过的池故障转移前中央管理服务器。</span><span class="sxs-lookup"><span data-stu-id="99f38-137">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="99f38-138">如果您需要已在运行 Business Server Skype 池中承载中央管理服务器故障转移，请使用此过程的步骤 5 中的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="99f38-138">If you need to fail over the Central Management Server that was hosted on a pool running Skype for Business Server, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="99f38-139">如果您不需要进行故障转移中央管理服务器，请跳过此过程的步骤 7。</span><span class="sxs-lookup"><span data-stu-id="99f38-139">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="99f38-140">故障转移中央管理存储业务服务器运行 Skype 的池上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="99f38-140">To fail over the Central Management store on a pool running Skype for Business Server, do the following:</span></span>
    
      - <span data-ttu-id="99f38-141">首先，检查备份中的后端服务器\_池运行中央管理存储的主体实例，通过键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="99f38-141">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="99f38-142">如果主后端服务器备份中\_池是主体，键入：</span><span class="sxs-lookup"><span data-stu-id="99f38-142">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="99f38-143">如果镜像中备份后端服务器\_池是主体，键入：</span><span class="sxs-lookup"><span data-stu-id="99f38-143">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="99f38-144">验证中央管理服务器故障转移已完成。</span><span class="sxs-lookup"><span data-stu-id="99f38-144">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="99f38-145">键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="99f38-145">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="99f38-146">检查 ActiveMasterFQDN 和 activefiletransferagents 是否指向备份 FQDN\_池。</span><span class="sxs-lookup"><span data-stu-id="99f38-146">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="99f38-147">最后，通过键入以下命令检查所有前端服务器的副本状态：</span><span class="sxs-lookup"><span data-stu-id="99f38-147">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="99f38-148">检查所有副本的值为 True。</span><span class="sxs-lookup"><span data-stu-id="99f38-148">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="99f38-149">跳到步骤 7 中此过程。</span><span class="sxs-lookup"><span data-stu-id="99f38-149">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="99f38-150">在后端服务器的备份上安装中央管理存储\_池。</span><span class="sxs-lookup"><span data-stu-id="99f38-150">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="99f38-151">首先，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="99f38-151">First, run the following command:</span></span>
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="99f38-152">一台前端最终备份服务器上运行下面的命令\_以强制移动中央管理存储的池：</span><span class="sxs-lookup"><span data-stu-id="99f38-152">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="99f38-153">验证移动是否完成：</span><span class="sxs-lookup"><span data-stu-id="99f38-153">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="99f38-154">检查 ActiveMasterFQDN 和 activefiletransferagents 是否指向备份 FQDN\_池。</span><span class="sxs-lookup"><span data-stu-id="99f38-154">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="99f38-155">通过键入以下命令检查所有前端服务器的副本状态：</span><span class="sxs-lookup"><span data-stu-id="99f38-155">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="99f38-156">检查所有副本的值为 True。</span><span class="sxs-lookup"><span data-stu-id="99f38-156">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="99f38-157">中央管理服务器服务安装在前端服务器备份中的其余部分\_池。</span><span class="sxs-lookup"><span data-stu-id="99f38-157">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="99f38-158">为此，请在所有前端服务器上运行以下命令，存储在此过程前面时强制中央管理使用以外的移动：</span><span class="sxs-lookup"><span data-stu-id="99f38-158">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="99f38-159">故障转移到 Pool2 将用户从 Pool1，通过 Skype 业务 Server 命令行管理程序窗口中运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="99f38-159">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Skype for Business Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="99f38-160">因为检查中央管理存储状态所需的此过程前面部分中的步骤不是通用的则仍可能将此 cmdlet 将失败，因为中央管理存储不尚未完全故障转移。</span><span class="sxs-lookup"><span data-stu-id="99f38-160">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="99f38-161">在这种情况下，您必须修复中央管理存储基于您看到的错误消息，然后再次运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="99f38-161">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="99f38-162">如果您看到以下错误消息，然后您需要更改在其他池用作通过池失败前其下一个跃点此站点的边缘池。</span><span class="sxs-lookup"><span data-stu-id="99f38-162">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool.</span></span> <span data-ttu-id="99f38-163">有关详细信息，请参阅本主题的开头的过程。</span><span class="sxs-lookup"><span data-stu-id="99f38-163">For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a><span data-ttu-id="99f38-164">故障回复池</span><span class="sxs-lookup"><span data-stu-id="99f38-164">Fail back a pool</span></span>

<span data-ttu-id="99f38-165">经历灾难的池恢复联机后 (也就是说，Pool1 在本例中)，执行以下步骤来使部署常规工作状态。</span><span class="sxs-lookup"><span data-stu-id="99f38-165">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="99f38-166">请注意，故障回复过程需要几分钟时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="99f38-166">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="99f38-167">作为参考，对于用户数为 20,000 的池而言，预期最多需要 60 分钟。</span><span class="sxs-lookup"><span data-stu-id="99f38-167">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="99f38-168">故障回复的用户最初驻留在 Pool1 中并已故障转移到 Pool2 通过键入以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="99f38-168">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="99f38-169">没有其他步骤是必需的。</span><span class="sxs-lookup"><span data-stu-id="99f38-169">No other steps are necessary.</span></span> <span data-ttu-id="99f38-170">如果您故障转移中央管理服务器，您可以将其置于 Pool2。</span><span class="sxs-lookup"><span data-stu-id="99f38-170">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a><span data-ttu-id="99f38-171">故障转移用于 Skype Business Server 联盟的边缘池</span><span class="sxs-lookup"><span data-stu-id="99f38-171">Fail over the Edge pool used for Skype for Business Server federation</span></span> 

<span data-ttu-id="99f38-172">如果 Skype 了配置 Business Server 联盟的边缘池不可用，则必须更改联合身份验证为使用联合身份验证的其他边缘池以。</span><span class="sxs-lookup"><span data-stu-id="99f38-172">If the Edge pool where you have Skype for Business Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

1.  <span data-ttu-id="99f38-173">在前端服务器上，打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="99f38-173">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="99f38-174">展开**边缘池**，，然后右键单击当前为联盟配置边缘服务器池的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="99f38-174">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="99f38-175">选择**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="99f38-175">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="99f38-176">在**编辑属性**在**常规**下，清除**启用联盟，为此边缘池 (端口 5061)**。</span><span class="sxs-lookup"><span data-stu-id="99f38-176">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="99f38-177">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="99f38-177">Click **OK**.</span></span>

3.  <span data-ttu-id="99f38-178">展开**边缘池**，，然后右键单击要立即使用联盟的边缘服务器或边缘服务器池。</span><span class="sxs-lookup"><span data-stu-id="99f38-178">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="99f38-179">选择**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="99f38-179">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="99f38-180">在**编辑属性**在**常规**下，选择**启用联盟，为此边缘池 (端口 5061)**。</span><span class="sxs-lookup"><span data-stu-id="99f38-180">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="99f38-181">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="99f38-181">Click **OK**.</span></span>

5.  <span data-ttu-id="99f38-182">单击**操作**，选择**拓扑**，选择**发布**。</span><span class="sxs-lookup"><span data-stu-id="99f38-182">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="99f38-183">当提示您在**发布拓扑**，请单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="99f38-183">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="99f38-184">完成发布后，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="99f38-184">When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="99f38-185">在边缘服务器上，打开 Skype 的业务 Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="99f38-185">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="99f38-186">单击**安装或更新 Skype 业务 Server 系统**，然后单击**安装或删除业务服务器组件的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="99f38-186">Click **Install or Update Skype for Business Server System**, and then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="99f38-187">单击**再次运行**。</span><span class="sxs-lookup"><span data-stu-id="99f38-187">Click **Run Again**.</span></span>

7.  <span data-ttu-id="99f38-188">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="99f38-188">Click **Next**.</span></span> <span data-ttu-id="99f38-189">摘要屏幕上将显示操作，为在执行。</span><span class="sxs-lookup"><span data-stu-id="99f38-189">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="99f38-190">完成部署后，单击**查看日志**以查看可用的日志文件。</span><span class="sxs-lookup"><span data-stu-id="99f38-190">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="99f38-191">单击**完成**以完成部署。</span><span class="sxs-lookup"><span data-stu-id="99f38-191">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="99f38-192">如果包含了故障的边缘池的站点包含仍在运行前端服务器，则必须更新的 Web 会议服务和 A / V 会议服务在这些前端池上用于远程边缘池，它是网站仍运行。</span><span class="sxs-lookup"><span data-stu-id="99f38-192">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a><span data-ttu-id="99f38-193">故障转移用于 XMPP 联盟中 Skype 业务服务器的边缘池</span><span class="sxs-lookup"><span data-stu-id="99f38-193">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span> 

<span data-ttu-id="99f38-194">在组织中没有一个指定为池用于 XMPP 联盟的边缘池。</span><span class="sxs-lookup"><span data-stu-id="99f38-194">In your organization, there is one Edge pool designated as the pool to use for XMPP federation.</span></span> <span data-ttu-id="99f38-195">如果此池不可用，您必须先对 XMPP 联盟之前 XMPP 联盟可以再次使用用于其他边缘池。</span><span class="sxs-lookup"><span data-stu-id="99f38-195">If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="99f38-196">当您首次安装边缘池，并启用 XMPP 联盟时，您可以通过设置的所有 XMPP 联盟，而不是只需一个边缘池的外部 DNS SRV 记录简化灾难恢复过程。</span><span class="sxs-lookup"><span data-stu-id="99f38-196">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="99f38-197">每个 SRV 记录必须具有不同的优先级设置。</span><span class="sxs-lookup"><span data-stu-id="99f38-197">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="99f38-198">所有 XMPP 联盟流量都遍历具有最高优先级的 SRV 记录的池。</span><span class="sxs-lookup"><span data-stu-id="99f38-198">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> 

<span data-ttu-id="99f38-199">在下面的过程中，EdgePool1 是最初承载 XMPP 联盟的池，EdgePool2 是现在承载 XMPP 联盟的池。</span><span class="sxs-lookup"><span data-stu-id="99f38-199">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="99f38-200">故障转移用于 XMPP 联盟的边缘池</span><span class="sxs-lookup"><span data-stu-id="99f38-200">To fail over the Edge pool used for XMPP federation</span></span>

1.  <span data-ttu-id="99f38-201">如果您已没有其他边缘池 （除了一个其当前已关闭） 部署，部署该池。</span><span class="sxs-lookup"><span data-stu-id="99f38-201">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> 

2.  <span data-ttu-id="99f38-202">在现在承载 XMPP 联盟 (EdgePool2) 的新边缘池的每台边缘服务器，运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="99f38-202">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="99f38-203">运行以下 cmdlet 以重建 XMPP 联盟路由指向 EdgePool2:</span><span class="sxs-lookup"><span data-stu-id="99f38-203">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="99f38-204">本示例中，Site2 是包含现在承载 XMPP 联盟路由的边缘池的站点和 EdgeServer2.contoso.com 为此池中的边缘服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="99f38-204">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="99f38-205">在外部 DNS 服务器上，更改为指向 EdgeServer2.contoso.com 的 XMPP 联盟的 DNS A 记录。</span><span class="sxs-lookup"><span data-stu-id="99f38-205">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="99f38-206">如果您已没有 XMPP 联盟，它解析为现在承载 XMPP 联盟的边缘池的 DNS SRV 记录，您必须添加，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="99f38-206">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="99f38-207">此 SRV 记录必须 5269 端口值。</span><span class="sxs-lookup"><span data-stu-id="99f38-207">This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="99f38-208">确认现在承载 XMPP 联盟的边缘池已打开的端口 5269 外部。</span><span class="sxs-lookup"><span data-stu-id="99f38-208">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="99f38-209">在现在承载 XMPP 联盟的边缘池的所有边缘服务器上启动服务：</span><span class="sxs-lookup"><span data-stu-id="99f38-209">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a><span data-ttu-id="99f38-210">故障回复用于 Skype Business Server 联盟或 XMPP 联盟的边缘池</span><span class="sxs-lookup"><span data-stu-id="99f38-210">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span> 

<span data-ttu-id="99f38-211">后失败的边缘池用于主机联盟已经联机后，使用此过程可为 Business Server 联盟路由和/或 XMPP 联盟路由 Skype 要再次将此已还原的边缘池进行故障回复。</span><span class="sxs-lookup"><span data-stu-id="99f38-211">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Skype for Business Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

1.  <span data-ttu-id="99f38-212">在边缘池中，现在可再次，启动边缘服务。</span><span class="sxs-lookup"><span data-stu-id="99f38-212">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="99f38-213">如果您想要进行故障回复 Business Server 联盟路由的 Skype，以使用恢复的边缘服务器，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="99f38-213">If you want to fail back the Skype for Business Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="99f38-214">在前端服务器上，打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="99f38-214">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="99f38-215">展开**边缘池**，然后右键单击当前为联盟配置边缘服务器池的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="99f38-215">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="99f38-216">选择**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="99f38-216">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="99f38-217">在**编辑属性**在**常规**下，清除**启用联盟，为此边缘池 (端口 5061)**。</span><span class="sxs-lookup"><span data-stu-id="99f38-217">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="99f38-218">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="99f38-218">Click **OK**.</span></span>
    
      - <span data-ttu-id="99f38-219">展开**边缘池**，然后右键单击要再次使用联合身份验证的原始边缘服务器或边缘服务器池。</span><span class="sxs-lookup"><span data-stu-id="99f38-219">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="99f38-220">选择**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="99f38-220">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="99f38-221">在**编辑属性**在**常规**下，选择**启用联盟，为此边缘池 (端口 5061)**。</span><span class="sxs-lookup"><span data-stu-id="99f38-221">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="99f38-222">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="99f38-222">Click **OK**.</span></span>
    
      - <span data-ttu-id="99f38-223">单击**操作**，选择**拓扑**，选择**发布**。</span><span class="sxs-lookup"><span data-stu-id="99f38-223">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="99f38-224">当提示您在**发布拓扑**，请单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="99f38-224">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="99f38-225">完成发布后，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="99f38-225">When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="99f38-226">在边缘服务器上，打开 Skype 的业务 Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="99f38-226">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="99f38-227">单击**安装或更新 Skype 业务 Server 系统**，然后单击**安装或删除的 Skype 业务服务器组件**。</span><span class="sxs-lookup"><span data-stu-id="99f38-227">Click **Install or Update Skype for Business Server System**, then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="99f38-228">单击**再次运行**。</span><span class="sxs-lookup"><span data-stu-id="99f38-228">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="99f38-229">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="99f38-229">Click **Next**.</span></span> <span data-ttu-id="99f38-230">摘要屏幕上将显示操作，为在执行。</span><span class="sxs-lookup"><span data-stu-id="99f38-230">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="99f38-231">完成部署后，单击**查看日志**以查看可用的日志文件。</span><span class="sxs-lookup"><span data-stu-id="99f38-231">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="99f38-232">单击**完成**以完成部署。</span><span class="sxs-lookup"><span data-stu-id="99f38-232">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="99f38-233">如果您想要进行故障回复 XMPP 联盟路由以使用恢复的边缘服务器，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="99f38-233">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="99f38-234">运行以下 cmdlet 以重建 XMPP 联盟路由到的边缘池，现在承载 XMPP 联盟 （在本例中为 EdgeServer1）：</span><span class="sxs-lookup"><span data-stu-id="99f38-234">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="99f38-235">本示例中，Site1 是包含现在承载 XMPP 联盟路由的边缘池的站点和 EdgeServer1.contoso.com 为此池中的边缘服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="99f38-235">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="99f38-236">如果您已没有 XMPP 联盟，它解析为现在承载 XMPP 联盟的边缘池的 DNS SRV 记录，您必须添加，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="99f38-236">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="99f38-237">此 SRV 记录必须 5269 端口值。</span><span class="sxs-lookup"><span data-stu-id="99f38-237">This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="99f38-238">在外部 DNS 服务器上，更改为指向 EdgeServer2.contoso.com 的 XMPP 联盟的 DNS A 记录。</span><span class="sxs-lookup"><span data-stu-id="99f38-238">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="99f38-239">确认现在承载 XMPP 联盟的边缘池已打开的端口 5269 外部。</span><span class="sxs-lookup"><span data-stu-id="99f38-239">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="99f38-240">如果前端池保持运行包含失败和已恢复的边缘池的站点，则应更新的 Web 会议服务和 A / V 会议服务在这些前端池再次使用其本地站点的边缘池。</span><span class="sxs-lookup"><span data-stu-id="99f38-240">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span>

5.  <span data-ttu-id="99f38-241">如果为了故障边缘池的同一站点上的前端池也出现故障，您现在可以使用 Invoke – CsPoolFailback 故障回复的前端池。</span><span class="sxs-lookup"><span data-stu-id="99f38-241">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="99f38-242">更改与前端池关联的边缘池</span><span class="sxs-lookup"><span data-stu-id="99f38-242">Change the Edge pool associated with a Front End pool</span></span>

<span data-ttu-id="99f38-243">如果边缘池不可用，但在同一站点的前端池仍在运行，您需要设置要使用不同站点的边缘池，直到还原了故障的边缘池的前端池。</span><span class="sxs-lookup"><span data-stu-id="99f38-243">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

1.  <span data-ttu-id="99f38-244">在拓扑生成器中，导航到需要更改的前端池的名称。</span><span class="sxs-lookup"><span data-stu-id="99f38-244">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="99f38-245">右键单击池，，，然后单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="99f38-245">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="99f38-246">在**关联**部分的**关联边缘池 （用于媒体组件）** 下,，使用下拉框选择要与此前端池关联的边缘池。</span><span class="sxs-lookup"><span data-stu-id="99f38-246">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="99f38-247">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="99f38-247">Click **OK**.</span></span>