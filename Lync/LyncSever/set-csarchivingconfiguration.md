---
title: Set-CsArchivingConfiguration
TOCTitle: Set-CsArchivingConfiguration
ms:assetid: f5202dc2-b3b4-48ae-93d2-d19e71847994
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413030(v=OCS.15)
ms:contentKeyID: 49314753
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsArchivingConfiguration

 

_**上一次修改主题：** 2015-03-09_

Modifies an existing collection of instant messaging (IM) archiving settings. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsArchivingConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsArchivingConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-ArchiveDuplicateMessages <$true | $false>] [-BlockOnArchiveFailure <$true | $false>] [-CachePurgingInterval <UInt32>] [-Confirm [<SwitchParameter>]] [-EnableArchiving <None | ImOnly | ImAndWebConf>] [-EnableExchangeArchiving <$true | $false>] [-EnablePurging <$true | $false>] [-Force <SwitchParameter>] [-KeepArchivingDataForDays <UInt32>] [-PurgeExportedArchivesOnly <$true | $false>] [-PurgeHourOfDay <UInt32>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In Example 1, the **Set-CsArchivingConfiguration** cmdlet is used to modify two properties of the archiving configuration settings that have the Identity site:Redmond. First, the command sets the ArchiveDuplicateMessages property to False; this prevents the server from archiving the same instant message session multiple times. The command also uses the KeepArchivingDataForDays parameter to instruct the server to keep instant messages for 30 days.

    Set-CsArchivingConfiguration -Identity site:Redmond -ArchiveDuplicateMessages $False -KeepArchivingDataForDays 30

## EXAMPLE 2

Example 2 is a variation of the command shown in Example 1: in this case, however, the values of the ArchiveDuplicateMessages and KeepArchivingDataForDays properties are modified for all the archiving settings that have been configured at the site scope. To carry out this task, the command first uses the **Get-CsArchivingConfiguration** cmdlet and the Filter parameter to return a collection of all the archiving settings configured at the site scope; the filter value "site:\*" ensures that only settings that have an Identity that begins with the characters "site:" are returned. The filtered collection is then piped to the **Set-CsArchivingConfiguration** cmdlet, which modifies the two property values for each item in the collection.

    Get-CsArchivingConfiguration -Filter "site:*" | Set-CsArchivingConfiguration -ArchiveDuplicateMessages $False -KeepArchivingDataForDays 30

## EXAMPLE 3

In Example 3, all of the archiving configuration settings that allow both IM session and web conferencing archiving are modified; after the command completes, those settings will allow only for IM session archiving. To do this, the command first calls the **Get-CsArchivingConfiguration** cmdlet without any parameters in order to return a collection of all the archiving configuration settings currently in use in the organization. This collection is then piped to the **Where-Object** cmdlet, which picks out only those settings where the EnableArchiving property is equal to (-eq) "ImAndWebConf". The filtered collection is then piped to the **Set-CsArchivingConfiguration** cmdlet, which takes each item in the collection and changes the value of EnableArchiving to "ImOnly".

    Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"

## Detailed Description

Many organizations find it useful to keep a transcript of all the IM sessions and conferences their users participate in. For other organizations, it’s mandatory to keep such transcripts; for example, many organizations in the financial world are required by law to keep copies of all their electronic communications.

In order to archive instant messages, you must set up at least one 存档服务器. After the 存档服务器 is set up, you must perform two additional steps. First, you need to enable archiving at the global scope (for details, see the the **Set-CsArchivingConfiguration** cmdlet help topic). Optionally, you can also configure custom archiving settings for different sites.

Second, you must use archiving policies to indicate which users will have their IM sessions archived. IM sessions will not be archived unless a policy is in force that requires IM sessions to be archived.

When you install Lync Server, a collection of global archiving configuration settings will be created for you; by default, these settings will apply to your entire organization. Alternatively, you can use the **New-CsArchivingConfiguration** cmdlet to create custom configuration settings on a site-by-site basis. Either way, you can use the **Set-CsArchivingConfiguration** cmdlet to modify the property values of an existing collection or archiving configuration settings.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsArchivingConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsArchivingConfiguration"}

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
<td><p><em>ArchiveDuplicateMessages</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Specifies how &quot;cross-pool&quot; instant messages should be archived. Consider a simple example: Ken Myer (with an account in Pool 1) sends an instant message to Pilar Ackerman, who has an account in Pool 2. Pilar, in turn, sends a reply to Ken’s instant message. If ArchiveDuplicateMessages is set to False, then (based on a built-in algorithm) the session transcript will be logged in either Pool 1 or Pool 2, but not both. If ArchiveDuplicateMessages is set to True (the default value), the transcript will be logged in both pools.</p></td>
</tr>
<tr class="even">
<td><p><em>BlockOnArchiveFailure</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If True, then the IM service will be suspended any time instant messages cannot be archived. If set to False (the default value), IM will continue even if instant messages cannot be archived.</p></td>
</tr>
<tr class="odd">
<td><p><em>CachePurgingInterval</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Indicates how often (in hours) the system is purged of transcripts where none of the participants have been enabled for archiving. By design, all group IM sessions and conferencing sessions are recorded when they take place. At the specified interval, the system determines whether any of the participants in these sessions have been enabled for archiving. If the system finds a session where none of the participants have been enabled for archiving, then that transcript will be deleted from the database.</p>
<p>The CachePurgingInterval property can be set to any integer value between 4 and 168, inclusive. The default value is 24.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableArchiving</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.Archiving.EnableArchiving</p></td>
<td><p>Indicates which items (if any) are saved to the archiving database. Valid values are:</p>
<p>None. No items are archived to the database. This is the default value.</p>
<p>ImOnly. IM sessions are archived to the database.</p>
<p>ImAndWebConf. Both IM and web conferencing sessions are archived to the database.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableExchangeArchiving</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, Lync Server 2013 instant message and conferencing transcripts are stored in Microsoft Exchange Server 2013 rather than a separate SQL Server database. Note that if you enable Exchange archiving then users will be managed by the Exchange archiving policies instead of Lync Server 2013 archiving policies.</p>
<p>The default value is False.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnablePurging</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If True, then archived instant messages will periodically be removed from the database, provided that these instant messages: 1) are older than the value specified in the KeepArchivingDataForDays property; or, 2) have been exported and marked for deletion.</p>
<p>If False, instant messages will not automatically be deleted from the database.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might arise when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Represents the unique identifier of the collection of archiving configuration settings to be modified. To modify the global settings, either leave out this parameter or use the following syntax: -Identity global. To modify settings at the site scope, use the prefix &quot;site:&quot; followed by the site name. For example: -Identity &quot;site:Redmond&quot;.</p>
<p>To modify settings assigned to an individual Registrar pool (a feature available only in Lync Server 2013) use syntax similar to this:</p>
<p>-Identity &quot;service:Registrar:atl-cs-001.litwareinc.com&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>ArchivingSettings object</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
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
<td><p>If True, then the system will only purge instant messages that have been exported (and, as a result, have been marked for deletion). Instant messages that have not been exported will remain in the database, even if those instant messages are older than the value specified by the KeepArchivingDataForDays property.</p></td>
</tr>
<tr class="odd">
<td><p><em>PurgeHourOfDay</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Indicates the time of day when expired records are deleted from the archiving database. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day. This means that you can schedule purging to take place at 4:00 AM but you cannot schedule it to take place at, for instance, 4:30 AM or 4:15 AM. The default value is 2 (2:00 AM).</p>
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

Microsoft.Rtc.Management.WritableConfig.Settings.Archiving.ArchivingSettings object. The **Set-CsArchivingConfiguration** cmdlet accepts pipelined input of archiving configuration objects.

## Return Types

The **Set-CsArchivingConfiguration** cmdlet does not return a value or object. Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Archiving.ArchivingSettings object.

## 另请参阅

#### 其他资源

[Get-CsArchivingConfiguration](get-csarchivingconfiguration.md)  
[New-CsArchivingConfiguration](new-csarchivingconfiguration.md)  
[Remove-CsArchivingConfiguration](remove-csarchivingconfiguration.md)  
[Set-CsArchivingServer](set-csarchivingserver.md)

