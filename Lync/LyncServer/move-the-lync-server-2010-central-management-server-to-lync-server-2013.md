---
title: 将 Lync Server 2010 中央管理服务器移动到 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move the Lync Server 2010 Central Management Server to Lync Server 2013
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49733602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f301c8f6e11ca3c8f19ed167489bb3fbf51fc63
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743692"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a><span data-ttu-id="b62e6-102">将 Lync Server 2010 中央管理服务器移动到 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b62e6-102">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b62e6-103">_**主题上次修改时间：** 2013-11-25_</span><span class="sxs-lookup"><span data-stu-id="b62e6-103">_**Topic Last Modified:** 2013-11-25_</span></span>

<span data-ttu-id="b62e6-104">从 Lync Server 2010 迁移到 Lync Server 2013 后，您需要将 Lync Server 2010 中央管理服务器移动到 Lync Server 2013 前端服务器或池，然后才能删除旧版 Lync Server 2010 服务器。</span><span class="sxs-lookup"><span data-stu-id="b62e6-104">After migrating from Lync Server 2010 to Lync Server 2013, you need to move the Lync Server 2010 Central Management Server to the Lync Server 2013 Front End Server or pool, before you can remove the legacy Lync Server 2010 server.</span></span>

<span data-ttu-id="b62e6-105">中央管理服务器是单个主/多副本系统，其中数据库的读/写副本由包含中央管理服务器的前端服务器保留。</span><span class="sxs-lookup"><span data-stu-id="b62e6-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="b62e6-106">拓扑中的每台计算机（包括包含中央管理服务器的前端服务器）在安装期间，在计算机上安装了 SQL Server 数据库中的中央管理存储数据的只读副本（默认情况下称为 RTCLOCAL）。部署.</span><span class="sxs-lookup"><span data-stu-id="b62e6-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="b62e6-107">本地数据库通过在所有计算机上作为服务运行的 Lync Server 副本复制程序代理来接收副本更新。</span><span class="sxs-lookup"><span data-stu-id="b62e6-107">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="b62e6-108">中央管理服务器和本地副本上的实际数据库的名称是 XDS，它由 XDS 和 XDS 文件组成。</span><span class="sxs-lookup"><span data-stu-id="b62e6-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="b62e6-109">Master 数据库位置由 Active Directory 域服务中的服务控制点（SCP）引用。</span><span class="sxs-lookup"><span data-stu-id="b62e6-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="b62e6-110">使用 "中央管理" 服务器管理和配置 Lync 服务器的所有工具均使用 SCP 查找中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="b62e6-110">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>

<span data-ttu-id="b62e6-111">成功移动中央管理服务器后，应从原始前端服务器中删除中央管理服务器数据库。</span><span class="sxs-lookup"><span data-stu-id="b62e6-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="b62e6-112">有关删除中央管理服务器数据库的信息，请参阅[删除前端池的 SQL Server 数据库](remove-the-sql-server-database-for-a-front-end-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="b62e6-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>

<span data-ttu-id="b62e6-113">在 Lync Server Management Shell 中使用 Windows PowerShell cmdlet **Move CsManagementServer** ，将数据库从 lync SERVER 2010 sql server 数据库移动到 lync SERVER 2013 sql server 数据库，然后更新 SCP 以指向 lync Server 2013 中央管理服务器位置。</span><span class="sxs-lookup"><span data-stu-id="b62e6-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Lync Server Management Shell to move the database from the Lync Server 2010 SQL Server database to the Lync Server 2013 SQL Server database, and then update the SCP to point to the Lync Server 2013 Central Management Server location.</span></span>

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a><span data-ttu-id="b62e6-114">在移动中央管理服务器之前准备 Lync Server 2013 前端服务器</span><span class="sxs-lookup"><span data-stu-id="b62e6-114">Preparing Lync Server 2013 Front End Servers before moving the Central Management Server</span></span>

<span data-ttu-id="b62e6-115">在移动 Lync Server 2010 中央管理服务器之前，请使用本部分中的步骤准备 Lync Server 2013 前端服务器。</span><span class="sxs-lookup"><span data-stu-id="b62e6-115">Use the procedures in this section to prepare the Lync Server 2013 Front End Servers before you move the Lync Server 2010 Central Management Server.</span></span>

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="b62e6-116">准备企业版前端池</span><span class="sxs-lookup"><span data-stu-id="b62e6-116">To prepare an Enterprise Edition Front End pool</span></span>

1.  <span data-ttu-id="b62e6-117">在要重定位中央管理服务器的 Lync Server 2013 企业版前端池上：登录到安装了 Lync Server 管理外壳的计算机作为**RTCUniversalServerAdmins**组的成员。</span><span class="sxs-lookup"><span data-stu-id="b62e6-117">On the Lync Server 2013 Enterprise Edition Front End pool where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="b62e6-118">你还必须在要安装中央管理存储的数据库上同时拥有 SQL Server 数据库 sysadmin 用户权限和权限。</span><span class="sxs-lookup"><span data-stu-id="b62e6-118">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span>

