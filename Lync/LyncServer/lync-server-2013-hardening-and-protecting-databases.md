---
title: Lync Server 2013：强化和保护数据库
description: Lync Server 2013：强化和保护数据库。
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
ms.openlocfilehash: af1ed8f54384e8ecac3b1e4ce6a4253a10bcc2c6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577428"
---
# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a><span data-ttu-id="4d029-103">强化和保护 Lync Server 2013 的数据库</span><span class="sxs-lookup"><span data-stu-id="4d029-103">Hardening and protecting the databases of Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d029-104">_**上次修改的主题：** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="4d029-104">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="4d029-105">Microsoft Lync Server 2013 还取决于用于存储用户信息、会议状态、存档数据和呼叫详细记录 (Cdr) 的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="4d029-105">Microsoft Lync Server 2013 also depends on SQL Server databases for storing user information, conference state, archiving data, and Call Detail Records (CDRs).</span></span> <span data-ttu-id="4d029-106">您可以在 Lync Server 后端数据库上最大限度地提高 Lync Server 2013 数据的可用性，具体方法是以改进容错和简化故障排除的方式对应用程序数据进行分区。</span><span class="sxs-lookup"><span data-stu-id="4d029-106">You can maximize the availability of Lync Server 2013 data on Lync Server back-end databases, by partitioning the application data in a way that improves fault tolerance and simplifies troubleshooting.</span></span> <span data-ttu-id="4d029-107">要实现这些目标，可按照以下方式对应用程序数据进行分区：</span><span class="sxs-lookup"><span data-stu-id="4d029-107">To achieve these goals, partition the application data by:</span></span>

  - <span data-ttu-id="4d029-108">**使用服务器分区最佳做法**    将您的操作系统、应用程序和程序文件与数据文件分开。</span><span class="sxs-lookup"><span data-stu-id="4d029-108">**Using server partitioning best practices**   Separate your operating system, application, and program files from your data files.</span></span>

  - <span data-ttu-id="4d029-109">**存储事务日志文件和数据库文件**    单独存储这些文件以提高容错能力并优化恢复，并将其存储在加密的磁盘或卷上。</span><span class="sxs-lookup"><span data-stu-id="4d029-109">**Storing transaction log files and database files**   Store these files separately to increase fault tolerance and optimize recovery, and store them on an encrypted disk or volume.</span></span>

  - <span data-ttu-id="4d029-110">**使用服务器群集**    对后端服务器进行群集以优化 Lync Server 2013 系统可用性。</span><span class="sxs-lookup"><span data-stu-id="4d029-110">**Using server clustering**   Cluster the back-end servers to optimize Lync Server 2013 system availability.</span></span>

  - <span data-ttu-id="4d029-111">**确保所有数据备份均已加密并正确处理**    丢失、放弃或错放备份媒体可能会对 Lync Server 2013 部署的数据安全造成重大威胁</span><span class="sxs-lookup"><span data-stu-id="4d029-111">**Ensure that all data backups are encrypted and properly handled**   Lost, discarded, or misplaced backup media can pose a significant threat to data security for Lync Server 2013 deployments</span></span>

