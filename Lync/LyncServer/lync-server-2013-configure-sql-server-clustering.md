---
title: 'Lync Server 2013: 配置 SQL Server 群集'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure SQL Server clustering
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56472032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 279c6581d0a56193c094c3dd7b9638fd74e2e60c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-clustering-for-lync-server-2013"></a><span data-ttu-id="1f38d-102">配置 Lync Server 2013 的 SQL Server 群集</span><span class="sxs-lookup"><span data-stu-id="1f38d-102">Configure SQL Server clustering for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f38d-103">_**主题上次修改时间:** 2014-01-10_</span><span class="sxs-lookup"><span data-stu-id="1f38d-103">_**Topic Last Modified:** 2014-01-10_</span></span>

<span data-ttu-id="1f38d-104">Microsoft Lync Server 2013 支持 SQL Server 2012 和 SQL Server 2008 R2 的群集。</span><span class="sxs-lookup"><span data-stu-id="1f38d-104">Microsoft Lync Server 2013 supports clustering for SQL Server 2012 and SQL Server 2008 R2.</span></span> <span data-ttu-id="1f38d-105">有关支持哪些内容的详细信息, 请参阅[Lync Server 2013 中的数据库软件支持](lync-server-2013-database-software-support.md)。</span><span class="sxs-lookup"><span data-stu-id="1f38d-105">For details about what is supported, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span>

<span data-ttu-id="1f38d-106">在安装和部署企业版前端服务器和后端数据库之前, 应设置和配置 SQL Server 群集。</span><span class="sxs-lookup"><span data-stu-id="1f38d-106">You should set up and configure the SQL Server cluster before you install and deploy the Enterprise Edition Front End Server and back-end database.</span></span> <span data-ttu-id="1f38d-107">有关 SQL Server 2012 中故障转移群集的最佳做法和设置说明, <http://technet.microsoft.com/en-us/library/hh231721.aspx>请参阅。</span><span class="sxs-lookup"><span data-stu-id="1f38d-107">For best practices and setup instructions for failover clustering in SQL Server 2012, see <http://technet.microsoft.com/en-us/library/hh231721.aspx>.</span></span> <span data-ttu-id="1f38d-108">有关 SQL Server 2008 中的故障转移群集<http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>, 请参阅。</span><span class="sxs-lookup"><span data-stu-id="1f38d-108">For failover clustering in SQL Server 2008, see <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>.</span></span>

<span data-ttu-id="1f38d-p103">安装 SQL Server 时，应安装 SQL Server Management Studio 来管理数据库位置和日志文件位置。安装 SQL Server 时，SQL Server Management Studio 将作为可选组件安装。</span><span class="sxs-lookup"><span data-stu-id="1f38d-p103">When you install SQL Server, you should install SQL Server Management Studio to manage the locations for database and log file locations. SQL Server Management Studio is installed as an optional component when you install SQL Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1f38d-111">若要在基于 SQL Server 的服务器上安装和部署数据库, 您必须是要在其中安装数据库文件的基于 SQL Server 的服务器的 SQL Server sysadmin 组的成员。</span><span class="sxs-lookup"><span data-stu-id="1f38d-111">To install and deploy the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmin group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="1f38d-112">如果您不是 SQL Server sysadmin 组的成员, 则需要请求将其添加到组中, 直到部署数据库文件。</span><span class="sxs-lookup"><span data-stu-id="1f38d-112">If you are not a member of the SQL Server sysadmin group, you will need to request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="1f38d-113">如果你不能成为 sysadmin 组的成员, 你应该向 SQL Server 数据库管理员提供用于配置和部署数据库的脚本。</span><span class="sxs-lookup"><span data-stu-id="1f38d-113">If you cannot be made a member of the sysadmin group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="1f38d-114">有关完成这些步骤所需的正确用户权限和权限的详细信息, 请参阅<A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 中的 SQL Server 部署权限</A>。</span><span class="sxs-lookup"><span data-stu-id="1f38d-114">For details about the proper user rights and permissions that you need to accomplish the procedures, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a><span data-ttu-id="1f38d-115">配置 SQL Server 群集</span><span class="sxs-lookup"><span data-stu-id="1f38d-115">To configure SQL Server clustering</span></span>

