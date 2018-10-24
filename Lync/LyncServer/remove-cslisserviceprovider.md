---
title: Remove-CsLisServiceProvider
TOCTitle: Remove-CsLisServiceProvider
ms:assetid: d26302bf-7794-4125-af80-ba7c92096b6d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398904(v=OCS.15)
ms:contentKeyID: 49314339
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsLisServiceProvider

 

_**上一次修改主题：** 2015-03-09_

Removes an object containing information about the web service provided by the Enhanced 9-1-1 (E9-1-1) Network Routing Provider to verify locations. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsLisServiceProvider [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This example removes the service provider web service from the E9-1-1 implementation. There will only be, at most, one service provider defined, which will be removed by this cmdlet.

    Remove-CsLisServiceProvider

## Detailed Description

In an Enterprise Voice implementation with E9-1-1, emergency calls must first be routed through an E9-1-1 Network Routing Provider to ensure that the calls are routed to the appropriate Public Safety Answering Point (PSAP). (A PSAP is the agency in the United States that directs the calls to the nearest emergency services, such as police, fire, and ambulance services.) In order to do this, the provider must have a list of locations from the organization that it can then match against the Master Street Address Guide to ensure all locations are valid. This cmdlet removes an entry for a provider; after running this cmdlet there will be no web service access to the provider.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsLisServiceProvider** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsLisServiceProvider"}

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

Accepts pipelined input of a Location Information Server (LIS) service provider object.

## Return Types

This cmdlet does not return an object or a value. It removes an object of type System.Management.Automation.PSCustomObject.

## 另请参阅

#### 其他资源

[Set-CsLisServiceProvider](set-cslisserviceprovider.md)  
[Get-CsLisServiceProvider](get-cslisserviceprovider.md)

