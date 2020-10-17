---
title: Lync Server 2013：使用 Lync Server 命令行管理程序进行数据库安装
description: Lync Server 2013：使用 Lync Server 命令行管理程序进行数据库安装。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database installation using Lync Server Management Shell
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398832(v=OCS.15)
ms:contentKeyID: 48185401
ms.date: 06/16/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d572984c94d280723b12c5343a92ddfaa12d4f0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558178"
---
# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a><span data-ttu-id="58b8f-103">在 Lync Server 2013 中使用 Lync Server 命令行管理程序进行数据库安装</span><span class="sxs-lookup"><span data-stu-id="58b8f-103">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58b8f-104">_**上次修改的主题：** 2016-06-16_</span><span class="sxs-lookup"><span data-stu-id="58b8f-104">_**Topic Last Modified:** 2016-06-16_</span></span>

<span data-ttu-id="58b8f-105">服务器管理员和 SQL Server 管理员之间角色和职责的分离可能会导致实现中出现延迟。</span><span class="sxs-lookup"><span data-stu-id="58b8f-105">Separation of roles and responsibilities between server administrators and SQL Server administrators can result in delays in implementation.</span></span> <span data-ttu-id="58b8f-106">Lync Server 2013 使用基于角色的访问控制 (RBAC) 来缓解这些问题。</span><span class="sxs-lookup"><span data-stu-id="58b8f-106">Lync Server 2013 uses role-based access control (RBAC) to mitigate these difficulties.</span></span> <span data-ttu-id="58b8f-107">在某些实例中，SQL Server 管理员必须管理在 RBAC 之外基于 SQL Server 的服务器上安装数据库。</span><span class="sxs-lookup"><span data-stu-id="58b8f-107">In some instances, the SQL Server administrator must manage the installation of databases on the SQL Server-based server outside RBAC.</span></span> <span data-ttu-id="58b8f-108">Lync Server 2013 命令行管理程序为 SQL Server 管理员提供了一种运行 Windows PowerShell cmdlet 的方法，这些 cmdlet 旨在使用正确的数据和日志文件配置数据库。</span><span class="sxs-lookup"><span data-stu-id="58b8f-108">The Lync Server 2013 Management Shell provides a way for the SQL Server administrator to run Windows PowerShell cmdlets designed to configure the databases with the correct data and log files.</span></span> <span data-ttu-id="58b8f-109">有关详细信息，请参阅 [Lync server 2013 中的 SQL Server 部署权限](lync-server-2013-deployment-permissions-for-sql-server.md)。</span><span class="sxs-lookup"><span data-stu-id="58b8f-109">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="58b8f-110">以下过程假定至少已安装了 Lync Server 2013 OCSCore.msi、SQL Server Native Client ( # A1) Microsoft SQL server 2012 管理对象、Microsoft SQL Server 2012 和 Microsoft SQL Server 2012 ADOMD.NET 的 CLR 类型。</span><span class="sxs-lookup"><span data-stu-id="58b8f-110">The following procedure assumes that at a minimum the Lync Server 2013 OCSCore.msi, SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012 Management Objects, CLR Types for Microsoft SQL Server 2012 and Microsoft SQL Server 2012 ADOMD.NET are installed.</span></span> <span data-ttu-id="58b8f-111">OCSCore.msi 位于安装介质的 \Setup\AMD64\Setup 目录中。</span><span class="sxs-lookup"><span data-stu-id="58b8f-111">The OCSCore.msi is located on the installation media in the \Setup\AMD64\Setup directory.</span></span> <span data-ttu-id="58b8f-112">其余的组件位于 \Setup\amd64. 中。</span><span class="sxs-lookup"><span data-stu-id="58b8f-112">The remaining components are located in \Setup\amd64.</span></span> <span data-ttu-id="58b8f-113">此外，已成功完成 Lync Server 2013 的 Active Directory 准备工作。</span><span class="sxs-lookup"><span data-stu-id="58b8f-113">Additionally, Active Directory preparation for Lync Server 2013 has been successfully completed.</span></span>



</div>

<span data-ttu-id="58b8f-114">**Install-CsDatabase** 是用于安装数据库的 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="58b8f-114">**Install-CsDatabase** is the Windows PowerShell cmdlet you use to install the databases.</span></span> <span data-ttu-id="58b8f-115">**Install-CsDatabase** cmdlet 有大量参数，此处只讨论其中的一部分。</span><span class="sxs-lookup"><span data-stu-id="58b8f-115">The **Install-CsDatabase** cmdlet has a large number of parameters, only a few of which are discussed here.</span></span> <span data-ttu-id="58b8f-116">有关可能的参数的详细信息，请参阅 Lync Server 2013 命令行管理程序文档。</span><span class="sxs-lookup"><span data-stu-id="58b8f-116">For details about the possible parameters, see the Lync Server 2013 Management Shell documentation.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="58b8f-117">为避免性能问题和可能出现的超时问题，引用基于 SQL Server 的服务器时请始终使用完全限定域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="58b8f-117">To avoid performance and possible time-out issues, always use fully qualified domain names (FQDNs) when referring to SQL Server-based servers.</span></span> <span data-ttu-id="58b8f-118">避免只引用主机名。</span><span class="sxs-lookup"><span data-stu-id="58b8f-118">Avoid using host name-only references.</span></span> <span data-ttu-id="58b8f-119">例如，使用 sqlbe01.contoso.net，但避免使用 SQLBE01。</span><span class="sxs-lookup"><span data-stu-id="58b8f-119">For example, use sqlbe01.contoso.net, but avoid using SQLBE01.</span></span>



</div>

<span data-ttu-id="58b8f-120">对于安装数据库， **CsDatabase** 使用三种主要方法将数据库放在已准备好的基于 SQL server 的服务器上：</span><span class="sxs-lookup"><span data-stu-id="58b8f-120">For installing databases, **Install-CsDatabase** uses three primary methods for placing the databases onto the prepared SQL Server-based server:</span></span>

  - <span data-ttu-id="58b8f-121">运行不带 DatabasePaths 或 UseDefaultSqlPath 的 **Install-CsDatabase**。</span><span class="sxs-lookup"><span data-stu-id="58b8f-121">Run **Install-CsDatabase** without DatabasePaths or UseDefaultSqlPath.</span></span> <span data-ttu-id="58b8f-122">该 cmdlet 使用内置算法确定日志和数据文件的最佳放置方法。</span><span class="sxs-lookup"><span data-stu-id="58b8f-122">The cmdlet uses a built in algorithm to determine the best placement for the log and data files.</span></span> <span data-ttu-id="58b8f-123">该算法仅适用于独立的 SQL Server 实现。</span><span class="sxs-lookup"><span data-stu-id="58b8f-123">The algorithm only works for stand-alone SQL Server implementations.</span></span>

  - <span data-ttu-id="58b8f-124">运行带有 DatabasePaths 参数的 **Install-CsDatabase**。</span><span class="sxs-lookup"><span data-stu-id="58b8f-124">Run **Install-CsDatabase** with the DatabasePaths parameter.</span></span> <span data-ttu-id="58b8f-125">如果定义了 DatabasePaths 参数，则不使用优化日志和数据文件位置的内置算法。</span><span class="sxs-lookup"><span data-stu-id="58b8f-125">The built-in algorithm to optimize log and data file locations is not used if the DatabasePaths parameter is defined.</span></span> <span data-ttu-id="58b8f-126">您可以使用该参数来定义要部署日志和数据文件的位置。</span><span class="sxs-lookup"><span data-stu-id="58b8f-126">Using this parameter allows you to define the locations where log and data files will be deployed.</span></span>

  - <span data-ttu-id="58b8f-127">运行带有 UseDefaultSqlPaths 的 **Install-CsDatabase**。</span><span class="sxs-lookup"><span data-stu-id="58b8f-127">Run **Install-CsDatabase** with UseDefaultSqlPaths.</span></span> <span data-ttu-id="58b8f-128">该选项不使用内置算法来优化日志和数据文件的位置。</span><span class="sxs-lookup"><span data-stu-id="58b8f-128">This option does not use the built-in algorithm to optimize the log and data file locations.</span></span> <span data-ttu-id="58b8f-129">日志和数据文件是根据 SQL Server 管理员设置的默认值来部署的。</span><span class="sxs-lookup"><span data-stu-id="58b8f-129">Log and data file are deployed according to the defaults set by the SQL Server administrator.</span></span> <span data-ttu-id="58b8f-130">通常设置这些路径，以便提前管理 SQL Server 上的日志和数据文件，并不与 Lync Server 2013 的安装程序相关联。</span><span class="sxs-lookup"><span data-stu-id="58b8f-130">These paths are typically set for the purpose of automatic administration of log and data files on the SQL Server in advance, and are not associated with the setup of Lync Server 2013.</span></span>

  - <span data-ttu-id="58b8f-131">DatabasePathMap 参数还可用于为每个数据库和其各自的日志文件显式指定一个位置。</span><span class="sxs-lookup"><span data-stu-id="58b8f-131">The DatabasePathMap parameter can also be used to explicitly specify a location for each database and its respective log file.</span></span>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a><span data-ttu-id="58b8f-132">使用 Windows PowerShell cmdlet 配置 SQL Server 中央管理存储</span><span class="sxs-lookup"><span data-stu-id="58b8f-132">To use Windows PowerShell cmdlets to configure the SQL Server Central Management store</span></span>

1.  <span data-ttu-id="58b8f-133">在任意计算机上，使用管理凭据进行登录，以便在基于 SQL Server 的服务器上创建数据库。</span><span class="sxs-lookup"><span data-stu-id="58b8f-133">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="58b8f-134">有关详细信息，请参阅 [Lync server 2013 中的 SQL Server 部署权限](lync-server-2013-deployment-permissions-for-sql-server.md)。</span><span class="sxs-lookup"><span data-stu-id="58b8f-134">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

2.  <span data-ttu-id="58b8f-135">打开 Lync Server 2013 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="58b8f-135">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="58b8f-136">如果尚未调整 Windows PowerShell 的执行策略，则必须调整策略以允许运行 Windows PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="58b8f-136">If you have not adjusted the execution policy for Windows PowerShell, you must adjust the policy to allow Windows PowerShell scripts to run.</span></span> <span data-ttu-id="58b8f-137">有关详细信息，请参阅中的 "检查执行策略" [https://go.microsoft.com/fwlink/p/?linkId=203093](https://go.microsoft.com/fwlink/p/?linkid=203093) 。</span><span class="sxs-lookup"><span data-stu-id="58b8f-137">For details, see “Examining the Execution Policy” at [https://go.microsoft.com/fwlink/p/?linkId=203093](https://go.microsoft.com/fwlink/p/?linkid=203093).</span></span>

3.  <span data-ttu-id="58b8f-138">使用 **CsDatabase** cmdlet 可以安装中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="58b8f-138">Use the **Install-CsDatabase** cmdlet to install the Central Management store.</span></span>
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <fully qualified domain name of SQL Server> 
        -SqlInstanceName <named instance> -DatabasePaths <logfile path>,<database file path> 
        -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn sqlbe.contoso.net -SqlInstanceName rtc -DatabasePaths "C:\CSDB-Logs","C:\CSDB-CMS" -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="58b8f-139">Report 参数是可选的，但是在记录安装过程时很有用。</span><span class="sxs-lookup"><span data-stu-id="58b8f-139">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

4.  <span data-ttu-id="58b8f-140">**CsDatabase – DatabasePaths** 最长可使用六条路径参数，每个参数定义了在 SQL Server 数据和日志文件放置中定义的驱动器的路径。</span><span class="sxs-lookup"><span data-stu-id="58b8f-140">**Install-CsDatabase –DatabasePaths** can use up to six path parameters, each defining the paths for the drives as defined in SQL Server Data and Log File Placement.</span></span> <span data-ttu-id="58b8f-141">按照 Lync Server 2013 中的数据库配置的逻辑规则，将驱动器解析为2、4或6的存储桶。</span><span class="sxs-lookup"><span data-stu-id="58b8f-141">By the logical rules of the database configuration in Lync Server 2013, drives are parsed out into buckets of two, four, or six.</span></span> <span data-ttu-id="58b8f-142">根据您的 SQL Server 配置和存储桶的数量，您将提供两条路径、四条路径或六条路径。</span><span class="sxs-lookup"><span data-stu-id="58b8f-142">Depending on your SQL Server configuration and the number of buckets, you will supply two paths, four paths, or six paths.</span></span>
    
    <span data-ttu-id="58b8f-143">如果您有三个驱动器，则将优先分发日志文件，然后再分发数据文件。</span><span class="sxs-lookup"><span data-stu-id="58b8f-143">If you have three drives, the log gets priority and the data files are distributed after.</span></span> <span data-ttu-id="58b8f-144">配置了六个驱动器的基于 SQL Server 的服务器的示例：</span><span class="sxs-lookup"><span data-stu-id="58b8f-144">An example for a SQL Server-based server configured with six drives:</span></span>
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  <span data-ttu-id="58b8f-145">在数据库安装完成后，您可以关闭 Lync Server 2013 命令行管理程序，或继续安装在拓扑生成器中定义的 Lync Server 2013 配置的数据库。</span><span class="sxs-lookup"><span data-stu-id="58b8f-145">When the database installation completes, you can close Lync Server 2013 Management Shell or proceed to the installation of the Lync Server 2013 configured databases defined in Topology Builder.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a><span data-ttu-id="58b8f-146">使用 Windows PowerShell cmdlet 对配置有 SQL Server 拓扑的数据库进行配置</span><span class="sxs-lookup"><span data-stu-id="58b8f-146">To use Windows PowerShell cmdlets to configure the SQL Server topology configured databases</span></span>

1.  <span data-ttu-id="58b8f-147">若要为 Lync Server 2013 安装拓扑生成器配置的数据库，Lync Server 2013 管理员必须发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="58b8f-147">To install the Topology Builder configured databases for Lync Server 2013, the Lync Server 2013 administrator must publish the topology.</span></span> <span data-ttu-id="58b8f-148">有关详细信息，请参阅部署文档中的在 [Lync Server 2013 中发布拓扑](lync-server-2013-publish-the-topology.md) 。</span><span class="sxs-lookup"><span data-stu-id="58b8f-148">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="58b8f-149">在任意计算机上，使用管理凭据进行登录，以便在基于 SQL Server 的服务器上创建数据库。</span><span class="sxs-lookup"><span data-stu-id="58b8f-149">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="58b8f-150">请参阅 [Lync server 2013 中的 SQL Server 部署权限](lync-server-2013-deployment-permissions-for-sql-server.md)主题。</span><span class="sxs-lookup"><span data-stu-id="58b8f-150">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="58b8f-151">若要能够配置基于 SQL Server 的数据库，请确保用于运行此处所述步骤的 SQL Server 管理员帐户也是运行 SQL Server 的服务器上的 sysadmin 组 (或等效) 并拥有中央管理服务器角色。</span><span class="sxs-lookup"><span data-stu-id="58b8f-151">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="58b8f-152">这对于检查是否有需要 SQL Server 数据库安装或配置的任何其他 Lync Server 2013 池尤为重要。</span><span class="sxs-lookup"><span data-stu-id="58b8f-152">This is especially important to check for any additional Lync Server 2013 pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="58b8f-153">例如，如果您正在部署第二个池 (pool02) 但中央管理服务器角色由 pool01 保留。</span><span class="sxs-lookup"><span data-stu-id="58b8f-153">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="58b8f-154">SQL Server sysadmin 组 (或等效) 必须具有对基于 SQL Server 的数据库的权限。</span><span class="sxs-lookup"><span data-stu-id="58b8f-154">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="58b8f-155">打开 Lync Server 2013 命令行管理程序（如果尚未打开）。</span><span class="sxs-lookup"><span data-stu-id="58b8f-155">Open Lync Server 2013 Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="58b8f-156">使用 **CsDatabase** cmdlet 可以安装拓扑生成器配置的数据库。</span><span class="sxs-lookup"><span data-stu-id="58b8f-156">Use the **Install-CsDatabase** cmdlet to install the Topology Builder configured databases.</span></span>
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <fully qualified domain name of SQL Server> 
         -DatabasePaths <logfile path>,<database file path> -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe.contoso.net 
        -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="58b8f-157">Report 参数是可选的，但是在记录安装过程时很有用。</span><span class="sxs-lookup"><span data-stu-id="58b8f-157">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

5.  <span data-ttu-id="58b8f-158">数据库安装完成后，关闭 Lync Server 2013 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="58b8f-158">When the database installation completes, close Lync Server 2013 Management Shell.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a><span data-ttu-id="58b8f-159">使用 Windows PowerShell cmdlet 使用 DatabasePathMap 参数配置 SQL Server 拓扑</span><span class="sxs-lookup"><span data-stu-id="58b8f-159">To use Windows PowerShell cmdlets to configure the SQL Server topology using the DatabasePathMap parameter</span></span>

1.  <span data-ttu-id="58b8f-160">若要为 Lync Server 2013 安装数据库，Lync Server 管理员必须根据一组预定义的规则创建路径并部署数据库文件和日志文件。</span><span class="sxs-lookup"><span data-stu-id="58b8f-160">To install databases for Lync Server 2013, the Lync Server administrator must create the paths and deploy the databases files and log files according to a predefined set of rules.</span></span>

2.  <span data-ttu-id="58b8f-161">在任意计算机上，使用管理凭据进行登录，以便在基于 SQL Server 的服务器上创建数据库。</span><span class="sxs-lookup"><span data-stu-id="58b8f-161">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="58b8f-162">请参阅 [Lync server 2013 中的 SQL Server 部署权限](lync-server-2013-deployment-permissions-for-sql-server.md)主题。</span><span class="sxs-lookup"><span data-stu-id="58b8f-162">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="58b8f-163">若要能够配置基于 SQL Server 的数据库，请确保用于运行此处所述步骤的 SQL Server 管理员帐户也是运行 SQL Server 的服务器上的 sysadmin 组 (或等效) 并拥有中央管理服务器角色。</span><span class="sxs-lookup"><span data-stu-id="58b8f-163">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="58b8f-164">这对于检查是否有需要 SQL Server 数据库安装或配置的任何其他 Lync Server 池尤为重要。</span><span class="sxs-lookup"><span data-stu-id="58b8f-164">This is especially important to check for any additional Lync Server pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="58b8f-165">例如，如果您正在部署第二个池 (pool02) 但中央管理服务器角色由 pool01 保留。</span><span class="sxs-lookup"><span data-stu-id="58b8f-165">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="58b8f-166">SQL Server sysadmin 组 (或等效) 必须具有对基于 SQL Server 的数据库的权限。</span><span class="sxs-lookup"><span data-stu-id="58b8f-166">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="58b8f-167">打开 Lync Server 命令行管理程序（如果尚未打开）。</span><span class="sxs-lookup"><span data-stu-id="58b8f-167">Open Lync Server Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="58b8f-168">将 **CsDatabase** Cmdlet 与 DatabasePathMap 参数和 PowerShell 哈希表结合使用，以安装拓扑生成器配置的数据库。</span><span class="sxs-lookup"><span data-stu-id="58b8f-168">Use the **Install-CsDatabase** cmdlet with the DatabasePathMap parameter and a PowerShell hash table to install the Topology Builder configured databases.</span></span>

5.  <span data-ttu-id="58b8f-169">在示例代码中，可以使用– DatabasePathMap 参数和定义的哈希表以精细的方式确定为数据库定义的路径，如下所示 (该示例将 "C： \\ CSData" 用于所有数据库 ( .mdf) 文件，将 "c： \\ CSLogFiles" 用于所有日志 ( .ldf) 文件。</span><span class="sxs-lookup"><span data-stu-id="58b8f-169">In the example code, the paths defined for the databases can be determined in a granular manner by using the –DatabasePathMap parameter and a defined hash table as follows (the example uses “C:\\CSData” for all database (.mdf) files, and “C:\\CSLogFiles” for all log (.ldf) files.</span></span> <span data-ttu-id="58b8f-170">将根据需要通过安装-CsDatabase) 来创建文件夹：</span><span class="sxs-lookup"><span data-stu-id="58b8f-170">Folder will be created as needed by Install-CsDatabase):</span></span>
    ```powershell
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
    ```
6.  <span data-ttu-id="58b8f-171">由于数据库和日志文件是使用其在目标数据库服务器上的位置显式命名的，因此您可以为每个服务类型的实际数据库和日志位置定义特定位置。</span><span class="sxs-lookup"><span data-stu-id="58b8f-171">Because the database and log files are explicitly named with their location on the destination database server, you can define specific locations for each service type’s actual database and log location.</span></span> <span data-ttu-id="58b8f-172">下面的示例将每个特定服务类型的数据库放在不同的磁盘上，并将相关联的日志文件放在另一个上。</span><span class="sxs-lookup"><span data-stu-id="58b8f-172">The following example puts databases for each specific service type on separate disks, and associated log files on another.</span></span> <span data-ttu-id="58b8f-173">例如：</span><span class="sxs-lookup"><span data-stu-id="58b8f-173">For example:</span></span>
    
      - <span data-ttu-id="58b8f-174">将所有 RTC 数据库重设为 "D： \\ RTCDatabase"</span><span class="sxs-lookup"><span data-stu-id="58b8f-174">All RTC databases to “D:\\RTCDatabase”</span></span>
    
      - <span data-ttu-id="58b8f-175">所有 RTC 日志文件到 "E： \\ RTCLogs"</span><span class="sxs-lookup"><span data-stu-id="58b8f-175">All RTC log files to “E:\\RTCLogs”</span></span>
    
      - <span data-ttu-id="58b8f-176">所有应用程序存储数据库到 "F： \\ CPSDatabases"</span><span class="sxs-lookup"><span data-stu-id="58b8f-176">All application store databases to “F:\\CPSDatabases”</span></span>
    
      - <span data-ttu-id="58b8f-177">所有应用程序存储日志到 "G： \\ CPSLogs"</span><span class="sxs-lookup"><span data-stu-id="58b8f-177">All application store logs to “G:\\CPSLogs”</span></span>
    
      - <span data-ttu-id="58b8f-178">所有响应组存储数据库到 "H： \\ RGSDatabases"</span><span class="sxs-lookup"><span data-stu-id="58b8f-178">All response group store databases to “H:\\RGSDatabases”</span></span>
    
      - <span data-ttu-id="58b8f-179">所有响应组存储日志到 "I： \\ RGSLogs"</span><span class="sxs-lookup"><span data-stu-id="58b8f-179">All response group store logs to “I:\\RGSLogs”</span></span>
    
      - <span data-ttu-id="58b8f-180">所有通讯簿存储数据库到 "J： \\ ABSDatabases"</span><span class="sxs-lookup"><span data-stu-id="58b8f-180">All address book store databases to “J:\\ABSDatabases”</span></span>
    
      - <span data-ttu-id="58b8f-181">所有通讯簿将日志文件存储到 "K： \\ ABSLogs"</span><span class="sxs-lookup"><span data-stu-id="58b8f-181">All address book store log files to “K:\\ABSLogs”</span></span>
    
      - <span data-ttu-id="58b8f-182">所有存档存储数据库到 "L： \\ ArchivingDatabases"</span><span class="sxs-lookup"><span data-stu-id="58b8f-182">All archiving store databases to “L:\\ArchivingDatabases”</span></span>
    
      - <span data-ttu-id="58b8f-183">所有存档存储日志到 "M： \\ ArchivingLogs"</span><span class="sxs-lookup"><span data-stu-id="58b8f-183">All archiving store logs to “M:\\ArchivingLogs”</span></span>
    
      - <span data-ttu-id="58b8f-184">所有监视存储数据库到 "N： \\ MonitoringDatabases"</span><span class="sxs-lookup"><span data-stu-id="58b8f-184">All monitoring store databases to “N:\\MonitoringDatabases”</span></span>
    
      - <span data-ttu-id="58b8f-185">所有监控存储日志文件到 "O： \\ MonitoringLogfiles"</span><span class="sxs-lookup"><span data-stu-id="58b8f-185">All monitoring store log files to “O:\\MonitoringLogfiles”</span></span>
    
    <!-- end list -->
    
    ```powershell    
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
    
    <span data-ttu-id="58b8f-186">使用– DatabasePathMap 参数，可以定义任何逻辑驱动器号映射组合，以提供适合您的 SQL Server 性能和放置要求的最佳解决方案。</span><span class="sxs-lookup"><span data-stu-id="58b8f-186">Using the –DatabasePathMap parameter, you can define any logical drive letter mapping combination that provides the best solution for your SQL Server performance and placement requirements.</span></span>

<span data-ttu-id="58b8f-187">如果使用 **DatabasePathMap** 方法配置数据库数据文件和日志文件，则需要在使用拓扑生成器时对正常过程稍作更改。</span><span class="sxs-lookup"><span data-stu-id="58b8f-187">If you configure your database data files and log files by using the **DatabasePathMap** method, you will need to make a slight change to your normal process when using Topology Builder.</span></span> <span data-ttu-id="58b8f-188">通常情况下，您需要定义拓扑选项、发布拓扑，并选择部署数据库选择。</span><span class="sxs-lookup"><span data-stu-id="58b8f-188">Typically, you would define your topology choices, publish the topology, and choose to deploy the database selections.</span></span>

<span data-ttu-id="58b8f-189">如果已使用 **DatabasePathMap** ，则您已经完成了拓扑生成器过程的第三部分。</span><span class="sxs-lookup"><span data-stu-id="58b8f-189">If you have used **DatabasePathMap** you have already accomplished the third part of the Topology Builder process.</span></span> <span data-ttu-id="58b8f-190">如果在运行拓扑生成器之前拥有完全配置的数据库服务器，则仍将定义所有服务器角色和选项，但不能取消选择用于创建数据库的选项。</span><span class="sxs-lookup"><span data-stu-id="58b8f-190">In the case of having a completely configured database server in advance of running Topology Builder, you would still define all of your server roles and options, but deselect the option to create the databases.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

