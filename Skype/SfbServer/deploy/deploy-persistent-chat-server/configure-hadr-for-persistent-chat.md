---
title: 为 Skype for Business Server 2015 中的持久聊天服务器配置高可用性和灾难恢复
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 摘要： 阅读本主题，了解如何为业务服务器 2015年配置在 Skype 的持久聊天服务器的高可用性和灾难恢复。
ms.openlocfilehash: f0bf1a98bb8967a7310844d9aa85d17d4ef4d167
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="76eeb-103">为 Skype for Business Server 2015 中的持久聊天服务器配置高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="76eeb-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="76eeb-104">**摘要：**阅读本主题，了解如何为业务服务器 2015年配置在 Skype 的持久聊天服务器的高可用性和灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="76eeb-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="76eeb-105">Skype 业务服务器为后端服务器，包括数据库镜像支持高可用性的多个模式。</span><span class="sxs-lookup"><span data-stu-id="76eeb-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="76eeb-106">有关详细信息，请参阅[规划高可用性和灾难恢复业务服务器 2015年的 Skype](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="76eeb-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="76eeb-107">AlwaysOn 可用性组与持久聊天服务器不支持。</span><span class="sxs-lookup"><span data-stu-id="76eeb-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="76eeb-108">您配置的高可用性和灾难恢复持久聊天部署之前，请确保您熟悉中[实现高可用性和业务服务器 2015年的 Skype 的持久聊天服务器的灾难恢复计划](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)的概念。</span><span class="sxs-lookup"><span data-stu-id="76eeb-108">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="76eeb-109">在这些主题中所述的永久性聊天服务器的灾难恢复解决方案构建在拉伸的持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="76eeb-109">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="76eeb-110">资源需求，并为持久的聊天服务器，包括使用高可用性和 SQL Server 日志传送来的 SQL Server 镜像使高可用性和灾难恢复的拉伸的池拓扑，介绍了规划的内容灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="76eeb-110">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="76eeb-111">使用拓扑生成器配置高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="76eeb-111">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="76eeb-112">在拓扑生成器中，执行以下步骤以为持久聊天服务器配置高可用性和灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="76eeb-112">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="76eeb-113">添加镜像数据库和 SQL Server 存储的日志传送辅助数据库。</span><span class="sxs-lookup"><span data-stu-id="76eeb-113">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="76eeb-114">编辑持久聊天服务器的服务属性：</span><span class="sxs-lookup"><span data-stu-id="76eeb-114">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="76eeb-115">a.</span><span class="sxs-lookup"><span data-stu-id="76eeb-115">a.</span></span> <span data-ttu-id="76eeb-116">为主数据库启用镜像。</span><span class="sxs-lookup"><span data-stu-id="76eeb-116">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="76eeb-117">b.</span><span class="sxs-lookup"><span data-stu-id="76eeb-117">b.</span></span> <span data-ttu-id="76eeb-118">添加主镜像 SQL Server 存储。</span><span class="sxs-lookup"><span data-stu-id="76eeb-118">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="76eeb-119">c.</span><span class="sxs-lookup"><span data-stu-id="76eeb-119">c.</span></span> <span data-ttu-id="76eeb-120">启用 SQL Server 日志传送的数据库。</span><span class="sxs-lookup"><span data-stu-id="76eeb-120">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="76eeb-121">d.</span><span class="sxs-lookup"><span data-stu-id="76eeb-121">d.</span></span> <span data-ttu-id="76eeb-122">添加 SQL Server 日志传送辅助 SQL Server 存储。</span><span class="sxs-lookup"><span data-stu-id="76eeb-122">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="76eeb-123">电子。</span><span class="sxs-lookup"><span data-stu-id="76eeb-123">e.</span></span> <span data-ttu-id="76eeb-124">添加为辅助数据库的 SQL Server 存储镜像。</span><span class="sxs-lookup"><span data-stu-id="76eeb-124">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="76eeb-125">f。</span><span class="sxs-lookup"><span data-stu-id="76eeb-125">f.</span></span> <span data-ttu-id="76eeb-126">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="76eeb-126">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="76eeb-127">为持久聊天服务器主数据库设置 SQL Server 日志传送</span><span class="sxs-lookup"><span data-stu-id="76eeb-127">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="76eeb-128">使用 SQL Server 管理 Studio，连接到持久聊天服务器辅助日志传送数据库实例，并确保 SQL Server 代理程序正在运行。</span><span class="sxs-lookup"><span data-stu-id="76eeb-128">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="76eeb-129">然后连接到持久聊天主数据库实例，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="76eeb-129">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="76eeb-130">右键单击 mgc 数据库，然后单击“**属性**”。</span><span class="sxs-lookup"><span data-stu-id="76eeb-130">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="76eeb-131">在“**选择页**”下，单击“**事务日志传送**”。</span><span class="sxs-lookup"><span data-stu-id="76eeb-131">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="76eeb-132">选中“**将此数据库启用为日志传送配置中的主数据库**”复选框。</span><span class="sxs-lookup"><span data-stu-id="76eeb-132">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="76eeb-133">在“**事务日志备份**”下，单击“**备份设置**”。</span><span class="sxs-lookup"><span data-stu-id="76eeb-133">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="76eeb-134">在“**备份文件夹的网络路径**”框中，键入您为事务日志备份文件夹创建的共享的网络路径。</span><span class="sxs-lookup"><span data-stu-id="76eeb-134">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="76eeb-p110">如果备份文件夹位于主服务器上，请在“**如果备份文件夹位于主服务器上，则键入该文件夹的本地路径(示例: c:\backup)**”框中键入该备份文件夹的本地路径。（如果备份文件夹不在主服务器上，则可将此框留空。）</span><span class="sxs-lookup"><span data-stu-id="76eeb-p110">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="76eeb-137">如果您的主服务器上的 SQL Server 服务帐户在本地系统帐户下运行，必须在主服务器上创建备份文件夹，并指定该文件夹的本地路径。</span><span class="sxs-lookup"><span data-stu-id="76eeb-137">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="76eeb-138">配置“**删除文件，如果其保留时间超过**”和“**在以下时间内没有执行备份时报警**”参数。</span><span class="sxs-lookup"><span data-stu-id="76eeb-138">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="76eeb-139">查看“**备份作业**”下的“**计划**”框中所列的备份计划。</span><span class="sxs-lookup"><span data-stu-id="76eeb-139">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="76eeb-140">若要自定义您的安装的日程安排，单击**日程安排**，并调整所需的 SQL Server 代理计划。</span><span class="sxs-lookup"><span data-stu-id="76eeb-140">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="76eeb-141">在“**压缩**”下，选择“**使用默认服务器设置**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="76eeb-141">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="76eeb-142">在“**辅助服务器实例和数据库**”下，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="76eeb-142">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="76eeb-143">单击**连接**，连接到已配置为从属服务器的 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="76eeb-143">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="76eeb-144">在“**辅助数据库**”框中，从列表中选择“**mgc**”数据库。</span><span class="sxs-lookup"><span data-stu-id="76eeb-144">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="76eeb-145">在“**初始化辅助数据库**”选项卡中，选择选项“**是，生成主数据库的完整备份，并将它还原到辅助数据库中（如果辅助数据库不存在，则创建它）**”。</span><span class="sxs-lookup"><span data-stu-id="76eeb-145">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="76eeb-p112">在“**复制文件**”选项卡上的“**复制文件的目标文件夹**”框中，键入应将事务日志备份复制到的文件夹的路径。此文件夹通常位于辅助服务器上。</span><span class="sxs-lookup"><span data-stu-id="76eeb-p112">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="76eeb-148">注意“**复制作业**”下的“**计划**”框中列出的复制计划。</span><span class="sxs-lookup"><span data-stu-id="76eeb-148">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="76eeb-149">若要自定义您的安装的日程安排，单击**日程安排**，并调整所需的 SQL Server 代理计划。</span><span class="sxs-lookup"><span data-stu-id="76eeb-149">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="76eeb-150">此计划应与备份计划大致相同。</span><span class="sxs-lookup"><span data-stu-id="76eeb-150">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="76eeb-151">在“**还原**”选项卡上的“**还原备份时的数据库状态**”下，选择“**无恢复模式**”选项。</span><span class="sxs-lookup"><span data-stu-id="76eeb-151">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="76eeb-152">在“**延迟还原备份操作至少：**”下，选择“**0 分钟**”。</span><span class="sxs-lookup"><span data-stu-id="76eeb-152">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="76eeb-153">在“**在以下时间内没有执行还原时报警**”下选择报警阈值。</span><span class="sxs-lookup"><span data-stu-id="76eeb-153">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="76eeb-154">查看“**还原作业**”下的“**计划**”框中列出的还原计划。</span><span class="sxs-lookup"><span data-stu-id="76eeb-154">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="76eeb-155">若要自定义您的安装的计划**日程**调整 SQL Server 代理计划的要求，和，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="76eeb-155">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="76eeb-156">此计划应与备份计划大致相同。</span><span class="sxs-lookup"><span data-stu-id="76eeb-156">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="76eeb-157">在“**数据库属性**”对话框中，单击“**确定**”开始配置过程。</span><span class="sxs-lookup"><span data-stu-id="76eeb-157">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="76eeb-158">在主镜像和辅助数据库之间设置 SQL Server 日志传送</span><span class="sxs-lookup"><span data-stu-id="76eeb-158">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="76eeb-159">为使日志传送继续如果持续聊天的主数据库故障转移到镜像数据库执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="76eeb-159">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="76eeb-160">手动故障转移到镜像主持久聊天数据库。</span><span class="sxs-lookup"><span data-stu-id="76eeb-160">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="76eeb-161">这是通过使用 Skype 业务服务器管理外壳程序和**调用 CsDatabaseFailover** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="76eeb-161">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="76eeb-162">使用 SQL Server 管理工作室，连接到主持久聊天服务器镜像实例。</span><span class="sxs-lookup"><span data-stu-id="76eeb-162">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="76eeb-163">请确保： SQL Server 代理程序正在运行。</span><span class="sxs-lookup"><span data-stu-id="76eeb-163">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="76eeb-164">右键单击 mgc 数据库，然后单击“**属性**”。</span><span class="sxs-lookup"><span data-stu-id="76eeb-164">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="76eeb-165">在“**选择页**”下，单击“**事务日志传送**”。</span><span class="sxs-lookup"><span data-stu-id="76eeb-165">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="76eeb-166">选中“**将此数据库启用为日志传送配置中的主数据库**”复选框。</span><span class="sxs-lookup"><span data-stu-id="76eeb-166">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="76eeb-167">在“**事务日志备份**”下，单击“**备份设置**”。</span><span class="sxs-lookup"><span data-stu-id="76eeb-167">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="76eeb-168">在“**备份文件夹的网络路径**”框中，键入您为事务日志备份文件夹创建的共享的网络路径。</span><span class="sxs-lookup"><span data-stu-id="76eeb-168">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="76eeb-p116">如果备份文件夹位于主服务器上，请在“**如果备份文件夹位于主服务器上，则键入该文件夹的本地路径（示例: c:\backup）**”框中键入该备份文件夹的本地路径。（如果备份文件夹不在主服务器上，则可将此框留空。）</span><span class="sxs-lookup"><span data-stu-id="76eeb-p116">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="76eeb-171">如果您的主服务器上的 SQL Server 服务帐户在本地系统帐户下运行，必须在主服务器上创建备份文件夹，并指定该文件夹的本地路径。</span><span class="sxs-lookup"><span data-stu-id="76eeb-171">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="76eeb-172">配置“**删除文件，如果其保留时间超过**”和“**在以下时间内没有执行备份时报警**”参数。</span><span class="sxs-lookup"><span data-stu-id="76eeb-172">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="76eeb-173">查看“**备份作业**”下的“**计划**”框中所列的备份计划。</span><span class="sxs-lookup"><span data-stu-id="76eeb-173">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="76eeb-174">以自定义您的安装的日程安排，请单击**日程安排**，并调整 SQL Server 代理程序调度，根据需要。</span><span class="sxs-lookup"><span data-stu-id="76eeb-174">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="76eeb-175">使用您对主数据库使用的相同设置。</span><span class="sxs-lookup"><span data-stu-id="76eeb-175">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="76eeb-176">在“**压缩**”下，选择“**使用默认服务器设置**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="76eeb-176">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="76eeb-177">在“**辅助服务器实例和数据库**”下，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="76eeb-177">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="76eeb-178">单击“**连接**”，然后连接到您已作为辅助服务器配置的 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="76eeb-178">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="76eeb-179">在“**辅助数据库**”框中，从列表中选择“**mgc**”数据库。</span><span class="sxs-lookup"><span data-stu-id="76eeb-179">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="76eeb-180">在“**初始化辅助数据库**”选项卡上，选择“**否，辅助数据库已初始化**”选项。</span><span class="sxs-lookup"><span data-stu-id="76eeb-180">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="76eeb-p118">在“**复制文件**”选项卡上的“**复制文件的目标文件夹**”中，键入事务日志备份应复制到的文件夹的路径，然后单击**“确定**”。此文件夹通常位于辅助服务器上。</span><span class="sxs-lookup"><span data-stu-id="76eeb-p118">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**. This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="76eeb-183">打开“**脚本配置**”下拉列表，然后选择“**将脚本配置保存到‘新建查询’窗口**”。</span><span class="sxs-lookup"><span data-stu-id="76eeb-183">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="76eeb-184">在新建查询窗口中的“**数据库属性**”上，单击“**确定**”开始配置过程。</span><span class="sxs-lookup"><span data-stu-id="76eeb-184">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="76eeb-185">选择并运行第一个查询的一半 （见第 18 步） 向上到行:- \* \* \* \* \* \*结束： 要在主运行的脚本： \* \* \* \* \* \*。</span><span class="sxs-lookup"><span data-stu-id="76eeb-185">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="76eeb-186">手动运行此脚本是必需的因为 SQL Server 管理 Studio 不支持 SQL Server 日志传送配置中的多个主数据库。</span><span class="sxs-lookup"><span data-stu-id="76eeb-186">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="76eeb-187">选择“**取消**”以关闭日志文件传送配置面板并建立正确实现主数据库和镜像数据库的日志文件传送的工作设置（在故障转移的情况下）。 </span><span class="sxs-lookup"><span data-stu-id="76eeb-187">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="76eeb-188">手动回切到主主持久聊天数据库。</span><span class="sxs-lookup"><span data-stu-id="76eeb-188">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="76eeb-189">这是通过使用 Skype 业务服务器命令行管理程序，并**调用 CsDatabaseFailover** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="76eeb-189">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

