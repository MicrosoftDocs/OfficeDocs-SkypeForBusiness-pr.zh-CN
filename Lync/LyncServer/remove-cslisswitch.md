---
title: Remove-CsLisSwitch
TOCTitle: Remove-CsLisSwitch
ms:assetid: 53456988-4b37-4f34-825d-bebee5124856
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398352(v=OCS.15)
ms:contentKeyID: 49312858
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsLisSwitch

 

_**上一次修改主题：** 2015-03-09_

Removes a Location Information Server (LIS) network switch. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsLisSwitch -ChassisID <String> [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 removes the LIS switch with the MAC address (ChassisID) 99-99-99-99-99-99.

This command will not succeed if the ChassisID is referenced by a port. Also, if this switch was associated with a location, that location will not be removed, only the switch will be removed from the location mapping.

    Remove-CsLisSwitch -ChassisID 99-99-99-99-99-99

## EXAMPLE 2

This example removes all switches that do not have a city. The example begins with a call to the **Get-CsLisSwitch** cmdlet, which returns a collection of all switches. This collection is piped to the **Where-Object** cmdlet, which finds the items in that collection that have a City property that is empty; in other words, a City that is equal to (-eq) an empty string (“”). Finally, we pipe this collection of switches that don’t have cities to the **Remove-CsLisSwitch** cmdlet, which removes everything in that collection.

Note that, as in Example 1, no locations are removed from the location database, only the switches that reference those locations are removed. In this case that means there will be invalid locations (they’re invalid because City is a required property for a location) in the location database that should also be removed. You can remove locations by calling the **Remove-CsLisLocation** cmdlet.

    Get-CsLisSwitch | Where-Object {$_.City -eq ""} | Remove-CsLisSwitch

## Detailed Description

Enhanced 9-1-1 (E9-1-1) allows an emergency operator to identify the location of a caller without having to ask the caller for that information. In the case where a caller is calling from a Voice over Internet Protocol (VoIP) connection, that information must be extracted based on various connection factors. The VoIP administrator must configure a location map (called a wiremap) that will determine a caller’s location. This cmdlet removes a switch from the location configuration database. Removing a switch will not remove the actual location; it removes only the switch. To remove the location, call the **Remove-CsLisLocation** cmdlet.

You cannot remove a switch if the ChassisID of the switch is in use by a port. (Run the following command to find out which ChassisIDs are in use by ports: Get-CsLisPort | Select-Object ChassisID.) You must first remove all ports with the given ChassisID before you can remove the switch.

If you attempt to remove a switch that does not exist, no action will be taken and you will not receive an error or a warning message.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsLisSwitch** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsLisSwitch"}

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
<td><p>The Media Access Control (MAC) address of the network switch. This value will be in the form nn-nn-nn-nn-nn-nn, such as 12-34-56-78-90-ab.</p></td>
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

Accepts pipelined input of LIS switch objects.

## Return Types

This cmdlet does not return a value. It removes an object of type System.Management.Automation.PSCustomObject.

## 另请参阅

#### 其他资源

[Set-CsLisSwitch](set-cslisswitch.md)  
[Get-CsLisSwitch](get-cslisswitch.md)  
[Remove-CsLisLocation](remove-cslislocation.md)  
[Get-CsLisPort](get-cslisport.md)

