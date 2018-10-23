﻿---
title: Set-CsLisWirelessAccessPoint
TOCTitle: Set-CsLisWirelessAccessPoint
ms:assetid: 9c491f8d-c4c0-48e5-afc2-0153864dab41
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412723(v=OCS.15)
ms:contentKeyID: 49313728
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsLisWirelessAccessPoint

 

_**上一次修改主题：** 2015-03-09_

Creates a Location Information Server (LIS) wireless access point (WAP), creates an association between a WAP and a location (creating a new location if that location doesn’t exist), or modifies an existing WAP and its associated location. The association between a WAP and location is used in an Enhanced 9-1-1 (E9-1-1) Enterprise Voice implementation to notify an emergency services operator of the caller’s location. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsLisWirelessAccessPoint -BSSID <String> [-City <String>] [-CompanyName <String>] [-Country <String>] [-Description <String>] [-HouseNumber <String>] [-HouseNumberSuffix <String>] [-Location <String>] [-PostalCode <String>] [-PostDirectional <String>] [-PreDirectional <String>] [-State <String>] [-StreetName <String>] [-StreetSuffix <String>] <COMMON PARAMETERS>

    Set-CsLisWirelessAccessPoint -BSSID <String> [-Description <String>] <COMMON PARAMETERS>

    Set-CsLisWirelessAccessPoint -City <String> -CompanyName <String> -Country <String> -HouseNumber <String> -HouseNumberSuffix <String> -Location <String> -PostalCode <String> -PostDirectional <String> -PreDirectional <String> -State <String> -StreetName <String> -StreetSuffix <String> <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 creates or updates a LIS WAP location entry. The command in this example includes only one (required) parameter: BSSID. The value of the BSSID is the identifier (in the form of a MAC address) of the WAP, in this case 99-99-99-99-99-99.

Notice that this example does not include any address information. It’s possible to create a WAP entry on the Location Information Server without associating it with an address. However, emergency calls routed through this WAP may not contain enough information for the emergency operator to identify a location.

IMPORTANT: If a LIS WAP location with this BSSID already exists, it will be replaced by the values in this command. That means that if this WAP were associated with an address (a physical location), that association would no longer exist because we didn’t include any location information in this command. The location will still exist in the location database, but it will not be associated with this WAP.

    Set-CsLisWirelessAccessPoint -BSSID 99-99-99-99-99-99

## EXAMPLE 2

Example 2 updates the WAP created in Example 1 by adding address information. (This is actually deleting the existing entry and replacing it with this new entry.) If the address does not exist in the location database, this cmdlet will create that location.

    Set-CsLisWirelessAccessPoint -BSSID 99-99-99-99-99-99 -Location "30/1000" -HouseNumber 1234 -PreDirectional NE -StreetName First -StreetSuffix Avenue -City Redmond -State WA -Country US -PostalCode 99999

## Detailed Description

Enhanced 9-1-1 allows an emergency operator to identify the location of a caller without having to ask the caller for that information. In the case where a caller is calling from a Voice over Internet Protocol (VoIP) connection, that information must be extracted based on various connection factors. The VoIP administrator must configure a location map (called a wiremap) that will determine a caller’s location. This cmdlet allows the administrator to map physical locations to the WAP through which calls will be routed.

The BSSID parameter is the only required parameter for this cmdlet. If you enter a BSSID value that already exists, this cmdlet will update the location for that WAP based on the location parameters that are supplied. If the BSSID does not exist, a new WAP location will be created.

If a location with an address exactly matching the address parameters entered here (including null values) does not exist in the location database, a new address will be created based on the parameters entered with this cmdlet. (You can retrieve a list of locations by calling the **Get-CsLisLocation** cmdlet.) The **Set-CsLisWirelessAccessPoint** cmdlet does not require or prompt for location parameters; you can create a WAP entry without associating it with a location. It’s also possible to create an invalid location with this cmdlet. A valid location consists of, at minimum, the Location, HouseNumber, StreetName, City, State, and Country. If you do not supply all of these parameters, calls that are received by the referenced WAP may not contain the information required by the emergency operator. It is recommended that you be as specific as possible with the location parameters and fill in as many as possible.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsLisWirelessAccessPoint** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsLisWirelessAccessPoint"}

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
<td><p>The Basic Service Set Identifier (BSSID) of the wireless access point. This value must be in the form nn-nn-nn-nn-nn-nn, such as 12-34-56-78-90-ab. If an entry with the specified BSSID value does not exist, a new WAP location will be created. If an entry with the specified BSSID does exist, that entry will be replaced.</p></td>
</tr>
<tr class="even">
<td><p><em>City</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The location city.</p>
<p>Maximum length: 64 characters.</p></td>
</tr>
<tr class="odd">
<td><p><em>CompanyName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The name of the company at this location.</p>
<p>Maximum length: 60 characters</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Country</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The country/region this location is in.</p>
<p>Maximum length: 2 characters</p></td>
</tr>
<tr class="even">
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>A detailed description of this WAP location.</p></td>
</tr>
<tr class="odd">
<td><p><em>HouseNumber</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The house number of the location. For a company this is the number on the street where the company is located.</p>
<p>Maximum length: 10 characters</p></td>
</tr>
<tr class="even">
<td><p><em>HouseNumberSuffix</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Additional information for the house number, such as 1/2 or A. For example, 1234 1/2 Oak Street or 1234 A Elm Street.</p>
<p>Note: To designate an apartment number or office suite, you must use the Location parameter. For example, -Location &quot;Suite 100/Office 150&quot;.</p>
<p>Maximum length: 5 characters</p></td>
</tr>
<tr class="odd">
<td><p><em>Location</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The name for this location. Typically this value is the name of a location more specific than the civic address, such as an office number, but it can be any string value.</p>
<p>Maximum length: 20 characters</p></td>
</tr>
<tr class="even">
<td><p><em>PostalCode</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The postal code associated with this location.</p>
<p>Maximum length: 10 characters</p></td>
</tr>
<tr class="odd">
<td><p><em>PostDirectional</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The directional designation of a street name. For example, NE or NW for Main Street NE or 7th Avenue NW.</p>
<p>Maximum length: 2 characters</p></td>
</tr>
<tr class="even">
<td><p><em>PreDirectional</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The directional designation for a street name that precedes the name of the street. For example, NE or NW for NE Main Street or NW 7th Avenue.</p>
<p>Maximum length: 2 characters</p></td>
</tr>
<tr class="odd">
<td><p><em>State</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The state or province associated with this location.</p>
<p>Maximum length: 2 characters</p></td>
</tr>
<tr class="even">
<td><p><em>StreetName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The name of the street for this location.</p>
<p>Maximum length: 60 characters</p></td>
</tr>
<tr class="odd">
<td><p><em>StreetSuffix</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The type of street designated in a street name, such as Street, Avenue, or Court.</p>
<p>Maximum length: 10 characters</p></td>
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

Accepts pipelined input of LIS wireless access point objects.

## Return Types

This cmdlet creates or modifies an object of type System.Management.Automation.PSCustomObject.

## 另请参阅

#### 其他资源

[Remove-CsLisWirelessAccessPoint](remove-csliswirelessaccesspoint.md)  
[Get-CsLisWirelessAccessPoint](get-csliswirelessaccesspoint.md)  
[Get-CsLisLocation](get-cslislocation.md)

