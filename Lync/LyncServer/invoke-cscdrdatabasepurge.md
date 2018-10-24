---
title: Invoke-CsCdrDatabasePurge
TOCTitle: Invoke-CsCdrDatabasePurge
ms:assetid: 95eb0faf-49dc-4afb-b98c-15735a4cab13
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205113(v=OCS.15)
ms:contentKeyID: 49313658
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Invoke-CsCdrDatabasePurge

 

_**上一次修改主题：** 2015-03-09_

Manually purges records from the Call Detail records (CDR) database. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Invoke-CsCdrDatabasePurge -Identity <XdsIdentity> <COMMON PARAMETERS>

    Invoke-CsCdrDatabasePurge -SqlServerFqdn <String> [-SqlInstanceName <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: -PurgeCallDetailDataOlderThanDays <Int32> -PurgeDiagnosticDataOlderThanDays <Int32> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 deletes all the records (both call detail and diagnostic records) from the monitoring database atl-sql-001.litwareinc.com that are more than 10 days old.

    Invoke-CsCdrDatabasePurge -Identity "service:MonitoringDatabase:atl-sql-001.litwareinc.com" -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

## Example 2

The command shown in Example 2 is a variation of the command shown in Example 1; in this case, however, the Confirm parameter is added using this syntax:

\-Confirm:$False

That syntax suppresses the confirmation prompts that would otherwise appear when purging CDR records.

    Invoke-CsCdrDatabasePurge -Identity "service:MonitoringDatabase:atl-sql-001.litwareinc.com" -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

## Example 3

Example 3 purges all the records more than 10 days old from all the CDR databases in use in the organization. To do this, the first command in the example uses the **Get-CsService** cmdlet and the MonitoringDatabase parameter to return a collection of all the monitoring databases. This collection is then piped to the **ForEach-Object** cmdlet. In turn, the **ForEach-Object** cmdlet takes each database in the collection and then runs the **Invoke-CsCdrDatabasePurge** cmdlet against that database, purging all the call detail records more than 10 days old.

    Get-CsService -MonitoringDatabase | ForEach-Object {Invoke-CsCdrDatabasePurge -Identity $_.Identity -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False}

## Detailed Description

Call detail recording (CDR) provides a way for you to track usage of Lync Server capabilities such as Voice over IP (VoIP) phone calls; instant messaging (IM); file transfers; audio/video (A/V) conferencing; and application sharing sessions. CDR keeps usage information: it logs information such as the parties involved in the call; the length of the call; and whether or not any files were transferred. However, CDR does not make a recording of the call itself.

CDR also keeps track of call error information: detailed diagnostic data for both peer-to-peer sessions and for conferencing calls.

Call detail records are stored in the SQL Server database LcsCDR. Over time, this database has the potential to grow extremely large. Because of that, Lync Server provides two ways for administrators to purge older records from the database: 1) you can configure Lync Server to automatically delete older CDR records each day; and/or, 2) you can use the **Invoke-CsCdrDatabasePurge** cmdlet at any time to delete CDR records from the LcsCDR database. (The **Invoke-CsCdrDatabasePurge** cmdlet does this by calling the SQL Server stored procedure RtcCleanupDB.)

When you call the **Invoke-CsCdrDatabasePurge** cmdlet you must specify the service location of the monitoring database where the CDR records are stored (for example, MonitoringDatabase:atl-sql-001.litwareinc.com); you must also indicate the minimum age (in days) of the call detail and diagnostic data records to be deleted. For example, if you specify a minimum age of 10 days for call detail records, then all call detail records older than 10 days will be deleted from the database.

Note that these records will be deleted even if the purging has been disabled for the specified database. (That is, the EnablePurging property in the CDR configuration settings has been set to False.) The EnablePurging property only controls the automated purging of CDR records; it has no effect on the **Invoke-CsCdrDatabasePurge** cmdlet.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Invoke-CsCdrDatabasePurge"}

**Lync Server 控制面板:** The functions carried out by the **Invoke-CsCdrDatabasePurge** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Service Identity of the monitoring database to be purged. You can retrieve the Identities for your monitoring databases by running this command:</p>
<p>Get-CsService –MonitoringDatabase</p>
<p>Note that you cannot use the Identity parameter and the SqlServerFqdn parameter in the same command.</p></td>
</tr>
<tr class="even">
<td><p><em>PurgeCallDetailDataOlderThanDays</em></p></td>
<td><p>Required</p></td>
<td><p>System.Int32</p></td>
<td><p>Specifies the age (in days) of the call detail records to be purged from the database; any records older than this value will be deleted. Call detail records represent user/session reports. They differ from diagnostic data reports, which are diagnostic logs uploaded by client applications such as Lync 2013.</p>
<p>PurgeCallDetailDataOlderThanDays can be set to any integer value between 1 and 2147483647, inclusive.</p></td>
</tr>
<tr class="odd">
<td><p><em>PurgeDiagnosticDataOlderThanDays</em></p></td>
<td><p>Required</p></td>
<td><p>System.Int32</p></td>
<td><p>Specifies the age (in days) of the diagnostic data records to be purged from the database; any records older than this value will be deleted. Diagnostic data reports are diagnostic logs uploaded by client applications such as Lync 2013.</p>
<p>PurgeDiagnosticDataOlderThanHours can be set to any integer value between 1 and 2147483647, inclusive.</p></td>
</tr>
<tr class="even">
<td><p><em>SqlServerFqdn</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Fully qualified domain name of the computer where the CDR database is located. For example:</p>
<p>-SqlServerFqdn &quot;atl-sql-001.litwareinc.com&quot;</p>
<p>Note that you cannot use the Identity parameter and the SqlServerFqdn parameter in the same command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>SqlInstanceName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>SQL Server instance name for the CDR database. For example:</p>
<p>-SqlInstanceName &quot;archinst&quot;</p></td>
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

The **Invoke-CsCdrDatabasePurge** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.Xds.DisplayMonitoringDatabase\#Decorated class.

## Return Types

The **Invoke-CsCdrDatabasePurge** cmdlet returns instances of the Microsoft.Rtc.Management.Purge.CdrDataPurgeStatistics class.

## 另请参阅

#### 其他资源

[New-CsCdrConfiguration](new-cscdrconfiguration.md)  
[Set-CsCdrConfiguration](set-cscdrconfiguration.md)

