---
title: Set-CsDialInConferencingConfiguration
TOCTitle: Set-CsDialInConferencingConfiguration
ms:assetid: 3300343f-c075-4b4f-aaa4-091dbf1fcd90
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425825(v=OCS.15)
ms:contentKeyID: 49312432
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsDialInConferencingConfiguration

 

_**上一次修改主题：** 2015-03-09_

Modifies settings that determine how Lync Server responds when users join or leave a dial-in conference. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsDialInConferencingConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsDialInConferencingConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-EnableNameRecording <$true | $false>] [-EntryExitAnnouncementsEnabledByDefault <$true | $false>] [-EntryExitAnnouncementsType <UseNames | ToneOnly>] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 modifies the EntryExitAnnoucements property for the dial-in configuration settings for the Redmond site. In this case, the EntryExitAnnouncementsType property is set to ToneOnly.

    Set-CsDialInConferencingConfiguration -Identity site:Redmond -EntryExitAnnouncementsType "ToneOnly"

## EXAMPLE 2

Example 2 modifies all the dial-in conferencing configurations settings in use in the organization. To do this, the command first uses the **Get-CsDialInConferencingConfiguration** cmdlet to return a collection of all dial-in conferencing settings. That collection is then piped to the **Set-CsDialInConferencingConfiguration** cmdlet, which sets the EnableNameRecording property for each item in the collection to True ($True).

    Get-CsDialInConferencingConfiguration | Set-CsDialInConferencingConfiguration -EnableNameRecording $True

## EXAMPLE 3

Example 3 modifies all the dial-in conferencing settings that have been configured at the site scope. To carry out this task, the command first uses the **Get-CsDialInConferencingConfiguration** cmdlet and the Filter parameter to return a collection of all the settings configured at the site scope; the filter value "site:\*" restricts returned data to settings that have an Identity beginning with the string value "site:". That filtered collection is then piped to the **Set-CsDialInConferencingConfiguration** cmdlet, which modifies the EnableNameRecording property and the EntryExitAnnouncementsType property for each item in the collection. When the command finishes running, all the dial-in conferencing settings configured at the site scope will have their EnableNameRecording property set to True and their EntryExitAnnoucements property set to "UseNames".

    Get-CsDialInConferencingConfiguration -Filter "site:*" | Set-CsDialInConferencingConfiguration -EnableNameRecording $True -EntryExitAnnouncementsType "UseNames"

## Detailed Description

When users join (or leave) a dial-in conference, Lync Server can respond in different ways. For example, participants might be asked to record their name before they can enter the conference itself. Likewise, administrators can decide whether they want to have Lync Server announce that dial-in participants have either left or joined a conference.

These conference "join behaviors" are managed using dial-in conferencing configuration settings; these settings can be configured at the global scope or at the site scope. When you first install Lync Server, the only dial-in conferencing configuration settings you will have are the ones at the global scope; however, you can create new settings at the site scope by using the **New-CsDialInConferencingConfiguration** cmdlet. In addition, you can modify any of these configuration settings (at either the global or site scopes) by using the **Set-CsDialInConferencingConfiguration** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsDialInConferencingConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsDialInConferencingConfiguration"}

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
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>EnableNameRecording</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Determines whether or not users are asked to record their name before entering the conference. Set to True to enable name recording; set to False to bypass name recording. The default value is True.</p></td>
</tr>
<tr class="odd">
<td><p><em>EntryExitAnnouncementsEnabledByDefault</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If set to True announcements will be played each time a participant enters or exits a conference. If set to False (the default value), entry and exit announcements will not be played.</p></td>
</tr>
<tr class="even">
<td><p><em>EntryExitAnnouncementsType</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.DialInConferencingSettings.EntryExitAnnouncementsType</p></td>
<td><p>Indicates the action taken by the system any time a participant enters or leaves a conference. (Announcements are made only if the EntryExitAnnouncementsEnabledByDefault is set to True.) Valid values are:</p>
<p>UseNames. The person's name is announced any time her or she enters or leaves a conference (for example, &quot;Ken Myer is exiting the conference&quot;).</p>
<p>ToneOnly. A tone is played any time a participant enters or leaves a conference.</p>
<p>The default value is UseNames.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Indicates the Identity of the dial-in conferencing configuration settings to be modified. To refer to the global settings, use this syntax: -Identity global. To refer to site settings, use syntax similar to this: -Identity site:Redmond. Note that you cannot use wildcards when specifying an Identity.</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSObject</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.DialInConferencingSettings.DialInConferencingConfiguration object. The **Set-CSDialInConferencingConfiguration** cmdlet accepts pipelined instances of the dial-in conferencing configuration object.

## Return Types

The **Set-CSDialInConferencingConfiguration** cmdlet does not return any objects or values. Instead, the cmdlet modifies existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.DialInConferencingSettings.DialInConferencingConfiguration object.

## 另请参阅

#### 其他资源

[Get-CsDialInConferencingConfiguration](get-csdialinconferencingconfiguration.md)  
[New-CsDialInConferencingConfiguration](new-csdialinconferencingconfiguration.md)  
[Remove-CsDialInConferencingConfiguration](remove-csdialinconferencingconfiguration.md)

