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
description: 摘要： 阅读本主题可了解如何为业务服务器 2015年对于 Persistent Chat Server in Skype 配置高可用性和灾难恢复。
ms.openlocfilehash: c2e4ff1d210e5a8fa5fccbc002ebd1c4ca59a545
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21004684"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="95e59-103">为 Skype for Business Server 2015 中的持久聊天服务器配置高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="95e59-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="95e59-104">**摘要：** 阅读本主题可了解如何为业务服务器 2015年对于 Persistent Chat Server in Skype 配置高可用性和灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="95e59-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="95e59-105">Skype 业务服务器支持的后端服务器，包括数据库镜像高可用性的多个的模式。</span><span class="sxs-lookup"><span data-stu-id="95e59-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="95e59-106">有关详细信息，请参阅[规划高可用性和灾难恢复的业务服务器 2015 Skype 中](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="95e59-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="95e59-107">与持久聊天服务器不支持 AlwaysOn 可用性组。</span><span class="sxs-lookup"><span data-stu-id="95e59-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 

> [!NOTE] 
> <span data-ttu-id="95e59-108">持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。</span><span class="sxs-lookup"><span data-stu-id="95e59-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="95e59-109">中团队提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="95e59-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="95e59-110">有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。</span><span class="sxs-lookup"><span data-stu-id="95e59-110">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="95e59-111">如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。</span><span class="sxs-lookup"><span data-stu-id="95e59-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="95e59-112">配置持久聊天的高可用性和灾难恢复部署之前，请确保您熟悉中[规划高可用性和灾难恢复 for Persistent Chat Server 中的业务服务器 2015 Skype](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)的概念。</span><span class="sxs-lookup"><span data-stu-id="95e59-112">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="95e59-113">这些主题中所述的持久聊天服务器的灾难恢复解决方案是基于拉伸的持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="95e59-113">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="95e59-114">规划内容介绍资源需求，以及启用持久聊天服务器，包括使用 SQL Server 镜像的高可用性和 SQL Server 日志传送的高可用性和灾难恢复的扩展的池拓扑灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="95e59-114">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="95e59-115">使用拓扑生成器配置高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="95e59-115">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="95e59-116">在拓扑生成器中，执行以下步骤以为持久聊天服务器配置高可用性和灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="95e59-116">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="95e59-117">添加镜像数据库和日志传送辅助数据库 SQL Server 存储。</span><span class="sxs-lookup"><span data-stu-id="95e59-117">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="95e59-118">编辑持久聊天服务器服务属性实现：</span><span class="sxs-lookup"><span data-stu-id="95e59-118">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="95e59-119">a.</span><span class="sxs-lookup"><span data-stu-id="95e59-119">a.</span></span> <span data-ttu-id="95e59-120">为主数据库启用镜像。</span><span class="sxs-lookup"><span data-stu-id="95e59-120">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="95e59-121">b.</span><span class="sxs-lookup"><span data-stu-id="95e59-121">b.</span></span> <span data-ttu-id="95e59-122">添加主镜像 SQL Server 存储。</span><span class="sxs-lookup"><span data-stu-id="95e59-122">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="95e59-123">c.</span><span class="sxs-lookup"><span data-stu-id="95e59-123">c.</span></span> <span data-ttu-id="95e59-124">启用 SQL Server 日志传送数据库。</span><span class="sxs-lookup"><span data-stu-id="95e59-124">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="95e59-125">d.</span><span class="sxs-lookup"><span data-stu-id="95e59-125">d.</span></span> <span data-ttu-id="95e59-126">添加 SQL Server 日志传送辅助 SQL Server 存储。</span><span class="sxs-lookup"><span data-stu-id="95e59-126">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="95e59-127">e。</span><span class="sxs-lookup"><span data-stu-id="95e59-127">e.</span></span> <span data-ttu-id="95e59-128">添加辅助数据库的 SQL Server 存储镜像。</span><span class="sxs-lookup"><span data-stu-id="95e59-128">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="95e59-129">f。</span><span class="sxs-lookup"><span data-stu-id="95e59-129">f.</span></span> <span data-ttu-id="95e59-130">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="95e59-130">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="95e59-131">为持久聊天服务器主数据库设置 SQL Server 日志传送</span><span class="sxs-lookup"><span data-stu-id="95e59-131">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="95e59-132">使用 SQL Server Management Studio，连接到持久聊天服务器辅助日志传送数据库实例，并确保 SQL Server 代理正在运行。</span><span class="sxs-lookup"><span data-stu-id="95e59-132">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="95e59-133">然后连接到的持久聊天主数据库实例并执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="95e59-133">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="95e59-134">右键单击 mgc 数据库，然后单击“**属性**”。</span><span class="sxs-lookup"><span data-stu-id="95e59-134">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="95e59-135">在“**选择页**”下，单击“**事务日志传送**”。</span><span class="sxs-lookup"><span data-stu-id="95e59-135">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="95e59-136">选中“**将此数据库启用为日志传送配置中的主数据库**”复选框。</span><span class="sxs-lookup"><span data-stu-id="95e59-136">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="95e59-137">在“**事务日志备份**”下，单击“**备份设置**”。</span><span class="sxs-lookup"><span data-stu-id="95e59-137">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="95e59-138">在“**备份文件夹的网络路径**”框中，键入您为事务日志备份文件夹创建的共享的网络路径。</span><span class="sxs-lookup"><span data-stu-id="95e59-138">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="95e59-p111">如果备份文件夹位于主服务器上，请在“**如果备份文件夹位于主服务器上，则键入该文件夹的本地路径(示例: c:\backup)**”框中键入该备份文件夹的本地路径。（如果备份文件夹不在主服务器上，则可将此框留空。）</span><span class="sxs-lookup"><span data-stu-id="95e59-p111">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="95e59-141">如果本地系统帐户下运行您的主服务器上的 SQL Server 服务帐户，您必须在主服务器上创建备份文件夹，并指定该文件夹的本地路径。</span><span class="sxs-lookup"><span data-stu-id="95e59-141">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="95e59-142">配置“**删除文件，如果其保留时间超过**”和“**在以下时间内没有执行备份时报警**”参数。</span><span class="sxs-lookup"><span data-stu-id="95e59-142">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="95e59-143">查看“**备份作业**”下的“**计划**”框中所列的备份计划。</span><span class="sxs-lookup"><span data-stu-id="95e59-143">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="95e59-144">若要自定义安装的计划，单击**计划**，并调整所需的 SQL Server 代理计划。</span><span class="sxs-lookup"><span data-stu-id="95e59-144">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="95e59-145">在“**压缩**”下，选择“**使用默认服务器设置**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="95e59-145">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="95e59-146">在“**辅助服务器实例和数据库**”下，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="95e59-146">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="95e59-147">单击**连接**并连接到 SQL Server 的已配置为辅助服务器实例。</span><span class="sxs-lookup"><span data-stu-id="95e59-147">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="95e59-148">在“**辅助数据库**”框中，从列表中选择“**mgc**”数据库。</span><span class="sxs-lookup"><span data-stu-id="95e59-148">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="95e59-149">在“**初始化辅助数据库**”选项卡中，选择选项“**是，生成主数据库的完整备份，并将它还原到辅助数据库中（如果辅助数据库不存在，则创建它）**”。</span><span class="sxs-lookup"><span data-stu-id="95e59-149">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="95e59-p113">在“**复制文件**”选项卡上的“**复制文件的目标文件夹**”框中，键入应将事务日志备份复制到的文件夹的路径。此文件夹通常位于辅助服务器上。</span><span class="sxs-lookup"><span data-stu-id="95e59-p113">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="95e59-152">注意“**复制作业**”下的“**计划**”框中列出的复制计划。</span><span class="sxs-lookup"><span data-stu-id="95e59-152">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="95e59-153">若要自定义安装的计划，单击**计划**，并调整所需的 SQL Server 代理计划。</span><span class="sxs-lookup"><span data-stu-id="95e59-153">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="95e59-154">此计划应与备份计划大致相同。</span><span class="sxs-lookup"><span data-stu-id="95e59-154">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="95e59-155">在“**还原**”选项卡上的“**还原备份时的数据库状态**”下，选择“**无恢复模式**”选项。</span><span class="sxs-lookup"><span data-stu-id="95e59-155">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="95e59-156">在“**延迟还原备份操作至少：**”下，选择“**0 分钟**”。</span><span class="sxs-lookup"><span data-stu-id="95e59-156">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="95e59-157">在“**在以下时间内没有执行还原时报警**”下选择报警阈值。</span><span class="sxs-lookup"><span data-stu-id="95e59-157">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="95e59-158">查看“**还原作业**”下的“**计划**”框中列出的还原计划。</span><span class="sxs-lookup"><span data-stu-id="95e59-158">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="95e59-159">若要自定义安装的计划，单击**计划**、 调整 SQL Server 代理计划，根据需要单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="95e59-159">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="95e59-160">此计划应与备份计划大致相同。</span><span class="sxs-lookup"><span data-stu-id="95e59-160">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="95e59-161">在“**数据库属性**”对话框中，单击“**确定**”开始配置过程。</span><span class="sxs-lookup"><span data-stu-id="95e59-161">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="95e59-162">在主镜像和辅助数据库之间设置 SQL Server 日志传送</span><span class="sxs-lookup"><span data-stu-id="95e59-162">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="95e59-163">执行以下步骤以便日志传送能够继续如果主持久聊天数据库故障转移到其镜像数据库。</span><span class="sxs-lookup"><span data-stu-id="95e59-163">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="95e59-164">手动故障转移到镜像主持久聊天数据库。</span><span class="sxs-lookup"><span data-stu-id="95e59-164">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="95e59-165">这是通过使用 Skype 业务 Server 命令行管理程序和**Invoke-csdatabasefailover** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="95e59-165">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="95e59-166">使用 SQL Server Management Studio，连接到主 Persistent Chat Server 镜像实例。</span><span class="sxs-lookup"><span data-stu-id="95e59-166">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="95e59-167">确保 SQL Server 代理正在运行。</span><span class="sxs-lookup"><span data-stu-id="95e59-167">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="95e59-168">右键单击 mgc 数据库，然后单击“**属性**”。</span><span class="sxs-lookup"><span data-stu-id="95e59-168">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="95e59-169">在“**选择页**”下，单击“**事务日志传送**”。</span><span class="sxs-lookup"><span data-stu-id="95e59-169">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="95e59-170">选中“**将此数据库启用为日志传送配置中的主数据库**”复选框。</span><span class="sxs-lookup"><span data-stu-id="95e59-170">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="95e59-171">在“**事务日志备份**”下，单击“**备份设置**”。</span><span class="sxs-lookup"><span data-stu-id="95e59-171">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="95e59-172">在“**备份文件夹的网络路径**”框中，键入您为事务日志备份文件夹创建的共享的网络路径。</span><span class="sxs-lookup"><span data-stu-id="95e59-172">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="95e59-p117">如果备份文件夹位于主服务器上，请在“**如果备份文件夹位于主服务器上，则键入该文件夹的本地路径（示例: c:\backup）**”框中键入该备份文件夹的本地路径。（如果备份文件夹不在主服务器上，则可将此框留空。）</span><span class="sxs-lookup"><span data-stu-id="95e59-p117">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="95e59-175">如果本地系统帐户下运行您的主服务器上的 SQL Server 服务帐户，您必须在主服务器上创建备份文件夹，并指定该文件夹的本地路径。</span><span class="sxs-lookup"><span data-stu-id="95e59-175">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="95e59-176">配置“**删除文件，如果其保留时间超过**”和“**在以下时间内没有执行备份时报警**”参数。</span><span class="sxs-lookup"><span data-stu-id="95e59-176">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="95e59-177">查看“**备份作业**”下的“**计划**”框中所列的备份计划。</span><span class="sxs-lookup"><span data-stu-id="95e59-177">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="95e59-178">若要自定义安装的计划，请单击**计划**，并调整 SQL Server 代理计划，根据需要。</span><span class="sxs-lookup"><span data-stu-id="95e59-178">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="95e59-179">使用您对主数据库使用的相同设置。</span><span class="sxs-lookup"><span data-stu-id="95e59-179">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="95e59-180">在“**压缩**”下，选择“**使用默认服务器设置**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="95e59-180">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="95e59-181">在“**辅助服务器实例和数据库**”下，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="95e59-181">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="95e59-182">单击“**连接**”，然后连接到您已作为辅助服务器配置的 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="95e59-182">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="95e59-183">在“**辅助数据库**”框中，从列表中选择“**mgc**”数据库。</span><span class="sxs-lookup"><span data-stu-id="95e59-183">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="95e59-184">在“**初始化辅助数据库**”选项卡上，选择“**否，辅助数据库已初始化**”选项。</span><span class="sxs-lookup"><span data-stu-id="95e59-184">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="95e59-p119">在“**复制文件**”选项卡上的“**复制文件的目标文件夹**”中，键入事务日志备份应复制到的文件夹的路径，然后单击 **“确定**”。此文件夹通常位于辅助服务器上。</span><span class="sxs-lookup"><span data-stu-id="95e59-p119">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**. This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="95e59-187">打开“**脚本配置**”下拉列表，然后选择“**将脚本配置保存到‘新建查询’窗口**”。</span><span class="sxs-lookup"><span data-stu-id="95e59-187">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="95e59-188">在新建查询窗口中的“**数据库属性**”上，单击“**确定**”开始配置过程。</span><span class="sxs-lookup"><span data-stu-id="95e59-188">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="95e59-189">选择并运行第一个查询的一半 （参见第 18 步） 安装到行:- \* \* \* \* \* \* End: Script to be run at Primary: \* \* \* \* \* \*。</span><span class="sxs-lookup"><span data-stu-id="95e59-189">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="95e59-190">手动运行此脚本是必需的因为 SQL Server Management Studio 中不支持 SQL Server 日志传送配置中的多个主数据库。</span><span class="sxs-lookup"><span data-stu-id="95e59-190">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="95e59-191">选择“**取消**”以关闭日志文件传送配置面板并建立正确实现主数据库和镜像数据库的日志文件传送的工作设置（在故障转移的情况下）。 </span><span class="sxs-lookup"><span data-stu-id="95e59-191">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="95e59-192">手动故障回复到主主持久聊天数据库。</span><span class="sxs-lookup"><span data-stu-id="95e59-192">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="95e59-193">这是通过使用 Skype 业务 Server Management Shell，并使用**Invoke-csdatabasefailover** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="95e59-193">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

