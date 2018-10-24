---
title: New-CsTestDevice
TOCTitle: New-CsTestDevice
ms:assetid: 3d223c5e-b987-4353-9bf7-b247a2bdfa25
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425899(v=OCS.15)
ms:contentKeyID: 49312583
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsTestDevice

 

_**上一次修改主题：** 2015-03-09_

Creates a new device update management test device. Test devices provide a way for administrators to test firmware updates before those updates are distributed to all the devices in an organization. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsTestDevice -Name <String> -Parent <String> <COMMON PARAMETERS>

    New-CsTestDevice -Identity <XdsIdentity> <COMMON PARAMETERS>

    COMMON PARAMETERS: -Identifier <String> -IdentifierType <MACAddress | SerialNumber> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 creates a new test device (named UCPhone) for the Redmond site. Note the syntax used to specify the device Identity: the device scope (site:Redmond) followed by the / character followed by the device Name (UCPhone). This device uses the serial number as the IdentifierType, and has a serial number of 07823-A345.

    New-CsTestDevice -Identity site:Redmond/UCPhone -IdentifierType SerialNumber -Identifier "07823-A345"

## EXAMPLE 2

The command shown in Example 2 is a variation of the command shown in Example 1. In Example 2, however, the Identity parameter is not used. Instead, the Parent parameter is used to specify the scope for the new test device (site:Redmond) and the Name parameter is used to indicate the name for the new device (UCPhone). The **New-CsTestDevice** cmdlet will take those two parameter values and construct the test device Identity (site:Redmond/UCPhone) for you.

    New-CsTestDevice -Parent "site:Redmond" -Name UCPhone -IdentifierType SerialNumber -Identifier "07823-A345"

## Detailed Description

By identifying specific phones that are compatible with Lync Phone Edition or other devices as test devices, administrators can verify and approve firmware updates before those updates are rolled out to the relevant devices in the organization. When device update rules are imported to Lync Server, they are marked as "pending," which means that the updates corresponding to these rules will not automatically be downloaded and installed by the affected devices.

Instead, these pending rules will be downloaded and installed by any relevant test devices. That’s the idea behind test devices: new device update rules are automatically applied to test devices, giving administrators the opportunity to verify that the firmware updates work as expected. If they do, those administrators can then mark the rules as approved; approved rules are then downloaded and installed by all the relevant devices in the organization.

Test devices are created by using the **New-CsTestDevice** cmdlet. These devices can be configured at either the global scope or the site scope.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsTestDevice** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsTestDevice"}

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
<td><p><em>Identifier</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Based on the IdentifierType, indicates the Media Access Control (MAC) address or serial number of the new test device. Serial numbers can be specified using numbers, letters, hyphens and underscores; for example:</p>
<p>-Identifier &quot;AB37_679e&quot;</p>
<p>MAC addresses must be specified as six or more two-character pairs; depending on the MAC address, these pairs can either be joined together in a single string or can be separated using hyphens or colons. (Note that MAC addresses can include both letters and/or numbers.) Each of the following are valid MAC addresses:</p>
<p>010203040506</p>
<p>01-02-03-04-05-06</p>
<p>01:02:03:04:05:06</p>
<p>A MAC address such as 01-02-03-04-05 will not be accepted because it does not have at least six two-character pairs.</p></td>
</tr>
<tr class="even">
<td><p><em>IdentifierType</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.DeviceUpdate.IdentifierType</p></td>
<td><p>Indicates whether the test device will be uniquely identified by its MAC address or by its serial number. To identify a device by its MAC address, set the IdentifierType to MACAddress. To identify a device by its serial number, set the IdentifierType to SerialNumber. MACAddress and SerialNumber are the only allowed values.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Indicates the Identity for the new test device. An Identity consists of both the scope where the test device is to be assigned (for example, site:Redmond) and the name for the new device (for example, UCPhone). To assign a test device named UCPhone to the Redmond site, your Identity parameter must look like this: -Identity &quot;site:Redmond/UCPhone&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Name</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Name for the new test device (names must be unique within a given scope). The Name parameter should be used only when using the Parent parameter.</p></td>
</tr>
<tr class="odd">
<td><p><em>Parent</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Name of the scope (for example, site:Redmond) where the new test device is to be assigned. If you use the Parent parameter then you must also use the Name parameter; for example: -Parent site:Redmond –Name UCPhone. If you use the Parent parameter then you should not use the Identity parameter, and vice-versa.</p></td>
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
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **New-CsTestDevice** cmdlet does not accept pipelined input.

## Return Types

Creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.DeviceUpdate.TestDevice object.

## 另请参阅

#### 其他资源

[Get-CsTestDevice](get-cstestdevice.md)  
[Remove-CsTestDevice](remove-cstestdevice.md)  
[Set-CsTestDevice](set-cstestdevice.md)

