---
title: 在 skype SQL Server 2015 中部署后端服务器高可用性的镜像
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: 为了能够部署 SQL 镜像，您的服务器必须至少运行 SQL Server 2008 R2。 此版本必须在所有涉及的服务器上运行：主、镜像和见证。 有关详细信息，请参阅 SQL Server 2008 Service Pack 1 的累积更新包 9。
ms.openlocfilehash: 8a546f65d8ad5c701eea20fb2c9c3bf0e026ff1f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830552"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a><span data-ttu-id="adde3-105">在 skype SQL Server 2015 中部署后端服务器高可用性的镜像</span><span class="sxs-lookup"><span data-stu-id="adde3-105">Deploy SQL mirroring for Back End Server high availability in Skype for Business server 2015</span></span>


<span data-ttu-id="adde3-106">为了能够部署 SQL 镜像，您的服务器必须至少运行 SQL Server 2008 R2。</span><span class="sxs-lookup"><span data-stu-id="adde3-106">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="adde3-107">此版本必须在所有涉及的服务器上运行：主、镜像和见证。</span><span class="sxs-lookup"><span data-stu-id="adde3-107">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="adde3-108">有关详细信息，请参阅[SQL Server 2008 Service Pack 1 的累积更新包 9。](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921)</span><span class="sxs-lookup"><span data-stu-id="adde3-108">For details, see [Cumulative update package 9 for SQL Server 2008 Service Pack 1](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).</span></span>

<span data-ttu-id="adde3-109">通常，在两台具有见证的后端服务器之间设置 SQL 镜像需要满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="adde3-109">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>

- <span data-ttu-id="adde3-110">主服务器的版本必须支持SQL Server镜像SQL版本。</span><span class="sxs-lookup"><span data-stu-id="adde3-110">The primary server's version of SQL Server must support SQL mirroring.</span></span>

- <span data-ttu-id="adde3-111">主、镜像和见证（如果部署）必须具有同一版本的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="adde3-111">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span>

- <span data-ttu-id="adde3-p103">主和镜像必须具有同一版本的 SQL Server。见证可以具有不同版本。</span><span class="sxs-lookup"><span data-stu-id="adde3-p103">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>

