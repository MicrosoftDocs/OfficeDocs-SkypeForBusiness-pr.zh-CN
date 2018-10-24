---
title: Remove-CsMediaConfiguration
TOCTitle: Remove-CsMediaConfiguration
ms:assetid: 8af2b8cb-4d58-4f8a-9acb-9b5104880bc9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398705(v=OCS.15)
ms:contentKeyID: 49313531
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsMediaConfiguration

 

_**上一次修改主题：** 2015-03-09_

Removes the specified collection of media configuration settings. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsMediaConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In Example 1, the **Remove-CsMediaConfiguration** cmdlet is used to delete the media configuration collection with the Identity site:Redmond1. When media settings are removed from the site scope, that site will automatically begin to use the global media settings.

    Remove-CsMediaConfiguration -Identity site:Redmond1

## EXAMPLE 2

In Example 2, three cmdlets—the **Get-CsMediaConfiguration** cmdlet, the **Where-Object** cmdlet, and the **Remove-CsMediaConfiguration**cmdlet—are used to remove all the media configuration collections where encryption is required of all parties involved in the conversation. To do this, the **Get-CsMediaConfiguration** cmdlet is first used to return all the media configuration collections in the organization. That information is then piped to the **Where-Object** cmdlet, which applies a filter that restricts the pipeline data to those collections where the EncryptionLevel property is equal to (-eq) RequireEncryption. Finally, that filtered set of data is passed to the **Remove-CsMediaConfiguration** cmdlet, which deletes each item in the set.

    Get-CsMediaConfiguration | Where-Object {$_.EncryptionLevel -eq "RequireEncryption"} | Remove-CsMediaConfiguration

## EXAMPLE 3

In this example all media configurations defined at the service scope (meaning the configuration applies to a specific service) are removed. This is accomplished by first calling the **Get-CsMediaConfiguration** cmdlet using the Filter service:\*. This filter retrieves all media configuration collections with an Identity starting with service, which means all collections at the service scope. That set of collections is then piped the **Remove-CsMediaConfiguration** cmdlet, which removes them all.

    Get-CsMediaConfiguration -Filter service:* | Remove-CsMediaConfiguration

## Detailed Description

This cmdlet removes a collection of media settings. These settings relate to audio and video calls between client endpoints.

This cmdlet can also be used to remove the global media settings. In that case, however, the settings will not actually be removed; instead, they will simply be reset to their default values.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsMediaConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsMediaConfiguration"}

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
<td><p>The unique identifier of the media configuration settings you want to remove. This identifier specifies the scope at which this configuration is applied (global, site, or service).</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.Media.MediaSettings object. Accepts pipelined input of media configuration objects.

## Return Types

Removes an object of type Microsoft.Rtc.Management.WritableConfig.Settings.Media.MediaSettings.

## 另请参阅

#### 其他资源

[New-CsMediaConfiguration](new-csmediaconfiguration.md)  
[Set-CsMediaConfiguration](set-csmediaconfiguration.md)  
[Get-CsMediaConfiguration](get-csmediaconfiguration.md)

