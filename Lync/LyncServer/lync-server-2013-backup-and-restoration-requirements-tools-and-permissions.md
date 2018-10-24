---
title: 备份和还原要求：工具和权限
TOCTitle: 备份和还原要求：工具和权限
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh202171(v=OCS.15)
ms:contentKeyID: 52060987
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 备份和还原要求：工具和权限

 

_**上一次修改主题：** 2015-03-09_

本主题介绍可用于备份和还原 Lync Server 2013 的工具、需要的权限，以及可以远程运行命令还是在本地运行命令。具体说来，本主题主要介绍与 Lync Server 一起提供的备份和还原工具。

## 备份

若要备份 Lync Server，请使用下表中标识的工具。备份 Lync Server 所需的所有命令均可编制脚本并远程运行。

### 用于备份 Lync Server 的工具

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
<td><p>永久用户数据（Rtcxds.mdf 数据库）</p>
<p>会议 ID</p></td>
<td><p>Export-CsUserData</p></td>
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
<td><p>持久聊天数据库 (Mgc.mdf)</p></td>
<td><p>SQL Server 备份过程或 Export-CsPersistentChatData。Export-CsPersistentChatData 将持久聊天数据导出成一个文件。</p></td>
</tr>
<tr class="odd">
<td><p>所有文件存储：Lync Server 文件存储、存档文件存储</p>
<div>

> [!NOTE]  
> 名为 <strong>Meeting.Active</strong> 的文件不应进行备份。在召开会议时，会使用并锁定这些文件。


</div></td>
<td><p>标准文件系统管理工具，例如 Robocopy。</p></td>
</tr>
</tbody>
</table>


## 还原

若要还原 Lync Server，请使用下表中的工具。还原 Lync Server 所需的所有命令均可编制脚本。某些命令可以远程运行，而其他命令需要在本地运行，如下表所指定。

### 用于还原 Lync Server 的工具

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
<td><p>还原指向中央管理存储的 Active Directory 域服务 指针</p>
<div>

> [!NOTE]  
> 如果在任何时候丢失服务连接点，则可重新运行该 cmdlet。


</div></td>
<td><p>Set-CsConfigurationStoreLocation</p></td>
</tr>
<tr class="odd">
<td><p>将拓扑、策略和配置设置导入中央管理存储 (Xds.mdf)</p></td>
<td><p>Import-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>发布并启用拓扑</p></td>
<td><p>拓扑生成器</p>
<p>- 或者 -</p>
<p>Publish-CsTopology 和 Enable-CsTopology</p></td>
</tr>
<tr class="odd">
<td><p>启用上一次发布的拓扑</p></td>
<td><p>Enable-CsTopology</p></td>
</tr>
<tr class="even">
<td><p>重新安装 Lync Server 组件</p></td>
<td><p>Lync Server 安装程序</p>
<div>

> [!NOTE]  
> 位于 \setup\amd64\Setup.exe 下的 Lync Server 安装文件夹或介质中。


</div></td>
</tr>
<tr class="odd">
<td><p>还原位置信息 (E9-1-1) 数据 (Lis.mdf)</p></td>
<td><p>Import-CsLisConfiguration</p></td>
</tr>
<tr class="even">
<td><p>还原永久用户数据 (Rtcxds.mdf)</p></td>
<td><p>Import-CsUserData</p></td>
</tr>
<tr class="odd">
<td><p>还原响应组配置数据 (RgsConfig.mdf)</p></td>
<td><p>Import-CsRgsConfiguration</p>
<div>

> [!NOTE]  
> 如果是在数据库中无响应组数据的新部署的池中还原配置，则应使用 –OverwriteOwner 选项。即使正在还原的数据位于具有同一完全限定域名 (FQDN) 的池中，也要使用此选项。否则，由于响应组的联系对象已存在于 Active Directory 中，导入操作将失败。


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
<td><p>持久聊天数据库 (Mgs.mdf)</p></td>
<td><p>SQL Server 还原过程或 Import-CsPersistentChatData。您可以通过 Export-CsPersistentChatData 创建的文件来使用 Import-CsPersistentChatData，相应数据将导入持久聊天数据库中。</p></td>
</tr>
</tbody>
</table>


## 所需权限

用户必须是“RTCUniversalServerAdmins”组的成员，才能执行本主题中介绍的所有命令。大多数备份和还原命令不支持基于角色的访问控制 (RBAC)。Export-CsPersistentChatData 和 Import-CsPersistentChatData 这两个持久聊天 cmdlet 例外，它们必须由具有 CsPersistentChatAdministrator 组成员身份的用户运行。若要运行 Lync Server 部署向导，用户必须同时是本地 Adminstrators 组的成员。

