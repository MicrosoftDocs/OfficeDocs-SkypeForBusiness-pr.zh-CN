---
title: Grant-CsClientPolicy
TOCTitle: Grant-CsClientPolicy
ms:assetid: c09d743d-cf2c-4622-b00c-cc815852e4a6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412942(v=OCS.15)
ms:contentKeyID: 49314123
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Grant-CsClientPolicy

 

_**上一次修改主题：** 2015-03-09_

Assigns a client policy to a user or a group of users. Among other things, client policies help determine the features of Lync Server that are available to users; for example, you might give some users the right to transfer files while denying this right to other users. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Grant-CsClientPolicy -Identity <UserIdParameter> [-Confirm [<SwitchParameter>]] [-DomainController <Fqdn>] [-PassThru <SwitchParameter>] [-PolicyName <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In Example 1, the client policy SalesPolicy is assigned to the user with the Identity Ken Myer.

    Grant-CsClientPolicy -Identity "Ken Myer" -PolicyName SalesPolicy

## EXAMPLE 2

In Example 2, all the users who belong to the Sales department are assigned the SalesPolicy client policy. The command first uses the **Get-CsUser** cmdlet and the LdapFilter parameter to return a collection of all the users who are members of the Sales department. This collection of users is then piped to the **Grant-CsClientPolicy** cmdlet, which assigns the policy SalesPolicy to each user in the collection.

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesPolicy

## EXAMPLE 3

In Example 3, the client policy RedmondAccountingPolicy is assigned to all the users who meet two criteria: 1) the user must have the job title Accountant; and, 2) the user must work in the city of Redmond. To do this, the command first uses the **Get-CsUser** cmdlet and the LdapFilter parameter to return a collection of all the users who work in Redmond and have the job title Accountant. The filter value "(&(Title=Accountant)(l=Redmond))" limits the returned data to users who have the job title Accountant (Title=Accountant) and (&) who work in Redmond (l=Redmond). (The "l" is a lowercase L, and represents the user’s locality.)

The resulting collection is then piped to the **Grant-CsClientPolicy** cmdlet, which assigns the policy RedmondAccountingPolicy to each user in the collection.

    Get-CsUser -LDAPFilter "(&(Title=Accountant)(l=Redmond))" | Grant-CsClientPolicy -PolicyName RedmondAccountingPolicy

## EXAMPLE 4

Example 4 assigns the policy AccountingPolicy to all the users who meet one of two criteria: either the user has the job title Accountant or the user has the job title Senior Accountant. To carry out this task, the **Get-CsUser** cmdlet and the LdapFilter parameter are used to return a collection of users with the job title Accountant or Senior Accountant. The filter value "(|(Title=Accountant)(Title=Senior Accountant))" limits the returned data to users with the job title Accountant (Title=Accountant) or (|) users with the job title Senior Accountant (Title=Senior Accountant). This filtered collection is then piped to the **Grant-CsClientPolicy** cmdlet, which assigns the client policy AccountingPolicy to each user in the collection.

    Get-CsUser -LdapFilter "(|(Title=Accountant)(Title=Senior Accountant))" | Grant-CsClientPolicy -PolicyName AccountingPolicy

## EXAMPLE 5

In Example 5 all the users with accounts on the Registrar pool atl-cs-001.litwareinc.com are assigned the client policy AtlantaBranchPolicy. To do this, the **Get-CsUser** cmdlet is first called to return the appropriate user accounts; the Filter parameter and the filter value {RegistrarPool -eq "atl-cs-001.litwareinc.com"} ensure that only user accounts homed on the Registrar pool atl-cs-001.litwareinc.com will be returned. This collection is then piped to the **Grant-CsClientPolicy** cmdlet, which assigns each user the client policy AtlantaBranchPolicy.

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsClientPolicy -PolicyName AtlantaBranchPolicy

## Detailed Description

In Lync Server, client policies replace the Group Policy settings used in previous versions of the product. In Microsoft Office Communicator 2007 and Microsoft Office Communicator 2007 R2, Group Policy helped determine what users could do with Communicator and other clients; for example, there were Group Policy settings that determined whether or not users could save a transcript of their instant messaging sessions; whether information from Microsoft Outlook was incorporated into their presence information; and whether or not users could include emoticons or formatted text in instant messages.

As useful as Group Policy is, however, the technology does have some limitations when applied to Lync Server. For one thing, Group Policy is designed to be applied on a per-domain or per-organizational unit (OU) basis; that makes it difficult to target policies toward a more select group of users (for example, all the users who work in a particular department, or all the users who have a particular job title). For another, Group Policy is only applied to users who log on to the domain and who log on using a computer; Group Policy is not applied to users who access Lync Server over the Internet or who access the system by using a mobile phone. This means that the same user can have a different experience depending on the device he or she uses to log on, and where he or she logs on from.

To help address these inconsistencies Lync Server uses client policies instead of Group Policy. Client policies are applied each time a user accesses the system, regardless of where the user logs on from and regardless of the type of device the user logs on with. In addition, client policies, like other Lync Server policies, can readily be targeted to selected groups of users. You can even create a custom policy that gets assigned to a single user.

Client policies can be configured at the global, site, and per-user scopes. In order to assign per-user policies to users, you must use the **Grant-CsClientPolicy** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Grant-CsClientPolicy** cmdlet locally: RTCUniversalUserAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Grant-CsClientPolicy"}

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
<p>In addition, you can use the asterisk (*) wildcard character when using the Display Name as the user Identity. For example, the Identity &quot;* Smith&quot; returns all the users who have a display name that ends in the string value &quot; Smith&quot;.</p></td>
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
<td><p>Enables you to specify a domain controller to connect to when assigning the policy. If this parameter is not included then the cmdlet will use the first available domain controller.</p></td>
</tr>
<tr class="even">
<td><p><em>PassThru</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>If present, causes the cmdlet to pass the user object (or objects) through the Windows PowerShell pipeline. By default, the <strong>Grant-CsClientPolicy</strong> cmdlet does not pass objects through the pipeline.</p></td>
</tr>
<tr class="odd">
<td><p><em>PolicyName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>&quot;Name&quot; of the policy to be assigned. The PolicyName is simply the policy Identity minus the policy scope (&quot;tag:&quot;). For example, a policy that has the Identity tag:Redmond has a PolicyName equal to Redmond; a policy with the Identity tag:RedmondConferencingPolicy has a PolicyName equal to RedmondConferencingPolicy.</p>
<p>If you set PolicyName to a null value, then the command will unassign any per-user policy assigned to the user. For example:</p>
<p>Grant-CsClientPolicy –Identity &quot;Ken Myer&quot; –PolicyName $Null</p></td>
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

String value or Microsoft.Rtc.Management.ADConnect.Schema.ADUser object. The **Grant-CsClientPolicy** cmdlet accepts pipelined input of string values representing the Identity of a user account. The cmdlet also accepts pipelined input of user objects.

## Return Types

By default, the **Grant-CsClientPolicy** cmdlet returns no objects or values. However, if you include the PassThru parameter, the cmdlet will return instances of the Microsoft.Rtc.Management.ADConnect.Schema.OCSUserOrAppContact object.

## 另请参阅

#### 其他资源

[Get-CsClientPolicy](get-csclientpolicy.md)  
[New-CsClientPolicy](new-csclientpolicy.md)  
[Remove-CsClientPolicy](remove-csclientpolicy.md)  
[Set-CsClientPolicy](set-csclientpolicy.md)

