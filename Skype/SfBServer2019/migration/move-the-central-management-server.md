---
title: 移动中央管理服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 迁移到 Skype for business Server 2019 后, 您需要将中央管理服务器移动到 Skype for business 服务器2019前端服务器或池, 然后才能删除旧服务器。
ms.openlocfilehash: 5e16145b6695a9ee7006ab7d5321af9e478d7c37
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291296"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="55102-103">将旧式中央管理服务器移动到 Skype for business Server 2019</span><span class="sxs-lookup"><span data-stu-id="55102-103">Move the legacy Central Management Server to Skype for Business Server 2019</span></span>

<span data-ttu-id="55102-104">迁移到 Skype for Business Server 2019 后, 在删除旧服务器之前, 需要将中央管理服务器移动到 Skype for business 服务器2019前端服务器或池。</span><span class="sxs-lookup"><span data-stu-id="55102-104">After migrating to Skype for Business Server 2019, and before you can remove the legacy server, you need to move the Central Management Server to the Skype for Business Server 2019 Front End Server or pool.</span></span> 
  
<span data-ttu-id="55102-105">中央管理服务器是单个主/多副本系统, 其中数据库的读/写副本由包含中央管理服务器的前端服务器保留。</span><span class="sxs-lookup"><span data-stu-id="55102-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="55102-106">拓扑中的每台计算机 (包括包含中央管理服务器的前端服务器) 在安装期间, 在计算机上安装了 SQL Server 数据库中的中央管理存储数据的只读副本 (默认情况下称为 RTCLOCAL)。部署.</span><span class="sxs-lookup"><span data-stu-id="55102-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="55102-107">本地数据库通过在所有计算机上作为服务运行的 Skype for Business Server 副本复制程序代理来接收副本更新。</span><span class="sxs-lookup"><span data-stu-id="55102-107">The local database receives replica updates by way of the Skype for Business Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="55102-108">中央管理服务器和本地副本上的实际数据库的名称是 XDS, 它由 XDS 和 XDS 文件组成。</span><span class="sxs-lookup"><span data-stu-id="55102-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="55102-109">Master 数据库位置由 Active Directory 域服务中的服务控制点 (SCP) 引用。</span><span class="sxs-lookup"><span data-stu-id="55102-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="55102-110">使用中心管理服务器管理和配置 Skype for Business 服务器的所有工具均使用 SCP 查找中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="55102-110">All tools that use the Central Management Server to manage and configure Skype for Business Server use the SCP to locate the Central Management store.</span></span>
  
<span data-ttu-id="55102-111">成功移动中央管理服务器后, 应从原始前端服务器中删除中央管理服务器数据库。</span><span class="sxs-lookup"><span data-stu-id="55102-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="55102-112">有关删除中央管理服务器数据库的信息, 请参阅[删除前端池的 SQL Server 数据库](remove-the-sql-server-database-for-a-front-end-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="55102-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>
  
<span data-ttu-id="55102-113">在 Skype for Business Server Management Shell 中使用 Windows PowerShell cmdlet **Move CsManagementServer** , 将数据库从旧版安装 SQL server 数据库移动到 Skype For business SERVER 2019 SQL server 数据库, 然后更新SCP 指向 Skype for Business Server 2019 中央管理服务器位置。</span><span class="sxs-lookup"><span data-stu-id="55102-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Skype for Business Server Management Shell to move the database from the legacy install SQL Server database to the Skype for Business Server 2019 SQL Server database, and then update the SCP to point to the Skype for Business Server 2019 Central Management Server location.</span></span> 
  
<span data-ttu-id="55102-114">在移动中央管理服务器之前, 使用本部分中的步骤准备 Skype for business Server 2019 前端服务器。</span><span class="sxs-lookup"><span data-stu-id="55102-114">Use the procedures in this section to prepare the Skype for Business Server 2019 Front End Servers before you move the Central Management Server.</span></span>
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="55102-115">准备企业版前端池</span><span class="sxs-lookup"><span data-stu-id="55102-115">To prepare an Enterprise Edition Front End pool</span></span>

1. <span data-ttu-id="55102-116">在要在其中重新定位中央管理服务器的 Skype for Business 服务器2019企业版前端池上, 登录到安装了 Skype for business Server Management Shell 的计算机作为 RTCUniversalServerAdmins 的成员。 \*\*\*\* 组。</span><span class="sxs-lookup"><span data-stu-id="55102-116">On the Skype for Business Server 2019 Enterprise Edition Front End pool where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="55102-117">你还必须在要安装中央管理存储的数据库上同时拥有 SQL Server 数据库 sysadmin 用户权限和权限。</span><span class="sxs-lookup"><span data-stu-id="55102-117">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span> 
    
