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
ms.openlocfilehash: 161a8577558705c773974b1cc733337b29b6dbd5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532619"
---
# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a><span data-ttu-id="c49e2-102">Lync Server 2013 的备份和还原工作表</span><span class="sxs-lookup"><span data-stu-id="c49e2-102">Backup and restoration worksheets for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c49e2-103">_**上次修改的主题：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="c49e2-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="c49e2-104">您的组织的备份和还原计划应包含有关如何以及何时备份数据和设置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c49e2-104">The backup and restoration plan for your organization should contain details about how and when you back up data and settings.</span></span> <span data-ttu-id="c49e2-105">您可以使用此处介绍的工作表来帮助您为特定部署记录此信息，并为您的组织的备份和还原要求提供此信息。</span><span class="sxs-lookup"><span data-stu-id="c49e2-105">You can use the worksheets presented here to help you document this information for your specific deployment and for your organization's backup and restoration requirements.</span></span>

<span data-ttu-id="c49e2-106">使用以下工作表记录备份和还原 Lync Server 池或 Standard Edition server 的数据库、文件存储和设置信息所需的信息。</span><span class="sxs-lookup"><span data-stu-id="c49e2-106">Use the following worksheets to record the information that you need to back up and restore database, File Store, and settings information for a Lync Server pool or Standard Edition server.</span></span> <span data-ttu-id="c49e2-107">将这些工作表的一个或多个副本保留在一个安全的位置，以便在需要还原 Lync Server 时可随时访问它们。</span><span class="sxs-lookup"><span data-stu-id="c49e2-107">Keep one or more copies of these worksheets in a secure location so that they are readily accessible if you need to restore Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c49e2-108">本节中的工作表仅包含还原 Lync Server 数据库和服务器的数据和设置所需的信息。</span><span class="sxs-lookup"><span data-stu-id="c49e2-108">The worksheets in this section cover only the information that is required to restore the data and settings of Lync Server databases and servers.</span></span> <span data-ttu-id="c49e2-109">如果需要记录其他还原信息（如用于重新安装操作系统和其他软件的信息），请使用贵组织的部署计划和备份和还原计划来满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="c49e2-109">If you need to document other restoration information, such as the information for reinstalling operating systems and other software, use your organization's deployment plans and backup and restoration plans to address those requirements.</span></span>



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a><span data-ttu-id="c49e2-110">数据库备份和还原工作表</span><span class="sxs-lookup"><span data-stu-id="c49e2-110">Database Backup and Restoration Worksheet</span></span>

<span data-ttu-id="c49e2-111">使用下表记录备份和还原 Lync Server 数据库时所需的信息。</span><span class="sxs-lookup"><span data-stu-id="c49e2-111">Use the following table to record the information that you need to back up and restore Lync Server databases.</span></span>