1.  <span data-ttu-id="1f38d-116">完成 SQL Server 群集的安装和配置后, 通过使用 SQL Server 实例虚拟群集名称 (在 SQL Server 群集设置中配置) 和实例, 在拓扑结构生成器中定义 SQL Server 应用商店。SQL Server 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="1f38d-116">After you have completed the installation and configuration of SQL Server clustering, you define the SQL Server store in Topology Builder by using the SQL Server instance virtual cluster name (as configured in the setup for SQL Server clustering) and the instance name of the SQL Server database.</span></span> <span data-ttu-id="1f38d-117">不同于单个基于 SQL Server 的服务器, 你将对基于 SQL Server 的群集服务器使用虚拟节点完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="1f38d-117">Different from a single SQL Server-based server, you will use the virtual node fully qualified domain name (FQDN) for a clustered SQL Server-based server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1f38d-118">无需为拓扑生成器配置单独的 Windows Server 群集节点。</span><span class="sxs-lookup"><span data-stu-id="1f38d-118">The individual Windows Server cluster nodes do not have to be configured for Topology Builder.</span></span> <span data-ttu-id="1f38d-119">你将仅使用虚拟 SQL Server 群集名称。</span><span class="sxs-lookup"><span data-stu-id="1f38d-119">You will use only the virtual SQL Server cluster name.</span></span>

    
    </div>

2.  <span data-ttu-id="1f38d-120">如果使用拓扑生成器部署数据库, 您必须是 SQL Server sysadmin 组的成员。</span><span class="sxs-lookup"><span data-stu-id="1f38d-120">If you are using Topology Builder to deploy your databases, you must be a member of the SQL Server sysadmin group.</span></span> <span data-ttu-id="1f38d-121">如果你是 SQL Server sysadmin 组的成员, 但你在域 (例如 SQL Server 数据库管理员角色) 中没有权限, 则你有权创建数据库, 但无法在 Lync Server 中读取所需的信息。</span><span class="sxs-lookup"><span data-stu-id="1f38d-121">If you are a member of the SQL Server sysadmin group, but you do not have privileges in the domain (for example, a SQL Server database administrator role), then you have the rights to create the databases but not to read necessary information in Lync Server.</span></span> <span data-ttu-id="1f38d-122">有关部署 Lync Server 所需的用户权利和权限的详细信息, 请参阅[Lync server 2013 中的 SQL Server 部署权限](lync-server-2013-deployment-permissions-for-sql-server.md)。</span><span class="sxs-lookup"><span data-stu-id="1f38d-122">For details about the user rights and permissions necessary to deploying Lync Server, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

3.  <span data-ttu-id="1f38d-123">通过使用 SQL Server Management Studio, 确保将数据库文件夹和日志文件文件夹默认值正确映射到 SQL Server 群集中的共享磁盘。</span><span class="sxs-lookup"><span data-stu-id="1f38d-123">Ensure that the database folder and log files folder defaults are mapped correctly to the shared disks in the SQL Server cluster by using SQL Server Management Studio.</span></span> <span data-ttu-id="1f38d-124">如果您将使用拓扑生成器创建数据库, 则这是必需的过程。</span><span class="sxs-lookup"><span data-stu-id="1f38d-124">This is a required procedure if you will create databases by using Topology Builder.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1f38d-125">如果未安装 SQL Server Management Studio, 则可以通过重新运行 SQL Server 安装来安装它, 然后选择管理工具作为现有 SQL Server 部署的新增功能。</span><span class="sxs-lookup"><span data-stu-id="1f38d-125">If you did not install SQL Server Management Studio, you can install it by rerunning the SQL Server installation, and then selecting the management tool as an added feature for the existing SQL Server deployment.</span></span>

    
    </div>

