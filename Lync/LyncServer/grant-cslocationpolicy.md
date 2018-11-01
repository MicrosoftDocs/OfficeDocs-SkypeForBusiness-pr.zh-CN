---
title: Grant-CsLocationPolicy
TOCTitle: Grant-CsLocationPolicy
ms:assetid: f820f892-c247-447c-947a-00414189842e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413049(v=OCS.15)
ms:contentKeyID: 49314789
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Grant-CsLocationPolicy

 

_**上一次修改主题：** 2015-03-09_

Assigns an Enhanced 9-1-1 (E9-1-1) location policy to individual users or groups. The E9-1-1 service enables those who answer 911 calls to determine the caller’s geographic location. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Grant-CsLocationPolicy -Identity <UserIdParameter> [-Confirm [<SwitchParameter>]] [-DomainController <Fqdn>] [-PassThru <SwitchParameter>] [-PolicyName <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In Example 1, the **Grant-CsLocationPolicy** cmdlet is used to assign the Reno location policy to user Ken Myer.

    Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName Reno

## EXAMPLE 2

In Example 2, the AccountingArea policy is assigned to all the users who are in the Accounting department. To return a collection of all the users in the Accounting department, the **Get-CsUser** cmdlet is used along with the LDAPFilter parameter. The query value passed to LDAPFilter--"Department=Accounting"--returns all the users who have an Active Directory Department setting of Accounting. This collection is then passed to the **Grant-CsLocationPolicy** cmdlet, which proceeds to assign the AccountingArea policy to each user in the collection.

    Get-CsUser -LDAPFilter "Department=Accounting" | Grant-CsLocationPolicy -PolicyName AccountingArea

## EXAMPLE 3

This example grants the location policy Reno to the user with the Identity (in this case, the display name) Ken Myer. In addition, the example includes the parameter PassThru, which will cause the user information for user Ken Myer to be displayed after the location policy has been granted. However, rather than immediately displaying the user information to the console, that information is piped to the **Select-Object** cmdlet, which will display only the DisplayName and LocationPolicy properties of the user.

One thing to notice with this example is that the newly granted location policy will appear in the output under LocationPolicy, but it will appear as an Anchor value rather than as a policy name. (An Anchor value is a numeric value automatically assigned to a policy at the time it is created.) To see that the policy name has been applied, run the command Get-CsUser –Identity "Ken Myer" | Select-Object DisplayName, LocationPolicy.

    Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName Reno -PassThru | Select-Object DisplayName, LocationPolicy

## Detailed Description

The location policy is used to apply settings that relate to E9-1-1 functionality. The location policy determines whether a user is enabled for E9-1-1, and if so, what the behavior is of an emergency call. For example, you can use the location policy to define what number constitutes an emergency call (911 in the United States), whether corporate security should be automatically notified, and how the call should be routed. This cmdlet grants a location policy to a specific user or group.

IMPORTANT: The location policy behaves differently from other policies in Lync Server in terms of order of scope. For all other policies, if a policy is defined at the per-user scope, the policy is applied to any user granted that policy. If the user has not been granted a per-user policy, the site policy is applied. If there is no site policy, the global policy is applied. Location policies are applied in the same way, with one exception: a per-user location policy can also be assigned to a network site. (A network site consists of a group of subnets.) If the user is making the emergency call from a location that is mapped to a network site within the organization, the user-level policy assigned to that network site is used. This functionality will override a per-user policy that has been granted to that user. If the user calls from a location that is unknown or unmapped in the organization, the standard policy scoping will be applied.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Grant-CsLocationPolicy** cmdlet locally: RTCUniversalUserAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Grant-CsLocationPolicy"}

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
<td><p>Indicates the Identity of the user account the policy should be assigned to. User identities can be specified using one of four formats: 1) The user's SIP address; 2) the user's user principal name (UPN); 3) the user's domain name and logon name, in the form domain\logon (for example, litwareinc\kenmyer); and, 4) the user's Active Directory display name (for example, Ken Myer). Note that the SAMAccountName cannot be used as an identity.</p>
<p>In addition, you can use the asterisk (*) wildcard character when using the Display Name as the user Identity. For example, the Identity &quot;* Smith&quot; would grant the policy to all the users with the last name Smith.</p></td>
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
<td><p>Including this parameter (which does not take a value) displays the user information when the cmdlet completes. Normally there is no output when this cmdlet is run.</p></td>
</tr>
<tr class="odd">
<td><p><em>PolicyName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The Identity of the location policy to apply to the user.</p></td>
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

String. Accepts a pipelined string value representing the Identity of a user account to which the location policy is being granted.

## Return Types

When used with the PassThru parameter, returns an object of type Microsoft.Rtc.Management.ADConnect.Schema.OCSADUserOrAppContact.

## 另请参阅

#### 其他资源

[New-CsLocationPolicy](new-cslocationpolicy.md)  
[Remove-CsLocationPolicy](remove-cslocationpolicy.md)  
[Set-CsLocationPolicy](set-cslocationpolicy.md)  
[Get-CsLocationPolicy](get-cslocationpolicy.md)  
[Test-CsLocationPolicy](test-cslocationpolicy.md)  
[Get-CsUser](get-csuser.md)

