---
title: Get-CsLisWirelessAccessPoint
TOCTitle: Get-CsLisWirelessAccessPoint
ms:assetid: 060ea753-2fa8-4473-8e90-cb3e0fd91e63
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398117(v=OCS.15)
ms:contentKeyID: 49311883
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsLisWirelessAccessPoint

 

_**上一次修改主题：** 2015-03-09_

Retrieves one or more wireless access points (WAPs) from the location configuration database. Each WAP can be associated with a location, in which case this cmdlet will also retrieve the location information of the WAPs. This location association is used in an Enhanced 9-1-1 (E9-1-1) Enterprise Voice implementation to notify an emergency services operator of the caller’s location. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsLisWirelessAccessPoint

## Examples

## EXAMPLE 1

Example 1 retrieves all Location Information Server (LIS) WAPs that have been defined in the Lync Server deployment.

    Get-CsLisWirelessAccessPoint

## EXAMPLE 2

This example retrieves all information for all WAPs that have a Basic Service Set Identifier (BSSID) equal to 99-99-99-99-99-99. Because BSSIDs must be unique, this command will retrieve, at most, one WAP location. The command begins by calling the **Get-CsLisWirelessAccessPoint** cmdlet to retrieve all WAP location associations. This collection of WAP locations is piped to the **Where-Object** cmdlet. The **Where-Object** cmdlet checks the BSSID property of each item in the collection and returns the item with the BSSID value 99-99-99-99-99-99.

    Get-CsLisWirelessAccessPoint | Where-Object {$_.BSSID -eq "99-99-99-99-99-99"}

## EXAMPLE 3

This example retrieves all information for all WAPs that have been associated with a location in the city of Redmond. The command begins by calling the **Get-CsLisWirelessAccessPoint** cmdlet to retrieve all WAP location associations. This collection of WAP locations is piped to the **Where-Object** cmdlet. The **Where-Object** cmdlet checks the City property of each item in the collection to determine whether the value is equal to (-eq) Redmond.

    Get-CsLisWirelessAccessPoint | Where-Object {$_.City -eq "Redmond"}

## Detailed Description

Enhanced 9-1-1 allows an emergency operator to identify the location of a caller without having to ask the caller for that information. In the case where a caller is calling from a Voice over Internet Protocol (VoIP) connection, that information must be extracted based on various connection factors. The VoIP administrator must configure a location map (called a wiremap) that will determine a caller’s location. This cmdlet retrieves information on associations between physical locations and the WAP through which the client is connected.

This cmdlet does not take any parameters (other than the Windows PowerShell common parameters). The cmdlet will retrieve all instances of WAP to location mappings. To narrow down the information retrieved, you must pipe the output from this cmdlet to another Windows PowerShell cmdlet such as the **Where-Object** cmdlet or the **Select-Object** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsLisWirelessAccessPoint** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsLisWirelessAccessPoint"}

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

[Remove-CsLisWirelessAccessPoint](remove-csliswirelessaccesspoint.md)  
[Set-CsLisWirelessAccessPoint](set-csliswirelessaccesspoint.md)

