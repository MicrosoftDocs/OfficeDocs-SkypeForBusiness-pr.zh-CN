---
title: Get-CsLisServiceProvider
TOCTitle: Get-CsLisServiceProvider
ms:assetid: 060b0b32-5787-487b-b1d9-7a0c7dd44d80
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398116(v=OCS.15)
ms:contentKeyID: 49311884
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsLisServiceProvider

 

_**上一次修改主题：** 2015-03-09_

Retrieves information about the web service provided by the Enhanced 9-1-1 (E9-1-1) Network Routing Provider to validate locations. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsLisServiceProvider

## Examples

## EXAMPLE 1

The **Get-CsLisServiceProvider** cmdlet does not have any parameters (other than the Windows PowerShell common parameters, such as Verbose). There will never be more than one service provider for an E9-1-1 implementation, so this cmdlet will retrieve information about the web service provided by that service provider.

    Get-CsLisServiceProvider

## Detailed Description

In an Enterprise Voice implementation with E9-1-1, emergency calls must first be routed through an E9-1-1 Network Routing Provider to ensure that the calls are routed to the appropriate Public Safety Answering Point (PSAP). (A PSAP is the agency in the United States that directs the calls to the nearest emergency services, such as police, fire, and ambulance services.) In order to do this, the provider must have a list of locations from the organization that it can then match against the Master Street Address Guide to ensure all locations are valid. This cmdlet retrieves information about a provider, including the name of the provider and a URL for the web service that the organization will use to send the locations.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsLisServiceProvider** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsLisServiceProvider"}

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

This cmdlet retrieves an object of type System.Management.Automation.PSCustomObject.

## 另请参阅

#### 其他资源

[Remove-CsLisServiceProvider](remove-cslisserviceprovider.md)  
[Set-CsLisServiceProvider](set-cslisserviceprovider.md)

