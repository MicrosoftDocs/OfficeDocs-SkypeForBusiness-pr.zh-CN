---
title: 'Lync Server 2013: 备份和还原要求: 工具和权限'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Backup and restoration requirements: tools and permissions'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202171(v=OCS.15)
ms:contentKeyID: 51541465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53128d99abfd438c174b98544889781b5f29b57b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a>Lync Server 2013 中的备份和还原要求: 工具和权限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-17_

本主题介绍可用于备份和还原 Lync Server 2013 的工具、所需权限以及是否可以远程或本地运行命令。 具体地说, 本主题重点介绍 Lync Server 提供的用于备份和还原的工具。

<div>

## <a name="backups"></a>量

若要备份 Lync Server, 请使用下表中标识的工具。 您需要用于备份 Lync 服务器的所有命令都可以编写脚本, 并且可以远程运行。

### <a name="tools-for-backing-up-lync-server"></a>用于备份 Lync Server 的工具

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>若要备份, 请执行以下操作:</th>
<th>使用此工具或 cmdlet:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>拓扑配置数据 (Xds)</p></td>
<td><p>Export-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>位置信息服务 (E9-1) 数据 (.Lis) 数据 (.Lis)</p></td>
<td><p>Export-CsLisConfiguration</p></td>
</tr>
<tr class="odd">
<td><p>响应组配置数据 (RgsConfig)</p></td>
<td><p>Export-CsRgsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>永久性用户数据 (Rtcxds 数据库)</p>
<p>会议 Id</p></td>
<td><p>Export-CsUserData</p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p>存档数据库 (LcsLog)</p></li>
<li><p>监视通话详细信息记录数据库 (LcsCDR)</p></li>
<li><p>监视 QoE 数据库 (QoEMetrics)</p></li>
</ul></td>
<td><p>SQL Server 数据库工具, 例如 SQL Server Management Studio</p></td>
</tr>
<tr class="even">
<td><p>持久聊天数据库 (Mgc)</p></td>
<td><p>SQL Server 备份过程或导出-CsPersistentChatData。 Export-CsPersistentChatData 将永久聊天数据导出为文件。</p></td>
</tr>
<tr class="odd">
<td><p>所有文件存储: Lync Server 文件存储、存档文件存储</p>
<div>

> [!NOTE]  
> 名为 "<STRONG>会议" 的</STRONG>文件不应备份。 这些文件正在使用中, 并且在召开会议时被锁定。


</div></td>
<td><p>标准文件系统管理工具, 例如 Robocopy。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a>还原

若要还原 Lync Server, 请使用下表中的工具。 可以为还原 Lync Server 所需的所有命令编写脚本。 有些可以远程运行, 但其他人需要在下表中指定的本地运行。

### <a name="tools-for-restoring-lync-server"></a>用于还原 Lync Server 的工具

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>为此, 请执行以下操作:</th>
<th>使用此工具或 cmdlet:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>构建新的或全新的计算机</p></td>
<td><ul>
<li><p>Windows 操作系统安装软件</p></li>
<li><p>SQL Server 安装软件</p></li>
<li><p>证书 Microsoft 管理控制台 (MMC) 管理单元 (如果使用可导出私钥还原证书)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>还原文件存储数据</p></td>
<td><p>标准文件系统管理工具, 例如 Robocopy</p></td>
</tr>
<tr class="odd">
<td><p>重新创建空数据库并为以下项设置权限:</p>
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
> 如果您随时失去服务连接点, 则可以重新运行此 cmdlet。


</div></td>
<td><p>Set-CsConfigurationStoreLocation</p></td>
</tr>
<tr class="odd">
<td><p>将拓扑、策略和配置设置导入中央管理存储 (Xds)</p></td>
<td><p>Import-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>发布和启用拓扑</p></td>
<td><p>拓扑生成器</p>
<p>或</p>
<p>发布-CsTopology 和 Enable-CsTopology</p></td>
</tr>
<tr class="odd">
<td><p>启用上次发布的拓扑</p></td>
<td><p>Enable-CsTopology</p></td>
</tr>
<tr class="even">
<td><p>重新安装 Lync Server 组件</p></td>
<td><p>Lync Server 安装程序</p>
<div>

> [!NOTE]  
> 位于 \setup\amd64\Setup.exe. 中的 Lync Server 安装文件夹或媒体中


</div></td>
</tr>
<tr class="odd">
<td><p>还原位置信息 (E9-1) 数据 (.Lis) 数据 (.Lis)</p></td>
<td><p>Import-CsLisConfiguration</p></td>
</tr>
<tr class="even">
<td><p>还原永久性用户数据 (Rtcxds)</p></td>
<td><p>Import-CsUserData</p></td>
</tr>
<tr class="odd">
<td><p>还原响应组配置数据 (RgsConfig)</p></td>
<td><p>Import-CsRgsConfiguration</p>
<div>

> [!NOTE]  
> 如果在数据库中没有响应组数据的新部署的池中还原配置, 则应使用– OverwriteOwner 选项。 即使正在还原的数据位于具有相同的完全限定的域名 (FQDN) 的池中, 也可使用此选项。 否则, 导入将不会成功, 原因是 Active Directory 中已存在对响应组的联系人对象。


</div></td>
</tr>
<tr class="even">
<td><p>还原以下数据库:</p>
<ul>
<li><p>存档数据库 (LcsLog)</p></li>
<li><p>监视数据库: 调用详细信息记录数据库 (LcsCDR) 和 QoE 数据库 (QoEMetrics)</p></li>
</ul></td>
<td><p>SQL Server 数据库管理工具</p></td>
</tr>
<tr class="odd">
<td><p>持久聊天数据库 (Mgs)</p></td>
<td><p>SQL Server 还原过程或导入-CsPersistentChatData。 你可以将 Import CsPersistentChatData 与由导出 CsPersistentChatData 创建的文件结合使用, 并将数据导入持久聊天数据库。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a>所需权限

用户必须是**RTCUniversalServerAdmins**组的成员才能执行本主题中所述的所有命令。 大多数备份和还原命令不支持基于角色的访问控制 (RBAC)。 两个例外是持久的聊天 cmdlet CsPersistentChatData 和 Import-CsPersistentChatData, 它必须由属于 CsPersistentChatAdministrator 组成员的用户运行。 若要运行 Lync Server 部署向导, 用户还必须是本地管理员组的成员。

</div>

</div>

<span> </span>

</div>

</div>

</div>

