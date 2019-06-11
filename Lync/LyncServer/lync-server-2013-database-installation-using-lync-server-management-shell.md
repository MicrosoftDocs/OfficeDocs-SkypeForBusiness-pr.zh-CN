---
title: Lync Server 2013：使用 Lync Server 命令行管理程序安装数据库
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Database installation using Lync Server Management Shell
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398832(v=OCS.15)
ms:contentKeyID: 48185401
ms.date: 06/16/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fd9f07b979f89a28b6fa545f3a43009402f4ed1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a><span data-ttu-id="72b12-102">在 Lync Server 2013 中使用 Lync Server 命令行管理程序安装数据库</span><span class="sxs-lookup"><span data-stu-id="72b12-102">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72b12-103">_**主题上次修改时间:** 2016-06-16_</span><span class="sxs-lookup"><span data-stu-id="72b12-103">_**Topic Last Modified:** 2016-06-16_</span></span>

<span data-ttu-id="72b12-104">服务器管理员和 SQL Server 管理员之间的角色和职责的分离可能导致实现延迟。</span><span class="sxs-lookup"><span data-stu-id="72b12-104">Separation of roles and responsibilities between server administrators and SQL Server administrators can result in delays in implementation.</span></span> <span data-ttu-id="72b12-105">Lync Server 2013 使用基于角色的访问控制 (RBAC) 来缓解这些问题。</span><span class="sxs-lookup"><span data-stu-id="72b12-105">Lync Server 2013 uses role-based access control (RBAC) to mitigate these difficulties.</span></span> <span data-ttu-id="72b12-106">在某些情况下, SQL Server 管理员必须在基于 SQL Server 的服务器上管理在 RBAC 外的数据库安装。</span><span class="sxs-lookup"><span data-stu-id="72b12-106">In some instances, the SQL Server administrator must manage the installation of databases on the SQL Server-based server outside RBAC.</span></span> <span data-ttu-id="72b12-107">Lync Server 2013 命令行管理程序为 SQL Server 管理员提供了一种运行 Windows PowerShell cmdlet 的方法, 该 cmdlet 旨在使用正确的数据和日志文件配置数据库。</span><span class="sxs-lookup"><span data-stu-id="72b12-107">The Lync Server 2013 Management Shell provides a way for the SQL Server administrator to run Windows PowerShell cmdlets designed to configure the databases with the correct data and log files.</span></span> <span data-ttu-id="72b12-108">有关详细信息, 请参阅[Lync server 2013 中的 SQL Server 部署权限](lync-server-2013-deployment-permissions-for-sql-server.md)。</span><span class="sxs-lookup"><span data-stu-id="72b12-108">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="72b12-109">以下过程假定至少安装了 Lync Server 2013 OCSCore、SQL Server Native Client (sqlncli) Microsoft SQL server 2012 管理对象、安装了 Microsoft SQL Server 2012 和 Microsoft SQL Server 2012 ADOMD.NET 的 CLR 类型。</span><span class="sxs-lookup"><span data-stu-id="72b12-109">The following procedure assumes that at a minimum the Lync Server 2013 OCSCore.msi, SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012 Management Objects, CLR Types for Microsoft SQL Server 2012 and Microsoft SQL Server 2012 ADOMD.NET are installed.</span></span> <span data-ttu-id="72b12-110">OCSCore 位于 \Setup\AMD64\Setup 目录的安装媒体中。</span><span class="sxs-lookup"><span data-stu-id="72b12-110">The OCSCore.msi is located on the installation media in the \Setup\AMD64\Setup directory.</span></span> <span data-ttu-id="72b12-111">剩余的组件位于 \Setup\amd64. 中。</span><span class="sxs-lookup"><span data-stu-id="72b12-111">The remaining components are located in \Setup\amd64.</span></span> <span data-ttu-id="72b12-112">此外, 已成功完成 Lync Server 2013 的 Active Directory 准备。</span><span class="sxs-lookup"><span data-stu-id="72b12-112">Additionally, Active Directory preparation for Lync Server 2013 has been successfully completed.</span></span>



</div>

