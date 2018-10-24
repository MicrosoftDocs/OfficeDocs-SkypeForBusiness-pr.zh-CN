---
title: Remove-CsVoicePolicy
TOCTitle: Remove-CsVoicePolicy
ms:assetid: 4d3e67be-c094-415f-b1e6-0719dec6f3fc
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398309(v=OCS.15)
ms:contentKeyID: 49312792
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsVoicePolicy

 

_**上一次修改主题：** 2015-03-09_

Removes the specified voice policy. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsVoicePolicy -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Tenant <Guid>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This example removes the UserVoicePolicy1 per-user voice policy settings.

    Remove-CsVoicePolicy -Identity UserVoicePolicy1

## EXAMPLE 2

This example removes all the voice policy settings that can be assigned to specific users. First the **Get-CsVoicePolicy** cmdlet is called with a Filter of tag\*, which retrieves all the per-user voice policies. That collection of policies is then piped to the **Remove-CsVoicePolicy** cmdlet to be removed.

    Get-CsVoicePolicy -Filter tag* | Remove-CsVoicePolicy

## Detailed Description

This cmdlet removes an existing voice policy. Voice policies are used to manage such Enterprise Voice-related features as simultaneous ringing (the ability to have a second phone ring each time someone calls your office phone) and call forwarding. This cmdlet can also be used to remove the global voice policy. In that case, however, the policy will not actually be removed; instead, the policy settings will simply be reset to their default values.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsVoicePolicy** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsVoicePolicy"}

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
<td><p>A unique identifier specifying the scope, and in some cases the name, of the policy to be removed.</p></td>
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
<td><p><em>Tenant</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Guid</p></td>
<td><p>Globally unique identifier (GUID) of the Office 365 tenant account for the voice policy being deleted. For example:</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>You can return the tenant ID for each of your tenants by running this command:</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p>
<p>If you are using a remote session of Windows PowerShell and are connected only to Skype for Business Online you do not have to include the Tenant parameter. Instead, the tenant ID will automatically be filled in for you based on your connection information. The Tenant parameter is primarily for use in a hybrid deployment.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Policy.Voice.VoicePolicy object. Accepts pipelined input of voice policy objects.

## Return Types

This cmdlet does not return a value. It removes an instance of a Microsoft.Rtc.Management.WritableConfig.Policy.Voice.VoicePolicy object.

## 另请参阅

#### 其他资源

[New-CsVoicePolicy](new-csvoicepolicy.md)  
[Set-CsVoicePolicy](set-csvoicepolicy.md)  
[Get-CsVoicePolicy](get-csvoicepolicy.md)  
[Grant-CsVoicePolicy](grant-csvoicepolicy.md)  
[Test-CsVoicePolicy](test-csvoicepolicy.md)

