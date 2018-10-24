---
title: Get-CsHostedVoicemailPolicy
TOCTitle: Get-CsHostedVoicemailPolicy
ms:assetid: 52dd4397-b1c5-44a5-a744-75d715a4511b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398348(v=OCS.15)
ms:contentKeyID: 49312853
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsHostedVoicemailPolicy

 

_**上一次修改主题：** 2015-03-09_

Retrieves a hosted voice mail policy. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

``` PowerShell
Get-CsHostedVoicemailPolicy [-Identity <XdsIdentity>] <COMMON PARAMETERS>

Get-CsHostedVoicemailPolicy [-Filter <String>] <COMMON PARAMETERS>

COMMON PARAMETERS: [-LocalStore <SwitchParameter>] [-Tenant <Guid>]
```

## Examples

## EXAMPLE 1

This command returns all defined hosted voice mail policies for the Lync Server implementation.

``` PowerShell
CsHostedVoicemailPolicy
```

## EXAMPLE 2

This command returns the policy settings for the per-user hosted voice mail policy ExRedmond.

``` PowerShell
Get-CsHostedVoicemailPolicy -Identity ExRedmond
```

## EXAMPLE 3

This command returns the policy settings for all per-user hosted voice mail policies (policies beginning with the tag scope).

``` PowerShell
Get-CsHostedVoicemailPolicy -Filter tag:*
```

## EXAMPLE 4

This command returns the hosted voice mail policy for the Lync Online tenant with the tenant ID 73d355dd-ce5d-4ab9-bf49-7b822c18dd98.

``` PowerShell
Get-CsHostedVoicemailPolicy -Tenant "73d355dd-ce5d-4ab9-bf49-7b822c18dd98"
```

## Detailed Description

This cmdlet retrieves a policy that specifies how to route unanswered calls to a user to a hosted Exchange 统一消息 (UM) service.

A user must be enabled for Exchange UM hosted voice mail for this policy to take effect. You can call the **Get-CsUser** cmdlet and check the HostedVoiceMail property to determine whether a user is enabled for hosted voice mail. (A value of True means the user is enabled.)

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsHostedVoicemailPolicy** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsHostedVoicemailPolicy"}

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
<td><p>This parameter allows you to do a wildcard search on the Identity of the hosted voice mail policy. This will retrieve all instances of a hosted voice mail policy where the Identity matches the wildcard pattern specified in the Filter value.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>The unique identifier for the hosted voice mail policy you want to retrieve. The Identity includes the scope (in the case of global), the scope and site (for a site policy, such as site:Redmond), or the policy name (for a per-user policy, such as HVUserPolicy).</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the hosted voice mail policy from the local replica of the 中央管理存储, rather than the 中央管理存储 itself.</p></td>
</tr>
<tr class="even">
<td><p><em>Tenant</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Guid</p></td>
<td><p>Globally unique identifier (GUID) of the Skype for Business Online tenant account whose voicemail policy is to be retrieved.</p>
<p>For example:</p>
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

This cmdlet returns an object of type Microsoft.Rtc.Management.WritableConfig.Policy.Voice.HostedVoicemailPolicy

## 另请参阅

#### 其他资源

[New-CsHostedVoicemailPolicy](new-cshostedvoicemailpolicy.md)  
[Remove-CsHostedVoicemailPolicy](remove-cshostedvoicemailpolicy.md)  
[Set-CsHostedVoicemailPolicy](Set-CsHostedVoicemailPolicy.md)  
[Grant-CsHostedVoicemailPolicy](grant-cshostedvoicemailpolicy.md)

