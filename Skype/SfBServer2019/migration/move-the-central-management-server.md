---
title: 移动中央管理服务器
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 迁移到 Skype for Business Server 2019 之后，您需要将移动中央管理服务器到 Skype 业务 Server 2019 前端服务器或池，然后才能删除旧服务器。
ms.openlocfilehash: 805b5c506fdda11bdc24144a0622e674e8ef281b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030523"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="8d069-103">将旧的中央管理服务器移动到 Skype 进行业务服务器 2019</span><span class="sxs-lookup"><span data-stu-id="8d069-103">Move the legacy Central Management Server to Skype for Business Server 2019</span></span>

<span data-ttu-id="8d069-104">迁移后到 Skype 业务服务器 2019年和可以删除旧服务器之前，您需要将中央管理服务器移动到 Skype，业务 Server 2019 前端服务器或池。</span><span class="sxs-lookup"><span data-stu-id="8d069-104">After migrating to Skype for Business Server 2019, and before you can remove the legacy server, you need to move the Central Management Server to the Skype for Business Server 2019 Front End Server or pool.</span></span> 
  
<span data-ttu-id="8d069-105">中央管理服务器是单个母版/多副本系统，数据库的读/写副本由前端服务器包含中央管理服务器。</span><span class="sxs-lookup"><span data-stu-id="8d069-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="8d069-106">在拓扑中，包括前端服务器包含中央管理服务器，每台计算机都安装过程中的计算机上安装 SQL Server 数据库 （名为默认情况下 RTCLOCAL） 中的中央管理存储数据的只读副本和部署。</span><span class="sxs-lookup"><span data-stu-id="8d069-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="8d069-107">本地数据库业务服务器副本复制程序代理的所有计算机上运行作为服务接收通过 Skype 的副本更新。</span><span class="sxs-lookup"><span data-stu-id="8d069-107">The local database receives replica updates by way of the Skype for Business Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="8d069-108">在中央管理服务器和的本地副本的实际数据库的名称为 XDS，组成 xds.mdf 和 xds.ldf 文件。</span><span class="sxs-lookup"><span data-stu-id="8d069-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="8d069-109">服务控制点 (SCP) Active Directory 域服务中被引用的主数据库位置。</span><span class="sxs-lookup"><span data-stu-id="8d069-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="8d069-110">中央管理服务器用于管理和配置 Business Server Skype 的所有工具都使用 SCP 查找中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="8d069-110">All tools that use the Central Management Server to manage and configure Skype for Business Server use the SCP to locate the Central Management store.</span></span>
  
<span data-ttu-id="8d069-111">您已成功移动中央管理服务器后，您应该从原始前端服务器中删除中央管理服务器数据库。</span><span class="sxs-lookup"><span data-stu-id="8d069-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="8d069-112">有关删除中央管理服务器数据库的信息，请参阅[删除前端池的 SQL Server 数据库](remove-the-sql-server-database-for-a-front-end-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="8d069-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>
  
<span data-ttu-id="8d069-113">使用 Windows PowerShell cmdlet 中的业务 Server 命令行管理程序移动 Business Server 2019 SQL Server 数据库的 Skype 的旧安装 SQL Server 数据库的数据库，然后更新 Skype **Move-csmanagementserver**SCP 以指向业务服务器 2019年中央管理服务器位置 Skype。</span><span class="sxs-lookup"><span data-stu-id="8d069-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Skype for Business Server Management Shell to move the database from the legacy install SQL Server database to the Skype for Business Server 2019 SQL Server database, and then update the SCP to point to the Skype for Business Server 2019 Central Management Server location.</span></span> 
  