<span data-ttu-id="4d029-112">在除 Standard Edition server 之外的任何 Lync Server 2013 服务器上，不能远程访问 RTCLOCAL 实例) 的 SQL Server Express (实例，并且不会创建任何本地防火墙例外，除非在 Standard Edition Server 上使用 SQL Server Express。</span><span class="sxs-lookup"><span data-stu-id="4d029-112">On any Lync Server 2013 server except Standard Edition server, the SQL Server Express instance (RTCLOCAL instance) is not remotely accessible, and no local firewall exceptions are created, except for SQL Server Express on a Standard Edition server.</span></span> <span data-ttu-id="4d029-113">在 Standard Edition Server 上，后端数据库和中央管理存储 (CMS) 均设置为可远程访问。</span><span class="sxs-lookup"><span data-stu-id="4d029-113">On a Standard Edition server, both the back-end database and the Central Management store (CMS) are set up to be remotely accessible.</span></span> <span data-ttu-id="4d029-114">要强化 SQL Server 数据库，可执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4d029-114">To harden SQL Server databases, you can do the following:</span></span>

  - <span data-ttu-id="4d029-p103">在 Standard Edition Server 上自定义 SQL Server Express 防火墙，限制可远程访问数据库的服务器的范围。默认情况下，所有 IP 地址都可以远程访问数据库。</span><span class="sxs-lookup"><span data-stu-id="4d029-p103">Customize the SQL Server Express firewall on Standard Edition servers, limiting the scope of servers that can remotely access the database. By default, any IP address can remotely access the database.</span></span>

  - <span data-ttu-id="4d029-117">使用 SQL Server 配置管理器指定 SQL Server 远程访问使用的协议、IP 地址和端口：</span><span class="sxs-lookup"><span data-stu-id="4d029-117">Use SQL Server Configuration Manager to specify the protocols, IP addresses, and ports for SQL Server remote access:</span></span>
    
      - <span data-ttu-id="4d029-118">Lync Server 2013 使用 TCP/IP 协议。</span><span class="sxs-lookup"><span data-stu-id="4d029-118">Lync Server 2013 uses the TCP/IP protocol.</span></span> <span data-ttu-id="4d029-119">它支持 IP 版本 4 (IPv4)，但不支持 IP 版本 6 (IPv6)。</span><span class="sxs-lookup"><span data-stu-id="4d029-119">It supports IP version 4 (IPv4), but not IP version 6 (IPv6).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="4d029-120">Lync Server 2013 可以在启用了双 IP 堆栈的网络中正常运行。</span><span class="sxs-lookup"><span data-stu-id="4d029-120">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

        
        </div>
    
      - <span data-ttu-id="4d029-121">Lync Server 2013 支持多个 IP 地址 (多穴网络地址卡) 。</span><span class="sxs-lookup"><span data-stu-id="4d029-121">Lync Server 2013 supports multiple IP address (multi-homed network address cards).</span></span> <span data-ttu-id="4d029-122">可以指定 SQL Server 只侦听特定 IP 地址（单个地址或子网），并且只使用特定协议。</span><span class="sxs-lookup"><span data-stu-id="4d029-122">You can specify that SQL Server listen only to specific IP addresses (individual address or by subnet) and only use specific protocols.</span></span>
    
      - <span data-ttu-id="4d029-123">Lync Server 2013 支持静态和动态 SQL Server 端口。</span><span class="sxs-lookup"><span data-stu-id="4d029-123">Lync Server 2013 supports static and dynamic SQL Server ports.</span></span>

  - <span data-ttu-id="4d029-124">应在静态（非默认）端口上运行 SQL Server，而不要运行 SQL Server 浏览器（这样就不会向客户端报告侦听端口）。</span><span class="sxs-lookup"><span data-stu-id="4d029-124">Run SQL Server on a static (non-default) port, and do not run SQL Server Browser (so it cannot report the listening port to the client).</span></span> <span data-ttu-id="4d029-125">这需要在每个 SQL Server 客户端上进行自定义配置，包括前端服务器、监视服务器、存档服务器和管理控制台 (运行 Lync Server 命令行管理程序、Lync Server 控制面板或拓扑生成器) ，以及运行 Lync Server 数据库的所有其他服务器) 。</span><span class="sxs-lookup"><span data-stu-id="4d029-125">This requires a custom configuration on each SQL Server client, including Front End Servers, Monitoring Server, Archiving Server, and administrative consoles (running Lync Server Management Shell, Lync Server Control Panel, or Topology Builder), and all other servers running Lync Server databases).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4d029-126">只能将数据库访问权限赋予受信任的数据库管理员。</span><span class="sxs-lookup"><span data-stu-id="4d029-126">Access to databases must be limited to trusted database administrators.</span></span> <span data-ttu-id="4d029-127">恶意数据库管理员可以在数据库中插入或修改数据，以通过 Lync Server 2013 服务器获取权限，或从服务获取敏感信息，即使尚未授予数据库管理员对 Lync Server 2013 服务器的直接访问或控制权限也是如此。</span><span class="sxs-lookup"><span data-stu-id="4d029-127">A malicious database administrator could insert or modify data into the databases to acquire privileges over the Lync Server 2013 servers or obtain sensitive information from the services, even if the database administrator has not been granted direct access or control of the Lync Server 2013 servers.</span></span>



</div>

<span data-ttu-id="4d029-128">有关自定义配置和强化 SQL Server 数据库的详细信息，请参阅 NextHop 博客文章 "使用 Lync Server 2010 with a Custom SQL Server Network Configuration" at [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008) 。</span><span class="sxs-lookup"><span data-stu-id="4d029-128">For details about custom configurations and hardening SQL Server databases, see the NextHop blog article, "Using Lync Server 2010 with a Custom SQL Server Network Configuration," at [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4d029-129">您还可以加强操作系统和应用程序服务器，也可以使用组策略在 Lync Server 部署中实施安全 lockdowns。</span><span class="sxs-lookup"><span data-stu-id="4d029-129">You can also harden operating systems and applications servers, and you can use Group Policy to implement security lockdowns in your Lync Server deployment.</span></span> <span data-ttu-id="4d029-130">有关详细信息，请参阅 <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">强化和保护 Lync Server 2013 的服务器和应用程序</A>。</span><span class="sxs-lookup"><span data-stu-id="4d029-130">For details, see <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Hardening and protecting servers and applications for Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

