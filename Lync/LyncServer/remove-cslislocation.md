﻿---
title: Remove-CsLisLocation
TOCTitle: Remove-CsLisLocation
ms:assetid: 24e49a83-01a9-48ce-b940-fb0503f52077
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425722(v=OCS.15)
ms:contentKeyID: 49312265
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsLisLocation

 

_**上一次修改主题：** 2015-03-09_

Removes a location from the location configuration database for Enhanced 9-1-1 (E9-1-1). 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsLisLocation [-City <String>] [-CompanyName <String>] [-Country <String>] [-HouseNumber <String>] [-HouseNumberSuffix <String>] [-Location <String>] [-PostalCode <String>] [-PostDirectional <String>] [-PreDirectional <String>] [-State <String>] [-StreetName <String>] [-StreetSuffix <String>] <COMMON PARAMETERS>

    Remove-CsLisLocation -City <String> -CompanyName <String> -Country <String> -HouseNumber <String> -HouseNumberSuffix <String> -Location <String> -PostalCode <String> -PostDirectional <String> -PreDirectional <String> -State <String> -StreetName <String> -StreetSuffix <String> <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 removes a location named Bldg30NEWing. This command specifies values for the parameters Location, HouseNumber, StreetName, City, State, and Country. This means that those are the only properties of the location to be deleted that contain non-null values. If you don’t supply parameter values for all non-null properties, the location will not be deleted. You will be prompted for any parameter that you haven’t specified in the command, but if they contain null values you can simply press Enter at each prompt.

    Remove-CsLisLocation -Location Bldg30NEWing -HouseNumber 1000 -StreetName Main -City Redmond -State WA -Country US

## EXAMPLE 2

This example will remove all locations that are not referenced by a LIS port, subnet, switch, or wireless access point. The command begins with a call to the **Get-CsLisLocation** cmdlet, specifying the Unreferenced parameter. This will return a collection of all locations that are not referenced by a LIS port, subnet, switch, or wireless access point. This collection is then piped to the **Remove-CsLisLocation** cmdlet, which removes each location in the collection.

    Get-CsLisLocation -Unreferenced | Remove-CsLisLocation

## Detailed Description

E9-1-1 enables those who answer emergency calls to determine the caller’s geographic location without having to ask the caller for that information. In Lync Server the location is determined based on mapping the caller’s port, subnet, switch, or wireless access point to a specific location. This cmdlet removes a location from the location configuration database. All properties of a location combined make the location unique, so you must enter all non-null properties of the location to remove it. If you do not enter all non-null properties of the location you want to remove (and no other location contains only the properties you specified), no locations will be removed. You won’t receive an error in this case, but no action will occur.

This cmdlet will not remove locations that are associated with a Location Information Server (LIS) port, subnet, switch, or wireless access point. If you attempt to remove a location referenced by any of these devices, you’ll receive an error. You must remove all references before removing the location. You can use the **Remove-CsLisPort** cmdlet, the **Remove-CsLisSubnet** cmdlet, the **Remove-CsLisSwitch** cmdlet, and the **Remove-CsLisWirelessAccessPoint** cmdlet to remove these references.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsLisLocation** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsLisLocation"}

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
<td><p><em>City</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The location city.</p></td>
</tr>
<tr class="even">
<td><p><em>CompanyName</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The name of the company at this location.</p></td>
</tr>
<tr class="odd">
<td><p><em>Country</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The country/region this location is in. This value will contain two characters or less.</p></td>
</tr>
<tr class="even">
<td><p><em>HouseNumber</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The house number of the location. For a company this is the number on the street where the company is located.</p></td>
</tr>
<tr class="odd">
<td><p><em>HouseNumberSuffix</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Additional information for the house number, such as 1/2 or A. For example, 1234 1/2 Oak Street or 1234 A Elm Street.</p></td>
</tr>
<tr class="even">
<td><p><em>Location</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The name for this location.</p></td>
</tr>
<tr class="odd">
<td><p><em>PostalCode</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The postal code associated with this location.</p></td>
</tr>
<tr class="even">
<td><p><em>PostDirectional</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The directional designation of a street name. For example, NE or NW for Main Street NE or 7th Avenue NW.</p></td>
</tr>
<tr class="odd">
<td><p><em>PreDirectional</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The directional designation for a street name that precedes the name of the street. For example, NE or NW for NE Main Street or NW 7th Avenue.</p></td>
</tr>
<tr class="even">
<td><p><em>State</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The state or province associated with this location. This value will be two characters or less.</p></td>
</tr>
<tr class="odd">
<td><p><em>StreetName</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The name of the street for this location.</p></td>
</tr>
<tr class="even">
<td><p><em>StreetSuffix</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The type of street designated in a street name, such as Street, Avenue, or Court.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
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

Accepts pipelined input of LIS location objects.

## Return Types

This cmdlet does not return a value or object. It removes an object of type System.Management.Automation.PSCustomObject.

## 另请参阅

#### 其他资源

[Set-CsLisLocation](set-cslislocation.md)  
[Get-CsLisLocation](get-cslislocation.md)  
[Remove-CsLisPort](remove-cslisport.md)  
[Remove-CsLisSubnet](remove-cslissubnet.md)  
[Remove-CsLisSwitch](remove-cslisswitch.md)  
[Remove-CsLisWirelessAccessPoint](remove-csliswirelessaccesspoint.md)  
[Get-CsLisCivicAddress](get-csliscivicaddress.md)

