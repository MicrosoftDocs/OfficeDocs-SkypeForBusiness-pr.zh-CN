---
title: Lync Server 2013：在主镜像和日志传送辅助数据库之间设置 SQL Server 日志传送
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database
ms:assetid: 4e8e9ce9-4301-47f2-a0c3-669afeb53295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204887(v=OCS.15)
ms:contentKeyID: 48184119
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3758e654826de42f6bf6bed8ead29ce03adb6ca5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database-in-lync-server-2013"></a><span data-ttu-id="0cae3-102">在 Lync Server 2013 中在主镜像和日志传送辅助数据库之间设置 SQL Server 日志传送</span><span class="sxs-lookup"><span data-stu-id="0cae3-102">Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cae3-103">_**主题上次修改时间:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="0cae3-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="0cae3-104">如果主持久聊天数据库故障转移到其镜像数据库, 请执行以下步骤, 以使日志传送继续进行。</span><span class="sxs-lookup"><span data-stu-id="0cae3-104">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>

1.  <span data-ttu-id="0cae3-105">将主持久聊天数据库手动故障转移到镜像。</span><span class="sxs-lookup"><span data-stu-id="0cae3-105">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="0cae3-106">这可通过使用 Lync Server 命令行管理程序和**CsDatabaseFailover** cmdlet 来完成。</span><span class="sxs-lookup"><span data-stu-id="0cae3-106">This is done by using the Lync Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span> <span data-ttu-id="0cae3-107">有关详细信息, 请参阅在[Lync server 2013 中部署 SQL 镜像以获得后端服务器高可用性](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)的 "使用 Lync Server Management Shell cmdlet"。</span><span class="sxs-lookup"><span data-stu-id="0cae3-107">For details, see "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

2.  <span data-ttu-id="0cae3-108">使用 SQL Server Management Studio 连接到主持久聊天服务器镜像实例。</span><span class="sxs-lookup"><span data-stu-id="0cae3-108">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>

3.  <span data-ttu-id="0cae3-109">请确保 SQL Server 代理正在运行。</span><span class="sxs-lookup"><span data-stu-id="0cae3-109">Be sure that the SQL Server Agent is running.</span></span>

4.  <span data-ttu-id="0cae3-110">右键单击 mgc 数据库，然后单击“**属性**”。</span><span class="sxs-lookup"><span data-stu-id="0cae3-110">Right-click the mgc database, and then click **Properties**.</span></span>

5.  <span data-ttu-id="0cae3-111">在“**选择页**”下，单击“**事务日志传送**”。</span><span class="sxs-lookup"><span data-stu-id="0cae3-111">Under **Select a page**, click **Transaction Log Shipping**.</span></span>

6.  <span data-ttu-id="0cae3-112">选中“**将此数据库启用为日志传送配置中的主数据库**”复选框。</span><span class="sxs-lookup"><span data-stu-id="0cae3-112">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>

7.  <span data-ttu-id="0cae3-113">在“**事务日志备份**”下，单击“**备份设置**”。</span><span class="sxs-lookup"><span data-stu-id="0cae3-113">Under **Transaction log backups**, click **Backup Settings**.</span></span>

8.  <span data-ttu-id="0cae3-114">在 "**备份文件夹的网络路径**" 框中, 键入为 "事务日志备份" 文件夹创建的共享的网络路径。</span><span class="sxs-lookup"><span data-stu-id="0cae3-114">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>

9.  <span data-ttu-id="0cae3-115">如果备份文件夹位于主服务器上, 请在 "**如果备份文件夹位于主服务器上**" 中键入备份文件夹的本地路径, 请在 "文件夹" 框中键入本地路径。</span><span class="sxs-lookup"><span data-stu-id="0cae3-115">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box.</span></span> <span data-ttu-id="0cae3-116">(如果备份文件夹不在主服务器上, 你可以将此框留空。)</span><span class="sxs-lookup"><span data-stu-id="0cae3-116">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0cae3-117">如果主服务器上的 SQL Server 服务帐户在本地系统帐户下运行, 则必须在主服务器上创建备份文件夹, 并指定该文件夹的本地路径。</span><span class="sxs-lookup"><span data-stu-id="0cae3-117">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>

    
    </div>

10. <span data-ttu-id="0cae3-118">配置“**删除文件，如果其保留时间超过**”和“**在以下时间内没有执行备份时报警**”参数。</span><span class="sxs-lookup"><span data-stu-id="0cae3-118">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>

