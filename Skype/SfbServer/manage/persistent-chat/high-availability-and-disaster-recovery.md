---
title: 在 Skype for Business Server 2015 中管理持久聊天服务器的高可用性和灾难恢复
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 摘要：了解如何在 Skype for Business Server 2015 中管理持久聊天服务器高可用性和灾难恢复。
ms.openlocfilehash: 4fb3a38fadf2a8a063715e389718859dcc7ddbdd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122406"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="66275-103">在 Skype for Business Server 2015 中管理持久聊天服务器的高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="66275-103">Manage high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="66275-104">**摘要：** 了解如何在 Skype for Business Server 2015 中管理持久聊天服务器的高可用性和灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="66275-104">**Summary:** Learn how to manage Persistent Chat Server high availability and disaster recovery in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="66275-105">本主题介绍如何对持久聊天服务器进行故障转移和故障回复。</span><span class="sxs-lookup"><span data-stu-id="66275-105">This topic describes how to fail over and fail back Persistent Chat Server.</span></span> <span data-ttu-id="66275-106">在阅读本主题之前，请务必阅读 Plan [for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)和[Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015。](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)</span><span class="sxs-lookup"><span data-stu-id="66275-106">Before reading this topic, be sure to read [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) and [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>

> [!NOTE]
> <span data-ttu-id="66275-107">持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="66275-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="66275-108">Teams 中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="66275-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="66275-109">有关详细信息，请参阅 Microsoft Teams 升级 [入门](/microsoftteams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="66275-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="66275-110">如果需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="66275-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="fail-over-persistent-chat-server"></a><span data-ttu-id="66275-111">故障转移持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="66275-111">Fail over Persistent Chat Server</span></span>

<span data-ttu-id="66275-112">持久聊天服务器的故障转移主要是一个手动过程。</span><span class="sxs-lookup"><span data-stu-id="66275-112">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>
  
<span data-ttu-id="66275-113">故障转移过程基于以下假设：辅助数据中心已启动且正在运行，但持久聊天数据库所在的持久聊天服务器服务完全不可用，其中包括：</span><span class="sxs-lookup"><span data-stu-id="66275-113">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>
  
- <span data-ttu-id="66275-114">持久聊天服务器主数据库和持久聊天服务器镜像数据库已关闭。</span><span class="sxs-lookup"><span data-stu-id="66275-114">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>
    
- <span data-ttu-id="66275-115">Skype for Business Server 前端服务器已关闭。</span><span class="sxs-lookup"><span data-stu-id="66275-115">Skype for Business Server Front End Server is down.</span></span>
    
<span data-ttu-id="66275-116">该过程主要包含两个基本步骤：</span><span class="sxs-lookup"><span data-stu-id="66275-116">The procedure is based on two basic steps:</span></span>
  
- <span data-ttu-id="66275-117">恢复主持久聊天数据库 (mgc) 。</span><span class="sxs-lookup"><span data-stu-id="66275-117">Recover the primary Persistent Chat database (mgc).</span></span>
    
- <span data-ttu-id="66275-118">建立新的主数据库的镜像。</span><span class="sxs-lookup"><span data-stu-id="66275-118">Establish mirroring for the new primary database.</span></span>
    
<span data-ttu-id="66275-119">未进行 (mgccomp) 持久聊天合规性数据库。</span><span class="sxs-lookup"><span data-stu-id="66275-119">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="66275-120">此数据库的内容具有临时性并将在合规性适配器处理数据时被清除。</span><span class="sxs-lookup"><span data-stu-id="66275-120">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="66275-121">作为持久聊天管理员，您有责任正确管理适配器输出以避免数据丢失。</span><span class="sxs-lookup"><span data-stu-id="66275-121">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>
  
<span data-ttu-id="66275-122">对持久聊天服务器进行故障转移：</span><span class="sxs-lookup"><span data-stu-id="66275-122">To fail over Persistent Chat Server:</span></span>
  
1. <span data-ttu-id="66275-123">从持久聊天服务器备份日志发货数据库中删除日志寄送。</span><span class="sxs-lookup"><span data-stu-id="66275-123">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
   - <span data-ttu-id="66275-124">使用 SQL Server Management Studio 连接到持久聊天服务器备份 mgc 数据库所在的数据库实例。</span><span class="sxs-lookup"><span data-stu-id="66275-124">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
   - <span data-ttu-id="66275-125">打开主数据库的查询窗口。</span><span class="sxs-lookup"><span data-stu-id="66275-125">Open a query window to the master database.</span></span>
    
   - <span data-ttu-id="66275-126">使用以下命令取消日志传送：</span><span class="sxs-lookup"><span data-stu-id="66275-126">Use the following command to drop log shipping:</span></span>
    
   ```SQL
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. <span data-ttu-id="66275-127">从备份共享将任何未复制的备份文件复制到备份服务器的复制目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="66275-127">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>
    
3. <span data-ttu-id="66275-128">按顺序将任何未应用的事务日志备份应用到辅助数据库。</span><span class="sxs-lookup"><span data-stu-id="66275-128">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="66275-129">有关详细信息，请参阅 [如何：将事务日志备份 (Transact-SQL) ](/previous-versions/sql/sql-server-2008-r2/ms187607(v=sql.105))。</span><span class="sxs-lookup"><span data-stu-id="66275-129">For details, see [How to: Apply a Transaction Log Backup (Transact-SQL)](/previous-versions/sql/sql-server-2008-r2/ms187607(v=sql.105)).</span></span>
    
4. <span data-ttu-id="66275-p105">使备份 mgc 数据库联机。使用在步骤 1b 中打开的查询窗口，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="66275-p105">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
   - <span data-ttu-id="66275-132">如果包含以下项，将断开与 mgc 数据库的所有连接：</span><span class="sxs-lookup"><span data-stu-id="66275-132">End all connections to the mgc database, if there are any:</span></span>
    
   - <span data-ttu-id="66275-133">**exec sp_who2** 标识与 mgc 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="66275-133">**exec sp_who2** to identify connections to the mgc database.</span></span>
    
   - <span data-ttu-id="66275-134">**kill \<spid\>** 以结束这些连接。</span><span class="sxs-lookup"><span data-stu-id="66275-134">**kill \<spid\>** to end these connections.</span></span>
    
   - <span data-ttu-id="66275-135">使数据库联机：</span><span class="sxs-lookup"><span data-stu-id="66275-135">Bring the database online:</span></span>
    
   - <span data-ttu-id="66275-136">**使用恢复 还原数据库 mgc。**</span><span class="sxs-lookup"><span data-stu-id="66275-136">**restore database mgc with recovery**.</span></span>
    
5. <span data-ttu-id="66275-137">在 Skype for Business Server 命令行管理程序 中，使用 **命令 Set-CsPersistentChatState -Identity "service：atl-cs-001.litwareinc.com" -PoolState FailedOver** 故障转移到 mgc 备份数据库。</span><span class="sxs-lookup"><span data-stu-id="66275-137">In Skype for Business Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="66275-138">请务必将持久聊天池的完全限定域名替换为 atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="66275-138">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="66275-139">mgc 备份数据库现在充当主数据库。</span><span class="sxs-lookup"><span data-stu-id="66275-139">The mgc backup database now serves as the primary database.</span></span>
    
6. <span data-ttu-id="66275-140">在 Skype for Business Server 命令行管理程序 中，使用 **Install-CsMirrorDatabase** cmdlet 为现在用作主数据库的备份数据库建立高可用性镜像。</span><span class="sxs-lookup"><span data-stu-id="66275-140">In Skype for Business Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="66275-141">使用备份数据库实例作为主数据库并使用备份镜像数据库实例作为镜像实例。</span><span class="sxs-lookup"><span data-stu-id="66275-141">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="66275-142">此镜像与最初在安装期间为主数据库配置的镜像不同。</span><span class="sxs-lookup"><span data-stu-id="66275-142">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span>
    
7. <span data-ttu-id="66275-143">设置持久聊天服务器活动服务器。</span><span class="sxs-lookup"><span data-stu-id="66275-143">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="66275-144">从 Skype for Business Server 命令行管理程序，使用 **Set-CsPersistentChatActiveServer** cmdlet 设置活动服务器的列表。</span><span class="sxs-lookup"><span data-stu-id="66275-144">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="66275-145">所有活动服务器都必须与新主数据库位于同一数据中心中，或位于与数据库之间存在低延迟/高带宽连接的数据中心中。</span><span class="sxs-lookup"><span data-stu-id="66275-145">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
    <span data-ttu-id="66275-146">此时，从持久聊天服务器主数据库到持久聊天服务器备份数据库的故障转移将成功完成。</span><span class="sxs-lookup"><span data-stu-id="66275-146">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>
    
## <a name="fail-back-persistent-chat-server"></a><span data-ttu-id="66275-147">对持久聊天服务器进行故障回复</span><span class="sxs-lookup"><span data-stu-id="66275-147">Fail back Persistent Chat Server</span></span>

<span data-ttu-id="66275-148">此过程概述了从持久聊天服务器故障中恢复以及从主数据中心重新建立操作所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="66275-148">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>
  
<span data-ttu-id="66275-149">在持久聊天服务器故障期间，主数据中心完全中断，主数据库和镜像数据库变得不可用。</span><span class="sxs-lookup"><span data-stu-id="66275-149">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="66275-150">主数据中心将故障转移到备份服务器。</span><span class="sxs-lookup"><span data-stu-id="66275-150">The primary data center fails over to the backup server.</span></span>
  
<span data-ttu-id="66275-151">以下过程在备份主数据中心并重新生成服务器后还原正常操作。</span><span class="sxs-lookup"><span data-stu-id="66275-151">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="66275-152">该过程假定主数据中心已从整体中断中恢复，并且 mgc 数据库和 mgccomp 数据库已使用拓扑生成器重新生成和重新安装。</span><span class="sxs-lookup"><span data-stu-id="66275-152">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>
  
<span data-ttu-id="66275-153">该过程还假定在故障转移期间没有部署新的镜像和备份服务器，并且部署的唯一服务器是备份服务器及其镜像服务器，如之前故障转移持久聊天服务器中的定义。</span><span class="sxs-lookup"><span data-stu-id="66275-153">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in Fail over Persistent Chat Server previously.</span></span>
  
<span data-ttu-id="66275-154">这些步骤旨在恢复配置在导致从主服务器故障转移到备份服务器的灾难发生之前的状态。</span><span class="sxs-lookup"><span data-stu-id="66275-154">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>
  
1. <span data-ttu-id="66275-155">使用 Skype for Business Server 命令行管理程序中的 **Set-CsPersistentChatActiveServer** cmdlet 清除持久聊天服务器活动服务器列表中的所有服务器。</span><span class="sxs-lookup"><span data-stu-id="66275-155">Clear all servers from the Persistent Chat Server Active Server list by using the **Set-CsPersistentChatActiveServer** cmdlet from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="66275-156">这将阻止所有持久聊天服务器在故障回复期间连接到 mgc 数据库和 mgccomp 数据库。</span><span class="sxs-lookup"><span data-stu-id="66275-156">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="66275-157">辅助SQL Server持久聊天服务器后端服务器的客户端代理应在特权帐户下运行。</span><span class="sxs-lookup"><span data-stu-id="66275-157">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="66275-158">尤其需要指出的是，该帐户必须具有以下权限：</span><span class="sxs-lookup"><span data-stu-id="66275-158">Specifically, the account must include:</span></span> 
  
   - <span data-ttu-id="66275-159">对于放置备份的网络共享的读取权限。</span><span class="sxs-lookup"><span data-stu-id="66275-159">Read access to the network share that backups are being placed in.</span></span>
    
   - <span data-ttu-id="66275-160">对于备份将复制到的特定本地目录的写入权限。</span><span class="sxs-lookup"><span data-stu-id="66275-160">Write access to the specific local directory that the backups are being copied to.</span></span>
    
2. <span data-ttu-id="66275-161">在备份 mgc 数据库上禁用镜像：</span><span class="sxs-lookup"><span data-stu-id="66275-161">Disable mirroring on the backup mgc database:</span></span>
    
   - <span data-ttu-id="66275-162">使用 SQL Server Management Studio 连接到备份 mgc 实例。</span><span class="sxs-lookup"><span data-stu-id="66275-162">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="66275-163">右键单击 mgc 数据库，指向“任务”，然后单击“镜像”。</span><span class="sxs-lookup"><span data-stu-id="66275-163">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
   - <span data-ttu-id="66275-164">单击“取消镜像”。</span><span class="sxs-lookup"><span data-stu-id="66275-164">Click **Remove Mirroring**.</span></span>
    
   - <span data-ttu-id="66275-165">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="66275-165">Click **OK**.</span></span>
    
   - <span data-ttu-id="66275-166">对 mgccomp 数据库执行相同步骤。</span><span class="sxs-lookup"><span data-stu-id="66275-166">Perform the same steps with the mgccomp database.</span></span>
    
3. <span data-ttu-id="66275-167">备份 mgc 数据库，使其可以还原为新主数据库：</span><span class="sxs-lookup"><span data-stu-id="66275-167">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
   - <span data-ttu-id="66275-168">使用 SQL Server Management Studio 连接到备份 mgc 实例。</span><span class="sxs-lookup"><span data-stu-id="66275-168">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="66275-p113">右键单击 mgc 数据库，指向“任务”，然后单击“备份”。随即将显示“备份数据库”对话框。</span><span class="sxs-lookup"><span data-stu-id="66275-p113">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="66275-171">在“备份类型”中，选择“完全”。</span><span class="sxs-lookup"><span data-stu-id="66275-171">In **Backup type**, select **Full**.</span></span>
    
   - <span data-ttu-id="66275-172">对于“备份组件”，请单击“数据库”。</span><span class="sxs-lookup"><span data-stu-id="66275-172">For **Backup component**, click **Database**.</span></span>
    
   - <span data-ttu-id="66275-173">接受“名称”中建议的默认备份集名称，或为备份集输入不同名称。</span><span class="sxs-lookup"><span data-stu-id="66275-173">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
   -  <span data-ttu-id="66275-174">*\<Optional\>*  在 **"说明**"中，输入备份集的说明。</span><span class="sxs-lookup"><span data-stu-id="66275-174">*\<Optional\>*  In **Description**, enter a description of the backup set.</span></span>
    
   - <span data-ttu-id="66275-175">从目标列表中删除默认备份位置。</span><span class="sxs-lookup"><span data-stu-id="66275-175">Remove the default backup location from the destination list.</span></span>
    
   - <span data-ttu-id="66275-p114">使用您建立用于日志传送的共享位置的路径向列表中添加文件。主数据库和备份数据库均可使用此路径。</span><span class="sxs-lookup"><span data-stu-id="66275-p114">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
   - <span data-ttu-id="66275-178">单击“确定”关闭对话框并开始备份过程。</span><span class="sxs-lookup"><span data-stu-id="66275-178">Click **OK** to close the dialog box and begin the backup process.</span></span>
    
4. <span data-ttu-id="66275-179">使用上一步中创建的备份数据库还原主数据库。</span><span class="sxs-lookup"><span data-stu-id="66275-179">Restore the primary database by using the backup database created in the previous step.</span></span>
    
   - <span data-ttu-id="66275-180">使用 SQL Server Management Studio 连接到主 mgc 实例。</span><span class="sxs-lookup"><span data-stu-id="66275-180">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
   - <span data-ttu-id="66275-p115">右键单击 mgc 数据库，指向“任务”，指向“还原”，然后单击“数据库”。随即会显示“还原数据库”对话框。</span><span class="sxs-lookup"><span data-stu-id="66275-p115">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="66275-183">选择“自设备”。</span><span class="sxs-lookup"><span data-stu-id="66275-183">Select **From Device**.</span></span>
    
   - <span data-ttu-id="66275-p116">单击浏览按钮，将打开“指定备份”对话框。在“备份媒体”中，选择“文件”。单击“添加”，选择您在步骤 3 中创建的备份文件，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="66275-p116">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
   - <span data-ttu-id="66275-187">在“选择用于还原的备份集”中，选择备份。</span><span class="sxs-lookup"><span data-stu-id="66275-187">In **Select the backup sets to restore**, select the backup.</span></span>
    
   - <span data-ttu-id="66275-188">在“选择页”窗格中单击“选项”。</span><span class="sxs-lookup"><span data-stu-id="66275-188">Click **Options** in the **Select a page** pane.</span></span>
    
   - <span data-ttu-id="66275-189">在“还原选项”中，选择“覆盖现有数据库”。</span><span class="sxs-lookup"><span data-stu-id="66275-189">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
   - <span data-ttu-id="66275-190">在“恢复状态”中，选择“使数据库处于可以使用的状态”。</span><span class="sxs-lookup"><span data-stu-id="66275-190">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
   - <span data-ttu-id="66275-191">单击“确定”开始还原过程。</span><span class="sxs-lookup"><span data-stu-id="66275-191">Click **OK** to begin the restoration process.</span></span>
    
5. <span data-ttu-id="66275-192">配置SQL Server数据库的日志寄送。</span><span class="sxs-lookup"><span data-stu-id="66275-192">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="66275-193">按照在 [Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) 中为持久聊天服务器配置高可用性和灾难恢复中的过程，为主 mgc 数据库建立日志寄送。</span><span class="sxs-lookup"><span data-stu-id="66275-193">Follow the procedures in [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) to establish log shipping for the primary mgc database.</span></span>
    
6. <span data-ttu-id="66275-194">设置持久聊天服务器活动服务器。</span><span class="sxs-lookup"><span data-stu-id="66275-194">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="66275-195">从 Skype for Business Server 命令行管理程序，使用 **Set-CsPersistentChatActiveServer** cmdlet 设置活动服务器的列表。</span><span class="sxs-lookup"><span data-stu-id="66275-195">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="66275-196">所有活动服务器都必须与新主数据库位于同一数据中心中，或位于与数据库之间存在低延迟/高带宽连接的数据中心中。</span><span class="sxs-lookup"><span data-stu-id="66275-196">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
<span data-ttu-id="66275-197">若要将池还原到其正常状态，运行以下Windows PowerShell命令：</span><span class="sxs-lookup"><span data-stu-id="66275-197">To restore the pool to its normal state run the following Windows PowerShell command:</span></span>
  
```PowerShell
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

<span data-ttu-id="66275-198">有关详细信息，请参阅 [Set-CsPersistentChatState](/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="66275-198">For more information, see the help topic for the [Set-CsPersistentChatState](/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet.</span></span>
