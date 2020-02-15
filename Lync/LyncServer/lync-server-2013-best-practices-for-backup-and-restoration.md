---
title: Lync Server 2013：备份和还原的最佳实践
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for backup and restoration
ms:assetid: abbce0e4-973a-4624-a0c1-e0f22e1d348b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202184(v=OCS.15)
ms:contentKeyID: 51541500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fc2aac99251c0b2e5bc950b3dc11e8e2044b440
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a><span data-ttu-id="16510-102">Lync Server 2013 备份和还原的最佳实践</span><span class="sxs-lookup"><span data-stu-id="16510-102">Best practices for backup and restoration for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16510-103">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="16510-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="16510-104">本节包括两种类型的最佳实践：</span><span class="sxs-lookup"><span data-stu-id="16510-104">This section includes two types of best practices:</span></span>

  - <span data-ttu-id="16510-105">备份和还原的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="16510-105">Best practices for backup and restoration.</span></span>

  - <span data-ttu-id="16510-106">最大程度降低灾难影响的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="16510-106">Best practices for minimizing the impact of a disaster.</span></span>

<div>

## <a name="best-practices-for-backup-and-restoration"></a><span data-ttu-id="16510-107">备份和还原最佳做法</span><span class="sxs-lookup"><span data-stu-id="16510-107">Best Practices for Backup and Restoration</span></span>

<span data-ttu-id="16510-108">为了便于执行备份和还原过程，请在备份或还原数据时应用以下最佳做法：</span><span class="sxs-lookup"><span data-stu-id="16510-108">To facilitate your backup and restoration process, apply the following best practices when you back up or restore your data:</span></span>

  - <span data-ttu-id="16510-109">按适当的时间间隔执行定期备份。</span><span class="sxs-lookup"><span data-stu-id="16510-109">Perform regular backups at appropriate intervals.</span></span> <span data-ttu-id="16510-110">最简单、最常用的备份类型和轮换计划是整个 SQL Server 数据库的夜间完整备份。</span><span class="sxs-lookup"><span data-stu-id="16510-110">The simplest and most commonly used backup type and rotation schedule is a full, nightly backup of the entire SQL Server database.</span></span> <span data-ttu-id="16510-111">然后，如果需要还原，则还原过程只需要一个备份，且不会丢失超过一天的数据。</span><span class="sxs-lookup"><span data-stu-id="16510-111">Then, if restoration is necessary, the restoration process requires only one backup, and no more than a day’s data should be lost.</span></span>

  - <span data-ttu-id="16510-112">如果使用 cmdlet 或 Lync Server 控制面板进行配置更改，请使用**CsConfiguration** cmdlet 在进行更改后拍摄拓扑配置文件（Xds）的快照备份，这样，如果需要还原数据库，则不会丢失所做的更改。</span><span class="sxs-lookup"><span data-stu-id="16510-112">If you use cmdlets or the Lync Server Control Panel to make configuration changes, use the **Export-CsConfiguration** cmdlet to take a snapshot backup of the topology configuration file (Xds.mdf) after you make the changes, so that you won't lose the changes if you need to restore your databases.</span></span> <span data-ttu-id="16510-113">请注意，将以 XML 格式备份此配置并将其压缩为 ZIP 文件。</span><span class="sxs-lookup"><span data-stu-id="16510-113">Note that this configuration is backed up in XML format and compressed as a ZIP file.</span></span>

  - <span data-ttu-id="16510-114">请确保计划用于备份 Lync Server 的共享文件夹有足够的磁盘空间来容纳所有备份的数据。</span><span class="sxs-lookup"><span data-stu-id="16510-114">Make sure that the shared folder you plan to use for backing up Lync Server has sufficient disk space to hold all the backed up data.</span></span>

  - <span data-ttu-id="16510-115">在 Lync Server 使用率通常较低时安排备份，以改善服务器性能和用户体验。</span><span class="sxs-lookup"><span data-stu-id="16510-115">Schedule backups when Lync Server usage is typically low, to improve server performance and user experience.</span></span>

  - <span data-ttu-id="16510-116">请确保备份数据的位置是安全的（我们建议远程位置）。</span><span class="sxs-lookup"><span data-stu-id="16510-116">Make sure that the location where you back up data is secure (we recommend a remote location).</span></span>

  - <span data-ttu-id="16510-117">将备份文件保留在其中，以便在需要还原数据时使用。</span><span class="sxs-lookup"><span data-stu-id="16510-117">Keep the backup files where they will be available, in case you need to restore the data.</span></span>

  - <span data-ttu-id="16510-118">规划和安排对组织支持的还原过程的定期测试。</span><span class="sxs-lookup"><span data-stu-id="16510-118">Plan for and schedule periodic testing of the restoration processes that are supported by your organization.</span></span>

  - <span data-ttu-id="16510-119">提前验证备份和还原过程以确保它们按预期工作。</span><span class="sxs-lookup"><span data-stu-id="16510-119">Validate your backup and restoration processes in advance to make sure that they work as expected.</span></span>

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a><span data-ttu-id="16510-120">最大程度降低灾难影响的最佳做法</span><span class="sxs-lookup"><span data-stu-id="16510-120">Best Practices for Minimizing the Impact of a Disaster</span></span>