<span data-ttu-id="8d069-114">使用本节中的过程移动中央管理服务器之前准备 Skype 业务 Server 2019 前端服务器。</span><span class="sxs-lookup"><span data-stu-id="8d069-114">Use the procedures in this section to prepare the Skype for Business Server 2019 Front End Servers before you move the Central Management Server.</span></span>
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="8d069-115">准备 Enterprise Edition 前端池</span><span class="sxs-lookup"><span data-stu-id="8d069-115">To prepare an Enterprise Edition Front End pool</span></span>

1. <span data-ttu-id="8d069-116">上要重定位中央管理服务器的业务服务器 2019 Enterprise Edition 前端池的 Skype，登录到计算机的业务 Server 命令行管理程序 Skype **RTCUniversalServerAdmins 成员的安装**组。</span><span class="sxs-lookup"><span data-stu-id="8d069-116">On the Skype for Business Server 2019 Enterprise Edition Front End pool where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="8d069-117">此外必须在要安装中央管理存储的数据库具有 SQL Server 数据库的系统管理员用户权限和权限。</span><span class="sxs-lookup"><span data-stu-id="8d069-117">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span> 
    
2. <span data-ttu-id="8d069-118">打开 Skype 业务 Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="8d069-118">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="8d069-119">若要创建新的中央管理存储中的业务服务器 2019 SQL Server 数据库中的业务 Server Management Shell，Skype Skype 键入：</span><span class="sxs-lookup"><span data-stu-id="8d069-119">To create the new Central Management store in the Skype for Business Server 2019 SQL Server database, in the Skype for Business Server Management Shell, type:</span></span>
    
  ```
  Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
  ```

4. <span data-ttu-id="8d069-120">确认**启动** **Skype 的业务 Server 前端**服务的状态。</span><span class="sxs-lookup"><span data-stu-id="8d069-120">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="8d069-121">准备 Standard Edition 前端服务器</span><span class="sxs-lookup"><span data-stu-id="8d069-121">To prepare a Standard Edition Front End Server</span></span>

1. <span data-ttu-id="8d069-122">上的业务 Server 2019 Standard Edition 前端服务器要重定位中央管理服务器 Skype，登录到计算机的业务 Server 命令行管理程序 Skype **RTCUniversalServerAdmins 成员的安装**组。</span><span class="sxs-lookup"><span data-stu-id="8d069-122">On the Skype for Business Server 2019 Standard Edition Front End Server where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> 
    
2. <span data-ttu-id="8d069-123">打开 Skype 业务 Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="8d069-123">Open the Skype for Business Server Deployment Wizard.</span></span>
    
3. <span data-ttu-id="8d069-124">在业务 Server 部署向导的 Skype，单击**准备第一个 Standard Edition server**。</span><span class="sxs-lookup"><span data-stu-id="8d069-124">In the Skype for Business Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>
    
4. <span data-ttu-id="8d069-125">在**正在执行命令**页上 SQL Server Express 安装为中央管理服务器。</span><span class="sxs-lookup"><span data-stu-id="8d069-125">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="8d069-126">创建必要防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="8d069-126">Necessary firewall rules are created.</span></span> <span data-ttu-id="8d069-127">完成数据库和必备软件的安装后，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="8d069-127">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8d069-128">在初始安装可能需要一些时间与没有可见的更新对命令输出摘要屏幕。</span><span class="sxs-lookup"><span data-stu-id="8d069-128">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="8d069-129">这是由于安装 SQL Server Express。</span><span class="sxs-lookup"><span data-stu-id="8d069-129">This is due to the installation of SQL Server Express.</span></span> <span data-ttu-id="8d069-130">如果您需要监视安装数据库，请使用任务管理器监视安装程序。</span><span class="sxs-lookup"><span data-stu-id="8d069-130">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span> 
  
5. <span data-ttu-id="8d069-131">若要业务服务器 2019 Standard Edition 前端服务器，业务 Server Management Shell，Skype Skype 上创建新的中央管理存储键入：</span><span class="sxs-lookup"><span data-stu-id="8d069-131">To create the new Central Management store on the Skype for Business Server 2019 Standard Edition Front End Server, in the Skype for Business Server Management Shell, type:</span></span> 
    
  ```
  Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
  ```

