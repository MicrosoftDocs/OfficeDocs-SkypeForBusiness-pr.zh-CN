---
title: Lync Server 2013： SQL Server 数据和日志文件的放置
description: Lync Server 2013： SQL Server 数据和日志文件的放置。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SQL Server data and log file placement
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48184395
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a127254fec41a734136df9b63fc6cc8929745df7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558278"
---
# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a><span data-ttu-id="56f8e-103">Lync Server 2013 的 SQL Server 数据和日志文件放置</span><span class="sxs-lookup"><span data-stu-id="56f8e-103">SQL Server data and log file placement for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56f8e-104">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="56f8e-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="56f8e-105">在为 Lync Server 2013 前端池规划和部署 Microsoft SQL Server 2012 或 Microsoft SQL Server 2008 R2 SP1 的过程中，重要的考虑因素是将数据和日志文件放置在物理硬盘上以提高性能。</span><span class="sxs-lookup"><span data-stu-id="56f8e-105">During the planning and deployment of Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2 SP1 for your Lync Server 2013 Front End pool, an important consideration is the placement of data and log files onto physical hard disks for performance.</span></span> <span data-ttu-id="56f8e-106">建议的磁盘配置是使用6个心轴来实现 1 + 0 RAID 集。</span><span class="sxs-lookup"><span data-stu-id="56f8e-106">The recommended disk configuration is to implement a 1+0 RAID set using 6 spindles.</span></span> <span data-ttu-id="56f8e-107">将由前端池和相关服务器角色和 (服务使用的所有数据库和日志文件（即，存档和监控服务器、Lync Server 响应组服务、Lync Server 呼叫寄存服务) 使用 Lync server 部署向导）中的所有数据库和日志文件都放在使用 Lync Server 部署向导的 RAID 驱动器集上时，将导致配置已测试为获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="56f8e-107">Placing all database and log files that are used by the Front End pool and associated server roles and services (that is, Archiving and Monitoring Server, Lync Server Response Group service, Lync Server Call Park service) onto the RAID drive set using the Lync Server Deployment Wizard will result in a configuration that has been tested for good performance.</span></span> <span data-ttu-id="56f8e-108">下表详细介绍了这些数据库文件以及它们负责的内容。</span><span class="sxs-lookup"><span data-stu-id="56f8e-108">The database files and what they are responsible for is detailed in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="56f8e-109">如果您的策略和 SQL Server 配置需要更专用的安装，则可以使用 Lync Server 命令行管理程序将数据库和日志文件安装到任何预定义的位置。</span><span class="sxs-lookup"><span data-stu-id="56f8e-109">If your policies and SQL Server configurations require a more specialized installation, the database and log files can be installed to any pre-defined location using the Lync Server Management Shell.</span></span> <span data-ttu-id="56f8e-110">有关更多详细信息，请参阅 <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">使用 Lync Server 命令行管理程序在 Lync server 2013 中安装数据库</A> 。</span><span class="sxs-lookup"><span data-stu-id="56f8e-110">See <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Database installation using Lync Server Management Shell in Lync Server 2013</A> for more details.</span></span>



</div>

