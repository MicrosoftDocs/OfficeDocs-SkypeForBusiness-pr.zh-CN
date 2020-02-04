---
title: Lync Server 2013：备份和还原要求：工具和权限
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
ms.openlocfilehash: ea5e4ce57e61be50bfd1e2a78529830b4a40e3ed
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a><span data-ttu-id="fcc40-102">Lync Server 2013 中的备份和还原要求：工具和权限</span><span class="sxs-lookup"><span data-stu-id="fcc40-102">Backup and restoration requirements in Lync Server 2013: tools and permissions</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fcc40-103">_**主题上次修改时间：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="fcc40-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="fcc40-104">本主题介绍可用于备份和还原 Lync Server 2013 的工具、所需权限以及是否可以远程或本地运行命令。</span><span class="sxs-lookup"><span data-stu-id="fcc40-104">This topic identifies the tools that you can use to back up and restore Lync Server 2013, the permissions that you need, and whether you can run commands remotely or locally.</span></span> <span data-ttu-id="fcc40-105">具体地说，本主题重点介绍 Lync Server 提供的用于备份和还原的工具。</span><span class="sxs-lookup"><span data-stu-id="fcc40-105">Specifically, this topic focuses on tools that are provided with Lync Server for backup and restoration.</span></span>

<div>

## <a name="backups"></a><span data-ttu-id="fcc40-106">量</span><span class="sxs-lookup"><span data-stu-id="fcc40-106">Backups</span></span>

<span data-ttu-id="fcc40-107">若要备份 Lync Server，请使用下表中标识的工具。</span><span class="sxs-lookup"><span data-stu-id="fcc40-107">To back up Lync Server, use the tools identified in the following table.</span></span> <span data-ttu-id="fcc40-108">您需要用于备份 Lync 服务器的所有命令都可以编写脚本，并且可以远程运行。</span><span class="sxs-lookup"><span data-stu-id="fcc40-108">All the commands that you need to back up Lync Server can be scripted and can be run remotely.</span></span>