<span data-ttu-id="16510-121">处理灾难性服务中断的最佳策略（因断电或突然出现硬件故障等事件而引起）是假设它们将会发生，并进行相应的规划。</span><span class="sxs-lookup"><span data-stu-id="16510-121">The best strategy for dealing with disastrous service interruptions (caused by unmanageable events such as power outages or sudden hardware failures) is to assume they will happen, and to plan accordingly.</span></span>

<span data-ttu-id="16510-122">如果至少中断和停机的 Lync 服务对您的组织至关重要，应考虑实施前端服务器的配对池，如在[Lync Server 2013 中规划高可用性和灾难恢复中](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)所述。</span><span class="sxs-lookup"><span data-stu-id="16510-122">If Lync services, with a minimum of disruption and outage, are business-critical for your organization, you should consider implementing paired pools of Front End Servers, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="16510-123">然后，如果其中一个池发生灾难，管理员可以将该池的用户切换为由另一个池提供服务，最少停机时间。</span><span class="sxs-lookup"><span data-stu-id="16510-123">Then, if one of these pools has a disaster, an administrator can switch the users of that pool to be served by the other pool, with a minimum of downtime.</span></span>

<span data-ttu-id="16510-124">作为备份和还原策略的一部分开发的灾难管理计划应包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="16510-124">The disaster management plans that you develop as part of your backup and restoration strategy should include the following:</span></span>

  - <span data-ttu-id="16510-125">保持软件媒体以及软件和固件更新可随时使用。</span><span class="sxs-lookup"><span data-stu-id="16510-125">Keeping your software media, and your software and firmware updates, readily available.</span></span>

  - <span data-ttu-id="16510-126">维护硬件和软件记录。</span><span class="sxs-lookup"><span data-stu-id="16510-126">Maintaining hardware and software records.</span></span>

  - <span data-ttu-id="16510-127">定期备份数据并监视备份的完整性。</span><span class="sxs-lookup"><span data-stu-id="16510-127">Backing up your data regularly and monitoring the integrity of your backups.</span></span>

  - <span data-ttu-id="16510-128">在灾难恢复中培训你的员工，记录过程，并实施灾难恢复模拟训练。</span><span class="sxs-lookup"><span data-stu-id="16510-128">Training your staff in disaster recovery, documenting procedures, and implementing disaster recovery simulation drills.</span></span>

  - <span data-ttu-id="16510-129">保留备用硬件，或者如果你有服务级别协议（SLA），请与硬件供应商和供应商签订以进行提示替换。</span><span class="sxs-lookup"><span data-stu-id="16510-129">Keeping spare hardware available, or, if you have a service level agreement (SLA), contracting with hardware vendors and suppliers for prompt replacements.</span></span>

  - <span data-ttu-id="16510-130">分隔事务日志文件（.ldf 文件）和数据库文件（.mdf 文件）的位置。</span><span class="sxs-lookup"><span data-stu-id="16510-130">Separating the location of your transaction log files (.ldf files) and database files (.mdf files).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

