---
title: Remove-CsQoEConfiguration
TOCTitle: Remove-CsQoEConfiguration
ms:assetid: 3b50e857-c524-4aad-b191-d324fc7c837c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425879(v=OCS.15)
ms:contentKeyID: 49312555
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsQoEConfiguration

 

_**上一次修改主题：** 2015-03-09_

Removes a collection of QoE (Quality of Experience) settings. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsQoEConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 uses the **Remove-CsQoEConfiguration** cmdlet to remove the QoE settings assigned to the site Redmond. Using the Identity parameter ensures that only the settings assigned to the specified site will be removed.

    Remove-CsQoEConfiguration -Identity site:Redmond

## EXAMPLE 2

The command shown in Example 2 removes all the QoE settings that have been assigned at the site scope. To do this, the command first uses the **Get-CsQoEConfiguration** cmdlet and the Filter parameter to retrieve the appropriate QoE settings; the wildcard string "site:\*" ensures that only those settings that have an identity beginning with the string value site: are returned. The filtered collection is then passed to the **Remove-CsQoEConfiguration** cmdlet, which deletes all the items in the collection.

    Get-CsQoEConfiguration -Filter site:* | Remove-CsQoEConfiguration

## EXAMPLE 3

In Example 3, any QoE settings where the KeepQoEDataForDays property is less than 30 are deleted. To carry out this task, the command calls the **Get-CsQoEConfiguration** cmdlet without any parameters in order to return a collection of all the QoE settings currently in use in the organization. This collection is then piped to the **Where-Object** cmdlet, which picks out only those settings where the KeepQoEDataForDays property is less than (-lt) 30 days. In turn, the filtered collection is piped to the **Remove-CsQoEConfiguration** cmdlet, which deletes each item in that collection.

    Get-CsQoEConfiguration | Where-Object {$_.KeepQoEDataForDays -lt 30} | Remove-CsQoEConfiguration

## Detailed Description

QoE metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording. Use this cmdlet to remove settings that configure QoE at the site level. Calling this cmdlet on the global QoE configuration will reset all properties to the defaults.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsQoEConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsQoEConfiguration"}

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
<td><p>The unique identifier of the settings you want to remove. Possible values are global and site:&lt;site name&gt;, where &lt;site name&gt; is the name of the site in your Lync Server deployment with the settings to be removed.</p></td>
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
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.QoE.QoESettings object. Accepts pipelined input of QoE configuration objects.

## Return Types

This cmdlet does not return a value or object. Instead, it removes instances of the Microsoft.Rtc.Management.WritableConfig.Settings.QoE.QoESettings object.

## 另请参阅

#### 其他资源

[New-CsQoEConfiguration](new-csqoeconfiguration.md)  
[Set-CsQoEConfiguration](set-csqoeconfiguration.md)  
[Get-CsQoEConfiguration](get-csqoeconfiguration.md)