<span data-ttu-id="72b12-113">**Install-CsDatabase**是用于安装数据库的 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="72b12-113">**Install-CsDatabase** is the Windows PowerShell cmdlet you use to install the databases.</span></span> <span data-ttu-id="72b12-114">**CsDatabase** cmdlet 具有大量参数, 这里只讨论几个参数。</span><span class="sxs-lookup"><span data-stu-id="72b12-114">The **Install-CsDatabase** cmdlet has a large number of parameters, only a few of which are discussed here.</span></span> <span data-ttu-id="72b12-115">有关可能的参数的详细信息, 请参阅 Lync Server 2013 管理外壳文档。</span><span class="sxs-lookup"><span data-stu-id="72b12-115">For details about the possible parameters, see the Lync Server 2013 Management Shell documentation.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="72b12-116">若要避免性能和可能出现的超时问题, 请在引用基于 SQL Server 的服务器时始终使用完全限定的域名 (Fqdn)。</span><span class="sxs-lookup"><span data-stu-id="72b12-116">To avoid performance and possible time-out issues, always use fully qualified domain names (FQDNs) when referring to SQL Server-based servers.</span></span> <span data-ttu-id="72b12-117">避免使用仅限主机名的引用。</span><span class="sxs-lookup"><span data-stu-id="72b12-117">Avoid using host name-only references.</span></span> <span data-ttu-id="72b12-118">例如, 使用 sqlbe01.contoso.net, 但避免使用 SQLBE01。</span><span class="sxs-lookup"><span data-stu-id="72b12-118">For example, use sqlbe01.contoso.net, but avoid using SQLBE01.</span></span>



</div>

<span data-ttu-id="72b12-119">对于安装数据库, **CsDatabase**使用三种主要方法将数据库放在基于 SQL server 的预安装服务器上:</span><span class="sxs-lookup"><span data-stu-id="72b12-119">For installing databases, **Install-CsDatabase** uses three primary methods for placing the databases onto the prepared SQL Server-based server:</span></span>

  - <span data-ttu-id="72b12-120">运行**安装-CsDatabase**而不 DatabasePaths 或 UseDefaultSqlPath。</span><span class="sxs-lookup"><span data-stu-id="72b12-120">Run **Install-CsDatabase** without DatabasePaths or UseDefaultSqlPath.</span></span> <span data-ttu-id="72b12-121">该 cmdlet 使用内置算法确定日志和数据文件的最佳位置。</span><span class="sxs-lookup"><span data-stu-id="72b12-121">The cmdlet uses a built in algorithm to determine the best placement for the log and data files.</span></span> <span data-ttu-id="72b12-122">该算法仅适用于独立的 SQL Server 实现。</span><span class="sxs-lookup"><span data-stu-id="72b12-122">The algorithm only works for stand-alone SQL Server implementations.</span></span>

  - <span data-ttu-id="72b12-123">通过 DatabasePaths 参数运行**Install CsDatabase** 。</span><span class="sxs-lookup"><span data-stu-id="72b12-123">Run **Install-CsDatabase** with the DatabasePaths parameter.</span></span> <span data-ttu-id="72b12-124">如果定义了 DatabasePaths 参数, 则不会使用内置算法来优化日志和数据文件位置。</span><span class="sxs-lookup"><span data-stu-id="72b12-124">The built-in algorithm to optimize log and data file locations is not used if the DatabasePaths parameter is defined.</span></span> <span data-ttu-id="72b12-125">使用此参数可定义将在其中部署日志和数据文件的位置。</span><span class="sxs-lookup"><span data-stu-id="72b12-125">Using this parameter allows you to define the locations where log and data files will be deployed.</span></span>

  - <span data-ttu-id="72b12-126">CsDatabase 与 UseDefaultSqlPaths 一起运行**安装**。</span><span class="sxs-lookup"><span data-stu-id="72b12-126">Run **Install-CsDatabase** with UseDefaultSqlPaths.</span></span> <span data-ttu-id="72b12-127">此选项不使用内置算法来优化日志和数据文件位置。</span><span class="sxs-lookup"><span data-stu-id="72b12-127">This option does not use the built-in algorithm to optimize the log and data file locations.</span></span> <span data-ttu-id="72b12-128">根据 SQL Server 管理员设置的默认值来部署日志和数据文件。</span><span class="sxs-lookup"><span data-stu-id="72b12-128">Log and data file are deployed according to the defaults set by the SQL Server administrator.</span></span> <span data-ttu-id="72b12-129">通常, 这些路径用于自动管理 SQL Server 上的日志和数据文件的目的, 并且不与 Lync Server 2013 的设置相关联。</span><span class="sxs-lookup"><span data-stu-id="72b12-129">These paths are typically set for the purpose of automatic administration of log and data files on the SQL Server in advance, and are not associated with the setup of Lync Server 2013.</span></span>

  - <span data-ttu-id="72b12-130">DatabasePathMap 参数还可用于为每个数据库和其各自的日志文件显式指定一个位置。</span><span class="sxs-lookup"><span data-stu-id="72b12-130">The DatabasePathMap parameter can also be used to explicitly specify a location for each database and its respective log file.</span></span>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a><span data-ttu-id="72b12-131">使用 Windows PowerShell cmdlet 配置 SQL Server 中央管理存储</span><span class="sxs-lookup"><span data-stu-id="72b12-131">To use Windows PowerShell cmdlets to configure the SQL Server Central Management store</span></span>

