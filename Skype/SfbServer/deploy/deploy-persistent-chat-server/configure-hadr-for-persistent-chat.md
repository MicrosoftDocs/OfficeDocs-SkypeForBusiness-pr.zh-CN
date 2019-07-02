---
title: 为 Skype for Business Server 2015 中的持久聊天服务器配置高可用性和灾难恢复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: '摘要: 阅读本主题, 了解如何在 Skype for business Server 2015 中配置持久聊天服务器的高可用性和灾难恢复。'
ms.openlocfilehash: 813ea29d8ea8b75c866e12c056b40e237173922c
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418165"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="5769d-103">为 Skype for Business Server 2015 中的持久聊天服务器配置高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="5769d-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5769d-104">**摘要:** 阅读本主题, 了解如何在 Skype for business Server 2015 中配置持久聊天服务器的高可用性和灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="5769d-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="5769d-105">Skype for Business 服务器支持对后端服务器的多个高可用性模式, 包括数据库镜像。</span><span class="sxs-lookup"><span data-stu-id="5769d-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="5769d-106">有关详细信息，请参阅[Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="5769d-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5769d-107">永久聊天服务器不支持 AlwaysOn 可用性组。</span><span class="sxs-lookup"><span data-stu-id="5769d-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 

> [!NOTE] 
> <span data-ttu-id="5769d-108">Skype for business Server 2015 中提供了持久聊天, 但 Skype for business Server 2019 不再支持此功能。</span><span class="sxs-lookup"><span data-stu-id="5769d-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="5769d-109">团队中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="5769d-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="5769d-110">有关详细信息, 请参阅[Microsoft 团队升级](/microsoftteams/upgrade-start-here)入门。</span><span class="sxs-lookup"><span data-stu-id="5769d-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="5769d-111">如果需要使用持久聊天, 您可以选择将需要此功能的用户迁移到团队, 或继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="5769d-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="5769d-112">在为高可用性和灾难恢复配置持久聊天部署之前, 请确保熟悉适用于[Skype for Business server 2015 中持久聊天服务器的高可用性和灾难恢复](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)的概念。</span><span class="sxs-lookup"><span data-stu-id="5769d-112">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="5769d-113">这些主题中所述的持久聊天服务器的灾难恢复解决方案是基于持续持续的持久聊天服务器池构建的。</span><span class="sxs-lookup"><span data-stu-id="5769d-113">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="5769d-114">规划内容介绍资源要求和延长的池拓扑, 该拓扑支持持久聊天服务器的高可用性和灾难恢复, 包括使用 SQL Server 镜像实现高可用性和 SQL Server 日志传送灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="5769d-114">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="5769d-115">使用拓扑生成器配置高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="5769d-115">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="5769d-116">在拓扑生成器中，执行以下步骤以为持久聊天服务器配置高可用性和灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="5769d-116">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="5769d-117">添加镜像数据库和日志传送辅助数据库 SQL Server 存储。</span><span class="sxs-lookup"><span data-stu-id="5769d-117">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="5769d-118">将持久聊天服务器服务属性编辑为:</span><span class="sxs-lookup"><span data-stu-id="5769d-118">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="5769d-119">a.</span><span class="sxs-lookup"><span data-stu-id="5769d-119">a.</span></span> <span data-ttu-id="5769d-120">为主数据库启用镜像。</span><span class="sxs-lookup"><span data-stu-id="5769d-120">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="5769d-121">b.</span><span class="sxs-lookup"><span data-stu-id="5769d-121">b.</span></span> <span data-ttu-id="5769d-122">添加主镜像 SQL Server 应用商店。</span><span class="sxs-lookup"><span data-stu-id="5769d-122">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="5769d-123">c.</span><span class="sxs-lookup"><span data-stu-id="5769d-123">c.</span></span> <span data-ttu-id="5769d-124">启用 SQL Server 日志传送数据库。</span><span class="sxs-lookup"><span data-stu-id="5769d-124">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="5769d-125">d.</span><span class="sxs-lookup"><span data-stu-id="5769d-125">d.</span></span> <span data-ttu-id="5769d-126">添加 SQL Server 日志传送辅助 SQL Server 应用商店。</span><span class="sxs-lookup"><span data-stu-id="5769d-126">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="5769d-127">e.i.</span><span class="sxs-lookup"><span data-stu-id="5769d-127">e.</span></span> <span data-ttu-id="5769d-128">为辅助数据库添加 SQL Server 应用商店镜像。</span><span class="sxs-lookup"><span data-stu-id="5769d-128">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="5769d-129">f.</span><span class="sxs-lookup"><span data-stu-id="5769d-129">f.</span></span> <span data-ttu-id="5769d-130">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="5769d-130">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="5769d-131">为持久聊天服务器主数据库设置 SQL Server 日志传送</span><span class="sxs-lookup"><span data-stu-id="5769d-131">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="5769d-132">使用 SQL Server Management Studio, 连接到持久聊天服务器辅助日志传送数据库实例, 并确保 SQL Server 代理正在运行。</span><span class="sxs-lookup"><span data-stu-id="5769d-132">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="5769d-133">然后, 连接到持久聊天主数据库实例并执行以下步骤:</span><span class="sxs-lookup"><span data-stu-id="5769d-133">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="5769d-134">右键单击 mgc 数据库，然后单击“**属性**”。</span><span class="sxs-lookup"><span data-stu-id="5769d-134">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="5769d-135">在“**选择页**”下，单击“**事务日志传送**”。</span><span class="sxs-lookup"><span data-stu-id="5769d-135">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="5769d-136">选中“**将此数据库启用为日志传送配置中的主数据库**”复选框。</span><span class="sxs-lookup"><span data-stu-id="5769d-136">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="5769d-137">在“**事务日志备份**”下，单击“**备份设置**”。</span><span class="sxs-lookup"><span data-stu-id="5769d-137">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="5769d-138">在“**备份文件夹的网络路径**”框中，键入您为事务日志备份文件夹创建的共享的网络路径。</span><span class="sxs-lookup"><span data-stu-id="5769d-138">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="5769d-p111">如果备份文件夹位于主服务器上，请在“**如果备份文件夹位于主服务器上，则键入该文件夹的本地路径(示例: c:\backup)**”框中键入该备份文件夹的本地路径。（如果备份文件夹不在主服务器上，则可将此框留空。）</span><span class="sxs-lookup"><span data-stu-id="5769d-p111">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5769d-141">如果主服务器上的 SQL Server 服务帐户在本地系统帐户下运行, 则必须在主服务器上创建备份文件夹, 并指定该文件夹的本地路径。</span><span class="sxs-lookup"><span data-stu-id="5769d-141">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="5769d-142">配置“**删除文件，如果其保留时间超过**”和“**在以下时间内没有执行备份时报警**”参数。</span><span class="sxs-lookup"><span data-stu-id="5769d-142">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="5769d-143">查看“**备份作业**”下的“**计划**”框中所列的备份计划。</span><span class="sxs-lookup"><span data-stu-id="5769d-143">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="5769d-144">若要自定义安装的计划, 请单击 "**计划**", 然后根据需要调整 SQL Server 代理计划。</span><span class="sxs-lookup"><span data-stu-id="5769d-144">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="5769d-145">在“**压缩**”下，选择“**使用默认服务器设置**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="5769d-145">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="5769d-146">在“**辅助服务器实例和数据库**”下，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="5769d-146">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="5769d-147">单击 "**连接**" 并连接到已配置为辅助服务器的 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="5769d-147">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="5769d-148">在“**辅助数据库**”框中，从列表中选择“**mgc**”数据库。</span><span class="sxs-lookup"><span data-stu-id="5769d-148">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="5769d-149">在 "**初始化辅助数据库**" 选项卡上, 选择 **"是, 生成主数据库的完整备份", 然后将其还原到辅助数据库 (如果不存在, 则创建辅助数据库)**。</span><span class="sxs-lookup"><span data-stu-id="5769d-149">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="5769d-150">在 "**复制文件**" 选项卡上的 "**复制的文件的目标文件夹**" 框中, 键入应将事务日志备份复制到其中的文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="5769d-150">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="5769d-151">此文件夹通常位于辅助服务器上。</span><span class="sxs-lookup"><span data-stu-id="5769d-151">This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="5769d-152">请注意 "**复制作业**" 下的 "**日程安排**" 框中列出的复制计划。</span><span class="sxs-lookup"><span data-stu-id="5769d-152">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="5769d-153">若要自定义安装的计划, 请单击 "**计划**", 然后根据需要调整 SQL Server 代理计划。</span><span class="sxs-lookup"><span data-stu-id="5769d-153">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="5769d-154">此计划应该与备份计划大致相同。</span><span class="sxs-lookup"><span data-stu-id="5769d-154">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="5769d-155">在 "**还原**" 选项卡上的 "**还原备份时数据库状态**" 下, 选择 "**无恢复模式**" 选项。</span><span class="sxs-lookup"><span data-stu-id="5769d-155">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="5769d-156">在 "**延迟还原备份至少:**" 下, 选择 " **0 分钟**"。</span><span class="sxs-lookup"><span data-stu-id="5769d-156">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="5769d-157">**如果未在内进行还原**, 请在 "警报" 下选择警报阈值。</span><span class="sxs-lookup"><span data-stu-id="5769d-157">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="5769d-158">查看 "**还原作业**" 下的 "**日程安排**" 框中列出的还原计划。</span><span class="sxs-lookup"><span data-stu-id="5769d-158">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="5769d-159">若要自定义安装的计划, 请单击 "**计划**", 根据需要调整 SQL Server 代理计划, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="5769d-159">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="5769d-160">此计划应该与备份计划大致相同。</span><span class="sxs-lookup"><span data-stu-id="5769d-160">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="5769d-161">在 "**数据库属性**" 对话框中, 单击 **"确定"** 开始配置过程。</span><span class="sxs-lookup"><span data-stu-id="5769d-161">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="5769d-162">在主镜像和辅助数据库之间设置 SQL Server 日志传送</span><span class="sxs-lookup"><span data-stu-id="5769d-162">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="5769d-163">如果主持久聊天数据库故障转移到其镜像数据库, 请执行以下步骤, 以使日志传送继续进行。</span><span class="sxs-lookup"><span data-stu-id="5769d-163">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="5769d-164">将主持久聊天数据库手动故障转移到镜像。</span><span class="sxs-lookup"><span data-stu-id="5769d-164">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="5769d-165">这可通过使用 Skype for Business 服务器命令行管理程序和**CsDatabaseFailover** cmdlet 完成。</span><span class="sxs-lookup"><span data-stu-id="5769d-165">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="5769d-166">使用 SQL Server Management Studio 连接到主持久聊天服务器镜像实例。</span><span class="sxs-lookup"><span data-stu-id="5769d-166">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="5769d-167">请确保 SQL Server 代理正在运行。</span><span class="sxs-lookup"><span data-stu-id="5769d-167">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="5769d-168">右键单击 mgc 数据库，然后单击“**属性**”。</span><span class="sxs-lookup"><span data-stu-id="5769d-168">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="5769d-169">在“**选择页**”下，单击“**事务日志传送**”。</span><span class="sxs-lookup"><span data-stu-id="5769d-169">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="5769d-170">选中“**将此数据库启用为日志传送配置中的主数据库**”复选框。</span><span class="sxs-lookup"><span data-stu-id="5769d-170">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="5769d-171">在“**事务日志备份**”下，单击“**备份设置**”。</span><span class="sxs-lookup"><span data-stu-id="5769d-171">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="5769d-172">在 "**备份文件夹的网络路径**" 框中, 键入为 "事务日志备份" 文件夹创建的共享的网络路径。</span><span class="sxs-lookup"><span data-stu-id="5769d-172">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="5769d-173">如果备份文件夹位于主服务器上, 请在 "**如果备份文件夹位于主服务器上**" 中键入备份文件夹的本地路径, 请在 "文件夹" 框中键入本地路径。</span><span class="sxs-lookup"><span data-stu-id="5769d-173">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box.</span></span> <span data-ttu-id="5769d-174">(如果备份文件夹不在主服务器上, 你可以将此框留空。)</span><span class="sxs-lookup"><span data-stu-id="5769d-174">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5769d-175">如果主服务器上的 SQL Server 服务帐户在本地系统帐户下运行, 则必须在主服务器上创建备份文件夹, 并指定该文件夹的本地路径。</span><span class="sxs-lookup"><span data-stu-id="5769d-175">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="5769d-176">配置“**删除文件，如果其保留时间超过**”和“**在以下时间内没有执行备份时报警**”参数。</span><span class="sxs-lookup"><span data-stu-id="5769d-176">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="5769d-177">查看“**备份作业**”下的“**计划**”框中所列的备份计划。</span><span class="sxs-lookup"><span data-stu-id="5769d-177">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="5769d-178">若要自定义安装的计划, 请单击 "**计划**", 然后根据需要调整 SQL Server 代理计划。</span><span class="sxs-lookup"><span data-stu-id="5769d-178">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5769d-179">使用您用于主数据库的相同设置。</span><span class="sxs-lookup"><span data-stu-id="5769d-179">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="5769d-180">在 "**压缩**" 下, 选择 "**使用默认服务器设置**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="5769d-180">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="5769d-181">在“**辅助服务器实例和数据库**”下，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="5769d-181">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="5769d-182">单击 "**连接**", 并连接到已配置为辅助服务器的 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="5769d-182">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="5769d-183">在“**辅助数据库**”框中，从列表中选择“**mgc**”数据库。</span><span class="sxs-lookup"><span data-stu-id="5769d-183">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="5769d-184">在 "**初始化辅助数据库**" 选项卡上, 选择 "**否, 辅助数据库已初始化**"。</span><span class="sxs-lookup"><span data-stu-id="5769d-184">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="5769d-185">在 "**复制**文件" 选项卡上, 在 "**复制的文件的目标文件夹**" 中, 键入应将事务日志备份复制到其中的文件夹的路径, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="5769d-185">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**.</span></span> <span data-ttu-id="5769d-186">此文件夹通常位于辅助服务器上。</span><span class="sxs-lookup"><span data-stu-id="5769d-186">This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="5769d-187">打开 "**脚本配置**" 下拉列表, 然后选择 "**对新查询进行脚本配置" 窗口**。</span><span class="sxs-lookup"><span data-stu-id="5769d-187">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="5769d-188">在 "新建查询" 窗口的 "**数据库属性**" 中, 单击 **"确定"** 开始配置过程。</span><span class="sxs-lookup"><span data-stu-id="5769d-188">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="5769d-189">选择并运行查询的第一半 (请参阅步骤 18 \* \* \* \* \* \* ) 至行:--结束: 要在主要\* \* \* \* \* \*位置运行的脚本:。</span><span class="sxs-lookup"><span data-stu-id="5769d-189">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5769d-190">必须手动运行此脚本, 因为 SQL Server Management Studio 不支持 SQL Server 日志传送配置中的多个主数据库。</span><span class="sxs-lookup"><span data-stu-id="5769d-190">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="5769d-191">选择 "**取消**" 以关闭日志文件传输配置面板, 并建立可正确为主数据库和镜像数据库 (如果故障转移) 实现日志文件传送的工作设置。</span><span class="sxs-lookup"><span data-stu-id="5769d-191">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="5769d-192">将主持久聊天数据库手动故障恢复到主数据库。</span><span class="sxs-lookup"><span data-stu-id="5769d-192">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="5769d-193">这是通过使用 Skype for Business 服务器命令行管理程序和**CsDatabaseFailover** cmdlet 完成的。</span><span class="sxs-lookup"><span data-stu-id="5769d-193">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

