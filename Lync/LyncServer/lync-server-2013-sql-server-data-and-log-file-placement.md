---
title: Lync Server 2013：SQL Server 数据和日志文件放置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SQL Server data and log file placement
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48184395
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a528ba7a348ebb5c8f865a795f8b1f1c1bc30cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845827"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a><span data-ttu-id="52174-102">Lync Server 2013 的 SQL Server 数据和日志文件放置</span><span class="sxs-lookup"><span data-stu-id="52174-102">SQL Server data and log file placement for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52174-103">_**主题上次修改时间:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="52174-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="52174-104">在为 Lync Server 2013 前端池规划和部署 Microsoft SQL Server 2012 或 Microsoft SQL Server 2008 R2 SP1 的过程中, 重要的考虑因素是将数据和日志文件放置在物理硬盘上以提高性能。</span><span class="sxs-lookup"><span data-stu-id="52174-104">During the planning and deployment of Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2 SP1 for your Lync Server 2013 Front End pool, an important consideration is the placement of data and log files onto physical hard disks for performance.</span></span> <span data-ttu-id="52174-105">推荐的磁盘配置是使用6个心轴实现 1 + 0 RAID 集。</span><span class="sxs-lookup"><span data-stu-id="52174-105">The recommended disk configuration is to implement a 1+0 RAID set using 6 spindles.</span></span> <span data-ttu-id="52174-106">将前端池和关联的服务器角色和服务 (即, 存档和监视服务器、Lync Server 响应组服务、Lync Server 呼叫驻留服务) 使用的所有数据库和日志文件放在使用 Lync Server 的 RAID 驱动器集上部署向导将导致配置已测试为获得良好性能。</span><span class="sxs-lookup"><span data-stu-id="52174-106">Placing all database and log files that are used by the Front End pool and associated server roles and services (that is, Archiving and Monitoring Server, Lync Server Response Group service, Lync Server Call Park service) onto the RAID drive set using the Lync Server Deployment Wizard will result in a configuration that has been tested for good performance.</span></span> <span data-ttu-id="52174-107">下表详细介绍了数据库文件及其所负责的内容。</span><span class="sxs-lookup"><span data-stu-id="52174-107">The database files and what they are responsible for is detailed in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="52174-108">如果你的策略和 SQL Server 配置需要更多专用安装, 则可以使用 Lync Server 命令行管理程序将数据库和日志文件安装到任何预定义的位置。</span><span class="sxs-lookup"><span data-stu-id="52174-108">If your policies and SQL Server configurations require a more specialized installation, the database and log files can be installed to any pre-defined location using the Lync Server Management Shell.</span></span> <span data-ttu-id="52174-109">有关详细信息, 请参阅<A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">在 Lync server 2013 中使用 Lync Server Management Shell 的数据库安装</A>。</span><span class="sxs-lookup"><span data-stu-id="52174-109">See <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Database installation using Lync Server Management Shell in Lync Server 2013</A> for more details.</span></span>



</div>