1.  <span data-ttu-id="72b12-132">在任何计算机上, 用管理凭据登录, 以便在基于 SQL Server 的服务器上创建数据库。</span><span class="sxs-lookup"><span data-stu-id="72b12-132">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="72b12-133">有关详细信息, 请参阅[Lync server 2013 中的 SQL Server 部署权限](lync-server-2013-deployment-permissions-for-sql-server.md)。</span><span class="sxs-lookup"><span data-stu-id="72b12-133">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

2.  <span data-ttu-id="72b12-134">打开 Lync Server 2013 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="72b12-134">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="72b12-135">如果尚未调整 Windows PowerShell 的执行策略, 则必须调整策略以允许 Windows PowerShell 脚本运行。</span><span class="sxs-lookup"><span data-stu-id="72b12-135">If you have not adjusted the execution policy for Windows PowerShell, you must adjust the policy to allow Windows PowerShell scripts to run.</span></span> <span data-ttu-id="72b12-136">有关详细信息, 请参阅中的 "检查执行[http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093)策略"。</span><span class="sxs-lookup"><span data-stu-id="72b12-136">For details, see “Examining the Execution Policy” at [http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093).</span></span>

3.  <span data-ttu-id="72b12-137">使用**CsDatabase** Cmdlet 安装中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="72b12-137">Use the **Install-CsDatabase** cmdlet to install the Central Management store.</span></span>
    
       ```
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <fully qualified domain name of SQL Server> 
        -SqlInstanceName <named instance> -DatabasePaths <logfile path>,<database file path> 
        -Report <path to report file>
       ```
    
       ```
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn sqlbe.contoso.net -SqlInstanceName rtc -DatabasePaths "C:\CSDB-Logs","C:\CSDB-CMS" -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="72b12-138">Report 参数是可选的, 但如果要记录安装过程, 则该参数非常有用。</span><span class="sxs-lookup"><span data-stu-id="72b12-138">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

4.  <span data-ttu-id="72b12-139">**Install-CsDatabase-DatabasePaths**最多可以使用六条路径参数, 每个参数定义了在 SQL Server Data 和日志文件放置中定义的驱动器路径。</span><span class="sxs-lookup"><span data-stu-id="72b12-139">**Install-CsDatabase –DatabasePaths** can use up to six path parameters, each defining the paths for the drives as defined in SQL Server Data and Log File Placement.</span></span> <span data-ttu-id="72b12-140">按照 Lync Server 2013 中的数据库配置的逻辑规则, 驱动器将被解析为2、4或6的存储桶。</span><span class="sxs-lookup"><span data-stu-id="72b12-140">By the logical rules of the database configuration in Lync Server 2013, drives are parsed out into buckets of two, four, or six.</span></span> <span data-ttu-id="72b12-141">根据你的 SQL Server 配置和存储桶的数量, 你将提供两条路径、四条路径或六条路径。</span><span class="sxs-lookup"><span data-stu-id="72b12-141">Depending on your SQL Server configuration and the number of buckets, you will supply two paths, four paths, or six paths.</span></span>
    
    <span data-ttu-id="72b12-142">如果你有三个驱动器, 日志将获得优先级, 并且将在之后分发数据文件。</span><span class="sxs-lookup"><span data-stu-id="72b12-142">If you have three drives, the log gets priority and the data files are distributed after.</span></span> <span data-ttu-id="72b12-143">使用6个驱动器配置的基于 SQL Server 的服务器的示例:</span><span class="sxs-lookup"><span data-stu-id="72b12-143">An example for a SQL Server-based server configured with six drives:</span></span>
    
        Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"

5.  <span data-ttu-id="72b12-144">数据库安装完成后, 您可以关闭 Lync Server 2013 命令行管理程序, 或继续安装在拓扑生成器中定义的 Lync Server 2013 配置的数据库。</span><span class="sxs-lookup"><span data-stu-id="72b12-144">When the database installation completes, you can close Lync Server 2013 Management Shell or proceed to the installation of the Lync Server 2013 configured databases defined in Topology Builder.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a><span data-ttu-id="72b12-145">使用 Windows PowerShell cmdlet 配置 SQL Server 拓扑配置的数据库</span><span class="sxs-lookup"><span data-stu-id="72b12-145">To use Windows PowerShell cmdlets to configure the SQL Server topology configured databases</span></span>

1.  <span data-ttu-id="72b12-146">若要为 Lync Server 2013 安装拓扑生成器配置的数据库, Lync Server 2013 管理员必须发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="72b12-146">To install the Topology Builder configured databases for Lync Server 2013, the Lync Server 2013 administrator must publish the topology.</span></span> <span data-ttu-id="72b12-147">有关详细信息, 请参阅部署文档中[Lync Server 2013 中的 "发布拓扑](lync-server-2013-publish-the-topology.md)"。</span><span class="sxs-lookup"><span data-stu-id="72b12-147">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="72b12-148">在任何计算机上, 用管理凭据登录, 以便在基于 SQL Server 的服务器上创建数据库。</span><span class="sxs-lookup"><span data-stu-id="72b12-148">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="72b12-149">请参阅[Lync server 2013 中的 SQL Server 部署权限](lync-server-2013-deployment-permissions-for-sql-server.md)主题。</span><span class="sxs-lookup"><span data-stu-id="72b12-149">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="72b12-150">若要配置基于 SQL Server 的数据库, 请确保用于运行此处所述步骤的 SQL Server 管理员帐户也是运行 SQL Server 并拥有集中管理的服务器上的 sysadmin 组 (等同) 成员服务器角色。</span><span class="sxs-lookup"><span data-stu-id="72b12-150">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="72b12-151">对于需要 SQL Server 数据库安装或配置的任何其他 Lync Server 2013 池, 这一点尤其重要。</span><span class="sxs-lookup"><span data-stu-id="72b12-151">This is especially important to check for any additional Lync Server 2013 pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="72b12-152">例如, 如果你要部署第二个池 (pool02), 但中央管理服务器角色由 pool01 拥有。</span><span class="sxs-lookup"><span data-stu-id="72b12-152">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="72b12-153">SQL Server sysadmin 组 (或同等身份) 必须具有对基于 SQL Server 的数据库的权限。</span><span class="sxs-lookup"><span data-stu-id="72b12-153">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="72b12-154">打开 Lync Server 2013 命令行管理程序 (如果它尚未打开)。</span><span class="sxs-lookup"><span data-stu-id="72b12-154">Open Lync Server 2013 Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="72b12-155">使用**CsDatabase** Cmdlet 安装拓扑生成器配置的数据库。</span><span class="sxs-lookup"><span data-stu-id="72b12-155">Use the **Install-CsDatabase** cmdlet to install the Topology Builder configured databases.</span></span>
    
       ```
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <fully qualified domain name of SQL Server> 
         -DatabasePaths <logfile path>,<database file path> -Report <path to report file>
       ```
    
       ```
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe.contoso.net 
        -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="72b12-156">Report 参数是可选的, 但如果要记录安装过程, 则该参数非常有用。</span><span class="sxs-lookup"><span data-stu-id="72b12-156">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

