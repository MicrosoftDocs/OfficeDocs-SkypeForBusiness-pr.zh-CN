---
title: 针对后端服务器高可用性部署 SQL 镜像
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying SQL mirroring for Back End Server high availability
ms:assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204992(v=OCS.15)
ms:contentKeyID: 48184451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8eb8c9647c24f326b1a2a51c99e7fa4ee5eafa23
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-sql-mirroring-for-back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="c3931-102">在 Lync Server 2013 中针对后端服务器高可用性部署 SQL 镜像</span><span class="sxs-lookup"><span data-stu-id="c3931-102">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3931-103">_**主题上次修改时间:** 2014-01-08_</span><span class="sxs-lookup"><span data-stu-id="c3931-103">_**Topic Last Modified:** 2014-01-08_</span></span>

<span data-ttu-id="c3931-104">为了能够部署 SQL 镜像，你的服务器必须至少运行 SQL Server 2008 R2。</span><span class="sxs-lookup"><span data-stu-id="c3931-104">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="c3931-105">此版本必须在所有涉及的服务器上运行：主服务器、镜像服务器和见证服务器。</span><span class="sxs-lookup"><span data-stu-id="c3931-105">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="c3931-106">有关详细信息, [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921)请参阅。</span><span class="sxs-lookup"><span data-stu-id="c3931-106">For details, see [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921).</span></span>

<span data-ttu-id="c3931-107">通常，在两台具有见证的后端服务器之间设置 SQL 镜像需要满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="c3931-107">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>

  - <span data-ttu-id="c3931-108">主服务器的 SQL Server 版本必须支持 SQL 镜像。</span><span class="sxs-lookup"><span data-stu-id="c3931-108">The primary server’s version of SQL Server must support SQL mirroring.</span></span>

  - <span data-ttu-id="c3931-109">主、镜像和见证（如果部署）必须具有同一版本的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="c3931-109">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span>

  - <span data-ttu-id="c3931-p102">主和镜像必须具有同一版本的 SQL Server。见证可以具有不同版本。</span><span class="sxs-lookup"><span data-stu-id="c3931-p102">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>