### <a name="tools-for-backing-up-lync-server"></a><span data-ttu-id="fcc40-109">用于备份 Lync Server 的工具</span><span class="sxs-lookup"><span data-stu-id="fcc40-109">Tools for Backing Up Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fcc40-110">若要备份，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fcc40-110">To back up this:</span></span></th>
<th><span data-ttu-id="fcc40-111">使用此工具或 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="fcc40-111">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fcc40-112">拓扑配置数据（Xds）</span><span class="sxs-lookup"><span data-stu-id="fcc40-112">Topology configuration data (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="fcc40-113">Export-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="fcc40-113">Export-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcc40-114">位置信息服务（E9-1）数据（.Lis）数据（.Lis）</span><span class="sxs-lookup"><span data-stu-id="fcc40-114">Location information service (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="fcc40-115">Export-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="fcc40-115">Export-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcc40-116">响应组配置数据（RgsConfig）</span><span class="sxs-lookup"><span data-stu-id="fcc40-116">Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="fcc40-117">Export-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="fcc40-117">Export-CsRgsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcc40-118">永久性用户数据（Rtcxds 数据库）</span><span class="sxs-lookup"><span data-stu-id="fcc40-118">Persistent user data (Rtcxds.mdf database)</span></span></p>
<p><span data-ttu-id="fcc40-119">会议 Id</span><span class="sxs-lookup"><span data-stu-id="fcc40-119">Conference IDs</span></span></p></td>
<td><p><span data-ttu-id="fcc40-120">Export-CsUserData</span><span class="sxs-lookup"><span data-stu-id="fcc40-120">Export-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="fcc40-121">存档数据库（LcsLog）</span><span class="sxs-lookup"><span data-stu-id="fcc40-121">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="fcc40-122">监视通话详细信息记录数据库（LcsCDR）</span><span class="sxs-lookup"><span data-stu-id="fcc40-122">Monitoring call detail record database (LcsCDR.mdf)</span></span></p></li>
<li><p><span data-ttu-id="fcc40-123">监视 QoE 数据库（QoEMetrics）</span><span class="sxs-lookup"><span data-stu-id="fcc40-123">Monitoring QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="fcc40-124">SQL Server 数据库工具，例如 SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fcc40-124">SQL Server database tool, such as SQL Server Management Studio</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcc40-125">持久聊天数据库（Mgc）</span><span class="sxs-lookup"><span data-stu-id="fcc40-125">Persistent Chat database (Mgc.mdf)</span></span></p></td>
<td><p><span data-ttu-id="fcc40-126">SQL Server 备份过程或导出-CsPersistentChatData。</span><span class="sxs-lookup"><span data-stu-id="fcc40-126">SQL Server backup procedures or Export-CsPersistentChatData.</span></span> <span data-ttu-id="fcc40-127">Export-CsPersistentChatData 将永久聊天数据导出为文件。</span><span class="sxs-lookup"><span data-stu-id="fcc40-127">Export-CsPersistentChatData exports Persistent Chat data as a file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcc40-128">所有文件存储： Lync Server 文件存储、存档文件存储</span><span class="sxs-lookup"><span data-stu-id="fcc40-128">All file stores: Lync Server file store, Archiving file store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="fcc40-129">名为 "<STRONG>会议" 的</STRONG>文件不应备份。</span><span class="sxs-lookup"><span data-stu-id="fcc40-129">Files named <STRONG>Meeting.Active</STRONG> should not be backed up.</span></span> <span data-ttu-id="fcc40-130">这些文件正在使用中，并且在召开会议时被锁定。</span><span class="sxs-lookup"><span data-stu-id="fcc40-130">These files are in use and locked while a meeting takes place.</span></span>


</div></td>
<td><p><span data-ttu-id="fcc40-131">标准文件系统管理工具，例如 Robocopy。</span><span class="sxs-lookup"><span data-stu-id="fcc40-131">Standard file system management tool, such as Robocopy.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a><span data-ttu-id="fcc40-132">还原</span><span class="sxs-lookup"><span data-stu-id="fcc40-132">Restoration</span></span>

<span data-ttu-id="fcc40-133">若要还原 Lync Server，请使用下表中的工具。</span><span class="sxs-lookup"><span data-stu-id="fcc40-133">To restore Lync Server, use the tools in the following table.</span></span> <span data-ttu-id="fcc40-134">可以为还原 Lync Server 所需的所有命令编写脚本。</span><span class="sxs-lookup"><span data-stu-id="fcc40-134">All the commands that you need to restore Lync Server can be scripted.</span></span> <span data-ttu-id="fcc40-135">有些可以远程运行，但其他人需要在下表中指定的本地运行。</span><span class="sxs-lookup"><span data-stu-id="fcc40-135">Some can be run remotely, but others need to be run locally, as specified in the following table.</span></span>

### <a name="tools-for-restoring-lync-server"></a><span data-ttu-id="fcc40-136">用于还原 Lync Server 的工具</span><span class="sxs-lookup"><span data-stu-id="fcc40-136">Tools for Restoring Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fcc40-137">要执行此操作：</span><span class="sxs-lookup"><span data-stu-id="fcc40-137">To do this:</span></span></th>
<th><span data-ttu-id="fcc40-138">使用此工具或 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="fcc40-138">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fcc40-139">构建新的或全新的计算机</span><span class="sxs-lookup"><span data-stu-id="fcc40-139">Build a new or clean computer</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="fcc40-140">Windows 操作系统安装软件</span><span class="sxs-lookup"><span data-stu-id="fcc40-140">Windows operating system installation software</span></span></p></li>
<li><p><span data-ttu-id="fcc40-141">SQL Server 安装软件</span><span class="sxs-lookup"><span data-stu-id="fcc40-141">SQL Server installation software</span></span></p></li>
<li><p><span data-ttu-id="fcc40-142">证书 Microsoft 管理控制台（MMC）管理单元（如果使用可导出私钥还原证书）</span><span class="sxs-lookup"><span data-stu-id="fcc40-142">Certificates Microsoft Management Console (MMC) snap-in, if restoring certificates with an exportable private key</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcc40-143">还原文件存储数据</span><span class="sxs-lookup"><span data-stu-id="fcc40-143">Restore file store data</span></span></p></td>
<td><p><span data-ttu-id="fcc40-144">标准文件系统管理工具，例如 Robocopy</span><span class="sxs-lookup"><span data-stu-id="fcc40-144">Standard file system management tool, such as Robocopy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcc40-145">重新创建空数据库并为以下项设置权限：</span><span class="sxs-lookup"><span data-stu-id="fcc40-145">Recreate empty databases and set permissions for the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fcc40-146">中央管理存储</span><span class="sxs-lookup"><span data-stu-id="fcc40-146">Central Management store</span></span></p></li>
<li><p><span data-ttu-id="fcc40-147">后端服务器</span><span class="sxs-lookup"><span data-stu-id="fcc40-147">Back End Server</span></span></p></li>
<li><p><span data-ttu-id="fcc40-148">监控数据库</span><span class="sxs-lookup"><span data-stu-id="fcc40-148">Monitoring database</span></span></p></li>
<li><p><span data-ttu-id="fcc40-149">存档数据库</span><span class="sxs-lookup"><span data-stu-id="fcc40-149">Archiving database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="fcc40-150">Install-CsDatabase</span><span class="sxs-lookup"><span data-stu-id="fcc40-150">Install-CsDatabase</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcc40-151">将 Active Directory 域服务指针还原到中央管理存储</span><span class="sxs-lookup"><span data-stu-id="fcc40-151">Restore the Active Directory Domain Services pointer to the Central Management store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="fcc40-152">如果您随时失去服务连接点，则可以重新运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fcc40-152">If you lose the service connection point at any time, you can rerun this cmdlet.</span></span>


</div></td>
<td><p><span data-ttu-id="fcc40-153">Set-CsConfigurationStoreLocation</span><span class="sxs-lookup"><span data-stu-id="fcc40-153">Set-CsConfigurationStoreLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcc40-154">将拓扑、策略和配置设置导入中央管理存储（Xds）</span><span class="sxs-lookup"><span data-stu-id="fcc40-154">Import the topology, policies, and configuration settings to the Central Management store (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="fcc40-155">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="fcc40-155">Import-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcc40-156">发布和启用拓扑</span><span class="sxs-lookup"><span data-stu-id="fcc40-156">Publish and enable the topology</span></span></p></td>
<td><p><span data-ttu-id="fcc40-157">拓扑生成器</span><span class="sxs-lookup"><span data-stu-id="fcc40-157">Topology Builder</span></span></p>
<p><span data-ttu-id="fcc40-158">或</span><span class="sxs-lookup"><span data-stu-id="fcc40-158">-or-</span></span></p>
<p><span data-ttu-id="fcc40-159">发布-CsTopology 和 Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="fcc40-159">Publish-CsTopology and Enable-CsTopology</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcc40-160">启用上次发布的拓扑</span><span class="sxs-lookup"><span data-stu-id="fcc40-160">Enable the last published topology</span></span></p></td>
<td><p><span data-ttu-id="fcc40-161">Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="fcc40-161">Enable-CsTopology</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcc40-162">重新安装 Lync Server 组件</span><span class="sxs-lookup"><span data-stu-id="fcc40-162">Reinstall Lync Server components</span></span></p></td>
<td><p><span data-ttu-id="fcc40-163">Lync Server 安装程序</span><span class="sxs-lookup"><span data-stu-id="fcc40-163">Lync Server Setup</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="fcc40-164">位于 \setup\amd64\Setup.exe. 中的 Lync Server 安装文件夹或媒体中</span><span class="sxs-lookup"><span data-stu-id="fcc40-164">Located in the Lync Server installation folder or media at \setup\amd64\Setup.exe.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcc40-165">还原位置信息（E9-1）数据（.Lis）数据（.Lis）</span><span class="sxs-lookup"><span data-stu-id="fcc40-165">Restore location information (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="fcc40-166">Import-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="fcc40-166">Import-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcc40-167">还原永久性用户数据（Rtcxds）</span><span class="sxs-lookup"><span data-stu-id="fcc40-167">Restore persistent user data (Rtcxds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="fcc40-168">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="fcc40-168">Import-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcc40-169">还原响应组配置数据（RgsConfig）</span><span class="sxs-lookup"><span data-stu-id="fcc40-169">Restore Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="fcc40-170">Import-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="fcc40-170">Import-CsRgsConfiguration</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="fcc40-171">如果在数据库中没有响应组数据的新部署的池中还原配置，则应使用– OverwriteOwner 选项。</span><span class="sxs-lookup"><span data-stu-id="fcc40-171">If the configuration is being restored in a newly deployed pool that has no Response Group data in the database, then you should use the –OverwriteOwner option.</span></span> <span data-ttu-id="fcc40-172">即使正在还原的数据位于具有相同的完全限定的域名（FQDN）的池中，也可使用此选项。</span><span class="sxs-lookup"><span data-stu-id="fcc40-172">Use this option even if the data being restored is in a pool with the same fully qualified domain name (FQDN).</span></span> <span data-ttu-id="fcc40-173">否则，导入将不会成功，原因是 Active Directory 中已存在对响应组的联系人对象。</span><span class="sxs-lookup"><span data-stu-id="fcc40-173">Otherwise, the import will not succeed, due to the contact objects to the Response Groups already existing in Active Directory.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcc40-174">还原以下数据库：</span><span class="sxs-lookup"><span data-stu-id="fcc40-174">Restore the following databases:</span></span></p>
<ul>
<li><p><span data-ttu-id="fcc40-175">存档数据库（LcsLog）</span><span class="sxs-lookup"><span data-stu-id="fcc40-175">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="fcc40-176">监视数据库：调用详细信息记录数据库（LcsCDR）和 QoE 数据库（QoEMetrics）</span><span class="sxs-lookup"><span data-stu-id="fcc40-176">Monitoring databases: call detail record database (LcsCDR.mdf) and QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="fcc40-177">SQL Server 数据库管理工具</span><span class="sxs-lookup"><span data-stu-id="fcc40-177">SQL Server database management tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcc40-178">持久聊天数据库（Mgs）</span><span class="sxs-lookup"><span data-stu-id="fcc40-178">Persistent Chat database (Mgs.mdf)</span></span></p></td>
<td><p><span data-ttu-id="fcc40-179">SQL Server 还原过程或导入-CsPersistentChatData。</span><span class="sxs-lookup"><span data-stu-id="fcc40-179">SQL Server restore procedures or Import-CsPersistentChatData.</span></span> <span data-ttu-id="fcc40-180">你可以将 Import CsPersistentChatData 与由导出 CsPersistentChatData 创建的文件结合使用，并将数据导入持久聊天数据库。</span><span class="sxs-lookup"><span data-stu-id="fcc40-180">You can use Import-CsPersistentChatData with a file created by Export-CsPersistentChatData, and the data will be imported into the Persistent Chat database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a><span data-ttu-id="fcc40-181">所需权限</span><span class="sxs-lookup"><span data-stu-id="fcc40-181">Required Permissions</span></span>

<span data-ttu-id="fcc40-182">用户必须是**RTCUniversalServerAdmins**组的成员才能执行本主题中所述的所有命令。</span><span class="sxs-lookup"><span data-stu-id="fcc40-182">Users must be a member of the **RTCUniversalServerAdmins** group to perform all the commands described in this topic.</span></span> <span data-ttu-id="fcc40-183">大多数备份和还原命令不支持基于角色的访问控制（RBAC）。</span><span class="sxs-lookup"><span data-stu-id="fcc40-183">Most backup and restore commands do not support role-based access control (RBAC).</span></span> <span data-ttu-id="fcc40-184">两个例外是持久的聊天 cmdlet CsPersistentChatData 和 Import-CsPersistentChatData，它必须由属于 CsPersistentChatAdministrator 组成员的用户运行。</span><span class="sxs-lookup"><span data-stu-id="fcc40-184">Two exceptions are the Persistent Chat cmdlets Export-CsPersistentChatData and Import-CsPersistentChatData, which must be run by a user who is a member of the CsPersistentChatAdministrator group.</span></span> <span data-ttu-id="fcc40-185">若要运行 Lync Server 部署向导，用户还必须是本地管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="fcc40-185">To run Lync Server Deployment Wizard, a user must also be a member of the Local Adminstrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