### <a name="data-and-log-files-for-central-management-store"></a><span data-ttu-id="52174-110">中央管理存储的数据和日志文件</span><span class="sxs-lookup"><span data-stu-id="52174-110">Data and Log Files for Central Management Store</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52174-111">中央管理存储数据库文件</span><span class="sxs-lookup"><span data-stu-id="52174-111">Central Management store database files</span></span></th>
<th><span data-ttu-id="52174-112">数据文件或日志用途</span><span class="sxs-lookup"><span data-stu-id="52174-112">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52174-113">Xds</span><span class="sxs-lookup"><span data-stu-id="52174-113">Xds.ldf</span></span></p></td>
<td><p><span data-ttu-id="52174-114">中央管理存储的事务日志文件</span><span class="sxs-lookup"><span data-stu-id="52174-114">Transaction log file for the Central Management store</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52174-115">Xds</span><span class="sxs-lookup"><span data-stu-id="52174-115">Xds.mdf</span></span></p></td>
<td><p><span data-ttu-id="52174-116">维护由拓扑生成器定义和发布的当前 Lync Server 2013 拓扑的配置</span><span class="sxs-lookup"><span data-stu-id="52174-116">Maintains the configuration of the current Lync Server 2013 topology, as defined and published by Topology Builder</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52174-117">.Lis</span><span class="sxs-lookup"><span data-stu-id="52174-117">Lis.mdf</span></span></p></td>
<td><p><span data-ttu-id="52174-118">位置信息服务数据文件</span><span class="sxs-lookup"><span data-stu-id="52174-118">Location Information service data file</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52174-119">.Lis</span><span class="sxs-lookup"><span data-stu-id="52174-119">Lis.ldf</span></span></p></td>
<td><p><span data-ttu-id="52174-120">位置信息服务数据文件的事务日志</span><span class="sxs-lookup"><span data-stu-id="52174-120">Transaction log for the Location Information service data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a><span data-ttu-id="52174-121">用户、会议和通讯簿的数据和日志文件</span><span class="sxs-lookup"><span data-stu-id="52174-121">Data and Log files for User, Conferencing, and Address Book</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52174-122">核心 Lync Server 2013 数据库文件</span><span class="sxs-lookup"><span data-stu-id="52174-122">Core Lync Server 2013 database files</span></span></th>
<th><span data-ttu-id="52174-123">数据文件或日志用途</span><span class="sxs-lookup"><span data-stu-id="52174-123">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52174-124">Rtc</span><span class="sxs-lookup"><span data-stu-id="52174-124">Rtc.mdf</span></span></p></td>
<td><p><span data-ttu-id="52174-125">永久性用户数据 (例如访问控制列表 (Acl)、联系人、计划的会议)</span><span class="sxs-lookup"><span data-stu-id="52174-125">Persistent user data (for example, access control lists (ACLs), contacts, scheduled conferences)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52174-126">Rtc</span><span class="sxs-lookup"><span data-stu-id="52174-126">Rtc.ldf</span></span></p></td>
<td><p><span data-ttu-id="52174-127">Rtc 数据的事务日志</span><span class="sxs-lookup"><span data-stu-id="52174-127">Transaction log for Rtc data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52174-128">Rtcdyn</span><span class="sxs-lookup"><span data-stu-id="52174-128">Rtcdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="52174-129">维护瞬时用户数据 (状态显示运行时数据)</span><span class="sxs-lookup"><span data-stu-id="52174-129">Maintains transient user data (presence runtime data)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52174-130">Rtcdyn</span><span class="sxs-lookup"><span data-stu-id="52174-130">Rtcdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="52174-131">Rtcdyn 数据的事务日志</span><span class="sxs-lookup"><span data-stu-id="52174-131">Transaction log for Rtcdyn data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52174-132">Rtcab</span><span class="sxs-lookup"><span data-stu-id="52174-132">Rtcab.mdf</span></span></p></td>
<td><p><span data-ttu-id="52174-133">实时通信 (RTC) 通讯簿数据库是存储通讯簿服务信息的 SQL Server 存储库</span><span class="sxs-lookup"><span data-stu-id="52174-133">Real-time communications (RTC) address book database is the SQL Server repository where Address Book service information is stored</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52174-134">Rtcab</span><span class="sxs-lookup"><span data-stu-id="52174-134">Rtcab.ldf</span></span></p></td>
<td><p><span data-ttu-id="52174-135">通讯簿服务的事务日志</span><span class="sxs-lookup"><span data-stu-id="52174-135">Transaction log for Address Book Service</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52174-136">Rtclocal</span><span class="sxs-lookup"><span data-stu-id="52174-136">Rtclocal.mdb</span></span></p></td>
<td><p><span data-ttu-id="52174-137">托管会议目录</span><span class="sxs-lookup"><span data-stu-id="52174-137">Hosts the conference directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52174-138">Rtcxds</span><span class="sxs-lookup"><span data-stu-id="52174-138">Rtcxds.mdf</span></span></p></td>
<td><p><span data-ttu-id="52174-139">维护用户数据的备份</span><span class="sxs-lookup"><span data-stu-id="52174-139">Maintains the backup for user data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52174-140">Rtcxds</span><span class="sxs-lookup"><span data-stu-id="52174-140">Rtcxds.ldf</span></span></p></td>
<td><p><span data-ttu-id="52174-141">Rtcxds 数据的事务日志</span><span class="sxs-lookup"><span data-stu-id="52174-141">Transaction log for Rtcxds data</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a><span data-ttu-id="52174-142">通话寄存和响应组的数据和日志文件</span><span class="sxs-lookup"><span data-stu-id="52174-142">Data and Log Files for Call Park and Response Group</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52174-143">应用程序数据库</span><span class="sxs-lookup"><span data-stu-id="52174-143">Application database</span></span></th>
<th><span data-ttu-id="52174-144">数据文件或日志用途</span><span class="sxs-lookup"><span data-stu-id="52174-144">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52174-145">Cpsdyn</span><span class="sxs-lookup"><span data-stu-id="52174-145">Cpsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="52174-146">用于呼叫驻留应用程序的动态信息数据库</span><span class="sxs-lookup"><span data-stu-id="52174-146">Dynamic information database for the Call Park application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52174-147">Cpsdyn</span><span class="sxs-lookup"><span data-stu-id="52174-147">Cpsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="52174-148">呼叫驻留应用程序数据文件的事务日志</span><span class="sxs-lookup"><span data-stu-id="52174-148">Transaction log for Call Park application data file</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52174-149">Rgsconfig</span><span class="sxs-lookup"><span data-stu-id="52174-149">Rgsconfig.mdf</span></span></p></td>
<td><p><span data-ttu-id="52174-150">用于配置服务的 Lync Server 响应组服务数据文件</span><span class="sxs-lookup"><span data-stu-id="52174-150">Lync Server Response Group service data file for the configuration of the services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52174-151">Rgsconfig</span><span class="sxs-lookup"><span data-stu-id="52174-151">Rgsconfig.ldf</span></span></p></td>
<td><p><span data-ttu-id="52174-152">响应组应用程序配置的事务日志文件</span><span class="sxs-lookup"><span data-stu-id="52174-152">Transaction log file for the Response Group application configuration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52174-153">Rgsdyn</span><span class="sxs-lookup"><span data-stu-id="52174-153">Rgsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="52174-154">运行时操作的响应组服务数据文件</span><span class="sxs-lookup"><span data-stu-id="52174-154">Response Group service data file for runtime operations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52174-155">Rgsdyn</span><span class="sxs-lookup"><span data-stu-id="52174-155">Rgsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="52174-156">响应组服务运行时数据文件的事务日志</span><span class="sxs-lookup"><span data-stu-id="52174-156">Transaction log for the Response Group service runtime data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a><span data-ttu-id="52174-157">用于存档和监视服务器的数据和日志文件</span><span class="sxs-lookup"><span data-stu-id="52174-157">Data and Log Files for Archiving and Monitoring Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52174-158">存档和监视数据库文件</span><span class="sxs-lookup"><span data-stu-id="52174-158">Archiving and Monitoring database files</span></span></th>
<th><span data-ttu-id="52174-159">数据文件或日志用途</span><span class="sxs-lookup"><span data-stu-id="52174-159">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52174-160">LcsCdr</span><span class="sxs-lookup"><span data-stu-id="52174-160">LcsCdr.mdf</span></span></p></td>
<td><p><span data-ttu-id="52174-161">监视服务器的呼叫详细记录 (CDR) 流程的数据存储</span><span class="sxs-lookup"><span data-stu-id="52174-161">Data store for the call detail recording (CDR) process of the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52174-162">LcsCdr</span><span class="sxs-lookup"><span data-stu-id="52174-162">LcsCdr.ldf</span></span></p></td>
<td><p><span data-ttu-id="52174-163">呼叫详细记录 (CDR) 数据的事务日志</span><span class="sxs-lookup"><span data-stu-id="52174-163">Transaction log for call detail recording (CDR) data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52174-164">QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="52174-164">QoEMetrics.mdf</span></span></p></td>
<td><p><span data-ttu-id="52174-165">从监视服务器存储的体验数据文件的质量</span><span class="sxs-lookup"><span data-stu-id="52174-165">Quality of Experience data file stored from the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52174-166">QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="52174-166">QoEMetrics.ldf</span></span></p></td>
<td><p><span data-ttu-id="52174-167">用于监视数据的事务日志</span><span class="sxs-lookup"><span data-stu-id="52174-167">Transaction log for Monitoring data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52174-168">Lcslog</span><span class="sxs-lookup"><span data-stu-id="52174-168">Lcslog.mdf</span></span></p></td>
<td><p><span data-ttu-id="52174-169">用于保留存档服务器上的即时消息和会议数据的数据文件</span><span class="sxs-lookup"><span data-stu-id="52174-169">Data file for the retention of instant messaging and conferencing data on an Archiving Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52174-170">Lcslog</span><span class="sxs-lookup"><span data-stu-id="52174-170">Lcslog.ldf</span></span></p></td>
<td><p><span data-ttu-id="52174-171">用于存档数据的事务日志</span><span class="sxs-lookup"><span data-stu-id="52174-171">Transaction log for Archiving data</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="52174-172">在本主题中, 对磁盘和 RAID 集进行引用。</span><span class="sxs-lookup"><span data-stu-id="52174-172">In this topic, references are made to disk and to RAID set.</span></span> <span data-ttu-id="52174-173">请注意, 在 SQL Server 资源的配置中, 引用磁盘意味着单个硬件设备。</span><span class="sxs-lookup"><span data-stu-id="52174-173">Note that in the configuration of SQL Server resources, referring to a disk means a single hardware device.</span></span> <span data-ttu-id="52174-174">包含两个分区的硬盘 (其中一个包含日志文件和保存数据文件的其他分区) 不同于两个磁盘, 每个磁盘都专用于日志或数据文件。</span><span class="sxs-lookup"><span data-stu-id="52174-174">A hard disk drive with two partitions, one holding log files and the other partition holding data files, is not the same as two disks, each dedicated to either log or data files.</span></span>