### <a name="data-and-log-files-for-central-management-store"></a><span data-ttu-id="56f8e-111">中央管理存储的数据和日志文件</span><span class="sxs-lookup"><span data-stu-id="56f8e-111">Data and Log Files for Central Management Store</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="56f8e-112">中央管理存储数据库文件</span><span class="sxs-lookup"><span data-stu-id="56f8e-112">Central Management store database files</span></span></th>
<th><span data-ttu-id="56f8e-113">用于数据文件或日志</span><span class="sxs-lookup"><span data-stu-id="56f8e-113">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56f8e-114">Xds</span><span class="sxs-lookup"><span data-stu-id="56f8e-114">Xds.ldf</span></span></p></td>
<td><p><span data-ttu-id="56f8e-115">中央管理存储的事务日志文件</span><span class="sxs-lookup"><span data-stu-id="56f8e-115">Transaction log file for the Central Management store</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56f8e-116">Xds</span><span class="sxs-lookup"><span data-stu-id="56f8e-116">Xds.mdf</span></span></p></td>
<td><p><span data-ttu-id="56f8e-117">维护由拓扑生成器定义和发布的当前 Lync Server 2013 拓扑的配置</span><span class="sxs-lookup"><span data-stu-id="56f8e-117">Maintains the configuration of the current Lync Server 2013 topology, as defined and published by Topology Builder</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56f8e-118">.Lis</span><span class="sxs-lookup"><span data-stu-id="56f8e-118">Lis.mdf</span></span></p></td>
<td><p><span data-ttu-id="56f8e-119">位置信息服务数据文件</span><span class="sxs-lookup"><span data-stu-id="56f8e-119">Location Information service data file</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56f8e-120">.Lis</span><span class="sxs-lookup"><span data-stu-id="56f8e-120">Lis.ldf</span></span></p></td>
<td><p><span data-ttu-id="56f8e-121">位置信息服务数据文件的事务日志</span><span class="sxs-lookup"><span data-stu-id="56f8e-121">Transaction log for the Location Information service data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a><span data-ttu-id="56f8e-122">用户、会议和通讯簿的数据和日志文件</span><span class="sxs-lookup"><span data-stu-id="56f8e-122">Data and Log files for User, Conferencing, and Address Book</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="56f8e-123">核心 Lync Server 2013 数据库文件</span><span class="sxs-lookup"><span data-stu-id="56f8e-123">Core Lync Server 2013 database files</span></span></th>
<th><span data-ttu-id="56f8e-124">用于数据文件或日志</span><span class="sxs-lookup"><span data-stu-id="56f8e-124">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56f8e-125">Rtc</span><span class="sxs-lookup"><span data-stu-id="56f8e-125">Rtc.mdf</span></span></p></td>
<td><p><span data-ttu-id="56f8e-126">持久性用户数据 (例如，访问控制列表 (Acl) 、联系人、安排的会议) </span><span class="sxs-lookup"><span data-stu-id="56f8e-126">Persistent user data (for example, access control lists (ACLs), contacts, scheduled conferences)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56f8e-127">Rtc</span><span class="sxs-lookup"><span data-stu-id="56f8e-127">Rtc.ldf</span></span></p></td>
<td><p><span data-ttu-id="56f8e-128">Rtc 数据的事务日志</span><span class="sxs-lookup"><span data-stu-id="56f8e-128">Transaction log for Rtc data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56f8e-129">Rtcdyn</span><span class="sxs-lookup"><span data-stu-id="56f8e-129">Rtcdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="56f8e-130">维护瞬时用户数据 (状态运行时数据) </span><span class="sxs-lookup"><span data-stu-id="56f8e-130">Maintains transient user data (presence runtime data)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56f8e-131">Rtcdyn</span><span class="sxs-lookup"><span data-stu-id="56f8e-131">Rtcdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="56f8e-132">Rtcdyn 数据的事务日志</span><span class="sxs-lookup"><span data-stu-id="56f8e-132">Transaction log for Rtcdyn data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56f8e-133">Rtcab</span><span class="sxs-lookup"><span data-stu-id="56f8e-133">Rtcab.mdf</span></span></p></td>
<td><p><span data-ttu-id="56f8e-134">实时通信 (RTC) 通讯簿数据库是存储通讯簿服务信息的 SQL Server 存储库</span><span class="sxs-lookup"><span data-stu-id="56f8e-134">Real-time communications (RTC) address book database is the SQL Server repository where Address Book service information is stored</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56f8e-135">Rtcab</span><span class="sxs-lookup"><span data-stu-id="56f8e-135">Rtcab.ldf</span></span></p></td>
<td><p><span data-ttu-id="56f8e-136">通讯簿服务的事务日志</span><span class="sxs-lookup"><span data-stu-id="56f8e-136">Transaction log for Address Book Service</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56f8e-137">Rtclocal</span><span class="sxs-lookup"><span data-stu-id="56f8e-137">Rtclocal.mdb</span></span></p></td>
<td><p><span data-ttu-id="56f8e-138">承载会议目录</span><span class="sxs-lookup"><span data-stu-id="56f8e-138">Hosts the conference directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56f8e-139">Rtcxds</span><span class="sxs-lookup"><span data-stu-id="56f8e-139">Rtcxds.mdf</span></span></p></td>
<td><p><span data-ttu-id="56f8e-140">维护用户数据的备份</span><span class="sxs-lookup"><span data-stu-id="56f8e-140">Maintains the backup for user data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56f8e-141">Rtcxds</span><span class="sxs-lookup"><span data-stu-id="56f8e-141">Rtcxds.ldf</span></span></p></td>
<td><p><span data-ttu-id="56f8e-142">Rtcxds 数据的事务日志</span><span class="sxs-lookup"><span data-stu-id="56f8e-142">Transaction log for Rtcxds data</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a><span data-ttu-id="56f8e-143">呼叫寄存和响应组的数据和日志文件</span><span class="sxs-lookup"><span data-stu-id="56f8e-143">Data and Log Files for Call Park and Response Group</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="56f8e-144">应用程序数据库</span><span class="sxs-lookup"><span data-stu-id="56f8e-144">Application database</span></span></th>
<th><span data-ttu-id="56f8e-145">用于数据文件或日志</span><span class="sxs-lookup"><span data-stu-id="56f8e-145">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56f8e-146">Cpsdyn</span><span class="sxs-lookup"><span data-stu-id="56f8e-146">Cpsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="56f8e-147">呼叫寄存应用程序的动态信息数据库</span><span class="sxs-lookup"><span data-stu-id="56f8e-147">Dynamic information database for the Call Park application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56f8e-148">Cpsdyn</span><span class="sxs-lookup"><span data-stu-id="56f8e-148">Cpsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="56f8e-149">呼叫寄存应用程序数据文件的事务日志</span><span class="sxs-lookup"><span data-stu-id="56f8e-149">Transaction log for Call Park application data file</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56f8e-150">Rgsconfig</span><span class="sxs-lookup"><span data-stu-id="56f8e-150">Rgsconfig.mdf</span></span></p></td>
<td><p><span data-ttu-id="56f8e-151">用于配置服务的 Lync Server 响应组服务数据文件</span><span class="sxs-lookup"><span data-stu-id="56f8e-151">Lync Server Response Group service data file for the configuration of the services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56f8e-152">Rgsconfig</span><span class="sxs-lookup"><span data-stu-id="56f8e-152">Rgsconfig.ldf</span></span></p></td>
<td><p><span data-ttu-id="56f8e-153">响应组应用程序配置的事务日志文件</span><span class="sxs-lookup"><span data-stu-id="56f8e-153">Transaction log file for the Response Group application configuration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56f8e-154">Rgsdyn</span><span class="sxs-lookup"><span data-stu-id="56f8e-154">Rgsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="56f8e-155">运行时操作的响应组服务数据文件</span><span class="sxs-lookup"><span data-stu-id="56f8e-155">Response Group service data file for runtime operations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56f8e-156">Rgsdyn</span><span class="sxs-lookup"><span data-stu-id="56f8e-156">Rgsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="56f8e-157">响应组服务运行时数据文件的事务日志</span><span class="sxs-lookup"><span data-stu-id="56f8e-157">Transaction log for the Response Group service runtime data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a><span data-ttu-id="56f8e-158">存档和监控服务器的数据和日志文件</span><span class="sxs-lookup"><span data-stu-id="56f8e-158">Data and Log Files for Archiving and Monitoring Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="56f8e-159">存档和监控数据库文件</span><span class="sxs-lookup"><span data-stu-id="56f8e-159">Archiving and Monitoring database files</span></span></th>
<th><span data-ttu-id="56f8e-160">用于数据文件或日志</span><span class="sxs-lookup"><span data-stu-id="56f8e-160">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56f8e-161">LcsCdr</span><span class="sxs-lookup"><span data-stu-id="56f8e-161">LcsCdr.mdf</span></span></p></td>
<td><p><span data-ttu-id="56f8e-162">监视服务器 (CDR) 流程的呼叫详细信息记录的数据存储</span><span class="sxs-lookup"><span data-stu-id="56f8e-162">Data store for the call detail recording (CDR) process of the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56f8e-163">LcsCdr</span><span class="sxs-lookup"><span data-stu-id="56f8e-163">LcsCdr.ldf</span></span></p></td>
<td><p><span data-ttu-id="56f8e-164">呼叫详细信息记录 (CDR) 数据的事务日志</span><span class="sxs-lookup"><span data-stu-id="56f8e-164">Transaction log for call detail recording (CDR) data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56f8e-165">QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="56f8e-165">QoEMetrics.mdf</span></span></p></td>
<td><p><span data-ttu-id="56f8e-166">从监视服务器存储的经验数据文件的质量</span><span class="sxs-lookup"><span data-stu-id="56f8e-166">Quality of Experience data file stored from the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56f8e-167">QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="56f8e-167">QoEMetrics.ldf</span></span></p></td>
<td><p><span data-ttu-id="56f8e-168">监控数据的事务日志</span><span class="sxs-lookup"><span data-stu-id="56f8e-168">Transaction log for Monitoring data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56f8e-169">Lcslog</span><span class="sxs-lookup"><span data-stu-id="56f8e-169">Lcslog.mdf</span></span></p></td>
<td><p><span data-ttu-id="56f8e-170">存档服务器上的即时消息和会议数据的保留数据文件</span><span class="sxs-lookup"><span data-stu-id="56f8e-170">Data file for the retention of instant messaging and conferencing data on an Archiving Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56f8e-171">Lcslog</span><span class="sxs-lookup"><span data-stu-id="56f8e-171">Lcslog.ldf</span></span></p></td>
<td><p><span data-ttu-id="56f8e-172">为数据存档的事务日志</span><span class="sxs-lookup"><span data-stu-id="56f8e-172">Transaction log for Archiving data</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="56f8e-p103">本主题引用了磁盘和 RAID 集的相关内容。请注意，SQL Server 资源配置中提及的磁盘表示单个硬件设备。硬盘驱动器包括两个分区，一个分区保存日志文件，另一个分区保存数据文件，这与有两个磁盘，每个磁盘专用于存储日志或数据文件的情况不同。</span><span class="sxs-lookup"><span data-stu-id="56f8e-p103">In this topic, references are made to disk and to RAID set. Note that in the configuration of SQL Server resources, referring to a disk means a single hardware device. A hard disk drive with two partitions, one holding log files and the other partition holding data files, is not the same as two disks, each dedicated to either log or data files.</span></span>

