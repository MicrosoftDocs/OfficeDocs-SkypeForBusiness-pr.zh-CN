---
title: Grant-CsPinPolicy
TOCTitle: Grant-CsPinPolicy
ms:assetid: ce5f610b-117b-46b3-ad06-0e93f5b7a4de
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398871(v=OCS.15)
ms:contentKeyID: 49314279
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Grant-CsPinPolicy

 

_**上一次修改主题：** 2015-03-09_

Assigns a client personal identification number (PIN) policy to a user or group of users. PIN authentication enables users to access Lync Server by providing a PIN instead of a user name and password. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Grant-CsPinPolicy -Identity <UserIdParameter> [-Confirm [<SwitchParameter>]] [-DomainController <Fqdn>] [-PassThru <SwitchParameter>] [-PolicyName <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 assigns the policy RedmondUsersPinPolicy to the user kenmyer@litwareinc.com.

    Grant-CsPinPolicy -Identity "kenmyer@litwareinc.com" -PolicyName RedmondUsersPinPolicy

## EXAMPLE 2

Example 2 unassigns any per-user PIN policy previously assigned to the user kenmyer@litwareinc.com. Calling the **Grant-CsPinPolicy** cmdlet and setting the policy name to a null value ($Null) removes any per-user policy assigned to the user.

    Grant-CsPinPolicy -Identity kenmyer@litwareinc.com -PolicyName $Null 

## EXAMPLE 3

In Example 3, the policy RedmondUsersPinPolicy is assigned to all the users who work in the city of Redmond. To do this, the **Get-CsUser** cmdlet first retrieves a collection of all the users who work in Redmond; this is done by including the LdapFilter parameter and using the filter value "l=Redmond". (With LDAP filters, l, a lowercase L, represents the user's locality.) That collection of users is then piped to the **Grant-CsPinPolicy** cmdlet, which assigns each user the policy RedmondUsersPinPolicy.

    Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName RedmondUsersPinPolicy

## EXAMPLE 4

In Example 4, the policy RedmondUsersPinPolicy is assigned to all the users who have not been assigned a per-user PIN policy. To determine which users have not been assigned a PIN policy, the **Get-CsUser** cmdlet is called, along with the Filter parameter; the filter value {ClientPinPolicy -eq $Null} returns only those users where the ClientPinPolicy property is null (that is, no per-user PIN policy has been assigned). That collection of users is then piped to the **Grant-CsPinPolicy** cmdlet, which assigns the policy RedmondUsersPinPolicy to each person in the collection.

    Get-CsUser -Filter {PinPolicy -eq $Null} | Grant-CsPinPolicy -PolicyName RedmondUsersPinPolicy

## Detailed Description

Lync Server enables users to connect to the system or to join public switched telephone network (PSTN) conferences via telephone. Typically, logging on to the system or joining a conference requires the user to enter a user name or password; unfortunately, entering a user name and password can be a problem if you are using a phone that does not have an alphanumeric keypad. Because of that, Lync Server enables you to supply users with numeric-only PINs; when prompted, users can then log on to the system or join a conference by entering the PIN instead of a user name and password.

Lync Server uses PIN policies to manage PIN authentication properties; for example, you can specify the minimum length for a PIN as well as determine whether you will allow PINs that use "common patterns" such as repeating digits (for example, a PIN like 11223344). PIN policies can be configured at the global or the site scope; in addition, PIN policies can be configured at the per-user scope and then assigned to a user or a specified set of users. In order to assign a per-user policy you must use the **Grant-CsPinPolicy** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Grant-CsPinPolicy** cmdlet locally: RTCUniversalUserAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Grant-CsPinPolicy"}

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
<td><p>Indicates the Identity of the user account to be assigned the per-user PIN policy. User Identities can be specified using one of four formats: 1) the user's SIP address; 2) the user's user principal name (UPN); 3) the user's domain name and logon name, in the form domain\logon (four example, litwareinc\kenmyer); and, 4) the user's Active Directory display name (for example, Ken Myer). User Identities can also be specified by using the user’s Active Directory distinguished name.</p>
<p>In addition, you can use the asterisk (*) wildcard character when using the Display Name as the user Identity. For example, the Identity &quot;* Smith&quot; returns all the users who have a display name that ends with the string value &quot; Smith&quot;.</p></td>
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
<td><p>Enables you to specify the fully qualified domain name of a domain (FQDN) controller to be contacted when assigning the new policy. If this parameter is not specified then the <strong>Grant-CsPinPolicy</strong> cmdlet will contact the first available domain controller.</p></td>
</tr>
<tr class="even">
<td><p><em>PassThru</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Enables you to pass a user object through the pipeline that represents the user being assigned the policy. By default, the <strong>Grant-CsPinPolicy</strong> cmdlet does not pass objects through the pipeline.</p></td>
</tr>
<tr class="odd">
<td><p><em>PolicyName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>&quot;Name&quot; of the policy to be assigned. The PolicyName is simply the policy Identity minus the policy scope (the &quot;tag:&quot; prefix). For example, a policy with the Identity tag:Redmond has a PolicyName equal to Redmond; a policy with the Identity tag:RedmondUsersPinPolicy has a PolicyName equal to RedmondUsersPinPolicy. To unassign a per-user policy previously assigned to a user, set the PolicyName to a null value ($Null).</p></td>
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

String value or Microsoft.Rtc.Management.UserPinService.PinInfoDetails object. The **Grant-CsPinPolicy** cmdlet accepts pipelined input of string values representing the Identity of a user account. The cmdlet also accepts pipelined input of user objects.

## Return Types

By default, the **Grant-CsPinPolicy** cmdlet does not return a value or object. However, if you include the PassThru parameter, the cmdlet will return instances of the Microsoft.Rtc.Management.ADConnect.Schema.OCSUserOrAppContact.

## 另请参阅

#### 其他资源

[Get-CsPinPolicy](get-cspinpolicy.md)  
[New-CsPinPolicy](new-cspinpolicy.md)  
[Remove-CsPinPolicy](remove-cspinpolicy.md)  
[Set-CsPinPolicy](set-cspinpolicy.md)