4.  <span data-ttu-id="1f38d-126">使用拓扑生成器或 Windows PowerShell cmdlet 为基于 SQL Server 的服务器安装数据库。</span><span class="sxs-lookup"><span data-stu-id="1f38d-126">Install the databases for the SQL Server-based server by using either Topology Builder or Windows PowerShell cmdlets.</span></span> <span data-ttu-id="1f38d-127">若要使用拓扑生成器, 请使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="1f38d-127">To use Topology Builder, use the following procedure.</span></span> <span data-ttu-id="1f38d-128">若要使用 Windows PowerShell cmdlet, 请参阅[在 Lync server 2013 中使用 Lync Server Management Shell 进行数据库安装](lync-server-2013-database-installation-using-lync-server-management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="1f38d-128">To use Windows PowerShell cmdlets, see [Database installation using Lync Server Management Shell in Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a><span data-ttu-id="1f38d-129">使用拓扑生成器创建数据库</span><span class="sxs-lookup"><span data-stu-id="1f38d-129">To create databases using Topology Builder</span></span>

1.  <span data-ttu-id="1f38d-130">启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="1f38d-130">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="1f38d-131">以下过程假定你已在拓扑生成器中定义并配置了拓扑。</span><span class="sxs-lookup"><span data-stu-id="1f38d-131">The following procedure assumes that you have defined and configured your topology in Topology Builder.</span></span> <span data-ttu-id="1f38d-132">有关定义拓扑的详细信息, 请参阅<A href="lync-server-2013-defining-and-configuring-the-topology.md">在 Lync Server 2013 中定义和配置拓扑</A>。</span><span class="sxs-lookup"><span data-stu-id="1f38d-132">For details about defining your topology, see<A href="lync-server-2013-defining-and-configuring-the-topology.md">Defining and configuring the topology in Lync Server 2013</A>.</span></span> <span data-ttu-id="1f38d-133">若要使用拓扑生成器发布拓扑和配置数据库, 您必须以具有正确的用户权限和组成员身份的用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="1f38d-133">To use Topology Builder to publish the topology and configure the database, you must log on as a user with the correct user rights and group memberships.</span></span> <span data-ttu-id="1f38d-134">有关所需权限和组成员身份的详细信息, 请参阅<A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 中的 SQL Server 部署权限</A>。</span><span class="sxs-lookup"><span data-stu-id="1f38d-134">For details about the required rights and group memberships, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="1f38d-135">在拓扑生成器中, 在发布拓扑时, 在 "**创建数据库**" 页面上, 单击 "**高级**"。</span><span class="sxs-lookup"><span data-stu-id="1f38d-135">In Topology Builder, as you publish the topology, on the **Create databases** page, click **Advanced**.</span></span>

3.  <span data-ttu-id="1f38d-136">"**选择数据库文件位置**" 页面具有两个选项, 可确定如何将数据库文件部署到 SQL Server 群集。</span><span class="sxs-lookup"><span data-stu-id="1f38d-136">The **Select Database File Location** page has two options that determine how the database files will be deployed to the SQL Server cluster.</span></span> <span data-ttu-id="1f38d-137">选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="1f38d-137">Select one of the following:</span></span>
    
      - <span data-ttu-id="1f38d-138">**自动确定数据库文件位置。**</span><span class="sxs-lookup"><span data-stu-id="1f38d-138">**Automatically determine the database file location.**</span></span> <span data-ttu-id="1f38d-139">此选择使用一个算法根据基于 SQL Server 的服务器上的驱动器配置确定数据库日志和数据文件位置。</span><span class="sxs-lookup"><span data-stu-id="1f38d-139">This selection uses an algorithm to determine the database log and data file locations based on the drive configuration on the SQL Server-based server.</span></span> <span data-ttu-id="1f38d-140">将以一种方式分发文件, 以尝试提供最佳性能。</span><span class="sxs-lookup"><span data-stu-id="1f38d-140">The files will be distributed in such a way as to attempt to provide optimal performance.</span></span>
    
      - <span data-ttu-id="1f38d-141">使用 SQL Server 实例默认值。</span><span class="sxs-lookup"><span data-stu-id="1f38d-141">Use SQL Server instance defaults.</span></span> <span data-ttu-id="1f38d-142">选择此选项将根据 SQL Server 实例设置安装日志和数据文件。</span><span class="sxs-lookup"><span data-stu-id="1f38d-142">Selecting this option will install the log and data files according to the SQL Server instance settings.</span></span> <span data-ttu-id="1f38d-143">在将数据库文件部署到 SQL Server 之后, 你的 SQL Server 数据库管理员可能需要重新定位文件以优化特定 SQL Server 配置要求的性能。</span><span class="sxs-lookup"><span data-stu-id="1f38d-143">After deployment of the database files to the SQL Server, your SQL Server database administrator may want to relocate the files to optimize performance for your particular SQL Server configuration requirements.</span></span>

4.  <span data-ttu-id="1f38d-144">完成拓扑的发布, 并确认操作期间没有出现任何错误。</span><span class="sxs-lookup"><span data-stu-id="1f38d-144">Complete the publishing of the topology and confirm that there were no errors during the operation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

