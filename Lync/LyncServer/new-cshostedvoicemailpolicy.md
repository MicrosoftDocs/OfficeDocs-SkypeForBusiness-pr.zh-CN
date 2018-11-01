---
title: New-CsHostedVoicemailPolicy
TOCTitle: New-CsHostedVoicemailPolicy
ms:assetid: 81e1ec62-45c4-49ad-8e2b-3568c092b6c1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398653(v=OCS.15)
ms:contentKeyID: 49313433
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsHostedVoicemailPolicy

 

_**上一次修改主题：** 2015-03-09_

Creates a new hosted voice mail policy. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsHostedVoicemailPolicy -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Description <String>] [-Destination <String>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-Organization <String>] [-Tenant <Guid>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This command creates a new hosted voice mail policy named ExRedmond. (The fact that no scope is specified means that this policy can be assigned to individual users or contacts.) This policy defines the Exchange UM destination for this policy to be at FQDN ExUM.fabrikam.com. In addition, the Lync Server users of this policy can be spread across the corp1 and corp2 organizations of litwareinc. This policy is described as (has a Description parameter value of) "Hosted voice mail property for Redmond users."

    New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voicemail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"

## Example 2

The commands shown in Example 2 are a variation of the command shown in Example 1; in this case, however, the new hosted voicemail policy is assigned to the Lync Online tenant with the tenant ID 73d355dd-ce5d-4ab9-bf49-7b822c18dd98. To create a new policy for a Lync Online tenant you must include the InMemory parameter and store the resulting policy in a variable. That’s what happens in the first command, with the new policy stored in a variable named $x. Note, too that you must set the Identity to Global and the Tenant parameter to the appropriate tenant ID.

To create the new policy, the second command then calls the **Set-CsHostedVoicemailPolicy** cmdlet along with the Instance parameter and the Tenant parameter.

    $x = New-CsHostedVoiceMailPolicy -Identity global -Tenant "73d355dd-ce5d-4ab9-bf49-7b822c18dd98" -Destination ExUM.fabrikam.com -Description "Hosted voicemail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    Set-CsHostedVoicemailPolicy -Instance $x -Tenant "73d355dd-ce5d-4ab9-bf49-7b822c18dd98"

## Detailed Description

This cmdlet creates a policy that configures a user account enabled for Lync Server or Office Communications Server to use an Exchange 统一消息 (UM) hosted voice mail service. The policy determines how to route unanswered calls to the user to a hosted Exchange UM service.

A user must be enabled for Exchange UM hosted voice mail for this policy to take effect. You can call the **Get-CsUser** cmdlet and check the HostedVoiceMail property to determine whether a user is enabled for hosted voice mail. (A value of True means the user is enabled.)

Policies created at the site scope will be automatically assigned to the users homed on those sites. Policies created at the per-user scope must be assigned to users or contact objects with the **Grant-CsHostedVoicemailPolicy** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsHostedVoicemailPolicy** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsHostedVoicemailPolicy"}

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
<td><p>A unique identifier for the policy, which includes the scope and site (for a site policy, such as site:Redmond), or the policy name (for a per-user policy, such as RenoHostedVoicemail). A global policy will always exist and can’t be removed, so you cannot create a global policy.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>A friendly description of the policy.</p></td>
</tr>
<tr class="even">
<td><p><em>Destination</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The value assigned to this parameter is the fully qualified domain name (FQDN) of the hosted Exchange UM service. Note that the chosen destination must be trusted for routing.</p>
<p>This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</p>
<p>This value must be 255 characters or less and in the form of an FQDN, such as server.litwareinc.com.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
</tr>
<tr class="even">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
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
<td><p>Globally unique identifier (GUID) of the Skype for Business Online tenant account for which the new hosted voicemail policy is being created. For example:</p>
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

None.

## Return Types

This cmdlet creates an object of type Microsoft.Rtc.Management.WritableConfig.Policy.Voice.HostedVoicemailPolicy

## 另请参阅

#### 其他资源

[Remove-CsHostedVoicemailPolicy](remove-cshostedvoicemailpolicy.md)  
[Set-CsHostedVoicemailPolicy](Set-CsHostedVoicemailPolicy.md)  
[Get-CsHostedVoicemailPolicy](get-cshostedvoicemailpolicy.md)  
[Grant-CsHostedVoicemailPolicy](grant-cshostedvoicemailpolicy.md)

