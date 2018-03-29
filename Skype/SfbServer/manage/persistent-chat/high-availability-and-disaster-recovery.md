---
title: 在 Skype for Business Server 2015 中管理持久聊天服务器的高可用性和灾难恢复
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 摘要： 了解如何管理业务服务器 2015年持久聊天服务器的高可用性和灾难恢复 Skype。
ms.openlocfilehash: 8bc80ff6a38238b81b658a7f4d9620dc3a56b9be
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="78f20-103">在 Skype for Business Server 2015 中管理持久聊天服务器的高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="78f20-103">Manage high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="78f20-104">**摘要：**了解如何管理业务服务器 2015年持久聊天服务器的高可用性和灾难恢复 Skype。</span><span class="sxs-lookup"><span data-stu-id="78f20-104">**Summary:** Learn how to manage Persistent Chat Server high availability and disaster recovery in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="78f20-105">本主题介绍如何进行故障转移和故障恢复持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="78f20-105">This topic describes how to fail over and fail back Persistent Chat Server.</span></span> <span data-ttu-id="78f20-106">在阅读本主题之前, 请务必阅读中对 Skype 的持久聊天服务器[实现高可用性和业务服务器 2015年的 Skype 的持久聊天服务器的灾难恢复计划](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)和[配置高可用性和灾难恢复商业服务器 2015年](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="78f20-106">Before reading this topic, be sure to read [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) and [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
## <a name="fail-over-persistent-chat-server"></a><span data-ttu-id="78f20-107">持久的聊天服务器故障转移</span><span class="sxs-lookup"><span data-stu-id="78f20-107">Fail over Persistent Chat Server</span></span>

<span data-ttu-id="78f20-108">持久的聊天服务器的故障切换可主要是一个手动过程。</span><span class="sxs-lookup"><span data-stu-id="78f20-108">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>
  
<span data-ttu-id="78f20-109">故障转移过程是基于假设从属数据中心都已启动并正在运行，但主要的持久聊天数据库所在的持久聊天服务器服务完全不可用，包括下列：</span><span class="sxs-lookup"><span data-stu-id="78f20-109">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>
  
- <span data-ttu-id="78f20-110">持续聊天服务器的主数据库和镜像数据库持久性的聊天服务器都已关闭。</span><span class="sxs-lookup"><span data-stu-id="78f20-110">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>
    
- <span data-ttu-id="78f20-111">Skype 的业务服务器前端服务器已关闭。</span><span class="sxs-lookup"><span data-stu-id="78f20-111">Skype for Business Server Front End Server is down.</span></span>
    
<span data-ttu-id="78f20-112">该过程主要包含两个基本步骤：</span><span class="sxs-lookup"><span data-stu-id="78f20-112">The procedure is based on two basic steps:</span></span>
  
- <span data-ttu-id="78f20-113">恢复主持久聊天数据库 (mgc)。</span><span class="sxs-lookup"><span data-stu-id="78f20-113">Recover the primary Persistent Chat database (mgc).</span></span>
    
- <span data-ttu-id="78f20-114">建立新的主数据库的镜像。</span><span class="sxs-lookup"><span data-stu-id="78f20-114">Establish mirroring for the new primary database.</span></span>
    
<span data-ttu-id="78f20-115">持续聊天的法规遵从性数据库 (mgccomp) 不被故障切换。</span><span class="sxs-lookup"><span data-stu-id="78f20-115">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="78f20-116">此数据库的内容具有临时性并将在合规性适配器处理数据时被清除。</span><span class="sxs-lookup"><span data-stu-id="78f20-116">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="78f20-117">它是您的责任，作为持久聊天管理员，来正确管理适配器输出，以避免数据丢失。</span><span class="sxs-lookup"><span data-stu-id="78f20-117">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>
  
<span data-ttu-id="78f20-118">对持久聊天服务器进行故障转移：</span><span class="sxs-lookup"><span data-stu-id="78f20-118">To fail over Persistent Chat Server:</span></span>
  
1. <span data-ttu-id="78f20-119">删除日志传送从持久聊天服务器备份日志传送的数据库。</span><span class="sxs-lookup"><span data-stu-id="78f20-119">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
  - <span data-ttu-id="78f20-120">使用 SQL Server 管理 Studio，连接到数据库实例的持久聊天服务器备份 mgc 数据库所在的位置。</span><span class="sxs-lookup"><span data-stu-id="78f20-120">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
  - <span data-ttu-id="78f20-121">打开主数据库的查询窗口。</span><span class="sxs-lookup"><span data-stu-id="78f20-121">Open a query window to the master database.</span></span>
    
  - <span data-ttu-id="78f20-122">使用以下命令取消日志传送：</span><span class="sxs-lookup"><span data-stu-id="78f20-122">Use the following command to drop log shipping:</span></span>
    
  ```
  exec sp_delete_log_shipping_secondary_database mgc
  ```

2. <span data-ttu-id="78f20-123">从备份共享将任何未复制的备份文件复制到备份服务器的复制目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="78f20-123">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>
    
3. <span data-ttu-id="78f20-124">按顺序将任何未应用的事务日志备份应用到辅助数据库。</span><span class="sxs-lookup"><span data-stu-id="78f20-124">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="78f20-125">有关详细信息，请参阅[如何： 在应用事务日志备份 (事务处理 SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428)。</span><span class="sxs-lookup"><span data-stu-id="78f20-125">For details, see [How to: Apply a Transaction Log Backup (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span></span>
    
4. <span data-ttu-id="78f20-p104">使备份 mgc 数据库联机。使用在步骤 1b 中打开的查询窗口，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="78f20-p104">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
  - <span data-ttu-id="78f20-128">如果包含以下项，将断开与 mgc 数据库的所有连接：</span><span class="sxs-lookup"><span data-stu-id="78f20-128">End all connections to the mgc database, if there are any:</span></span>
    
  - <span data-ttu-id="78f20-129">**exec sp_who2**，用于识别与 mgc 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="78f20-129">**exec sp_who2** to identify connections to the mgc database.</span></span>
    
  - <span data-ttu-id="78f20-130">**kill \<spid\>**来结束这些连接。</span><span class="sxs-lookup"><span data-stu-id="78f20-130">**kill \<spid\>** to end these connections.</span></span>
    
  - <span data-ttu-id="78f20-131">使数据库联机：</span><span class="sxs-lookup"><span data-stu-id="78f20-131">Bring the database online:</span></span>
    
  - <span data-ttu-id="78f20-132">**通过恢复还原数据库 mgc**。</span><span class="sxs-lookup"><span data-stu-id="78f20-132">**restore database mgc with recovery**.</span></span>
    
5. <span data-ttu-id="78f20-133">在业务服务器管理外壳的 Skype，使用命令**集 CsPersistentChatState-标识"服务： atl-cs-001.litwareinc.com"-PoolState FailedOver**故障转移到 mgc 备份数据库。</span><span class="sxs-lookup"><span data-stu-id="78f20-133">In Skype for Business Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="78f20-134">确保用您的“持久聊天”池的完全限定的域名替换 atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="78f20-134">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="78f20-135">mgc 备份数据库现在充当主数据库。</span><span class="sxs-lookup"><span data-stu-id="78f20-135">The mgc backup database now serves as the primary database.</span></span>
    
6. <span data-ttu-id="78f20-136">在业务服务器管理外壳的 Skype，使用**安装 CsMirrorDatabase** cmdlet 建立高可用性镜像正在充当主数据库的备份数据库。</span><span class="sxs-lookup"><span data-stu-id="78f20-136">In Skype for Business Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="78f20-137">使用备份数据库实例作为主数据库并使用备份镜像数据库实例作为镜像实例。</span><span class="sxs-lookup"><span data-stu-id="78f20-137">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="78f20-138">此镜像与最初在安装期间为主数据库配置的镜像不同。</span><span class="sxs-lookup"><span data-stu-id="78f20-138">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span>
    
7. <span data-ttu-id="78f20-139">设置活动持久聊天服务器的服务器。</span><span class="sxs-lookup"><span data-stu-id="78f20-139">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="78f20-140">从业务服务器管理外壳的 Skype，使用**一组 CsPersistentChatActiveServer** cmdlet 设置活动服务器的列表。</span><span class="sxs-lookup"><span data-stu-id="78f20-140">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="78f20-141">所有活动服务器必须都与新主数据库位于同一数据中心中，或位于与数据库之间存在低延迟/高带宽连接的数据中心中。</span><span class="sxs-lookup"><span data-stu-id="78f20-141">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
    <span data-ttu-id="78f20-142">在这种情况下，从持久聊天服务器的主数据库故障转移到持久聊天服务器备份数据库已成功完成。</span><span class="sxs-lookup"><span data-stu-id="78f20-142">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>
    
## <a name="fail-back-persistent-chat-server"></a><span data-ttu-id="78f20-143">故障恢复持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="78f20-143">Fail back Persistent Chat Server</span></span>

<span data-ttu-id="78f20-144">此步骤概述从持久聊天服务器故障时，恢复和重建从主数据中心的操作所必需的步骤。</span><span class="sxs-lookup"><span data-stu-id="78f20-144">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>
  
<span data-ttu-id="78f20-145">持久的聊天服务器发生故障，在主数据中心发生完全停电，并且主和镜像数据库变得不可用。</span><span class="sxs-lookup"><span data-stu-id="78f20-145">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="78f20-146">主数据中心将故障转移到备份服务器。</span><span class="sxs-lookup"><span data-stu-id="78f20-146">The primary data center fails over to the backup server.</span></span>
  
<span data-ttu-id="78f20-147">以下过程在备份主数据中心并重新生成服务器后还原正常操作。</span><span class="sxs-lookup"><span data-stu-id="78f20-147">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="78f20-148">此过程假定主数据中心已经从总的停机中恢复并且，mgc 数据库和 mgccomp 数据库已重新构建和重新安装通过使用拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="78f20-148">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>
  
<span data-ttu-id="78f20-149">该过程还假定在故障转移期间未部署新镜像和备份服务器，并且唯一部署的服务器是故障转移持久聊天服务器中之前定义的备份服务器及其镜像服务器。</span><span class="sxs-lookup"><span data-stu-id="78f20-149">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in Fail over Persistent Chat Server previously.</span></span>
  
<span data-ttu-id="78f20-150">这些步骤旨在恢复配置在导致从主服务器故障转移到备份服务器的灾难发生之前的状态。</span><span class="sxs-lookup"><span data-stu-id="78f20-150">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>
  
1. <span data-ttu-id="78f20-151">通过**设置 CsPersistentChatActiveServer** cmdlet 从 Skype 业务服务器管理外壳程序清除持久聊天活动服务器列表中的所有服务器。</span><span class="sxs-lookup"><span data-stu-id="78f20-151">Clear all servers from the Persistent Chat Server Active Server list by using the **Set-CsPersistentChatActiveServer** cmdlet from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="78f20-152">这将停止所有持久聊天服务器回切期间对 mgc 数据库和 mgccomp 数据库连接。</span><span class="sxs-lookup"><span data-stu-id="78f20-152">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="78f20-153">辅助数据库上的 SQL Server 代理持久聊天服务器后端服务器应特权帐户下运行。</span><span class="sxs-lookup"><span data-stu-id="78f20-153">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="78f20-154">尤其需要指出的是，该帐户必须具有以下权限：</span><span class="sxs-lookup"><span data-stu-id="78f20-154">Specifically, the account must include:</span></span> 
  
   - <span data-ttu-id="78f20-155">对于放置备份的网络共享的读取权限。</span><span class="sxs-lookup"><span data-stu-id="78f20-155">Read access to the network share that backups are being placed in.</span></span>
    
   - <span data-ttu-id="78f20-156">对于备份将复制到的特定本地目录的写入权限。</span><span class="sxs-lookup"><span data-stu-id="78f20-156">Write access to the specific local directory that the backups are being copied to.</span></span>
    
2. <span data-ttu-id="78f20-157">在备份 mgc 数据库上禁用镜像：</span><span class="sxs-lookup"><span data-stu-id="78f20-157">Disable mirroring on the backup mgc database:</span></span>
    
   - <span data-ttu-id="78f20-158">使用 SQL Server 管理 Studio，连接到备份 mgc 实例。</span><span class="sxs-lookup"><span data-stu-id="78f20-158">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="78f20-159">右键单击 mgc 数据库，指向“**任务**”，然后单击“**镜像**”。</span><span class="sxs-lookup"><span data-stu-id="78f20-159">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
   - <span data-ttu-id="78f20-160">单击“**取消镜像**”。</span><span class="sxs-lookup"><span data-stu-id="78f20-160">Click **Remove Mirroring**.</span></span>
    
   - <span data-ttu-id="78f20-161">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="78f20-161">Click **OK**.</span></span>
    
   - <span data-ttu-id="78f20-162">对 mgccomp 数据库执行相同步骤。</span><span class="sxs-lookup"><span data-stu-id="78f20-162">Perform the same steps with the mgccomp database.</span></span>
    
3. <span data-ttu-id="78f20-163">备份 mgc 数据库，使其可以还原为新主数据库：</span><span class="sxs-lookup"><span data-stu-id="78f20-163">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
   - <span data-ttu-id="78f20-164">使用 SQL Server 管理 Studio，连接到备份 mgc 实例。</span><span class="sxs-lookup"><span data-stu-id="78f20-164">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="78f20-p112">右键单击 mgc 数据库，指向“**任务**”，然后单击“**备份**”。随即将显示“**备份数据库**”对话框。</span><span class="sxs-lookup"><span data-stu-id="78f20-p112">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="78f20-167">在“**备份类型**”中，选择“**完全**”。</span><span class="sxs-lookup"><span data-stu-id="78f20-167">In **Backup type**, select **Full**.</span></span>
    
   - <span data-ttu-id="78f20-168">对于“**备份组件**”，请单击“**数据库**”。</span><span class="sxs-lookup"><span data-stu-id="78f20-168">For **Backup component**, click **Database**.</span></span>
    
   - <span data-ttu-id="78f20-169">接受“**名称**”中建议的默认备份集名称，或为备份集输入不同名称。</span><span class="sxs-lookup"><span data-stu-id="78f20-169">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
   -  <span data-ttu-id="78f20-170">*\<可选\>* 在**说明**中，输入备份集的描述。</span><span class="sxs-lookup"><span data-stu-id="78f20-170">*\<Optional\>*  In **Description**, enter a description of the backup set.</span></span>
    
   - <span data-ttu-id="78f20-171">从目标列表中删除默认备份位置。</span><span class="sxs-lookup"><span data-stu-id="78f20-171">Remove the default backup location from the destination list.</span></span>
    
   - <span data-ttu-id="78f20-p113">使用您建立用于日志传送的共享位置的路径向列表中添加文件。主数据库和备份数据库均可使用此路径。</span><span class="sxs-lookup"><span data-stu-id="78f20-p113">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
   - <span data-ttu-id="78f20-174">单击“**确定**”关闭对话框并开始备份过程。</span><span class="sxs-lookup"><span data-stu-id="78f20-174">Click **OK** to close the dialog box and begin the backup process.</span></span>
    
4. <span data-ttu-id="78f20-175">使用上一步中创建的备份数据库还原主数据库。</span><span class="sxs-lookup"><span data-stu-id="78f20-175">Restore the primary database by using the backup database created in the previous step.</span></span>
    
   - <span data-ttu-id="78f20-176">使用 SQL Server 管理 Studio，连接到主 mgc 实例。</span><span class="sxs-lookup"><span data-stu-id="78f20-176">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
   - <span data-ttu-id="78f20-p114">右键单击 mgc 数据库，指向“**任务**”，指向“**还原**”，然后单击“**数据库**”。随即会显示“**还原数据库**”对话框。</span><span class="sxs-lookup"><span data-stu-id="78f20-p114">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="78f20-179">选择“**自设备**”。</span><span class="sxs-lookup"><span data-stu-id="78f20-179">Select **From Device**.</span></span>
    
   - <span data-ttu-id="78f20-p115">单击浏览按钮，将打开“**指定备份**”对话框。在“**备份媒体**”中，选择“**文件**”。单击“**添加**”，选择您在步骤 3 中创建的备份文件，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="78f20-p115">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
   - <span data-ttu-id="78f20-183">在“**选择用于还原的备份集**”中，选择备份。</span><span class="sxs-lookup"><span data-stu-id="78f20-183">In **Select the backup sets to restore**, select the backup.</span></span>
    
   - <span data-ttu-id="78f20-184">在“**选择页**”窗格中单击“**选项**”。</span><span class="sxs-lookup"><span data-stu-id="78f20-184">Click **Options** in the **Select a page** pane.</span></span>
    
   - <span data-ttu-id="78f20-185">在“**还原选项**”中，选择“**覆盖现有数据库**”。</span><span class="sxs-lookup"><span data-stu-id="78f20-185">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
   - <span data-ttu-id="78f20-186">在“**恢复状态**”中，选择“**使数据库处于可以使用的状态**”。</span><span class="sxs-lookup"><span data-stu-id="78f20-186">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
   - <span data-ttu-id="78f20-187">单击“**确定**”开始还原过程。</span><span class="sxs-lookup"><span data-stu-id="78f20-187">Click **OK** to begin the restoration process.</span></span>
    
5. <span data-ttu-id="78f20-188">主数据库配置 SQL Server 日志传送。</span><span class="sxs-lookup"><span data-stu-id="78f20-188">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="78f20-189">请按照中的过程[配置高可用性和灾难恢复业务服务器 2015年的 Skype 的持久聊天服务器](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)来建立主 mgc 数据库的日志传送。</span><span class="sxs-lookup"><span data-stu-id="78f20-189">Follow the procedures in [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) to establish log shipping for the primary mgc database.</span></span>
    
6. <span data-ttu-id="78f20-190">设置活动持久聊天服务器的服务器。</span><span class="sxs-lookup"><span data-stu-id="78f20-190">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="78f20-191">从业务服务器管理外壳的 Skype，使用**一组 CsPersistentChatActiveServer** cmdlet 设置活动服务器的列表。</span><span class="sxs-lookup"><span data-stu-id="78f20-191">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="78f20-192">所有活动服务器必须都与新主数据库位于同一数据中心中，或位于与数据库之间存在低延迟/高带宽连接的数据中心中。</span><span class="sxs-lookup"><span data-stu-id="78f20-192">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
<span data-ttu-id="78f20-193">若要恢复到正常状态运行下的 Windows PowerShell 命令的池：</span><span class="sxs-lookup"><span data-stu-id="78f20-193">To restore the pool to its normal state run the following Windows PowerShell command:</span></span>
  
```
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

<span data-ttu-id="78f20-194">有关详细信息，请参阅[设置 CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="78f20-194">For more information, see the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet.</span></span>
  