11. <span data-ttu-id="0cae3-119">查看“**备份作业**”下的“**计划**”框中所列的备份计划。</span><span class="sxs-lookup"><span data-stu-id="0cae3-119">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="0cae3-120">若要自定义安装的计划, 请单击 "**计划**", 然后根据需要调整 SQL Server 代理计划。</span><span class="sxs-lookup"><span data-stu-id="0cae3-120">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0cae3-121">使用您用于主数据库的相同设置。</span><span class="sxs-lookup"><span data-stu-id="0cae3-121">Use the same settings that you used for the primary database.</span></span>

    
    </div>

12. <span data-ttu-id="0cae3-122">在 "**压缩**" 下, 选择 "**使用默认服务器设置**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="0cae3-122">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>

13. <span data-ttu-id="0cae3-123">在“**辅助服务器实例和数据库**”下，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="0cae3-123">Under **Secondary server instances and databases**, click **Add**.</span></span>

14. <span data-ttu-id="0cae3-124">单击 "**连接**", 并连接到已配置为辅助服务器的 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="0cae3-124">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>

15. <span data-ttu-id="0cae3-125">在“**辅助数据库**”框中，从列表中选择“**mgc**”数据库。</span><span class="sxs-lookup"><span data-stu-id="0cae3-125">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>

16. <span data-ttu-id="0cae3-126">在 "**初始化辅助数据库**" 选项卡上, 选择 "**否, 辅助数据库已初始化**"。</span><span class="sxs-lookup"><span data-stu-id="0cae3-126">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>

17. <span data-ttu-id="0cae3-127">在 "**复制**文件" 选项卡上, 在 "**复制的文件的目标文件夹**" 中, 键入应将事务日志备份复制到其中的文件夹的路径, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="0cae3-127">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**.</span></span> <span data-ttu-id="0cae3-128">此文件夹通常位于辅助服务器上。</span><span class="sxs-lookup"><span data-stu-id="0cae3-128">This folder is often located on the secondary server.</span></span>

18. <span data-ttu-id="0cae3-129">打开 "**脚本配置**" 下拉列表, 然后选择 "**对新查询进行脚本配置" 窗口**。</span><span class="sxs-lookup"><span data-stu-id="0cae3-129">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>

19. <span data-ttu-id="0cae3-130">在 "新建查询" 窗口的 "**数据库属性**" 中, 单击 **"确定"** 开始配置过程。</span><span class="sxs-lookup"><span data-stu-id="0cae3-130">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>

20. <span data-ttu-id="0cae3-131">选择并运行查询的第一半 (请参阅步骤 18 \* \* \* \* \* \* ) 至行:--结束: 要在主要\* \* \* \* \* \*位置运行的脚本:。</span><span class="sxs-lookup"><span data-stu-id="0cae3-131">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0cae3-132">必须手动运行此脚本, 因为 SQL Server Management Studio 不支持 SQL Server 日志传送配置中的多个主数据库。</span><span class="sxs-lookup"><span data-stu-id="0cae3-132">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span>

    
    </div>

21. <span data-ttu-id="0cae3-133">选择 "**取消**" 以关闭日志文件传输配置面板, 并建立可正确为主数据库和镜像数据库 (如果故障转移) 实现日志文件传送的工作设置。</span><span class="sxs-lookup"><span data-stu-id="0cae3-133">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>

22. <span data-ttu-id="0cae3-134">将主持久聊天数据库手动故障恢复到主数据库。</span><span class="sxs-lookup"><span data-stu-id="0cae3-134">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="0cae3-135">这可通过使用 Lync Server 命令行管理程序和**CsDatabaseFailover** cmdlet 来完成。</span><span class="sxs-lookup"><span data-stu-id="0cae3-135">This is done by using the Lync Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span> <span data-ttu-id="0cae3-136">有关详细信息, 请参阅在[Lync server 2013 中部署 SQL 镜像以获得后端服务器高可用性](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)的 "使用 Lync Server Management Shell cmdlet"。</span><span class="sxs-lookup"><span data-stu-id="0cae3-136">For details, see "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="0cae3-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0cae3-137">See Also</span></span>


[<span data-ttu-id="0cae3-138">在 Lync Server 2013 中针对后端服务器高可用性部署 SQL 镜像</span><span class="sxs-lookup"><span data-stu-id="0cae3-138">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
[<span data-ttu-id="0cae3-139">在 Lync Server 2013 中针对后端服务器高可用性部署 SQL 镜像</span><span class="sxs-lookup"><span data-stu-id="0cae3-139">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