### <a name="database-information-for-backup-and-restoration"></a><span data-ttu-id="c49e2-112">备份和还原的数据库信息</span><span class="sxs-lookup"><span data-stu-id="c49e2-112">Database Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="c49e2-113">数据库</span><span class="sxs-lookup"><span data-stu-id="c49e2-113">Database</span></span></th>
<th><span data-ttu-id="c49e2-114"> (FQDN) 的服务器名称</span><span class="sxs-lookup"><span data-stu-id="c49e2-114">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="c49e2-115">备份计划</span><span class="sxs-lookup"><span data-stu-id="c49e2-115">Backup schedule</span></span></th>
<th><span data-ttu-id="c49e2-116">数据库备份工具</span><span class="sxs-lookup"><span data-stu-id="c49e2-116">Database backup tool</span></span></th>
<th><span data-ttu-id="c49e2-117">备份集</span><span class="sxs-lookup"><span data-stu-id="c49e2-117">Backup set</span></span></th>
<th><span data-ttu-id="c49e2-118">备份目标</span><span class="sxs-lookup"><span data-stu-id="c49e2-118">Backup destination</span></span></th>
<th><span data-ttu-id="c49e2-119">注释</span><span class="sxs-lookup"><span data-stu-id="c49e2-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c49e2-120">用于用户数据的后端服务器上的 Rtc 数据库</span><span class="sxs-lookup"><span data-stu-id="c49e2-120">Rtc database on Back End Server for user data</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="c49e2-121"><strong>Export-csuserdata</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="c49e2-121"><strong>Export-CsUserData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="c49e2-122">别名</span><span class="sxs-lookup"><span data-stu-id="c49e2-122">Name:</span></span></p>
<p><span data-ttu-id="c49e2-123">时间</span><span class="sxs-lookup"><span data-stu-id="c49e2-123">Expiration:</span></span></p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c49e2-124">存档数据库服务器上的 LcsLog (默认名称) 数据库</span><span class="sxs-lookup"><span data-stu-id="c49e2-124">LcsLog (default name) database on Archiving database server</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c49e2-125">SQL Server 管理工具</span><span class="sxs-lookup"><span data-stu-id="c49e2-125">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="c49e2-126">别名</span><span class="sxs-lookup"><span data-stu-id="c49e2-126">Name:</span></span></p>
<p><span data-ttu-id="c49e2-127">时间</span><span class="sxs-lookup"><span data-stu-id="c49e2-127">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c49e2-128">监视数据库服务器上的 LcsCdr 数据库中的呼叫详细信息记录 (Cdr) </span><span class="sxs-lookup"><span data-stu-id="c49e2-128">LcsCdr database on Monitoring database server for call detail records (CDRs)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c49e2-129">SQL Server 管理工具</span><span class="sxs-lookup"><span data-stu-id="c49e2-129">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="c49e2-130">别名</span><span class="sxs-lookup"><span data-stu-id="c49e2-130">Name:</span></span></p>
<p><span data-ttu-id="c49e2-131">时间</span><span class="sxs-lookup"><span data-stu-id="c49e2-131">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c49e2-132">监控数据库服务器上的 QoEMetrics 数据库的体验质量 (QoE) 数据</span><span class="sxs-lookup"><span data-stu-id="c49e2-132">QoEMetrics database on Monitoring database server for Quality of Experience (QoE) data</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c49e2-133">SQL Server 管理工具</span><span class="sxs-lookup"><span data-stu-id="c49e2-133">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="c49e2-134">别名</span><span class="sxs-lookup"><span data-stu-id="c49e2-134">Name:</span></span></p>
<p><span data-ttu-id="c49e2-135">时间</span><span class="sxs-lookup"><span data-stu-id="c49e2-135">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c49e2-136">持久聊天数据库</span><span class="sxs-lookup"><span data-stu-id="c49e2-136">Persistent Chat Database</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="c49e2-137">SQL Server 管理工具或 <strong>export-cspersistentchatdata</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="c49e2-137">SQL Server management tool or <strong>Export-CsPersistentChatData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="c49e2-138">别名</span><span class="sxs-lookup"><span data-stu-id="c49e2-138">Name:</span></span></p>
<p><span data-ttu-id="c49e2-139">时间</span><span class="sxs-lookup"><span data-stu-id="c49e2-139">Expiration:</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c49e2-140">不需要对以下数据库进行备份或还原：</span><span class="sxs-lookup"><span data-stu-id="c49e2-140">No backup or restoration is required of the following databases:</span></span>

  - <span data-ttu-id="c49e2-141">Rtcdyn.</span><span class="sxs-lookup"><span data-stu-id="c49e2-141">Rtcdyn.</span></span> <span data-ttu-id="c49e2-142">此数据库中的临时用户数据不是还原服务所必需的。</span><span class="sxs-lookup"><span data-stu-id="c49e2-142">The transient user data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="c49e2-143">Rtcab.</span><span class="sxs-lookup"><span data-stu-id="c49e2-143">Rtcab.</span></span> <span data-ttu-id="c49e2-144">通讯簿数据库将自动从 Active Directory 域服务中 (GAL) 的全局地址列表中重新创建。</span><span class="sxs-lookup"><span data-stu-id="c49e2-144">The Address Book database is automatically recreated from the Global Address List (GAL) in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="c49e2-145">Rgsdyn.</span><span class="sxs-lookup"><span data-stu-id="c49e2-145">Rgsdyn.</span></span> <span data-ttu-id="c49e2-146">此数据库中的临时响应组服务数据不是还原服务所必需的。</span><span class="sxs-lookup"><span data-stu-id="c49e2-146">The transient Response Group service data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="c49e2-147">Cpsdyn.</span><span class="sxs-lookup"><span data-stu-id="c49e2-147">Cpsdyn.</span></span> <span data-ttu-id="c49e2-148">用于呼叫寄存应用程序的动态信息不是还原服务所必需的。</span><span class="sxs-lookup"><span data-stu-id="c49e2-148">The dynamic information for the Call Park application is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="c49e2-149">MgcComp.</span><span class="sxs-lookup"><span data-stu-id="c49e2-149">MgcComp.</span></span> <span data-ttu-id="c49e2-150">用于持久聊天的合规性数据库不是还原服务所必需的。</span><span class="sxs-lookup"><span data-stu-id="c49e2-150">The compliance database for Persistent Chat is not necessary for restoration of service.</span></span>

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a><span data-ttu-id="c49e2-151">文件存储备份和还原工作表</span><span class="sxs-lookup"><span data-stu-id="c49e2-151">File Store Backup and Restoration Worksheet</span></span>

