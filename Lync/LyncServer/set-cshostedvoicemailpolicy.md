---
title: Set-CsHostedVoicemailPolicy
TOCTitle: Set-CsHostedVoicemailPolicy
ms:assetid: 9c47d2a5-356c-4bab-9cef-8346c4b5d99c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412722(v=OCS.15)
ms:contentKeyID: 49313726
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsHostedVoicemailPolicy

 

_**上一次修改主题：** 2015-03-09_

Modifies a hosted voice mail policy. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsHostedVoicemailPolicy [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsHostedVoicemailPolicy [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Description <String>] [-Destination <String>] [-Force <SwitchParameter>] [-Organization <String>] [-Tenant <Guid>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This command modifies the Destination property of a hosted voice mail policy named ExRedmond. It sets the Exchange UM destination for this policy to be at FQDN ExUM.contoso.com.

    Set-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.contoso.com

## EXAMPLE 2

This command adds an Exchange tenant to the comma-separated list of tenants (organizations) for the policy ExRedmond. The first line calls the **Get-CsHostedVoicemailPolicy** cmdlet to retrieve the policy with the Identity ExRedmond. This cmdlet call is in parentheses because we need to first retrieve this policy. We then use "dot notation" to retrieve the Organization property of the policy. We save the returned string in the variable $a. The next line uses the += operator to append the assigned string (,corp3.litwareinc.com) to the end of the string stored in variable $a. (Note the comma in the assigned string. Organization is a comma-separated list, so if there’s already a value in the list any additional values need to be preceded by a comma.) Finally, in the last line we call the **Set-CsHostedVoicemailPolicy** cmdlet and assign the new Organization string by passing the variable $a to the parameter Organization.

    $a = (Get-CsHostedVoicemailPolicy -Identity ExRedmond).Organization
    $a += ",corp3.litwareinc.com"
    Set-CsHostedVoicemailPolicy -Identity ExRedmond -Organization $a

## Example 3

The command shown in Example 3 modifies the Destination property of the hosted voicemail policy assigned to the Lync Online tenant with the tenant ID 73d355dd-ce5d-4ab9-bf49-7b822c18dd98.

    Set-CsHostedVoicemailPolicy -Tenant "73d355dd-ce5d-4ab9-bf49-7b822c18dd98" -Destination "ExUM.contoso.com"

## Detailed Description

This cmdlet modifies a policy that configures a user account enabled for Lync Server or Microsoft Office Communications Server to use an Exchange 统一消息 (UM) hosted voice mail service. The policy determines how to route unanswered calls to the user to a hosted Exchange UM service.

A user must be enabled for Exchange UM hosted voice mail for this policy to take effect. You can call the **Get-CsUser** cmdlet and check the HostedVoiceMail property to determine whether a user is enabled for hosted voice mail. (A value of True means the user is enabled.)

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsHostedVoicemailPolicy** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsHostedVoicemailPolicy"}

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
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>A friendly description of the policy.</p></td>
</tr>
<tr class="odd">
<td><p><em>Destination</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The value assigned to this parameter is the fully qualified domain name (FQDN) of the hosted Exchange UM service. Note that the chosen destination must be trusted for routing.</p>
<p>If you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</p>
<p>This value must be 255 characters or less and in a format matching the regular expression string ^[a-zA-Z0-9\-_]+(\.[a-zA-Z0-9\-_]+){0,}$. This just means it should be in the form of an FQDN, such as server.litwareinc.com.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>A unique identifier for the hosted voice mail policy you want to modify. This identifier includes the scope (in the case of global), the scope and site (for a site policy, such as site:Redmond), or the policy name (for a per-user policy, such as HVUserPolicy).</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>HostedVoicemailPolicy</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。 The object must be of type HostedVoicemailPolicy and can be retrieved by calling the <strong>Get-CsHostedVoicemailPolicy</strong> cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><em>Organization</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>This parameter contains a comma-separated list of the Exchange tenants that contain Lync Server users. Each tenant must be specified as an FQDN of the tenant on the hosted Exchange Service.</p></td>
</tr>
<tr class="even">
<td><p><em>Tenant</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Guid</p></td>
<td><p>Globally unique identifier (GUID) of the Skype for Business Online tenant account for which hosted voicemail policy being modified. For example:</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>You can return the tenant ID for each of your tenants by running this command:</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Policy.Voice.HostedVoicemailPolicy object. Accepts pipelined input of hosted voice mail policy objects.

## Return Types

This cmdlet modifies an object of type Microsoft.Rtc.Management.WritableConfig.Policy.Voice.HostedVoicemailPolicy

## 另请参阅

#### 其他资源

[New-CsHostedVoicemailPolicy](new-cshostedvoicemailpolicy.md)  
[Remove-CsHostedVoicemailPolicy](remove-cshostedvoicemailpolicy.md)  
[Get-CsHostedVoicemailPolicy](get-cshostedvoicemailpolicy.md)  
[Grant-CsHostedVoicemailPolicy](grant-cshostedvoicemailpolicy.md)

