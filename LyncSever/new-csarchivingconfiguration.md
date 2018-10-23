---
title: New-CsArchivingConfiguration
TOCTitle: New-CsArchivingConfiguration
ms:assetid: 66cab8b7-c3b3-4c1b-a77a-28f295ff6010
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398471(v=OCS.15)
ms:contentKeyID: 49313084
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsArchivingConfiguration

 

_**上一次修改主题：** 2015-03-09_

Creates a new set of instant messaging (IM) archiving settings. These settings can be used to enable or disable the automatic saving of IM sessions; these settings also enable you to block any instant messages that cannot be archived. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsArchivingConfiguration -Identity <XdsIdentity> [-ArchiveDuplicateMessages <$true | $false>] [-BlockOnArchiveFailure <$true | $false>] [-CachePurgingInterval <UInt32>] [-Confirm [<SwitchParameter>]] [-EnableArchiving <None | ImOnly | ImAndWebConf>] [-EnableExchangeArchiving <$true | $false>] [-EnablePurging <$true | $false>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-KeepArchivingDataForDays <UInt32>] [-PurgeExportedArchivesOnly <$true | $false>] [-PurgeHourOfDay <UInt32>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 creates a new collection of archiving configuration settings and applies these settings to the Redmond site. By adding the EnableArchiving parameter and setting the parameter value to "ImOnly", the command also enables IM session archiving (but not web conference archiving) for the Redmond site.

    New-CsArchivingConfiguration -Identity site:Redmond -EnableArchiving "ImOnly"

## EXAMPLE 2

Example 2 demonstrates the use of the InMemory parameter to create a collection of archiving configuration settings that initially exist only in memory. To do this, the example creates a new collection of settings (with the Identity site:Redmond) and stores this collection in a variable named $x. Note that, after this first command runs, the collection exists only in memory; if you run the command the **Get-CsArchivingConfiguration** cmdlet you will not see an entry for site:Redmond.

In the second command, the EnableArchiving property for this virtual collection of settings is set to "ImOnly", which enables IM session archiving. Finally, the last command uses the **Set-CsArchivingConfiguration** cmdlet to transform the virtual archiving settings into an actual collection of settings applied to the Redmond site. If you do not call the **Set-CsArchivingConfiguration** cmdlet, these settings will remain in memory only and will disappear when your Windows PowerShell session is terminated or the variable $x is deleted.

    $x = New-CsArchivingConfiguration -Identity site:Redmond -InMemory
    $x.EnableArchiving = "ImOnly"
    Set-CsArchivingConfiguration -Instance $x

## Detailed Description

Many organizations find it useful to keep a transcript of all the IM sessions carried out by their users. For other organizations, it’s mandatory to keep such transcripts; for example, many organizations in the financial world are required by law to keep copies of all their electronic communications.

Lync Server gives you flexibility when it comes to archiving IM and web conferencing sessions. If you have deployed 存档服务器, you can use the various **CsArchivingConfiguration** cmdlets to enable and disable IM session archiving and to manage your archiving database. You can also suspend IM should archiving fail; this helps to ensure that you keep a record of all your electronic communications.

When you install Lync Server, a collection of global archiving settings will be created for you; by default, these settings will apply to your entire organization. Alternatively, you can use the **New-CsArchivingConfiguration** cmdlet to create custom configuration settings on a site-by-site basis.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsArchivingConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsArchivingConfiguration"}

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
<td><p>Unique identifier to be assigned to the new collection of archiving configuration settings. In Lync Server 2013 you can create new collections at the site scope or at the service scope. (In Microsoft Lync Server 2010 you can only create these settings at the site scope.) To create new settings at the site scope, use syntax similar to this:</p>
<p>-Identity &quot;site:Redmond&quot;</p>
<p>To create settings at the service scope (for the Registrar service only) use syntax like this:</p>
<p>-Identity &quot;service:Registrar:atl-cs-001.litwareinc.com&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>ArchiveDuplicateMessages</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Specifies how cross-pool instant messages should be archived. For example, Ken Myer (with an account in Pool 1) sends an instant message to Pilar Ackerman (who has an account in Pool 2). Pilar, in turn, sends a reply to Ken’s instant message. If ArchiveDuplicateMessages is set to False, then (based on a built-in algorithm) the session transcript will be logged in either Pool 1 or Pool 2, but not both. If ArchiveDuplicateMessages is set to True (the default value), the transcript will be logged in both pools.</p></td>
</tr>
<tr class="odd">
<td><p><em>BlockOnArchiveFailure</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If True, then the IM service will be suspended any time your instant message sessions cannot be archived. If set to False (the default value), instant messaging will continue even if sessions cannot be archived.</p></td>
</tr>
<tr class="even">
<td><p><em>CachePurgingInterval</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Indicates how often (in hours) the system is purged of transcripts where none of the participants have been enabled for archiving. By design, all group IM sessions and conferencing sessions are recorded when they take place. At the specified interval, the system will determine whether any of the participants in these sessions have been enabled for archiving. If the system finds a session where none of the participants have been enabled for archiving, then that transcript will be deleted from the database.</p>
<p>The CachePurgeInterval property can be set to any integer value between 4 and 168, inclusive. The default value is 24.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>EnableArchiving</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.Archiving.EnableArchiving</p></td>
<td><p>Indicates which items (if any) are saved to the archiving database. Valid values are:</p>
<p>None. No items are archived to the database. This is the default value.</p>
<p>ImOnly. IM sessions are archived to the database.</p>
<p>ImAndWebConf. Both IM and web conferencing sessions are archived to the database.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableExchangeArchiving</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, Lync Server 2013 instant message and conferencing transcripts are stored in Microsoft Exchange Server 2013 rather than a separate SQL Server database. Note that if you enable Exchange archiving then users will be managed by the Exchange archiving policies instead of Lync Server archiving policies.</p>
<p>The default value is False.</p></td>
</tr>
<tr class="even">
<td><p><em>EnablePurging</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If True, archived instant messages will periodically be removed from the database, provided that these instant messages: 1) are older than the value specified in the KeepArchivingDataForDays property; or, 2) have been exported and marked for deletion.</p>
<p>If False, instant messages will not be automatically deleted from the database.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might arise when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="odd">
<td><p><em>KeepArchivingDataForDays</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Number of days (between 1 and 2562) that archived instant messages are kept in the database before being automatically deleted. The default value is 14.</p>
<p>This property takes effect only if EnablePurging has been set to True.</p></td>
</tr>
<tr class="even">
<td><p><em>PurgeExportedArchivesOnly</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If True, then the system will only purge instant messages that have been exported (and, as a result, have been marked for deletion). Instant messages that have not been exported will remain in the database, even if those messages are older than the value specified by the KeepArchivingDataForDays property.</p></td>
</tr>
<tr class="odd">
<td><p><em>PurgeHourOfDay</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Indicates the time of day when expired records are deleted from the archiving database. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day. This means that you can schedule purging to take place at 4:00 AM, but you cannot schedule it to take place at, for instance, 4:30 AM or 4:15 AM. The default value is 2 (2:00 AM).</p>
<p>Database purging takes place only if the EnablePurging property is set to True.</p></td>
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

None. The **New-CsArchivingConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **New-CsArchivingConfiguration** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Archiving.ArchivingSettings object.

## 另请参阅

#### 其他资源

[Get-CsArchivingConfiguration](get-csarchivingconfiguration.md)  
[Remove-CsArchivingConfiguration](remove-csarchivingconfiguration.md)  
[Set-CsArchivingConfiguration](set-csarchivingconfiguration.md)  
[Set-CsArchivingServer](set-csarchivingserver.md)

