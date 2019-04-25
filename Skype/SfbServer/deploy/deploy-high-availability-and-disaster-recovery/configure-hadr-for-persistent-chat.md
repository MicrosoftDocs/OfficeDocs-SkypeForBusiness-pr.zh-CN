---
title: 为 Skype for Business Server 2015 中的持久聊天服务器配置高可用性和灾难恢复
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 摘要： 阅读本主题可了解如何为业务服务器 2015年对于 Persistent Chat Server in Skype 配置高可用性和灾难恢复。
ms.openlocfilehash: 5c53652cf5084b5a6c021c38f71f1cccc0322efa
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225488"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="8ff33-103">为 Skype for Business Server 2015 中的持久聊天服务器配置高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="8ff33-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8ff33-104">**摘要：** 阅读本主题可了解如何为业务服务器 2015年对于 Persistent Chat Server in Skype 配置高可用性和灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="8ff33-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="8ff33-105">Skype 业务服务器支持的后端服务器，包括数据库镜像高可用性的多个的模式。</span><span class="sxs-lookup"><span data-stu-id="8ff33-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="8ff33-106">有关详细信息，请参阅[Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="8ff33-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8ff33-107">与持久聊天服务器不支持 AlwaysOn 可用性组。</span><span class="sxs-lookup"><span data-stu-id="8ff33-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="8ff33-108">配置持久聊天的高可用性和灾难恢复部署之前，请确保您熟悉中[规划高可用性和灾难恢复 for Persistent Chat Server 中的业务服务器 2015 Skype](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)的概念。</span><span class="sxs-lookup"><span data-stu-id="8ff33-108">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="8ff33-109">这些主题中所述的持久聊天服务器的灾难恢复解决方案是基于拉伸的持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="8ff33-109">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="8ff33-110">规划内容介绍资源需求，以及启用持久聊天服务器，包括使用 SQL Server 镜像的高可用性和 SQL Server 日志传送的高可用性和灾难恢复的扩展的池拓扑灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="8ff33-110">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="8ff33-111">使用拓扑生成器配置高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="8ff33-111">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="8ff33-112">在拓扑生成器中，执行以下步骤以为持久聊天服务器配置高可用性和灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="8ff33-112">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="8ff33-113">添加镜像数据库和日志传送辅助数据库 SQL Server 存储。</span><span class="sxs-lookup"><span data-stu-id="8ff33-113">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="8ff33-114">编辑持久聊天服务器服务属性实现：</span><span class="sxs-lookup"><span data-stu-id="8ff33-114">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="8ff33-115">a.</span><span class="sxs-lookup"><span data-stu-id="8ff33-115">a.</span></span> <span data-ttu-id="8ff33-116">为主数据库启用镜像。</span><span class="sxs-lookup"><span data-stu-id="8ff33-116">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="8ff33-117">b.</span><span class="sxs-lookup"><span data-stu-id="8ff33-117">b.</span></span> <span data-ttu-id="8ff33-118">添加主镜像 SQL Server 存储。</span><span class="sxs-lookup"><span data-stu-id="8ff33-118">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="8ff33-119">c.</span><span class="sxs-lookup"><span data-stu-id="8ff33-119">c.</span></span> <span data-ttu-id="8ff33-120">启用 SQL Server 日志传送数据库。</span><span class="sxs-lookup"><span data-stu-id="8ff33-120">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="8ff33-121">d.</span><span class="sxs-lookup"><span data-stu-id="8ff33-121">d.</span></span> <span data-ttu-id="8ff33-122">添加 SQL Server 日志传送辅助 SQL Server 存储。</span><span class="sxs-lookup"><span data-stu-id="8ff33-122">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="8ff33-123">e。</span><span class="sxs-lookup"><span data-stu-id="8ff33-123">e.</span></span> <span data-ttu-id="8ff33-124">添加辅助数据库的 SQL Server 存储镜像。</span><span class="sxs-lookup"><span data-stu-id="8ff33-124">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="8ff33-125">f。</span><span class="sxs-lookup"><span data-stu-id="8ff33-125">f.</span></span> <span data-ttu-id="8ff33-126">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="8ff33-126">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="8ff33-127">为持久聊天服务器主数据库设置 SQL Server 日志传送</span><span class="sxs-lookup"><span data-stu-id="8ff33-127">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="8ff33-128">使用 SQL Server Management Studio，连接到持久聊天服务器辅助日志传送数据库实例，并确保 SQL Server 代理正在运行。</span><span class="sxs-lookup"><span data-stu-id="8ff33-128">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="8ff33-129">然后连接到的持久聊天主数据库实例并执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="8ff33-129">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="8ff33-130">右键单击 mgc 数据库，然后单击“**属性**”。</span><span class="sxs-lookup"><span data-stu-id="8ff33-130">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="8ff33-131">在“**选择页**”下，单击“**事务日志传送**”。</span><span class="sxs-lookup"><span data-stu-id="8ff33-131">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="8ff33-132">选中“**将此数据库启用为日志传送配置中的主数据库**”复选框。</span><span class="sxs-lookup"><span data-stu-id="8ff33-132">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="8ff33-133">在“**事务日志备份**”下，单击“**备份设置**”。</span><span class="sxs-lookup"><span data-stu-id="8ff33-133">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="8ff33-134">在“**备份文件夹的网络路径**”框中，键入您为事务日志备份文件夹创建的共享的网络路径。</span><span class="sxs-lookup"><span data-stu-id="8ff33-134">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="8ff33-p110">如果备份文件夹位于主服务器上，请在“**如果备份文件夹位于主服务器上，则键入该文件夹的本地路径(示例: c:\backup)**”框中键入该备份文件夹的本地路径。（如果备份文件夹不在主服务器上，则可将此框留空。）</span><span class="sxs-lookup"><span data-stu-id="8ff33-p110">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8ff33-137">如果本地系统帐户下运行您的主服务器上的 SQL Server 服务帐户，您必须在主服务器上创建备份文件夹，并指定该文件夹的本地路径。</span><span class="sxs-lookup"><span data-stu-id="8ff33-137">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="8ff33-138">配置“**删除文件，如果其保留时间超过**”和“**在以下时间内没有执行备份时报警**”参数。</span><span class="sxs-lookup"><span data-stu-id="8ff33-138">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="8ff33-139">查看“**备份作业**”下的“**计划**”框中所列的备份计划。</span><span class="sxs-lookup"><span data-stu-id="8ff33-139">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="8ff33-140">若要自定义安装的计划，单击**计划**，并调整所需的 SQL Server 代理计划。</span><span class="sxs-lookup"><span data-stu-id="8ff33-140">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="8ff33-141">在“**压缩**”下，选择“**使用默认服务器设置**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="8ff33-141">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="8ff33-142">在“**辅助服务器实例和数据库**”下，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="8ff33-142">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="8ff33-143">单击**连接**并连接到 SQL Server 的已配置为辅助服务器实例。</span><span class="sxs-lookup"><span data-stu-id="8ff33-143">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="8ff33-144">在“**辅助数据库**”框中，从列表中选择“**mgc**”数据库。</span><span class="sxs-lookup"><span data-stu-id="8ff33-144">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="8ff33-145">在**初始化辅助数据库**选项卡中，选择选项**是，生成主数据库的完整备份和还原到辅助数据库 （以及创建辅助数据库不存在时）**。</span><span class="sxs-lookup"><span data-stu-id="8ff33-145">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="8ff33-146">**复制文件**选项卡中，在**复制的文件的目标文件夹**框中，键入应该将事务日志备份复制到其中的文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="8ff33-146">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="8ff33-147">此文件夹通常位于辅助服务器。</span><span class="sxs-lookup"><span data-stu-id="8ff33-147">This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="8ff33-148">复制计划**复制作业**下的**日程表**框中列出的注释。</span><span class="sxs-lookup"><span data-stu-id="8ff33-148">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="8ff33-149">若要自定义安装的计划，单击**计划**，并调整所需的 SQL Server 代理计划。</span><span class="sxs-lookup"><span data-stu-id="8ff33-149">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="8ff33-150">此计划应该大约是相同的备份的计划。</span><span class="sxs-lookup"><span data-stu-id="8ff33-150">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="8ff33-151">在**还原**选项卡上，在**数据库状态还原备份时**，下选择**无恢复模式**选项。</span><span class="sxs-lookup"><span data-stu-id="8ff33-151">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="8ff33-152">在**延迟还原备份至少：**，选择**0 分钟**。</span><span class="sxs-lookup"><span data-stu-id="8ff33-152">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="8ff33-153">选择下**警报内没有执行还原时**报警阈值。</span><span class="sxs-lookup"><span data-stu-id="8ff33-153">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="8ff33-154">查看下**还原作业**的**日程表**框中列出的还原计划。</span><span class="sxs-lookup"><span data-stu-id="8ff33-154">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="8ff33-155">若要自定义安装的计划，单击**计划**、 调整 SQL Server 代理计划，根据需要单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8ff33-155">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="8ff33-156">此计划应该大约是相同的备份的计划。</span><span class="sxs-lookup"><span data-stu-id="8ff33-156">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="8ff33-157">在**数据库属性**对话框中，单击**确定**以开始配置过程。</span><span class="sxs-lookup"><span data-stu-id="8ff33-157">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="8ff33-158">设置 SQL Server 日志传送主镜像和辅助数据库之间</span><span class="sxs-lookup"><span data-stu-id="8ff33-158">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="8ff33-159">执行以下步骤以便日志传送能够继续如果主持久聊天数据库故障转移到其镜像数据库。</span><span class="sxs-lookup"><span data-stu-id="8ff33-159">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="8ff33-160">手动故障转移到镜像主持久聊天数据库。</span><span class="sxs-lookup"><span data-stu-id="8ff33-160">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="8ff33-161">这是通过使用 Skype 业务 Server 命令行管理程序和**Invoke-csdatabasefailover** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8ff33-161">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="8ff33-162">使用 SQL Server Management Studio，连接到主 Persistent Chat Server 镜像实例。</span><span class="sxs-lookup"><span data-stu-id="8ff33-162">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="8ff33-163">确保 SQL Server 代理正在运行。</span><span class="sxs-lookup"><span data-stu-id="8ff33-163">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="8ff33-164">右键单击 mgc 数据库，然后单击“**属性**”。</span><span class="sxs-lookup"><span data-stu-id="8ff33-164">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="8ff33-165">在“**选择页**”下，单击“**事务日志传送**”。</span><span class="sxs-lookup"><span data-stu-id="8ff33-165">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="8ff33-166">选中“**将此数据库启用为日志传送配置中的主数据库**”复选框。</span><span class="sxs-lookup"><span data-stu-id="8ff33-166">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="8ff33-167">在“**事务日志备份**”下，单击“**备份设置**”。</span><span class="sxs-lookup"><span data-stu-id="8ff33-167">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="8ff33-168">在**备份文件夹的网络路径**框中，键入您为事务日志备份文件夹创建的共享的网络路径。</span><span class="sxs-lookup"><span data-stu-id="8ff33-168">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="8ff33-169">如果备份文件夹位于主服务器上，请在**如果备份文件夹所在的主服务器上，键入文件夹的本地路径**框中键入指向备份文件夹的本地路径。</span><span class="sxs-lookup"><span data-stu-id="8ff33-169">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box.</span></span> <span data-ttu-id="8ff33-170">（如果备份文件夹不是主服务器上，您可以将此框保留为空。）</span><span class="sxs-lookup"><span data-stu-id="8ff33-170">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8ff33-171">如果本地系统帐户下运行您的主服务器上的 SQL Server 服务帐户，您必须在主服务器上创建备份文件夹，并指定该文件夹的本地路径。</span><span class="sxs-lookup"><span data-stu-id="8ff33-171">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="8ff33-172">配置“**删除文件，如果其保留时间超过**”和“**在以下时间内没有执行备份时报警**”参数。</span><span class="sxs-lookup"><span data-stu-id="8ff33-172">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="8ff33-173">查看“**备份作业**”下的“**计划**”框中所列的备份计划。</span><span class="sxs-lookup"><span data-stu-id="8ff33-173">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="8ff33-174">若要自定义安装的计划，请单击**计划**，并调整 SQL Server 代理计划，根据需要。</span><span class="sxs-lookup"><span data-stu-id="8ff33-174">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8ff33-175">使用相同的设置用于主数据库。</span><span class="sxs-lookup"><span data-stu-id="8ff33-175">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="8ff33-176">在**压缩**下选择**使用默认服务器设置**并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8ff33-176">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="8ff33-177">在“**辅助服务器实例和数据库**”下，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="8ff33-177">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="8ff33-178">单击**连接**，并连接到 SQL Server 的已配置为辅助服务器实例。</span><span class="sxs-lookup"><span data-stu-id="8ff33-178">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="8ff33-179">在“**辅助数据库**”框中，从列表中选择“**mgc**”数据库。</span><span class="sxs-lookup"><span data-stu-id="8ff33-179">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="8ff33-180">在**初始化辅助数据库**选项卡中，选择**否，辅助数据库已初始化**的选项。</span><span class="sxs-lookup"><span data-stu-id="8ff33-180">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="8ff33-181">在**将文件复制**选项卡上的在**复制的文件的目标文件夹**中，键入到事务日志备份文件夹的路径应复制，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8ff33-181">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**.</span></span> <span data-ttu-id="8ff33-182">此文件夹通常位于辅助服务器。</span><span class="sxs-lookup"><span data-stu-id="8ff33-182">This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="8ff33-183">打开**脚本配置**下拉列表，并选择**配置脚本保存到新的查询窗口**。</span><span class="sxs-lookup"><span data-stu-id="8ff33-183">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="8ff33-184">在新的查询窗口中，在**数据库属性**，单击**确定**开始配置过程。</span><span class="sxs-lookup"><span data-stu-id="8ff33-184">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="8ff33-185">选择并运行第一个查询的一半 （参见第 18 步） 安装到行:- \* \* \* \* \* \* End: Script to be run at Primary: \* \* \* \* \* \*。</span><span class="sxs-lookup"><span data-stu-id="8ff33-185">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8ff33-186">手动运行此脚本是必需的因为 SQL Server Management Studio 中不支持 SQL Server 日志传送配置中的多个主数据库。</span><span class="sxs-lookup"><span data-stu-id="8ff33-186">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="8ff33-187">选择**取消**以关闭日志文件传送配置面板并建立正确地实现 （出现时故障转移） 主和镜像数据库的日志文件传送工作安装程序。</span><span class="sxs-lookup"><span data-stu-id="8ff33-187">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="8ff33-188">手动故障回复到主主持久聊天数据库。</span><span class="sxs-lookup"><span data-stu-id="8ff33-188">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="8ff33-189">这是通过使用 Skype 业务 Server Management Shell，并使用**Invoke-csdatabasefailover** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8ff33-189">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