2. <span data-ttu-id="55102-118">打开 Skype for Business 服务器命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="55102-118">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="55102-119">若要在 Skype for business Server 2019 SQL Server 数据库中创建新的中央管理存储, 请在 Skype for business Server Management Shell 中键入:</span><span class="sxs-lookup"><span data-stu-id="55102-119">To create the new Central Management store in the Skype for Business Server 2019 SQL Server database, in the Skype for Business Server Management Shell, type:</span></span>
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. <span data-ttu-id="55102-120">确认**已启动** **Skype For business Server 前端**服务的状态。</span><span class="sxs-lookup"><span data-stu-id="55102-120">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="55102-121">准备标准版前端服务器</span><span class="sxs-lookup"><span data-stu-id="55102-121">To prepare a Standard Edition Front End Server</span></span>

1. <span data-ttu-id="55102-122">在要在其中重新定位中央管理服务器的 Skype for Business Server 2019 标准版前端服务器上, 登录到安装了 Skype for business Server Management Shell 的计算机作为 RTCUniversalServerAdmins 的成员。 \*\*\*\* 组。</span><span class="sxs-lookup"><span data-stu-id="55102-122">On the Skype for Business Server 2019 Standard Edition Front End Server where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> 
    
2. <span data-ttu-id="55102-123">打开 Skype for Business 服务器部署向导。</span><span class="sxs-lookup"><span data-stu-id="55102-123">Open the Skype for Business Server Deployment Wizard.</span></span>
    
3. <span data-ttu-id="55102-124">在 "Skype for Business 服务器部署" 向导中, 单击 "**准备第一个标准版服务器**"。</span><span class="sxs-lookup"><span data-stu-id="55102-124">In the Skype for Business Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>
    
4. <span data-ttu-id="55102-125">在 "**执行命令**" 页面上, 将 SQL Server Express 作为中央管理服务器进行安装。</span><span class="sxs-lookup"><span data-stu-id="55102-125">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="55102-126">已创建必要的防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="55102-126">Necessary firewall rules are created.</span></span> <span data-ttu-id="55102-127">当数据库和必备软件的安装完成后, 单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="55102-127">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="55102-128">初始安装可能需要一些时间, 但不显示命令输出摘要屏幕的更新。</span><span class="sxs-lookup"><span data-stu-id="55102-128">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="55102-129">这是由于 SQL Server Express 的安装所致。</span><span class="sxs-lookup"><span data-stu-id="55102-129">This is due to the installation of SQL Server Express.</span></span> <span data-ttu-id="55102-130">如果需要监视数据库的安装, 请使用 "任务管理器" 监视设置。</span><span class="sxs-lookup"><span data-stu-id="55102-130">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span> 
  
5. <span data-ttu-id="55102-131">若要在 Skype for business Server 2019 标准版前端服务器上创建新的中央管理存储, 请在 Skype for business Server Management Shell 中键入:</span><span class="sxs-lookup"><span data-stu-id="55102-131">To create the new Central Management store on the Skype for Business Server 2019 Standard Edition Front End Server, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. <span data-ttu-id="55102-132">确认**已启动** **Skype For business Server 前端**服务的状态。</span><span class="sxs-lookup"><span data-stu-id="55102-132">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="55102-133">将旧式安装中央管理服务器移动到 Skype for business Server 2019</span><span class="sxs-lookup"><span data-stu-id="55102-133">To move the legacy installs Central Management Server to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="55102-134">在将成为中央管理服务器的 Skype for Business Server 2019 服务器上, 登录到安装了 Skype for business 服务器管理外壳的计算机作为**RTCUniversalServerAdmins**组的成员。</span><span class="sxs-lookup"><span data-stu-id="55102-134">On the Skype for Business Server 2019 server that will be the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="55102-135">您还必须拥有 SQL Server 数据库管理员用户的权限。</span><span class="sxs-lookup"><span data-stu-id="55102-135">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="55102-136">打开 Skype for Business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="55102-136">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="55102-137">在 Skype for Business 服务器命令行管理程序中, 键入:</span><span class="sxs-lookup"><span data-stu-id="55102-137">In the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Enable-CsTopology
   ```

    > [!CAUTION]
    > <span data-ttu-id="55102-138">如果`Enable-CsTopology`未成功, 请解决阻止命令完成的问题, 然后再继续。</span><span class="sxs-lookup"><span data-stu-id="55102-138">If `Enable-CsTopology` is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="55102-139">如果**Enable-CsTopology**未成功, 则移动将失败, 并且可能会将拓扑置于没有中央管理存储的状态。</span><span class="sxs-lookup"><span data-stu-id="55102-139">If **Enable-CsTopology** is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span> 
  
4. <span data-ttu-id="55102-140">在 skype for business Server 2019 前端服务器或前端池的 Skype for business 服务器管理外壳中, 键入:</span><span class="sxs-lookup"><span data-stu-id="55102-140">On the Skype for Business Server 2019 Front End Server or Front End pool, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Move-CsManagementServer
   ```

5. <span data-ttu-id="55102-141">Skype for Business 服务器管理外壳显示当前状态和建议状态的服务器、文件存储、数据库存储和服务连接点。</span><span class="sxs-lookup"><span data-stu-id="55102-141">Skype for Business Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="55102-142">请仔细阅读信息, 确认这是预期的源和目标。</span><span class="sxs-lookup"><span data-stu-id="55102-142">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="55102-143">键入**Y**继续, 或按**N**停止移动。</span><span class="sxs-lookup"><span data-stu-id="55102-143">Type **Y** to continue, or **N** to stop the move.</span></span> 
    
