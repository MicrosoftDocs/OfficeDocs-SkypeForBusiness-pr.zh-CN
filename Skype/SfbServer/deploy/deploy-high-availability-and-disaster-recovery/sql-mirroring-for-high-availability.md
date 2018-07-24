---
title: 在 Skype for Business Server 2015 中针对后端服务器高可用性部署 SQL 镜像
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: 为了能够部署 SQL 镜像，你的服务器必须至少运行 SQL Server 2008 R2。 此版本必须在所有涉及的服务器上运行：主服务器、镜像服务器和见证服务器。 有关详细信息，请参阅累积更新程序包 9 的 SQL Server 2008 Service Pack 1。
ms.openlocfilehash: a0baf639b050d323a29eb347c14b38505f059ef2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21016204"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a><span data-ttu-id="4b94b-105">部署 SQL 镜像后端服务器高可用性 Skype 中的业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="4b94b-105">Deploy SQL mirroring for Back End Server high availability in Skype for Business server 2015</span></span>
 

<span data-ttu-id="4b94b-106">为了能够部署 SQL 镜像，你的服务器必须至少运行 SQL Server 2008 R2。</span><span class="sxs-lookup"><span data-stu-id="4b94b-106">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="4b94b-107">此版本必须在所有涉及的服务器上运行：主服务器、镜像服务器和见证服务器。</span><span class="sxs-lookup"><span data-stu-id="4b94b-107">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="4b94b-108">有关详细信息，请参阅[累积更新程序包 9 SQL Server 2008 Service Pack 1 ](http://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921)。</span><span class="sxs-lookup"><span data-stu-id="4b94b-108">For details, see [Cumulative update package 9 for SQL Server 2008 Service Pack 1 ](http://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).</span></span>
  
<span data-ttu-id="4b94b-109">通常，在两台具有见证的后端服务器之间设置 SQL 镜像需要满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="4b94b-109">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>
  
- <span data-ttu-id="4b94b-110">SQL server 的主服务器的版本必须支持 SQL 镜像。</span><span class="sxs-lookup"><span data-stu-id="4b94b-110">The primary server's version of SQL Server must support SQL mirroring.</span></span>
    
- <span data-ttu-id="4b94b-111">主、镜像和见证（如果部署）必须具有同一版本的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="4b94b-111">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span> 
    
- <span data-ttu-id="4b94b-p103">主和镜像必须具有同一版本的 SQL Server。见证可以具有不同版本。</span><span class="sxs-lookup"><span data-stu-id="4b94b-p103">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>
    
<span data-ttu-id="4b94b-114">有关见证角色支持的 SQL 版本的 SQL 最佳实践，请参阅[数据库镜像见证](https://go.microsoft.com/fwlink/p/?LinkId=247345)。</span><span class="sxs-lookup"><span data-stu-id="4b94b-114">For SQL best practices in terms of what SQL versions are supported for a Witness role, see [Database Mirroring Witness](https://go.microsoft.com/fwlink/p/?LinkId=247345).</span></span>
  
<span data-ttu-id="4b94b-115">使用拓扑生成器来部署 SQL 镜像。</span><span class="sxs-lookup"><span data-stu-id="4b94b-115">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="4b94b-116">在拓扑生成器中进行镜像数据库，选择一个选项和设置镜像 （如果您希望包括设置见证） 拓扑生成器发布拓扑时。</span><span class="sxs-lookup"><span data-stu-id="4b94b-116">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="4b94b-117">请注意，设置或删除见证服务器会同时设置或删除镜像服务器。</span><span class="sxs-lookup"><span data-stu-id="4b94b-117">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="4b94b-118">没有用于仅部署或删除见证服务器的单独命令。</span><span class="sxs-lookup"><span data-stu-id="4b94b-118">There is no separate command to deploy or remove only a witness.</span></span>
  
<span data-ttu-id="4b94b-119">要配置服务器镜像，必须正确设置 SQL 数据库权限。</span><span class="sxs-lookup"><span data-stu-id="4b94b-119">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="4b94b-120">有关详细信息，请参阅[设置建立登录帐户的数据库镜像或 AlwaysOn 可用性组 (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268454)。</span><span class="sxs-lookup"><span data-stu-id="4b94b-120">For details, see [Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268454).</span></span>
  
<span data-ttu-id="4b94b-p106">对于 SQL 镜像，数据库恢复模式始终设置为“**完全**”，这意味着你必须密切监控事务日志大小并定期备份事务日志以避免后端服务器上的磁盘空间不足。事务日志备份频率取决于日志增长速率，反过来，日志增长速率又取决于前端池上的用户活动所产生的数据库事务数。建议确定你的部署工作负载预计将达到的事务日志增长幅度，以便相应地进行规划。以下文章提供了有关 SQL 备份和日志管理的其他信息：</span><span class="sxs-lookup"><span data-stu-id="4b94b-p106">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>
  
- [<span data-ttu-id="4b94b-125">数据库恢复模型</span><span class="sxs-lookup"><span data-stu-id="4b94b-125">Database recovery models</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268446)
    
- [<span data-ttu-id="4b94b-126">备份概述 （英文)</span><span class="sxs-lookup"><span data-stu-id="4b94b-126">Backup overview</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268449)
    
- [<span data-ttu-id="4b94b-127">备份事务日志</span><span class="sxs-lookup"><span data-stu-id="4b94b-127">Backup transaction log</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268452)
    
<span data-ttu-id="4b94b-128">对于 SQL 镜像，可在创建池时或之后为镜像配置拓扑。</span><span class="sxs-lookup"><span data-stu-id="4b94b-128">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4b94b-129">使用拓扑生成器或 cmdlet 来设置和删除 SQL 镜像仅当主、 镜像和见证 （如果需要） 服务器所有属于同一域时，才支持。</span><span class="sxs-lookup"><span data-stu-id="4b94b-129">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="4b94b-130">如果您需要在不同域中的服务器之间设置 SQL 镜像，请参阅 SQL Server 文档。</span><span class="sxs-lookup"><span data-stu-id="4b94b-130">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="4b94b-131">只要更改了后端数据库镜像关系，就必须重新启动池中的所有前端服务器。</span><span class="sxs-lookup"><span data-stu-id="4b94b-131">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span> <span data-ttu-id="4b94b-132">> 对于镜像的更改，（如更改镜像位置），您必须使用拓扑生成器以执行以下三个步骤：</span><span class="sxs-lookup"><span data-stu-id="4b94b-132">> For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span> 
  
1. <span data-ttu-id="4b94b-133">从旧镜像服务器中删除镜像。</span><span class="sxs-lookup"><span data-stu-id="4b94b-133">Remove mirroring from the old mirror server.</span></span>
    
2. <span data-ttu-id="4b94b-134">向新镜像服务器中添加镜像。</span><span class="sxs-lookup"><span data-stu-id="4b94b-134">Add mirroring to the new mirror server.</span></span>
    
3. <span data-ttu-id="4b94b-135">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="4b94b-135">Publish the topology.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4b94b-136">必须为要写入到的镜像文件创建文件共享，SQL Server 和 SQL 代理在其下运行的服务需要读取/写入访问权限。</span><span class="sxs-lookup"><span data-stu-id="4b94b-136">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="4b94b-137">如果网络服务的上下文中运行 SQL Server 服务，您可以添加\<域\>\\< SQLSERVERNAME\>$ 的主体和镜像 SQL Server 在共享权限。</span><span class="sxs-lookup"><span data-stu-id="4b94b-137">If the SQL Server service is running under the context of Network Service, you can add \<Domain\>\\<SQLSERVERNAME\>$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="4b94b-138">$ 非常重要，可用于标识这是一个计算机帐户。</span><span class="sxs-lookup"><span data-stu-id="4b94b-138">The $ is important to identify that this is a computer account.</span></span> 
  
## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="4b94b-139">配置 SQL 镜像时在拓扑生成器中创建池</span><span class="sxs-lookup"><span data-stu-id="4b94b-139">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1. <span data-ttu-id="4b94b-140">在“**定义 SQL 存储**”页上，单击“**SQL 存储**”框旁边的“**新建**”。</span><span class="sxs-lookup"><span data-stu-id="4b94b-140">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>
    
2. <span data-ttu-id="4b94b-141">在“**定义新的 SQL 存储**”页上，指定主存储，选择“**此 SQL 实例处于镜像关系中**”，指定 SQL 镜像端口号（默认为 5022），然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="4b94b-141">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>
    
3. <span data-ttu-id="4b94b-142">返回到“**定义 SQL 存储**”页，选中“**启用 SQL 存储镜像**”。</span><span class="sxs-lookup"><span data-stu-id="4b94b-142">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span> 
    
4. <span data-ttu-id="4b94b-p110">在“**定义新的 SQL 存储**”页中，指定要用作镜像的 SQL 存储，选择“**此 SQL 实例处于镜像关系中**”，指定端口号（默认为 5022），然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="4b94b-p110">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror. Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>
    
5. <span data-ttu-id="4b94b-145">如果要将见证服务器用于此镜像，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4b94b-145">If you want a witness for this mirror, do the following:</span></span> 
    
    <span data-ttu-id="4b94b-146">a.</span><span class="sxs-lookup"><span data-stu-id="4b94b-146">a.</span></span> <span data-ttu-id="4b94b-147">选中“**使用 SQL 镜像见证启用自动故障转移**”。</span><span class="sxs-lookup"><span data-stu-id="4b94b-147">Select **Use SQL mirroring witness to enable automatic failover**.</span></span> 
    
    <span data-ttu-id="4b94b-148">b.</span><span class="sxs-lookup"><span data-stu-id="4b94b-148">b.</span></span> <span data-ttu-id="4b94b-149">在“**定义 SQL 存储**”页中，选中“**使用 SQL 镜像见证启用自动故障转移**”，并指定要用作见证服务器的 SQL 存储。</span><span class="sxs-lookup"><span data-stu-id="4b94b-149">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span> 
    
    <span data-ttu-id="4b94b-150">c.</span><span class="sxs-lookup"><span data-stu-id="4b94b-150">c.</span></span> <span data-ttu-id="4b94b-151">指定端口号（默认为 7022）并单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="4b94b-151">Specify the port number (the default is 7022) and click **OK**.</span></span> 
    
6. <span data-ttu-id="4b94b-152">后在拓扑中，定义前端池和所有其他角色使用拓扑生成器发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="4b94b-152">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="4b94b-153">发布拓扑时，如果承载中央管理存储的前端池已启用 SQL 镜像，您将看到创建两个主和镜像 SQL 存储数据库放在一个选项。</span><span class="sxs-lookup"><span data-stu-id="4b94b-153">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>
    
    <span data-ttu-id="4b94b-154">单击“**设置**”，并键入要用作镜像备份的文件共享的路径。</span><span class="sxs-lookup"><span data-stu-id="4b94b-154">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>
    
    <span data-ttu-id="4b94b-p115">单击“**确定**”，然后单击“**下一步**”以创建数据库并发布拓扑。这将部署镜像服务器和见证服务器（如果已指定）。</span><span class="sxs-lookup"><span data-stu-id="4b94b-p115">Click **OK** and then **Next** to create the databases and publish the topology. The mirroring and the witness (if specified) will be deployed.</span></span>
    
<span data-ttu-id="4b94b-157">可以使用拓扑生成器-编辑已现有池以启用 SQL 镜像的属性。</span><span class="sxs-lookup"><span data-stu-id="4b94b-157">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span> 
  
## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="4b94b-158">若要添加到拓扑生成器中的现有前端池的 SQL 镜像</span><span class="sxs-lookup"><span data-stu-id="4b94b-158">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1. <span data-ttu-id="4b94b-159">在拓扑生成器中，右键单击池，然后单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="4b94b-159">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="4b94b-160">选中“**启用 SQL 存储镜像**”，然后单击“**镜像 SQL 存储**”旁边的“**新建**”。</span><span class="sxs-lookup"><span data-stu-id="4b94b-160">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span> 
    
3. <span data-ttu-id="4b94b-161">指定要用作镜像的 SQL 存储。</span><span class="sxs-lookup"><span data-stu-id="4b94b-161">Specify the SQL store that you want to use as the mirror.</span></span> 
    
4. <span data-ttu-id="4b94b-162">选择“**此 SQL 实例处于镜像关系中**”，指定 SQL 镜像端口号（默认端口为 5022），然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="4b94b-162">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>
    
5. <span data-ttu-id="4b94b-163">如果要配置见证服务器，请选中“**使用 SQL 镜像见证启用自动故障转移**”，然后单击“**新建**”。</span><span class="sxs-lookup"><span data-stu-id="4b94b-163">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span> 
    
6. <span data-ttu-id="4b94b-164">指定要用作见证服务器的 SQL 存储。</span><span class="sxs-lookup"><span data-stu-id="4b94b-164">Specify the SQL store that you want to use as the witness.</span></span> 
    
7. <span data-ttu-id="4b94b-165">选择“**此 SQL 实例处于镜像关系中**”，指定 SQL 镜像端口号（默认端口为 7022），然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="4b94b-165">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>
    
8. <span data-ttu-id="4b94b-166">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="4b94b-166">Click **OK**.</span></span>
    
9. <span data-ttu-id="4b94b-p116">发布拓扑。在执行此操作时，系统会提示你安装数据库。</span><span class="sxs-lookup"><span data-stu-id="4b94b-p116">Publish the topology. When you do so, you will be prompted to install the database.</span></span> 
    
    <span data-ttu-id="4b94b-p117">在拓扑发布过程中，系统将要求你定义文件共享路径。参与镜像的 SQL Server 必须对此文件共享具有读取/写入访问权限，才能建立镜像。</span><span class="sxs-lookup"><span data-stu-id="4b94b-p117">During the topology publishing process, you will be asked to define a file share path. The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>
    
<span data-ttu-id="4b94b-171">然后必须在继续下一步之前安装数据库。</span><span class="sxs-lookup"><span data-stu-id="4b94b-171">You must then install the database before going on to the next procedure.</span></span>
  
<span data-ttu-id="4b94b-172">设置 SQL 镜像时，应谨记以下几点：</span><span class="sxs-lookup"><span data-stu-id="4b94b-172">You should keep the following in mind when setting up SQL mirroring:</span></span>
  
- <span data-ttu-id="4b94b-173">如果某个镜像端点已存在，则会使用其中定义的端口重用该端点，并忽略你在拓扑中指定的端口。</span><span class="sxs-lookup"><span data-stu-id="4b94b-173">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>
    
- <span data-ttu-id="4b94b-p118">已为同一服务器上的其他应用程序分配的任何端口（包括用于其他 SQL 实例的端口）均不得用于当前安装的 SQL 实例。这意味着，如果在同一服务器上安装了多个 SQL 实例，它们不能将同一端口用于镜像。有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="4b94b-p118">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand. This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring. For details, see the following articles:</span></span>
    
  - [<span data-ttu-id="4b94b-177">指定服务器网络地址 （数据库镜像）</span><span class="sxs-lookup"><span data-stu-id="4b94b-177">Specify a Server Network Address (Database Mirroring)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=247346)
    
  - [<span data-ttu-id="4b94b-178">数据库镜像终结点 (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4b94b-178">The Database Mirroring Endpoint (SQL Server)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=247347)
    
## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="4b94b-179">Skype 用于业务服务器 2015年管理命令行管理程序 Cmdlet 设置 SQL 镜像</span><span class="sxs-lookup"><span data-stu-id="4b94b-179">Using Skype for Business Server 2015 Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="4b94b-180">设置镜像的最简单方式是使用拓扑生成器，但您还可以使用 cmdlet 完成。</span><span class="sxs-lookup"><span data-stu-id="4b94b-180">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>
  
1. <span data-ttu-id="4b94b-181">打开业务服务器 2015年命令行管理程序窗口 Skype 并运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4b94b-181">Open a Skype for Business Server 2015 Management Shell window and run the following cmdlet:</span></span>
    
   ```
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
   ```

    <span data-ttu-id="4b94b-182">例如：</span><span class="sxs-lookup"><span data-stu-id="4b94b-182">For example:</span></span>
    
   ```
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 
   ```

    <span data-ttu-id="4b94b-183">你将看到以下内容：</span><span class="sxs-lookup"><span data-stu-id="4b94b-183">You will see the following:</span></span>
    
 <pre>
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
</pre>

2. <span data-ttu-id="4b94b-184">验证以下内容：</span><span class="sxs-lookup"><span data-stu-id="4b94b-184">Verify the following:</span></span>
    
    - <span data-ttu-id="4b94b-185">如果在主 SQL Server e04-ocs.los_a.lsipt.local\rtc 中启用 Windows 防火墙，则可通过防火墙访问端口 5022。</span><span class="sxs-lookup"><span data-stu-id="4b94b-185">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los_a.lsipt.local\rtc.</span></span> 
    
    - <span data-ttu-id="4b94b-186">如果在镜像 SQL Server K16-ocs.los_a.lsipt.local\rtc 中启用 Windows 防火墙，则可通过防火墙访问端口 5022。</span><span class="sxs-lookup"><span data-stu-id="4b94b-186">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los_a.lsipt.local\rtc.</span></span> 
    
    - <span data-ttu-id="4b94b-187">如果在见证 SQL Server AB14-lct.los_a.lsipt.local\rtc 中启用 Windows 防火墙，则可通过防火墙访问端口 7022。</span><span class="sxs-lookup"><span data-stu-id="4b94b-187">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los_a.lsipt.local\rtc.</span></span> 
    
   - <span data-ttu-id="4b94b-188">运行 SQL 服务器上所有主和镜像 SQL server 的帐户具有对文件共享的读/写权限\\E04-OCS\csdatabackup</span><span class="sxs-lookup"><span data-stu-id="4b94b-188">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\E04-OCS\csdatabackup</span></span> 
    
   - <span data-ttu-id="4b94b-p119">验证 Windows Management Instrumentation (WMI) 提供程序是否正在所有这些服务器上运行。该 cmdlet 使用此提供程序查找在所有主服务器、镜像服务器和见证服务器上运行的 SQL Server 服务的帐户信息。</span><span class="sxs-lookup"><span data-stu-id="4b94b-p119">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers. The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span> 
    
   - <span data-ttu-id="4b94b-191">验证运行此 cmdlet 的帐户是否有权为所有镜像服务器上的数据和日志文件创建文件夹。</span><span class="sxs-lookup"><span data-stu-id="4b94b-191">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span> 
    
   - <span data-ttu-id="4b94b-p120">请注意，用于运行 SQL 实例的用户帐户必须具有对文件共享的读取/写入权限。如果文件共享位于其他服务器上且 SQL 实例运行本地系统帐户，则你必须向承载 SQL 实例的服务器授予文件共享权限。</span><span class="sxs-lookup"><span data-stu-id="4b94b-p120">Note that the user account that the SQL instance uses to run must have read/write permission to the file share. If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>
    
3. <span data-ttu-id="4b94b-194">键入 A 并按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="4b94b-194">Type A and press ENTER.</span></span>
    
    <span data-ttu-id="4b94b-195">将配置镜像。</span><span class="sxs-lookup"><span data-stu-id="4b94b-195">The mirroring will be configured.</span></span>
    
    <span data-ttu-id="4b94b-196">**Install-csmirrordatabase**安装镜像并配置有在主 SQL 存储区的所有数据库的镜像。</span><span class="sxs-lookup"><span data-stu-id="4b94b-196">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="4b94b-197">如果您想要配置为仅特定数据库镜像，则可以使用-DatabaseType 选项，或者如果您想要配置的一些除外的所有数据库镜像，您可以使用-ExcludeDatabaseList 选项，以及数据库的以逗号分隔列表若要排除的名称。</span><span class="sxs-lookup"><span data-stu-id="4b94b-197">If you want to configure mirroring for only specific databases, you can use the -DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>
  
    <span data-ttu-id="4b94b-198">例如，如果您将以下选项添加到**Install-csmirrordatabase**，除 rtcab 和 rtcxds 之外的所有数据库将进行都镜像。</span><span class="sxs-lookup"><span data-stu-id="4b94b-198">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>
  
    `-ExcludeDatabaseList rtcab,rtcxds`
  
   <span data-ttu-id="4b94b-199">例如，如果将以下选项添加到**Install-csmirrordatabase**中，将镜像仅 rtcab、 rtcshared 和 rtcxds 数据库。</span><span class="sxs-lookup"><span data-stu-id="4b94b-199">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>
  
    `-DatabaseType User`
  
## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="4b94b-200">删除或更改 SQL 镜像</span><span class="sxs-lookup"><span data-stu-id="4b94b-200">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="4b94b-p122">要在拓扑生成器中删除池的 SQL 镜像，你必须先使用 cmdlet 删除 SQL Server 中的镜像。随后，你可以使用拓扑生成器删除拓扑中的镜像。要删除 SQL Server 中的镜像，请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="4b94b-p122">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server. You can then use Topology Builder to remove the mirror from the topology. To remove the mirror in SQL Server, use the following cmdlet:</span></span>
  
```
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

<span data-ttu-id="4b94b-204">例如，要删除镜像并删除针对用户数据库的数据库，请键入：</span><span class="sxs-lookup"><span data-stu-id="4b94b-204">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>
  
```
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

<span data-ttu-id="4b94b-205">`-DropExistingDatabasesOnMirror`选项会导致从镜像中删除受影响的数据库。</span><span class="sxs-lookup"><span data-stu-id="4b94b-205">The  `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>
  
<span data-ttu-id="4b94b-206">然后，要从拓扑中删除镜像，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4b94b-206">Then, to remove the mirror from the topology, do the following:</span></span>
  
1. <span data-ttu-id="4b94b-207">在拓扑生成器中，右键单击该池并单击“**编辑属性**”。</span><span class="sxs-lookup"><span data-stu-id="4b94b-207">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="4b94b-208">取消选中“**启用 SQL 存储镜像**”并单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="4b94b-208">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>
    
3. <span data-ttu-id="4b94b-209">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="4b94b-209">Publish the topology.</span></span>
    
## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="4b94b-210">删除镜像见证</span><span class="sxs-lookup"><span data-stu-id="4b94b-210">Removing a Mirroring Witness</span></span>

<span data-ttu-id="4b94b-211">如果您需要从后端服务器镜像配置中删除见证，请使用此过程。</span><span class="sxs-lookup"><span data-stu-id="4b94b-211">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>
  
1. <span data-ttu-id="4b94b-212">在拓扑生成器中，右键单击该池并单击“**编辑属性**”。</span><span class="sxs-lookup"><span data-stu-id="4b94b-212">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span> 
    
2. <span data-ttu-id="4b94b-213">取消选中“**使用 SQL Server 镜像见证启用自动故障转移**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="4b94b-213">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>
    
3. <span data-ttu-id="4b94b-214">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="4b94b-214">Publish the topology.</span></span>
    
    <span data-ttu-id="4b94b-215">后发布拓扑生成器的拓扑，您将看到一条消息，包括以下</span><span class="sxs-lookup"><span data-stu-id="4b94b-215">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>
    
   ```
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    <span data-ttu-id="4b94b-216">但是，不执行该步骤，并且不要键入`Uninstall-CsMirrorDatabase`，这将卸载整个镜像配置。</span><span class="sxs-lookup"><span data-stu-id="4b94b-216">However, do not follow that step, and do not type  `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>
    
4. <span data-ttu-id="4b94b-217">若要从 SQL Server 配置中删除见证，请按照中[删除见证从数据库镜像会话 (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268456)的说明。</span><span class="sxs-lookup"><span data-stu-id="4b94b-217">To remove just the witness from the SQL Server configuration, follow the instructions in [Remove the Witness from a Database Mirroring Session (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268456).</span></span>
    

