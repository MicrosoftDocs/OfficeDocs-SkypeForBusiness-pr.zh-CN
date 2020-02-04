---
title: Lync Server 2013：备份和还原工作表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration worksheets
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202169(v=OCS.15)
ms:contentKeyID: 51541460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 390d6289daf8075c873e90319642f0e74b61d835
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a><span data-ttu-id="a4832-102">Lync Server 2013 的备份和还原工作表</span><span class="sxs-lookup"><span data-stu-id="a4832-102">Backup and restoration worksheets for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4832-103">_**主题上次修改时间：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="a4832-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="a4832-104">您的组织的备份和还原计划应包含有关备份数据和设置的方式和时间的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a4832-104">The backup and restoration plan for your organization should contain details about how and when you back up data and settings.</span></span> <span data-ttu-id="a4832-105">你可以使用此处介绍的工作表来帮助你为特定部署以及你的组织的备份和还原要求记录此信息。</span><span class="sxs-lookup"><span data-stu-id="a4832-105">You can use the worksheets presented here to help you document this information for your specific deployment and for your organization's backup and restoration requirements.</span></span>

<span data-ttu-id="a4832-106">使用以下工作表记录用于备份和还原 Lync Server 池或标准版服务器的数据库、文件存储和设置信息所需的信息。</span><span class="sxs-lookup"><span data-stu-id="a4832-106">Use the following worksheets to record the information that you need to back up and restore database, File Store, and settings information for a Lync Server pool or Standard Edition server.</span></span> <span data-ttu-id="a4832-107">将这些工作表的一个或多个副本保留在一个安全位置，以便在需要还原 Lync 服务器时可以随时访问它们。</span><span class="sxs-lookup"><span data-stu-id="a4832-107">Keep one or more copies of these worksheets in a secure location so that they are readily accessible if you need to restore Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a4832-108">本部分中的工作表仅涵盖还原 Lync Server 数据库和服务器的数据和设置所需的信息。</span><span class="sxs-lookup"><span data-stu-id="a4832-108">The worksheets in this section cover only the information that is required to restore the data and settings of Lync Server databases and servers.</span></span> <span data-ttu-id="a4832-109">如果需要记录其他还原信息，例如用于重新安装操作系统和其他软件的信息，请使用组织的部署计划和备份和还原计划来满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="a4832-109">If you need to document other restoration information, such as the information for reinstalling operating systems and other software, use your organization's deployment plans and backup and restoration plans to address those requirements.</span></span>



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a><span data-ttu-id="a4832-110">数据库备份和还原工作表</span><span class="sxs-lookup"><span data-stu-id="a4832-110">Database Backup and Restoration Worksheet</span></span>

<span data-ttu-id="a4832-111">使用下表记录备份和还原 Lync Server 数据库所需的信息。</span><span class="sxs-lookup"><span data-stu-id="a4832-111">Use the following table to record the information that you need to back up and restore Lync Server databases.</span></span>

