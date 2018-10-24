---
title: Remove-CsLisPort
TOCTitle: Remove-CsLisPort
ms:assetid: b8a648af-1064-4a1e-8462-f267b7b72be1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412899(v=OCS.15)
ms:contentKeyID: 49314061
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsLisPort

 

_**上一次修改主题：** 2015-03-09_

Removes an association between a Location Information Server (LIS) port and a location. This association is used in an Enhanced 9-1-1 (E9-1-1) Enterprise Voice implementation to notify an emergency services operator of the caller’s location. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsLisPort -ChassisID <String> -PortID <String> -PortIDSubType <InterfaceAlias | InterfaceName | LocallyAssigned> [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 removes the LIS port with the MAC address (ChassisID) 99-99-99-99-99-99, the PortID 4200, and the PortIDSubType 1. (Note that a value of 1 for PortIDSubType translates into a value of InterfaceAlias. This parameter and value could also have been entered like this: -PortIDSubType InterfaceAlias)

If this port was associated with a location, that location will not be removed, only the port will be removed from the location mapping.

    Remove-CsLisPort -ChassisID 99-99-99-99-99-99 -PortID 4200 -PortIDSubType 1

## EXAMPLE 2

This example removes all port locations that do not have a house number. The example begins with a call to the **Get-CsLisPort** cmdlet, which returns a collection of all LIS ports. This collection is piped to the **Where-Object** cmdlet, which finds the items in that collection that have a HouseNumber property that is empty; in other words, a HouseNumber that is equal to (-eq) an empty string (“”). Finally, we pipe this collection of port locations that don’t have house numbers to the **Remove-CsLisPort** cmdlet, which removes everything in that collection.

Note that, as in example 1, no locations are removed from the location configuration database, only the ports that reference those locations are removed. In this case that means there will be invalid locations (they’re invalid because HouseNumber is a required property for a location) in the location database that should also be removed. You can remove locations by calling the **Remove-CsLisLocation** cmdlet.

    Get-CsLisPort | Where-Object {$_.HouseNumber -eq ""} | Remove-CsLisPort

## Detailed Description

Enhanced 9-1-1 allows an emergency operator to identify the location of a caller without having to ask the caller for that information. In the case where a caller is calling from a Voice over Internet Protocol (VoIP) connection, that information must be extracted based on various connection factors. The VoIP administrator must configure a location map (called a wiremap) that will determine a caller’s location. This cmdlet removes an association between a physical location and a port through which calls will be routed by removing the port from the location configuration database.

Removing a port location will not remove the actual location of the port; it removes only the port. To remove the location, call the **Remove-CsLisLocation** cmdlet. Removing the port will also not remove the switch with the given ChassisID; to remove the switch, call the **Remove-CsLisSwitch** cmdlet.

If you attempt to remove a port that does not exist, no action will be taken and you will not receive an error or a warning message.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsLisPort** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsLisPort"}

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
<td><p><em>ChassisID</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The Media Access Control (MAC) address of the port’s switch. This value will be in the form nn-nn-nn-nn-nn-nn, such as 12-34-56-78-90-ab.</p></td>
</tr>
<tr class="even">
<td><p><em>PortID</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The ID of the port you want to remove.</p></td>
</tr>
<tr class="odd">
<td><p><em>PortIDSubType</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Lis.PortIDSubType</p></td>
<td><p>The subtype of the port you want to remove. This value can be entered as a numeric value or a string, but it must be a valid subtype. Valid subtypes are:</p>
<p>1: InterfaceAlias</p>
<p>5: InterfaceName</p>
<p>7: LocallyAssigned</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
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

Accepts pipelined input of LIS port objects.

## Return Types

This cmdlet does not return a value. It removes an object of type System.Management.Automation.PSCustomObject.

## 另请参阅

#### 其他资源

[Set-CsLisPort](set-cslisport.md)  
[Get-CsLisPort](get-cslisport.md)  
[Remove-CsLisLocation](remove-cslislocation.md)  
[Remove-CsLisSwitch](remove-cslisswitch.md)

