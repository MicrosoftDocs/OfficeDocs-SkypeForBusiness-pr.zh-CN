---
title: New-CsDialInConferencingDtmfConfiguration
TOCTitle: New-CsDialInConferencingDtmfConfiguration
ms:assetid: 2e373bab-fc4c-4b8b-96e7-fc23ac3bcf47
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425792(v=OCS.15)
ms:contentKeyID: 49312370
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsDialInConferencingDtmfConfiguration

 

_**上一次修改主题：** 2015-03-09_

Creates a new collection of dual-tone multifrequency (DTMF) signaling settings used for dial-in conferencing. DTMF enables users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsDialInConferencingDtmfConfiguration -Identity <XdsIdentity> [-AdmitAll <String>] [-AudienceMuteCommand <String>] [-CommandCharacter <String>] [-Confirm [<SwitchParameter>]] [-EnableDisableAnnouncementsCommand <String>] [-Force <SwitchParameter>] [-HelpCommand <String>] [-InMemory <SwitchParameter>] [-LockUnlockConferenceCommand <String>] [-MuteUnmuteCommand <String>] [-OperatorLineUri <String>] [-PrivateRollCallCommand <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 creates a new set of DTMF configuration settings for the Redmond site. In this example, the MuteUnmuteCommand property is set to 4 and the AudienceMuteCommand property is set to 6.

    New-CSDialInConferencingDtmfConfiguration -Identity site:Redmond -MuteUnmuteCommand 4 -AudienceMuteCommand 6

## EXAMPLE 2

Example 2 creates a new set of DTMF configuration settings for the Redmond site. In this example, the AdmitAll property is disabled; that’s done by using the AdmitAll parameter and setting the parameter value to null.

    New-CSDialInConferencingDtmfConfiguration -Identity site:Redmond -AdmitAll $Null

## EXAMPLE 3

Example 3 shows how you can use the InMemory parameter to create an in-memory-only instance of a DTMF configuration settings collection, modify those settings, and then use the **Set-CSDialInConferencingDtmfConfiguration** cmdlet to create an actual collection with the Identity site:Redmond. To do this, the first command in the example creates a new in-memory-only instance of a DTMF configuration settings collection, storing that instance in a variable named $x. These settings will exist only in memory; if you close Windows PowerShell or delete the variable $x the settings will disappear and will never be applied to the Redmond site.

The next 3 commands modify properties of this "virtual" DTMF settings collection: commands 2, 3, and 4 assign new values to AdmitAll, MuteUnmuteCommand, and AudienceMuteCommand, respectively. The final command then uses the **Set-CSDialInConferencingDtmfConfiguration** cmdlet and the Instance parameter to transform the virtual settings stored in $x into an actual collection of settings configured for the Redmond site.

    $x = New-CSDialInConferencingDtmfConfiguration -Identity site:Redmond -InMemory
    $x.AdmitAll = $Null
    $x.MuteUnmuteCommand = 4 
    $x.AudienceMuteCommand = 6
    Set-CSDialInConferencingDtmfConfiguration -Instance $x

## Detailed Description

Lync Server enables users to join conferences by dialing in over the telephone. Dial-in users are not able to view video or exchange instant messages with other conference attendees, but they are able to fully participate in the audio portion of the meeting.

In addition to being able to join a conference, users are also able to manage selected portions of that conference by using their telephone keypad. (The specific conference settings users can and cannot manage depend on whether or not the user is a presenter.) For example, by default users can press the 6 key on their keypad to mute or unmute themselves. Participants can privately play the names of all the other people attending the meeting, while presenters can do such things as mute and unmute all the meeting participants and enable or disable the announcement that is played any time someone joins or leaves a conference.

The ability to make selections like these using a telephone keypad is known as dual-tone multi-frequency (DTMF) signaling: if you have ever dialed a phone number and been instructed to do something along the order of "Press 1 for English or press 2 for Spanish," then you have used DTMF signaling.

When you install Lync Server, a global collection of DTMF settings is created for you. In addition to those global settings, you can use the **New-CSDialInConferencingDtmfConfiguration** cmdlet to create custom settings on a site-by-site basis. For example, you can create a new collection of settings for the Redmond site (and only the Redmond site) that uses the 4 key instead of the 6 key as the mute/unmute key. Note that any settings you configure at the site scope take precedence over the settings configured at the global scope. As a result, users in the Redmond site will use the 4 key as the mute/unmute key even though the global settings use the 6 key for muting and unmuting.

You can have only one collection of DTMF settings and one global collection per site. For example, suppose you already have a collection with the Identity site:Redmond and you then try to run this command:

New- CSDialInConferencingDtmfConfiguration –Identity site:Redmond

That command will fail, because the site:Redmond collection already exists. If you want to modify the settings for the Redmond site, either use the **Set-CSDialInConferencingDtmfConfiguration** cmdlet, or remove the existing collection and then create a new collection that uses the Identity site:Redmond.

When configuring values for the DTMF commands, keep two things in mind. First, you can only use the numeric keys 0 through 9 and the asterisk (\*); any other keys that might be found on your keypad (such as the \# key) are not allowed. (With one exception: the CommandCharacter key accepts only the \* key or the \# key.) Second, commands must be assigned unique keys; for example, the 4 key cannot be used both to mute and unmute yourself and to lock and unlock a conference. That means that, when modifying the keys assigned to a command, you might need to swap the keys used by two different commands. For example, if you want to assign the 4 key to EnableDisableAnnouncementsCommand (default value: 9), then you should, in the same command, assign the 9 key to AudienceMuteCommand.

To disable a command, set its value to Null ($Null).

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsDialInConferencingDtmfConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsDialInConferencingDtmfConfiguration"}

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
<td><p>Unique identifier to be assigned to the new collection of DTMF configuration settings. Because you can only create new collections at the site scope, the Identity will always be the prefix &quot;site:&quot; followed by the site name; for example &quot;site:Redmond&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>AdmitAll</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Indicates the key to be pressed in order to allow all the users in the lobby to immediately join the conference. The default value is 8.</p></td>
</tr>
<tr class="odd">
<td><p><em>AudienceMuteCommand</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Indicates the key a presenter can press to mute or unmute everyone else in the conference (that is, everyone other than the presenter will be muted or unmuted). The default key is 4.</p></td>
</tr>
<tr class="even">
<td><p><em>CommandCharacter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Indicates the key to be pressed at the beginning of a command. The default key is the asterisk (*). The only other allowed value is #.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>EnableDisableAnnouncementsCommand</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Indicates the key to be pressed to enable or disable announcements each time someone joins or leaves the conference. The default key is 9.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>HelpCommand</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Indicates the key to be pressed in order to privately play a description of all the DTMF commands. The default key is 1.</p></td>
</tr>
<tr class="odd">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="even">
<td><p><em>LockUnlockConferenceCommand</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Indicates the key to be pressed to lock or unlock a conference. If a conference is locked, then no new participants will be allowed to join that conference, at least not until the conference has been unlocked. The default key is 7.</p></td>
</tr>
<tr class="odd">
<td><p><em>MuteUnmuteCommand</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Indicates the key to be pressed to mute or unmute yourself; the same key is used to toggle back and forth between muting and unmuting. The default key is 6.</p></td>
</tr>
<tr class="even">
<td><p><em>OperatorLineUri</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Phone number that the dial-in conferencing auto-attendant will connect a PSTN user to any time that user presses *0 on their telephone keypad. Pressing *0 is designed to connect dial-in conferencing users to operator assistance.</p></td>
</tr>
<tr class="odd">
<td><p><em>PrivateRollCallCommand</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Indicates the key to be pressed to privately play the name of each conference participant. The default key is 3.</p></td>
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

None. The **New-CsDialInConferencingDtmfConfiguration** cmdlet does not accept pipelined input.

## Return Types

Creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.DialInConferencingSettings.DialInConferencingDtmfConfiguration object.

## 另请参阅

#### 其他资源

[Get-CsDialInConferencingDtmfConfiguration](get-csdialinconferencingdtmfconfiguration.md)  
[Remove-CsDialInConferencingDtmfConfiguration](remove-csdialinconferencingdtmfconfiguration.md)  
[Set-CsDialInConferencingDtmfConfiguration](set-csdialinconferencingdtmfconfiguration.md)

