---
title: Remove-CsDialInConferencingConfiguration
TOCTitle: Remove-CsDialInConferencingConfiguration
ms:assetid: 0c7f2a69-eeed-41bf-8ba7-5cc36dfdfa3c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398174(v=OCS.15)
ms:contentKeyID: 49311979
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsDialInConferencingConfiguration

 

_**上一次修改主题：** 2015-03-09_

Removes one or more collections of dial-in conferencing configuration settings. These settings determine how Lync Server responds when users join or leave a dial-in conference. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsDialInConferencingConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In Example 1, the dial-in conferencing configuration settings for the Redmond site are deleted.

    Remove-CSDialInConferencingConfiguration -Identity "site:Redmond"

## EXAMPLE 2

In Example 2, all the dial-in conferencing settings that have been configured at the site scope are deleted. To do this, the command first uses the **Get-CSDialInConferencingConfiguration** cmdlet and the Filter parameter to return a collection of all the dial-in conferencing settings that have been configured at the site scope. (The filter value "site:\*" ensures that only settings that have an Identity that begins with the string value "site:" are returned.) This filtered collection is then piped to the **Remove-CSDialInConferencingConfiguration** cmdlet, which removes each item in the collection.

    Get-CSDialInConferencingConfiguration -Filter "site:*" | Remove-CSDialInConferencingConfiguration

## EXAMPLE 3

In Example 3, all the dial-in conferencing configuration settings that do not use name recording are deleted. To carry out this task, the command first calls the **Get-CSDialInConferencingConfiguration** cmdlet without any parameters in order to return a collection of all the dial-in conferencing configuration settings currently in use in the organization. This collection is then piped to the **Where-Object** cmdlet, which picks out only those settings where the EnableNameRecording property is equal to False. In turn, this filtered collection is piped to the **Remove-CSDialInConferencingConfiguration** cmdlet, which deletes each item in the collection.

    Get-CSDialInConferencingConfiguration | Where-Object {$_.EnableNameRecording -eq $False} | Remove-CSDialInConferencingConfiguration

## Detailed Description

When users join (or leave) a dial-in conference, Lync Server can respond in different ways. For example, participants might be asked to record their name before they can enter the conference itself. Likewise, administrators can decide whether they want to have Lync Server announce that dial-in participants have either left or joined a conference.

These conference "join behaviors" are managed using dial-in conferencing configuration settings; these settings can be configured at the global scope or at the site scope. (Settings configured at the site scope take precedence over settings configured at the global scope.) When you install Lync Server, a global collection of dial-in conferencing configuration settings will be created for you. If you want to have different settings for a site (or set of sites), you can create those collections by using the **New-CSDialInConferencingConfiguration** cmdlet.

The **Remove-CSDialInConferencingConfiguration** cmdlet deletes any dial-in conferencing settings that have been configured at the site scope. When these site-specific settings are deleted, users in the affected sites will have their dial-in conferencing behaviors governed by the global settings.

You can also run the **Remove-CSDialInConferencingConfiguration** cmdlet against the global dial-in conferencing settings. If you do that, the global settings will not be removed; that’s because the global settings cannot be removed. Instead, all the properties within that collection of settings will be reset to their default values.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsDialInConferencingConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsDialInConferencingConfiguration"}

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
<td><p>Indicates the Identity of the dial-in conferencing configuration settings to be removed. To refer to the global settings, use this syntax: -Identity global. To refer to site settings, use syntax similar to this: -Identity site:Redmond. Note that you cannot use wildcards when specifying an Identity.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.DialInConferencingSettings.DialInConferencingConfiguration object. The **Remove-CSDialInConferencingConfiguration** cmdlet accepts pipelined instances of the dial-in conferencing configuration object.

## Return Types

None. Instead, the **Remove-CSDialInConferencingConfiguration** cmdlet deletes instances of the Microsoft.Rtc.Management.WritableConfig.Settings.DialInConferencingSettings.DialInConferencingConfiguration object.

## 另请参阅

#### 其他资源

[Get-CsDialInConferencingConfiguration](get-csdialinconferencingconfiguration.md)  
[New-CsDialInConferencingConfiguration](new-csdialinconferencingconfiguration.md)  
[Set-CsDialInConferencingConfiguration](set-csdialinconferencingconfiguration.md)