<span data-ttu-id="52174-175">在对 RAID 集的参考中, 有许多来自不同供应商的不同 RAID 技术。</span><span class="sxs-lookup"><span data-stu-id="52174-175">In reference to RAID sets, there are a number of different RAID technologies from various vendors.</span></span> <span data-ttu-id="52174-176">随着存储区域网络 (SAN) 的急剧增加, 专用于单个系统的 RAID 集将 rarer。</span><span class="sxs-lookup"><span data-stu-id="52174-176">And, with the proliferation of storage area networks (SAN), RAID sets dedicated to a single system are rarer.</span></span> <span data-ttu-id="52174-177">在针对 Lync Server 2013 配置 SQL Server 性能时, 应咨询你的 RAID 或 SAN 供应商, 以确定你的磁盘布局的最佳配置。</span><span class="sxs-lookup"><span data-stu-id="52174-177">You should consult with your RAID or SAN vendor to determine what the best configuration is for your disk layout when configuring for SQL Server performance with Lync Server 2013.</span></span>

<span data-ttu-id="52174-178">另请注意, 并非所有磁盘驱动器都是同等创建的;某些性能比其他更好。</span><span class="sxs-lookup"><span data-stu-id="52174-178">Note also that not all disk drives are created equally; some perform better than others.</span></span> <span data-ttu-id="52174-179">由于转速、硬件缓存大小和其他因素, 来自同一制造商的驱动器在性能上可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="52174-179">Even drives from the same manufacturer can vary in performance because of rotational speed, hardware cache size, and other factors.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