<span data-ttu-id="56f8e-176">谈到 RAID 集，不同的供应商提供了几种不同的 RAID 技术。</span><span class="sxs-lookup"><span data-stu-id="56f8e-176">In reference to RAID sets, there are a number of different RAID technologies from various vendors.</span></span> <span data-ttu-id="56f8e-177">并且，随着存储区域网络 (SAN) 的扩展，专用于单个系统的 RAID 集越来越少。</span><span class="sxs-lookup"><span data-stu-id="56f8e-177">And, with the proliferation of storage area networks (SAN), RAID sets dedicated to a single system are rarer.</span></span> <span data-ttu-id="56f8e-178">在使用 Lync Server 2013 配置 SQL Server 性能时，应咨询你的 RAID 或 SAN 供应商，以确定您的磁盘布局的最佳配置。</span><span class="sxs-lookup"><span data-stu-id="56f8e-178">You should consult with your RAID or SAN vendor to determine what the best configuration is for your disk layout when configuring for SQL Server performance with Lync Server 2013.</span></span>

<span data-ttu-id="56f8e-179">另请注意，创建的磁盘驱动器的性能可能各不相同，一些磁盘驱动器的性能优于其他磁盘驱动器。</span><span class="sxs-lookup"><span data-stu-id="56f8e-179">Note also that not all disk drives are created equally; some perform better than others.</span></span> <span data-ttu-id="56f8e-180">由于转速、硬件缓存大小以及其他因素，即使是同一制造商的驱动器的性能也会有所不同。</span><span class="sxs-lookup"><span data-stu-id="56f8e-180">Even drives from the same manufacturer can vary in performance because of rotational speed, hardware cache size, and other factors.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

