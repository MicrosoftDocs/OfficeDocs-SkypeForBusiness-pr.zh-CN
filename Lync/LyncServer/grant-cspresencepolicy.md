---
title: Grant-CsPresencePolicy
TOCTitle: Grant-CsPresencePolicy
ms:assetid: 756c08a7-26b0-4ea8-816b-b33ebcac51aa
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398571(v=OCS.15)
ms:contentKeyID: 49313274
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Grant-CsPresencePolicy

 

_**上一次修改主题：** 2015-03-09_

Grants a per-user presence policy to a user or group of users. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Grant-CsPresencePolicy -Identity <UserIdParameter> [-Confirm [<SwitchParameter>]] [-DomainController <Fqdn>] [-PassThru <SwitchParameter>] [-PolicyName <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 assigns the per-user presence policy RedmondPresencePolicy to a single user: the user with the Identity Ken Myer.

    Grant-CsPresencePolicy -Identity "Ken Myer" -PolicyName "RedmondPresencePolicy"

## EXAMPLE 2

In Example 2, the presence policy RedmondPresencePolicy is assigned to all the users who have accounts in the Redmond OU in Active Directory 域服务. To do this, the command first uses the **Get-CsUser** cmdlet and the OU parameter to return a collection of all the user accounts found in the Redmond OU (OU=Redmond,dc=litwareinc,dc=com). This collection is then piped to the **Grant-CsPresencePolicy** cmdlet, which assigns the policy RedmondPresencePolicy to each user in the collection.

    Get-CsUser -OU "OU=Redmond,dc=litwareinc,dc=com" | Grant-CsPresencePolicy -PolicyName "RedmondPresencePolicy"

## EXAMPLE 3

Example 3 assigns the policy RedmondPresencePolicy to all the users who work in the city of Redmond. To carry out this task, the command first uses the **Get-CsUser** cmdlet and the LdapFilter parameter to return a collection of all the users who work in Redmond; the filter value "l=Redmond" limits the returned data to users from Redmond. (In the LDAP query language, l, the lowercase L, is short for "locality.") The retrieved collection is then piped to the **Grant-CsPresencePolicy** cmdlet, which assigns the policy RedmondPresencePolicy to each user in the collection.

    Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPresencePolicy -PolicyName "RedmondPresencePolicy"

## EXAMPLE 4

The command shown in Example 4 unassigns any per-user presence policy previously assigned to users who work in Redmond. Calling the **Grant-CsPresencePolicy** cmdlet while setting the PolicyName parameter to a null value ($Null) causes the cmdlet to remove any per-user presence policies assigned to the users affected by the command.

    Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPresencePolicy -PolicyName $Null

## Detailed Description

Presence information (which, among other things, lets you know whether a contact is available to take part in an instant messaging conversation) is invaluable. At the same time, however, there is a cost associated with presence information: the more presence subscriptions you have the more network bandwidth must be devoted to updating presence information. If network bandwidth is a concern, you might want to limit the number of presence subscriptions any one user can have.

The CsPresencePolicy cmdlets enable you to manage two important aspects of presence subscriptions: prompted subscribers and category subscriptions. When you are added to another person’s Lync Contacts list, the default behavior is for you to receive a pop-up notification informing you that you have been added to that list. Until you dismiss the pop-up, each notification counts as a prompted subscriber. The presence policy’s MaxPromptedSubscriber property enables you to specify the maximum number of unresolved notification dialogs a user can have. (If a user reaches the maximum amount, then he or she will not receive new contact notifications, at least not until some of those dialogs have been resolved.)

Category subscriptions represent a request for a specific category of information; for example, an application that requests calendar data. The MaxCategorySubscription property enables administrators to place a limit on the number of category subscriptions a user can have.

Prior to the release of Lync Server, prompted subscriber and category subscriptions were managed on a global basis. With the **CsPresencePolicy** cmdlets you can now manage these presence subscriptions at the global scope, the site scope, or the per-user scope. This enables you to control bandwidth use while, at the same time, ensuring that users have access to the presence information they need to do their jobs.

When you create a per-user policy, that policy is not automatically assigned to anyone. Instead, per-user presence policies must be explicitly assigned to users (or groups of users) by running the **Grant-CsPresencePolicy** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Grant-CsPresencePolicy** cmdlet locally: RTCUniversalUserAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Grant-CsPresencePolicy"}

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
<td><p>Indicates the Identity of the user account to be assigned the presence policy. User Identities can be specified using one of four formats: 1) the user's SIP address; 2) the user's user principal name (UPN); 3) the user's domain name and logon name, in the form domain\logon (for example, litwareinc\kenmyer); and, 4) the user's Active Directory display name (for example, Ken Myer). User Identities can also be specified by using the user’s Active Directory distinguished name.</p>
<p>In addition, you can use the asterisk (*) wildcard character when using the Display Name as the user Identity. For example, the Identity &quot;* Smith&quot; returns all the users with display name that ends with the string value &quot;Smith&quot;.</p></td>
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
<td><p>Fully qualified name of the domain (FQDN) controller to be contacted when assigning the policy. For example: -DomainController atl-dc-001.litwareinc.com.</p>
<p>If not specified, the <strong>Grant-CsPresencePolicy</strong> cmdlet will contact the nearest available domain controller when assigning the policy.</p></td>
</tr>
<tr class="even">
<td><p><em>PassThru</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Enables you to pass a user object through the pipeline that represents the user being assigned the policy. By default, the <strong>Grant-CsPresencePolicy</strong> cmdlet does not pass objects through the pipeline.</p></td>
</tr>
<tr class="odd">
<td><p><em>PolicyName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Identity of the per-user policy to be assigned; for example: -PolicyName &quot;RedmondPresencePolicy&quot;. The PolicyName is the Identity of the policy minus the &quot;tag:&quot; prefix. For example, a policy with the Identity &quot;tag:NorthAmericaPresencePolicy&quot; has a PolicyName equal to &quot;NorthAmericaPresencePolicy&quot;.</p></td>
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

String value or Microsoft.Rtc.Management.WritebleConfig.Policy.Presence.PresencePolicy object. The **Grant-CsPresencePolicy** cmdlet accepts pipelined input of string values representing the Identity of a user account. The cmdlet also accepts pipelined input of user objects.

## Return Types

By default, the **Grant-CsPresencePolicy** cmdlet does not return an objects or values. However, if you include the PassThru parameter, the cmdlet will return instances of the Microsoft.Rtc.Management.ADConnect.Schema.OCSUserOrAppContact.

## 另请参阅

#### 其他资源

[Get-CsPresencePolicy](get-cspresencepolicy.md)  
[New-CsPresencePolicy](new-cspresencepolicy.md)  
[Remove-CsPresencePolicy](remove-cspresencepolicy.md)  
[Set-CsPresencePolicy](set-cspresencepolicy.md)

