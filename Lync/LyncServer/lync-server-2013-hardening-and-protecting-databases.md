---
title: Lync Server 2013：强化和保护数据库
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting the databases of Lync Server 2013
ms:assetid: 6953e721-3511-4235-b848-51bab093dc89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518330(v=OCS.15)
ms:contentKeyID: 62625490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f222e92da686792a48ccceeaf1686d96f0406e50
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a><span data-ttu-id="36c9a-102">强化和保护 Lync Server 2013 的数据库</span><span class="sxs-lookup"><span data-stu-id="36c9a-102">Hardening and protecting the databases of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36c9a-103">_**上次修改的主题：** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="36c9a-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="36c9a-104">Microsoft Lync Server 2013 还取决于用于存储用户信息、会议状态、存档数据和呼叫详细信息记录（Cdr）的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="36c9a-104">Microsoft Lync Server 2013 also depends on SQL Server databases for storing user information, conference state, archiving data, and Call Detail Records (CDRs).</span></span> <span data-ttu-id="36c9a-105">您可以在 Lync Server 后端数据库上最大限度地提高 Lync Server 2013 数据的可用性，具体方法是以改进容错和简化故障排除的方式对应用程序数据进行分区。</span><span class="sxs-lookup"><span data-stu-id="36c9a-105">You can maximize the availability of Lync Server 2013 data on Lync Server back-end databases, by partitioning the application data in a way that improves fault tolerance and simplifies troubleshooting.</span></span> <span data-ttu-id="36c9a-106">要实现这些目标，可按照以下方式对应用程序数据进行分区：</span><span class="sxs-lookup"><span data-stu-id="36c9a-106">To achieve these goals, partition the application data by:</span></span>

  - <span data-ttu-id="36c9a-107">**使用服务器分区最佳实践**   将您的操作系统、应用程序和程序文件与数据文件分开。</span><span class="sxs-lookup"><span data-stu-id="36c9a-107">**Using server partitioning best practices**   Separate your operating system, application, and program files from your data files.</span></span>

  - <span data-ttu-id="36c9a-108">**存储事务日志文件和数据库文件**   将分别存储这些文件以提高容错能力并优化恢复，并将其存储在加密的磁盘或卷上。</span><span class="sxs-lookup"><span data-stu-id="36c9a-108">**Storing transaction log files and database files**   Store these files separately to increase fault tolerance and optimize recovery, and store them on an encrypted disk or volume.</span></span>

  - <span data-ttu-id="36c9a-109">**使用服务器群集**   群集后端服务器优化 Lync server 2013 系统可用性。</span><span class="sxs-lookup"><span data-stu-id="36c9a-109">**Using server clustering**   Cluster the back-end servers to optimize Lync Server 2013 system availability.</span></span>

  - <span data-ttu-id="36c9a-110">**确保所有数据备份均已加密并正确处理**   丢失、放弃或错放备份媒体可能会对 Lync Server 2013 部署的数据安全造成严重威胁</span><span class="sxs-lookup"><span data-stu-id="36c9a-110">**Ensure that all data backups are encrypted and properly handled**   Lost, discarded, or misplaced backup media can pose a significant threat to data security for Lync Server 2013 deployments</span></span>