5.  <span data-ttu-id="72b12-157">数据库安装完成后, 关闭 Lync Server 2013 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="72b12-157">When the database installation completes, close Lync Server 2013 Management Shell.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a><span data-ttu-id="72b12-158">使用 Windows PowerShell cmdlet 使用 DatabasePathMap 参数配置 SQL Server 拓扑</span><span class="sxs-lookup"><span data-stu-id="72b12-158">To use Windows PowerShell cmdlets to configure the SQL Server topology using the DatabasePathMap parameter</span></span>

1.  <span data-ttu-id="72b12-159">若要为 Lync Server 2013 安装数据库, Lync Server 管理员必须创建路径并根据预定义的一组规则部署数据库文件和日志文件。</span><span class="sxs-lookup"><span data-stu-id="72b12-159">To install databases for Lync Server 2013, the Lync Server administrator must create the paths and deploy the databases files and log files according to a predefined set of rules.</span></span>

2.  <span data-ttu-id="72b12-160">在任何计算机上, 用管理凭据登录, 以便在基于 SQL Server 的服务器上创建数据库。</span><span class="sxs-lookup"><span data-stu-id="72b12-160">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="72b12-161">请参阅[Lync server 2013 中的 SQL Server 部署权限](lync-server-2013-deployment-permissions-for-sql-server.md)主题。</span><span class="sxs-lookup"><span data-stu-id="72b12-161">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="72b12-162">若要配置基于 SQL Server 的数据库, 请确保用于运行此处所述步骤的 SQL Server 管理员帐户也是运行 SQL Server 并拥有集中管理的服务器上的 sysadmin 组 (等同) 成员服务器角色。</span><span class="sxs-lookup"><span data-stu-id="72b12-162">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="72b12-163">这对于检查是否有需要 SQL Server 数据库安装或配置的任何其他 Lync 服务器池尤其重要。</span><span class="sxs-lookup"><span data-stu-id="72b12-163">This is especially important to check for any additional Lync Server pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="72b12-164">例如, 如果你要部署第二个池 (pool02), 但中央管理服务器角色由 pool01 拥有。</span><span class="sxs-lookup"><span data-stu-id="72b12-164">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="72b12-165">SQL Server sysadmin 组 (或同等身份) 必须具有对基于 SQL Server 的数据库的权限。</span><span class="sxs-lookup"><span data-stu-id="72b12-165">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="72b12-166">打开 Lync Server 命令行管理程序 (如果尚未打开)。</span><span class="sxs-lookup"><span data-stu-id="72b12-166">Open Lync Server Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="72b12-167">将**CsDatabase** Cmdlet 与 DatabasePathMap 参数和 PowerShell 哈希表配合使用, 以安装拓扑生成器配置的数据库。</span><span class="sxs-lookup"><span data-stu-id="72b12-167">Use the **Install-CsDatabase** cmdlet with the DatabasePathMap parameter and a PowerShell hash table to install the Topology Builder configured databases.</span></span>

