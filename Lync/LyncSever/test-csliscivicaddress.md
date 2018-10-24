---
title: Test-CsLisCivicAddress
TOCTitle: Test-CsLisCivicAddress
ms:assetid: 4079e767-3339-40c9-b7cd-08ec6c9d2c25
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425914(v=OCS.15)
ms:contentKeyID: 49312613
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsLisCivicAddress

 

_**上一次修改主题：** 2015-03-09_

Tests one or more civic addresses against the Master Street Address Guide. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Test-CsLisCivicAddress [-City <String>] [-Confirm [<SwitchParameter>]] [-Country <String>] [-HouseNumber <String>] [-HouseNumberSuffix <String>] [-PostalCode <String>] [-PostDirectional <String>] [-PreDirectional <String>] [-State <String>] [-StreetName <String>] [-StreetSuffix <String>] [-UpdateValidationStatus <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This command validates the address with the properties matching the values specified in these parameters against the Master Street Address Guide. Notice the inclusion of the UpdateValidationStatus parameter at the end: this will update the MSAGValid property of the address.

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 99999 -Country US -UpdateValidationStatus

## EXAMPLE 2

This example shows how to test all LIS civic addresses. The example begins with a call to the **Get-CsLisCivicAddress** cmdlet to retrieve all civic addresses defined in the location database. These addresses are piped to the **Test-CsLisCivicAddress** cmdlet, which uses the E9-1-1 Network Routing Provider web service to validate each address.

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

## Detailed Description

In an Enterprise Voice implementation with Enhanced 9-1-1 (E9-1-1), user locations are determined based on location maps that map a subnet, port, switch, or wireless access point to a location. (In the absence of a connection to a mapped location, the user may be asked to input their location manually.) The addresses of these locations must be validated against the Master Street Address Guide (MSAG) by the E9-1-1 Network Routing Provider. This cmdlet uses the web service of that provider to validate mapped addresses. You can set up a service provider by calling the **Set-CsLisServiceProvider** cmdlet.

If you want to update the MSAGValid property of the civic address, be sure to include the UpdateValidationStatus parameter in your call to the **Test-CsLisCivicAddress** cmdlet. Use the **Get-CsLisCivicAddress** cmdlet to retrieve civic addresses.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Test-CsLisCivicAddress** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsLisCivicAddress"}

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
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The location city.</p>
<p>Maximum length: 64 characters.</p></td>
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
<td><p><em>HouseNumber</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The house number of the location. For a company, this is the number on the street where the company is located.</p>
<p>Maximum length: 10 characters</p></td>
</tr>
<tr class="odd">
<td><p><em>HouseNumberSuffix</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Additional information for the house number, such as 1/2 or A. For example, 1234 1/2 Oak Street or 1234 A Elm Street.</p>
<p>Maximum length: 5 characters</p></td>
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
<td><p><em>UpdateValidationStatus</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Including this parameter will change the MSAGValid property of the civic address depending on whether the address is validated through this cmdlet. If the address is valid, MSAGValid will be set to True. Omitting this parameter will leave the MSAGValid value unchanged.</p></td>
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

Accepts pipelined input containing a Location Information Server (LIS) civic address object.

## Return Types

This cmdlet does not return a value.

## 另请参阅

#### 其他资源

[Get-CsLisCivicAddress](get-csliscivicaddress.md)

