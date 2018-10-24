---
title: Backup-CsPool
TOCTitle: Backup-CsPool
ms:assetid: 66ec46de-e1e7-4e33-961d-7ef785059c48
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204955(v=OCS.15)
ms:contentKeyID: 49313089
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Backup-CsPool

 

_**上一次修改主题：** 2015-03-09_

Creates a backup copy of the specified Lync Server 2013 pool. This cmdlet was introduced in Lync Server 2013.

## 语法

    Backup-CsPool -PoolFqdn <Fqdn> [-Category <UserData | CMS>] [-Confirm [<SwitchParameter>]] [-FailedOverPoolOnly <SwitchParameter>] [-Force <SwitchParameter>] [-FullBackup <SwitchParameter>] [-LocalStore <SwitchParameter>] [-Report <String>] [-RetryCount <Int32>] [-SteadyState <SwitchParameter>] [-WaitTime <TimeSpan>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 backs up the pool atl-cs-001.litwareinc.com.

    Backup-CsPool -PoolFqdn "atl-cs-001.litwareinc.com"

## Example 2

In Example 2, a "steady state" backup is done for the pool atl-cs-001.litwareinc.com.

    Backup-CsPool -PoolFqdn "atl-cs-001.litwareinc.com" -SteadyState

## Detailed Description

The **Backup-CsPool** cmdlet enables administrators to copy user data and conference data for a Registrar pool to a specified backup pool. If the primary pool should fail or otherwise become unavailable, users homed on that primary pool can then be "failed over" to the backup pool. Those users can then log on to Lync Server via the backup pool, and continue to use that pool until their home pool has been restored.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Backup-CsPool"}

**Lync Server 控制面板**: The functions carried out by the **Backup-CsPool** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Fully qualified domain name of the pool being backed up. For example:</p>
<p>-SourcePoolFqdn &quot;atl-cs-001.litwareinc.com&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Category</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Hadr.BackupService.BackupCategory</p></td>
<td><p>Enables you to select the Lync Server modules that will be backed up; if this parameter is not present then all the modules will be backed up. Allowed values are:</p>
<p>* CMS</p>
<p>* UserData</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="even">
<td><p><em>FailedOverPoolOnly</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When specified, backup will take place only if the pool is in a failed over state. If you use this parameter then you must also use the FullBackup parameter.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>FullBackup</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present, backup will not begin until the backup service has reached its final state. You cannot use both the FullBackup parameter and the SteadyState parameter in the same command.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the topology information from the local replica of the Central Management store rather than from the Central Management store itself.</p></td>
</tr>
<tr class="even">
<td><p><em>Report</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>File path for the log file created when the cmdlet runs. For example:</p>
<p>-Report &quot;C:\Logs\BackupPool.html&quot;</p>
<p>If this file already exists, it will be overwritten when you run the cmdlet.</p>
<p>By default, reports are written to the AppData\Local\Temp folder in your user profile.</p></td>
</tr>
<tr class="odd">
<td><p><em>RetryCount</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>Maximum number of times Backup-CsPool will try to call the backup service before failing.</p></td>
</tr>
<tr class="even">
<td><p><em>SteadyState</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present, backup will not begin until the backup service has reached a steady state. A &quot;steady state&quot; occurs when the pool switches to read-only or failover/failback mode, and no longer produces any new data that needs to be backed up.</p></td>
</tr>
<tr class="odd">
<td><p><em>WaitTime</em></p></td>
<td><p>Optional</p></td>
<td><p>System.TimeSpan</p></td>
<td><p>Amount of time (in seconds) that the cmdlet will wait before checking to see if the backup service is in either the full state or the steady state.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Backup-CsPool** cmdlet does not accept pipelined data.

## Return Types

None.

## 另请参阅

#### 其他资源

[Get-CsBackupServiceConfiguration](get-csbackupserviceconfiguration.md)  
[Get-CsBackupServiceStatus](get-csbackupservicestatus.md)  
[Get-CsPoolBackupRelationship](get-cspoolbackuprelationship.md)

