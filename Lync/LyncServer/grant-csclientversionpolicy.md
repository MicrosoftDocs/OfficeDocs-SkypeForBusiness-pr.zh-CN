---
title: Grant-CsClientVersionPolicy
TOCTitle: Grant-CsClientVersionPolicy
ms:assetid: b94d9473-db5f-4350-a7b4-991d0e26e525
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412903(v=OCS.15)
ms:contentKeyID: 49314064
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Grant-CsClientVersionPolicy

 

_**上一次修改主题：** 2015-03-09_

Assigns a client version policy at the global, site, service, or per-user scope. Client version policies enable you to specify which clients (such as Microsoft Office Communicator 2007 R2) will be able to log on to your Lync Server system. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Grant-CsClientVersionPolicy -Identity <UserIdParameter> [-Confirm [<SwitchParameter>]] [-DomainController <Fqdn>] [-PassThru <SwitchParameter>] [-PolicyName <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In Example 1, the client version policy RedmondClientVersionPolicy is assigned to user Ken Myer.

    Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## EXAMPLE 2

The command shown in Example 2 assigns the client version policy RedmondClientVersionPolicy to all the users who work in the city of Redmond. To do this, the command first uses the **Get-CsUser** cmdlet and the LdapFilter parameter to retrieve the appropriate collection of user accounts; the filter value "l=Redmond" (where "l" is the lowercase letter L, the LDAP attribute name for "locality") limits data retrieval to users who work in the city of Redmond. This collection is then piped to the **Grant-CsClientVersionPolicy** cmdlet, which assigns the specified policy to each user in the collection.

    Get-CsUser -LdapFilter "l=Redmond" | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## EXAMPLE 3

In Example 3, all the users in a specific organizational unit (OU) are assigned the client version policy RedmondClientVersionPolicy. To accomplish this task, the command first calls the **Get-CsUser** cmdlet and the OU parameter; the parameter value represents the distinguished name of the OU in which users are to be assigned the client version policy (ou=Redmond,ou=North America,dc=litwareinc,dc=com). After the user accounts have been retrieved, the collection is piped to the **Grant-CsClientVersionPolicy** cmdlet, which assigns RedmondClientVersionPolicy to each of those users.

    Get-CsUser -OU "ou=Redmond,ou=North America,dc=litwareinc,dc=com" | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## EXAMPLE 4

Example 4 assigns the client version policy RedmondClientVersionPolicy to all of the users who have previously been assigned the voice policy RedmondVoicePolicy. To do this, the command first calls the **Get-CsUser** cmdlet along with the Filter parameter; the filter value {VoicePolicy -eq "RedmondVoicePolicy"} ensures that the only user accounts returned are those where the VoicePolicy property is equal to "RedmondVoicePolicy". The resulting user accounts are then piped to the **Grant-CsClientVersionPolicy** cmdlet and assigned the client version policy RedmondClientVersionPolicy.

    Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## EXAMPLE 5

In Example 5, all the users in the organization are unassigned any per-user client version policies previously assigned to them. To do this, the command first uses the **Get-CsUser** cmdlet to return a collection of all the users in the organization who have been enabled for Lync Server. This collection is then piped to the **Remove-CsClientVersionPolicy** cmdlet, which removes any per-user client version policies assigned to those users. This is done by setting the parameter value of PolicyName to $null.

    Get-CsUser | Grant-CsClientVersionPolicy -PolicyName $Null

## Detailed Description

Client version policies represent a collection of client version rules; in turn, client version rules are used to determine which client applications are allowed to log on to Lync Server. When a user attempts to log on to Lync Server his or her client application sends a SIP header to the server; this header includes detailed information about the application itself, including the software’s major version, minor version, and build number. The version information included in the SIP header is then checked against a collection of client version rules to see if any rules apply to that particular application. If such a rule exists, Lync Server will then take the action specified by the rule. For example, the rule might tell Lync Server to allow the logon, to block it, or to allow the logon but then silently update the client application to the latest version (for example, update Office Communicator 2007 R2 to Lync 2013).

Client version policies, which can be applied at the global scope, the site scope, the service scope (Registrar service only), or the per-user scope, give you flexibility in determining which client applications can be used to access the system. For example, you might want to prevent users from logging on to Lync Server by using Communicator 2007 R2 because this older client application does not support the same features and capabilities as Lync. However, due to hardware or software conflicts, you might also have a select group of users who cannot upgrade to Lync. In that case, you can create a separate rule -- and a separate client version policy -- that allows those users to log on from within Communicator 2007 R2.

The **Grant-CsClientVersionPolicy** cmdlet enables you to assign client version policies to individual users. When you create a per-user policy, that policy is not automatically assigned to anyone; assignment does not take place until you call the **Grant-CsClientVersionPolicy** cmdlet to explicitly assign the policy to a user or set of users.

It’s important to note that client version policies do not apply to federated users; instead, federated users are bound by the client version policies used in their own organization. For example, suppose a federated user uses client A, a client allowed by the federated organization. As long as the federated organization allows the use of client A, this user will be able to communicate with your organization using that client. This will be true even if your client version policy blocks the use of client A. Client version policies enforced in your organization do not override the client version policies used in a federated organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Grant-CsClientVersionPolicy** cmdlet locally: RTCUniversalUserAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Grant-CsClientVersionPolicy"}

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
<td><p>Indicates the Identity of the user account the policy should be assigned to. User Identities can be specified by using one of four formats: 1) the user's SIP address; 2) the user's user principal name (UPN); 3) the user's domain name and logon name, in the form domain\logon (for example, litwareinc\kenmyer); and, 4) the user's Active Directory display name (for example, Ken Myer). User Identities can also be referenced by using the user’s Active Directory distinguished name.</p>
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
<td><p>Enables you to specify a domain controller to connect to when assigning the policy. If this parameter is not included, then the cmdlet will use the first available domain controller.</p></td>
</tr>
<tr class="even">
<td><p><em>PassThru</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>If present, causes the cmdlet to pass the user object (or objects) through the Windows PowerShell pipeline. By default, the <strong>Grant-CsClientVersionPolicy</strong> cmdlet does not pass objects through the pipeline.</p></td>
</tr>
<tr class="odd">
<td><p><em>PolicyName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>&quot;Name&quot; of the policy to be assigned. The PolicyName is simply the policy Identity minus the policy scope (&quot;tag:&quot;). For example, a policy with the Identity tag:Redmond has a PolicyName equal to Redmond; a policy with the Identity tag:RedmondClientVersionPolicy has a PolicyName equal to RedmondClientVersionPolicy. To unassign a per-user policy previously assigned to a user, set the PolicyName to a null value ($null).</p></td>
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

String value or Microsoft.Rtc.Management.ADConnect.Schema.ADUser object. The **Grant-CsClientVersionPolicy** cmdlet accepts pipelined input of string values representing the Identity of a user account. The cmdlet also accepts pipelined input of user objects.

## Return Types

By default, the **Grant-CsClientVersionPolicy** cmdlet does not return objects or values. However, if you include the PassThru parameter, the cmdlet will return instances of the Microsoft.Rtc.Management.ADConnect.Schema.OCSUserOrAppContact object.

## 另请参阅

#### 其他资源

[Get-CsClientVersionPolicy](get-csclientversionpolicy.md)  
[New-CsClientVersionPolicy](new-csclientversionpolicy.md)  
[Remove-CsClientVersionPolicy](remove-csclientversionpolicy.md)  
[Set-CsClientVersionPolicy](Set-CsClientVersionPolicy.md)

