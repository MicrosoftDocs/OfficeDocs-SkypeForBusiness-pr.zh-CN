﻿---
title: Remove-CsDialInConferencingDtmfConfiguration
TOCTitle: Remove-CsDialInConferencingDtmfConfiguration
ms:assetid: 3cd6313c-fd0a-4fb2-bacd-b1bdf2a59430
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425894(v=OCS.15)
ms:contentKeyID: 49312573
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsDialInConferencingDtmfConfiguration

 

_**上一次修改主题：** 2015-03-09_

Removes an existing collection of dual-tone multifrequency (DTMF) signaling settings used for dial-in conferencing. DTMF enables users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsDialInConferencingDtmfConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 deletes the collection of DTMF configuration settings that has the Identity site:Redmond.

    Remove-CSDialInConferencingDtmfConfiguration -Identity site:Redmond

## EXAMPLE 2

The command shown in Example 2 deletes all the DTMF settings that have been configured at the site scope. To perform this task, the command first uses the **Get-CSDialInConferencingDtmfConfiguration** cmdlet and the Filter parameter to return a collection of all the DTMF settings that have been configured at the site scope; the filter value "site:\*" ensures that only settings that have an Identity that begins with the string value "site:" are returned. This filtered collection is then piped to the **Remove-CSDialInConferencingConfiguration** cmdlet, which removes each item in that collection.

    Get-CSDialInConferencingDtmfConfiguration -Filter "site:*" | Remove-CSDialInConferencingDtmfConfiguration

## EXAMPLE 3

In Example 3, the **Remove-CSDialInConferencingDtmfConfiguration** cmdlet is used to delete all the DTMF settings where the PrivateRollCallCommand property is equal to a null value. (That is, where the private roll call command has been disabled.) To do this, the command first uses the **Get-CSDialInConferencingDtmfConfiguration** cmdlet to return a collection of all the DTMF settings currently in use in the organization. This collection is then piped to the **Where-Object** cmdlet, which selects only those settings where PrivateRollCallCommand is equal to a null value. The filtered collection is then piped to the **Remove-CSDialInConferencingDtmfConfiguration** cmdlet, which deletes each item in the collection.

    Get-CSDialInConferencingDtmfConfiguration | Where-Object {$_.PrivateRollCallCommand -eq $Null} | Remove-CSDialInConferencingDtmfConfiguration

## Detailed Description

Lync Server enables users to join conferences by dialing in over the telephone. Dial-in users are not able to view video or exchange instant messages with other conference attendees, but they are able to fully participate in the audio portion of the meeting.

In addition to being able to join a conference, users are also able to manage selected portions of that conference by using their telephone keypad. (The specific conference settings users can and cannot manage depend on whether or not the user is a presenter.) For example, by default users can press the 6 key on their keypad to mute or unmute themselves. Participants can privately play the names of all the other people attending the meeting, while presenters can do such things as mute and unmute all the meeting participants and enable/disable the announcement that is played any time someone joins or leaves a conference.

The ability to make selections like these by using a telephone keypad is known as dual-tone multifrequency (DTMF) signaling: if you have ever dialed a phone number and been instructed to do something along the order of "Press 1 for English or press 2 for Spanish," then you have used DTMF signaling.

When you install Lync Server, a global collection of DTMF settings is created for you. In addition to those global settings, you can use the **New-CSDialInConferencingDtmfConfiguration** cmdlet to create custom settings on a site-by-site basis. Settings you create at the site scope can later be removed by using the **Remove-CSDialInConferencingDtmfConfiguration** cmdlet. When you remove DTMF settings applied at the site scope, users in the affected site will automatically fall under the jurisdiction of the global DTMF configuration settings.

You can also run the **Remove-CSDialInConferencingDtmfConfiguration** cmdlet against the global settings. If you do that, however, the global settings will not be removed; that’s because you cannot remove the global DTMF settings. Instead, the properties in the global settings will be reset to their default values. For example, suppose you have modified the global settings to make the 4 key the mute/unmute key. If you now run the **Remove-CSDialInConferencingDtmfConfiguration** cmdlet against the global settings, the value of the mute/unmute key will be reset to the default value 6.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsDialInConferencingDtmfConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsDialInConferencingDtmfConfiguration"}

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
<td><p>Unique identifier for the collection of DTMF settings to be removed. To &quot;remove&quot; the global settings, use this syntax: -Identity global. (As noted earlier, you cannot actually remove the global setting; all you can do is reset the properties to their default values.) To remove a collection configured at the site scope, use syntax similar to this: -Identity site:Redmond. You cannot use wildcards when specifying an Identity</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.DialInConferencingSettings.DialInConferencingDtmfConfiguration object. The **Remove-CsDialInConferencingDtmfConfiguration** cmdlet accepts pipelined instances of the dial-in conference DTMF configuration object.

## Return Types

None. Instead, the **Remove-CSDialInConferencingDtmfConfiguration** cmdlet deletes instances of the Microsoft.Rtc.Management.WritableConfig.Settings.DialInConferencingSettings.DialInConferencingDtmfConfiguration object.

## 另请参阅

#### 其他资源

[Get-CsDialInConferencingDtmfConfiguration](get-csdialinconferencingdtmfconfiguration.md)  
[New-CsDialInConferencingDtmfConfiguration](new-csdialinconferencingdtmfconfiguration.md)  
[Set-CsDialInConferencingDtmfConfiguration](set-csdialinconferencingdtmfconfiguration.md)

