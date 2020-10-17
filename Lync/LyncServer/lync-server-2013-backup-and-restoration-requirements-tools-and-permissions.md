---
title: Lync Server 2013：备份和还原要求：工具和权限
description: Lync Server 2013：备份和还原要求：工具和权限。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: tools and permissions'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202171(v=OCS.15)
ms:contentKeyID: 51541465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36327d1214854586b44024f126bbd87acad6c4b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553460"
---
# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a><span data-ttu-id="33203-103">Lync Server 2013 中的备份和还原要求：工具和权限</span><span class="sxs-lookup"><span data-stu-id="33203-103">Backup and restoration requirements in Lync Server 2013: tools and permissions</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33203-104">_**上次修改的主题：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="33203-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="33203-105">本主题介绍可用于备份和还原 Lync Server 2013 的工具、所需的权限以及是否可以远程或在本地运行命令。</span><span class="sxs-lookup"><span data-stu-id="33203-105">This topic identifies the tools that you can use to back up and restore Lync Server 2013, the permissions that you need, and whether you can run commands remotely or locally.</span></span> <span data-ttu-id="33203-106">具体来说，本主题重点介绍了随 Lync Server 提供的用于备份和还原的工具。</span><span class="sxs-lookup"><span data-stu-id="33203-106">Specifically, this topic focuses on tools that are provided with Lync Server for backup and restoration.</span></span>

<div>

## <a name="backups"></a><span data-ttu-id="33203-107">备份</span><span class="sxs-lookup"><span data-stu-id="33203-107">Backups</span></span>

<span data-ttu-id="33203-108">若要备份 Lync Server，请使用下表中指出的工具。</span><span class="sxs-lookup"><span data-stu-id="33203-108">To back up Lync Server, use the tools identified in the following table.</span></span> <span data-ttu-id="33203-109">您需要备份 Lync Server 的所有命令都可以编写脚本，并且可以远程运行。</span><span class="sxs-lookup"><span data-stu-id="33203-109">All the commands that you need to back up Lync Server can be scripted and can be run remotely.</span></span>