<span data-ttu-id="c3931-112">有关见证角色支持哪些 SQL 版本的 SQL 最佳做法, 请参阅 MSDN 库中的 "数据库镜像见证" [http://go.microsoft.com/fwlink/p/?LinkId=247345](http://go.microsoft.com/fwlink/p/?linkid=247345)。</span><span class="sxs-lookup"><span data-stu-id="c3931-112">For SQL best practices in terms of what SQL versions are supported for a Witness role, see "Database Mirroring Witness" in the MSDN Library at [http://go.microsoft.com/fwlink/p/?LinkId=247345](http://go.microsoft.com/fwlink/p/?linkid=247345).</span></span>

<span data-ttu-id="c3931-113">使用拓扑生成器部署 SQL 镜像。</span><span class="sxs-lookup"><span data-stu-id="c3931-113">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="c3931-114">在 "拓扑生成器" 中选择一个选项以镜像数据库, 拓扑生成器将在发布拓扑时设置镜像 (包括设置见证 (如果需要)。</span><span class="sxs-lookup"><span data-stu-id="c3931-114">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="c3931-115">请注意，设置或删除见证服务器会同时设置或删除镜像服务器。</span><span class="sxs-lookup"><span data-stu-id="c3931-115">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="c3931-116">没有用于仅部署或删除见证服务器的单独命令。</span><span class="sxs-lookup"><span data-stu-id="c3931-116">There is no separate command to deploy or remove only a witness.</span></span>

<span data-ttu-id="c3931-117">要配置服务器镜像，必须正确设置 SQL 数据库权限。</span><span class="sxs-lookup"><span data-stu-id="c3931-117">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="c3931-118">有关详细信息, 请参阅 "为数据库镜像或 AlwaysOn 可用性组 (SQL Server) 设置登录帐户" [http://go.microsoft.com/fwlink/p/?LinkId=268454](http://go.microsoft.com/fwlink/p/?linkid=268454)。</span><span class="sxs-lookup"><span data-stu-id="c3931-118">For details, see "Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268454](http://go.microsoft.com/fwlink/p/?linkid=268454).</span></span>

<span data-ttu-id="c3931-p105">对于 SQL 镜像，数据库恢复模式始终设置为“**完全**”，这意味着你必须密切监控事务日志大小并定期备份事务日志以避免后端服务器上的磁盘空间不足。事务日志备份频率取决于日志增长速率，反过来，日志增长速率又取决于前端池上的用户活动所触发的数据库事务数。建议你确定你的 Lync 部署工作负载所需的事务日志增长程度，以便进行适当的规划。下列文章提供了有关 SQL 备份和日志管理的其他信息：</span><span class="sxs-lookup"><span data-stu-id="c3931-p105">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your Lync deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>

  - <span data-ttu-id="c3931-123">数据库恢复模型: "恢复模型 (SQL Server)"[http://go.microsoft.com/fwlink/p/?LinkId=268446](http://go.microsoft.com/fwlink/p/?linkid=268446)</span><span class="sxs-lookup"><span data-stu-id="c3931-123">Database recovery models: "Recovery Models (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268446](http://go.microsoft.com/fwlink/p/?linkid=268446)</span></span>

  - <span data-ttu-id="c3931-124">备份概述: "备份概述 (SQL Server)"[http://go.microsoft.com/fwlink/p/?LinkId=268449](http://go.microsoft.com/fwlink/p/?linkid=268449)</span><span class="sxs-lookup"><span data-stu-id="c3931-124">Backup overview: "Backup Overview (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268449](http://go.microsoft.com/fwlink/p/?linkid=268449)</span></span>

  - <span data-ttu-id="c3931-125">备份事务日志: "备份事务日志 (SQL Server)"[http://go.microsoft.com/fwlink/p/?LinkId=268452](http://go.microsoft.com/fwlink/p/?linkid=268452)</span><span class="sxs-lookup"><span data-stu-id="c3931-125">Backup transaction log: "Backup a Transaction Log (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268452](http://go.microsoft.com/fwlink/p/?linkid=268452)</span></span>

<span data-ttu-id="c3931-126">对于 SQL 镜像，可在创建池时或之后为镜像配置拓扑。</span><span class="sxs-lookup"><span data-stu-id="c3931-126">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>



> [!IMPORTANT]
> <span data-ttu-id="c3931-127">仅当主映像、镜像和见证 (如果需要) 服务器都属于同一域时, 才支持使用拓扑生成器或 cmdlet 来设置和删除 SQL 镜像。</span><span class="sxs-lookup"><span data-stu-id="c3931-127">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="c3931-128">如果您需要在不同域中的服务器之间设置 SQL 镜像，请参阅 SQL Server 文档。</span><span class="sxs-lookup"><span data-stu-id="c3931-128">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span>





> [!IMPORTANT]
> <span data-ttu-id="c3931-129">只要更改了后端数据库镜像关系，就必须重新启动池中的所有前端服务器。</span><span class="sxs-lookup"><span data-stu-id="c3931-129">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span><BR><span data-ttu-id="c3931-130">对于镜像更改 (如更改镜像的位置), 必须使用拓扑生成器执行以下三个步骤:</span><span class="sxs-lookup"><span data-stu-id="c3931-130">For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="c3931-131">从旧镜像服务器中删除镜像。</span><span class="sxs-lookup"><span data-stu-id="c3931-131">Remove mirroring from the old mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="c3931-132">向新镜像服务器中添加镜像。</span><span class="sxs-lookup"><span data-stu-id="c3931-132">Add mirroring to the new mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="c3931-133">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="c3931-133">Publish the topology.</span></span></P></LI></OL>




> [!NOTE]
> <span data-ttu-id="c3931-134">必须为要写入到的镜像文件创建文件共享，SQL Server 和 SQL 代理在其下运行的服务需要读取/写入访问权限。</span><span class="sxs-lookup"><span data-stu-id="c3931-134">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="c3931-135">如果 SQL Server 服务在网络服务上下文下运行, 则&lt;可以将域&gt;&#92;&lt;SQLSERVERNAME&gt;$ 和镜像 SQL server 添加到共享权限。</span><span class="sxs-lookup"><span data-stu-id="c3931-135">If the SQL Server service is running under the context of Network Service, you can add &lt;Domain&gt;&#92;&lt;SQLSERVERNAME&gt;$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="c3931-136">$ 非常重要，可用于标识这是一个计算机帐户。</span><span class="sxs-lookup"><span data-stu-id="c3931-136">The $ is important to identify that this is a computer account.</span></span>


<div>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="c3931-137">在拓扑生成器中创建池时配置 SQL 镜像</span><span class="sxs-lookup"><span data-stu-id="c3931-137">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1.  <span data-ttu-id="c3931-138">在“**定义 SQL 存储**”页上，单击“**SQL 存储**”框旁边的“**新建**”。</span><span class="sxs-lookup"><span data-stu-id="c3931-138">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>

2.  <span data-ttu-id="c3931-139">在“**定义新的 SQL 存储**”页上，指定主存储，选择“**此 SQL 实例处于镜像关系中**”，指定 SQL 镜像端口号（默认为 5022），然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="c3931-139">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>

3.  <span data-ttu-id="c3931-140">返回到“**定义 SQL 存储**”页，选中“**启用 SQL 存储镜像**”。</span><span class="sxs-lookup"><span data-stu-id="c3931-140">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span>

4.  <span data-ttu-id="c3931-p108">在“**定义新的 SQL 存储**”页中，指定要用作镜像的 SQL 存储，选择“**此 SQL 实例处于镜像关系中**”，指定端口号（默认为 5022），然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="c3931-p108">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror. Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="c3931-143">如果要将见证服务器用于此镜像，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c3931-143">If you want a witness for this mirror, do the following:</span></span>
    
    1.  <span data-ttu-id="c3931-144">选中“**使用 SQL 镜像见证启用自动故障转移**”。</span><span class="sxs-lookup"><span data-stu-id="c3931-144">Select **Use SQL mirroring witness to enable automatic failover**.</span></span>
    
    2.  <span data-ttu-id="c3931-145">在“**定义 SQL 存储**”页中，选中“**使用 SQL 镜像见证启用自动故障转移**”，并指定要用作见证服务器的 SQL 存储。</span><span class="sxs-lookup"><span data-stu-id="c3931-145">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span>
    
    3.  <span data-ttu-id="c3931-146">指定端口号（默认为 7022）并单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="c3931-146">Specify the port number (the default is 7022) and click **OK**.</span></span>

6.  <span data-ttu-id="c3931-147">在你的拓扑中定义完你的前端池和所有其他角色后, 请使用拓扑生成器发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="c3931-147">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="c3931-148">当发布拓扑时, 如果承载中央管理存储的前端池已启用 SQL 镜像, 你将看到创建主 SQL 应用商店数据库和镜像 SQL 应用商店数据库的选项。</span><span class="sxs-lookup"><span data-stu-id="c3931-148">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>
    
    <span data-ttu-id="c3931-149">单击“**设置**”，并键入要用作镜像备份的文件共享的路径。</span><span class="sxs-lookup"><span data-stu-id="c3931-149">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>
    
    <span data-ttu-id="c3931-p110">单击“**确定**”，然后单击“**下一步**”以创建数据库并发布拓扑。这将部署镜像服务器和见证服务器（如果已指定）。</span><span class="sxs-lookup"><span data-stu-id="c3931-p110">Click **OK** and then **Next** to create the databases and publish the topology. The mirroring and the witness (if specified) will be deployed.</span></span>

<span data-ttu-id="c3931-152">你可以使用拓扑生成器编辑现有池的属性, 以启用 SQL 镜像。</span><span class="sxs-lookup"><span data-stu-id="c3931-152">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span>

</div>

<div>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="c3931-153">在拓扑生成器中向现有前端池添加 SQL 镜像</span><span class="sxs-lookup"><span data-stu-id="c3931-153">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1.  <span data-ttu-id="c3931-154">在拓扑生成器中, 右键单击池, 然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="c3931-154">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="c3931-155">选中“**启用 SQL 存储镜像**”，然后单击“**镜像 SQL 存储**”旁边的“**新建**”。</span><span class="sxs-lookup"><span data-stu-id="c3931-155">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span>

3.  <span data-ttu-id="c3931-156">指定要用作镜像的 SQL 存储。</span><span class="sxs-lookup"><span data-stu-id="c3931-156">Specify the SQL store that you want to use as the mirror.</span></span>

4.  <span data-ttu-id="c3931-157">选择“**此 SQL 实例处于镜像关系中**”，指定 SQL 镜像端口号（默认端口为 5022），然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="c3931-157">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="c3931-158">如果要配置见证服务器，请选中“**使用 SQL 镜像见证启用自动故障转移**”，然后单击“**新建**”。</span><span class="sxs-lookup"><span data-stu-id="c3931-158">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span>

6.  <span data-ttu-id="c3931-159">指定要用作见证服务器的 SQL 存储。</span><span class="sxs-lookup"><span data-stu-id="c3931-159">Specify the SQL store that you want to use as the witness.</span></span>

7.  <span data-ttu-id="c3931-160">选择“**此 SQL 实例处于镜像关系中**”，指定 SQL 镜像端口号（默认端口为 7022），然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="c3931-160">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>

8.  <span data-ttu-id="c3931-161">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="c3931-161">Click **OK**.</span></span>

9.  <span data-ttu-id="c3931-p111">发布拓扑。在执行此操作时，系统会提示你安装数据库。</span><span class="sxs-lookup"><span data-stu-id="c3931-p111">Publish the topology. When you do so, you will be prompted to install the database.</span></span>
    
    <span data-ttu-id="c3931-p112">在拓扑发布过程中，系统将要求你定义文件共享路径。参与镜像的 SQL Server 必须对此文件共享具有读取/写入访问权限，才能建立镜像。</span><span class="sxs-lookup"><span data-stu-id="c3931-p112">During the topology publishing process, you will be asked to define a file share path. The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>

<span data-ttu-id="c3931-166">然后必须在继续下一步之前安装数据库。</span><span class="sxs-lookup"><span data-stu-id="c3931-166">You must then install the database before going on to the next procedure.</span></span>

<span data-ttu-id="c3931-167">设置 SQL 镜像时，应谨记以下几点：</span><span class="sxs-lookup"><span data-stu-id="c3931-167">You should keep the following in mind when setting up SQL mirroring:</span></span>

  - <span data-ttu-id="c3931-168">如果某个镜像端点已存在，则会使用其中定义的端口重用该端点，并忽略你在拓扑中指定的端口。</span><span class="sxs-lookup"><span data-stu-id="c3931-168">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>

  - <span data-ttu-id="c3931-p113">已为同一服务器上的其他应用程序分配的任何端口（包括用于其他 SQL 实例的端口）均不得用于当前安装的 SQL 实例。这意味着，如果在同一服务器上安装了多个 SQL 实例，它们不能将同一端口用于镜像。有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="c3931-p113">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand. This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring. For details, see the following articles:</span></span>
    
      - <span data-ttu-id="c3931-172">"在 MSDN Library 中的" 指定服务器网络地址 (数据库镜像) "[http://go.microsoft.com/fwlink/p/?LinkId=247346](http://go.microsoft.com/fwlink/p/?linkid=247346)</span><span class="sxs-lookup"><span data-stu-id="c3931-172">"Specify a Server Network Address (Database Mirroring)" in the MSDN Library at [http://go.microsoft.com/fwlink/p/?LinkId=247346](http://go.microsoft.com/fwlink/p/?linkid=247346)</span></span>
    
      - <span data-ttu-id="c3931-173">"数据库镜像终结点 (SQL Server)"[http://go.microsoft.com/fwlink/p/?LinkId=247347](http://go.microsoft.com/fwlink/p/?linkid=247347)</span><span class="sxs-lookup"><span data-stu-id="c3931-173">"The Database Mirroring Endpoint (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=247347](http://go.microsoft.com/fwlink/p/?linkid=247347)</span></span>

</div>

<div>

## <a name="using-lync-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="c3931-174">使用 Lync Server Management Shell Cmdlet 设置 SQL 镜像</span><span class="sxs-lookup"><span data-stu-id="c3931-174">Using Lync Server Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="c3931-175">设置镜像最简单的方法是使用拓扑生成器, 但你也可以使用 cmdlet 执行此操作。</span><span class="sxs-lookup"><span data-stu-id="c3931-175">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>

1.  <span data-ttu-id="c3931-176">打开 Lync Server Management Shell 窗口并运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c3931-176">Open a Lync Server Management Shell window and run the following cmdlet:</span></span>
    
        Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
    
    <span data-ttu-id="c3931-177">例如：</span><span class="sxs-lookup"><span data-stu-id="c3931-177">For example:</span></span>
    
        Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 
    
    <span data-ttu-id="c3931-178">你将看到以下内容：</span><span class="sxs-lookup"><span data-stu-id="c3931-178">You will see the following:</span></span>
    
        Database Name:rtcxds 
                Data File:D:\CsData\BackendStore\rtc\DbPath\rtcxds.mdf 
                 Log File:D:\CsData\BackendStore\rtc\LogPath\rtcxds.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rtcshared 
                Data File:D:\CsData\BackendStore\rtc\DbPath\rtcshared.mdf 
                 Log File:D:\CsData\BackendStore\rtc\LogPath\rtcshared.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rtcab 
                Data File:D:\CsData\ABSStore\rtc\DbPath\rtcab.mdf 
                 Log File:D:\CsData\ABSStore\rtc\LogPath\rtcab.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rgsconfig 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsconfig.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsconfig.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rgsdyn 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsdyn.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsdyn.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:cpsdyn 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\cpsdyn.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\cpsdyn.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:xds 
                Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\xds.mdf 
                 Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\xds.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:lis 
                Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\lis.mdf 
                 Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\lis.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$
        [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): 

2.  <span data-ttu-id="c3931-179">验证以下内容：</span><span class="sxs-lookup"><span data-stu-id="c3931-179">Verify the following:</span></span>
    
      - <span data-ttu-id="c3931-180">如果在主 SQL Server e04-ocs 中启用了 Windows 防火墙, 则可以通过防火墙访问端口5022。\_lsipt。\\</span><span class="sxs-lookup"><span data-stu-id="c3931-180">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="c3931-181">如果在镜像 SQL Server K16-ocs\_\\Rtc 中启用了 Windows 防火墙, 则可以通过防火墙访问端口5022。</span><span class="sxs-lookup"><span data-stu-id="c3931-181">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="c3931-182">如果在见证 SQL Server AB14-lct 中启用了 Windows 防火墙, 则可以通过防火墙访问端口7022。\_lsipt。\\</span><span class="sxs-lookup"><span data-stu-id="c3931-182">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="c3931-183">在所有主 sql 服务器和镜像 sql server 上运行 sql server 的帐户对文件共享\\ \\E04 (OCS\\csdatabackup) 具有读/写权限。</span><span class="sxs-lookup"><span data-stu-id="c3931-183">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\\\E04-OCS\\csdatabackup</span></span>
    
      - <span data-ttu-id="c3931-p114">验证 Windows Management Instrumentation (WMI) 提供程序是否正在所有这些服务器上运行。该 cmdlet 使用此提供程序查找在所有主服务器、镜像服务器和见证服务器上运行的 SQL Server 服务的帐户信息。</span><span class="sxs-lookup"><span data-stu-id="c3931-p114">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers. The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span>
    
      - <span data-ttu-id="c3931-186">验证运行此 cmdlet 的帐户是否有权为所有镜像服务器上的数据和日志文件创建文件夹。</span><span class="sxs-lookup"><span data-stu-id="c3931-186">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span>
    
      - <span data-ttu-id="c3931-p115">请注意，用于运行 SQL 实例的用户帐户必须具有对文件共享的读取/写入权限。如果文件共享位于其他服务器上且 SQL 实例运行本地系统帐户，则你必须向承载 SQL 实例的服务器授予文件共享权限。</span><span class="sxs-lookup"><span data-stu-id="c3931-p115">Note that the user account that the SQL instance uses to run must have read/write permission to the file share. If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>

3.  <span data-ttu-id="c3931-189">键入 A 并按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="c3931-189">Type A and press ENTER.</span></span>
    
    <span data-ttu-id="c3931-190">将配置镜像。</span><span class="sxs-lookup"><span data-stu-id="c3931-190">The mirroring will be configured.</span></span>

<span data-ttu-id="c3931-191">**Install-CsMirrorDatabase** 将为主 SQL 存储中存在的所有数据库安装并配置镜像。</span><span class="sxs-lookup"><span data-stu-id="c3931-191">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="c3931-192">如果只想为特定数据库配置镜像，你可以使用 –DatabaseType option 选项；如果要为除少数几个数据库之外的所有其他数据库配置镜像，你可以使用 -ExcludeDatabaseList 选项以及要排除的数据库名称的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="c3931-192">If you want to configure mirroring for only specific databases, you can use the –DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>

<span data-ttu-id="c3931-193">例如，如果将以下选项添加到 **Install-CsMirrorDatabase** 中，则除了 rtcab 和 rtcxds 之外的所有数据库都将进行镜像。</span><span class="sxs-lookup"><span data-stu-id="c3931-193">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>

`-ExcludeDatabaseList rtcab,rtcxds`

<span data-ttu-id="c3931-194">例如，如果将以下选项添加到 **Install-CsMirrorDatabase** 中，则只有 rtcab、rtcshared 和 rtcxds 数据库将进行镜像。</span><span class="sxs-lookup"><span data-stu-id="c3931-194">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>

`-DatabaseType User`

</div>

<div>

## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="c3931-195">删除或更改 SQL 镜像</span><span class="sxs-lookup"><span data-stu-id="c3931-195">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="c3931-p117">要在拓扑生成器中删除池的 SQL 镜像，你必须先使用 cmdlet 删除 SQL Server 中的镜像。随后，你可以使用拓扑生成器删除拓扑中的镜像。要删除 SQL Server 中的镜像，请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c3931-p117">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server. You can then use Topology Builder to remove the mirror from the topology. To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="c3931-199">例如，要删除镜像并删除针对用户数据库的数据库，请键入：</span><span class="sxs-lookup"><span data-stu-id="c3931-199">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="c3931-200">该`-DropExistingDatabasesOnMirror`选项会将受影响的数据库从镜像中删除。</span><span class="sxs-lookup"><span data-stu-id="c3931-200">The `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>

<span data-ttu-id="c3931-201">然后，要从拓扑中删除镜像，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c3931-201">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="c3931-202">在拓扑生成器中，右键单击该池并单击“**编辑属性**”。</span><span class="sxs-lookup"><span data-stu-id="c3931-202">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="c3931-203">取消选中“**启用 SQL 存储镜像**”并单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="c3931-203">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="c3931-204">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="c3931-204">Publish the topology.</span></span>

</div>

<div>

## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="c3931-205">删除镜像见证</span><span class="sxs-lookup"><span data-stu-id="c3931-205">Removing a Mirroring Witness</span></span>

<span data-ttu-id="c3931-206">如果需要从后端服务器镜像配置中删除见证, 请使用此过程。</span><span class="sxs-lookup"><span data-stu-id="c3931-206">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>

1.  <span data-ttu-id="c3931-207">在拓扑生成器中，右键单击该池并单击“**编辑属性**”。</span><span class="sxs-lookup"><span data-stu-id="c3931-207">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="c3931-208">取消选中“**使用 SQL Server 镜像见证启用自动故障转移**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="c3931-208">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>

3.  <span data-ttu-id="c3931-209">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="c3931-209">Publish the topology.</span></span>
    
    <span data-ttu-id="c3931-210">发布拓扑后, 拓扑生成器将看到一条消息, 其中包含以下内容:</span><span class="sxs-lookup"><span data-stu-id="c3931-210">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    <span data-ttu-id="c3931-211">但是, 不要按照该步骤操作, 不要像这样键入`Uninstall-CsMirrorDatabase`卸载整个镜像配置。</span><span class="sxs-lookup"><span data-stu-id="c3931-211">However, do not follow that step, and do not type `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>

4.  <span data-ttu-id="c3931-212">若要仅从 SQL Server 配置中删除见证, 请按照 "从数据库镜像会话中删除见证 (SQL Server)" 中的说明进行[http://go.microsoft.com/fwlink/p/?LinkId=268456](http://go.microsoft.com/fwlink/p/?linkid=268456)操作。</span><span class="sxs-lookup"><span data-stu-id="c3931-212">To remove just the witness from the SQL Server configuration, follow the instructions in "Remove the Witness from a Database Mirroring Session (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268456](http://go.microsoft.com/fwlink/p/?linkid=268456).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

