---
title: Get-CsEnhancedEmergencyServiceDisclaimer
TOCTitle: Get-CsEnhancedEmergencyServiceDisclaimer
ms:assetid: b5e3a01e-4056-47a0-9c3c-efdf55a08f69
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412877(v=OCS.15)
ms:contentKeyID: 49314009
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsEnhancedEmergencyServiceDisclaimer

 

_**上一次修改主题：** 2015-03-09_

Retrieves the disclaimer text that is used globally to prompt for location information for an Enhanced 9-1-1 (E9-1-1) implementation. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsEnhancedEmergencyServiceDisclaimer [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsEnhancedEmergencyServiceDisclaimer [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

This command retrieves the text of the enhanced emergency service disclaimer.

    Get-CsEnhancedEmergencyServiceDisclaimer

## Detailed Description

In order for an Enterprise Voice implementation to provide E9-1-1 service, locations must be mapped to ports, subnets, switches, and wireless access points to identify the caller’s location. When the caller is connecting from outside one of these mapped points, he must enter his location manually in order for it to be received by emergency services. This cmdlet retrieves a text string that will be displayed to users who decide not to enter their location information. This message will be displayed only if the LocationRequired property of the user’s location policy is set to Disclaimer. (You can retrieve location policy settings by calling the **Get-CsLocationPolicy** cmdlet.)

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsEnhancedEmergencyServiceDisclaimer** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsEnhancedEmergencyServiceDisclaimer"}

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
<td><p>This parameter allows for wildcard searches of the Identity. However, since the only valid value for Identity is Global, this parameter is not useful for this cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>This will always be Global.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the disclaimer information from the local replica of the 中央管理存储, rather than the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None.

## Return Types

Returns an object of type Microsoft.Rtc.Management.WritableConfig.Policy.Location.EnhancedEmergencyServiceDisclaimer.

## 另请参阅

#### 其他资源

[Remove-CsEnhancedEmergencyServiceDisclaimer](remove-csenhancedemergencyservicedisclaimer.md)  
[Set-CsEnhancedEmergencyServiceDisclaimer](set-csenhancedemergencyservicedisclaimer.md)  
[Get-CsLocationPolicy](get-cslocationpolicy.md)