### <a name="tools-for-backing-up-lync-server"></a><span data-ttu-id="33203-110">用于备份 Lync Server 的工具</span><span class="sxs-lookup"><span data-stu-id="33203-110">Tools for Backing Up Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="33203-111">备份以下内容：</span><span class="sxs-lookup"><span data-stu-id="33203-111">To back up this:</span></span></th>
<th><span data-ttu-id="33203-112">使用以下工具或 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="33203-112">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33203-113">拓扑配置数据 (Xds.mdf)</span><span class="sxs-lookup"><span data-stu-id="33203-113">Topology configuration data (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="33203-114">Export-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="33203-114">Export-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33203-115">位置信息服务 (E9-1-1) 数据 (Lis.mdf)</span><span class="sxs-lookup"><span data-stu-id="33203-115">Location information service (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="33203-116">Export-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="33203-116">Export-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33203-117">响应组配置数据 (RgsConfig.mdf)</span><span class="sxs-lookup"><span data-stu-id="33203-117">Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="33203-118">Export-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="33203-118">Export-CsRgsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33203-119">永久性用户数据 (Rtcxds 数据库) </span><span class="sxs-lookup"><span data-stu-id="33203-119">Persistent user data (Rtcxds.mdf database)</span></span></p>
<p><span data-ttu-id="33203-120">会议 ID</span><span class="sxs-lookup"><span data-stu-id="33203-120">Conference IDs</span></span></p></td>
<td><p><span data-ttu-id="33203-121">Export-CsUserData</span><span class="sxs-lookup"><span data-stu-id="33203-121">Export-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="33203-122">存档数据库 (LcsLog.mdf)</span><span class="sxs-lookup"><span data-stu-id="33203-122">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="33203-123">监控呼叫详细信息记录数据库 (LcsCDR.mdf)</span><span class="sxs-lookup"><span data-stu-id="33203-123">Monitoring call detail record database (LcsCDR.mdf)</span></span></p></li>
<li><p><span data-ttu-id="33203-124">监控 QoE 数据库 (QoEMetrics.mdf)</span><span class="sxs-lookup"><span data-stu-id="33203-124">Monitoring QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="33203-125">SQL Server 数据库工具，例如 SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="33203-125">SQL Server database tool, such as SQL Server Management Studio</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33203-126">持久聊天数据库 (Mgc) </span><span class="sxs-lookup"><span data-stu-id="33203-126">Persistent Chat database (Mgc.mdf)</span></span></p></td>
<td><p><span data-ttu-id="33203-127">SQL Server 备份过程或 Export-cspersistentchatdata。</span><span class="sxs-lookup"><span data-stu-id="33203-127">SQL Server backup procedures or Export-CsPersistentChatData.</span></span> <span data-ttu-id="33203-128">Export-CsPersistentChatData 将持久聊天数据作为文件导出。</span><span class="sxs-lookup"><span data-stu-id="33203-128">Export-CsPersistentChatData exports Persistent Chat data as a file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33203-129">所有文件存储： Lync Server 文件存储、存档文件存储</span><span class="sxs-lookup"><span data-stu-id="33203-129">All file stores: Lync Server file store, Archiving file store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="33203-130">名为 <STRONG>Meeting.Active</STRONG> 的文件不应进行备份。</span><span class="sxs-lookup"><span data-stu-id="33203-130">Files named <STRONG>Meeting.Active</STRONG> should not be backed up.</span></span> <span data-ttu-id="33203-131">在召开会议时，会使用并锁定这些文件。</span><span class="sxs-lookup"><span data-stu-id="33203-131">These files are in use and locked while a meeting takes place.</span></span>


</div></td>
<td><p><span data-ttu-id="33203-132">标准文件系统管理工具，如 Robocopy。</span><span class="sxs-lookup"><span data-stu-id="33203-132">Standard file system management tool, such as Robocopy.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a><span data-ttu-id="33203-133">之</span><span class="sxs-lookup"><span data-stu-id="33203-133">Restoration</span></span>

<span data-ttu-id="33203-134">若要还原 Lync Server，请使用下表中的工具。</span><span class="sxs-lookup"><span data-stu-id="33203-134">To restore Lync Server, use the tools in the following table.</span></span> <span data-ttu-id="33203-135">可以为还原 Lync Server 所需的所有命令编写脚本。</span><span class="sxs-lookup"><span data-stu-id="33203-135">All the commands that you need to restore Lync Server can be scripted.</span></span> <span data-ttu-id="33203-136">有些可远程运行，但其他一些需要在本地运行，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="33203-136">Some can be run remotely, but others need to be run locally, as specified in the following table.</span></span>

### <a name="tools-for-restoring-lync-server"></a><span data-ttu-id="33203-137">用于还原 Lync Server 的工具</span><span class="sxs-lookup"><span data-stu-id="33203-137">Tools for Restoring Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="33203-138">为执行此操作：</span><span class="sxs-lookup"><span data-stu-id="33203-138">To do this:</span></span></th>
<th><span data-ttu-id="33203-139">使用以下工具或 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="33203-139">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33203-140">构建新的或未受感染的计算机</span><span class="sxs-lookup"><span data-stu-id="33203-140">Build a new or clean computer</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="33203-141">Windows 操作系统安装软件</span><span class="sxs-lookup"><span data-stu-id="33203-141">Windows operating system installation software</span></span></p></li>
<li><p><span data-ttu-id="33203-142">SQL Server 安装软件</span><span class="sxs-lookup"><span data-stu-id="33203-142">SQL Server installation software</span></span></p></li>
<li><p><span data-ttu-id="33203-143">证书 Microsoft 管理控制台 (MMC) 管理单元（如果使用可导出的私钥还原证书）</span><span class="sxs-lookup"><span data-stu-id="33203-143">Certificates Microsoft Management Console (MMC) snap-in, if restoring certificates with an exportable private key</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33203-144">还原文件存储数据</span><span class="sxs-lookup"><span data-stu-id="33203-144">Restore file store data</span></span></p></td>
<td><p><span data-ttu-id="33203-145">标准文件系统管理工具，例如 Robocopy</span><span class="sxs-lookup"><span data-stu-id="33203-145">Standard file system management tool, such as Robocopy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33203-146">重新创建空数据库，并设置以下权限：</span><span class="sxs-lookup"><span data-stu-id="33203-146">Recreate empty databases and set permissions for the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="33203-147">中央管理存储</span><span class="sxs-lookup"><span data-stu-id="33203-147">Central Management store</span></span></p></li>
<li><p><span data-ttu-id="33203-148">后端服务器</span><span class="sxs-lookup"><span data-stu-id="33203-148">Back End Server</span></span></p></li>
<li><p><span data-ttu-id="33203-149">监控数据库</span><span class="sxs-lookup"><span data-stu-id="33203-149">Monitoring database</span></span></p></li>
<li><p><span data-ttu-id="33203-150">存档数据库</span><span class="sxs-lookup"><span data-stu-id="33203-150">Archiving database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="33203-151">Install-CsDatabase</span><span class="sxs-lookup"><span data-stu-id="33203-151">Install-CsDatabase</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33203-152">将 Active Directory 域服务指针还原到中央管理存储</span><span class="sxs-lookup"><span data-stu-id="33203-152">Restore the Active Directory Domain Services pointer to the Central Management store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="33203-153">如果在任何时候丢失服务连接点，则可重新运行该 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="33203-153">If you lose the service connection point at any time, you can rerun this cmdlet.</span></span>


</div></td>
<td><p><span data-ttu-id="33203-154">Set-CsConfigurationStoreLocation</span><span class="sxs-lookup"><span data-stu-id="33203-154">Set-CsConfigurationStoreLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33203-155">将拓扑、策略和配置设置导入到中央管理存储中 (Xds) </span><span class="sxs-lookup"><span data-stu-id="33203-155">Import the topology, policies, and configuration settings to the Central Management store (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="33203-156">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="33203-156">Import-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33203-157">发布和启用拓扑</span><span class="sxs-lookup"><span data-stu-id="33203-157">Publish and enable the topology</span></span></p></td>
<td><p><span data-ttu-id="33203-158">拓扑生成器</span><span class="sxs-lookup"><span data-stu-id="33203-158">Topology Builder</span></span></p>
<p><span data-ttu-id="33203-159">-或者-</span><span class="sxs-lookup"><span data-stu-id="33203-159">-or-</span></span></p>
<p><span data-ttu-id="33203-160">Publish-CsTopology 和 Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="33203-160">Publish-CsTopology and Enable-CsTopology</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33203-161">启用上一次发布的拓扑</span><span class="sxs-lookup"><span data-stu-id="33203-161">Enable the last published topology</span></span></p></td>
<td><p><span data-ttu-id="33203-162">Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="33203-162">Enable-CsTopology</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33203-163">重新安装 Lync Server 组件</span><span class="sxs-lookup"><span data-stu-id="33203-163">Reinstall Lync Server components</span></span></p></td>
<td><p><span data-ttu-id="33203-164">Lync Server 安装程序</span><span class="sxs-lookup"><span data-stu-id="33203-164">Lync Server Setup</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="33203-165">位于 \setup\amd64\Setup.exe 的 Lync Server 安装文件夹或媒体中。</span><span class="sxs-lookup"><span data-stu-id="33203-165">Located in the Lync Server installation folder or media at \setup\amd64\Setup.exe.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33203-166">还原位置信息 (E9-1-1) 数据 (Lis.mdf)</span><span class="sxs-lookup"><span data-stu-id="33203-166">Restore location information (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="33203-167">Import-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="33203-167">Import-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33203-168">将永久性用户数据还原 (Rtcxds) </span><span class="sxs-lookup"><span data-stu-id="33203-168">Restore persistent user data (Rtcxds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="33203-169">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="33203-169">Import-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33203-170">还原响应组配置数据 (RgsConfig.mdf)</span><span class="sxs-lookup"><span data-stu-id="33203-170">Restore Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="33203-171">Import-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="33203-171">Import-CsRgsConfiguration</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="33203-172">如果要在数据库中没有响应组数据的新部署的池中还原配置，则应使用– OverwriteOwner 选项。</span><span class="sxs-lookup"><span data-stu-id="33203-172">If the configuration is being restored in a newly deployed pool that has no Response Group data in the database, then you should use the –OverwriteOwner option.</span></span> <span data-ttu-id="33203-173">即使要还原的数据位于具有相同完全限定域名的池中 (FQDN) ，也可使用此选项。</span><span class="sxs-lookup"><span data-stu-id="33203-173">Use this option even if the data being restored is in a pool with the same fully qualified domain name (FQDN).</span></span> <span data-ttu-id="33203-174">否则，导入将不会成功，原因是 Active Directory 中已存在响应组的联系人对象。</span><span class="sxs-lookup"><span data-stu-id="33203-174">Otherwise, the import will not succeed, due to the contact objects to the Response Groups already existing in Active Directory.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33203-175">还原以下数据库：</span><span class="sxs-lookup"><span data-stu-id="33203-175">Restore the following databases:</span></span></p>
<ul>
<li><p><span data-ttu-id="33203-176">存档数据库 (LcsLog.mdf)</span><span class="sxs-lookup"><span data-stu-id="33203-176">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="33203-177">监控数据库：呼叫详细信息记录数据库 (LcsCDR.mdf) 和 QoE 数据库 (QoEMetrics.mdf)</span><span class="sxs-lookup"><span data-stu-id="33203-177">Monitoring databases: call detail record database (LcsCDR.mdf) and QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="33203-178">SQL Server 数据库管理工具</span><span class="sxs-lookup"><span data-stu-id="33203-178">SQL Server database management tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33203-179">持久聊天数据库 (Mgs) </span><span class="sxs-lookup"><span data-stu-id="33203-179">Persistent Chat database (Mgs.mdf)</span></span></p></td>
<td><p><span data-ttu-id="33203-180">SQL Server 还原过程或 Export-cspersistentchatdata。</span><span class="sxs-lookup"><span data-stu-id="33203-180">SQL Server restore procedures or Import-CsPersistentChatData.</span></span> <span data-ttu-id="33203-181">您可以将 Import-CsPersistentChatData 与 Export-cspersistentchatdata 创建的文件结合使用，并将数据导入到持久聊天数据库中。</span><span class="sxs-lookup"><span data-stu-id="33203-181">You can use Import-CsPersistentChatData with a file created by Export-CsPersistentChatData, and the data will be imported into the Persistent Chat database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a><span data-ttu-id="33203-182">所需权限</span><span class="sxs-lookup"><span data-stu-id="33203-182">Required Permissions</span></span>

<span data-ttu-id="33203-183">用户必须是 **RTCUniversalServerAdmins** 组的成员，才能执行本主题中所述的所有命令。</span><span class="sxs-lookup"><span data-stu-id="33203-183">Users must be a member of the **RTCUniversalServerAdmins** group to perform all the commands described in this topic.</span></span> <span data-ttu-id="33203-184">大多数备份和还原命令不支持基于角色的访问控制 (RBAC) 。</span><span class="sxs-lookup"><span data-stu-id="33203-184">Most backup and restore commands do not support role-based access control (RBAC).</span></span> <span data-ttu-id="33203-185">两个例外是持久聊天 cmdlet Export-CsPersistentChatData 和 Export-cspersistentchatdata，必须由属于 CsPersistentChatAdministrator 组成员的用户运行。</span><span class="sxs-lookup"><span data-stu-id="33203-185">Two exceptions are the Persistent Chat cmdlets Export-CsPersistentChatData and Import-CsPersistentChatData, which must be run by a user who is a member of the CsPersistentChatAdministrator group.</span></span> <span data-ttu-id="33203-186">若要运行 Lync Server 部署向导，用户还必须是本地管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="33203-186">To run Lync Server Deployment Wizard, a user must also be a member of the Local Adminstrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

