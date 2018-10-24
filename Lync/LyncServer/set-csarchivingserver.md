---
title: Set-CsArchivingServer
TOCTitle: Set-CsArchivingServer
ms:assetid: d4e51c14-34a6-4134-bb71-87bc2f11092d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398923(v=OCS.15)
ms:contentKeyID: 49314352
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsArchivingServer

 

_**上一次修改主题：** 2015-03-09_

Enables you to specify a new database location for one or more 存档服务器. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsArchivingServer [-Identity <XdsGlobalRelativeIdentity>] [-ArchivingDatabase <String>] [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 changes the location of the 存档数据库 for the ArchivingServer:atl-cs-001.litwareinc.com 存档服务器 . In this example, the new database is located at ArchivingDatabase:atl-sql-001.litwareinc.com.

    Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.litwareinc.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.litwareinc.com"

## Detailed Description

存档服务器 provide a way for you to save complete transcripts of the instant messaging (IM) sessions that take place in your organization. In some organizations, it can be useful to have copies of these IM sessions. In other organizations, where records must be kept of all electronic communications, it can be mandatory to have copies of these IM sessions.

存档服务器 records the transcript of each IM session (as well as information about when the session took place, and who participated in the session) in a SQL Server database. The location of this database must be specified when you install 存档服务器; in most cases, you will not need to change the location of that database. However, if a hardware failure or other problem should occur, you can point 存档服务器 to a new database by using the **Set-CsArchivingServer** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsArchivingServer** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsArchivingServer"}

## 参数


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Parameter</th>
<th>Required</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>ArchivingDatabase</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Service location where the new 存档数据库 is located. For example: -ArchivingDatabase ArchivingDatabase:atl-sql-001.litwareinc.com. Make sure you use the service location and not the SQL Server path when specifying the database location.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Service location of the 存档服务器 instance to be modified. For example: -Identity ArchivingServer:atl-cs-001.litwareinc.com. You can retrieve the service location for all your Archiving servers by running this command:</p>
<p>Get-CsService –ArchivingServer | Select-Object Identity</p>
<p>Note that you can leave off the prefix &quot;ArchivingServer:&quot; when specifying an Archiving server. For example: -Identity &quot;atl-cs-001.litwareinc.com&quot;.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Set-CsArchivingServer** cmdlet does not accept pipelined input.

## Return Types

The **Set-CsArchivingServer** cmdlet does not return any objects or values. Instead, the cmdlet modifies instances of the Microsoft.Rtc.Management.Xds.DisplayArchivingServer object.

## 另请参阅

#### 其他资源

[Get-CsArchivingConfiguration](get-csarchivingconfiguration.md)

