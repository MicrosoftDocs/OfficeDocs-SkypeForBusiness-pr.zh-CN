---
title: Get-CsDialInConferencingConfiguration
TOCTitle: Get-CsDialInConferencingConfiguration
ms:assetid: 75a959f7-5712-4dbc-b7ac-5a15b9b2f404
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398575(v=OCS.15)
ms:contentKeyID: 49313288
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsDialInConferencingConfiguration

 

_**上一次修改主题：** 2015-03-09_

Retrieves information about how Lync Server responds when users join or leave a dial-in conference. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsDialInConferencingConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsDialInConferencingConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

Example 1 returns a collection of all the dial-in conferencing configuration settings currently in use in the organization. Calling the **Get-CsDialInConferencingConfiguration** cmdlet without any additional parameters always returns the complete collection of dial-in conferencing settings.

    Get-CsDialInConferencingConfiguration

## EXAMPLE 2

Example 2 returns the dial-in conferencing configuration settings with the Identity site:Redmond.

    Get-CsDialInConferencingConfiguration -Identity site:Redmond

## EXAMPLE 3

In Example 3, the Filter parameter is used to return all the dial-in conferencing settings that have been configured at the site scope. The filter value "site:\*" instructs the **Get-CsDialInConferencingConfiguration** cmdlet to return only those settings where the Identity begins with the string value "site:". By design, any dial-conferencing settings that have an Identity beginning with "site:" represent settings configured at the site scope.

    Get-CsDialInConferencingConfiguration -Filter "site:*"

## EXAMPLE 4

Example 4 uses the the **Get-CsDialInConferencingConfiguration** cmdlet and the **Where-Object** cmdlet to return a collection of all the dial-in conferencing configuration settings where the EnableNameRecording property is set to False. To do this, the **Get-CsDialInConferencingConfiguration** cmdlet is called without any parameters in order to return a collection of all the dial-in conferencing settings. That collection is then piped to the **Where-Object** cmdlet, which picks out only those settings where the EnableNameRecording property is equal to False.

    Get-CsDialInConferencingConfiguration | Where-Object {$_.EnableNameRecording -eq $False}

## Detailed Description

When users join (or leave) a dial-in conference, Lync Server can respond in different ways. For example, participants might be asked to record their name before they can enter the conference itself. Likewise, administrators can decide whether they want to have Lync Server announce that dial-in participants have either left or joined a conference.

These conference "join behaviors" are managed using dial-in conferencing configuration settings; these settings can be configured at the global scope or at the site scope. (Settings configured at the site scope take precedence over settings configured at the global scope.) The **Get-CsDialInConferencingConfiguration** cmdlet enables you to retrieve information about the dial-in conferencing configuration settings currently in use in your organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsDialInConferencingConfiguration** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsDialInConferencingConfiguration"}

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
<td><p>Provides a way for you to use wildcard characters when specifying dial-in conferencing configuration settings. For example, to return a collection of all the configuration settings that have been applied at the site scope use this syntax: -Filter &quot;site:*&quot;. To return all the settings that have the term &quot;EMEA&quot; in their Identity use this syntax: -Filter &quot;*EMEA*&quot;. Note that the Filter parameter acts only on the Identity of the settings; you cannot filter on other dial-in conferencing configuration properties.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Indicates the Identity of the dial-in conferencing configuration settings to be retrieved. To refer to the global settings, use this syntax: -Identity global. To refer to site settings, use syntax similar to this: -Identity site:Redmond. You cannot use wildcards when specifying an Identity. To do that, use the Filter parameter instead.</p>
<p>If called without any parameters the <strong>Get-CsDialInConferencingConfiguration</strong> cmdlet returns information about all the dial-in conferencing configuration settings in use in your organization.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the dial-in conferencing data from the local replica of the 中央管理存储 rather than from the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsDialInConferencingConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsDialInConferencingConfiguration** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Settings.DialInConferencingSettings.DialInConferencingConfiguration object.

## 另请参阅

#### 其他资源

[New-CsDialInConferencingConfiguration](new-csdialinconferencingconfiguration.md)  
[Remove-CsDialInConferencingConfiguration](remove-csdialinconferencingconfiguration.md)  
[Set-CsDialInConferencingConfiguration](set-csdialinconferencingconfiguration.md)

