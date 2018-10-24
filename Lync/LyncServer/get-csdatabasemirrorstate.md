---
title: Get-CsDatabaseMirrorState
TOCTitle: Get-CsDatabaseMirrorState
ms:assetid: 458f5367-ee04-4281-971f-08f79a625509
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204845(v=OCS.15)
ms:contentKeyID: 49312708
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsDatabaseMirrorState

 

_**上一次修改主题：** 2015-03-09_

Returns information about whether database mirroring has been implemented for a specified database on a specified pool. Database mirroring enables you to simultaneously maintain two copies of a database, with each copy residing on a different server. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Get-CsDatabaseMirrorState -PoolFqdn <Fqdn> [-DatabaseType <Application | Archiving | Monitoring | User | Provision | CentralAdmin | Lyss | Registrar | Edge | PersistentChat | PersistentChatCompliance | CentralMgmt>] [-LocalStore <SwitchParameter>] [-Report <String>]

## Examples

## Example 1

The command shown in Example 1 returns the state of the database mirror assigned to the monitoring database for the pool atl-cs-001.litwareinc.com.

    Get-CsDatabaseMirrorState -PoolFqdn "atl-cs-001.litwareinc.com" -DatabaseType Monitoring

## Detailed Description

The **Get-CsDatabaseMirrorState** cmdlet returns information about the mirror databases configured for a pool; this includes information about the mirror databases that might (or might not) have been configured for the Front End server database, the Location Information Service database, the call detail recording and Quality of Experience databases, and so on. For each database the cmdlet will report back the synchronization status for both the primary database and the mirror database. In some cases you will see output similar to this, including the property value DatabaseInaccessibleOrMirroringNotEnabled:

DatabaseName : lcscdr

StateOnPrimary : DatabaseInaccessibleOrMirroringNotEnabled

StateOnMirror : DatabaseInaccessibleOrMirroringNotEnabled

MirroringStatusOnPrimary :

MirroringStatusOnSecondary :

That typically means that no mirror database has been assigned to the primary database (in this case, the database lcscdr, used for maintaining call detail data).

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsDatabaseMirrorState"}

**Lync Server 控制面板:** The functions carried out by the **Get-CsDatabaseMirrorState** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>PoolFqdn</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified domain name of the pool whose database mirroring state is being checked. For example:</p>
<p>-PoolFqdn &quot;atl-cs-001.litwareinc.com&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>DatabaseType</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deployment.DatabaseNameType</p></td>
<td><p>Type of database whose mirror state is being checked. Allowed values are:</p>
<p>Application</p>
<p>Archiving</p>
<p>CentralAdmin</p>
<p>CentralMgmt</p>
<p>Edge</p>
<p>Lyss</p>
<p>Monitoring</p>
<p>PersistentChat</p>
<p>PersistentChatCompliance</p>
<p>Provision</p>
<p>Registrar</p>
<p>User</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the backup mirror state from the local replica of the Central Management store rather than from the Central Management store itself.</p></td>
</tr>
<tr class="even">
<td><p><em>Report</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to specify a file path for the log file created when the cmdlet runs. For example:</p>
<p>-Report &quot;C:\Logs\DatabaseMirrorState.html&quot;</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsDatabaseMirrorState** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsDatabaseMirrorState** cmdlet returns instances of the Microsoft.Rtc.Management.Deployment.DatabaseMirrorState class.

## 另请参阅

#### 其他资源

[Install-CsMirrorDatabase](install-csmirrordatabase.md)  
[Uninstall-CsMirrorDatabase](uninstall-csmirrordatabase.md)

