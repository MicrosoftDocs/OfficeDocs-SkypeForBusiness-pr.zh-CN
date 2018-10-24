﻿---
title: Set-CsDialInConferencingDtmfConfiguration
TOCTitle: Set-CsDialInConferencingDtmfConfiguration
ms:assetid: cc22353e-6c14-49b1-bf23-f952c100bfd8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398860(v=OCS.15)
ms:contentKeyID: 49314262
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsDialInConferencingDtmfConfiguration

 

_**上一次修改主题：** 2015-03-09_

Modifies the dual-tone multifrequency (DTMF) signaling settings used for dial-in conferencing. DTMF enables users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsDialInConferencingDtmfConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsDialInConferencingDtmfConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-AdmitAll <String>] [-AudienceMuteCommand <String>] [-CommandCharacter <String>] [-Confirm [<SwitchParameter>]] [-EnableDisableAnnouncementsCommand <String>] [-Force <SwitchParameter>] [-HelpCommand <String>] [-LockUnlockConferenceCommand <String>] [-MuteUnmuteCommand <String>] [-OperatorLineUri <String>] [-PrivateRollCallCommand <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 swaps the keys assigned to the command for enabling and disabling announcements (default value: 9) and the command for muting and unmuting all participants (default value: 4) for the global DTMF settings. To do this two different parameters are used: EnableDisableAnnoucementsCommand, which is given the parameter value 4; and AudienceMuteCommand, which is given the value 9. Because no Identity is specified, these changes will affect the global DTMF settings.

    Set-CsDialInConferencingDtmfConfiguration -Identity global -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9

## EXAMPLE 2

The command shown in Example 2 is a variation of the command shown in the first example. In this case, however, the changes affect the DTMF settings that have the Identity site:Redmond.

    Set-CsDialInConferencingDtmfConfiguration -Identity site:Redmond -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9

## EXAMPLE 3

The command shown in Example 3 disables the roll call command (the ability to play back a list of all the people participating in the conference) for the Redmond site. To disable this command, the PrivateRollCallCommand parameter is included, with the parameter value set to $Null. This means that no keypad key will be associated with the command, which makes the command unavailable to users.

    Set-CsDialInConferencingDtmfConfiguration -Identity "site:Redmond" -PrivateRollCallCommand $Null

## EXAMPLE 4

Example 4 is a variation on Example 3: in this example, the roll call command is disabled for all the DTMF settings configured at the site scope. To do this, the command first uses the **Get-CsDialInConferencingDtmfConfiguration** cmdlet and the Filter parameter to return a collection of all the settings configured at the site scope; the filter value "site:\*" limits the returned data to those settings where the Identity begins with the characters "site:". This filtered collection is then piped to the **Set-CsDialInConferencingDtmfConfiguration** cmdlet, which sets the value of the PrivateRollCallCommand property to null ($Null).

    Get-CsDialInConferencingDtmfConfiguration -Filter "site:*" | Set-CsDialInConferencingDtmfConfiguration -PrivateRollCallCommand $Null

## Detailed Description

Lync Server enables users to join conferences by dialing in over the telephone. Dial-in users are not able to view video or exchange instant messages with other conference attendees, but they are able to fully participate in the audio portion of the meeting.

In addition to being able to join a conference, users are also able to manage selected portions of that conference by using their telephone keypad. (The specific conference settings users can and cannot manage depend on whether or not the user is a presenter.) For example, by default users can press the 6 key on their keypad to mute or unmute themselves. Participants can privately play the names of all the other people attending the meeting, while presenters can do such things as mute and unmute all the meeting participants and enable or disable the announcement that is played any time someone joins or leaves a conference.

The ability to make selections like these using a telephone keypad is known as dual-tone multifrequency (DTMF) signaling: if you have ever dialed a phone number and been instructed to do something along the order of "Press 1 for English or press 2 for Spanish," then you have used DTMF signaling.

The **Set-CsDialInConferencingDtmfConfiguration** cmdlet enables you to modify the keys used to trigger the commands supported in a Lync Server dial-in conference.

When modifying the DTMF commands keep two things in mind. First, you can only use the numeric keys 0 through 9; any other keys that might be found on your keypad (such as the \# key) are not allowed. There is one exception to that rule: the CommandCharacter parameter allows you to use only the asterisk key (\*), or the pound key (\#); you cannot assign a numeric value to the CommandCharacter parameter. However, all the other command parameters will only accept numeric values.

Second, commands must be assigned unique keys; for example, the 4 key cannot be used both to mute and unmute yourself and to lock and unlock a conference. That means that, when modifying the keys assigned to a command, you might want to swap the keys used by two different commands. For example, if you want to assign the 4 key to EnableDisableAnnouncementsCommand (default value: 9) you should, in the same command, assign the 9 key to AudienceMuteCommand.

To disable a command, set its value to Null ($Null).

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsDialInConferencingDtmfConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsDialInConferencingDtmfConfiguration"}

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
<td><p><em>AdmitAll</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Indicates the key to be pressed in order to allow all the users in the lobby to immediately join the conference. The default value is 8.</p></td>
</tr>
<tr class="even">
<td><p><em>AudienceMuteCommand</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Indicates the key a presenter can press to mute everyone else in the conference (that is, everyone other than the presenter will be muted). The default key is 4.</p></td>
</tr>
<tr class="odd">
<td><p><em>CommandCharacter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Indicates the key to be pressed at the beginning of a command. The default key is the asterisk (*); the only other allowed value is the pound key (#).</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableDisableAnnouncementsCommand</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Indicates the key to be pressed to enable or disable announcements each time someone joins or leaves the conference. The default key is 9.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>HelpCommand</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Indicates the key to be pressed in order to privately play a description of all the DTMF commands. The default key is 1.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Indicates the unique identifier for the collection of DTMF settings you want to modify. To refer to the global settings, use this syntax: -Identity global. To refer to a collection configured at the site scope, use syntax similar to this: -Identity site:Redmond. Note that you cannot use wildcards when specifying an Identity.</p>
<p>If this parameter is not specified, then the <strong>Set-CsDialInConferencingDtmfConfiguration</strong> cmdlet will modify the global DTMF settings.</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>DialInConferencingDtmfConfiguration object</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
</tr>
<tr class="even">
<td><p><em>LockUnlockConferenceCommand</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Indicates the key to be pressed to lock or unlock a conference. If a conference is locked then no new participants will be allowed to join that conference, at least not until the conference has been unlocked. The default key is 7.</p></td>
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
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

Microsoft.Rtc.Management.WritableConfig.Settings.DialInConferencingSettings.DialInConferencingDtmfConfiguration object. The **Set-CsDialInConferencingDtmfConfiguration** cmdlet accepts pipelined instances of the dial-in conference DTMF configuration object.

## Return Types

The **Set-CsDialInConferencingDtmfConfiguration** cmdlet does not return a value or object. Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.WritableConfig.Settings.DialInConferencingSettings.DialInConferencingDtmfConfiguration object.

## 另请参阅

#### 其他资源

[Get-CsDialInConferencingDtmfConfiguration](get-csdialinconferencingdtmfconfiguration.md)  
[New-CsDialInConferencingDtmfConfiguration](new-csdialinconferencingdtmfconfiguration.md)  
[Remove-CsDialInConferencingDtmfConfiguration](remove-csdialinconferencingdtmfconfiguration.md)

