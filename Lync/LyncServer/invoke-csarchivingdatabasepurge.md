---
title: Invoke-CsArchivingDatabasePurge
TOCTitle: Invoke-CsArchivingDatabasePurge
ms:assetid: 02310b08-736d-4ce9-91d8-5a6c8f323d7c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204627(v=OCS.15)
ms:contentKeyID: 49311816
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Invoke-CsArchivingDatabasePurge

 

_**上一次修改主题：** 2015-03-09_

Manually purges records from the Archiving database. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Invoke-CsArchivingDatabasePurge -Identity <XdsIdentity> <COMMON PARAMETERS>

    Invoke-CsArchivingDatabasePurge -SqlServerFqdn <String> [-SqlInstanceName <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: -PurgeArchivingDataOlderThanHours <Int32> -PurgeExportedArchivesOnly <$true | $false> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-MaxArchivingRecordsToDelete <Int32>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 purges all the records more than 24 hours old from the archiving database on atl-sql-001.litwareinc.com. To ensure that all the records are deleted, including records that have not been exported, the PurgeExportedArchivesOnly parameter is set to False ($False).

    Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.litwareinc.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False

## Example 2

The command shown in Example 2 is a variation of the command shown in Example 1; in this case, however, the Confirm parameter is added using this syntax:

\-Confirm:$False

That syntax suppresses the confirmation prompts that would otherwise appear when purging archiving records.

    Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.litwareinc.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False -Confirm:$False

## Example 3

Example 3 purges all the records more than 24 hours old from all the Archiving databases in use in the organization. To do this, the first command in the example uses the **Get-CsService** cmdlet and the ArchivingDatabase parameter to return a collection of all the archiving databases. This collection is then piped to the **ForEach-Object** cmdlet. In turn, the ForEach-Object cmdlet takes each database in the collection and then runs the **Invoke-CsArchivingDatabasePurge** cmdlet against that database, purging all the records more than 24 hours old.

    Get-CsService -ArchivingDatabase | ForEach-Object {Invoke-CsArchivingDatabasePurge -Identity $_.Identity -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False -Confirm:$False}

## Detailed Description

Many organizations find it useful to keep a transcript of all the IM sessions carried out by their users (or a selected subset of users). For other organizations, it’s mandatory to keep such transcripts. For example, many organizations in the financial world are required by law to keep copies of all their electronic communications.

If you have enabled archiving in your organization and if you have chosen to use Lync Server as your archiving backend, then your archiving records will be stored in the SQL Server database LcsLog. (Alternatively, archiving records can be stored using Microsoft Exchange instead. See the help topic for the **New-CsArchivingConfiguration** cmdlet for more information.) Over time, the archiving database has the potential to grow extremely large. Because of that, Lync Server provides two ways for administrators to purge older records from the database: 1) you can configure Lync Server to automatically delete older archiving records each day; and/or, 2) you can use the **Invoke-CsArchivingDatabasePurge** cmdlet at any time to delete archiving records from the LcsLog database. (The **Invoke-CsArchivingDatabasePurge** cmdlet does this by calling the SQL Server stored procedures RtcCleanupTempConference and RtcCleanupDB as well as deleted stored meeting content.)

When you call the **Invoke-CsArchivingDatabasePurge** cmdlet you must specify the service location of the archiving database where the archiving records are stored (for example, ArchivingDatabase:atl-sql-001.litwareinc.com); you must also indicate the minimum age (in hours) of the archiving records to be deleted. For example, if you specify a minimum age of 24 hours then all archiving records older than 24 hours will be deleted from the database.

Note that these records will be deleted even if the purging has been disabled for the specified database. (That is, the EnablePurging property in the archiving configuration settings has been set to False.) The EnablePurging property only controls the automated purging of archiving records; it has no effect on the **Invoke-CsArchivingDatabasePurge** cmdlet.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Invoke-CsArchivingDatabasePurge"}

**Lync Server 控制面板:** The functions carried out by the **Invoke-CsArchivingDatabasePurge** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Service Identity of the archiving database to be purged. You can retrieve the Identities for your archiving databases by running this command:</p>
<p>Get-CsService –ArchivingDatabase</p>
<p>Note that you cannot use the Identity parameter and the SqlServerFqdn parameter in the same command.</p></td>
</tr>
<tr class="even">
<td><p><em>PurgeArchivingDataOlderThanHours</em></p></td>
<td><p>Required</p></td>
<td><p>System.Int32</p></td>
<td><p>Specifies the age (in hours) of the archiving records to be purged from the database; any records older than this value will be deleted. PurgeArchivingDataOlderThanHours can be set to any integer value between 1 and 2147483647, inclusive.</p></td>
</tr>
<tr class="odd">
<td><p><em>PurgeExportedArchivesOnly</em></p></td>
<td><p>Required</p></td>
<td><p>System.Boolean</p></td>
<td><p>When present, records will be removed for the archiving database only if those records have been exported (and, as a result, have been marked for deletion). Records that have not been exported will remain in the database, even if those records are older than the value specified by the PurgeArchivingDataOlderThanHours property.</p></td>
</tr>
<tr class="even">
<td><p><em>SqlServerFqdn</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Fully qualified domain name of the computer where the archiving database is located. For example:</p>
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
<td><p><em>MaxArchivingRecordsToDelete</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>Specifies the maximum number of archiving records to be purged from the database; if you set this value to 99 and you have 100 records in the database that meet the PurgeArchivingDataOlderThanHours criterion, only the 99 oldest records will be deleted.</p>
<p>MaxArchivingRecordsToDelete can be set to any integer value between 1 and 2147483647, inclusive.</p></td>
</tr>
<tr class="even">
<td><p><em>SqlInstanceName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>SQL Server instance name for the archiving database. For example:</p>
<p>-SqlInstanceName &quot;archinst&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

The **Invoke-CsArchivingDatabasePurge** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.Xds.DisplayArchivingDatabase\#Decorated class.

## Return Types

The Invoke-CsArchivingDatabasePurge cmdlet returns instances of the Microsoft.Rtc.Management.Purge.ArchDataPurgeStatistics class.

## 另请参阅

#### 其他资源

[New-CsArchivingConfiguration](new-csarchivingconfiguration.md)  
[Set-CsArchivingConfiguration](set-csarchivingconfiguration.md)

