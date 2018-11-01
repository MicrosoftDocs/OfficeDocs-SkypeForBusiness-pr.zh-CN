---
title: Get-CsTestDevice
TOCTitle: Get-CsTestDevice
ms:assetid: 4c88d448-4130-40de-b7e9-7389922322f4
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398304(v=OCS.15)
ms:contentKeyID: 49312777
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsTestDevice

 

_**上一次修改主题：** 2015-03-09_

Retrieves information about the device update management test devices that have been configured for use in your organization. Test devices provide a way for administrators to test firmware updates before those updates are distributed to all the devices in an organization. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsTestDevice [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsTestDevice [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

Example 1 returns all the test devices in the organization. Calling the **Get-CsTestDevice** cmdlet without any additional parameters will return all the test devices currently in use.

    Get-CsTestDevice

## EXAMPLE 2

This example returns the test device named UCPhone that was assigned to the Redmond site.

    Get-CsTestDevice -Identity site:Redmond/UCPhone

## EXAMPLE 3

In Example 3, the command returns all the test devices configured for the Redmond site.

``` 
Get-CsTestDevice -Identity site:Redmond  
```

## EXAMPLE 4

Example 4 returns all the test devices that have been configured at the site scope. To do this, the command uses the Filter parameter; the filter value "site:\*" limits the returned data to test devices that have an Identity that begins with the string value "site:".

    Get-CsTestDevice -Filter site:*

## Detailed Description

By identifying specific phones compatible with Lync Phone Edition or other devices as test devices, administrators can verify and approve firmware updates before those updates are rolled out to all the relevant devices in the organization. When device update rules are imported to Lync Server, they are marked as "pending," which means that the updates corresponding to these rules will not automatically be downloaded and installed by the affected devices.

Instead, these pending rules will be downloaded and installed by any relevant test devices. That’s what test devices are for: new device update rules are automatically applied to test devices, giving administrators the opportunity to verify that the firmware updates work as expected. If they do, those administrators can then mark the rules as approved; approved rules are then downloaded and installed by all the relevant devices in the organization.

Test devices can be assigned to either the global or the site scope. You can use the **Get-CsTestDevice** cmdlet to retrieve information about the test devices currently configured for use in your organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsTestDevice** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsTestDevice"}

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
<td><p>Provides a way for you to use wildcard characters when specifying the test device (or devices) to be returned. For example, to return all the test device collections that have been configured at the site scope, use this syntax: -Filter &quot;site:*&quot;. To return all the devices that have the term &quot;EMEA&quot; in their Identity, use this syntax: -Filter &quot;*EMEA*&quot;. Note that Filter acts only on the Identity of the test device collection; you cannot filter on other collection properties.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Indicates the Identity of the test device to be returned. To refer to an individual device named UCPhone (stored in the global collection), use this syntax: -Identity global/UCPhone. To refer to a device found in a site collection, use syntax similar to this: -Identity site:Redmond/UCPhone. To refer to an entire collection, leave off the device name. For example, this syntax returns all the test devices configured for the Redmond site: -Identity site:Redmond.</p>
<p>Note that you cannot use wildcards when specifying an Identity.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the test device data from the local replica of the 中央管理存储 rather than from the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsTestDevice** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsTestDevice** cmdlet returns one or more instances of the Microsoft.Rtc.Management.WritableConfig.Settings.DeviceUpdate.TestDevice object.

## 另请参阅

#### 其他资源

[New-CsTestDevice](new-cstestdevice.md)  
[Remove-CsTestDevice](remove-cstestdevice.md)  
[Set-CsTestDevice](set-cstestdevice.md)