6. <span data-ttu-id="8d069-132">确认**启动** **Skype 的业务 Server 前端**服务的状态。</span><span class="sxs-lookup"><span data-stu-id="8d069-132">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="8d069-133">将旧的业务服务器 2019年到 Skype 安装中央管理服务器</span><span class="sxs-lookup"><span data-stu-id="8d069-133">To move the legacy installs Central Management Server to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="8d069-134">上将中央管理服务器的业务服务器 2019年服务器 Skype，登录到计算机的业务 Server 命令行管理程序 Skype 以**RTCUniversalServerAdmins**组的成员身份的安装。</span><span class="sxs-lookup"><span data-stu-id="8d069-134">On the Skype for Business Server 2019 server that will be the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="8d069-135">您还必须具有 SQL Server 数据库管理员的用户权限和权限。</span><span class="sxs-lookup"><span data-stu-id="8d069-135">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="8d069-136">打开 Skype 业务 Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="8d069-136">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="8d069-137">在业务 Server Management Shell 的 Skype，键入：</span><span class="sxs-lookup"><span data-stu-id="8d069-137">In the Skype for Business Server Management Shell, type:</span></span> 
    
  ```
  Enable-CsTopology
  ```

    > [!CAUTION]
    > <span data-ttu-id="8d069-138">如果`Enable-CsTopology`不成功，解决此问题，然后再继续完成阻止此命令。</span><span class="sxs-lookup"><span data-stu-id="8d069-138">If `Enable-CsTopology` is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="8d069-139">如果**Enable-cstopology**不成功，移动将失败，它可能导致您的拓扑处于状态没有中央管理存储的位置。</span><span class="sxs-lookup"><span data-stu-id="8d069-139">If **Enable-CsTopology** is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span> 
  
4. <span data-ttu-id="8d069-140">对于业务 Server 2019 前端服务器或前端池中的业务 Server Management Shell，Skype Skype 上键入：</span><span class="sxs-lookup"><span data-stu-id="8d069-140">On the Skype for Business Server 2019 Front End Server or Front End pool, in the Skype for Business Server Management Shell, type:</span></span> 
    
  ```
  Move-CsManagementServer
  ```

5. <span data-ttu-id="8d069-141">业务 Server Management Shell 的 Skype 显示服务器、 文件存储、 数据库存储和当前状态和已建议状态的服务连接点。</span><span class="sxs-lookup"><span data-stu-id="8d069-141">Skype for Business Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="8d069-142">仔细阅读信息，并确认这是预期的源和目标。</span><span class="sxs-lookup"><span data-stu-id="8d069-142">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="8d069-143">键入**Y**以继续或**N**停止移动。</span><span class="sxs-lookup"><span data-stu-id="8d069-143">Type **Y** to continue, or **N** to stop the move.</span></span> 
    
6. <span data-ttu-id="8d069-144">查看所有警告或错误**Move-csmanagementserver**命令生成并解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="8d069-144">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span> 
    
7. <span data-ttu-id="8d069-145">在业务服务器 2019年服务器 Skype，打开业务 Server 部署向导 Skype。</span><span class="sxs-lookup"><span data-stu-id="8d069-145">On the Skype for Business Server 2019 server, open the Skype for Business Server Deployment Wizard.</span></span> 
    
8. <span data-ttu-id="8d069-146">Skype 的业务 Server 部署向导，在中，单击**安装或更新 Skype 业务 Server 系统**，单击**步骤 2： 安装或删除业务服务器组件的 Skype**单击**下一步**，查看摘要，然后单击**完成**.</span><span class="sxs-lookup"><span data-stu-id="8d069-146">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
9. <span data-ttu-id="8d069-147">在旧上安装服务器，打开部署向导。</span><span class="sxs-lookup"><span data-stu-id="8d069-147">On the legacy install server, open the Deployment Wizard.</span></span> 
    