<span data-ttu-id="adde3-114">有关SQL见证角色支持哪些SQL的最佳实践，请参阅"数据库[镜像见证"。](https://go.microsoft.com/fwlink/p/?LinkId=247345)</span><span class="sxs-lookup"><span data-stu-id="adde3-114">For SQL best practices in terms of what SQL versions are supported for a Witness role, see [Database Mirroring Witness](https://go.microsoft.com/fwlink/p/?LinkId=247345).</span></span>

<span data-ttu-id="adde3-115">使用拓扑生成器部署SQL镜像。</span><span class="sxs-lookup"><span data-stu-id="adde3-115">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="adde3-116">在拓扑生成器中选择一个选项来镜像数据库，并且拓扑生成器会设置镜像 (包括设置见证（如果需要在发布拓扑时) 见证）。</span><span class="sxs-lookup"><span data-stu-id="adde3-116">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="adde3-117">请注意，您在设置或删除镜像的同时将设置或删除见证。</span><span class="sxs-lookup"><span data-stu-id="adde3-117">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="adde3-118">没有用于仅部署或删除见证的单独命令。</span><span class="sxs-lookup"><span data-stu-id="adde3-118">There is no separate command to deploy or remove only a witness.</span></span>

<span data-ttu-id="adde3-119">若要配置服务器镜像，您必须先正确设置 SQL 数据库权限。</span><span class="sxs-lookup"><span data-stu-id="adde3-119">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="adde3-120">有关详细信息，请参阅"为数据库镜像或 [AlwaysOn ](https://go.microsoft.com/fwlink/p/?LinkId=268454)可用性组设置登录帐户" (SQL Server) 。</span><span class="sxs-lookup"><span data-stu-id="adde3-120">For details, see [Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268454).</span></span>

<span data-ttu-id="adde3-121">对于 SQL 镜像，数据库恢复模式始终设置为“完全”，这意味着您必须密切监控事务日志大小并定期备份事务日志以避免后端服务器上的磁盘空间不足。</span><span class="sxs-lookup"><span data-stu-id="adde3-121">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers.</span></span> <span data-ttu-id="adde3-122">事务日志备份频率取决于日志增长速率，反过来，日志增长速率又取决于前端池上的用户活动所触发的数据库事务数。</span><span class="sxs-lookup"><span data-stu-id="adde3-122">The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool.</span></span> <span data-ttu-id="adde3-123">建议您确定部署工作负载的预期事务日志增长量，以便可以相应地进行规划。</span><span class="sxs-lookup"><span data-stu-id="adde3-123">We recommend that you determine how much transaction log growth is expected for your deployment workload so that you can do the planning accordingly.</span></span> <span data-ttu-id="adde3-124">下列文章提供了有关 SQL 备份和日志管理的其他信息：</span><span class="sxs-lookup"><span data-stu-id="adde3-124">The following articles provide additional information on SQL backup and log management:</span></span>

- [<span data-ttu-id="adde3-125">数据库恢复模型</span><span class="sxs-lookup"><span data-stu-id="adde3-125">Database recovery models</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268446)

- [<span data-ttu-id="adde3-126">备份概述</span><span class="sxs-lookup"><span data-stu-id="adde3-126">Backup overview</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268449)

- [<span data-ttu-id="adde3-127">备份事务日志</span><span class="sxs-lookup"><span data-stu-id="adde3-127">Backup transaction log</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268452)

<span data-ttu-id="adde3-128">对于 SQL 镜像，可在创建池时或之后为镜像配置拓扑。</span><span class="sxs-lookup"><span data-stu-id="adde3-128">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="adde3-129">仅在主、镜像和见证 (（如果需要）) 服务器都属于同一域时，才支持使用拓扑生成器或 cmdlet 设置和删除 SQL 镜像。</span><span class="sxs-lookup"><span data-stu-id="adde3-129">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="adde3-130">如果您需要在不同域中的服务器之间设置 SQL 镜像，请参阅 SQL Server 文档。</span><span class="sxs-lookup"><span data-stu-id="adde3-130">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="adde3-131">只要更改后端数据库镜像关系，就必须重新启动池中的所有前端服务器。</span><span class="sxs-lookup"><span data-stu-id="adde3-131">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span> <span data-ttu-id="adde3-132">>对于镜像中的更改， (（如更改镜像) 的位置）必须使用拓扑生成器执行以下三个步骤：</span><span class="sxs-lookup"><span data-stu-id="adde3-132">> For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span>

1. <span data-ttu-id="adde3-133">从旧镜像服务器中删除镜像。</span><span class="sxs-lookup"><span data-stu-id="adde3-133">Remove mirroring from the old mirror server.</span></span>

2. <span data-ttu-id="adde3-134">向新镜像服务器中添加镜像。</span><span class="sxs-lookup"><span data-stu-id="adde3-134">Add mirroring to the new mirror server.</span></span>

3. <span data-ttu-id="adde3-135">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="adde3-135">Publish the topology.</span></span>

> [!NOTE]
> <span data-ttu-id="adde3-136">必须创建文件共享，以写入镜像文件，并且运行 SQL Server 和 SQL 代理的服务需要读/写访问权限。</span><span class="sxs-lookup"><span data-stu-id="adde3-136">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="adde3-137">如果 SQL Server 服务在网络服务上下文中运行，您可以将主体服务器和镜像 SQL 服务器的 \<Domain\> \\<SQLSERVERNAME $ 添加到 \> 共享权限。</span><span class="sxs-lookup"><span data-stu-id="adde3-137">If the SQL Server service is running under the context of Network Service, you can add \<Domain\>\\<SQLSERVERNAME\>$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="adde3-138">$ 对于确定这是计算机帐户非常重要。</span><span class="sxs-lookup"><span data-stu-id="adde3-138">The $ is important to identify that this is a computer account.</span></span>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="adde3-139">在SQL生成器创建池时配置镜像</span><span class="sxs-lookup"><span data-stu-id="adde3-139">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1. <span data-ttu-id="adde3-140">在“定义 SQL 存储”页上，单击“SQL 存储”框旁边的“新建”。</span><span class="sxs-lookup"><span data-stu-id="adde3-140">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>

2. <span data-ttu-id="adde3-141">在“定义新的 SQL 存储”页上，指定主存储，选择“此 SQL 实例处于镜像关系中”，指定 SQL 镜像端口号（默认为 5022），然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="adde3-141">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>

3. <span data-ttu-id="adde3-142">返回“定义 SQL 存储”页，选择“启用 SQL 存储镜像”。</span><span class="sxs-lookup"><span data-stu-id="adde3-142">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span>

4. <span data-ttu-id="adde3-p110">在“定义新的 SQL 存储”页中，指定要用作镜像的 SQL 存储，选择“此 SQL 实例处于镜像关系中”，指定端口号（默认为 5022），然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="adde3-p110">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror. Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>

5. <span data-ttu-id="adde3-145">如果要将见证用于此镜像，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="adde3-145">If you want a witness for this mirror, do the following:</span></span>

    <span data-ttu-id="adde3-146">a.</span><span class="sxs-lookup"><span data-stu-id="adde3-146">a.</span></span> <span data-ttu-id="adde3-147">选择“使用 SQL 镜像见证启用自动故障转移”。</span><span class="sxs-lookup"><span data-stu-id="adde3-147">Select **Use SQL mirroring witness to enable automatic failover**.</span></span>

    <span data-ttu-id="adde3-148">b.</span><span class="sxs-lookup"><span data-stu-id="adde3-148">b.</span></span> <span data-ttu-id="adde3-149">在“定义 SQL 存储”页中，选择“使用 SQL 镜像见证启用自动故障转移”，并指定要用作见证的 SQL 存储。</span><span class="sxs-lookup"><span data-stu-id="adde3-149">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span>

    <span data-ttu-id="adde3-150">c.</span><span class="sxs-lookup"><span data-stu-id="adde3-150">c.</span></span> <span data-ttu-id="adde3-151">指定端口号（默认为 7022）并单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="adde3-151">Specify the port number (the default is 7022) and click **OK**.</span></span>

6. <span data-ttu-id="adde3-152">定义完拓扑中的前端池和所有其他角色后，使用拓扑生成器发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="adde3-152">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="adde3-153">发布拓扑后，如果承载中央管理存储的前端池启用了 SQL 镜像，则会看到一个选项，用于创建主和镜像SQL存储数据库。</span><span class="sxs-lookup"><span data-stu-id="adde3-153">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>

    <span data-ttu-id="adde3-154">单击“设置”，并键入要用作镜像备份的文件共享的路径。</span><span class="sxs-lookup"><span data-stu-id="adde3-154">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>

    <span data-ttu-id="adde3-p115">单击“确定”，然后单击“下一步”以创建数据库并发布拓扑。这将部署镜像和见证（如果已指定）。</span><span class="sxs-lookup"><span data-stu-id="adde3-p115">Click **OK** and then **Next** to create the databases and publish the topology. The mirroring and the witness (if specified) will be deployed.</span></span>

<span data-ttu-id="adde3-157">可以使用拓扑生成器编辑现有池的属性，以启用SQL镜像。</span><span class="sxs-lookup"><span data-stu-id="adde3-157">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="adde3-158">在拓扑SQL中添加到现有前端池的镜像</span><span class="sxs-lookup"><span data-stu-id="adde3-158">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1. <span data-ttu-id="adde3-159">在拓扑生成器中，右键单击该池，然后单击"**编辑属性"。**</span><span class="sxs-lookup"><span data-stu-id="adde3-159">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>

2. <span data-ttu-id="adde3-160">选择“启用 SQL 存储镜像”，然后单击“镜像 SQL 存储”旁边的“新建”。</span><span class="sxs-lookup"><span data-stu-id="adde3-160">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span>

3. <span data-ttu-id="adde3-161">指定要用作镜像的 SQL 存储。</span><span class="sxs-lookup"><span data-stu-id="adde3-161">Specify the SQL store that you want to use as the mirror.</span></span>

4. <span data-ttu-id="adde3-162">选择“此 SQL 实例处于镜像关系中”中，指定 SQL 镜像端口号（默认端口为 5022），然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="adde3-162">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>

5. <span data-ttu-id="adde3-163">如果要配置见证，请选择“使用 SQL 镜像见证启用自动故障转移”，然后单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="adde3-163">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span>

6. <span data-ttu-id="adde3-164">指定要用作见证的 SQL 存储。</span><span class="sxs-lookup"><span data-stu-id="adde3-164">Specify the SQL store that you want to use as the witness.</span></span>

7. <span data-ttu-id="adde3-165">选择“此 SQL 实例处于镜像关系中”，指定 SQL 镜像端口号（默认端口为 7022），然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="adde3-165">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>

8. <span data-ttu-id="adde3-166">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="adde3-166">Click **OK**.</span></span>

9. <span data-ttu-id="adde3-p116">发布拓扑。在执行此操作时，系统会提示您安装数据库。</span><span class="sxs-lookup"><span data-stu-id="adde3-p116">Publish the topology. When you do so, you will be prompted to install the database.</span></span>

    <span data-ttu-id="adde3-169">在拓扑发布过程中，将要求您定义文件共享路径。</span><span class="sxs-lookup"><span data-stu-id="adde3-169">During the topology publishing process, you will be asked to define a file share path.</span></span> <span data-ttu-id="adde3-170">参与SQL的服务器必须具有对此文件共享的读/写访问权限，镜像要建立。</span><span class="sxs-lookup"><span data-stu-id="adde3-170">The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>

<span data-ttu-id="adde3-171">然后必须在继续下一步之前安装数据库。</span><span class="sxs-lookup"><span data-stu-id="adde3-171">You must then install the database before going on to the next procedure.</span></span>

<span data-ttu-id="adde3-172">设置 SQL 镜像时，应记住以下几点：</span><span class="sxs-lookup"><span data-stu-id="adde3-172">You should keep the following in mind when setting up SQL mirroring:</span></span>

- <span data-ttu-id="adde3-173">如果某个镜像终结点已存在，则会使用其中定义的端口重用该终结点，并将忽略您在拓扑中指定的端口。</span><span class="sxs-lookup"><span data-stu-id="adde3-173">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>

- <span data-ttu-id="adde3-p118">已为同一服务器上的其他应用程序分配的任何端口（包括用于其他 SQL 实例的端口）均不应用于当前安装的 SQL 实例。这意味着，如果在同一服务器上安装了多个 SQL 实例，它们不能将同一端口用于镜像。有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="adde3-p118">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand. This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring. For details, see the following articles:</span></span>

  - [<span data-ttu-id="adde3-177">指定数据库镜像 (服务器网络) </span><span class="sxs-lookup"><span data-stu-id="adde3-177">Specify a Server Network Address (Database Mirroring)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=247346)

  - [<span data-ttu-id="adde3-178">数据库镜像终结点 (SQL Server) </span><span class="sxs-lookup"><span data-stu-id="adde3-178">The Database Mirroring Endpoint (SQL Server)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=247347)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="adde3-179">使用 Skype for Business Server 2015 命令行管理程序 Cmdlet 设置SQL镜像</span><span class="sxs-lookup"><span data-stu-id="adde3-179">Using Skype for Business Server 2015 Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="adde3-180">设置镜像的最简单方法是使用拓扑生成器，但您也可以使用 cmdlet 执行此操作。</span><span class="sxs-lookup"><span data-stu-id="adde3-180">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>

1. <span data-ttu-id="adde3-181">打开 Skype for Business Server 2015 命令行管理程序窗口并运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="adde3-181">Open a Skype for Business Server 2015 Management Shell window and run the following cmdlet:</span></span>

   ```powershell
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose
   ```

    <span data-ttu-id="adde3-182">例如：</span><span class="sxs-lookup"><span data-stu-id="adde3-182">For example:</span></span>

   ```powershell
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose
   ```

    <span data-ttu-id="adde3-183">您将看到以下内容：</span><span class="sxs-lookup"><span data-stu-id="adde3-183">You will see the following:</span></span>

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

2. <span data-ttu-id="adde3-184">确认以下内容：</span><span class="sxs-lookup"><span data-stu-id="adde3-184">Verify the following:</span></span>

    - <span data-ttu-id="adde3-185">如果在主 SQL Server e04-ocs.los_a.lsipt.local\rtc 中启用 Windows 防火墙，则可通过防火墙访问端口 5022。</span><span class="sxs-lookup"><span data-stu-id="adde3-185">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los_a.lsipt.local\rtc.</span></span>

    - <span data-ttu-id="adde3-186">如果在镜像 SQL Server K16-ocs.los_a.lsipt.local\rtc 中启用 Windows 防火墙，则可通过防火墙访问端口 5022。</span><span class="sxs-lookup"><span data-stu-id="adde3-186">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los_a.lsipt.local\rtc.</span></span>

    - <span data-ttu-id="adde3-187">如果在见证 SQL Server AB14-lct.los_a.lsipt.local\rtc 中启用 Windows 防火墙，则可通过防火墙访问端口 7022。</span><span class="sxs-lookup"><span data-stu-id="adde3-187">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los_a.lsipt.local\rtc.</span></span>

   - <span data-ttu-id="adde3-188">在所有主SQL和镜像服务器上运行 SQL 服务器的帐户对文件共享 \\ E04-OCS\csdatabackup 具有读/写权限</span><span class="sxs-lookup"><span data-stu-id="adde3-188">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\E04-OCS\csdatabackup</span></span>

   - <span data-ttu-id="adde3-p119">确认 Windows Management Instrumentation (WMI) 提供程序正在所有这些服务器上运行。该 cmdlet 使用此提供程序查找在所有主、镜像和见证服务器上运行的 SQL Server 服务的帐户信息。</span><span class="sxs-lookup"><span data-stu-id="adde3-p119">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers. The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span>

   - <span data-ttu-id="adde3-191">确认运行此 cmdlet 的帐户有权为所有镜像服务器上的数据和日志文件创建文件夹。</span><span class="sxs-lookup"><span data-stu-id="adde3-191">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span>

   - <span data-ttu-id="adde3-p120">请注意，用于运行 SQL 实例的用户帐户必须具有对文件共享的读/写权限。如果文件共享位于其他服务器上且 SQL 实例运行本地系统帐户，则您必须向承载 SQL 实例的服务器授予文件共享权限。</span><span class="sxs-lookup"><span data-stu-id="adde3-p120">Note that the user account that the SQL instance uses to run must have read/write permission to the file share. If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>

3. <span data-ttu-id="adde3-194">键入 A 并按 Enter。</span><span class="sxs-lookup"><span data-stu-id="adde3-194">Type A and press ENTER.</span></span>

    <span data-ttu-id="adde3-195">将配置镜像。</span><span class="sxs-lookup"><span data-stu-id="adde3-195">The mirroring will be configured.</span></span>

    <span data-ttu-id="adde3-196">**Install-CsMirrorDatabase** 可为主 SQL 存储中存在的所有数据库安装和配置镜像。</span><span class="sxs-lookup"><span data-stu-id="adde3-196">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="adde3-197">如果要仅为特定数据库配置镜像，可以使用 -DatabaseType 选项，或者如果要为除少数数据库之外的所有数据库配置镜像，可以使用 -ExcludeDatabaseList 选项以及要排除的数据库名称的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="adde3-197">If you want to configure mirroring for only specific databases, you can use the -DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>

    <span data-ttu-id="adde3-198">例如，如果将以下选项添加到 **Install-CsMirrorDatabase** 中，则除了 rtcab 和 rtcxds 之外的所有数据库都将进行镜像。</span><span class="sxs-lookup"><span data-stu-id="adde3-198">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>

    `-ExcludeDatabaseList rtcab,rtcxds`

   <span data-ttu-id="adde3-199">例如，如果将以下选项添加到 **Install-CsMirrorDatabase**，则仅镜像 rtcab、rtcshared 和 rtcxds 数据库。</span><span class="sxs-lookup"><span data-stu-id="adde3-199">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>

    `-DatabaseType User`

## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="adde3-200">删除或更改 SQL 镜像</span><span class="sxs-lookup"><span data-stu-id="adde3-200">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="adde3-p122">若要在拓扑生成器中删除池的 SQL 镜像，您必须先使用 cmdlet 删除 SQL Server 中的镜像。随后，您可使用拓扑生成器删除拓扑中的镜像。若要删除 SQL Server 中的镜像，请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="adde3-p122">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server. You can then use Topology Builder to remove the mirror from the topology. To remove the mirror in SQL Server, use the following cmdlet:</span></span>

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

<span data-ttu-id="adde3-204">例如，若要删除镜像并删除针对用户数据库的数据库，请键入：</span><span class="sxs-lookup"><span data-stu-id="adde3-204">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

<span data-ttu-id="adde3-205">`-DropExistingDatabasesOnMirror`该选项会导致从镜像中删除受影响的数据库。</span><span class="sxs-lookup"><span data-stu-id="adde3-205">The  `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>

<span data-ttu-id="adde3-206">然后，若要从拓扑中删除镜像，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="adde3-206">Then, to remove the mirror from the topology, do the following:</span></span>

1. <span data-ttu-id="adde3-207">在拓扑生成器中，右键单击池并单击“编辑属性”。</span><span class="sxs-lookup"><span data-stu-id="adde3-207">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2. <span data-ttu-id="adde3-208">取消选中“启用 SQL 存储镜像”并单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="adde3-208">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>

3. <span data-ttu-id="adde3-209">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="adde3-209">Publish the topology.</span></span>

## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="adde3-210">删除镜像见证</span><span class="sxs-lookup"><span data-stu-id="adde3-210">Removing a Mirroring Witness</span></span>

<span data-ttu-id="adde3-211">如果需要从后端服务器镜像配置中删除见证，请使用此过程。</span><span class="sxs-lookup"><span data-stu-id="adde3-211">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>

1. <span data-ttu-id="adde3-212">在拓扑生成器中，右键单击池并单击“编辑属性”。</span><span class="sxs-lookup"><span data-stu-id="adde3-212">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2. <span data-ttu-id="adde3-213">清除“使用 SQL Server 镜像见证启用自动故障转移”，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="adde3-213">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>

3. <span data-ttu-id="adde3-214">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="adde3-214">Publish the topology.</span></span>

    <span data-ttu-id="adde3-215">发布拓扑后，拓扑生成器将显示一条消息，其中包含以下内容</span><span class="sxs-lookup"><span data-stu-id="adde3-215">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>

   ```console
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    <span data-ttu-id="adde3-216">但是，不要按照此步骤操作，不要键入，因为这样做会  `Uninstall-CsMirrorDatabase` 卸载整个镜像配置。</span><span class="sxs-lookup"><span data-stu-id="adde3-216">However, do not follow that step, and do not type  `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>

4. <span data-ttu-id="adde3-217">若要仅从数据库配置中删除SQL Server，请按照"从数据库镜像会话中删除见证"中的[ (SQL Server) 。 ](https://go.microsoft.com/fwlink/p/?LinkId=268456)</span><span class="sxs-lookup"><span data-stu-id="adde3-217">To remove just the witness from the SQL Server configuration, follow the instructions in [Remove the Witness from a Database Mirroring Session (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268456).</span></span>


