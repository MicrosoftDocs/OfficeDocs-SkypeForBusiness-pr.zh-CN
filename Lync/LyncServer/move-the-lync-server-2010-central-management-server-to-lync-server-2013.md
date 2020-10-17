---
title: 将 Lync Server 2010 中央管理服务器移动到 Lync Server 2013
description: 将 Lync Server 2010 中央管理服务器移动到 Lync Server 2013。
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
ms.openlocfilehash: 19d53d797375b1eb8fde72f6b999e509b97f85ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571278"
---
# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a><span data-ttu-id="73af3-103">将 Lync Server 2010 中央管理服务器移动到 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73af3-103">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73af3-104">_**上次修改的主题：** 2013-11-25_</span><span class="sxs-lookup"><span data-stu-id="73af3-104">_**Topic Last Modified:** 2013-11-25_</span></span>

<span data-ttu-id="73af3-105">从 Lync Server 2010 迁移到 Lync Server 2013 之后，您需要将 Lync Server 2010 中心管理服务器移动到 Lync Server 2013 前端服务器或池，然后才能删除旧版 Lync Server 2010 服务器。</span><span class="sxs-lookup"><span data-stu-id="73af3-105">After migrating from Lync Server 2010 to Lync Server 2013, you need to move the Lync Server 2010 Central Management Server to the Lync Server 2013 Front End Server or pool, before you can remove the legacy Lync Server 2010 server.</span></span>

<span data-ttu-id="73af3-106">中央管理服务器是单个主/多副本系统，其中数据库的读/写副本由包含中央管理服务器的前端服务器保留。</span><span class="sxs-lookup"><span data-stu-id="73af3-106">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="73af3-107">拓扑中的每台计算机（包括包含中央管理服务器的前端服务器）都具有 SQL Server (数据库中的中央管理存储数据的只读副本，默认情况下，RTCLOCAL 在安装和部署过程中) 安装在计算机上。</span><span class="sxs-lookup"><span data-stu-id="73af3-107">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="73af3-108">本地数据库通过作为所有计算机上的服务运行的 Lync Server 副本复制器代理来接收副本更新。</span><span class="sxs-lookup"><span data-stu-id="73af3-108">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="73af3-109">中央管理服务器和本地副本上的实际数据库的名称为 XDS，它由 XDS 和 XDS 文件组成。</span><span class="sxs-lookup"><span data-stu-id="73af3-109">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="73af3-110">主数据库位置由 Active Directory 域服务中 (SCP) 的服务控制点引用。</span><span class="sxs-lookup"><span data-stu-id="73af3-110">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="73af3-111">使用中央管理服务器来管理和配置 Lync Server 的所有工具都使用 SCP 查找中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="73af3-111">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>