<span data-ttu-id="c49e2-152">使用下表记录备份和还原文件存储区所需的信息。</span><span class="sxs-lookup"><span data-stu-id="c49e2-152">Use the following table to record the information that you need to back up and restore the File Stores.</span></span> <span data-ttu-id="c49e2-153">文件存储区包含会议内容元数据、会议合规性日志、设备更新的更新日志以及响应组、呼叫寄存和通知应用程序的音频文件等数据。</span><span class="sxs-lookup"><span data-stu-id="c49e2-153">File Stores contain data such as meeting content metadata, meeting compliance logs, update logs for device updates, and audio files for the Response Group, Call Park, and Announcement applications.</span></span>

### <a name="file-store-information-for-backup-and-restoration"></a><span data-ttu-id="c49e2-154">用于备份和还原的文件存储信息</span><span class="sxs-lookup"><span data-stu-id="c49e2-154">File Store Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="c49e2-155">内容</span><span class="sxs-lookup"><span data-stu-id="c49e2-155">Content</span></span></th>
<th><span data-ttu-id="c49e2-156"> (FQDN) 的服务器名称</span><span class="sxs-lookup"><span data-stu-id="c49e2-156">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="c49e2-157">备份计划</span><span class="sxs-lookup"><span data-stu-id="c49e2-157">Backup schedule</span></span></th>
<th><span data-ttu-id="c49e2-158">文件系统备份工具</span><span class="sxs-lookup"><span data-stu-id="c49e2-158">File system backup tool</span></span></th>
<th><span data-ttu-id="c49e2-159">要备份的文件共享 \*</span><span class="sxs-lookup"><span data-stu-id="c49e2-159">File share to be backed up \*</span></span></th>
<th><span data-ttu-id="c49e2-160">备份目标</span><span class="sxs-lookup"><span data-stu-id="c49e2-160">Backup destination</span></span></th>
<th><span data-ttu-id="c49e2-161">注释</span><span class="sxs-lookup"><span data-stu-id="c49e2-161">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c49e2-162">Lync Server 文件存储</span><span class="sxs-lookup"><span data-stu-id="c49e2-162">Lync Server File Store</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="c49e2-163">标准备份工具，如 Robocopy</span><span class="sxs-lookup"><span data-stu-id="c49e2-163">Standard backup tool, such as Robocopy</span></span></p></td>
<td><p><span data-ttu-id="c49e2-164">在文件服务器上的 Enterprise Edition。</span><span class="sxs-lookup"><span data-stu-id="c49e2-164">On file server for Enterprise Edition.</span></span> <span data-ttu-id="c49e2-165">默认情况下为 Standard edition （针对 Standard Edition 部署）。</span><span class="sxs-lookup"><span data-stu-id="c49e2-165">On Standard Edition by default, for Standard Edition deployment.</span></span> <span data-ttu-id="c49e2-166">通常，每个站点一个。</span><span class="sxs-lookup"><span data-stu-id="c49e2-166">Typically, one per site.</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c49e2-167">名为 <strong>Meeting.Active</strong> 的文件不应进行备份。</span><span class="sxs-lookup"><span data-stu-id="c49e2-167">Files named <strong>Meeting.Active</strong> should not be backed up.</span></span> <span data-ttu-id="c49e2-168">这些文件正在使用，并在会议发生时被锁定。</span><span class="sxs-lookup"><span data-stu-id="c49e2-168">These files are in use and are locked while a meeting takes place.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a><span data-ttu-id="c49e2-169">设置备份和还原工作表</span><span class="sxs-lookup"><span data-stu-id="c49e2-169">Settings Backup and Restoration Worksheet</span></span>

