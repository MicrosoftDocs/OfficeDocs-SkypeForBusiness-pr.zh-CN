---
title: Export-CsArchivingData
TOCTitle: Export-CsArchivingData
ms:assetid: 644bf86e-0e7e-4607-bedf-d491b1c16745
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398452(v=OCS.15)
ms:contentKeyID: 49313057
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Export-CsArchivingData

 

_**上一次修改主题：** 2015-03-09_

Enables you to export records that have been stored in the Lync Server 存档数据库. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Export-CsArchivingData -DBInstance <String> -Identity <XdsIdentity> <COMMON PARAMETERS>

    Export-CsArchivingData -Identity <XdsIdentity> <COMMON PARAMETERS>

    Export-CsArchivingData -DBInstance <String> <COMMON PARAMETERS>

    COMMON PARAMETERS: -OutputFolder <String> -StartDate <DateTime> [-Confirm [<SwitchParameter>]] [-EndDate <DateTime>] [-ExcludeWebConfArchive <SwitchParameter>] [-Force <SwitchParameter>] [-IncludeTrustedApplication <SwitchParameter>] [-Purge <SwitchParameter>] [-UserUri <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 extracts records from the 存档数据库 located on the server atl-sql-001.litwareinc.com, and then saves the resulting EML file to the folder C:\\ArchivingExports. The specified start date of June 1, 2012 (-StartDate 6/1/2012) ensures that only items recorded in the database after 5/31/2012 will be exported.

    Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

## EXAMPLE 2

Example 2 is a variation of the command shown in Example 1; in this case, however, only the records pertaining to the user Ken Myer are exported. To limit your export to records pertaining to a single user, include the UserUri parameter followed by appropriate SIP address.

    Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "kenmyer@litwareinc.com"

## EXAMPLE 3

Example 3 represents another variation of the command shown in Example 1. In Example 3, however, only items recorded in the database during the month of June, 2012 are exported. To limit exporting to this time interval, the EndDate parameter is included along with the StartDate parameter. With a start date of June 1, 2012 and an end date of June 30, 2012, exporting is limited to items recorded during June 2012.

    Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -EndDate 6/30/2012 -OutputFolder "C:\ArchivingExports"

## Detailed Description

Many organizations find it useful to keep a transcript of all the instant messaging (IM) sessions carried out by their users. Other organizations find it mandatory to keep such transcripts. For example, organizations in the financial world are often required by law to keep copies of all their electronic communications.

Regardless of the reason, Lync Server gives you flexibility when it comes to archiving IM and conferencing sessions. If you have deployed 存档服务器, you can use the various **CsArchivingConfiguration** cmdlets to enable and disable instant message archiving and to manage your 存档数据库. You can also suspend IM should archiving fail, which helps ensure that you keep a record of all your electronic communications.

If you have enabled archiving, records of your users’ electronic communications are stored in the 存档数据库. If you would like to view all of these records (or a selected subset of these records), you can use the **Export-CsArchivingData** cmdlet to extract these records from the database and save them as an Outlook Express Electronic Mail (EML) file (.EML file extension).

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Export-CsArchivingData** cmdlet locally: RTCComponentUniversalServices. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Export-CsArchivingData"}

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
<td><p><em>DBInstance</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Path to the SQL Server database instance where archiving data is recorded. For example: &quot;atl-sql-001\Archinst&quot;.</p>
<p>This parameter is intended for use only with Microsoft Lync Server 2010. If you are using the <strong>Export-CsArchivingData</strong> cmdlet on Lync Server 2013 you should use the Identity parameter instead.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Service identity of the archiving database to be exported. For example:</p>
<p>-Identity &quot;ArchivingDatabase:atl-sql-001.litwareinc.com&quot;</p>
<p>You can also specify the database by using just the pool name:</p>
<p>-Identity &quot;atl-sql-001.litwareinc.com&quot;</p>
<p>You can retrieve the service identities for your archiving databases by using this command:</p>
<p>Get-CsService –ArchivingDatabase | Select-Object Identity</p></td>
</tr>
<tr class="odd">
<td><p><em>OutputFolder</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Full path to the folder where the exported data should be stored (for example, C:\ArchivingExports). If this folder does not exist, then the <strong>Export-CsArchivingData</strong> cmdlet will create it.</p></td>
</tr>
<tr class="even">
<td><p><em>StartDate</em></p></td>
<td><p>Required</p></td>
<td><p>System.DateTime</p></td>
<td><p>Indicates the earliest activity date for the records to be exported. For example, if you set the start date to 6/1/2010 (June 1, 2010, in U.S. English) any items recorded in the database prior to that date (for example, items recorded on May 31, 2010) will be excluded from the export.</p>
<p>Use the date-time formats specified by your Regional and Language Options settings when assigning values to the StartDate and EndDate properties.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>EndDate</em></p></td>
<td><p>Optional</p></td>
<td><p>System.DateTime</p></td>
<td><p>Indicates the latest activity date for records to be exported. For example, if you set the end date to 6/1/2010 (June 1, 2010, in U.S. English) any items recorded in the database after that date (for example, items recorded on June 2, 2010) will be excluded from the export. Although you will not receive an error message, your export will fail if the end date occurs before the start date (for example, an end date of 1/1/2010 and a start date of 6/1/2010).</p>
<p>Use the date-time formats specified by your Regional and Language Options settings when assigning values to the StartDate and EndDate properties.</p>
<p>If an end date is not specified then the current date will be used.</p></td>
</tr>
<tr class="odd">
<td><p><em>ExcludeWebConfArchive</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Instructs the <strong>Export-CsArchivingData</strong> cmdlet to only export instant messaging records. By default, the cmdlet exports both IM and conferencing records.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>IncludeTrustedApplication</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When included, instructs the <strong>Export-CsArchivingData</strong> cmdlet to include data logged by trusted applications when exporting records.</p></td>
</tr>
<tr class="even">
<td><p><em>Purge</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When included, the Purge parameter causes any record that has been successfully exported to be deleted from the 存档数据库. If you do not include this parameter, exported records will be retained in the database.</p></td>
</tr>
<tr class="odd">
<td><p><em>UserUri</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to export archiving data for a single user; this is done by using the UserUri parameter and specifying the SIP address of the user. The UserUri parameter will accept only one URI at a time.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Export-CsArchivingData** cmdlet does not accept pipelined input.

## Return Types

The **Export-CsArchivingData** cmdlet returns 存档数据库 records in EML format.

## 另请参阅

#### 其他资源

[Get-CsArchivingConfiguration](get-csarchivingconfiguration.md)

