---
title: Get-CsLisCivicAddress
TOCTitle: Get-CsLisCivicAddress
ms:assetid: 6538b811-6b74-4c57-95f7-e1496df62e7f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398459(v=OCS.15)
ms:contentKeyID: 49313077
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsLisCivicAddress

 

_**上一次修改主题：** 2015-03-09_

Retrieves only the address portion of one or more locations in the location configuration database for Enhanced 9-1-1 (E9-1-1). 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsLisCivicAddress

## Examples

## EXAMPLE 1

This example retrieves all civic addresses from the location database. The **Get-CsLisCivicAddress** cmdlet does not accept any parameters (other than the common Windows PowerShell parameters such as Verbose). Therefore any call to the **Get-CsLisCivicAddress** cmdlet will always return all civic addresses. See Example 2 for a command that will allow you to retrieve more specific results.

    Get-CsLisCivicAddress

## EXAMPLE 2

In this example, all the civic addresses in the city of Redmond are retrieved. The example begins with a call to the **Get-CsLisCivicAddress** cmdlet, which retrieves a collection of all civic addresses in the location database. This collection is then piped to the **Where-Object** cmdlet, which will return only those items in the collection with a City property value equal to (-eq) Redmond.

    Get-CsLisCivicAddress | Where-Object {$_.City -eq "Redmond"}

## EXAMPLE 3

Example 3 retrieves all Location Information Server (LIS) civic addresses that have been validated against the Master Street Address Guide (MSAG).

    Get-CsLisCivicAddress | Where-Object {$_.MSAGValid -eq $true}

## Detailed Description

E9-1-1 enables those who answer emergency calls to determine the caller’s geographic location without having to ask the caller for that information. In Lync Server, the location is determined based on mapping the caller’s port, subnet, switch, or wireless access point to a specific location. This cmdlet retrieves one or more of the addresses associated with these locations.

This cmdlet differs from the **Get-CsLisLocation** cmdlet in that it returns only unique addresses. It does not return the company name or a location name, it returns only address information. It also returns a flag (MSAGValid) that specifies whether the address has been validated against the Master Street Address Guide. This flag can be automatically updated by running the **Test-CsLisCivicAddress** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsLisCivicAddress** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsLisCivicAddress"}

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

This cmdlet retrieves one or more objects of type System.Management.Automation.PSCustomObject.

## 另请参阅

#### 其他资源

[Test-CsLisCivicAddress](test-csliscivicaddress.md)  
[Get-CsLisLocation](get-cslislocation.md)

