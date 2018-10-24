---
title: Set-CsAVEdgeConfiguration
TOCTitle: Set-CsAVEdgeConfiguration
ms:assetid: b410164b-b47d-450c-8048-983cac4be624
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412869(v=OCS.15)
ms:contentKeyID: 49313994
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsAVEdgeConfiguration

 

_**上一次修改主题：** 2015-03-09_

Enables you to modify configuration settings for computers running the A/V 边缘服务 (these computers are also known as A/V Edge servers). An A/V Edge server enables internal users to share audio and video data with external users (that is, users who are not logged on to your internal network), as well as exchange files and participate in desktop sharing sessions. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsAVEdgeConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsAVEdgeConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-MaxBandwidthPerPortKb <UInt32>] [-MaxBandwidthPerUserKb <UInt32>] [-MaxTokenLifetime <TimeSpan>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In Example 1, the command modifies the MaxTokenLifetime property for the global A/V Edge configuration settings. In this example, the maximum token lifetime is set to 4 hours (04 hours : 00 minutes : 00 seconds).

    Set-CsAVEdgeConfiguration -Identity global -MaxTokenLifetime "04:00:00"

## Detailed Description

An A/V Edge server provides a way for audio and video traffic to be exchanged across an organization’s firewall. Among other things, this enables users to use Lync Server across the Internet, and then exchange audio and video data with users who have logged onto the system from inside the firewall. 边缘服务器 configuration settings can be assigned at the global scope, the site scope, and the service scope. These configuration settings enable administrators to do such things as manage the amount of time that user authentication is valid before it must be renewed, and to limit the amount of bandwidth that can be used by a single user or a single port.

The **Set-CsAVEdgeConfiguration** cmdlet provides a way for you to modify the A/V Edge configuration settings currently in use in your organization. However, unless instructed by Microsoft support personnel, it is recommended that administrators do not modify the default A/V Edge settings.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsAVEdgeConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsAVEdgeConfiguration"}

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
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the collection of A/V Edge configuration settings to be modified. To modify the global collection, use the following syntax: -Identity global. To modify a site collection use syntax similar to this: -Identity site:Redmond. Settings configured at the service scope should be referred to using syntax similar to this: -Identity service:EdgeServer:atl-cs-001.litwareinc.com.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>MediaRelaySettings object</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
</tr>
<tr class="odd">
<td><p><em>MaxBandwidthPerPortKb</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Indicates the maximum amount of bandwidth (in kilobits per second) that can be allocated to a single port. The maximum bandwidth can be set to any integer value between 1 and 4294967296 (4096 gigabits) per second; the default value is 3000.</p></td>
</tr>
<tr class="even">
<td><p><em>MaxBandwidthPerUserKb</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Indicates the maximum amount of bandwidth (in kilobits per second) that can be allocated to any one user. The maximum bandwidth can be set to any integer value between 1 and 4294967296 (4096 gigabits) per second; the default value is 10000.</p></td>
</tr>
<tr class="odd">
<td><p><em>MaxTokenLifetime</em></p></td>
<td><p>Optional</p></td>
<td><p>System.TimeSpan</p></td>
<td><p>The maximum amount of time that an authentication token can be used before it expires and must be renewed. Token lifetimes are expressed using the following format: Days.Hours:Minutes:Seconds. For example, 13 days must be expressed like this, with a period (.) following the number of days, and colons (:) used to separate the hours, minutes, and seconds:</p>
<p>13.00:00:00</p>
<p>The default value of 8 hours must be expressed like this:</p>
<p>08:00:00</p>
<p>The minimum allowed token lifetime is 1 minute (00:01:00); the maximum allowed lifetime is 180 days (180.00:00:00).</p>
<p></p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.Edge.MediaRelaySettings object. The **Set-CsAVEdgeConfiguration** cmdlet accepts pipelined input of media relay settings objects.

## Return Types

The **Set-CsAVEdgeConfiguration** cmdlet does not return a value or object. Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Edge.MediaRelaySettings object.

## 另请参阅

#### 其他资源

[Get-CsAVEdgeConfiguration](get-csavedgeconfiguration.md)  
[New-CsAVEdgeConfiguration](new-csavedgeconfiguration.md)  
[Remove-CsAVEdgeConfiguration](remove-csavedgeconfiguration.md)

