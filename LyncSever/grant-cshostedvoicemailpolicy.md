---
title: Grant-CsHostedVoicemailPolicy
TOCTitle: Grant-CsHostedVoicemailPolicy
ms:assetid: ae69358f-1618-4a08-9ec2-225ded3f301f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412829(v=OCS.15)
ms:contentKeyID: 49313917
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Grant-CsHostedVoicemailPolicy

 

_**上一次修改主题：** 2015-03-09_

Assigns a hosted voice mail policy at the per-user scope. (The per-user scope enables you to assign policies to individual users or groups.) 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Grant-CsHostedVoicemailPolicy -Identity <UserIdParameter> [-Confirm [<SwitchParameter>]] [-DomainController <Fqdn>] [-PassThru <SwitchParameter>] [-PolicyName <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This example assigns the hosted voice mail policy with the Identity ExRedmond to the user with the display name Ken Myer.

    Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond

## EXAMPLE 2

This example assigns the hosted voice mail policy with the Identity ExRedmond to all users in the Finance organizational unit (OU): OU=Finance,OU=NorthAmerica,DC=litwareinc,DC=com. The first part of the command calls the **Get-CsUser** cmdlet to retrieve all users who are enabled for Lync Server or Office Communications Server from the specified OU. This collection of users is then piped to the **Grant-CsHostedVoicemailPolicy** cmdlet, which assigns the policy ExRedmond to each of these users.

    Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsHostedVoicemailPolicy -PolicyName ExRedmond

## Detailed Description

This cmdlet assigns an existing user-specific hosted voice mail policy to a user. A hosted voice mail policy specifies how to route unanswered calls to a user to a hosted Exchange 统一消息 (UM) service.

You can check whether a user has been granted a per-user hosted voice mail policy by calling a command in this format: Get-CsUser "\<user name\>" | Select-Object HostedVoicemailPolicy. For example:

Get-CsUser "Ken Myer" | Select-Object HostedVoicemailPolicy

If you assign to a user a hosted voice mail policy that does not include a destination, you cannot enable that user for hosted voice mail.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Grant-CsHostedVoicemailPolicy** cmdlet locally: RTCUniversalUserAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Grant-CsHostedVoicemailPolicy"}

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
<td><p>Microsoft.Rtc.Management.AD.UserIdParameter</p></td>
<td><p>The Identity (unique identifier) of the user to whom the hosted voice mail policy is being assigned.</p>
<p>User identities can be specified using one of four formats: 1) The user's SIP address; 2) the user’s user principal name (UPN); 3) the user's domain name and logon name, in the form domain\logon (for example, litwareinc\kenmyer); and, 4) the user's Active Directory display name (for example, Ken Myer).</p>
<p>Note that you can use the asterisk (*) wildcard character when using the Display Name as the user Identity. For example, the Identity &quot;* Smith&quot; would return all the users with the last name Smith.</p>
<p>Full data type: Microsoft.Rtc.Management.AD.UserIdParameter</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>DomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Allows you to specify a domain controller. If no domain controller is specified, the first available will be used.</p></td>
</tr>
<tr class="even">
<td><p><em>PassThru</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns the results of the command. By default, this cmdlet does not generate any output.</p></td>
</tr>
<tr class="odd">
<td><p><em>PolicyName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The name (Identity) of the hosted voice mail policy to be assigned to the user. (Note that this includes only the name portion of the Identity. Per-user hosted voice mail policy identities include a prefix of tag: that should not be included with the PolicyName.)</p></td>
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

String. Accepts a pipelined string value representing the Identity of a user account to which the hosted voice mail policy is being granted.

## Return Types

When used with the PassThru parameter, returns an object of type Microsoft.Rtc.Management.ADConnect.Schema.OCSADUserOrAppContact.

## 另请参阅

#### 其他资源

[New-CsHostedVoicemailPolicy](new-cshostedvoicemailpolicy.md)  
[Remove-CsHostedVoicemailPolicy](remove-cshostedvoicemailpolicy.md)  
[Set-CsHostedVoicemailPolicy](Set-CsHostedVoicemailPolicy.md)  
[Get-CsHostedVoicemailPolicy](get-cshostedvoicemailpolicy.md)  
[Get-CsUser](get-csuser.md)

