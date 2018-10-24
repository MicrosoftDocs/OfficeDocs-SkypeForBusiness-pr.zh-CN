---
title: Grant-CsDialPlan
TOCTitle: Grant-CsDialPlan
ms:assetid: 730ad014-b1e8-4f0a-be78-32b1b5488b78
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398547(v=OCS.15)
ms:contentKeyID: 49313244
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Grant-CsDialPlan

 

_**上一次修改主题：** 2015-03-09_

Assigns a dial plan to one or more users or groups. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Grant-CsDialPlan -Identity <UserIdParameter> [-Confirm [<SwitchParameter>]] [-DomainController <Fqdn>] [-PassThru <SwitchParameter>] [-PolicyName <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In the example, the **Grant-CsDialPlan** cmdlet is used to assign the dial plan RedmondDialPlan to the user with the Identity (in this case the display name) Ken Myer.

    Grant-CsDialPlan -Identity "Ken Myer" -PolicyName RedmondDialPlan

## EXAMPLE 2

In Example 2, the RedmondDialPlan dial plan is assigned to all the users who have offices in the city of Redmond. To do this, the **Get-CsUser** cmdlet is invoked in order to retrieve a collection of all the users who have an office in the city of Redmond; this is done by using the LdapFilter parameter and the LDAP query l=Redmond. (In the LDAP query language used by Active Directory 域服务, the l indicates a user's locality, or city.) This collection is then piped to the **Grant-CsDialPlan** cmdlet, which assigns the Redmond dial plan to each user in the collection.

    Get-CsUser -LDAPFilter "l=Redmond" | Grant-CsDialPlan -PolicyName RedmondDialPlan

## Detailed Description

This cmdlet assigns an existing user-specific dial plan to a user. Dial plans provide information required to enable Enterprise Voice users to make telephone calls. Users who do not have a valid dial plan will not be enabled to make calls by using Enterprise Voice. A dial plan determines such things as how normalization rules are applied and whether a prefix must be dialed for external calls.

You can check whether a user has been granted a per-user dial plan by calling a command in this format: Get-CsUser "\<user name\>" | Select-Object DialPlan. For example:

Get-CsUser "Ken Myer" | Select-Object DialPlan

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Grant-CsDialPlan** cmdlet locally: RTCUniversalUserAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Grant-CsDialPlan"}

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
<td><p>The Identity (unique identifier) of the user to whom the dial plan is being assigned.</p>
<p>User identities can be specified using one of four formats: 1) The user's SIP address; 2) the user's user principal name (UPN); 3) the user's domain name and logon name, in the form domain\logon (for example, litwareinc\kenmyer); and, 4) the user's Active Directory display name (for example, Ken Myer).</p>
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
<td><p>The Identity value of the dial plan to be assigned to the user. (Note that this includes only the name portion of the Identity. Per-user dial plan identities include a prefix of tag: that should not be included with the PolicyName.)</p></td>
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

String. Accepts a pipelined string value representing the Identity of a user account to which the dial plan is being granted.

## Return Types

When used with the PassThru parameter, returns an object of type Microsoft.Rtc.Management.ADConnect.Schema.OCSADUserOrAppContact.

## 另请参阅

#### 其他资源

[New-CsDialPlan](new-csdialplan.md)  
[Remove-CsDialPlan](remove-csdialplan.md)  
[Set-CsDialPlan](set-csdialplan.md)  
[Get-CsDialPlan](get-csdialplan.md)  
[Test-CsDialPlan](test-csdialplan.md)  
[Get-CsUser](get-csuser.md)

