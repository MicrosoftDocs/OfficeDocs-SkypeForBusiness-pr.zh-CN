---
title: Lync Server 2013：为持久聊天服务器主数据库设置 SQL Server 日志传送
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up SQL Server Log Shipping for the Persistent Chat Server primary database
ms:assetid: 088ea1c2-d592-4a11-b3b8-f1e2f8beae93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204653(v=OCS.15)
ms:contentKeyID: 48183337
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0de2285d77ba2228b90d244c841efc0b986bf454
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845882"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="5446c-102">在 Lync Server 2013 中为持久聊天服务器主数据库设置 SQL Server 日志传送</span><span class="sxs-lookup"><span data-stu-id="5446c-102">Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5446c-103">_**主题上次修改时间:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="5446c-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="5446c-104">使用 SQL Server Management Studio, 连接到持久聊天服务器辅助日志传送数据库实例, 并确保 SQL Server 代理正在运行。</span><span class="sxs-lookup"><span data-stu-id="5446c-104">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span>

<span data-ttu-id="5446c-105">使用连接到持久聊天主数据库实例的 SQL Server Management Studio, 请执行以下步骤:</span><span class="sxs-lookup"><span data-stu-id="5446c-105">Using SQL Server Management Studio connected to the Persistent Chat primary database instance, perform the following steps:</span></span>

1.  <span data-ttu-id="5446c-106">请确保 SQL Server 代理正在运行。</span><span class="sxs-lookup"><span data-stu-id="5446c-106">Be sure that the SQL Server Agent is running.</span></span>

2.  <span data-ttu-id="5446c-107">右键单击 mgc 数据库，然后单击“**属性**”。</span><span class="sxs-lookup"><span data-stu-id="5446c-107">Right-click the mgc database, and then click **Properties**.</span></span>

3.  <span data-ttu-id="5446c-108">在“**选择页**”下，单击“**事务日志传送**”。</span><span class="sxs-lookup"><span data-stu-id="5446c-108">Under **Select a page**, click **Transaction Log Shipping**.</span></span>

4.  <span data-ttu-id="5446c-109">选中“**将此数据库启用为日志传送配置中的主数据库**”复选框。</span><span class="sxs-lookup"><span data-stu-id="5446c-109">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>

5.  <span data-ttu-id="5446c-110">在“**事务日志备份**”下，单击“**备份设置**”。</span><span class="sxs-lookup"><span data-stu-id="5446c-110">Under **Transaction log backups**, click **Backup Settings**.</span></span>

6.  <span data-ttu-id="5446c-111">在“**备份文件夹的网络路径**”框中，键入您为事务日志备份文件夹创建的共享的网络路径。</span><span class="sxs-lookup"><span data-stu-id="5446c-111">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>

7.  <span data-ttu-id="5446c-112">如果备份文件夹位于主服务器上, 请在 "如果备份文件夹位于主服务器上" 中键入备份文件夹的本地路径 **, 请键入文件夹的本地路径 (例如: c:\\backup)** 框。</span><span class="sxs-lookup"><span data-stu-id="5446c-112">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\\backup)** box.</span></span> <span data-ttu-id="5446c-113">(如果备份文件夹不在主服务器上, 你可以将此框留空。)</span><span class="sxs-lookup"><span data-stu-id="5446c-113">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5446c-114">如果主服务器上的 SQL Server 服务帐户在本地系统帐户下运行, 则必须在主服务器上创建备份文件夹, 并指定该文件夹的本地路径。</span><span class="sxs-lookup"><span data-stu-id="5446c-114">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>

    
    </div>

8.  <span data-ttu-id="5446c-115">配置“**删除文件，如果其保留时间超过**”和“**在以下时间内没有执行备份时报警**”参数。</span><span class="sxs-lookup"><span data-stu-id="5446c-115">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>

9.  <span data-ttu-id="5446c-116">查看“**备份作业**”下的“**计划**”框中所列的备份计划。</span><span class="sxs-lookup"><span data-stu-id="5446c-116">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="5446c-117">若要自定义安装的计划, 请单击 "**计划**", 然后根据需要调整 SQL Server 代理计划。</span><span class="sxs-lookup"><span data-stu-id="5446c-117">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>

10. <span data-ttu-id="5446c-118">在“**压缩**”下，选择“**使用默认服务器设置**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="5446c-118">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>

11. <span data-ttu-id="5446c-119">在“**辅助服务器实例和数据库**”下，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="5446c-119">Under **Secondary server instances and databases**, click **Add**.</span></span>

12. <span data-ttu-id="5446c-120">单击 "**连接**" 并连接到已配置为辅助服务器的 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="5446c-120">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>

13. <span data-ttu-id="5446c-121">在“**辅助数据库**”框中，从列表中选择“**mgc**”数据库。</span><span class="sxs-lookup"><span data-stu-id="5446c-121">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>

14. <span data-ttu-id="5446c-122">在 "**初始化辅助数据库**" 选项卡上, 选择 **"是, 生成主数据库的完整备份", 然后将其还原到辅助数据库 (如果不存在, 则创建辅助数据库)**。</span><span class="sxs-lookup"><span data-stu-id="5446c-122">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>

15. <span data-ttu-id="5446c-123">在 "**复制文件**" 选项卡上的 "**复制的文件的目标文件夹**" 框中, 键入应将事务日志备份复制到其中的文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="5446c-123">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="5446c-124">此文件夹通常位于辅助服务器上。</span><span class="sxs-lookup"><span data-stu-id="5446c-124">This folder is often located on the secondary server.</span></span>

16. <span data-ttu-id="5446c-125">请注意 "**复制作业**" 下的 "**日程安排**" 框中列出的复制计划。</span><span class="sxs-lookup"><span data-stu-id="5446c-125">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="5446c-126">若要自定义安装的计划, 请单击 "**计划**", 然后根据需要调整 SQL Server 代理计划。</span><span class="sxs-lookup"><span data-stu-id="5446c-126">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="5446c-127">此计划应该与备份计划大致相同。</span><span class="sxs-lookup"><span data-stu-id="5446c-127">This schedule should be approximately the same as the backup schedule.</span></span>

17. <span data-ttu-id="5446c-128">在 "**还原**" 选项卡上的 "**还原备份时数据库状态**" 下, 选择 "**无恢复模式**" 选项。</span><span class="sxs-lookup"><span data-stu-id="5446c-128">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>

18. <span data-ttu-id="5446c-129">在 "**延迟还原备份至少:**" 下, 选择 " **0 分钟**"。</span><span class="sxs-lookup"><span data-stu-id="5446c-129">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>

19. <span data-ttu-id="5446c-130">**如果未在内进行还原**, 请在 "警报" 下选择警报阈值。</span><span class="sxs-lookup"><span data-stu-id="5446c-130">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>

20. <span data-ttu-id="5446c-131">查看 "**还原作业**" 下的 "**日程安排**" 框中列出的还原计划。</span><span class="sxs-lookup"><span data-stu-id="5446c-131">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="5446c-132">若要自定义安装的计划, 请单击 "**计划**", 根据需要调整 SQL Server 代理计划, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="5446c-132">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="5446c-133">此计划应该与备份计划大致相同。</span><span class="sxs-lookup"><span data-stu-id="5446c-133">This schedule should be approximately the same as the backup schedule.</span></span>

21. <span data-ttu-id="5446c-134">在 "**数据库属性**" 对话框中, 单击 **"确定"** 开始配置过程。</span><span class="sxs-lookup"><span data-stu-id="5446c-134">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