### <a name="database-information-for-backup-and-restoration"></a><span data-ttu-id="a4832-112">用于备份和还原的数据库信息</span><span class="sxs-lookup"><span data-stu-id="a4832-112">Database Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4832-113">数据库</span><span class="sxs-lookup"><span data-stu-id="a4832-113">Database</span></span></th>
<th><span data-ttu-id="a4832-114">服务器名称（FQDN）</span><span class="sxs-lookup"><span data-stu-id="a4832-114">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="a4832-115">备份计划</span><span class="sxs-lookup"><span data-stu-id="a4832-115">Backup schedule</span></span></th>
<th><span data-ttu-id="a4832-116">数据库备份工具</span><span class="sxs-lookup"><span data-stu-id="a4832-116">Database backup tool</span></span></th>
<th><span data-ttu-id="a4832-117">备份集</span><span class="sxs-lookup"><span data-stu-id="a4832-117">Backup set</span></span></th>
<th><span data-ttu-id="a4832-118">备份目标</span><span class="sxs-lookup"><span data-stu-id="a4832-118">Backup destination</span></span></th>
<th><span data-ttu-id="a4832-119">注释</span><span class="sxs-lookup"><span data-stu-id="a4832-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4832-120">用户数据的后端服务器上的 Rtc 数据库</span><span class="sxs-lookup"><span data-stu-id="a4832-120">Rtc database on Back End Server for user data</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="a4832-121"><strong>Export-CsUserData</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="a4832-121"><strong>Export-CsUserData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="a4832-122">姓</span><span class="sxs-lookup"><span data-stu-id="a4832-122">Name:</span></span></p>
<p><span data-ttu-id="a4832-123">满</span><span class="sxs-lookup"><span data-stu-id="a4832-123">Expiration:</span></span></p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4832-124">存档数据库服务器上的 LcsLog （默认名称）数据库</span><span class="sxs-lookup"><span data-stu-id="a4832-124">LcsLog (default name) database on Archiving database server</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a4832-125">SQL Server 管理工具</span><span class="sxs-lookup"><span data-stu-id="a4832-125">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="a4832-126">姓</span><span class="sxs-lookup"><span data-stu-id="a4832-126">Name:</span></span></p>
<p><span data-ttu-id="a4832-127">满</span><span class="sxs-lookup"><span data-stu-id="a4832-127">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4832-128">用于针对通话详细记录（CDRs）监控数据库服务器的 LcsCdr 数据库</span><span class="sxs-lookup"><span data-stu-id="a4832-128">LcsCdr database on Monitoring database server for call detail records (CDRs)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a4832-129">SQL Server 管理工具</span><span class="sxs-lookup"><span data-stu-id="a4832-129">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="a4832-130">姓</span><span class="sxs-lookup"><span data-stu-id="a4832-130">Name:</span></span></p>
<p><span data-ttu-id="a4832-131">满</span><span class="sxs-lookup"><span data-stu-id="a4832-131">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4832-132">用于监视数据库服务器上的 QoEMetrics 数据库的体验质量（QoE）数据</span><span class="sxs-lookup"><span data-stu-id="a4832-132">QoEMetrics database on Monitoring database server for Quality of Experience (QoE) data</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a4832-133">SQL Server 管理工具</span><span class="sxs-lookup"><span data-stu-id="a4832-133">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="a4832-134">姓</span><span class="sxs-lookup"><span data-stu-id="a4832-134">Name:</span></span></p>
<p><span data-ttu-id="a4832-135">满</span><span class="sxs-lookup"><span data-stu-id="a4832-135">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4832-136">持久聊天数据库</span><span class="sxs-lookup"><span data-stu-id="a4832-136">Persistent Chat Database</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="a4832-137">SQL Server 管理工具或<strong>Export-CsPersistentChatData</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="a4832-137">SQL Server management tool or <strong>Export-CsPersistentChatData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="a4832-138">姓</span><span class="sxs-lookup"><span data-stu-id="a4832-138">Name:</span></span></p>
<p><span data-ttu-id="a4832-139">满</span><span class="sxs-lookup"><span data-stu-id="a4832-139">Expiration:</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a4832-140">不需要以下数据库的备份或还原：</span><span class="sxs-lookup"><span data-stu-id="a4832-140">No backup or restoration is required of the following databases:</span></span>

  - <span data-ttu-id="a4832-141">Rtcdyn.</span><span class="sxs-lookup"><span data-stu-id="a4832-141">Rtcdyn.</span></span> <span data-ttu-id="a4832-142">还原服务不需要此数据库中的瞬时用户数据。</span><span class="sxs-lookup"><span data-stu-id="a4832-142">The transient user data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="a4832-143">Rtcab.</span><span class="sxs-lookup"><span data-stu-id="a4832-143">Rtcab.</span></span> <span data-ttu-id="a4832-144">通讯簿数据库将从 Active Directory 域服务中的全局地址列表（GAL）自动重新创建。</span><span class="sxs-lookup"><span data-stu-id="a4832-144">The Address Book database is automatically recreated from the Global Address List (GAL) in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="a4832-145">Rgsdyn.</span><span class="sxs-lookup"><span data-stu-id="a4832-145">Rgsdyn.</span></span> <span data-ttu-id="a4832-146">还原服务不需要此数据库中的暂时性响应组服务数据。</span><span class="sxs-lookup"><span data-stu-id="a4832-146">The transient Response Group service data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="a4832-147">Cpsdyn.</span><span class="sxs-lookup"><span data-stu-id="a4832-147">Cpsdyn.</span></span> <span data-ttu-id="a4832-148">还原服务不需要调用寄存应用程序的动态信息。</span><span class="sxs-lookup"><span data-stu-id="a4832-148">The dynamic information for the Call Park application is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="a4832-149">MgcComp.</span><span class="sxs-lookup"><span data-stu-id="a4832-149">MgcComp.</span></span> <span data-ttu-id="a4832-150">用于持久聊天的合规性数据库不是还原服务所必需的。</span><span class="sxs-lookup"><span data-stu-id="a4832-150">The compliance database for Persistent Chat is not necessary for restoration of service.</span></span>

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a><span data-ttu-id="a4832-151">文件存储备份和还原工作表</span><span class="sxs-lookup"><span data-stu-id="a4832-151">File Store Backup and Restoration Worksheet</span></span>

<span data-ttu-id="a4832-152">使用下表记录备份和还原文件存储所需的信息。</span><span class="sxs-lookup"><span data-stu-id="a4832-152">Use the following table to record the information that you need to back up and restore the File Stores.</span></span> <span data-ttu-id="a4832-153">文件存储包含会议内容元数据、会议合规性日志、更新设备更新日志以及响应组的音频文件、呼叫寄存和发布应用程序等数据。</span><span class="sxs-lookup"><span data-stu-id="a4832-153">File Stores contain data such as meeting content metadata, meeting compliance logs, update logs for device updates, and audio files for the Response Group, Call Park, and Announcement applications.</span></span>