2.  <span data-ttu-id="b62e6-119">打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="b62e6-119">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="b62e6-120">若要在 Lync Server 2013 SQL Server 数据库中创建新的中央管理存储，请在 Lync Server 命令行管理程序中键入：</span><span class="sxs-lookup"><span data-stu-id="b62e6-120">To create the new Central Management store in the Lync Server 2013 SQL Server database, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  <span data-ttu-id="b62e6-121">确认**Lync Server 前端**服务的状态为 "已**启动**"。</span><span class="sxs-lookup"><span data-stu-id="b62e6-121">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="b62e6-122">准备标准版前端服务器</span><span class="sxs-lookup"><span data-stu-id="b62e6-122">To prepare a Standard Edition Front End Server</span></span>

1.  <span data-ttu-id="b62e6-123">在要重定位中央管理服务器的 Lync Server 2013 标准版前端服务器上：登录到安装了 Lync Server 命令行管理程序的计算机作为**RTCUniversalServerAdmins**组的成员。</span><span class="sxs-lookup"><span data-stu-id="b62e6-123">On the Lync Server 2013 Standard Edition Front End Server where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span>

2.  <span data-ttu-id="b62e6-124">打开 Lync Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="b62e6-124">Open the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="b62e6-125">在 Lync Server 部署向导中，单击 "**准备第一个标准版服务器**"。</span><span class="sxs-lookup"><span data-stu-id="b62e6-125">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="b62e6-126">在 "**执行命令**" 页面上，将 SQL Server Express 作为中央管理服务器进行安装。</span><span class="sxs-lookup"><span data-stu-id="b62e6-126">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="b62e6-127">已创建必要的防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="b62e6-127">Necessary firewall rules are created.</span></span> <span data-ttu-id="b62e6-128">当数据库和必备软件的安装完成后，单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="b62e6-128">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b62e6-129">初始安装可能需要一些时间，但不显示命令输出摘要屏幕的更新。</span><span class="sxs-lookup"><span data-stu-id="b62e6-129">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="b62e6-130">这是由于 SQL Server Express 的安装所致。</span><span class="sxs-lookup"><span data-stu-id="b62e6-130">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="b62e6-131">如果需要监视数据库的安装，请使用 "任务管理器" 监视设置。</span><span class="sxs-lookup"><span data-stu-id="b62e6-131">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

5.  <span data-ttu-id="b62e6-132">若要在 Lync Server 2013 标准版前端服务器上创建新的中心管理存储，请在 Lync Server 命令行管理程序中键入：</span><span class="sxs-lookup"><span data-stu-id="b62e6-132">To create the new Central Management store on the Lync Server 2013 Standard Edition Front End Server, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  <span data-ttu-id="b62e6-133">确认**Lync Server 前端**服务的状态为 "已**启动**"。</span><span class="sxs-lookup"><span data-stu-id="b62e6-133">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a><span data-ttu-id="b62e6-134">将 Lync Server 2010 中央管理服务器移动到 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b62e6-134">To move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

1.  <span data-ttu-id="b62e6-135">在将成为中央管理服务器的 Lync Server 2013 服务器上：登录到安装了 Lync Server Management Shell 的计算机作为**RTCUniversalServerAdmins**组的成员。</span><span class="sxs-lookup"><span data-stu-id="b62e6-135">On the Lync Server 2013 server that will be the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="b62e6-136">您还必须拥有 SQL Server 数据库管理员用户的权限。</span><span class="sxs-lookup"><span data-stu-id="b62e6-136">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="b62e6-137">打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="b62e6-137">Open Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="b62e6-138">在 Lync Server 命令行管理器中，键入：</span><span class="sxs-lookup"><span data-stu-id="b62e6-138">In the Lync Server Management Shell, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="b62e6-139">如果<CODE>Enable-CsTopology</CODE>未成功，请解决阻止命令完成的问题，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="b62e6-139">If <CODE>Enable-CsTopology</CODE> is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="b62e6-140">如果<STRONG>Enable-CsTopology</STRONG>未成功，则移动将失败，并且可能会将拓扑置于没有中央管理存储的状态。</span><span class="sxs-lookup"><span data-stu-id="b62e6-140">If <STRONG>Enable-CsTopology</STRONG> is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span>

    
    </div>

4.  <span data-ttu-id="b62e6-141">在 Lync Server 2013 前端服务器或前端池的 Lync Server 命令行管理程序中，键入：</span><span class="sxs-lookup"><span data-stu-id="b62e6-141">On the Lync Server 2013 Front End Server or Front End pool, in the Lync Server Management Shell, type:</span></span>
    
        Move-CsManagementServer

