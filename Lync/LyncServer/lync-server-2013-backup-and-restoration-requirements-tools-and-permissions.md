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
ms.openlocfilehash: b86f283aae05985ea903a17dfb15dff83574c42f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029213"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a>Lync Server 2013 中的备份和还原要求：工具和权限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-17_

本主题介绍可用于备份和还原 Lync Server 2013 的工具、所需的权限以及是否可以远程或在本地运行命令。 具体来说，本主题重点介绍了随 Lync Server 提供的用于备份和还原的工具。

<div>

## <a name="backups"></a>备份

若要备份 Lync Server，请使用下表中指出的工具。 您需要备份 Lync Server 的所有命令都可以编写脚本，并且可以远程运行。

### <a name="tools-for-backing-up-lync-server"></a>用于备份 Lync Server 的工具

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>备份以下内容：</th>
<th>使用以下工具或 cmdlet：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>拓扑配置数据 (Xds.mdf)</p></td>
<td><p>Export-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>位置信息服务 (E9-1-1) 数据 (Lis.mdf)</p></td>
<td><p>Export-CsLisConfiguration</p></td>
</tr>
<tr class="odd">
<td><p>响应组配置数据 (RgsConfig.mdf)</p></td>
<td><p>Export-CsRgsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>持久性用户数据（Rtcxds 数据库）</p>
<p>会议 ID</p></td>
<td><p>Export-Export-csuserdata</p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p>存档数据库 (LcsLog.mdf)</p></li>
<li><p>监控呼叫详细信息记录数据库 (LcsCDR.mdf)</p></li>
<li><p>监控 QoE 数据库 (QoEMetrics.mdf)</p></li>
</ul></td>
<td><p>SQL Server 数据库工具，例如 SQL Server Management Studio</p></td>
</tr>
<tr class="even">
<td><p>持久聊天数据库（Mgc）</p></td>
<td><p>SQL Server 备份过程或 Export-cspersistentchatdata。 Export-Export-cspersistentchatdata 将持久聊天数据导出为文件。</p></td>
</tr>
<tr class="odd">
<td><p>所有文件存储： Lync Server 文件存储、存档文件存储</p>
<div>

> [!NOTE]  
> 名为 <STRONG>Meeting.Active</STRONG> 的文件不应进行备份。 在召开会议时，会使用并锁定这些文件。


</div></td>
<td><p>标准文件系统管理工具，如 Robocopy。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a>之

若要还原 Lync Server，请使用下表中的工具。 可以为还原 Lync Server 所需的所有命令编写脚本。 有些可远程运行，但其他一些需要在本地运行，如下表所示。

### <a name="tools-for-restoring-lync-server"></a>用于还原 Lync Server 的工具

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>为执行此操作：</th>
<th>使用以下工具或 cmdlet：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>构建新的或未受感染的计算机</p></td>
<td><ul>
<li><p>Windows 操作系统安装软件</p></li>
<li><p>SQL Server 安装软件</p></li>
<li><p>证书 Microsoft 管理控制台 (MMC) 管理单元（如果使用可导出的私钥还原证书）</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>还原文件存储数据</p></td>
<td><p>标准文件系统管理工具，例如 Robocopy</p></td>
</tr>
<tr class="odd">
<td><p>重新创建空数据库，并设置以下权限：</p>
<ul>
<li><p>中央管理存储</p></li>
<li><p>后端服务器</p></li>
<li><p>监控数据库</p></li>
<li><p>存档数据库</p></li>
</ul></td>
<td><p>Install-CsDatabase</p></td>
</tr>
<tr class="even">
<td><p>将 Active Directory 域服务指针还原到中央管理存储</p>
<div>

> [!NOTE]  
> 如果在任何时候丢失服务连接点，则可重新运行该 cmdlet。


</div></td>
<td><p>CsConfigurationStoreLocation</p></td>
</tr>
<tr class="odd">
<td><p>将拓扑、策略和配置设置导入到中央管理存储（Xds）</p></td>
<td><p>Import-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>发布和启用拓扑</p></td>
<td><p>拓扑生成器</p>
<p>- 或 -</p>
<p>发布-Enable-cstopology 和 Enable-Enable-cstopology</p></td>
</tr>
<tr class="odd">
<td><p>启用上一次发布的拓扑</p></td>
<td><p>Enable-Enable-cstopology</p></td>
</tr>
<tr class="even">
<td><p>重新安装 Lync Server 组件</p></td>
<td><p>Lync Server 安装程序</p>
<div>

> [!NOTE]  
> 位于 \setup\amd64\Setup.exe. 的 Lync Server 安装文件夹或媒体中


</div></td>
</tr>
<tr class="odd">
<td><p>还原位置信息 (E9-1-1) 数据 (Lis.mdf)</p></td>
<td><p>Import-CsLisConfiguration</p></td>
</tr>
<tr class="even">
<td><p>还原永久性用户数据（Rtcxds）</p></td>
<td><p>Import-Export-csuserdata</p></td>
</tr>
<tr class="odd">
<td><p>还原响应组配置数据 (RgsConfig.mdf)</p></td>
<td><p>Import-CsRgsConfiguration</p>
<div>

> [!NOTE]  
> 如果要在数据库中没有响应组数据的新部署的池中还原配置，则应使用– OverwriteOwner 选项。 即使要还原的数据位于具有相同完全限定域名（FQDN）的池中，也可使用此选项。 否则，导入将不会成功，原因是 Active Directory 中已存在响应组的联系人对象。


</div></td>
</tr>
<tr class="even">
<td><p>还原以下数据库：</p>
<ul>
<li><p>存档数据库 (LcsLog.mdf)</p></li>
<li><p>监控数据库：呼叫详细信息记录数据库 (LcsCDR.mdf) 和 QoE 数据库 (QoEMetrics.mdf)</p></li>
</ul></td>
<td><p>SQL Server 数据库管理工具</p></td>
</tr>
<tr class="odd">
<td><p>持久聊天数据库（Mgs）</p></td>
<td><p>SQL Server 还原过程或 Export-cspersistentchatdata。 可以将 Export-cspersistentchatdata 与由 Export Export-cspersistentchatdata 创建的文件结合使用，并将数据导入到持久聊天数据库中。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a>所需权限

用户必须是**RTCUniversalServerAdmins**组的成员，才能执行本主题中所述的所有命令。 大多数备份和还原命令不支持基于角色的访问控制（RBAC）。 两个例外是持久的聊天 cmdlet Export-cspersistentchatdata 和 Export-cspersistentchatdata，它必须由作为 CsPersistentChatAdministrator 组成员的用户运行。 若要运行 Lync Server 部署向导，用户还必须是本地管理员组的成员。

</div>

</div>

<span> </span>

</div>

</div>

</div>

