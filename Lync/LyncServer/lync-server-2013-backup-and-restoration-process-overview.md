---
title: Lync Server 2013：备份和还原过程概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration process overview
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202192(v=OCS.15)
ms:contentKeyID: 51541524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 559ebb5a5d5ba91b5a4952037c18ad509ed5cec7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a><span data-ttu-id="7d3b1-102">Lync Server 2013 的备份和还原过程概述</span><span class="sxs-lookup"><span data-stu-id="7d3b1-102">Backup and restoration process overview for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d3b1-103">_**主题上次修改时间：** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="7d3b1-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="7d3b1-104">本节概述了 Lync Server 2013 的备份和还原过程的工作原理。</span><span class="sxs-lookup"><span data-stu-id="7d3b1-104">This section provides an overview of how the backup and restoration process works for Lync Server 2013.</span></span> <span data-ttu-id="7d3b1-105">无论其位置如何，都可以对所有标准版服务器和企业版服务器使用相同的过程。</span><span class="sxs-lookup"><span data-stu-id="7d3b1-105">You use the same process for all Standard Edition servers and Enterprise Edition servers, regardless of their location.</span></span>

<span data-ttu-id="7d3b1-106">通常，备份过程的工作原理如下所示：</span><span class="sxs-lookup"><span data-stu-id="7d3b1-106">In general, the backup process works as follows:</span></span>

  - <span data-ttu-id="7d3b1-107">在不属于任何池的独立计算机上创建作为共享文件夹的备份位置。</span><span class="sxs-lookup"><span data-stu-id="7d3b1-107">You create a backup location as a shared folder on a stand-alone computer that is not part of any pool.</span></span> <span data-ttu-id="7d3b1-108">备份的位置在 **$Backup**中引用。</span><span class="sxs-lookup"><span data-stu-id="7d3b1-108">The location of the backup is referenced in **$Backup**.</span></span>

  - <span data-ttu-id="7d3b1-109">在定期、计划的基础上，你备份 lync server 数据库和[Lync server 2013 中的备份和还原要求](lync-server-2013-backup-and-restoration-requirements-data.md)中描述的所有文件存储：按照[备份 lync server 2013](lync-server-2013-backing-up-lync-server.md)中所述的过程，数据集中管理存储包括所有服务器设置和配置。</span><span class="sxs-lookup"><span data-stu-id="7d3b1-109">On a regular, scheduled basis, you back up all the Lync Server databases and all the file stores that are described in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md) by following the procedures described in [Backing up Lync Server 2013](lync-server-2013-backing-up-lync-server.md) The Central Management store includes all the server settings and configurations.</span></span>

  - <span data-ttu-id="7d3b1-110">每次运行后续备份时，都将创建一个新的共享文件夹，并更改 **$Backup**引用的路径。</span><span class="sxs-lookup"><span data-stu-id="7d3b1-110">Each time you run a subsequent backup, you create a new shared folder and change the path that **$Backup** references.</span></span>

<span data-ttu-id="7d3b1-111">通常，还原过程的工作原理如下所示：</span><span class="sxs-lookup"><span data-stu-id="7d3b1-111">In general, the restoration process works as follows:</span></span>

  - <span data-ttu-id="7d3b1-112">当发生故障或中断时，请将 **$Backup**引用的位置中的数据还原到新计算机或全新计算机。</span><span class="sxs-lookup"><span data-stu-id="7d3b1-112">When a failure or outage occurs, you restore the data in the location referenced by **$Backup** to new or clean computers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7d3b1-113">此还原过程不会将数据还原到现有服务器状态。</span><span class="sxs-lookup"><span data-stu-id="7d3b1-113">This restoration process does not restore data onto an existing server state.</span></span> <span data-ttu-id="7d3b1-114">也就是说，此过程要求服务器干净或全新。</span><span class="sxs-lookup"><span data-stu-id="7d3b1-114">That is, this process requires that the server is clean or new.</span></span>

    
    </div>

  - <span data-ttu-id="7d3b1-115">若要使你的用户和会议信息能够恢复到故障点，你可以使用配对的前端池实施灾难恢复拓扑，如在[Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="7d3b1-115">To enable your user and conference information to be recoverable to the point of failure, you can implement a disaster recovery topology with paired Front End pools, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="7d3b1-116">所有域名系统（DNS）配置、动态主机配置协议（DHCP）配置、域名、计算机完全限定的域名（Fqdn）、文件存储路径等在还原时的还原时间必须相同。退后。</span><span class="sxs-lookup"><span data-stu-id="7d3b1-116">All Domain Name System (DNS) configuration, Dynamic Host Configuration Protocol (DHCP) configuration, domain names, computer fully qualified domain names (FQDNs), file store paths, and so on must be the same at the time of restoration that they were at the time of back up.</span></span>

<span data-ttu-id="7d3b1-117">如果运行 Lync Server 的服务器失败，则恢复包括以下步骤：</span><span class="sxs-lookup"><span data-stu-id="7d3b1-117">If a server running Lync Server fails, recovery includes the following steps:</span></span>

  - <span data-ttu-id="7d3b1-118">使用与故障计算机相同的 FQDN 在新计算机或全新计算机上安装操作系统。</span><span class="sxs-lookup"><span data-stu-id="7d3b1-118">Install the operating system on a new or clean computer with the same FQDN as the failed computer.</span></span>

  - <span data-ttu-id="7d3b1-119">重新安装证书。</span><span class="sxs-lookup"><span data-stu-id="7d3b1-119">Reinstall certificates.</span></span>

  - <span data-ttu-id="7d3b1-120">如果服务器托管数据库，请安装 Microsoft SQL Server 2012 或 Microsoft SQL Server 2008 R2。</span><span class="sxs-lookup"><span data-stu-id="7d3b1-120">If the server hosted a database, install Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2.</span></span>

  - <span data-ttu-id="7d3b1-121">通常情况下，如果服务器托管数据库，请运行拓扑生成器来创建和安装数据库并设置访问控制列表（Acl）。</span><span class="sxs-lookup"><span data-stu-id="7d3b1-121">In general, if the server hosted a database, run Topology Builder to create and install the database and set up access control lists (ACLs).</span></span>

  - <span data-ttu-id="7d3b1-122">一般情况下，如果服务器托管了服务器角色，请运行 "Lync Server 部署向导" 的步骤1到步骤4以安装本地配置文件、安装服务器角色组件、分配证书和启动服务。</span><span class="sxs-lookup"><span data-stu-id="7d3b1-122">In general, if the server hosted a server role, run step 1 through step 4 of the Lync Server Deployment Wizard to install the local configuration files, install the server role components, assign certificates, and start the services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7d3b1-123">如果服务器托管与服务器角色 collocated 的数据库，运行 Lync Server 部署向导的步骤2将重新创建数据库。</span><span class="sxs-lookup"><span data-stu-id="7d3b1-123">If the server hosted a database collocated with the server role, running step 2 of the Lync Server Deployment Wizard recreates the database.</span></span>

    
    </div>

  - <span data-ttu-id="7d3b1-124">如果服务器托管数据库，请还原备份的数据。</span><span class="sxs-lookup"><span data-stu-id="7d3b1-124">If the server hosted a database, restore the backed up data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