### <a name="file-store-information-for-backup-and-restoration"></a><span data-ttu-id="a4832-154">用于备份和还原的文件存储信息</span><span class="sxs-lookup"><span data-stu-id="a4832-154">File Store Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4832-155">内容</span><span class="sxs-lookup"><span data-stu-id="a4832-155">Content</span></span></th>
<th><span data-ttu-id="a4832-156">服务器名称（FQDN）</span><span class="sxs-lookup"><span data-stu-id="a4832-156">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="a4832-157">备份计划</span><span class="sxs-lookup"><span data-stu-id="a4832-157">Backup schedule</span></span></th>
<th><span data-ttu-id="a4832-158">文件系统备份工具</span><span class="sxs-lookup"><span data-stu-id="a4832-158">File system backup tool</span></span></th>
<th><span data-ttu-id="a4832-159">要备份的文件共享 \*</span><span class="sxs-lookup"><span data-stu-id="a4832-159">File share to be backed up \*</span></span></th>
<th><span data-ttu-id="a4832-160">备份目标</span><span class="sxs-lookup"><span data-stu-id="a4832-160">Backup destination</span></span></th>
<th><span data-ttu-id="a4832-161">注释</span><span class="sxs-lookup"><span data-stu-id="a4832-161">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4832-162">Lync Server 文件存储</span><span class="sxs-lookup"><span data-stu-id="a4832-162">Lync Server File Store</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="a4832-163">标准备份工具，如 Robocopy</span><span class="sxs-lookup"><span data-stu-id="a4832-163">Standard backup tool, such as Robocopy</span></span></p></td>
<td><p><span data-ttu-id="a4832-164">在 "适用于企业版的文件服务器" 上。</span><span class="sxs-lookup"><span data-stu-id="a4832-164">On file server for Enterprise Edition.</span></span> <span data-ttu-id="a4832-165">对于标准版，默认情况下为标准版部署。</span><span class="sxs-lookup"><span data-stu-id="a4832-165">On Standard Edition by default, for Standard Edition deployment.</span></span> <span data-ttu-id="a4832-166">通常，每个站点一个。</span><span class="sxs-lookup"><span data-stu-id="a4832-166">Typically, one per site.</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4832-167">名为 "<strong>会议" 的</strong>文件不应备份。</span><span class="sxs-lookup"><span data-stu-id="a4832-167">Files named <strong>Meeting.Active</strong> should not be backed up.</span></span> <span data-ttu-id="a4832-168">这些文件正在使用中，并且在会议发生时被锁定。</span><span class="sxs-lookup"><span data-stu-id="a4832-168">These files are in use and are locked while a meeting takes place.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a><span data-ttu-id="a4832-169">设置备份和还原工作表</span><span class="sxs-lookup"><span data-stu-id="a4832-169">Settings Backup and Restoration Worksheet</span></span>

<span data-ttu-id="a4832-170">使用下表记录备份和还原设置所需的信息。</span><span class="sxs-lookup"><span data-stu-id="a4832-170">Use the following table to record the information that you need to back up and restore settings.</span></span>

### <a name="settings-information-for-backup-and-restoration"></a><span data-ttu-id="a4832-171">备份和还原的设置信息</span><span class="sxs-lookup"><span data-stu-id="a4832-171">Settings Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4832-172">数据库</span><span class="sxs-lookup"><span data-stu-id="a4832-172">Database</span></span></th>
<th><span data-ttu-id="a4832-173">服务器名称（FQDN）</span><span class="sxs-lookup"><span data-stu-id="a4832-173">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="a4832-174">备份计划</span><span class="sxs-lookup"><span data-stu-id="a4832-174">Backup schedule</span></span></th>
<th><span data-ttu-id="a4832-175">备份工具</span><span class="sxs-lookup"><span data-stu-id="a4832-175">Backup tool</span></span></th>
<th><span data-ttu-id="a4832-176">配置文件（.xml）名称</span><span class="sxs-lookup"><span data-stu-id="a4832-176">Configuration file (.xml) name</span></span></th>
<th><span data-ttu-id="a4832-177">备份位置</span><span class="sxs-lookup"><span data-stu-id="a4832-177">Backup location</span></span></th>
<th><span data-ttu-id="a4832-178">注释</span><span class="sxs-lookup"><span data-stu-id="a4832-178">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4832-179">拓扑配置的中央管理存储中的 Xds 数据库（全局）</span><span class="sxs-lookup"><span data-stu-id="a4832-179">Xds database in Central Management store for topology configuration (global)</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="a4832-180"><strong>Export-CsConfiguration</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="a4832-180"><strong>Export-CsConfiguration</strong> cmdlet</span></span></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4832-181">E9 的中央管理存储中的 .lis 数据库-1-1-1 位置信息（全局）</span><span class="sxs-lookup"><span data-stu-id="a4832-181">Lis database in Central Management store for E9-1-1 location information (global)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a4832-182"><strong>Export-CsLisConfiguration</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="a4832-182"><strong>Export-CsLisConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4832-183">响应组配置的后端服务器上的 RgsConfig 数据库（池）</span><span class="sxs-lookup"><span data-stu-id="a4832-183">RgsConfig database on Back End Server for Response Group configuration (pool)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a4832-184"><strong>Export-CsRgsConfiguration</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="a4832-184"><strong>Export-CsRgsConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

