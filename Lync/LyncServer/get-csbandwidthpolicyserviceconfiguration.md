---
title: Get-CsBandwidthPolicyServiceConfiguration
TOCTitle: Get-CsBandwidthPolicyServiceConfiguration
ms:assetid: 9cb9cf59-c47e-40f6-9f9e-235b83329a69
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412727(v=OCS.15)
ms:contentKeyID: 49313742
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsBandwidthPolicyServiceConfiguration

 

_**上一次修改主题：** 2015-03-09_

Retrieves one or more bandwidth policy service configurations. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsBandwidthPolicyServiceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsBandwidthPolicyServiceConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

Example 1 retrieves all bandwidth policy service configurations defined within the Lync Server implementation.

    Get-CsBandwidthPolicyServiceConfiguration

## EXAMPLE 2

This example retrieves the bandwidth policy service configuration defined for the Redmond site (-Identity site:Redmond).

    Get-CsBandwidthPolicyServiceConfiguration -Identity site:Redmond

## EXAMPLE 3

In this example we use the Filter parameter to retrieve all bandwidth policy service configurations defined at the site level. We do this by passing the value site:\* to the Filter parameter. This will search the Identity property of all bandwidth policy service configurations for values that begin with site: and are followed by any other characters. Because all site-level configurations have Identity values beginning with site: and followed by the name of the site, this filter will find all configurations for all sites.

    Get-CsBandwidthPolicyServiceConfiguration -Filter site:*

## EXAMPLE 4

Example 4 retrieves all bandwidth policy service configurations that allow log files to reach sizes greater than four megabytes. The example begins with a call to the **Get-CsBandwidthPolicyServiceConfiguration** cmdlet. As in Example 1, this cmdlet retrieves a collection of all configurations defined within the Lync Server deployment. This collection is then piped to the **Where-Object** cmdlet. The **Where-Object** cmdlet cycles through the collection one item at a time. For each item in the collection, the **Where-Object** cmdlet checks to see whether the value of the MaxLogFileSizeMb property is greater than (-gt) 4. If it is, that item remains part of the collection and is part of the command output. If the value of MaxLogFileSizeMb is not greater than 4, the item is ignored and will not be returned.

    Get-CsBandwidthPolicyServiceConfiguration | Where-Object {$_.MaxLogFileSizeMb -gt 4}

## Detailed Description

Call admission control (CAC) is a way of determining whether to allow real-time communications sessions, such as voice or video calls, to be established based on bandwidth constraints. Within the Lync Server implementation of CAC, regions, sites, and subnets are defined within a network along with the relationships and links between those entities in order to place bandwidth constraints between them. Bandwidth Policy service is the component that performs CAC functionality in the Lync Server deployment, enabling the decision as to whether sufficient bandwidth exists for a call to be established. The **Get-CsBandwidthPolicyServiceConfiguration** cmdlet retrieves settings for one or more bandwidth policy services.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsBandwidthPolicyServiceConfiguration** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsBandwidthPolicyServiceConfiguration"}

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
<td><p>A string containing one or more wildcard characters that will be used to search the Identity property of all bandwidth policy service configurations to find every configuration with an Identity that matches the wildcard pattern. For example, the Filter value site:* will retrieve all configurations with Identity values that begin with the string site: and end with any set of characters.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>The unique identifier of the configuration you want to retrieve. This identifier will consist of the scope (for the global configuration) or the scope and name (for a site-level configuration, such as site:Redmond).</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the bandwidth policy service configuration from the local replica of the 中央管理存储, rather than from the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None.

## Return Types

Returns one or more objects of type Microsoft.Rtc.Management.WritableConfig.Settings.BandwidthPolicyServiceConfiguration.BandwidthPolicyServiceConfiguration.

## 另请参阅

#### 其他资源

[New-CsBandwidthPolicyServiceConfiguration](new-csbandwidthpolicyserviceconfiguration.md)  
[Remove-CsBandwidthPolicyServiceConfiguration](remove-csbandwidthpolicyserviceconfiguration.md)  
[Set-CsBandwidthPolicyServiceConfiguration](set-csbandwidthpolicyserviceconfiguration.md)

