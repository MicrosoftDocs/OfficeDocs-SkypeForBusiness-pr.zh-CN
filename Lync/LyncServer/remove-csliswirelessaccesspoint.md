---
title: Remove-CsLisWirelessAccessPoint
TOCTitle: Remove-CsLisWirelessAccessPoint
ms:assetid: 656190b0-bde0-4a92-a6b5-b96a389c4863
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398461(v=OCS.15)
ms:contentKeyID: 49313067
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsLisWirelessAccessPoint

 

_**上一次修改主题：** 2015-03-09_

Removes a Location Information Server (LIS) wireless access point (WAP). 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsLisWirelessAccessPoint -BSSID <String> [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 removes the LIS WAP location with the BSSID 99-99-99-99-99-99.

If this WAP was associated with a location, that location will not be removed, only the WAP will be removed from the location mapping.

    Remove-CsLisWirelessAccessPoint -BSSID 99-99-99-99-99-99

## EXAMPLE 2

This example removes all WAPs in building 30. The example begins with a call to the **Get-CsLisWirelessAccessPoint** cmdlet, which returns a collection of all WAPs. This collection is piped to the **Where-Object** cmdlet, which finds the items in that collection that have a Location property that contains the string Bldg30 anywhere in the value; in other words, a Location that is like (-like) Bldg30. Finally, we pipe this collection of WAPs in building 30 to the **Remove-CsLisWirelessAccessPoint** cmdlet, which removes everything in that collection.

Note that, as in Example 1, no locations are removed from the location configuration database, only the WAPs that reference those locations are removed.

    Get-CsLisWirelessAccessPoint | Where-Object {$_.Location -like "*Bldg30*"} | Remove-CsLisWirelessAccessPoint

## Detailed Description

Enhanced 9-1-1 allows an emergency operator to identify the location of a caller without having to ask the caller for that information. In the case where a caller is calling from a Voice over Internet Protocol (VoIP) connection, that information must be extracted based on various connection factors. The VoIP administrator must configure a location map (called a wiremap) that will determine a caller’s location. This cmdlet removes a WAP from the location configuration database. Removing the WAP will not remove the location associated with that WAP. Use the **Remove-CsLisLocation** cmdlet to remove a location.

If you attempt to remove a WAP that does not exist, no action will be taken and you will not receive an error or a warning message.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsLisWirelessAccessPoint** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsLisWirelessAccessPoint"}

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
<td><p><em>BSSID</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The Basic Service Set Identifier (BSSID) of the wireless access point you want to remove. This value will be in the form nn-nn-nn-nn-nn-nn, such as 12-34-56-78-90-ab.</p></td>
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

Accepts pipelined input of LIS wireless access point objects.

## Return Types

This cmdlet removes an object of type System.Management.Automation.PSCustomObject.

## 另请参阅

#### 其他资源

[Set-CsLisWirelessAccessPoint](set-csliswirelessaccesspoint.md)  
[Get-CsLisWirelessAccessPoint](get-csliswirelessaccesspoint.md)  
[Remove-CsLisLocation](remove-cslislocation.md)