<span data-ttu-id="c49e2-170">使用下表可记录备份和还原设置所需的信息。</span><span class="sxs-lookup"><span data-stu-id="c49e2-170">Use the following table to record the information that you need to back up and restore settings.</span></span>

### <a name="settings-information-for-backup-and-restoration"></a><span data-ttu-id="c49e2-171">备份和还原的设置信息</span><span class="sxs-lookup"><span data-stu-id="c49e2-171">Settings Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="c49e2-172">数据库</span><span class="sxs-lookup"><span data-stu-id="c49e2-172">Database</span></span></th>
<th><span data-ttu-id="c49e2-173"> (FQDN) 的服务器名称</span><span class="sxs-lookup"><span data-stu-id="c49e2-173">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="c49e2-174">备份计划</span><span class="sxs-lookup"><span data-stu-id="c49e2-174">Backup schedule</span></span></th>
<th><span data-ttu-id="c49e2-175">备份工具</span><span class="sxs-lookup"><span data-stu-id="c49e2-175">Backup tool</span></span></th>
<th><span data-ttu-id="c49e2-176">配置文件 ( .xml) 名称</span><span class="sxs-lookup"><span data-stu-id="c49e2-176">Configuration file (.xml) name</span></span></th>
<th><span data-ttu-id="c49e2-177">备份位置</span><span class="sxs-lookup"><span data-stu-id="c49e2-177">Backup location</span></span></th>
<th><span data-ttu-id="c49e2-178">注释</span><span class="sxs-lookup"><span data-stu-id="c49e2-178">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c49e2-179">用于拓扑配置 (全局) 的中央管理存储中的 Xds 数据库</span><span class="sxs-lookup"><span data-stu-id="c49e2-179">Xds database in Central Management store for topology configuration (global)</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="c49e2-180"><strong>CsConfiguration</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="c49e2-180"><strong>Export-CsConfiguration</strong> cmdlet</span></span></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c49e2-181">E9 的中央管理存储中的 .lis 数据库-1-1 位置信息 (全局) </span><span class="sxs-lookup"><span data-stu-id="c49e2-181">Lis database in Central Management store for E9-1-1 location information (global)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c49e2-182"><strong>CsLisConfiguration</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="c49e2-182"><strong>Export-CsLisConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c49e2-183"> (池) 的后端服务器上的 RgsConfig 数据库的响应组配置</span><span class="sxs-lookup"><span data-stu-id="c49e2-183">RgsConfig database on Back End Server for Response Group configuration (pool)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c49e2-184"><strong>CsRgsConfiguration</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="c49e2-184"><strong>Export-CsRgsConfiguration</strong> cmdlet</span></span></p></td>
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

