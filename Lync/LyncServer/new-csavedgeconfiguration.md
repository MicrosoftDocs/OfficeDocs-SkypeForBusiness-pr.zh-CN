---
title: New-CsAVEdgeConfiguration
TOCTitle: New-CsAVEdgeConfiguration
ms:assetid: b6bcf426-9037-4679-99dc-e94bfb8f72a6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412884(v=OCS.15)
ms:contentKeyID: 49314016
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsAVEdgeConfiguration

 

_**上一次修改主题：** 2015-03-09_

Creates a new collection of configuration settings for computers running the A/V 边缘服务 (these computers are also known as A/V Edge servers). An A/V Edge server enables internal users to share audio and video data with external users (that is, users who are not logged on to your internal network). 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsAVEdgeConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-MaxBandwidthPerPortKb <UInt32>] [-MaxBandwidthPerUserKb <UInt32>] [-MaxTokenLifetime <TimeSpan>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 creates a new collection of A/V Edge configuration settings for the Redmond site. In this example, the MaxTokenLifetime property is set to 4 hours (04 hours : 00 minutes : 00 seconds).

    New-CsAVEdgeConfiguration -Identity site:Redmond -MaxTokenLifetime "04:00:00"

## EXAMPLE 2

Example 2 demonstrates how you can create a new collection of A/V Edge configuration settings in memory, and then later transform those virtual settings into an actual collection of A/V Edge settings. To do this, the first command in the example creates a new collection of settings for the Redmond site; the InMemory parameter is added to ensure that these settings are created in memory only and are not immediately applied to the Redmond site. (Because these settings exist in memory only, they must be stored in a variable, in this case, a variable named $x.)

In the second command, the value of the MaxTokenLifetime property is set to 4 hours (04 hours : 00 minutes : 00 seconds). The third command then uses the **Set-CsAVEdgeConfiguration** cmdlet to apply the settings stored in $x to the Redmond site.

    $x = New-CsAVEdgeConfiguration -Identity site:Redmond -InMemory
    $x.MaxTokenLifetime = "04:00:00"
    Set-CsAVEdgeConfiguration -Instance $x

## Detailed Description

An A/V Edge server provides a way for audio and video traffic to be exchanged across an organization’s firewall. Among other things, this enables users to use Lync Server across the Internet, and then exchange audio and video data with users who have logged onto the system from inside the firewall. 边缘服务器 configuration settings can be assigned at the global scope, the site scope, and the service scope. The A/V Edge configuration settings enable administrators to manage the amount of time that user authentication is valid before it must be renewed, and to limit the amount of bandwidth that can be used by a single user or a single port.

The **New-CsAVEdgeConfiguration** cmdlet enables you to create new collections of A/V Edge configuration settings at either the site or the service scope. As noted, A/V Edge settings can also be configured at the global scope. However, you cannot create a new collection at the global scope.

Note that any given site or service can host, at most, a single collection of A/V Edge configuration settings. If the Redmond site already hosts a collection of A/V Edge settings, you cannot create a new collection with the Identity site:Redmond.

Unless instructed by Microsoft support personnel, it is recommended that you do not change the default A/V Edge configuration settings. Because of that, you will probably not need to create a new collection of settings for a site or service.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsAVEdgeConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsAVEdgeConfiguration"}

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
<td><p>Unique identifier for the collection of A/V Edge configuration settings to be created. To create a collection of settings to be applied at the site scope, use syntax similar to this: -Identity site:Redmond. (Note that this command will fail if a collection of A/V Edge configuration settings have already been applied to the Redmond site.) Settings configured at the service scope should use syntax similar to this: -Identity service:EdgeServer:atl-cs-001.litwareinc.com.</p></td>
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
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
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

None. The **New-CsAVEdgeConfiguration** cmdlet does not accept pipelined input.

## Return Types

Creates instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Edge.MediaRelaySettings object.

## 另请参阅

#### 其他资源

[Get-CsAVEdgeConfiguration](get-csavedgeconfiguration.md)  
[Remove-CsAVEdgeConfiguration](remove-csavedgeconfiguration.md)  
[Set-CsAVEdgeConfiguration](set-csavedgeconfiguration.md)