6. <span data-ttu-id="55102-144">查看由**CsManagementServer**命令生成并解决的任何警告或错误。</span><span class="sxs-lookup"><span data-stu-id="55102-144">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span> 
    
7. <span data-ttu-id="55102-145">在 Skype for business Server 2019 服务器上, 打开 "Skype for Business 服务器部署" 向导。</span><span class="sxs-lookup"><span data-stu-id="55102-145">On the Skype for Business Server 2019 server, open the Skype for Business Server Deployment Wizard.</span></span> 
    
8. <span data-ttu-id="55102-146">在 "Skype for Business 服务器部署向导" 中, 单击 "**安装或更新 skype for Business 服务器系统**", 单击 "**步骤 2: 设置" 或 "删除 Skype for Business 服务器" 组件**, 单击 "**下一步**", 查看摘要, 然后单击 "**完成"**.</span><span class="sxs-lookup"><span data-stu-id="55102-146">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
9. <span data-ttu-id="55102-147">在旧版安装服务器上, 打开 "部署向导"。</span><span class="sxs-lookup"><span data-stu-id="55102-147">On the legacy install server, open the Deployment Wizard.</span></span> 
    
10. <span data-ttu-id="55102-148">在 "Skype for Business 服务器部署向导" 中, 单击 "**安装或更新 skype for Business 服务器系统**", 单击 "**步骤 2: 设置" 或 "删除 Skype for Business 服务器" 组件**, 单击 "**下一步**", 查看摘要, 然后单击 "**完成"**.</span><span class="sxs-lookup"><span data-stu-id="55102-148">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
11. <span data-ttu-id="55102-149">重新启动 Skype for Business Server 2019 服务器。</span><span class="sxs-lookup"><span data-stu-id="55102-149">Reboot the Skype for Business Server 2019 server.</span></span> <span data-ttu-id="55102-150">这是必需的, 因为访问中央管理服务器数据库的组成员身份发生更改。</span><span class="sxs-lookup"><span data-stu-id="55102-150">This is required because of a group membership change to access Central Management Server database.</span></span>
    
12. <span data-ttu-id="55102-151">若要确认与新的中央管理存储进行复制, 请在 Skype for business Server Management Shell 中键入:</span><span class="sxs-lookup"><span data-stu-id="55102-151">To confirm that replication with the new Central Management store is occurring, in the Skype for Business Server Management Shell, type:</span></span> 
    
    ```
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > <span data-ttu-id="55102-152">复制可能需要一些时间来更新所有当前副本。</span><span class="sxs-lookup"><span data-stu-id="55102-152">The replication may take some time to update all current replicas.</span></span> 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a><span data-ttu-id="55102-153">移动后删除旧版安装中央管理存储文件</span><span class="sxs-lookup"><span data-stu-id="55102-153">To remove legacy install Central Management store files after a move</span></span>

1. <span data-ttu-id="55102-154">在旧版安装服务器上, 登录到安装了 Skype for Business 服务器管理外壳的计算机作为**RTCUniversalServerAdmins**组的成员。</span><span class="sxs-lookup"><span data-stu-id="55102-154">On the legacy install server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="55102-155">您还必须拥有 SQL Server 数据库管理员用户的权限。</span><span class="sxs-lookup"><span data-stu-id="55102-155">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="55102-156">打开 Skype for Business 服务器命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="55102-156">Open Skype for Business Server Management Shell</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="55102-157">在复制完成且稳定之前, 不要继续删除以前的数据库文件。</span><span class="sxs-lookup"><span data-stu-id="55102-157">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="55102-158">如果在完成复制之前删除文件, 将中断复制过程, 并使新移动的中央管理服务器处于未知状态。</span><span class="sxs-lookup"><span data-stu-id="55102-158">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="55102-159">使用 cmdlet **CsManagementStoreReplicationStatus**确认复制状态。</span><span class="sxs-lookup"><span data-stu-id="55102-159">Use the cmdlet **Get-CsManagementStoreReplicationStatus** to confirm the replication status.</span></span> 
  
3. <span data-ttu-id="55102-160">若要从旧版安装中央管理服务器中删除中央管理存储数据库文件, 请键入:</span><span class="sxs-lookup"><span data-stu-id="55102-160">To remove the Central Management store database files from the legacy install Central Management Server, type:</span></span>
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    <span data-ttu-id="55102-161">例如：</span><span class="sxs-lookup"><span data-stu-id="55102-161">For example:</span></span>
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    <span data-ttu-id="55102-162">_ \<SQL Server\>的 FQDN_是企业版部署中的旧安装后端服务器或标准版服务器的 fqdn。</span><span class="sxs-lookup"><span data-stu-id="55102-162">Where the  _\<FQDN of SQL Server\>_ is either the legacy install Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span> 
    

