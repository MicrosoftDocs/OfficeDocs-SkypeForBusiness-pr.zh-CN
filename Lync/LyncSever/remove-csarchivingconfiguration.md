---
title: Remove-CsArchivingConfiguration
TOCTitle: Remove-CsArchivingConfiguration
ms:assetid: d83b8935-079e-47d0-ba48-c95dd07965c0
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398951(v=OCS.15)
ms:contentKeyID: 49314411
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsArchivingConfiguration

 

_**上一次修改主题：** 2015-03-09_

Removes the specified collection of archiving settings. Archiving settings are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsArchivingConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 uses the **Remove-CsArchivingConfiguration** cmdlet to delete the archiving configuration settings with the identity site:Redmond.

    Remove-CsArchivingConfiguration -Identity site:Redmond

## EXAMPLE 2

The command shown in Example 2 removes all of the archiving configuration settings that have been configured at the site scope. To do this, the command first uses the **Get-CsArchivingConfiguration** cmdlet and the Filter parameter to return a collection of all of the settings configured at the site scope. This is done by using the filter value "site:\*", which limits the returned data to settings that have an Identity that begins with the characters "site:". The filtered collection is then piped to the **Remove-CsArchivingConfiguration** cmdlet, which deletes each item in that collection.

    Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration

## EXAMPLE 3

Example 3 deletes all the archiving configuration settings where the EnableArchiving property has been set to "None". To carry out this task, the **Get-CsArchivingConfiguration** cmdlet is called without any parameters in order to return a collection of all the archiving settings configured for use in the organization. This collection is then piped to the **Where-Object** cmdlet, which picks out only those settings where the EnableArchiving property is equal to "None". The filtered collection is then piped to the **Remove-CsArchivingConfiguration** cmdlet, which deletes each item in the collection.

    Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "None"} | Remove-CsArchivingConfiguration

## Detailed Description

Many organizations find it useful to keep a transcript of all the IM sessions and conferences their users participate in. For other organizations, it’s mandatory to keep such transcripts; for example, many organizations in the financial world are required by law to keep copies of all their electronic communications.

Lync Server gives you flexibility when it comes to archiving IM and web conferencing sessions. If you have deployed 存档服务器, you can use the various **CsArchivingConfiguration** cmdlets to enable and disable IM session archiving and to manage your archiving database. You can also suspend IM should archiving fail; this helps to ensure that you keep a record of all your electronic communications.

When you install Lync Server, a collection of global archiving settings will be created for you; by default, these settings will apply to your entire organization. Alternatively, you can use the **New-CsArchivingConfiguration** cmdlet to create custom configuration settings on a site-by-site basis. Any site-specific settings created using the **New-CsArchivingConfiguration** cmdlet can later be removed by using the **Remove-CsArchivingConfiguration** cmdlet. When you remove the settings for a site, the affected site will then be governed by the global settings.

Note that you can also run the **Remove-CsArchivingConfiguration** cmdlet against the global archiving settings. In that case, however, the settings will not be removed; that’s because you cannot delete the global settings. Instead, all the global properties will be reset to their default values. For example, suppose you have enabled IM session archiving at the global scope; sometime later, you run this command:

Remove-CsArchivingConfiguration -Identity global

Running that command will reset the property values for the global settings; that means that EnableArchiving will revert to its default value of None. In turn, that will disable archiving at the global scope.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsArchivingConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsArchivingConfiguration"}

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
<td><p>Unique identifier for the collection of archiving configuration settings to be removed. To remove the global collection, use the following syntax: -Identity global. (Note that you cannot actually remove the global settings; instead, you can only reset the properties to their default values.) To remove a site collection, use syntax similar to this: -Identity site:Redmond. To remove settings configured for an individual Registrar pool syntax like this:</p>
<p>-Identity &quot;service:Registrar:atl-cs-001.litwareinc.com&quot;</p>
<p>Note that pool-level settings are available only in Lync Server 2013.</p>
<p>You cannot use wildcards when specifying a policy Identity.</p></td>
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
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

Microsoft.Rtc.Management.WritableConfig.Settings.Archiving.ArchivingSettings object. The **Remove-CsArchivingConfiguration** cmdlet accepts pipelined input of archiving configuration objects.

## Return Types

The **Remove-CsArchivingConfiguration** cmdlet does not return a value or object. Instead, the cmdlet removes instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Archiving.ArchivingSettings object.

## 另请参阅

#### 其他资源

[Get-CsArchivingConfiguration](get-csarchivingconfiguration.md)  
[New-CsArchivingConfiguration](new-csarchivingconfiguration.md)  
[Set-CsArchivingConfiguration](set-csarchivingconfiguration.md)  
[Set-CsArchivingServer](set-csarchivingserver.md)