5.  <span data-ttu-id="72b12-168">在示例代码中, 可以使用– DatabasePathMap 参数和定义的哈希表以粒度方式确定为数据库定义的路径 (示例对所有数据库 (.mdf) 文件使用 "C:\\CSData", 而 "c:\\ "CSLogFiles "的所有日志 (.ldf) 文件。</span><span class="sxs-lookup"><span data-stu-id="72b12-168">In the example code, the paths defined for the databases can be determined in a granular manner by using the –DatabasePathMap parameter and a defined hash table as follows (the example uses “C:\\CSData” for all database (.mdf) files, and “C:\\CSLogFiles” for all log (.ldf) files.</span></span> <span data-ttu-id="72b12-169">将按安装所需创建文件夹-CsDatabase):</span><span class="sxs-lookup"><span data-stu-id="72b12-169">Folder will be created as needed by Install-CsDatabase):</span></span>
    
        $pathmap = @{
        "BackendStore:BlobStore:DbPath"="C:\CsData";"BackendStore:BlobStore:LogPath"="C:\CsLogFiles"
        "BackendStore:RtcSharedDatabase:DbPath"="C:\CsData";"BackendStore:RtcSharedDatabase:LogPath"="C:\CsLogFiles"
        "ABSStore:AbsDatabase:DbPath"="C:\CsData";"ABSStore:AbsDatabase:LogPath"="C:\CsLogFiles"
        "ApplicationStore:RgsConfigDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsConfigDatabase:LogPath"="C:\CsLogFiles"
        "ApplicationStore:RgsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsDynDatabase:LogPath"="C:\CsLogFiles"
        "ApplicationStore:CpsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:CpsDynDatabase:LogPath"="C:\CsLogFiles"
        "ArchivingStore:ArchivingDatabase:DbPath"="C:\CsData";"ArchivingStore:ArchivingDatabase:LogPath"="C:\CsLogFiles"
        "MonitoringStore:MonitoringDatabase:DbPath"="C:\CsData";"MonitoringStore:MonitoringDatabase:LogPath"="C:\CsLogFiles"
        "MonitoringStore:QoEMetricsDatabase:DbPath"="C:\CsData";"MonitoringStore:QoEMetricsDatabase:LogPath"="C:\CsLogFiles"
        }
        Install-CsDatabase -ConfigureDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap

6.  <span data-ttu-id="72b12-170">由于数据库和日志文件在目标数据库服务器上的位置显式命名, 因此你可以为每个服务类型的实际数据库和日志位置定义特定位置。</span><span class="sxs-lookup"><span data-stu-id="72b12-170">Because the database and log files are explicitly named with their location on the destination database server, you can define specific locations for each service type’s actual database and log location.</span></span> <span data-ttu-id="72b12-171">下面的示例将每个特定服务类型的数据库放在单独的磁盘上, 并将关联的日志文件放在另一个磁盘上。</span><span class="sxs-lookup"><span data-stu-id="72b12-171">The following example puts databases for each specific service type on separate disks, and associated log files on another.</span></span> <span data-ttu-id="72b12-172">例如：</span><span class="sxs-lookup"><span data-stu-id="72b12-172">For example:</span></span>
    
      - <span data-ttu-id="72b12-173">所有 RTC 数据库到 "D:\\RTCDatabase"</span><span class="sxs-lookup"><span data-stu-id="72b12-173">All RTC databases to “D:\\RTCDatabase”</span></span>
    
      - <span data-ttu-id="72b12-174">所有 RTC 日志文件到 "E:\\RTCLogs"</span><span class="sxs-lookup"><span data-stu-id="72b12-174">All RTC log files to “E:\\RTCLogs”</span></span>
    
      - <span data-ttu-id="72b12-175">所有应用商店数据库到 "F:\\CPSDatabases"</span><span class="sxs-lookup"><span data-stu-id="72b12-175">All application store databases to “F:\\CPSDatabases”</span></span>
    
      - <span data-ttu-id="72b12-176">所有应用商店日志到 "G:\\CPSLogs"</span><span class="sxs-lookup"><span data-stu-id="72b12-176">All application store logs to “G:\\CPSLogs”</span></span>
    
      - <span data-ttu-id="72b12-177">所有响应组存储数据库到 "H:\\RGSDatabases"</span><span class="sxs-lookup"><span data-stu-id="72b12-177">All response group store databases to “H:\\RGSDatabases”</span></span>
    
      - <span data-ttu-id="72b12-178">所有响应组存储日志到 "I:\\RGSLogs"</span><span class="sxs-lookup"><span data-stu-id="72b12-178">All response group store logs to “I:\\RGSLogs”</span></span>
    
      - <span data-ttu-id="72b12-179">所有通讯簿将数据库存储到 "J\\: ABSDatabases"</span><span class="sxs-lookup"><span data-stu-id="72b12-179">All address book store databases to “J:\\ABSDatabases”</span></span>
    
      - <span data-ttu-id="72b12-180">"所有通讯簿" 将日志文件存储到\\"K: ABSLogs"</span><span class="sxs-lookup"><span data-stu-id="72b12-180">All address book store log files to “K:\\ABSLogs”</span></span>
    
      - <span data-ttu-id="72b12-181">所有存档将数据库存储到 "L\\: ArchivingDatabases"</span><span class="sxs-lookup"><span data-stu-id="72b12-181">All archiving store databases to “L:\\ArchivingDatabases”</span></span>
    
      - <span data-ttu-id="72b12-182">所有存档存储日志到 "M:\\ArchivingLogs"</span><span class="sxs-lookup"><span data-stu-id="72b12-182">All archiving store logs to “M:\\ArchivingLogs”</span></span>
    
      - <span data-ttu-id="72b12-183">所有监视存储数据库到 "N:\\MonitoringDatabases"</span><span class="sxs-lookup"><span data-stu-id="72b12-183">All monitoring store databases to “N:\\MonitoringDatabases”</span></span>
    
      - <span data-ttu-id="72b12-184">所有监视应用商店日志文件均为 "\\O: MonitoringLogfiles"</span><span class="sxs-lookup"><span data-stu-id="72b12-184">All monitoring store log files to “O:\\MonitoringLogfiles”</span></span>
    
    <!-- end list -->
    
    ``` 
    
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="D:\RTCDatabase";"BackendStore:BlobStore:LogPath"="E:\RTCLogs"
    "BackendStore:RtcSharedDatabase:DbPath"="D:\RTCDatabase";"BackendStore:RtcSharedDatabase:LogPath"="E:\RTCLogs"
    "ABSStore:AbsDatabase:DbPath"="J:\ABSDatabases";"ABSStore:AbsDatabase:LogPath"="K:\ABSLogs"
    "ApplicationStore:RgsConfigDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsConfigDatabase:LogPath"="G:\CPSLogs"
    "ApplicationStore:RgsDynDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsDynDatabase:LogPath"="I:\RGSLogs"
    "ApplicationStore:CpsDynDatabase:DbPath"="F:\CPSDatabases";"ApplicationStore:CpsDynDatabase:LogPath"="G:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="M:\ArchivingLogs";"ArchivingStore:ArchivingDatabase:LogPath"="N:\MonitoringDatabases"
    "MonitoringStore:MonitoringDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:MonitoringDatabase:LogPath"="O:\MonitoringLogfiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:QoEMetricsDatabase:LogPath"="O:\MonitoringLogfiles"
    }
    
    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
    
    <span data-ttu-id="72b12-185">使用-DatabasePathMap 参数, 你可以定义任何逻辑驱动器号映射组合, 为你的 SQL Server 性能和放置要求提供最佳解决方案。</span><span class="sxs-lookup"><span data-stu-id="72b12-185">Using the –DatabasePathMap parameter, you can define any logical drive letter mapping combination that provides the best solution for your SQL Server performance and placement requirements.</span></span>

<span data-ttu-id="72b12-186">如果你使用**DatabasePathMap**方法配置数据库数据文件和日志文件, 你将需要在使用拓扑生成器时对你的正常过程稍作更改。</span><span class="sxs-lookup"><span data-stu-id="72b12-186">If you configure your database data files and log files by using the **DatabasePathMap** method, you will need to make a slight change to your normal process when using Topology Builder.</span></span> <span data-ttu-id="72b12-187">通常, 你将定义拓扑选项, 发布拓扑, 并选择部署数据库选择。</span><span class="sxs-lookup"><span data-stu-id="72b12-187">Typically, you would define your topology choices, publish the topology, and choose to deploy the database selections.</span></span>

<span data-ttu-id="72b12-188">如果您使用过**DatabasePathMap** , 则您已经完成了拓扑生成器过程的第三部分。</span><span class="sxs-lookup"><span data-stu-id="72b12-188">If you have used **DatabasePathMap** you have already accomplished the third part of the Topology Builder process.</span></span> <span data-ttu-id="72b12-189">如果在运行拓扑生成器之前拥有完全配置的数据库服务器, 您仍可以定义所有服务器角色和选项, 但取消选择用于创建数据库的选项。</span><span class="sxs-lookup"><span data-stu-id="72b12-189">In the case of having a completely configured database server in advance of running Topology Builder, you would still define all of your server roles and options, but deselect the option to create the databases.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

