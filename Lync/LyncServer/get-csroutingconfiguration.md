---
title: Get-CsRoutingConfiguration
TOCTitle: Get-CsRoutingConfiguration
ms:assetid: 37a1cbc9-b8b2-423c-8ebb-7947fdcad24e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425851(v=OCS.15)
ms:contentKeyID: 49312526
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsRoutingConfiguration

 

_**上一次修改主题：** 2015-03-09_

Retrieves the routing configuration object, which contains a list of all voice routes defined within a Lync Server deployment. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsRoutingConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsRoutingConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

This example retrieves the routing configuration. To retrieve individual voice routes, use the **Get-CsVoiceRoute** cmdlet.

    Get-CsRoutingConfiguration

## Detailed Description

Voice routes contain instructions that tell Lync Server how to route calls from Enterprise Voice users to phone numbers on the public switched telephone network (PSTN) or a private branch exchange (PBX). This cmdlet is used to retrieve the global instance that holds a list of all voice routes defined within the Lync Server deployment. To retrieve individual voice routes or to retrieve them as individual objects rather than as a list, use the **Get-CsVoiceRoute** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsRoutingConfiguration** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsRoutingConfiguration"}

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
<td><p><em>Filter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>There can be only one instance of this object, so this parameter does nothing.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>The scope of the routing configuration to retrieve. The only possible value is Global.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the routing configuration from the local replica of the 中央管理存储, rather than the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None.

## Return Types

The **Get-CsRoutingConfiguration** cmdlet returns instances of the Microsoft.Rtc.Management.Writable.Policy.Voice.PSTNRoutingSettings object.

## 另请参阅

#### 其他资源

[New-CsRoutingConfiguration](new-csroutingconfiguration.md)  
[Remove-CsRoutingConfiguration](remove-csroutingconfiguration.md)  
[Set-CsRoutingConfiguration](set-csroutingconfiguration.md)  
[Get-CsVoiceRoute](get-csvoiceroute.md)

