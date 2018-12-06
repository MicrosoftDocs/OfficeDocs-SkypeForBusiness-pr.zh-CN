---
title: Get-CsAVEdgeConfiguration
TOCTitle: Get-CsAVEdgeConfiguration
ms:assetid: f1a0db80-158c-47bd-8a8e-30e3f095fb2a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413008(v=OCS.15)
ms:contentKeyID: 49314712
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsAVEdgeConfiguration

 

_**上一次修改主题：** 2015-03-09_

Returns configuration information for computers running the A/V 边缘服务 in your organization. The configuration settings on these computers, also known as A/V Edge servers, enable internal users to share audio and video data with external users (that is, users who are not logged on to your internal network), as well as exchange files and participate in desktop sharing sessions. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsAVEdgeConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsAVEdgeConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

The command shown in Example 1 returns a collection of all the A/V Edge configuration settings configured for use in the organization. Calling the **Get-CsAVEdgeConfiguration** cmdlet without any additional parameters always returns a complete collection of A/V Edge configuration settings.

    Get-CsAVEdgeConfiguration

## EXAMPLE 2

In Example 2 a single collection of A/V Edge configuration settings is returned: the collection that has the Identity site:Redmond.

    Get-CsAVEdgeConfiguration -Identity site:Redmond

## EXAMPLE 3

Example 3 returns a collection of all the A/V Edge configuration settings that have been configured at the site scope. To do this, the **Get-CsAVEdgeConfiguration** cmdlet is called along with the Filter parameter; the filter value "site:\*" limits the returned data to settings that have an Identity that begins with the characters "site:". By definition, that limits the returned data to settings configured at the site scope.

    Get-CsAVEdgeConfiguration -Filter "site:*"

## EXAMPLE 4

In Example 4, the only A/V Edge configuration settings that are returned are those where the MaxBandwidthPerUserKB property is greater than 10,000 kilobits per second. To perform this task, the command first calls the **Get-CsAVEdgeConfiguration** cmdlet without any parameters; that returns a collection of all the A/V Edge configuration settings currently in use. That collection is then piped to the **Where-Object** cmdlet, which picks out only the settings where the MaxBandwidthPerUserKB is greater than 10000 kilobits per second.

    Get-CsAVEdgeConfiguration | Where-Object {$_.MaxBandwidthPerUserKB -gt 10000}

## EXAMPLE 5

Example 5 is similar to the command shown in Example 4; in Example 5, however, the only A/V Edge settings returned are those where the MaxBandwidthPerUserKB property is exactly equal to 10000 kilobits per second.

    Get-CsAVEdgeConfiguration | Where-Object {$_.MaxBandwidthPerUserKB -eq 10000}

## EXAMPLE 6

The command shown in Example 6 returns only the A/V Edge configuration settings where the MaxTokenLifetime property is less than 8 hours (08 hours : 00 minutes : 00 seconds). The command first calls the **Get-CsAVEdgeConfiguration** cmdlet without any parameters in order to return a collection of all the A/V Edge configuration settings used in the organization. This collection is then piped to the **Where-Object** cmdlet, which picks out only the settings where the MaxTokenLifetime is less than 8 hours (08:00:00).

    Get-CsAVEdgeConfiguration | Where-Object {$_.MaxTokenLifetime -lt "08:00:00"}

## Detailed Description

An A/V Edge server provides a way for audio and video traffic to be exchanged across an organization’s firewall. Among other things, this enables users to use Lync Server across the Internet, and then exchange audio and video data with users who have logged onto the system from inside the firewall. 边缘服务器 configuration settings can be assigned at the global scope, the site scope, and the service scope. The A/V Edge configuration settings enable administrators to do such things as manage the amount of time that user authentication is valid before it must be renewed, and to limit the amount of bandwidth that can be used by a single user or a single port.

The **Get-CsAVEdgeConfiguration** cmdlet provides a way for you to retrieve information about the A/V Edge configuration settings currently in use in your organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsAVEdgeConfiguration** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsAVEdgeConfiguration"}

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
<td><p>Enables you to use wildcard characters when indicating the A/V Edge configuration settings to be returned. For example, to return all the settings configured at the site scope, use this syntax: -Filter site:*. To return a collection of all the settings configured at the service, use this syntax: -Filter &quot;service:*&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the collection of A/V Edge configuration settings to be retrieved. To retrieve the global collection, use the following syntax: -Identity global. To retrieve a site collection use syntax similar to this: -Identity site:Redmond. Settings configured at the service scope should be referred to using syntax similar to this: -Identity service:EdgeServer:atl-cs-001.litwareinc.com. Note that you cannot use wildcards when specifying a policy Identity.</p>
<p>If this parameter is not included, the <strong>Get-CsAVEdgeConfiguration</strong> cmdlet returns a collection of all the Edge configuration settings currently in use in your organization.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the A/V Edge configuration data from the local replica of the 中央管理存储 rather than from the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsAVEdgeConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsAVEdgeConfiguration** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Edge.MediaRelaySettings object.

## 另请参阅

#### 其他资源

[New-CsAVEdgeConfiguration](new-csavedgeconfiguration.md)  
[Remove-CsAVEdgeConfiguration](remove-csavedgeconfiguration.md)  
[Set-CsAVEdgeConfiguration](set-csavedgeconfiguration.md)

