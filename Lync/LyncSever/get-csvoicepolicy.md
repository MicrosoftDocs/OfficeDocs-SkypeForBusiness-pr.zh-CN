---
title: Get-CsVoicePolicy
TOCTitle: Get-CsVoicePolicy
ms:assetid: 05096aec-321c-4a50-99be-6e9fbbbe17fa
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398101(v=OCS.15)
ms:contentKeyID: 49311862
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsVoicePolicy

 

_**上一次修改主题：** 2015-03-09_

Returns information about one or more voice policies configured for your organization. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsVoicePolicy [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsVoicePolicy [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>] [-Tenant <Guid>]

## Examples

## EXAMPLE 1

This example displays all the voice policies that have been defined for an organization along with the settings for each.

    Get-CsVoicePolicy

## EXAMPLE 2

This example uses the Identity parameter to retrieve the voice policy settings for the per-user policy named UserPolicy1.

    Get-CsVoicePolicy -Identity UserPolicy1

## EXAMPLE 3

This example uses the Filter parameter to retrieve all the voice policy settings that can be assigned to users. All per-user voice policies have an Identity in the format **tag:\<UserVoicePolicy\>**, so we filter on tag to retrieve all user voice policies.

    Get-CsVoicePolicy -Filter tag*

## Detailed Description

This cmdlet retrieves voice policy information. Voice policies are used to manage such Enterprise Voice-related features as simultaneous ringing (the ability to have a second phone ring each time someone calls your office phone) and call forwarding. Use this cmdlet to retrieve the settings that enable and disable many of these features.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsVoicePolicy** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsVoicePolicy"}

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
<td><p>This parameter accepts a wildcard string and returns all voice policies with identities matching that string. For example, a Filter value of site:* will return all voice policies defined at the site level.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>A unique identifier specifying the scope, and in some cases the name, of the policy. If this parameter is omitted, all voice policies for the organization are returned.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the voice policy from the local replica of the 中央管理存储, rather than the 中央管理存储 itself.</p></td>
</tr>
<tr class="even">
<td><p><em>Tenant</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Guid</p></td>
<td><p>Globally unique identifier (GUID) of the Skype for Business Online tenant account whose voice policy is to be retrieved. For example:</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>You can return the tenant ID for each of your tenants by running this command:</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p>
<p>If you are using a remote session of Windows PowerShell and are connected only to Skype for Business Online you do not have to include the Tenant parameter. Instead, the tenant ID will automatically be filled in for you based on your connection information. The Tenant parameter is primarily for use in a hybrid deployment.</p></td>
</tr>
</tbody>
</table>


## Input Types

None.

## Return Types

This cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Policy.Voice.VoicePolicy object.

## 另请参阅

#### 其他资源

[New-CsVoicePolicy](new-csvoicepolicy.md)  
[Remove-CsVoicePolicy](remove-csvoicepolicy.md)  
[Set-CsVoicePolicy](set-csvoicepolicy.md)  
[Grant-CsVoicePolicy](grant-csvoicepolicy.md)  
[Test-CsVoicePolicy](test-csvoicepolicy.md)