10. <span data-ttu-id="8d069-148">Skype 的业务 Server 部署向导，在中，单击**安装或更新 Skype 业务 Server 系统**，单击**步骤 2： 安装或删除业务服务器组件的 Skype**单击**下一步**，查看摘要，然后单击**完成**.</span><span class="sxs-lookup"><span data-stu-id="8d069-148">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
11. <span data-ttu-id="8d069-149">重新启动业务服务器 2019年服务器 Skype。</span><span class="sxs-lookup"><span data-stu-id="8d069-149">Reboot the Skype for Business Server 2019 server.</span></span> <span data-ttu-id="8d069-150">这是所需由于组成员身份更改中央管理服务器数据库的访问。</span><span class="sxs-lookup"><span data-stu-id="8d069-150">This is required because of a group membership change to access Central Management Server database.</span></span>
    
12. <span data-ttu-id="8d069-151">若要确认新的中央管理存储出现，则在进行复制的业务 Server Management Shell，Skype 键入：</span><span class="sxs-lookup"><span data-stu-id="8d069-151">To confirm that replication with the new Central Management store is occurring, in the Skype for Business Server Management Shell, type:</span></span> 
    
  ```
  Get-CsManagementStoreReplicationStatus
  ```

    > [!NOTE]
    > <span data-ttu-id="8d069-152">复制可能需要一些时间来更新当前所有副本。</span><span class="sxs-lookup"><span data-stu-id="8d069-152">The replication may take some time to update all current replicas.</span></span> 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a><span data-ttu-id="8d069-153">移动后删除旧安装中央管理存储文件</span><span class="sxs-lookup"><span data-stu-id="8d069-153">To remove legacy install Central Management store files after a move</span></span>

1. <span data-ttu-id="8d069-154">在旧安装服务器上，登录到计算机的业务 Server 命令行管理程序 Skype 以**RTCUniversalServerAdmins**组的成员身份的安装。</span><span class="sxs-lookup"><span data-stu-id="8d069-154">On the legacy install server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="8d069-155">您还必须具有 SQL Server 数据库管理员的用户权限和权限。</span><span class="sxs-lookup"><span data-stu-id="8d069-155">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="8d069-156">打开 Skype 业务 Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="8d069-156">Open Skype for Business Server Management Shell</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="8d069-157">请不要继续删除以前的数据库文件之前复制已完成，稳定。</span><span class="sxs-lookup"><span data-stu-id="8d069-157">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="8d069-158">如果删除之前完成复制文件，您将会中断复制过程，并将新移动中央管理服务器保留未知状态。</span><span class="sxs-lookup"><span data-stu-id="8d069-158">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="8d069-159">使用**Get-csmanagementstorereplicationstatus** cmdlet 确认复制状态。</span><span class="sxs-lookup"><span data-stu-id="8d069-159">Use the cmdlet **Get-CsManagementStoreReplicationStatus** to confirm the replication status.</span></span> 
  
3. <span data-ttu-id="8d069-160">若要从旧安装中央管理服务器中删除中央管理存储数据库文件，请键入：</span><span class="sxs-lookup"><span data-stu-id="8d069-160">To remove the Central Management store database files from the legacy install Central Management Server, type:</span></span>
    
  ```
  Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
  ```

    <span data-ttu-id="8d069-161">例如：</span><span class="sxs-lookup"><span data-stu-id="8d069-161">For example:</span></span>
    
  ```
  Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
  ```

    <span data-ttu-id="8d069-162">其中_\<FQDN SQL Server\>_ 是任一的传统安装在 Enterprise Edition 部署中或 Standard Edition 服务器的 FQDN 的后端服务器。</span><span class="sxs-lookup"><span data-stu-id="8d069-162">Where the  _\<FQDN of SQL Server\>_ is either the legacy install Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span> 
    