<span data-ttu-id="73af3-112">成功移动中央管理服务器后，应从原始前端服务器中删除中央管理服务器数据库。</span><span class="sxs-lookup"><span data-stu-id="73af3-112">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="73af3-113">有关删除中央管理服务器数据库的信息，请参阅 [删除前端池的 SQL Server 数据库](remove-the-sql-server-database-for-a-front-end-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="73af3-113">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>

<span data-ttu-id="73af3-114">在 Lync Server 命令行管理 **程序** 中使用 Windows PowerShell cmdlet move-csmanagementserver 在 Lync Server 命令行管理程序中，将数据库从 lync SERVER 2010 sql server 数据库移动到 lync SERVER 2013 sql server 数据库，然后将 SCP 更新为指向 lync Server 2013 中央管理服务器位置。</span><span class="sxs-lookup"><span data-stu-id="73af3-114">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Lync Server Management Shell to move the database from the Lync Server 2010 SQL Server database to the Lync Server 2013 SQL Server database, and then update the SCP to point to the Lync Server 2013 Central Management Server location.</span></span>

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a><span data-ttu-id="73af3-115">在移动中央管理服务器之前准备 Lync Server 2013 前端服务器</span><span class="sxs-lookup"><span data-stu-id="73af3-115">Preparing Lync Server 2013 Front End Servers before moving the Central Management Server</span></span>

<span data-ttu-id="73af3-116">使用本节中的过程准备 Lync Server 2013 前端服务器，然后再移动 Lync Server 2010 中央管理服务器。</span><span class="sxs-lookup"><span data-stu-id="73af3-116">Use the procedures in this section to prepare the Lync Server 2013 Front End Servers before you move the Lync Server 2010 Central Management Server.</span></span>

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="73af3-117">准备企业版前端池</span><span class="sxs-lookup"><span data-stu-id="73af3-117">To prepare an Enterprise Edition Front End pool</span></span>

1.  <span data-ttu-id="73af3-118">在要重定位中央管理服务器的 Lync Server 2013 Enterprise Edition 前端池上：登录到安装了 Lync Server 命令行管理程序的计算机作为 **RTCUniversalServerAdmins** 组的成员。</span><span class="sxs-lookup"><span data-stu-id="73af3-118">On the Lync Server 2013 Enterprise Edition Front End pool where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="73af3-119">此外，还必须在要安装中央管理存储的数据库上具有 SQL Server 数据库 sysadmin 用户权限和权限。</span><span class="sxs-lookup"><span data-stu-id="73af3-119">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span>

2.  <span data-ttu-id="73af3-120">打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="73af3-120">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="73af3-121">若要在 Lync Server 2013 SQL Server 数据库中创建新的中央管理存储，请在 Lync Server 命令行管理程序中键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="73af3-121">To create the new Central Management store in the Lync Server 2013 SQL Server database, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  <span data-ttu-id="73af3-122">确认“Lync Server 前端”\*\*\*\* 服务的状态为“已启动”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="73af3-122">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="73af3-123">准备标准版前端服务器</span><span class="sxs-lookup"><span data-stu-id="73af3-123">To prepare a Standard Edition Front End Server</span></span>

1.  <span data-ttu-id="73af3-124">在要重新定位中央管理服务器的 Lync Server 2013 Standard Edition 前端服务器上：登录到安装了 Lync Server 命令行管理程序的计算机作为 **RTCUniversalServerAdmins** 组的成员。</span><span class="sxs-lookup"><span data-stu-id="73af3-124">On the Lync Server 2013 Standard Edition Front End Server where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span>

2.  <span data-ttu-id="73af3-125">打开“Lync Server 部署向导”。</span><span class="sxs-lookup"><span data-stu-id="73af3-125">Open the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="73af3-126">在 "Lync Server 部署向导" 中，单击 " **准备第一个 Standard Edition Server**"。</span><span class="sxs-lookup"><span data-stu-id="73af3-126">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="73af3-127">在 " **正在执行命令** " 页上，SQL Server Express 安装为中央管理服务器。</span><span class="sxs-lookup"><span data-stu-id="73af3-127">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="73af3-128">创建必需的防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="73af3-128">Necessary firewall rules are created.</span></span> <span data-ttu-id="73af3-129">安装数据库和必备软件后，单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="73af3-129">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="73af3-130">初始安装可能要花费一些时间，这期间命令输出摘要屏幕上不显示更新。</span><span class="sxs-lookup"><span data-stu-id="73af3-130">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="73af3-131">这是因为安装了 SQL Server Express。</span><span class="sxs-lookup"><span data-stu-id="73af3-131">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="73af3-132">如果需要监视数据库安装，请使用任务管理器监视安装过程。</span><span class="sxs-lookup"><span data-stu-id="73af3-132">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

5.  <span data-ttu-id="73af3-133">若要在 Lync Server 2013 Standard Edition 前端服务器上创建新的中央管理存储，请在 Lync Server 命令行管理程序中键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="73af3-133">To create the new Central Management store on the Lync Server 2013 Standard Edition Front End Server, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  <span data-ttu-id="73af3-134">确认“Lync Server 前端”\*\*\*\* 服务的状态为“已启动”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="73af3-134">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a><span data-ttu-id="73af3-135">将 Lync Server 2010 中央管理服务器移动到 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73af3-135">To move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

1.  <span data-ttu-id="73af3-136">在将成为中央管理服务器的 Lync Server 2013 服务器上：登录到安装了 Lync Server 命令行管理程序的计算机作为 **RTCUniversalServerAdmins** 组的成员。</span><span class="sxs-lookup"><span data-stu-id="73af3-136">On the Lync Server 2013 server that will be the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="73af3-137">您还必须具有 SQL Server 数据库管理员用户权限。</span><span class="sxs-lookup"><span data-stu-id="73af3-137">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="73af3-138">打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="73af3-138">Open Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="73af3-139">在 Lync Server 命令行管理程序中，键入：</span><span class="sxs-lookup"><span data-stu-id="73af3-139">In the Lync Server Management Shell, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="73af3-140">如果 <CODE>Enable-CsTopology</CODE> 未成功，请先解决阻止命令完成的问题，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="73af3-140">If <CODE>Enable-CsTopology</CODE> is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="73af3-141">如果 <STRONG>enable-cstopology</STRONG> 不成功，移动将会失败，并且可能会使拓扑处于没有中央管理存储的状态。</span><span class="sxs-lookup"><span data-stu-id="73af3-141">If <STRONG>Enable-CsTopology</STRONG> is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span>

    
    </div>

4.  <span data-ttu-id="73af3-142">在 lync Server 2013 前端服务器或前端池上的 Lync Server 命令行管理程序中，键入：</span><span class="sxs-lookup"><span data-stu-id="73af3-142">On the Lync Server 2013 Front End Server or Front End pool, in the Lync Server Management Shell, type:</span></span>
    
        Move-CsManagementServer

5.  <span data-ttu-id="73af3-143">Lync Server 命令行管理程序显示服务器、文件存储、数据库存储以及当前状态和建议状态的服务连接点。</span><span class="sxs-lookup"><span data-stu-id="73af3-143">Lync Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="73af3-144">请仔细查看这些信息，确认这是预期的源和目标。</span><span class="sxs-lookup"><span data-stu-id="73af3-144">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="73af3-145">键入 **Y** 继续，或键入 **N** 停止移动。</span><span class="sxs-lookup"><span data-stu-id="73af3-145">Type **Y** to continue, or **N** to stop the move.</span></span>

6.  <span data-ttu-id="73af3-146">查看 **Move-CsManagementServer** 命令生成的所有警告或错误，并解决它们。</span><span class="sxs-lookup"><span data-stu-id="73af3-146">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span>

7.  <span data-ttu-id="73af3-147">在 Lync Server 2013 服务器上，打开 "Lync Server 部署向导"。</span><span class="sxs-lookup"><span data-stu-id="73af3-147">On the Lync Server 2013 server, open the Lync Server Deployment Wizard.</span></span>

8.  <span data-ttu-id="73af3-148">在 "Lync Server 部署向导" 中，依次单击 " **安装或更新 Lync Server 系统**"、" **步骤2：设置" 或 "删除 Lync server 组件**"，单击 " **下一步**"，查看摘要，然后单击 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="73af3-148">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

9.  <span data-ttu-id="73af3-149">在 Lync Server 2010 服务器上，打开 "Lync Server 部署向导"。</span><span class="sxs-lookup"><span data-stu-id="73af3-149">On the Lync Server 2010 server, open the Lync Server Deployment Wizard.</span></span>

10. <span data-ttu-id="73af3-150">在 "Lync Server 部署向导" 中，依次单击 " **安装或更新 Lync Server 系统**"、" **步骤2：设置" 或 "删除 Lync server 组件**"，单击 " **下一步**"，查看摘要，然后单击 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="73af3-150">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

11. <span data-ttu-id="73af3-151">重新启动 Lync Server 2013 服务器。</span><span class="sxs-lookup"><span data-stu-id="73af3-151">Reboot the Lync Server 2013 server.</span></span> <span data-ttu-id="73af3-152">这是必需的，因为对 access 中央管理服务器数据库进行组成员资格更改。</span><span class="sxs-lookup"><span data-stu-id="73af3-152">This is required because of a group membership change to access Central Management Server database.</span></span>

12. <span data-ttu-id="73af3-153">若要确认具有新的中央管理存储的复制正在发生，请在 Lync Server 命令行管理程序中键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="73af3-153">To confirm that replication with the new Central Management store is occurring, in the Lync Server Management Shell, type:</span></span>
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="73af3-154">复制可能需要一段时间来更新当前所有副本。</span><span class="sxs-lookup"><span data-stu-id="73af3-154">The replication may take some time to update all current replicas.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a><span data-ttu-id="73af3-155">移动后删除 Lync Server 2010 中央管理存储文件</span><span class="sxs-lookup"><span data-stu-id="73af3-155">To remove Lync Server 2010 Central Management store files after a move</span></span>

1.  <span data-ttu-id="73af3-156">在 Lync Server 2010 服务器上：登录到安装了 Lync Server 命令行管理程序的计算机作为 **RTCUniversalServerAdmins** 组的成员。</span><span class="sxs-lookup"><span data-stu-id="73af3-156">On the Lync Server 2010 server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="73af3-157">您还必须具有 SQL Server 数据库管理员用户权限。</span><span class="sxs-lookup"><span data-stu-id="73af3-157">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="73af3-158">打开 Lync Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="73af3-158">Open Lync Server Management Shell</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="73af3-159">在复制完成和系统稳定之前，不要继续删除以前的数据库文件。</span><span class="sxs-lookup"><span data-stu-id="73af3-159">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="73af3-160">如果在完成复制之前删除了文件，则会中断复制过程，并使新移动的中央管理服务器处于未知状态。</span><span class="sxs-lookup"><span data-stu-id="73af3-160">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="73af3-161">可使用 cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> 确认复制状态。</span><span class="sxs-lookup"><span data-stu-id="73af3-161">Use the cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> to confirm the replication status.</span></span>

    
    </div>

3.  <span data-ttu-id="73af3-162">若要从 Lync Server 2010 中央管理服务器中删除中央管理存储数据库文件，请键入：</span><span class="sxs-lookup"><span data-stu-id="73af3-162">To remove the Central Management store database files from the Lync Server 2010 Central Management Server, type:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    <span data-ttu-id="73af3-163">例如：</span><span class="sxs-lookup"><span data-stu-id="73af3-163">For example:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    <span data-ttu-id="73af3-164">其中， \<FQDN of SQL Server\> 是企业版部署中的 Lync server 2010 后端服务器或 Standard edition 服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="73af3-164">Where the \<FQDN of SQL Server\> is either the Lync Server 2010 Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