<span data-ttu-id="36c9a-111">在任何 Lync Server 2013 服务器（Standard Edition server 除外）中，不能远程访问 SQL Server Express 实例（RTCLOCAL 实例），也不会创建任何本地防火墙例外（标准版服务器上的 SQL Server Express 除外）。</span><span class="sxs-lookup"><span data-stu-id="36c9a-111">On any Lync Server 2013 server except Standard Edition server, the SQL Server Express instance (RTCLOCAL instance) is not remotely accessible, and no local firewall exceptions are created, except for SQL Server Express on a Standard Edition server.</span></span> <span data-ttu-id="36c9a-112">在 Standard Edition Server 上，后端数据库和中央管理存储 (CMS) 均设置为可远程访问。</span><span class="sxs-lookup"><span data-stu-id="36c9a-112">On a Standard Edition server, both the back-end database and the Central Management store (CMS) are set up to be remotely accessible.</span></span> <span data-ttu-id="36c9a-113">要强化 SQL Server 数据库，可执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="36c9a-113">To harden SQL Server databases, you can do the following:</span></span>

  - <span data-ttu-id="36c9a-p103">在 Standard Edition Server 上自定义 SQL Server Express 防火墙，限制可远程访问数据库的服务器的范围。默认情况下，所有 IP 地址都可以远程访问数据库。</span><span class="sxs-lookup"><span data-stu-id="36c9a-p103">Customize the SQL Server Express firewall on Standard Edition servers, limiting the scope of servers that can remotely access the database. By default, any IP address can remotely access the database.</span></span>

  - <span data-ttu-id="36c9a-116">使用 SQL Server 配置管理器指定 SQL Server 远程访问使用的协议、IP 地址和端口：</span><span class="sxs-lookup"><span data-stu-id="36c9a-116">Use SQL Server Configuration Manager to specify the protocols, IP addresses, and ports for SQL Server remote access:</span></span>
    
      - <span data-ttu-id="36c9a-117">Lync Server 2013 使用 TCP/IP 协议。</span><span class="sxs-lookup"><span data-stu-id="36c9a-117">Lync Server 2013 uses the TCP/IP protocol.</span></span> <span data-ttu-id="36c9a-118">它支持 IP 版本 4 (IPv4)，但不支持 IP 版本 6 (IPv6)。</span><span class="sxs-lookup"><span data-stu-id="36c9a-118">It supports IP version 4 (IPv4), but not IP version 6 (IPv6).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="36c9a-119">Lync Server 2013 可以在启用了双 IP 堆栈的网络中正常运行。</span><span class="sxs-lookup"><span data-stu-id="36c9a-119">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

        
        </div>
    
      - <span data-ttu-id="36c9a-120">Lync Server 2013 支持多个 IP 地址（多穴网络地址卡）。</span><span class="sxs-lookup"><span data-stu-id="36c9a-120">Lync Server 2013 supports multiple IP address (multi-homed network address cards).</span></span> <span data-ttu-id="36c9a-121">可以指定 SQL Server 只侦听特定 IP 地址（单个地址或子网），并且只使用特定协议。</span><span class="sxs-lookup"><span data-stu-id="36c9a-121">You can specify that SQL Server listen only to specific IP addresses (individual address or by subnet) and only use specific protocols.</span></span>
    
      - <span data-ttu-id="36c9a-122">Lync Server 2013 支持静态和动态 SQL Server 端口。</span><span class="sxs-lookup"><span data-stu-id="36c9a-122">Lync Server 2013 supports static and dynamic SQL Server ports.</span></span>

  - <span data-ttu-id="36c9a-123">应在静态（非默认）端口上运行 SQL Server，而不要运行 SQL Server 浏览器（这样就不会向客户端报告侦听端口）。</span><span class="sxs-lookup"><span data-stu-id="36c9a-123">Run SQL Server on a static (non-default) port, and do not run SQL Server Browser (so it cannot report the listening port to the client).</span></span> <span data-ttu-id="36c9a-124">这需要在每个 SQL Server 客户端上进行自定义配置，包括前端服务器、监视服务器、存档服务器和管理控制台（运行 Lync Server 命令行管理程序、Lync Server 控制面板或拓扑生成器）以及其他所有运行 Lync Server 数据库的服务器）。</span><span class="sxs-lookup"><span data-stu-id="36c9a-124">This requires a custom configuration on each SQL Server client, including Front End Servers, Monitoring Server, Archiving Server, and administrative consoles (running Lync Server Management Shell, Lync Server Control Panel, or Topology Builder), and all other servers running Lync Server databases).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="36c9a-125">只能将数据库访问权限赋予受信任的数据库管理员。</span><span class="sxs-lookup"><span data-stu-id="36c9a-125">Access to databases must be limited to trusted database administrators.</span></span> <span data-ttu-id="36c9a-126">恶意数据库管理员可以在数据库中插入或修改数据，以通过 Lync Server 2013 服务器获取权限，或从服务获取敏感信息，即使尚未授予数据库管理员的直接访问权限也是如此。对 Lync Server 2013 服务器的控制。</span><span class="sxs-lookup"><span data-stu-id="36c9a-126">A malicious database administrator could insert or modify data into the databases to acquire privileges over the Lync Server 2013 servers or obtain sensitive information from the services, even if the database administrator has not been granted direct access or control of the Lync Server 2013 servers.</span></span>



</div>

<span data-ttu-id="36c9a-127">有关自定义配置和强化 SQL Server 数据库的详细信息，请参阅 NextHop 博客文章 "使用 Lync Server 2010 with a Custom SQL Server Network Configuration" at [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008)。</span><span class="sxs-lookup"><span data-stu-id="36c9a-127">For details about custom configurations and hardening SQL Server databases, see the NextHop blog article, "Using Lync Server 2010 with a Custom SQL Server Network Configuration," at [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="36c9a-128">您还可以加强操作系统和应用程序服务器，也可以使用组策略在 Lync Server 部署中实施安全 lockdowns。</span><span class="sxs-lookup"><span data-stu-id="36c9a-128">You can also harden operating systems and applications servers, and you can use Group Policy to implement security lockdowns in your Lync Server deployment.</span></span> <span data-ttu-id="36c9a-129">有关详细信息，请参阅<A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">强化和保护 Lync Server 2013 的服务器和应用程序</A>。</span><span class="sxs-lookup"><span data-stu-id="36c9a-129">For details, see <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Hardening and protecting servers and applications for Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

