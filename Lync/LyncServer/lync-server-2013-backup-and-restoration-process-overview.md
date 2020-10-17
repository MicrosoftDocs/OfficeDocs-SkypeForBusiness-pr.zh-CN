---
title: Lync Server 2013：备份和还原过程概述
description: Lync Server 2013：备份和还原过程概述。
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
ms.openlocfilehash: 77b833a05021d3a848e9de1ee8768f7daa194c6a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563168"
---
# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a><span data-ttu-id="dcf7c-103">Lync Server 2013 的备份和还原过程概述</span><span class="sxs-lookup"><span data-stu-id="dcf7c-103">Backup and restoration process overview for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dcf7c-104">_**上次修改的主题：** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="dcf7c-104">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="dcf7c-105">本节提供了有关 Lync Server 2013 备份和还原过程的工作原理的概述。</span><span class="sxs-lookup"><span data-stu-id="dcf7c-105">This section provides an overview of how the backup and restoration process works for Lync Server 2013.</span></span> <span data-ttu-id="dcf7c-106">所有 Standard Edition 服务器和 Enterprise Edition 服务器都使用相同的过程，而不考虑其位置。</span><span class="sxs-lookup"><span data-stu-id="dcf7c-106">You use the same process for all Standard Edition servers and Enterprise Edition servers, regardless of their location.</span></span>

<span data-ttu-id="dcf7c-107">通常情况下，备份过程的工作方式如下所示：</span><span class="sxs-lookup"><span data-stu-id="dcf7c-107">In general, the backup process works as follows:</span></span>

  - <span data-ttu-id="dcf7c-108">您将备份位置创建为独立计算机上的共享文件夹，该文件夹不是任何池的一部分。</span><span class="sxs-lookup"><span data-stu-id="dcf7c-108">You create a backup location as a shared folder on a stand-alone computer that is not part of any pool.</span></span> <span data-ttu-id="dcf7c-109">备份的位置在 **$Backup**中引用。</span><span class="sxs-lookup"><span data-stu-id="dcf7c-109">The location of the backup is referenced in **$Backup**.</span></span>

  - <span data-ttu-id="dcf7c-110">在定期计划的基础上，您可以备份 lync server 2013 中的 [备份和还原要求](lync-server-2013-backup-and-restoration-requirements-data.md) 中描述的所有 lync server 数据库和所有文件存储区：数据按照 [备份 lync server 2013](lync-server-2013-backing-up-lync-server.md) 中所述的过程操作中央管理存储包括所有服务器设置和配置。</span><span class="sxs-lookup"><span data-stu-id="dcf7c-110">On a regular, scheduled basis, you back up all the Lync Server databases and all the file stores that are described in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md) by following the procedures described in [Backing up Lync Server 2013](lync-server-2013-backing-up-lync-server.md) The Central Management store includes all the server settings and configurations.</span></span>

  - <span data-ttu-id="dcf7c-111">每次运行后续备份时，都会创建一个新的共享文件夹，并更改 **$Backup** 引用的路径。</span><span class="sxs-lookup"><span data-stu-id="dcf7c-111">Each time you run a subsequent backup, you create a new shared folder and change the path that **$Backup** references.</span></span>

<span data-ttu-id="dcf7c-112">通常情况下，还原过程的工作方式如下所示：</span><span class="sxs-lookup"><span data-stu-id="dcf7c-112">In general, the restoration process works as follows:</span></span>

  - <span data-ttu-id="dcf7c-113">当发生故障或中断时，您将 **$Backup** 引用的位置中的数据还原到新的或清理的计算机。</span><span class="sxs-lookup"><span data-stu-id="dcf7c-113">When a failure or outage occurs, you restore the data in the location referenced by **$Backup** to new or clean computers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="dcf7c-114">此还原过程不会将数据还原到现有的服务器状态。</span><span class="sxs-lookup"><span data-stu-id="dcf7c-114">This restoration process does not restore data onto an existing server state.</span></span> <span data-ttu-id="dcf7c-115">也就是说，此过程要求服务器是干净的或新的。</span><span class="sxs-lookup"><span data-stu-id="dcf7c-115">That is, this process requires that the server is clean or new.</span></span>

    
    </div>

  - <span data-ttu-id="dcf7c-116">若要使您的用户和会议信息能够恢复到故障点，您可以实施具有配对前端池的灾难恢复拓扑，如在 [Lync Server 2013 中规划高可用性和灾难恢复中](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)所述。</span><span class="sxs-lookup"><span data-stu-id="dcf7c-116">To enable your user and conference information to be recoverable to the point of failure, you can implement a disaster recovery topology with paired Front End pools, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="dcf7c-117">所有域名系统 (DNS) 配置、动态主机配置协议 (DHCP) 配置、域名、计算机完全限定的域名 (Fqdn) 、文件存储路径等，在还原时，它们在备份时必须相同。</span><span class="sxs-lookup"><span data-stu-id="dcf7c-117">All Domain Name System (DNS) configuration, Dynamic Host Configuration Protocol (DHCP) configuration, domain names, computer fully qualified domain names (FQDNs), file store paths, and so on must be the same at the time of restoration that they were at the time of back up.</span></span>

<span data-ttu-id="dcf7c-118">如果运行 Lync Server 的服务器出现故障，恢复过程将包括以下步骤：</span><span class="sxs-lookup"><span data-stu-id="dcf7c-118">If a server running Lync Server fails, recovery includes the following steps:</span></span>

  - <span data-ttu-id="dcf7c-119">在具有故障计算机的 FQDN 相同的新计算机或干净计算机上安装操作系统。</span><span class="sxs-lookup"><span data-stu-id="dcf7c-119">Install the operating system on a new or clean computer with the same FQDN as the failed computer.</span></span>

  - <span data-ttu-id="dcf7c-120">重新安装证书。</span><span class="sxs-lookup"><span data-stu-id="dcf7c-120">Reinstall certificates.</span></span>

  - <span data-ttu-id="dcf7c-121">如果服务器托管数据库，则安装 Microsoft SQL Server 2012 或 Microsoft SQL Server 2008 R2。</span><span class="sxs-lookup"><span data-stu-id="dcf7c-121">If the server hosted a database, install Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2.</span></span>

  - <span data-ttu-id="dcf7c-122">通常情况下，如果服务器托管数据库，请运行拓扑生成器以创建和安装数据库，并设置 (Acl) 中的访问控制列表。</span><span class="sxs-lookup"><span data-stu-id="dcf7c-122">In general, if the server hosted a database, run Topology Builder to create and install the database and set up access control lists (ACLs).</span></span>

  - <span data-ttu-id="dcf7c-123">通常情况下，如果服务器托管服务器角色，请运行 Lync Server 部署向导的步骤1到步骤4以安装本地配置文件，安装服务器角色组件，分配证书，并启动服务。</span><span class="sxs-lookup"><span data-stu-id="dcf7c-123">In general, if the server hosted a server role, run step 1 through step 4 of the Lync Server Deployment Wizard to install the local configuration files, install the server role components, assign certificates, and start the services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dcf7c-124">如果服务器托管了与服务器角色并置的数据库，运行 Lync Server 部署向导的步骤2将重新创建数据库。</span><span class="sxs-lookup"><span data-stu-id="dcf7c-124">If the server hosted a database collocated with the server role, running step 2 of the Lync Server Deployment Wizard recreates the database.</span></span>

    
    </div>

  - <span data-ttu-id="dcf7c-125">如果服务器托管数据库，请还原备份的数据。</span><span class="sxs-lookup"><span data-stu-id="dcf7c-125">If the server hosted a database, restore the backed up data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

