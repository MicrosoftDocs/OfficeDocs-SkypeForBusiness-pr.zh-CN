---
title: Get-CsQoEConfiguration
TOCTitle: Get-CsQoEConfiguration
ms:assetid: e2ed87e0-a5ae-41a2-8572-bda0070c59dc
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399004(v=OCS.15)
ms:contentKeyID: 49314520
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsQoEConfiguration

 

_**上一次修改主题：** 2015-03-09_

Retrieves one or more collections of Quality of Experience (QoE) settings. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsQoEConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsQoEConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

This example uses the **Get-CsQoEConfiguration** cmdlet to return a collection of all the QoE settings configured for use in your organization.

    Get-CsQoEConfiguration

## EXAMPLE 2

Example 2 uses the Identity parameter to ensure that the **Get-CsQoEConfiguration** cmdlet returns only the QoE settings with the Identity site:Redmond.

    Get-CsQoEConfiguration -Identity site:Redmond

## EXAMPLE 3

In Example 3 the Filter parameter is used to return all the QoE settings that have been configured at the site scope. The wildcard "site:\*" returns all the QoE settings that have an Identity beginning with the string value site:. Settings that meet those criteria are settings that have been configured at the site scope.

    Get-CsQoEConfiguration -Filter site:*

## EXAMPLE 4

Example 4 returns a collection of all the QoE settings where the KeepQoEDataForDays property is less than 30 days. To do this, the command first uses the **Get-CsQoEConfiguration** cmdlet to return a collection of all the QoE settings configured in the organization. That collection is then piped to the **Where-Object** cmdlet, which applies a filter that limits the returned data to those settings that have a KeepQoEDataForDays value of less than 30 days.

    Get-CsQoEConfiguration | Where-Object {$_.KeepQoEDataForDays -lt 30}

## Detailed Description

QoE metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording. Use this cmdlet to retrieve settings that configure QoE at the global or site level.

QoE is part of the 监控服务器 role; therefore 监控服务器 must be deployed on your Lync Server installation before QoE recording takes effect or any QoE data can be collected.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsQoEConfiguration** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsQoEConfiguration"}

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
<td><p>Enables you to use wildcard characters in order to return a collection (or multiple collections) of QoE configuration settings. To return a collection of all the settings configured at the site scope, use this syntax: -Filter site:*. To return a collection of all the settings that have the string value &quot;Western&quot; somewhere in their Identity (the only property you can filter on) use this syntax: -Filter *Western*.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>The unique identifier of the settings you want to retrieve. Possible values are global and site:&lt;site name&gt;, where &lt;site name&gt; is the name of the site in your Lync Server deployment to which you want to apply the changes.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the settings from the local replica of the 中央管理存储.</p></td>
</tr>
</tbody>
</table>


## Input Types

None.

## Return Types

The **Get-CsQoEConfiguration** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Settings.QoE.QoESettings object.

## 另请参阅

#### 其他资源

[New-CsQoEConfiguration](new-csqoeconfiguration.md)  
[Remove-CsQoEConfiguration](remove-csqoeconfiguration.md)  
[Set-CsQoEConfiguration](set-csqoeconfiguration.md)