5.  <span data-ttu-id="b62e6-142">Lync Server Management Shell 显示当前状态和建议状态的服务器、文件存储、数据库存储和服务连接点。</span><span class="sxs-lookup"><span data-stu-id="b62e6-142">Lync Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="b62e6-143">请仔细阅读信息，确认这是预期的源和目标。</span><span class="sxs-lookup"><span data-stu-id="b62e6-143">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="b62e6-144">键入**Y**继续，或按**N**停止移动。</span><span class="sxs-lookup"><span data-stu-id="b62e6-144">Type **Y** to continue, or **N** to stop the move.</span></span>

6.  <span data-ttu-id="b62e6-145">查看由**CsManagementServer**命令生成并解决的任何警告或错误。</span><span class="sxs-lookup"><span data-stu-id="b62e6-145">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span>

7.  <span data-ttu-id="b62e6-146">在 Lync Server 2013 服务器上，打开 "Lync Server 部署向导"。</span><span class="sxs-lookup"><span data-stu-id="b62e6-146">On the Lync Server 2013 server, open the Lync Server Deployment Wizard.</span></span>

8.  <span data-ttu-id="b62e6-147">在 Lync Server 部署向导中，单击 "**安装或更新 Lync Server 系统**"，单击 "**步骤2：设置" 或 "删除 Lync server 组件**"，单击 "**下一步**"，查看摘要，然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="b62e6-147">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

9.  <span data-ttu-id="b62e6-148">在 Lync Server 2010 服务器上，打开 "Lync Server 部署向导"。</span><span class="sxs-lookup"><span data-stu-id="b62e6-148">On the Lync Server 2010 server, open the Lync Server Deployment Wizard.</span></span>

10. <span data-ttu-id="b62e6-149">在 Lync Server 部署向导中，单击 "**安装或更新 Lync Server 系统**"，单击 "**步骤2：设置" 或 "删除 Lync server 组件**"，单击 "**下一步**"，查看摘要，然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="b62e6-149">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

11. <span data-ttu-id="b62e6-150">重新启动 Lync Server 2013 服务器。</span><span class="sxs-lookup"><span data-stu-id="b62e6-150">Reboot the Lync Server 2013 server.</span></span> <span data-ttu-id="b62e6-151">这是必需的，因为访问中央管理服务器数据库的组成员身份发生更改。</span><span class="sxs-lookup"><span data-stu-id="b62e6-151">This is required because of a group membership change to access Central Management Server database.</span></span>

12. <span data-ttu-id="b62e6-152">若要确认与新的中央管理存储进行复制，请在 Lync Server 命令行管理程序中键入：</span><span class="sxs-lookup"><span data-stu-id="b62e6-152">To confirm that replication with the new Central Management store is occurring, in the Lync Server Management Shell, type:</span></span>
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b62e6-153">复制可能需要一些时间来更新所有当前副本。</span><span class="sxs-lookup"><span data-stu-id="b62e6-153">The replication may take some time to update all current replicas.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a><span data-ttu-id="b62e6-154">移动后删除 Lync Server 2010 中央管理存储文件</span><span class="sxs-lookup"><span data-stu-id="b62e6-154">To remove Lync Server 2010 Central Management store files after a move</span></span>

1.  <span data-ttu-id="b62e6-155">在 Lync Server 2010 服务器上：登录到安装了 Lync Server 命令行管理程序的计算机作为**RTCUniversalServerAdmins**组的成员。</span><span class="sxs-lookup"><span data-stu-id="b62e6-155">On the Lync Server 2010 server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="b62e6-156">您还必须拥有 SQL Server 数据库管理员用户的权限。</span><span class="sxs-lookup"><span data-stu-id="b62e6-156">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="b62e6-157">打开 Lync Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="b62e6-157">Open Lync Server Management Shell</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="b62e6-158">在复制完成且稳定之前，不要继续删除以前的数据库文件。</span><span class="sxs-lookup"><span data-stu-id="b62e6-158">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="b62e6-159">如果在完成复制之前删除文件，将中断复制过程，并使新移动的中央管理服务器处于未知状态。</span><span class="sxs-lookup"><span data-stu-id="b62e6-159">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="b62e6-160">使用 cmdlet <STRONG>CsManagementStoreReplicationStatus</STRONG>确认复制状态。</span><span class="sxs-lookup"><span data-stu-id="b62e6-160">Use the cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> to confirm the replication status.</span></span>

    
    </div>

3.  <span data-ttu-id="b62e6-161">若要从 Lync Server 2010 中央管理服务器删除中央管理存储数据库文件，请键入：</span><span class="sxs-lookup"><span data-stu-id="b62e6-161">To remove the Central Management store database files from the Lync Server 2010 Central Management Server, type:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    <span data-ttu-id="b62e6-162">例如：</span><span class="sxs-lookup"><span data-stu-id="b62e6-162">For example:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    <span data-ttu-id="b62e6-163">SQL Server \<\>的 FQDN 是企业版部署中的 Lync Server 2010 后端服务器或标准版服务器的 fqdn。</span><span class="sxs-lookup"><span data-stu-id="b62e6-163">Where the \<FQDN of SQL Server\> is either the Lync Server 2010 Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

