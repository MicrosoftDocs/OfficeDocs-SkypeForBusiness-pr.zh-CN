---
title: Get-CsDialInConferencingDtmfConfiguration
TOCTitle: Get-CsDialInConferencingDtmfConfiguration
ms:assetid: 764741e4-c1cb-4627-8774-95cf08f6cf98
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398578(v=OCS.15)
ms:contentKeyID: 49313281
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsDialInConferencingDtmfConfiguration

 

_**上一次修改主题：** 2015-03-09_

Returns the dual-tone multifrequency (DTMF) signaling settings used for dial-in conferencing. DTMF enables users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsDialInConferencingDtmfConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsDialInConferencingDtmfConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

The command show in Example 1 returns the DTMF settings for the Redmond site.

    Get-CsDialInConferencingDtmfConfiguration -Identity site:Redmond

## EXAMPLE 2

Example 2 returns a collection of all the DTMF settings, and then, for each item in the collection, displays the value of the key to be pressed in order to privately play a description of DTMF commands. To do this, the **Get-CsDialInConferencingDtmfConfiguration** cmdlet is called in order to return a collection of all the property values for all the DTMF settings currently in use in the organization. That collection is then piped to the **Select-Object** cmdlet, which picks two properties (Identity and HelpCommand) to be displayed on the screen.

    Get-CsDialInConferencingDtmfConfiguration | Select-Object Identity, HelpCommand

## EXAMPLE 3

The command shown in Example 3 returns all the DTMF settings that have been configured at the site scope. This is done by including the Filter parameter and the filter value "site:\*". That filter value limits the returned data to settings that have an Identity that begins with the characters "site:". By definition, those are settings configured at the site scope.

    Get-CsDialInConferencingDtmfConfiguration -Filter "site:*"

## EXAMPLE 4

Example 4 returns all the DTMF configuration settings where the AdmitAll property is not equal to 8 (the default value). To accomplish this task, the **Get-CsDialInConferencingDtmfConfiguration** cmdlet is first called without any parameters in order to return a collection of all the DTMF settings currently in use. This collection is then piped to the **Where-Object** cmdlet, which picks out only those settings where the AdmitAll property is not equal to 8.

    Get-CsDialInConferencingDtmfConfiguration | Where-Object {$_.AdmitAll -ne 8}

## Detailed Description

Lync Server enables users to join conferences by dialing in over the telephone. Dial-in users are not able to view video or exchange instant messages with other conference attendees, but they are able to fully participate in the audio portion of the meeting.

In addition to being able to join a conference, users are also able to manage selected portions of that conference by using their telephone keypad. (The specific conference settings users can and cannot manage depend on whether or not the user is a presenter.) For example, by default users can press the 6 key on their keypad to mute or unmute themselves. Participants can privately play the names of all the other people attending the meeting, while presenters can do such things as mute and unmute all the meeting participants and enable/disable the announcement that is played any time someone joins or leaves a conference.

The ability to make selections using a telephone keypad is known as dual-tone multifrequency (DTMF) signaling: if you have ever dialed a phone number and been instructed to do something along the order of "Press 1 for English or press 2 for Spanish," then you have used DTMF signaling. The **Get-CsDialInConferencingDtmfConfiguration** cmdlet enables you to retrieve a list of all the available DTMF commands as well as the keys used to carry out those commands.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsDialInConferencingDtmfConfiguration** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsDialInConferencingDtmfConfiguration"}

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
<td><p><em>Filter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to use wildcard characters in order to return a collection (or collections) of DTMF configuration settings. To return a collection of all the settings configured at the site scope, use this syntax: -Filter site:*. To return a collection of all the settings that have the string value &quot;EMEA&quot; somewhere in their Identity (the only property you can filter for), use this syntax: -Filter *EMEA*.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Indicates the unique identifier for the collection of DTMF settings you want to return. To refer to the global settings, use this syntax: -Identity global. To refer to a collection configured at the site scope, use syntax similar to this: -Identity site:Redmond. Note that you cannot use wildcards when specifying an Identity. If you need to use wildcards, then use the Filter parameter instead.</p>
<p>If this parameter is not specified, then the <strong>Get-CsDialInConferencingDtmfConfiguration</strong> cmdlet returns a collection of all the DTMF configuration settings in use in the organization.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the DTMF configuration data from the local replica of the 中央管理存储 rather than from the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsDialInConferencingDtmfConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsDialInConferencingDtmfConfiguration** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Settings.DialInConferencingSettings.DialInConferencingDtmfConfiguration object.

## 另请参阅

#### 其他资源

[New-CsDialInConferencingDtmfConfiguration](new-csdialinconferencingdtmfconfiguration.md)  
[Remove-CsDialInConferencingDtmfConfiguration](remove-csdialinconferencingdtmfconfiguration.md)  
[Set-CsDialInConferencingDtmfConfiguration](set-csdialinconferencingdtmfconfiguration.md)

