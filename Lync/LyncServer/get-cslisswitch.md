---
title: Get-CsLisSwitch
TOCTitle: Get-CsLisSwitch
ms:assetid: 2b09e8f1-4930-4ac2-8f6f-48c08cd890c5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425769(v=OCS.15)
ms:contentKeyID: 49312337
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsLisSwitch

 

_**上一次修改主题：** 2015-03-09_

Retrieves one or more network switches from the location configuration database. Each switch can be associated with a location, in which case this cmdlet will also retrieve the location information of the switches. This location association is used in an Enhanced 9-1-1 (E9-1-1) Enterprise Voice implementation to notify an emergency services operator of the caller’s location. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsLisSwitch

## Examples

## EXAMPLE 1

Example 1 retrieves all Location Information Server (LIS) switches that have been defined in the Lync Server deployment.

    Get-CsLisSwitch

## EXAMPLE 2

This example retrieves all information for all switches that have a ChassisID equal to 99-99-99-99-99-99. Because ChassisIDs must be unique, this command will retrieve, at most, one switch location. The command begins by calling the **Get-CsLisSwitch** cmdlet to retrieve all switch location associations. This collection of switch locations is piped to the **Where-Object** cmdlet. The **Where-Object** cmdlet checks the ChassisID property of each item in the collection and returns the item with the ChassisID value 99-99-99-99-99-99.

    Get-CsLisSwitch | Where-Object {$_.ChassisID -eq "99-99-99-99-99-99"}

## EXAMPLE 3

This example retrieves all information for all switches that have been associated with a location in the city of Redmond. The command begins by calling the **Get-CsLisSwitch** cmdlet to retrieve all switch location associations. This collection of switch locations is piped to the **Where-Object** cmdlet. The **Where-Object** cmdlet checks the City property of each item in the collection to determine whether the value is equal to (-eq) Redmond.

    Get-CsLisSwitch | Where-Object {$_.City -eq "Redmond"}

## Detailed Description

Enhanced 9-1-1 allows an emergency operator to identify the location of a caller without having to ask the caller for that information. In the case where a caller is calling from a Voice over Internet Protocol (VoIP) connection, that information must be extracted based on various connection factors. The VoIP administrator must configure a location map (called a wiremap) that will determine a caller’s location. This cmdlet retrieves information on associations between physical locations and the network switch through which the client is connected.

This cmdlet does not take any parameters (other than the Windows PowerShell common parameters). The cmdlet will retrieve all instances of switch to location mappings. To narrow down the information retrieved you must pipe the output from this cmdlet to another Windows PowerShell cmdlet such as the **Where-Object** cmdlet or the **Select-Object** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsLisSwitch** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsLisSwitch"}

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
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>This cmdlet provides only common Windows PowerShell parameters.</p></td>
<td><p></p></td>
<td><p></p></td>
<td> </td>
</tr>
</tbody>
</table>


## Input Types

None.

## Return Types

This cmdlet retrieve one or more objects of type System.Management.Automation.PSCustomObject.

## 另请参阅

#### 其他资源

[Remove-CsLisSwitch](remove-cslisswitch.md)  
[Set-CsLisSwitch](set-cslisswitch.md)

