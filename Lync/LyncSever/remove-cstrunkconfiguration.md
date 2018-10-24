---
title: Remove-CsTrunkConfiguration
TOCTitle: Remove-CsTrunkConfiguration
ms:assetid: 45546534-1a18-4db2-be61-850bacf55a52
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425943(v=OCS.15)
ms:contentKeyID: 49312704
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsTrunkConfiguration

 

_**上一次修改主题：** 2015-03-09_

Removes an existing trunk configuration that describes the settings for a trunking peer entity such as a public switched telephone network (PSTN) gateway, IP-public branch exchange (PBX), or Session Border Controller (SBC) at the service provider. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsTrunkConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This example removes the trunk configuration with the Identity site:Redmond.

    Remove-CsTrunkConfiguration -Identity site:Redmond

## EXAMPLE 2

Example 2 removes all trunk configurations defined at the site level. The first part of the command is a call to the **Get-CsTrunkConfiguration** cmdlet that uses the Filter parameter to retrieve all trunk configurations with an Identity beginning with site: (that is, all trunk configurations defined at the site level). This collection of configurations is then piped to the **Remove-CsTrunkConfiguration** cmdlet, which removes each object in the collection.

    Get-CsTrunkConfiguration -Filter site:* | Remove-CsTrunkConfiguration

## Detailed Description

Use this cmdlet to remove a trunking configuration applicable to PSTN gateway entities. Each configuration contains specific settings for a trunking peer entity such as a PSTN gateway, IP-PBX, or SBC at the service provider. These settings configure such things as whether media bypass is enabled on this trunk, whether real-time transport control protocol (RTCP) packets are sent under certain conditions, and whether to require secure real-time protocol (SRTP) encryption.

Note that if you call the **Remove-CsTrunkConfiguration** cmdlet on the Global configuration, that trunk configuration will not be removed. Instead the configuration will be "reset" and all custom settings will be replaced with default values.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsTrunkConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsTrunkConfiguration"}

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
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>The unique identifier of the trunk configuration you want to remove.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.TrunkConfiguration.TrunkConfiguration object. Accepts pipelined input of trunk configuration objects.

## Return Types

This cmdlet does not return a value. It removes an object of type Microsoft.Rtc.Management.WritableConfig.Settings.TrunkConfiguration.TrunkConfiguration.

## 另请参阅

#### 其他资源

[New-CsTrunkConfiguration](new-cstrunkconfiguration.md)  
[Set-CsTrunkConfiguration](Set-CsTrunkConfiguration.md)  
[Get-CsTrunkConfiguration](get-cstrunkconfiguration.md)  
[Test-CsTrunkConfiguration](test-cstrunkconfiguration.md)

